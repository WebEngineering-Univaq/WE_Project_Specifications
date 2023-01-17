# Web Engineering Course
*Final Projects A.Y. 2012/2013* - Specification #1

## Project "ContentManager"

> Version 1.0

### Preamble

The course projects are inspired by real-world needs, and they usually refer to similar sites already on the web. Students must follow the specifications given by this document, but they can also refine them through an interaction with the teacher and the analysis of similar websites. The final website must be completely original, well organized and easily accessible to all the users.

### Site Specifications

The *ContentManager* site is a simple web-based system for creating static mini-websites without the need for programming or writing of HTML/CSS.

Each mini-site is identified by its author's username and has a tree structure corresponding to the logical structure of the site navigation, with an HTML page associated to each node. The root node always corresponds to the homepage. For example:

Homepage  
\> About  
\> Interests  
\> Ski  
\> Photography  
\> Links  
\> Contacts

All the pages of the mini-site are identified by a numeric code, share the same header and footer, and are displayed using the same stylesheet.

Header, footer, and bodies of HTML pages are stored in the site database, whereas stylesheets are saved on the file system. The system has a default set of stylesheets, each associated with a name and a description, which define the appearance of all major HTML elements (headings, paragraphs, tables, lists, etc.).

The homepage of the mini-site for a particular user can be requested with an URL like http://\<web_application_base_URL\>/site?user=\<*username* \>, whereas any other page with identifier *X* on same site should correspond to the URL http://\<web_application_base_URL\>/site?user=\<*username* \>\&page=*X.*

To answer these URLs, the system dynamically composes the final web page and, in particular, inserts in its body the following four parts: the common header of the mini-site, followed by the contents of the requested page, then a navigation menu (which could appear anywhere on the final page), and finally the common footer. The generated page head should also contain a reference to the stylesheet chosen by the user.

The navigation menu is created automatically from the tree structure of the site, and contains at least a link to the parent of the current page (if it is not the homepage) and links to all its child pages. For example, the menu for the *Interests* page in the structure above should contain links to *Homepage* , *Ski* and *Photography*.

The user can also upload images in the web space, following a suitable procedure, and up to a given maximum size (that is, until the total size of the uploaded images is below a certain limit). Each image is associated to a numeric identifier *Y* , in such a way that it can be downloaded (for example, within a page of the mini-site, with an *img* tag) using a URL like http://\<web_application_base_URL\>/image?user=\<*username* \>\&image=*Y. Tip*: To create a servlet that allows to "download" an image and to figure out how to upload a binary file on the server, see the examples developed during the lectures. Images can be stored in user-specific separate directories or in the same directory, renaming each file so that their names do not conflict. Each numeric identifier must then be mapped on the correct file name on the file system.

The following list contains a brief description of the contents and functionalities required by this site. Obviously, any further refinement or enrichment of these specifications will increase the value of the project.
* Users can register on *ContentManager* by providing their data and a valid email address (the validity check, which can be performed by sending an email with a link to click, is *optional*), and receiving the corresponding login credentials. The system initializes the user web space by creating the homepage (the root of the navigation tree), initially containing a predefined text, and generating a default header/footer for the mini-site (e.g., with the user name, the creation date, etc.).
* Registered users can access their web space, view the site tree structure, edit or delete each page, and create new pages at any level of the tree. When creating a new page, after specifying where it should appear within the tree, the user can choose whether to start from a blank page or from a page template (see below).
* *Optionally* , the user may also have the ability to move a subtree (i.e., a page and all its descendants) in a different position of the navigation tree.
* Registered users can also modify the header and footer of their mini-site.
* Editing of pages and header/footer contents must be performed through a WYSIWYG HTML editor like *ckeditor* (http://ckeditor.com/) or *tinymce* (http://www.tinymce.com/).
* Registered users can view a list of all the images they uploaded in the site, delete some of them or add new ones. The list should clearly show the link (as the one above) to be used to embed or download the image.
* Registered users can view the list of predefined system stylesheets and choose which one to apply to their site.
* Finally, users may make "public" one or more of their pages by marking them as *templates*, so that other users can use them to start new pages of their mini-site, as described above.
* The application homepage should contain, besides the register and login controls, the names of the last created mini-sites, which can be clicked to access the mini-site homepages and then browse them using either the navigation menu or any internal link.

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
