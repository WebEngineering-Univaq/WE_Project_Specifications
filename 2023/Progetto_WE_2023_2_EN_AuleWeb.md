# Web Engineering Course<br/>*Final Projects A.Y. 2023/2024* - Specification #2

<section class="specifica">

## Project "AuleWeb"
> Version 2

### Preamble

The course projects are inspired by real-world needs, and they usually refer to similar sites already published on the web. 
Students must follow the specifications given by this document, but they can also refine them through an interaction 
with the teacher and the analysis of similar websites. 
The final website must be completely original, well organized and easily accessible to all the users.  

### Site Specifications

<section class="descrizione">



The *AuleWeb* site represents a simplified (*and perhaps visually improved!*) version of our University's classroom management system (https://aule.univaq.it).

Each *classroom* managed by the system has a name, a position (place, building, floor), a capacity (number of seats), the manager's email address, the number of electrical and network sockets present, some generic notes and the list of available equipments, chosen from a list configurable via the application itself, which will initially include the elements Projector, Motorized Screen, Manual Screen, Audio System, Desktop PC, Wired Microphone, Wireless Microphone, Overhead Projector, WiFi.

The classrooms are divided into *groups* (which may represent, e.g., departments) configurable via the application itself. Each group has a name and a description.

It is possible assign *events* to classrooms. For simplicity, we assume that an event cannot span two or more days: in other words, each event will take place on a single day (the date of which must be specified), with a specific start and end time. The event also has a description associated with it, the name and email address of the event manager, a type (lecture, final exam, seminar, partial exam, meeting, graduation session, other) and, for the lecture and exam types, also the name of a course. To select courses and managers the user can choose from a list or enter a new name, which will then be automatically added to the list for subsequent entries.

An event can be declared as *recurring*, and in this case you have to specify the type of recurrence (daily, weekly or monthly) and until which date to repeat it. *Tip: A recurring event is actually an event copied to the same time slot for all days determined by the recurrence type, until the specified deadline. Therefore, when defining a recurring event you could simply create the entire series of corresponding single events and insert them into the calendar. These events will, however, have a "master ID" in common, so that the system can understand that they are related (for example, when deleting or modifying one of the elements of a recurring group, the system could ask the user whether to modify only that one or all the others in the same group). Obviously this is an idea, you can also find other equally or more valid solutions.*


</section>


The following list contains a brief description of the contents and functionalities required by this site. Obviously, any further refinement or enrichment of these specifications will increase the value of the project.


<section class="operazioni">
  


- Read access to the front-end of the site will be free and not require any authentication.

- In the front-end the classroom allocation status will be reported in different ways:
    - Show the events associated with a specific classroom in a specific week,
    - Show the events associated with each classroom on a given day,
    - Show all current events (i.e. currently in progress) and those of the next three hours (i.e. starting in the next three hours),
    - Show events associated with a specific course in a specific week.   
   
  For all the views above, the only classrooms to be considered should be those relating to a specific *group*, which must always be selected before 
  choosing the other view parameters. You should make the views as clear as possible, so as to make the main data visible "at a glance" and providing, 
  if necessary, detailed sub-views accessible by clicking on certain elements.  
   
- From the front-end, users will be able to export all events relating to a certain time interval, and eventually
   also related to a specific course, in CSV format (*tip: to easily manipulate CSVs in Java you can use https://commons.apache.org/proper/commons-csv*) or, *optionally*, iCalendar (for example using https://github.com/ical4j/ical4j).  
   
- The system also has a group of administrator users who, once logged in, are be able to:
   - Insert and modify the configuration of classrooms and related groups,
   - Insert and edit events,
   - Insert and modify the available equipments
   - Export and import the classroom configuration to/from CSV.
  
  </section>

<section class="indicazioni break">

# Directions for Project Development

### Technologies

- The basic *structure* of the site must be created using **HTML5**. The validation of the main site pages 
is important and must be reported in the documentation.

- The site *layout* must be realised using CCS style sheets. The layout can be freely based 
on third party layouts available on the web or shown during the lectures. In this case, 
the degree of **customization** of the layout will be taken into account in the final project assessment.
 **A responsive layout is not required, but strongly suggested.**
 
- For the *client-side* programming, JavaScript is the required language. It is possible to include 
libraries developed by third parties, provided that they have suitable cross-browser portability 
and that they are described in the project documentation. It is, in any case, **not recommended
the abuse of these technologies**, especially when it is possible to replace them
with adequate use of HTML, CSS, etc. Generally speaking, it is **admissible that
scripts play a more important role in the functionalities addressed to a
restricted and predetermined group of users**, for example in *back-end* functionalities
for administrators, but not in the public *front-end* of the site or in a
login procedure. On these pages, the site without scripts may be less "friendly" 
or allow the access to "core" functionalities only.

- For the *server-side* programming, Java *(servlets)* is the **required** language.
Any *DBMS* and *template engine*  (like *Freemarker*) can be employed, if required.
Again, it is possible to rely on external libraries.

- In general, the site must work and have a good *rendering* on the latest versions of Edge, 
Firefox and Chrome, and *possibly* be compatible with older browsers (in this case it should 
at least *degrade well*) and with the latest versions of other browsers, like Opera. Browser
compatibility **must** be explicitly stated in the documentation.  

### Project Development and Documentation

The specifications may not be exhaustive or completely defined. Every feature added or refined, also through an interaction with the stakeholder or the site end users, should be adequately discussed. All the design choices must be discussed and motivated.

The final project, developed following the guidelines given by the present specification, must be a fully functional website, whose contents and features will be assessed during the examination. The specification parts marked as *optional*, if not developed, will not make the project insufficient but, on the other hand, they will not allow your project to reach the highest mark. If you choose to implement an optional feature, the result should not be necessarily perfect or complete: it must only show your commitment to deal with an advanced issue.

The documentation (**in electronic format**) that accompanies the project **must** contain at least the following information:

- Indication of software dependencies (which libraries are required on the client and server side?).

- Indication of the functionalities that have been developed or not developed. Detailed description of any extra or optional functionality added to the project.

- Diagram showing the site structure (e.g. a *navigation diagram*).

- Relational schema of the database (if any).

- Analytical description of the site layout, also indicating its static/dynamic components.

- Description of any advanced technology (language, framework, plugin, library, etc.) used in the project, specifying the reason of its adoption and the actual contribution given to the project development.

- Description of any *possible* cross-browser programming/rendering problem encountered, list of compatible browsers.

- Screenshots of the most important website pages (*optional*).

*The actual contribution of each group member* to the project **must** be declared in the documentation (indicating, for example, the members that mainly worked on server and client side programming, the layout designer, etc.). During the examination, each group member will describe its part of the project.  

### Project Evaluation

To evaluate the project, the following aspects will be considered (in order of importance):
1. Compliance with the specifications.
2. Technical correctness.
3. Organizational clarity and correctness of the contents.
4. Accessibility and standards compliance.
5. Appropriate use of static and dynamic contents. 
6. Design quality.
7. Adequacy of the documentation.

This evaluation will be combined with the result of the project discussion.  

### Additional Information

This specification is available in Web Engineering course repository at the address https://github.com/WebEngineering-Univaq/WE_Project_Specifications. 
Additional information on the specifications can be obtained directly via email by writing to giuseppe.dellapenna@univaq.it.

Please note that projects should be carried out by *small* student groups (three members is the recommended number). 
Exceptions to this rule must be agreed with the teacher.  
</section>

