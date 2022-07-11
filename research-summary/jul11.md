## research conducted 
### Main topic of the day: how to store preview app data
- First decision of the day, starting where we left off on Friday: **do we keep data about all review apps for a repo locally on a user's machine or have a per user database provisioned through IAM** started with the assumption that we'd use AWS Aurora
	- We explored the option of saving data on a file that would be stored on the user's local file system, which seemed simpler
  - The question was then: do we create such a file on a per-user or a per-repo basis?
  - **Per user** would mean that we'd have to store the file outside of the project directory
    - Pros
      - By running something like `bubble list`, you could see a holistic view of all previews for all repos, but this seems like a bit of a contrived need
      - It would be harder to accidentally delete, and this is a good thing since it would be our one source of truth for all of the preview app data; it's not something we could reconstruct for a user
    - Cons
      - A little bit more complex to find and write/read to the file
      - If it were accidentally deleted, it would take down preview apps for ALL repos instead of just one
  - **Per repo** would mean that we'd store the file in the project directory
    - Pros
      - Easier to find and read/write to the file
      - Makes more sense semantically, since perhaps only the project should even concern itself with `bubble` data
      - If it's accidentally deleted, the source of truth for all preview app data dies

... but then we realized... when a preview app is created via Github actions... _we cannot access the local file with all the data_ :joy:

### We decide to go with a database

... so the decision was made for us that **we would provision a database on the user's AWS account.**

### Deciding on database provider, level and type
#### Provider
Why AWS? Since we're starting small for our MVP, just sticking with one cloud provider seems like a good option, at least for now; AWS has by far the greatest market share and offers a very wide range of microservices which we can customize as needed for our purposes.

#### Database at what level (user or repo)
- So we asked, "do we create a database for each user? or for each repo?"
	- We decided to keep things at the repo level; we're already using one set of access kes per repo to deploy preview apps anyway

#### AWS RDS
- Assuming we use a relational database... do we use AWS Aurora or RDS?
	- RDS is small fry and less expensive: https://www.reddit.com/r/aws/comments/am6psr/aurora_vs_rds_whats_the_difference/
	- MySQL or Postgres? we're more familiar with Postgres
- We then tinkered around with AWS RDS, and found it pretty complex
  - AWS RDS databases need to be created in a virtual private cloud
  - This would add some additional complexity around adding and removing security groups with the right permissions before and after we accessed the db from Github Actions (if we didn't want to whitelist all IPs)
  - Just trying to create and connect to a database manually (from the command line) was tricky; we didn't even get to creating and querying/selecting from tables
- As Jess and Julia returned to the ERD we'd created when our initial plan was to host our own database, **it challenged our assumption to use a relational database in the first place.**

#### DynamoDB
- We met back as a group to determine once more what we actually needed to store in our database, and determined that only metadata about each preview app was needed.
- This led us to play with the idea of a NoSQL database. We decided our output for `bubble init`, which is the `bubble` command with the most detailed output, should look something like this:

```
bubble list

Bubbles~
Yay! First PR #1
  commit #gekh65      added kitten graphics    gekjht4.cloudfront.net
  commit #gterh65     added puppy graphics     gegrerjht4.cloudfront.net
Yay! Second PR #4
  commit #gekh65      added kitten graphics    gekjht4.cloudfront.net
  commit #gterh65     added puppy graphics     gegrerjht4.cloudfront.net
```

- This led us to structure a hypothetical key-value design like this:

```
{ 1: { 
    Name: "Yay! First PR",
    Commits: [
      {
        CommitId: "gekh65",
        CloudfrontDistroId: "GWRE436987DF",
        BucketId: "vdse493-438y9hgl",
        CommitMessageHeader: "added kitten graphics",
        CloudfrontSubdomain: "gekjht4",
        CreatedAt: "2022-07-11T19:08:34.063Z",
      },
      {
        CommitId: "gterh65",
        CloudfrontDistroId: "1WDS836987DF",
        BucketId: "avds7493-438ygl",
        CommitMessageHeader: "added puppy graphics",
        CloudfrontSubdomain: "gegrerjht4",
        CreatedAt: "2022-07-11T19:08:35.063Z",
      }
    ],
    IsOpen: True
  }
}
```

- Between this data structure and the extreme ease of use that we experienced when playing with DynamoDB, we've decided to move forward creating a DynamoDB table for each repository to store preview app data; when we reported this decision to Daniel, he told us it was a good call.

##  problems collected
- Still need to figure out how to delete Lambdas
- Slight complication in reading/writing data from GitHub Actions: you need to check if the PR has been added to the table already before adding a commit and accompanying preview app data

### Todos
- Set up ESLint and refactor `npm` package code accordingly
- Figure out how to read and write data to the table from Github Actions