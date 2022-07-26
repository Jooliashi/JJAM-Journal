## Implementation/writeup conducted 
- continued working on ui
- began conducting another round of e2e testing, collecting lots of little bugs~
  - Added functionality to 'cancel' after running `bubble init`

- build logs:
  - Unfortunately proved too tricky to store the logs themselves in Dynamo
  - s3 storage could have potentially been a more suitable means of storage, but it wouldn't obviate the issues with the Dynamo approach
  - potential to include this in our 'Challenges' section
    - Rather than frame it as "we wanted to do this but couldn't", we could point out that achieving this would have meant our end users would be storing quite a bit of log information in their aws accounts which == $$
    - Perhaps an example of a premature assumption?
    - Using the work done collecting the runner ids from last week, we instead store the URL from that workflow in the `Commits` array in each Dynamo table; this way the dashboard can display a link to the logs on GH
      - Potential to add this to `bubble detail` as well

##  Meeting w/Daniel
- Main topic of discussion: going over outline of project writeup
- Feedback points
  - When discussing our serverless options, either start or end with serverless framework since it's what we ultimately ended up using; a bit awkward to sandwich it in the middle of two unused options
  - We need to go back to daily writeups to find more interesting challenges :joy:
- We don't have to justify why or get into detail about the 'future work' section; at most it would be a short sentence for each topic
- The introduction seems potentially a bit sudden; it's possible that we're dropping in too soon into static site generation.
	- potentially introducing a lil' baby use case for SSG?
		- how development got to SSG
		- why development got to SSG
		- SSG is becoming more and more well known so this is potentially overkill
- Also potential to switch around the ordering of Giraffe's evolution: start them off with an SSR app that wants to add static pages rather than the other way around.
	- This potentially obviates the need to discuss Giraffe's DIY preview app solution and just have them using a shared staging environment previously

### Q&A from meeting
- Should we include the npm package as a section in our architecture?
  - no
- Where should we discuss the point of "where is the dashboard run"? ie hosted by us or locally on the user's machine? Could this be in the Challenges section?
  - maybe we don't even need to mention it
  - Didn't really impress him in terms of a challenge
  - We could just have a demo of using the dashboard in the 'using bubble' section that would show it was running on localhost
  - Such a visual could be a "hook" at the beginning to entice people to keep reading
- How do we reconcile our future work of "supporting more platforms" with the fact that serverless-nextjs only supports Next?
	- Just say "we want to bring it to more platforms" and we don't need to worry about the fact that serverless-next is running our app; we don't have to get into the implementation details
	- Future work is "hyopthetical, in a dream world, what would you do?"

### Todos from Daniel
- **We should start to focus on diagrams**
- Make a big list of potential future challenges even if some of them seem far-fetched
- Have the dashboard ready :joy:
