## research conducted 
- started on the additional feature of build log. The current plan is to first find the runner id for deployment workflow and use that in another workflow. The second workflow will pull down the log and save it to aws dynamodb database.
- using Tailwind CSS to design the UI of dashboard
- started the write up and presentation slide planning
##  problems collected and Todos
- need to choose between two options on use case scenario
	- Option A: the transition from SSG to SSR seems contrived
	- Option B: missing background explanation on industry transition
## Meeting Notes
Daniel meeting notes 7/27

Use case:
Story of having an app already beginning with a hybrid SSR/SSG site, beginning with a shared staging environment, is basically exactly the same as Stagehand's narrative. The point here would be advocating for preview apps and how they're solving a problem. If we go this route, we would need to get a little into what SSR and SSG are and why the company has a hybrid site like this.

Our preexisting narrative, where a company is adding on SSR to their SSG-only site, may be more interesting with the site changing (and could also allow us to flex some web development knowledge talking about how sites have changed).

Doesn't think we have to have a company as a backdrop to make it interesting. (Kind of become a Capstone cliché to keep referring back to a fictitious company—it works and can work, but it's not at all necessary).

VISUALS!!!

What happened in web dev:
SSR apps (pretty much everything was this)
SSG then came along, and a lot of people transitioned to that
Then a lot of SSR apps started offering SSG as well

Daniel thinks Option B makes the most sense: tweak that and roll with it, in his opinion, but also could go with another as well.

He suggests talking about SSR before bringing in SSG, and thinks it would be good context to discuss that as the history of web dev.

Another angle to consider: Thinks a company changing their architecture is more interesting, perhaps—could also think of a monolithic site starting to separate things out/decouple things and wanting to keep both their static and dynamic functionality. Perhaps they don't have preview app functionality now; or otherwise what they used to use won't work with their new architecture. (this goes more toward option B, and gives us the opportunity to discuss legacy architecture and more modern architecture and how it all fits together)

Had something old…like PHP…and were looking for more modern frameworks and settled on something like Next.js…as part of this transition, they want to add on preview apps.

Suggests we do more research to find more validation: try to find companies who migrated from some kind of monolith to more of a decoupled architecture; or going from something like just a blog to adding on additional functionality afterward. We want to dig in a little more to understand and find our specific use case

Companies we're talking to will probably be way more used to something like monolithic -> decoupled rather than something like starting static and adding dynamic functionality

(Maybe monolith and PHP may be bad examples).

Whatever we end up going with, we should discuss more about the history of things and how we got to our current place: how apps traditionally were made (pre-SSG) before we get to the current point where SSG already exists.

Something seems to be missing, and we need to figure out what that is and fill it in. The beginning of the story isn't quite here yet

Challenges

Daniel suggests including teardown and build logs (logs could make an interesting story) for the challenges section

Challenges are more about theoretical ideas

Not going with build logs: S3 bucket (more app complexity, a lot more to develop there); also adding the build logs would cost more for the user in AWS fees when they can get the data on GitHub for free for only a couple more clicks

Dashboard looks great!

Illustrations w/jokes, stories: could possibly work but will really depend on the execution. Overall tone of the write-up/presentation should be professional, but ok to have occasional moments of levity

Architecture diagram: something missing but not sure what yet…then suggested using the look of visual "stacks"(is there a better word for this?)—where multiple boxes are stacked together with a slight diagonal offset—rather than having more than one complete row.

"You want the architecture diagram to have a little clutter as possible while still showing everything"

Once the diagrams are there, the whole narrative will be easier to understand and get feedback on. The diagrams are the main part of it

Architecture diagram: something missing but not sure what yet…then suggested using the look of visual "stacks"(is there a better word for this?)—where multiple boxes are stacked together with a slight diagonal offset—rather than having more than one complete row.

You want the architecture diagram to have a little clutter as possible while still showing everything