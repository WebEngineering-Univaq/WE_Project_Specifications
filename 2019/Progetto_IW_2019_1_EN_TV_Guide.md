# Web Engineering Course
*Final Projects A.Y. 2019/2020* - Specification #1

## Project "TV Guide"

> Version 1.0

### Preamble

The course projects are inspired by real-world needs, and they usually refer to similar sites already on the web. Students must follow the specifications given by this document, but they can also refine them through an interaction with the teacher and the analysis of similar websites. The final website must be completely original, well organized and easily accessible to all the users.

### Site Specifications

The "TV Guide" site is an online guide to television shows. The site will show the schedule of a certain number of television channels, listing the shows available day by day. In particular, the site should provide information about the shows up to seven days in the future (there may be fewer, based on the data provided by the broadcasters). Information about the past shows should be also available, but in this case, you should set a time limit and delete all the older entries from the database, to avoid unnecessary load.

For each television show, the site will store the start and end time, the name, a brief description and the type (the types are taken from a predefined list). If the show represents an episode of a series, it will also have associated the season number and the episode number within the season. There could be also a link to an in-depth information page (not necessarily internal to the site itself: it may be a Wikipedia page, for example) as well as an image. The latter may be internal to the site or connected though an external link.

Users should be able to read the schedule of each channel (shows of a certain day) and perform searches by title and/or type, possibly restricted to a specific channel. The user may also specify the time interval of these searches.

Tip: consider that the same shows or the same episodes of the same series may appear several times in the schedules. In designing the data model, and therefore the operations that use it, try to optimize the structure based on this consideration. For example, if a show is broadcast on two different days, the database should not contain all its basic information twice (title, description, link ...): only the airing data (channel, time, etc.), which are the only ones that change, should exist in two different versions.

Any user will be able to register on the site by entering an email and password. Registered users, once logged in, can specify how to receive a daily email with the latest updates to the schedule. The email may contain today's shows for selected channels, possibly only for certain time slots (morning / afternoon / evening / night) and/or the results of a saved search (of the type described above), to be notified, for example, when a show he wants to follow appears on the schedule. *Note: the application created for the project will not necessarily have to send these emails, but you will still have to write all the code to create the email content and then transfer it, in the demo phase, to an external file.*

Please note: since this site will be often accessed from mobile devices, pay particular attention to the *responsiveness* of its layout.

The following list contains a brief description of the contents and functionalities required by this site. Obviously, any further refinement or enrichment of these specifications will increase the value of the project.
* The homepage has to show the list of available channels, as well as the shows currently broadcast on each of them.

* From the homepage, it should be possible to access a second view, similar to the homepage itself, which however lists, for each channel, all the shows in the daily schedule *relative to a specific time slot (morning / afternoon / evening / night).*

* In any view, by clicking on a channel, it should be possible to view its complete schedule for the current day. In this view, the classic "TV guide" view, the shows should appear (sorted!) together with their start time, end time, type and title. If available, the related image (appropriately scaled) may be shown alongside a show.

* In any view, by clicking on a show the user should access the corresponding details page: larger image (if available), description, in-depth link.

* If the show is part of a series, in its detail page it should be possible to view the broadcasting date/time and channel of all the related episodes in the last month.

* The search functionality, accessible on every page of the site, should allow to specify one or more of the following criteria, combined in AND: (part of) title, type, maximum and minimum start time, channels, time interval (dates). The search results will be then shown in a "TV guide"-like view, in this case sorted by date, start time and channel.

* A user can register by providing a valid email and a password of his choice. The email must be confirmed by clicking on a link sent to the same address. *Note: write the code to generate the validation link and manage its click, but during the demo, you can simply print the link somewhere and enter it in the browser, without having to actually send the email*.

* In his profile, the user can enable the daily schedule email, described above, possibly specifying a list of channels and one or more time slots of interest.

* Furthermore, the authenticated user, once a search has been performed as seen above, should be able to save the criteria (by clicking on an appropriate button), so that they can be used to generate further information to be included in his daily email, as already illustrated.

