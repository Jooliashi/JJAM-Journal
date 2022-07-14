## research conducted 
- completing workflow files for deleting preview apps when pull request close and when user issue `bubble destroy`
- completing bubble `list` to see all the pull requests 
##  problems collected and Todos
- need to identify the absolute path for repo so the user does not need to issue command from root folder all the time
- need to add AWS region to github secrets as we need it to configure the command line on github server
- need to create new aws command line profile and issue requests from there so that the default profile is not touched.
- need to figure out how to delete Lambda functions after cloudfront is torn down
- set additional wait logic to make sure the AWS user is created before creating the database.
- need to implement deleting config and credentials for `bubble destroy`
- need to determine the branch name for workflow file location when `bubble destory`  is called.