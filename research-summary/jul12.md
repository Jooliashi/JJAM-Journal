## research conducted 
- Cleaned up shared repository together and merged branches for changes made in regards to DynamoDB add.
- Worked on editing `delete_preview_app` (we can re-consider the file name now that this is actually deleting all preview apps for a pull request instead of a single preview app ;)) workflow file that should be triggered either by workflow dispatch or automatically upon closing of a pull request. This workflow deletes all preview apps associated with the relevant pull request - retrieves and removes all of the relevant S3 bucket and CloudFront distro information from DynamoDB for all preview apps related to the particular pull request, determines and removes all Lambdas associated with the CF distros, and soft deletes the pull request entry from DynamoDB so that it's marked as an inactive PR.  
- Worked on `bubble destroy` command that deletes the IAM user, all preview apps associated with all pull requests of the repo, Github Secrets access keys that were added by `bubble init`, the DynamoDB table, and all Bubble-related files in user's local directory.

##  questions/problems collected
- Upon `bubble destroy`, what workflow files that we had added during `bubble init` should be removed for the user
  - Decided to delete the local workflow files on the user's machine, but not from the remote repo itself - after the local workflow files are removed, the user can just make another push to their Github repo to clear out if any workflow files still live there
- Upon deletion of a CloudFront distro, replicated Lambdas are supposed to be automatically deleted eventually, but based off experience, it's seemed like some have still had to be manually deleted
  - In order to ensure everything is truly removed, when destroying all the resources related to each preview app, we have to determine all relevant Lambdas including potential replicated ones, and issue a command to delete each one. In addition, before each replicated Lambda is deleted, its associated CloudFront distro must be deleted first
- Should `bubble destroy` iterate through each pull request and dispatch the workflow for deleting preview apps for each pull request from the logic of the function itself, or can it dispatch a single workflow that will itself dispatch the workflows for deleting preview apps for each pull request
  - Decided on the latter for consistency and potential performance advantage - the logic of `bubble destroy` will parse out all active pull requests, and will pass this information along to a workflow. That workflow will then iterate through the pull requests, and dispatch the workflow for deleting preview apps related to a particular PR
- Should we separate out the functionality for deleting a "bundle" (i.e. set of resources (S3 bucket, CF distro id, lambdas) related to a single preview app) to a separate workflow file
  - Originally, we were keeping functionality of deleting all resources related to all preview apps for a pull request within one workflow (i.e. iterating through all of these resources and deleting all S3 buckets first, then CF distros, then lambdas) - however, given that destroying AWS resources can take quite some time (in particular, deleting CF distros) and to avoid issues around time limitation when it comes to GH Actions, we decided to separate out the functionality of deleting a "bundle" to an isolated workflow file, so that each preview app resources deletion can be run on its own. Within the workflow for deleting all preview apps for a PR, we will iterate through each preview app (and its relevant resources), and for each, will dispatch the workflow for deleting each bundle
- There were a few nuances that proved a bit tricky iterating through a space-delineated list in bash and running commands for each item in the list
- Testing workflow file changes can get a bit tedious/messy, particularly when testing the workflow for deleting a preview app, as this required ensuring some preview apps were first created for our PRs, as well as a cycle of closing PRs and subsequently re-opening them (in order to be able to close them again to test a change)

### Todos
- Finish working on functionality to delete preview apps for a particular pull request
- Once we are confident in workflow for deleting preview apps for one pull request, we can test out full flow with `bubble destroy` to delete preview apps for all pull requests 
- Since we're potentially adding two new workflows, these will need to be added to the user's workflows folder upon `bubble init` as well 
- Start working on `bubble list` command