* Obviously, the registered user should be also able to stop the sending of the search results and/or of the daily schedule.

* The site administrator, who we will suppose unique and pre-registered in the system, should be able to insert, modify or delete the channels and the relative schedules, that is, the shows and the information about their broadcasting.

# Directions for Project Development

## Technologies

* The basic structure of the site must be created using HTML5.The validation of all the site pages with respect to the chosen HTML flavour is an important part of the development and **must**be reported in the documentation.
* The site layout must be realised using CCS style sheets. The layout can be freely based on third party layouts available on the web or shown during the lectures. In this case, the degree of **customization** of the layout will be taken into account in the final project assessment. **A responsive layout is not required, but strongly suggested.**
* For the *client-side* programming, JavaScript is the required language. It is possible to include libraries developed by third parties, provided that they have suitable cross-browser portability and that they are described in the project documentation. However, **any abuse of these technologies is not recommended** , especially when they can be replaced with a suitable use of HTML, CSS, etc. **In general, your site should be functional also with JavaScript disabled** . The site without scripts may be less "friendly" or allow the access to "core" functionalities only, but sites whose dynamics is entirely script-based are not allowed. However, **scripts can play a more important a role in the functionalities whose users are restricted and pre-determined** (e.g., in the *back-end* functionalities for administrators, but not in the public *front-end*or in the login procedure).
* For the *server-side* programming, Java *(servlets, JSP)* is the **required** language\*.\* Any DBMS and template engine can be employed, if required\*.\*Again, it is possible to rely on external libraries.
* In general, the site must work and have a good *rendering* on the latest versions of Edge, Firefox and Chrome, and *possibly* be compatible with older browsers (in this case it should at least \*degrade well)\*and with the latest versions of other browsers, like Opera. Browser compatibility **must**be explicitly stated in the documentation.

## Project Development and Documentation

The specifications may not be exhaustive or completely defined. Every feature added or refined, also through an interaction with the stakeholder or the site end users, should be adequately discussed. All the design choices must be discussed and motivated.

The final project, developed following the guidelines given by the present specification, must be a fully functional website, whose contents and features will be assessed during the examination. The specification parts marked as *optional*, if not developed, will not make the project insufficient but, on the other hand, they will not allow your project to reach the highest mark. If you choose to implement an optional feature, the result should not be necessarily perfect or complete: it must only show your commitment to deal with an advanced issue.

The documentation (**in electronic format** ) which accompanies the project **must**contain at least the following information:

* Indication of software dependencies (which libraries are required on the client and server side?).
* Indication of the functionalities that have been developed or not developed. Detailed description of any extra or optional functionality added to the project.
* Diagram showing the site structure.
* Relational schema of the database (if any).
* Analytical description of the site layout, also indicating its static/dynamic components.
* Description of any advanced technology (language, framework, plugin, library, etc.) used in the project, specifying the reason of its adoption and the actual contribution given to the project development.
* Description of *any*cross-browser programming/rendering problem encountered, list of compatible browsers.
* Screenshots of the most important website pages (*optional*).

*The actual contribution of each group member* to the project **must**be declared in the documentation (indicating, for example, the members that mainly worked on server and client side programming, the layout designer, etc.). During the examination, each group member will describe its part of the realisation.

## Project Evaluation

To evaluate the project, the following issues will be considered (in order of importance):

1. Compliance with the specifications.
2. Technical correctness.
3. Organizational clarity and correctness of the contents.
4. Accessibility and standards compliance.
5. Appropriate use of static and dynamic contents.
6. Design quality.
7. Adequacy of the documentation.

This evaluation will be combined with the result of the project discussion.

## Additional Information

This specification is available in Web Engineering course repository at the address https://github.com/WebEngineering-Univaq/WE_Project_Specifications. Additional information on the specifications can be obtained directly via email by writing to giuseppe.dellapenna@univaq.it.

Please note that projects should be carried out by *small* student groups (three members is the recommended number). Exceptions to this rule must be agreed with the teacher.
