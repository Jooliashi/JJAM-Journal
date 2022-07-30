##  Meeting w/Daniel
- Questions for Daniel:
  - How detailed should we get about certain topics/what should we expect audience to know, e.g. do we need to explain specifically how workflows work when we discuss GitHub Actions?
	  - easier to determine in a presentation format when things are going too long or we’re getting into too much detail
	  - we’re not necessarily trying to teach someone how to build our project or how to write the exact workflow files - we just want the audience to understand what they are and how they’re used
  - Is there a recommendation for presenting a demo at the very beginning of the presentation vs. waiting until later on in the presentation to do so?
	  - Don’t necessarily save it until the very end, but it’s also not necessary to include it at the very beginning
    - Consider if an audience knew nothing about our problem domain, would the demo be easy to understand or impressive right from the start? 
- Presented narrative portion of presentation and received feedback on slides and general flow
	- Diagrams depicting architectures in history of web development section: 
      - each image within each diagram should be a component, so having two images that both technically represent the client is confusing
      - it’s difficult to follow the flow, as there’s a lot of visual clutter - the diagrams should be oriented so we can read left to right
      - keep words in diagrams to a minimum
  - May remove explanation of CSR in the presentation altogether - can instead present only SSR and SSG - SSR existed, but lacked some things SSG would be an ideal use case for
  - Early definition of what we mean by “dynamic” would be helpful
  - Think of everything as tradeoffs - try not to imply that anything is “better” than the other, i.e. just because SSG is newer than SSR doesn’t mean it’s better
	  - pros and cons tables may be helpful visually
	  - narrow down use cases for each - SSR is good for these use cases but not others -> SSG became a thing and is good for these use cases but not others -> why/when would we need both? What use cases would this be good for and what wouldn’t?
  - Title of “Introduction to Use Case” section seems a bit strange, as this portion feels a bit more like just the second part of our narrative - the transition moving from the previous history section into this next section should be more clear
  - Diagram depicting shared staging environment process could be a bit clearer as well
	  - we discussed afterwards: is the idea of technical code reviews happening necessary to include in the diagram, or would it bring more clarity to simplify the diagram, and how can we depict the process of using a shared staging environment in a way where we’ll be able to easily contrast it with the preview app process later?
  - Regarding downsides to using a shared staging environment, a key one mentioned was the idea of new features being batched together - there should be emphasis placed on this as having to rollback releases is challenging
  - Our mention of Giraffe can seem a bit out of the blue and distracting - it was hard to keep track and remember again what Giraffe was - it didn’t feel like using Giraffe as a vehicle for this part of the narrative was particularly helpful or that it added much value, but ultimately it’s up to us
	  - we discussed afterwards that utilizing Giraffe could still be useful from a general public perspective - perhaps ensuring there is more concrete mention of Giraffe throughout this portion, and a more consistent throughline diagram-wise so that visually the audience can clearly see we are following the journey of Giraffe, their problem, and their options may make this a bit easier to understand
  - The transition from explaining what preview apps are to what dynamic preview apps are needs to be clearer
	  - every section should give permission to the next to be able to introduce/talk about the next thing, and it didn’t quite feel like we had permission to discuss dynamic frontend preview apps yet
	  - we should more clearly explain what the difference is between a dynamic preview app and a static one, what complexity it adds, and why someone would want/need that - it’s ok to use architecture diagrams here to depict this 
- Our current writeup is coming in at around 10k words - around 8k words would be ok, but that would be around the highest end of the word-count range we should be aiming for
- After we tighten up the narrative portion of the presentation, it could be helpful to have someone present this part to the rest of the group, and the remaining group members should watch from a perspective of someone who is completely new to our project and problem domain - be on the lookout for areas where we may be taking liberties or where there may be jumps and transitions that are unclear

## Presentation/Writeup progress
- Discussed how to re-work some of the diagrams (particularly the diagrams depicting shared staging environment vs. preview app process, as well as dynamic frontend preview apps) mentioned by Daniel to ensure they depict the main point we are trying to convey as clearly and simply as possible
- Began to finalize/beautify SSG and SSR architecture diagrams into the diagrams we will want to use in our actual presentation
- Walked through slides for narrative portion of presentation and began to adjust each one based off of Daniel’s feedback, focusing on ensuring our transitions make sense, and that the diagrams for each slide are entirely relevant

## Todos
- Schedule presentation with Srdjan
- Continue tightening up narrative section of presentation, and start mapping out script 
- Continue working on post-narrative sections of presentation
- Continue working on diagrams and finalizing them a bit more
