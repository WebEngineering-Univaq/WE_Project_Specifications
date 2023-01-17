# Web Engineering Course
*Final Projects A.Y. 2021/2022* - Specification #1

## Project "Web of Forms"

> Version 1.0

### Preamble

The course projects are inspired by real-world needs, and they usually refer to similar sites already on the web. Students must follow the specifications given by this document, but they can also refine them through an interaction with the teacher and the analysis of similar websites. The final website must be completely original, well organized and easily accessible to all the users.

### Site Specifications

The *Web of Forms* website is a handy way to generate formatted forms (standard letters, public forms, etc.) without using a word processor. The idea is to exploit the potential of HTML and templates, which we learned to use for the creation of web pages, also to generate forms printable or otherwise exportable in common document formats such as PDF. To this aim, users-authors will be able to create templates for standard documents *(tip: starting from a document you already have in a word processor format, you can use the common "save as HTML" function to generate an initial draft of such template)* and define the name and type of the placeholder fields they contain. Other users of the site will then be able to fill in these fields and view (as HTML) or download (as PDF) the resulting formatted document. In particular, the system will support (with the suitable form controls) the input of text fields, numbers, and textual values chosen from a list. For sake of simplicity, we omit tables (for example the rows of an invoice), but if you try to include them, it will be a great added value for your project! *Tip: study in-depth how to combine, in your template engine, a data model with a template loaded as a string from the database, and how to have the output written to a second string. For HTML-PDF conversion, use the converter provided by iText (https://itextpdf.com/en/products/itext-7/convert-html-css-to-pdf-pdfhtml, https://itextpdf.com/en/blog/technical-notes/pdfhtml-configuration-options).*

The following list contains a brief description of the contents and functionalities required by this site. Obviously, any further refinement or enrichment of these specifications will increase the value of the project.
* Users will be able to register in the system by providing a nickname and an email address.

* Once authenticated, users will be able to upload a template in three steps: 1) provide its name and description, 2) upload the HTML template (file upload and/or direct input in a text field), 3) provide name, type, descriptive text and internal name (the one used in the template and to be inserted in the data model) for each of the placeholder fields in the template.

* A new template will be accessible only to administrative users (which we simply assume to be users with special privileges) until one of them, having tested it, will make it public.

* Authors of a template can delete or modify it at any time. The system will keep track of the last modification date and include a version counter to be incremented with each modification. This information should be clearly presented to users, so that they know if and when the template has been changed.

* The process of filling out the form by users (*even anonymous*) will be as follows:

  1. Users will be able to choose a module from a list. *Optionally, to help users make their choice, you could provide a preview of the form by filling it in "on the fly" with random data associated with all of its fields.*

  2. Once a form has been selected, the system must generate and show to the user an appropriate form in which to enter the values of all the fields required by the form itself\*. In this phase, try to assist users as much as possible, e.g., use the right controls for each type of field and provide some kind of validation, also on the client side.\*

  3. Once the field values have been sent (and validated on the server), the server will combine them with the template, providing the user with a final HTML version of the completed form.

  4. After examining the result, the user can choose to go back (to step 2 to change the values of the fields or to step 1 to choose another template) or download the completed template both in HTML format (the same displayed ) and in PDF format (converted from HTML as explained above).

* The user should also be able to download, in step 3, a file in JSON format containing the definition of the completed form, that is, the name of the template and the list of fields with their values. The system should provide a way to load this kind of file in step 1, going directly to the final preview (step 4), with the ability to go back and correct the choices, as already illustrated.

* Finally, registered users should be able to send feedback to the form authors by sending them text messages that can be read by the authors themselves, once authenticated, in a special personal area.

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
