---
titolo: SocialDevelop
numero: 2
versione 2.0
lingua: EN
anno: 2016
materia: IW
mainfile: Progetto_Master.rcp
thisfile: specifica
---

-------
{#specifiche}

*SocialDevelop* is a web support tool for collaborative software development. While other sites like GitHub focus on the actual code writing and versioning, our system stays on a "meta" level, namely its aim is to publicize the software projects and identify suitable freelance developers to employ, automatically creating their "references".

*Thanks to Konstantinos, Svetoslav, Petyo and Danail for suggesting me this idea* 

The site is similar to a regular forum, but instead of discussion threads, SocialDevelop contains *projects*.

Each project has a *coordinator* and is associated with a set of *tasks* , i.e., activities to accomplish. Each task is accompanied by a textual *description* , the required *number of collaborators* (i.e., people to employ on the task), and the *time frame* for its completion.

Moreover, each task also has a *type* (very general, and chosen from a predefined list, such as "development", "graphics", "documentation", etc.) and a list of *skills* it requires, each one associated with a *level of expertise* (from 1 to 10, for example, "C++ programming" level 8, or "Responsive design" level 5, etc.). These skills are also chosen from a predefined list, specific to the task type.

Finally, a task can be *open* or *closed*. A closed task does not accept further collaborators, unless they are added directly by the project coordinator. On the other hand, developers, as described later, can send applications requests for open tasks. A task is considered closed if it already has the required number of collaborators or if the coordinator has explicitly closed it. Otherwise, it is open.

Messages (announcements, requests, and internal discussions) can be posted within projects, and they can be marked as public, i.e., visible to any user, or private, i.e., visible only to the project collaborators.


The site has an administrator who is only responsible of entering/editing the list of task types and the list of skills associated with each task type (*optionally* , you may associate the same skill to more than one task type). Skills may *optionally* have a hierarchical structure (for example, "Design Swing Interfaces" could be a "son" of "Java Programming") to organize them better. A skill, as already described, can be generic or very specific, and can be associated with tasks and with user profiles, as we will see.

The users of our site, that we shall call *developers,* must register themselves by providing their personal and contact information and their curriculum (as plain text or uploaded as a PDF file). They should also indicate their skills, chosen among the global list of skills available in the system, specifying for each of them the achieved level of expertise (through the same scale used for the skills associated with tasks, as specified above). For example, a developer could declare a level-7 skill in "Java Programming".

-------
{#operazioni}


- All the users, including the *anonymous* ones, can browse the list of projects, see the related tasks (both as a compact list and in a detailed view) and read the public messages posted in the projects.

- All the users, including the anonymous ones, can search on *SocialDevelop* in two ways:
   1. Search for developers: the user indicates a set of skills (taken from the global list) and optionally a minimum level of expertise for each of them. The system will then return a list of developer profiles having all of those skills, with a level of expertise greater than or equal to the given threshold, if specified;
   2. Search for projects: the user enters some keywords, and the system returns a list of projects having these words in their name or description.

- Anonymous users can register on *SocialDevelop* to become registered users, i.e., developers. During the registration process, developers must provide their personal and contact details, their curriculum and their skills, as already described in this specification.

- The public profile of a developer shows, in addition to the above-described information, a list of *automatic references* generated from the projects he/she has worked or is working on. In particular, such references show the project name, the specific task(s) the developer was involved in, and an evaluation (when the task is complete) given by the project coordinator, whose name and email address are also included.

- Developers enrolled in a project can read all messages, both public and private, posted in the project, and post new messages.

- Every developer can create new projects, becoming their coordinator, and populate them with tasks. The definition of projects, tasks and skill requirements must follow the structure already illustrated in this specification. The coordinator should also be able, at any time, to modify the project, for example changing the dates or the skills associated with a task, increasing the number of collaborators required, etc.

- The project coordinator, once a task is fully defined, should be able to view a list of developers suitable for that task (that is, with suitable skills), automatically generated by appropriately using the search function (1) described above.

- The project coordinator can send to any registered developer a *collaboration proposal* for a particular task. Such proposal will be then included in the "*invitations panel*" of the coordinator that reports, for each proposal, the associated task, the contacted the developer, the proposal submission date and its status ( "waiting", "accepted" or "rejected"). The coordinator can
cancel a proposal at any time.

- Each developer has a "*proposals panel* " that lists all the collaboration proposals sent by project coordinators as just described. The developer should be able to see the details of the associated project and task, and then accept or decline the proposal. The proposals not considered (i.e., accepted or declined) will be automatically declined after a certain period. If a developer accepts a proposal the system, after changing the status of the proposal in the "*invitations panel* " of the coordinator and in the "*proposals
panel*" of the developer, automatically enrolls him/her in the project and assigned task and decreases accordingly the number of collaborators required for that task.

- Developers also have an "*offers panel* " that shows an automatic selection of the collaboration opportunities suitable for their skills. In other words, the system will search and show automatically (using a search system similar to the (1)) the *open tasks* having skills compatible with those of the developer. Developers should be able to send *application
requests*for these offers to the corresponding project coordinator. In this case, the offer status in the panel will change from "available" to "applied". According to the coordinator's decision, the status will then become "accepted" or "rejected". An application
request can be cancelled at any time.

- The project coordinator has an "*applications
panel* " that lists all the application requests received, with the indication of the developer and task. From here, the coordinator can browse to view the developer profile, and then accept or reject the application. If accepted, the application status will change both in the "*applications panel* " of the coordinator and in the "*offers panel*" of the developer, who will be automatically enrolled in project/task, as already described.

- *Optionally* , every status update in the "*invitations* " "*offers* " and "*applications*" panels just described may generate a notification email sent to the corresponding user. For example, a coordinator will be notified when one of his/her offers is accepted or rejected by a developer or when a developer applies for one of his/her projects, while a developer will be notified of the results of his/her application requests.

- The project coordinator may, at any time, exclude a developer from a task (e.g., if he/she is not working as required), de-enrolling him/her and eventually reopening the corresponding task to new applications requests (i.e., increasing by one the number of collaborators required by the task).

- At the end of a task, the project coordinator has the opportunity to evaluate (on a scale 1-5) all the developers that collaborated to it. This evaluation, as explained above, will then appear in the developer profile.  
