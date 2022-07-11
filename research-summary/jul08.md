## research conducted 
- Completed `bubble init` `bubble deleteUser` commands
- completed workflows for removing a review app which can be triggered through external HTTP

##  problems collected
- Should we think about creating a dashboard and host that ourselves
	- We decided to not think about creating a bubble-hosted dashboard for now because we would need to host sensitive information regarding repos and user, which will infringe on the purpose of why someone would want to use a self-hosted preview app
	- We also decided not to host a database for similar reasons.
- Where to keep the data mapping for repos/users/preview apps
	- We are considering either keeping that locally on a user's machine or have a per user database provisioned through iam user
	- at the moment, for creating a MVP, a local file would be a better option
- Some problems we discussed but are not super impactful:
	- how to design good CLI interface
	- should we provide the functionality of deleting one preview app only
	- what functionality should deleteUser entail? at the moment it only deletes the iam user in aws and github secrets


### Todos
-   Reconfigure removing review app workflow so that it's triggered by the closure of a pull request
-   explore github repo cache vs. local file in terms of storing the mapping