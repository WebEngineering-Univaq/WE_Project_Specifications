# Web Engineering Course
*Final Projects A.Y. 2015/2016* - Specification #2

## Project "BiblioManager"

> Version 1.0

### Preamble

The course projects are inspired by real-world needs, and they usually refer to similar sites already on the web. Students must follow the specifications given by this document, but they can also refine them through an interaction with the teacher and the analysis of similar websites. The final website must be completely original, well organized and easily accessible to all the users.

### Site Specifications

The *BiblioManager* site represents a simple online bibliographical catalogue.

The catalogue contains a number of *publications* , each characterized by a *title* , a list of *authors* , a *publisher* , a set of *metadata* (see below) and, optionally, a textual *description* (publication summary or presentation), an *index* (i.e., the chapter/section titles, numbered and sorted) and a set of online *sources* which can be used to access the publication or parts of it. Each source is characterized by a *type* , a *URI* , a *format* and a *description*. Examples of valid sources could be the following:

* type="image", URI ="http://server.net/cover.jpg", format= "image/jpeg", description="cover"

* type="download", URI="http://server.net/book.pdf",format="application/pdf", description="free electronic version"

* type="purchase", URI="http://www.amazon.it/xyz",format="paper, hardcover", description="buy online"

Finally, publication metadata consist of (at least) the following information: *ISBN* , number of *pages* , *language* , *date* of publication, list of *reprints* (number and date) and *keywords* (zero or more).

The following list contains a brief description of the contents and functionalities required by this site. Obviously, any further refinement or enrichment of these specifications will increase the value of the project.
* There will be two classes of users: *active* and *passive* . Passive users can only view the catalogue, whereas the active ones can also update it. *Anonymous* users can view the site homepage, but a login is required in order to access all the other content.

* Passive users can register on the site using a form, filling it with their personal information, an email address (which will be used as their username) and, of course, the chosen password. Active users can "promote" any registered passive user, making it active. Thus, the system will provide a default pre-registered active user.

* The site homepage lists the latest publications added and/or recently updated. The page also presents a list of the more "collaborative" active users (i.e., the ones who entered more publications): by clicking on their name, users will be able to view the list of publications they added to the catalogue (*optionally* formatted as the search results described in the following paragraphs).

* Users can browse the complete catalogue in a paginated list, showing all the publications with their title, author, publisher and year of publication. The list should be orderable using title and year as the key (the title will be the default-ordering key) and *optionally* using all the other columns. Selecting a publication, the user accesses its complete bibliographic record.

* Obviously, the site must offer also a search system in order to allow users to find their publications of interest using various criteria, without necessarily navigating the complete list described in the previous point. The search criteria to support are ISBN, title, author, publisher, year of publication, keywords, language, presence of sources of type "download" (indicating free publications). The user should be able to specify one or more of the above criteria, which will be AND-combined. The search results list should have the same format and functionalities of the complete catalogue listing described in the previous point. Obviously, any improvement to this search functionality, for example with the addition of further criteria, will increase the value of the project.

* The bibliographic record must show, in the clearest and well-structured way possible, all the information related to the publication. If required, you can also use sub-pages, accessible from the main bibliographic record, to better organize the information. Sources of "image" type, if present in the publication data, must be used to create an image gallery displayed in the bibliographic record or in an appropriate sub-page. In particular, a source of "image" type with description "cover", if available, should be shown at the beginning of the bibliographic record, next to the title.

* There will be also a social section, where (active and passive) users should be able to *recommend* the reading of a publication or enter a *review* . The number of "recommendations" given to a publication is displayed in the bibliographic record together with its most recent review, and the complete (*optionally* paged) list of reviews is available in a suitable sub-page. The reviews, however, will not be immediately visible, but will be subject to moderation, as described later.

* Active users can update the publications. Thus, you should provide appropriate forms through which to enter, edit and delete every detail of the publications. In particular, the "edit" and "delete" functions should be accessible via appropriate links added to the bibliographic records when accessed by an active user. Similarly, the "add" links should be shown to active users at the beginning of the main catalogue listing.

* Active users, when accessing a bibliographic record, should also see how many new reviews (for that publication) are waiting to be approved. These reviews are visible, in their case, along with the approved reviews, but suitably highlighted as "awaiting moderation" and including a link to approve them (i.e., make them visible to all), or delete them permanently.

* To keep track of the changes made to the bibliography by active users, the system must maintain a "history" of each bibliographic record. Each entry of this history contains a timestamp, the username and a description of the modifications. You can decide the detail level of this description: descriptions like "changed the publication", "added the publication", "approved a review of user X", etc. are also acceptable. This publication history, properly formatted, should be visible to all the active users from the corresponding bibliographic record.

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
