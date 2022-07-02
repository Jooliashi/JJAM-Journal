## Research conducted
- Met with Daniel to update him on our experiences thus far with trying to deploy an example Next app using Serverless framework and Fab. 
  - Major takeaways:
    - similar to limiting frameworks we support, it's also ok if we only support certain versions of frameworks
    - also keep in mind that it takes people time to upgrade versions/not everyone is using the most current version of a framework, so it wouldn't be the end of the world if we can't support the latest version
    - conversations we'll have about our project with prospective employers will be more around the architecture of our project and the high-level problem it solves
    - it's ok if our project consists of connecting other tools/it's normal to feel like our project is "too simple". The project as a whole isn't just about coding something up and deploying it - it also includes all of the time spent driling down on the problem domain and the research involved.
    - all of the actions we didn't take/things we didn't use but researched will still be valuable in the end, because it's all about the narratives and the tradeoffs. It's ok if the end project is straightforward with not too many components, what's important is how we got there. 
    - we should continue prototyping and trying to deploy things ourselves/gain more experience/understanding in this area. After this, we could think about how a user might interact with our service, and what parts we should automate. We can then talk about what features we'd want to add/not add/what will make the project more interesting with the least amount of extra work. ;) 

## Problems/Questions
- If we don't use Fab or the Serverless framework, how would we deploy a Next app to AWS Lambda and S3 manually? What are other helpful options in this space?
- If we end up using the Serverless framework, we may need to be mindful of the version we're using.
	
##  Todos/Next Steps
- Gain better understanding of how the Serverless framework is working under the hood, since so much is abstracted away from us
- Continue with our deployment journeys :) This may include further exploration on method of deployment, as well as variation in app we're deploying beyond the example Next app we've been using (i.e. apps that interact with a database via API calls, apps that require the use of environment variables, apps of varying sizes and framework versions, etc.) 
- Continue prototyping other pieces of our project
