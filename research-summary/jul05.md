## Research conducted
- Deployed Next app using Terraform as an alternate automated option
  - Used v0.x, which supports environment variables, but does not support atomic deployments
  - While it seems subsequent builds are somewhat optimized (i.e. first build took 13 minutes, second took 4.5 minutes, and third took 2 minutes), each new build is not a new deployment and will keep the same URL, so presumably, if we want a new URL for each new build, we'd potentially have to go through the full 10+ min process each time
  - There seemed to be potential issue with spaces in the route names, though this may have also just been attributed to the way the specific example app we were using was coded up in terms of not explicitly URL encoding each path name
  - The Terraform version we used only supports up to Next version 11, so any Next apps using version 12 would have to be downgraded to 11
  - Ran into issue re' serverless quotas/reserved concurrent executions - we're thinking this wouldn't be an issue if we use Terraform v1 since it supports atomic deployments, but then we'd potentially have an issue with that version not supporting environment variables
- Used Github Actions to deploy Next app with Serverless framework
- Started working on creating new Next test app with statically generated blog and multiple SSR routes (that need to get data from database via API call and also that uses environment variables) as another app to test deployment with

## Problems/Questions
- Is there further guidance on how we should model our case study/writeup in terms of specific sections required? And how much does our current project narrative feed into our final writeup? Also, in terms of the downsides of preview apps we've researched, how much do we need to get into that in our writeup, or is that more just for our own knowledge?
- If we're not able to create a .env file from the Github Secrets and inject into our deployment environment, what would be the best workaround option to access environment variables securely if the logic of the code requires it, and in a way where no part of the user's code would have to be changed? 
- This was an issue we had encountered last week, but potentially will have to look into some more re' making sure base URL for API calls is valid

## Helpful Links
- https://github.com/milliHQ/terraform-aws-next-js
- https://milli.is/blog/why-we-self-host-our-serverless-next-js-site-on-aws-with-terraform
- https://milli.is/blog/the-road-to-atomic-deployments
- https://github.com/milliHQ/terraform-aws-next-js/blob/v0.x/docs/known-issues/0001_reserved-concurrent-executions.md
- https://github.com/milliHQ/terraform-aws-next-js/issues/251
- https://stackoverflow.com/questions/54828808/aws-lambdaedge-nodejs-environment-variables-are-not-supported 
- https://dev.to/aws-builders/dynamically-configure-your-lambda-edge-functions-2pkp
- https://docs.aws.amazon.com/secretsmanager/latest/apireference/Welcome.html
	
##  Todos/Next Steps
- Outline and split up sections for first part of the writeup
- Finish working on new Next test app - get connection to MongoDB working
- Look into how we'll create IAM users with the necessary privileges on the customer's behalf
- Continue prototyping other pieces of our project
