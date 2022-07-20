## Implementation Completed
- Added `destroy` and `teardown` functionality to dashboard
- Connected framework to dashboard, so that upon running `bubble dashboard`, the dashboard app (whose code lives in the user's home `.bubble` folder, added with packages installed during `bubble init`) will be started up
  - We wanted to display clear messaging to the user for this process of the dashboard starting up, so once we detect that the React app has started up, we display to the user the URL of the dashboard that they can click into
  - While the dashboard has navigation to view all Bubble repos, we wanted the main page the user is initially brought to to be specific to the repo they ran `bubble dashboard` from. We discussed how to pass the information of what the current repo is to the dashboard code, and decided that the URL displayed to the user through the `bubble dashboard` command will include as its path the repo, i.e. http://localhost:3000/repo-name
  - For this reason, we've also decided to suppress the automatic opening up of the browser upon the React app starting up so that we can display the proper URL with the repo name path
  - Various error checking for issues/edge cases encountered while testing was added to this functionality as well, though more may come as we continue testing
- Organized workflow files
- Cleanup of framework code with ESLint
- If the user runs `teardown` too soon after `destroy`, we encountered an error where the Lambdas table wasn't even ready yet, because we had been creating/populating it during our workflow for app removal
  - Decided to move the responsibility of creating the Lambdas table (if it had not already been created previously) and populating it with the Lambda prefixes to the workflow dealing with preview app deployment instead. This way, we know for sure that the Lambdas table will always be ready and populated whenever the user wants to run `teardown`, and the change shouldn't affect much else, since we're still able to easily get/store all of the relevant Lambda prefixes during the deployment stage that we'd need during the teardown stage.

## Questions/Issues
- We had discussed potentially adding the ability for users to view the build logs of the preview apps in the dashboard, but loading the logs may prove a bit more difficult than we had anticipated
  - There is a GH command we can use to retrieve the logs, but it seems to require a `run-id`, which we'll need get from the workflow. Planning on digging into this some more after the rest of the functionality is all set and tested.
- Ran into an interesting bug where executing `bubble dashboard` for the first time in a repo was not displaying our messaging with the dashboard URL (even if the dashboard app was indeed ready to be viewed), but subsequent executions were
  - Will be testing/digging into this further, but for now, noticed that a contributing factor to this could be an error that seems to occasionally occur re' the server port number
  - For now, we've implemented a catch for if the user is left hanging re' messaging - after 15 seconds, if the user has not been displayed the link to view the dashboard, we do a double check if the dashboard is actually available to be viewed, and if so, display the URL message to the user, and if not, end the process and have them try running the command again
- Is there a way to potentially discourage the user from trying to `teardown` too soon, particularly on the dashboard side/can we disable the teardown button for a certain period of time or until at least one/some Lambdas are actually ready to be deleted? Have we overlooked any possibility of being able to know when/whether a Lambda is ready to be deleted (probably not, but just a thought we were wondering)?

## Todos
- Continue working through our list of Github Issues on both framework and dashboard sides
- Continue polishing up framework code
- Continue testing framework and dashboard together
- Add visual styling to dashboard
- Write basic unit tests for CLI and dashboard
- Write README
- Potentially add build log viewing functionality to dashboard
