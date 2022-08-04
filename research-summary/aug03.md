## Presentation Progress
- Finalized on use case of presentation and got feedback from both Daniel and Elizabeth
- architecture diagrams were largely approved
- now moving on to architecture flow. 
	- Removed pull request decision
	- Github Apps vs EC2

## Meeting Notes
Daniel notes 8/3

8 Changing Landscape: what if we lined up the client so that both SSR and SSG have it in the same position/overlapped? May be more effective

19 Downsides of Preview Apps:
    Agrees that Labor is confusing as a downside: need to continue making it more clear. (We discussed distinguishing between 3rd-party provider and DIY/self-hosted options, with labor in the second category)

He loves the diagrams/visuals! Asked where we found them… (Missy: 😎)

Likes the demo videos but wants to see more of the dashboard on the managing preview app video (it's the most appealing thing to show visually)

Can delete when to build slides…not a particularly rich decision and was already covered earlier

If we want to get into GitHub actions, that's fine, but we should compare it against deploying our own build server—most people aren't familiar with GitHub Apps and it sounds like it wouldn't've been different than deploying our own build server anyway  🤷

Getting into containers vs serverless functions (and then Terraform/FAB/Serverless) is good, as is the two planned challenges

Future Work: usually just one slide with a few bullet points, probably don't need a visual there

Things are looking good! We'll probably be ready early… J~JAM!!!

Elizabeth dry-run notes 8/3

Great job! We've done a lot!
Asked about what happens if a build fails

Likes how the diagrams are partially grayed out and colored differently

NOTES/SUGGESTIONS

Slide 4 SSR: maybe move the location of the sticky note for "client renders page"? Wasn't sure if that 

5 SSG: feels like a slide between SSR and SSG could make the transition flow better…felt like the diagram didn't come into play until later in the speech
    Should define CDN in one sentence on the SSG slide: say out the full name and say what it is/does

6 SSG vs SSR: had a hard time reading the graph w/checks and Xs

7 The Changing Landscape: Could work more into our explanation why we're referencing blogs and products

10 The Giraffe Team: change the "head of marketing" label to "product manager"? Great that we expand on this later: how much of a role non-technical stakeholders play

12 Shared Staging Environment: Change "real traffic" to something like "simulated traffic"

13 Downsides to Shared Staging Environment: Slide was good, gets batching/queuing distinction
    Feels like batching explanation is fuzzier: why are things being batched? What's leading to the batching?
    Can we "unfuzzy" this and explain in a stronger way what the issue with batching is?

18 Downsides/Limitations of Preview Apps: Wasn't completely clear on the labor graphic…can we underline our point more in the speech?

24 Where Bubble Fits In: Table is hard to read, need to iterate on this graphic

26 Features of Bubble: Why do we need the dashboard? What makes it different? (Unclear on the differences)

POSITIVES YAAAAAAY!

15 What are Preview Apps? Loved this slide!

16 Example Preview App Workflow: Loved this slide too! Really liked how it visually supported everything said and went through the entire flow

Great how we keep coming back to the feedback loop throughout the presentation: this is really going to hit for any engineer

26 Features of Bubble Loved these visuals (whoever did these visuals…GREAT JOB MISSY!)

27 CLI: Could we have a visual of the command line (animations?) instead of the table? Table is kind of meh…

28 Demo: Great to see things in the video (GREAT JOB JESS!)

Elizabeth's team used a tool called Carbon to create an example terminal and illustrate them

Could just get rid of Slide 27 CLI since we're going to show the video demo on the next slide

It's OK not to cover every single feature/command of Bubble in our presentation

We're in good shape and even some of what we didn't go through is looking good!