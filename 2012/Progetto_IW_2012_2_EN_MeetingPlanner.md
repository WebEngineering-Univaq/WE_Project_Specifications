# Web Engineering Course
*Final Projects A.Y. 2012/2013* - Specification #2

## Project "MeetingPlanner"

> Version 1.0

### Preamble

The course projects are inspired by real-world needs, and they usually refer to similar sites already on the web. Students must follow the specifications given by this document, but they can also refine them through an interaction with the teacher and the analysis of similar websites. The final website must be completely original, well organized and easily accessible to all the users.

### Site Specifications

The *MeetingPlanner* site is an easy way to arrange meetings.

The site can be accessed by three types of users: *administrators* , *organizers* and *participants*. The participants, as we shall see, are not registered in the system, but can access specific site pages by invitation only, and for a limited time.

The site database contains information about all the meetings being organized or already arranged. The database also contains a list of available meeting rooms. Each room is associated with its name, location, capacity and equipments, chosen from a predefined list (e.g., projector, air conditioning, microphone, etc.).

Organizers can create meeting proposals by specifying when and where the meeting could take place and inviting a number of participants. Participants will receive an invitation via email and will be able to use the provided link to enter the site and declare their availability. Finally, organizers, given the participants preferences, will define the meeting time and location, and the system will send a notification to all the participants with the final meeting information.

The following list contains a brief description of the contents and functionalities required by this site. Obviously, any further refinement or enrichment of these specifications will increase the value of the project.
* The site homepage should not contain any relevant information: it must only allow the login of registered administrators and organizers. The rest of the site must not be accessible to anonymous users.
* Administrators can register new administrators and organizers (therefore a default, initial administrator must be always defined in the system).
* Administrators can define and edit meeting rooms information, as described above.
* Organizers can create meeting proposals. To this aim, they must specify a description of the meeting and the list of participants, with their full name and email address. They must also define a set of possible dates, time intervals and locations for the meeting, such as "3/4/2014 from 15 to 18 in meeting room 2, or 7/6/2015 from 9.30 to 13.30 in Via Garibaldi 12".
* Organizers may ask the system to check the availability in a certain date/time of a meeting room with specific features. In this case the system, based on its data, indicates which free meeting rooms have the required characteristics (including a capacity compatible with the number of invited participants). Organizers may then choose one of the proposed rooms as the location of the meeting on that date/time. However, organizers are not restricted in their choice by the meeting rooms indicated by the system, but can freely specify any other place or address as the meeting location.
* Meeting proposals can be optionally accompanied by one or more files in text or PDF format, which organizers can upload during the meeting definition.
* When the meeting proposal is complete, organizers can ask the system to send email invitations to all the participants. In this "toy" application it is not required to really send the emails: you may, e.g., simply print the email text on the screen.
* Emails sent to potential participants must contain a description of the meeting, the name of its organizer and a link to click in order to express their preferences and availability. This link is automatically generated and contains enough information (e.g., as parameters in a *query string* ) for the system to identify the meeting and the invited user. *Tip*: instead of directly including information such as the meeting ID or the name of the participant in the link, making it very fragile and easy to tamper, you should put in the link a unique, randomly generated alphanumeric string, which is associated with all the necessary information in site database.
* Users invited to a meeting can access the system via the provided link, and are presented with an overview of all the possible date/time/location options defined by the organizer. Users can then check their preferred options and optionally leave a note. They may also download and read the documents attached to the meeting invitation. Once an user has expressed his preferences, he will not be able to change them, and the link used to access the system will be no longer valid.
* Organizers, at any time, can check which participants answered and how. The system also calculates and displays the date/time/location combinations which are compatible with all (or the majority of) the participants preferences.
* Organizers can finally choose the final date/time/location for the meeting, whose details are recorded in the system database (this is very useful to determine the available meeting rooms, as described above)
* When a meeting is finally arranged, the system sends a confirmation email to all participants who declared their availability for the selected date/time/location, and an email with apologies to all the invited users who won't be able to attend.

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

This specification is available in PDF format on the website of the Web Engineering course at the address http://people.disim.univaq.it/dellapenna. Additional information on the specifications can be obtained directly via email by writing to giuseppe.dellapenna@univaq.it.

Please note that projects should be carried out by *small* student groups (three members is the recommended number). Exceptions to this rule must be agreed with the teacher.
