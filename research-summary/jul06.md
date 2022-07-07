## research conducted 
- How to export all repo secrets through github actions
- What's going on in Lambda functions; How many Lambda functions are created for API routes and SSR routes.
- created Mock next.js project including multiple SSR routes

##  problems collected
- how to deploy env with serverless framework
	- we have found a github action package to be used, which exports all Github Secrets into environment variables. The deployed application will be able to maintain those variables.
- Mock next.js project database access
	- directly connecting to Mongo database with access key as an env

## Notes on the write up:
- > Hey Missy! Good questions all around. It'll be more like B, and we've got instructions on the write up queued up for the cohort to be released around week 12. I believe your project is more like a product/framework hybrid (correct me if I'm wrong). I'd recommend reading a few past project writeups to get a good idea of the flow. Projects that I think would be good are probably Stagehand and Beekeeper, as those kind of fit this hybrid space. I'm including a part of the instructions that would be helpful for you now below. I think the big things are to:

-   start to craft your problem setup, narrative, use case
-   make sure transitions between sections are smooth and logical
-   start to file away design decisions and technical challenges as you encounter them. Sometimes teams go through the project, forget to write any of this down, and then struggle when they need to start putting their writeup together

- Recall that we said the primary deliverable in Capstone is your case study write up. Given how important this is, it's time to start mapping your technical journey to the narrative. As you embark on this task, we want to give you some ways to think about the narrative.

Typically, Capstone Projects fall into two major types: Product and Framework. 

Product Narratives
The product narrative is usually pretty straightforward: a chronological "how we built this" journey of how each problem was resolved. The hard part is to not be enslaved by the chronology, but to craft a technical journey. It's also important to outline solutions considered but not implemented. Another important factor is to take time to explain the background and context certain technologies (solutions) used to solve problems; be ok with tangents where appropriate. Most product narratives spend some sections setting up the background for what the product is doing. The overall narration arc, however, is sequential.

Examples:

    [https://redpoint-notebooks.github.io/https://spacecraft-repl.comhttps://prefixy.github.iohttps://conclave-team.github.io/conclave-site/](https://redpoint-notebooks.github.io/https://spacecraft-repl.comhttps://prefixy.github.iohttps://conclave-team.github.io/conclave-site/)

Framework Narratives
The framework narrative deviates from the product narrative a little bit. Usually, it doesn't get into the "how we built this" immediately. In fact, that chronological journey typically only makes up 1/3 of the entire case study. Instead, frameworks have to spend an exorbitant amount of time setting up the problem and context. 

Frameworks are typically productivity enhancements for a particular workflow that solves some niche problem. Therefore, before we can even talk about the framework and how its built, we have to first set up context for the problem. That is, first we have to convince people this is a real problem worth addressing. That's half the battle.  Only after that is achieved can we start to talk about how the framework solves said problem. And then finally, only then can we talk about how the framework is built.

Summary of example framework narrative:

    Problem set up
    Solution set up (our framework)
    How it's built


Example: Below is the breakdown of BAM, a serverless framework

    Introduction 
        148 words 
    Serverless 
        2110 words 
        Background on what serverless is; Intro relevant AWS services; challenges of manually creating services using AWS API Gateway and Lambda 
    Frameworks
        563 words 
        Pros/cons list of existing solutions (frameworks) and how BAM fits into solution space
    BAM Framework and Design 
        555 words 
        List of CLI commands and some features 
        Notice it still doesn't get into "how it's built" (this section is misnamed, imo since it just lists CLI commands) 
    Behind the Scenes 
        1078 words 
        still very little "how it's built" but more of "how BAM automates work for the developer", so more of a "how BAM does the magic" 
    Challenges 
        1952 words 
        Finally some more of "how it's built", but it's not listed as a "journey" but they're categorized under challenges faced. The "journey" narrative is better suited for product oriented projects, like Spacecraft. 


Notice that they spent over 4000 words before getting into "how it's built", because they have to set up the problem for people to appreciate the story of how its built. You don't need to spend 4000 words, but the idea is that setting up the problem context is really important. Side note: we actually feel they don't get into the "how it's built" enough in their case study, but in general, the setup is very good and they don't give the impression it's a school project trying to impress; it looks like a production-ready project built by professionals. 

Try do to this type of breakdown analysis for a few of the other Framework projects and see how they match up with BAM. Your total writeup word count should probably be around 6500-7000 words.

Examples:

    [https://jolt-framework.github.io/https://getdendro.com/case-studyhttps://chronos-project.github.iohttps://turtle-db.github.io](https://jolt-framework.github.io/https://getdendro.com/case-studyhttps://chronos-project.github.iohttps://turtle-db.github.io)
	
	
### Using Serverless Framework
- There are limitations within the framework itself which we should declare in the write up
- https://www.serverless.com/plugins/serverless-nextjs-plugin AWS permission setup
- By design, there is only one Lambda function for all API routes and one Lambda for all page routes

### Todos
-   Figure out how to build using code from current branch
-   Possibly find another app or two to try deploying in the same way
-   Figure out first steps for creating an `npm` package (would we do something like a `cricket init` to create the initial workflow file and `serverless.yml`?)
-   Decide what data to store about the deployments in our Cricket architecture
-   Figure out how we tear down apps when the branch closes (or when some other event or expiration date occurs, option to manually teardown available?)
-   Create and test IAM user/role with only the permissions needed per the serverless documentation
-   Possibly brainstorming about the dashboard --> next steps there??