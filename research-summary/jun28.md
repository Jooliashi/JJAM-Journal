## Research conducted
- We decided that, in our proposed architecture, **any persistent data needed by the application needs to be fetched over the internet via API calls**
  - These API calls can be made either by the server-side code
  - Or by scripts running in the client's browser, that were served as static assets
- We walked through our proposed architecture with two user stories:
  1. logging in to a statically-generated login page
  2. serving a user-specific shopping cart page rendered using SSR
- We all but determined that users should input any secrets (e.g. environment variables) to GitHub, and that under the hood the GitHub actions workflow would be able to interrogate a user's account for those secrets when deploying the review app
  - Then the environment variables will be in the global scope of the deployed server's environment
  - If we were to have the user input the secrets to the Cricket dashboard instead, repeated API calls to Cricket services would need to be made

## Questions
- How do different databases authenticate? Would best practice be to whitelist all IPs attempting to connect to a particular DB? Is that something that we mandate since our review app IPs can't be determined ahead of deployment?
- Is "whitelisting URLs" a thing?
- Is there any need to store environment variables in client-side JavaScript? Is this a huge security risk?
- Once the environment variables are provided by the review app user, how do we pass them along to the cloud provider deploying the review app itself?
- Is FAB still a viable option?

## Interesting/Useful links:
- https://blog.logrocket.com/deploying-nextjs-aws-serverless-next-js/
- https://stackoverflow.com/questions/71090120/aws-serverless-with-nextjs-only-deploy-s3-and-cloudfront
- https://dev.to/aws/deploy-a-next-js-app-to-aws-amplify-3571
- https://dev.to/dabit3/next-js-ci-cd-on-aws-with-github-actions-3502
- https://aws.amazon.com/getting-started/hands-on/build-serverless-web-app-lambda-apigateway-s3-dynamodb-cognito/
- https://dev.to/windupbird/try-to-use-ruby-and-sinatra-app-with-aws-lambda--44f7
	
##  Todos/Next Steps
- In service of proposing an architecture...
- Big todo: see if we can deploy apps in such a way as to mirror our proposed review app architecture
  - We should deploy a completely SSG app, a completely SSR app, and a hybrid
  - This todo breaks out into smaller todos:
    1. Deploy just the server-side logic to a serverless function provider (AWS Lambda)
      - We probably need to first familiarize ourselves further with AWS Lambda and S3
    2. Deploy the assets for a static website to an S3 bucket
    3. Find real life code for apps that make use of both SSR and SSG
    4. Determine how to separate SSR and SSG code so we can deploy it separately