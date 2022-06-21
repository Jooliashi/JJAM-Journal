## research conducted (refer to google doc Project Narrative Outline)

- Reorganize the current research material into one doc file
- narrow down on the use case
- build the project narrative with the mateiral so it has an easy to understand flow

##  problems collected
- Need to conduct more user experiences for review as a service options, and note down different comparison points. A list of companies include: **bunnyshell, shipyard, tugboat, release, roost, webapp.io**

## general thoughts/impressions of the problems
- We believe we have a good understanding of the use case for review app in general(ie, for a front end developer, a review app is used to easily verify the functionality of a front end feature and share that preview with stakeholders to get feedback)

-  need to narrow down more on the procs and cons of existing solutions to gather a better understanding of the architectures of different solutions. This could also help us construct our own solution implementation and the corresponding tradeoffs.

## Useful conversation notes:
- i tested out shipyard and put all the information in the google doc; it’s quite a lot so we can move them out later if we want to only use them for reference. i have to say the general user experience is pretty sucky for a front end developer yay for us? my docker-compose with potatobin-frontend worked locally but did not work with their build…![:rolling_on_the_floor_laughing:](https://a.slack-edge.com/production-standard-emoji-assets/13.0/apple-medium/1f923@2x.png)..the build time is 5 mins for each URL(they claim they are building a full stack environment each time for a PR so I’m suspecting that’s the reason it’s taking so long, altho my application does not have any backend but maybe they are still going through the same step for preparation of the environment?) My impression of EaaS after shipyard is really they seem to target different use cases or just more use cases. They (at least shipyard) don’t optimise front end application deployment, and preview seems to be a must have but not differentiating feature within the whole product(or why it’s a fullstack review app). Cuz i think the product really shines if the user wants to do end to end testing which would require a database layer. was thinking trying another one but took a general browse of EaaS and it seems they are all relatively similar in terms of architecture. Target full stack, support E2E testing, use dockerfile to generate containerised app, deploy on kubernetes. so not sure if i will get more out of it by trying more, maybe you guys will have a different insight. also wonder if Missy feels tugboat is very different from shipyard in terms of user experience

- Tugboat is different than Shipyard in that it is actually focused on preview environments, but you can use them for other tasks e.g.  from temporary staging environments, to QA environments, to code reviews; and for more complex DevOps tasks like interoperability testing or experimenting with infrastructure changes. Really they just kinda provide a skeleton and you can mix and match whatever services... in theory. I don't know the actual extent of different combinations outside of their preferred technologies that would work. Just for E2E for example, I did find a tutorial in which you can specify Cypress as a dependency and use an automated testing platform called Testery (TBH not really sure what they do outside of providing a dashboard for your Cypress tests) so on the one hand it's not actually built into Tugboat, but it's also pretty trivial to set up
	
- Kinda went backwards->forwards on the list lol, so fleshing out some notes on Roost I'll share later, and started trying webapp before passing out last night - didn't get a chance to look too deeply into webapp quite yet, but I believe they use VMs vs. containers. Deployed a very basic React frontend app with them and was super easy to set up and view previews etc., but wonder if it might be useful to try with an SSG/SSR hybrid app to get the picture with our particular use case
	
##   Todos
-   research current solutions specifically for review as a service apps
-   continue to structure the narrative towards server side rendering? needs for front end review apps
	