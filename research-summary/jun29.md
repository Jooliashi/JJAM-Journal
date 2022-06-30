## Research conducted
- Met with Daniel and discussed comments he made on our project narrative outline and walked him through updates to our proposed architecture in regards to questions he posed to us on Monday
  - Major takeaways:
    - language around hybrid SSG/SSR use case should be clear we're describing one application (stored in one repository) that uses both
    - we could tweak our story to add interest, i.e. describe a site that started off statically generated and wants to build in more dynamic content so they're adding SSR to part of their app - they currently have their own existing review app solution that only supports SSG sites, and they want to continue to own their own data, but as their needs are changing, what solutions are out there so they don't lose their review app capability? 
    - we should be more specific about the type of team or developer we're targeting/best suited for (i.e. what tech stack they're using/what the frameworks they're using support, size of team)
    - be clear around language re' "fully ephemeral" and "fully self-contained" to avoid potential confusion as we're setting things up in our narrative
    - it's ok to start off with support for one framework (i.e. Next) and go from there - it's more important to have our solution working well for one framework than it is to try and support everything
    - understand how existing review app solutions handle DB API access
    - we could continue exploring what it looks like to host an app (i.e. a Next or Gatsby app) using serverless functions to gain a better understanding of how well they fit to our use case
- Deployed a hybrid SSG and SSR Next.js app to AWS Lambda@Edge

## Questions
- What are the use cases for serverless functions if not for SSR?
- Do we need to consider 15-minute execution timeout aspect of serverless functions? Would it be better to use traditional app servers for the review app backends?
- Re' the fact that the deployment of the Next.js app with the Serverless framework took around 4-5 min, is this normal? And if so, are there potential limitations/challenges we can foresee with larger/more complex apps?
- How can we restrict the access level for the created IAM user further for better security purposes, so that they only have the minimum access needed to the relevant AWS resources (i.e. Lambda, Cloudfront) 
- Is using the Serverless framework for deployment of Next.js apps too easy? ;)

## Interesting/Useful links:
- https://css-tricks.com/serverless-functions-the-secret-to-ultra-productive-front-end-teams/#:~:text=Using%20serverless%20functions%20allows%20front,creates%20risk%20and%20decreases%20productivity
- https://backbencher.dev/articles/hosting-nextjs-aws-lambda-serverless
- https://blog.logrocket.com/deploying-nextjs-aws-serverless-next-js/
- https://dev.to/dabit3/next-js-ci-cd-on-aws-with-github-actions-3502
- https://github.com/serverless-nextjs/serverless-next.js
	
##  Todos/Next Steps
- In light of SSR route now not working with deployed Next.js app, look further into source of issues there
- Research downsides of review apps
- Clarify/refine our use case, and make adjustments to our Project Narrative to address Daniel's comments
- Continuing to try out deploying apps based off potential use cases with our proposed review app architecture
  - Starting off with app built using Next.js framework, but could explore others as well (i.e. Gatsby)
  - Based off potential customer having an app that fetches data from database via an API call, we could add functionality like this to our Next app, and deploy that
  - We could include the use of environment variables within the app code to explore that further as well
  - We could also try using Github Actions to deploy the Next app to Lambda (there's a tutorial for this as well that we took a brief look at, linked above)
- Continue exploring implementation of other pieces of our project, i.e. storing each of these deployed review apps, building out dashboard, how we should access user's AWS account to create IAM credentials/provision resources for them, etc.
