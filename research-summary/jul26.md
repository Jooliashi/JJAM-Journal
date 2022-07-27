## Implementation/writeup conducted 
- Added temporary informative message to dashboard to be displayed when user clicks the `destroy` button
- Moved deletion of PreviewApps DynamoDB table to `teardown` command
	- The deletion of our table tracking all the preview apps was previously intended to occur during the `destroy` command - we had included this as a final step in our workflow for destroying a branch of preview apps if it was dispatched by our repo-destroying workflow, however we realized that this approach would end up prematurely deleting the table during the `destroy` process, which would cause a ripple effect of issues removing resources down the line. In order to adjust for this, we discussed either adding a check in the workflow that this is the last branch needed to be destroyed before deleting the table, or moving the responsibility of deleting the preview apps table to the `teardown` command instead. Ultimately, we felt it would be more straightforward and fool-proof to simply move this process to `teardown`, so now, whenever the user runs `teardown` for the first time, the preview apps table will be deleted as they won’t need it for any further executions of `teardown`. They will still be able to retain their smaller Lambdas table, however, until all Lambdas have successfully been removed.
- Combed through old daily summaries to compile list of difficulties and tradeoffs we encountered along our research/implementation journey in order to come up with more challenges we feel are worth discussing further in our case study
- Wrote draft for alternate narrative option to compare with our original narrative - also outlined a third potential narrative as another option
- Started mapping out and creating potential diagrams, tables and illustrations for each section of our writeup

## Todos
- Walk through both narrative drafts as a group one more time and make adjustments as necessary based off group thoughts/feedback (i.e. changing illustration brainstorms, tweaking language, adding additional information on certain concepts for clarity, etc.) before sharing with Daniel
- Work on expanding Challenges section together as a group before sharing with Daniel
- Demo dashboard for Daniel
- Continue walking through other parts of our writeup together
- Continue working on diagrams
