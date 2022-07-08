## Research Conducted/Work Accomplished
  - Brainstormed tear down (possibility of using serverless framework’s method or doing it more manually; currently leaning toward doing it manually bc of a simpler implementation with fewer files to work with on the GitHub action serverless function)
  - Learned about how we can tear down resources: AWS CLI, ARNs (unique AWS ID for resources)
    - Identified pattern for AWS deployments so that we can identify resources associated with a given deployment
  - Began discussing architecture/thinking about data layer
  - Discussed potential features for CLI app as well as cloud dashboard
  - Continued fleshing out problem statement and use case for write-up outline
  - Brainstormed flow of data and user actions both from the CLI and dashboard
  - Began work on automating IAM interaction for AWS user/role/permissions management
  - Created and published an npm package which can be installed and run its  `init` command
  - Validated that we can trigger GitHub actions via `POST` request and pass in values to be used in the workflow files
  - Potential app name!
    - Bubble

##  Problems Collected
- Need to ensure AWS lambda function teardown
	- May be torn down automatically after CloudFront distribution teardown; TBD

## Next Steps
- Continue drafting and refining narrative
- Continue considering architecture and design for our Bubble app (storing necessary data, app server, dashboard)
- Continue specifying CLI functionality and adding features to our node package
- Test teardown when automated from a GitHub action (triggered from a POST request to GitHub) and then from our CLI
- Further specify data needs for preview app deployments/tear downs as well as the potential user dashboard
- Validate that “replicated function” lambdas will automatically teardown after their associated CloudFront distribution is torn down
