## Implementation conducted 
- Created the scaffolding for the bubble dashboard react app
- Worked on various "polishing" issues
  - Made messages in CLI and on Github more consistent and friendly :joy: and extracted them to a messages file
  - Installed eslint and adjusted code to adhere to airbnb JavaScript style guide
  - Updated workflow file names
- Adjusted bubble framework to create a `activeRepos.json` file to be stored in the user's `.bubble` (outside of the project root) folder
    - This is for the purpose of storing data locally that the bubble dashboard will be able to pull from 
- Moved the Lambda table creation to the deployment workflow
- Probably some other pretty random bugs and refactors that we worked on independently :grin:

##  Questions/problems collected
- We decided to keep the dashboard app local; going to make it available via a `bubble dashboard` command from the CLI
- Based off of that, we thought we would just need a React client only but...
	- The aws cli cannot be accessed directly from client side
	- So `bubble dashboard` will then spin up another server on another port
	- Ideally the dashboard can display a navigation of all bubble repos?
		- It would then list each repo and all preview apps for each repo
  - Should we pull the GH actions build logs to view logs for each preview app on the dashboard?
		- This is seeming doable ATM since GH's api has been good to work with thus far
		- Is streaming them an option? (throwback to durable objects!)

## Todos
- Continue working on GH issues
- Continue adding dashboard functionality
- Refactor existing framework code
- Write framework `README`
- Write basic framework unit tests
