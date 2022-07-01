## research conducted
- We further refined our narrative according to the comments from Daniel.
	- modified statements regarding static sites + server side rendering(hybrid use case).
	- clarified regarding "self-contained".
	- added additional explanation for review apps.
- previously we have deployed two different Next.js projects with serverless framework to AWS LambdaOnEdge, and decided to try deploying with FAB. It turned out that since FAB is a no longer actively supported package, it only works for certain versions of Next.js.

##  problems collected
- 15 mins execution time for Lambda function, what limitation does that imply?
- FAB vs serverless framework.

## general thoughts/impressions of the problems
- FAB is a no longer actively updated package. However, using serverless framework presents other tradeoffs as an open source package
	-  it limits the user to only deploy to AWS Lambda@Edge. 
	-  it's not gonna be always maintained up to the latest version of Next since it takes time for maintainer to update and it currently only has one maintainer.

##  Todos
- next Monday we should produce the final proposal.
- July 4th HORRAYY a holiday.
	