# Web Engineering Course
*Final Projects A.Y. 2021/2022* - Specification #2

## Project "Collectors Site"

> Version 2.0

### Preamble

The course projects are inspired by real-world needs, and they usually refer to similar sites already on the web. Students must follow the specifications given by this document, but they can also refine them through an interaction with the teacher and the analysis of similar websites. The final website must be completely original, well organized and easily accessible to all the users.

### Site Specifications

The *Collectors Site* website is a meeting point for record collectors (although the same type of site could fit almost any type of collection, we will use the records as a case study so we can add more details to the specification).

Once registered, the users of this site, or *collectors* , will be able to enter all the data relating to their record *collections* (each collector can create multiple collections, each with a distinct name). For each *disc* in a collection, the collector should provide the authors, the title, the release year, the publisher, the genre (chosen from a predefined list of musical genres), the status (of conservation of the object, chosen from a predefined list), the format (vinyl, CD, digital, ...), the *barcode* number, if available (the barcodes guarantee the unique identification of the element), and then obviously the track list, each with title, duration, and information on composer and performer (singer, musician), if different from those of the entire disc. Finally, each disc can be associated with one or more images (cover, back, booklet pages, etc.). In short, try to be as realistic as possible.

For each disc, the collector will also be able to indicate the possible number of *duplicates* owned (maybe since they are expected to be resold).

Collectors can decide to *share* their collection with specific users or in a public way. Each collector will therefore have a panel with a list of the collections shared specifically with him, which he can freely view.

The site should have an advanced search function (by artist, title, collector, etc.), also available to anonymous users, which will consider all public collections and, for a logged in user, also the personal collections and all collections shared with him *(tip: you can perform the same search on every collection accessible by the user and then merge the results)*.

It is important that, in the system, the same discs, even if belonging to different collections and collectors, should be linked in some way, so that they can be grouped together if necessary, e.g., to answer questions such as "who owns this disc?". To this aim, always try, when a new disc is added, to "suggest" to the collector to import (as initial values) the data of the same disk, if already present in the system in other collections. By doing so, you will internally create a connection between the "same" discs, even if the collector will then be free to edit the data of his copy. Furthermore, it would be helpful to use auto-completion wherever possible, using the data of the same field already present in the database as a source: for example, by entering the name of a singer, the system should suggest the completions using the names of the singers already known. This trick not only has the purpose of speeding up the input, but it is also useful to avoid the same object (in this case, a singer) to be entered several times with small variations (for example spaces, apostrophes , etc.).

The following list contains a brief description of the contents and functionalities required by this site. Obviously, any further refinement or enrichment of these specifications will increase the value of the project.
* Collectors register in the system by providing a nickname and an email address. It is not required, even if possible, to enter the real name and surname.

* Each collector has a public profile, also visible to anonymous users, containing the personal data entered and the list of his public collections.

* Once authenticated, collectors can manage their collections, and in particular create or delete a collection and insert/delete/modify the individual discs contained in a collection, as described above.

* The site must provide (at least) two views on the collections: list of the entire collection and detail of a disc contained in a collection. Either way, you'll need to decide what information to show and how to organize it. Obviously, the view on the collection and its contents will be accessible to the owner and to all those who have access rights to the collection itself (for public or shared collections).

* An important element of the site will be the search functionality. It must be possible to search for author/composer/performer names, titles and collector nicknames. The results may be of different types based on the elements found: single discs, entire collections, collector profiles. The user can include in the search results only his own collections (if logged in) or also the shared/public ones.

* A collector has a panel with the list of collections shared with him, from which it is possible to directly access the view of the related collection.

* A collector can decide whether to make each of his collections private (default), public, or share it with other specific users. When sharing a collection with a user, he will receive an email notification *(tip: you can simulate such an action, you don't really need to send an email).*

* The site must provide statistics, public or personal (per collector). You are free to define the most interesting ones. Suggestions can be the number of discs by author, by genre, etc. (in a collection, for the collector, or in the whole system, as a global statistic)

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
