## use case
- when an engineer prefers using AWS CDK to optimisize and customize deployment
- How about Amplify?
	- potentially cheaper than AWS Amplify which is a premium service and not sure how Amplify works behind the scenes
	- only supports up to next version 11
	- limited routing + rewriting options and don't support query strings. 
- prefer not to use the framework because want to have full control over the deployment and want to do it natively
- Reference: https://stackoverflow.com/questions/70833847/how-to-deploy-nextjs-on-aws-the-same-way-vercel-does

### What is Terraform?
It's an Infrastructure as code  tools that allow you to manage infrastructure with configuration files rather than through a graphical user interface. Imagine setting up AWS services with a single file instead of going into AWS interface. 

## Setup Example 1
- https://github.com/milliHQ/terraform-aws-next-js (open source terraform module)
- consists of 3 main resources:
	- CloudFront: works as a serverless reverse proxy that routes traffic from internet to either S3 or Lambda;
	- S3: for static content
	- Lambda: used to server the server generated pages (SSR & API). They contain a minimal version of the Next.js server
- The setup can be built with terraform, node.js and bash.
- Potential Benefits claimed:
	-  ✅  Supports any version of [Next.js](https://nextjs.org/)
	-   ✅  [Terraform](https://www.terraform.io/) `v0.15+`
	-   ✅  Unlimited parallel deployments of Next.js apps (atomic deployments)
	-   ✅  Static, SSG, Lambda and API pages (with [dynamic routes](https://nextjs.org/docs/routing/dynamic-routes))
	-   ✅  Automatic expiration of old static assets
	-   ✅  [Rewrites](https://nextjs.org/docs/api-reference/next.config.js/rewrites) & [Redirects](https://nextjs.org/docs/api-reference/next.config.js/redirects)
	-   ✅  [Image Component & Image Optimization](https://nextjs.org/docs/basic-features/image-optimization) support
	-   🚧  [Incremental Static Regeneration](https://nextjs.org/docs/basic-features/data-fetching#incremental-static-regeneration)
	-   ⛔️  [Middleware](https://nextjs.org/docs/advanced-features/middleware) (Not supported by Lambda@Edge / CloudFront functions)
	
### Setup Example 2
- compile next.js application into docker image
- use terraform to create a ECR
- push the image to terraform created
- full steps: https://levelup.gitconnected.com/fully-automated-nextjs-builds-deployments-github-aws-ecr-fargate-service-ecs-part-1-4-6216e58dcb89
- compared to setup example 1, an even more manual example. The terraform used is only for specific components but the module from example 1 consists of the full deployment automation.





		

