# Web Engineering Course
*Final Projects A.Y. 2010/2011* - Specification #1

## Project "BooksOnLine"

> Version 1.0

### Preamble

The course projects are inspired by real-world needs, and they usually refer to similar sites already on the web. Students must follow the specifications given by this document, but they can also refine them through an interaction with the teacher and the analysis of similar websites. The final website must be completely original, well organized and easily accessible to all the users.

### Site Specifications

The *BooksOnLine* websiteis a simple web interface for a library.

The website database contains information on the books, the library (registered) users and the book loans. In particular, for every book we have the ISBN, title, language, publisher, year of publication, the names of all authors and, *optionally* , a review or a short description (like the one that often appears on the back cover of the book). A set of *tags* , i.e. words or short phrases (e.g., "computer", "programming", "C++ language", etc.), is also associated to each volume and can be, e.g., extracted from the book title and/or entered by librarians. Each book has a maximum loan duration (default: one month) and may be present in the library in multiple copies. Finally, some books are marked "free to read" and therefore accessible directly online in the form of downloadable text or PDF files. For each book, the site generates a description page containing all the above information, suitably organized.

The site is accessed by of three types of users: *librarians, registered users* and *anonymous* *users* . Appropriate login procedures must be provided. **We assume that only librarians can add new users (including other librarians) to the system** (which is initialized with a single default "root librarian"), e.g., it may be possible to register a new user when he/she deposits his/her credentials to the library. Each registered user is associated with a profile containing some basic personal data, an email address and a phone number.

The following list contains a brief description of the contents and functionalities required by this site. Obviously, any further refinement or enrichment of these specifications will increase the value of the project.
* Users must be able to search for books based on: (1) their title or part of it, (2) the associated *tags* , (3) one or more of the authors, (4) the ISBN. The completeness and versatility of the search function, which is an essential element of this kind of site, are left to the initiative of the students. The search results should be presented as a list showing title, author, publisher and year of each book found. Clicking on a listed book opens the corresponding description page.

* On the description page of a book, users must be able to click on an author's name to automatically start a search for all the books written by him/her (i.e., his/her complete bibliography).

* On the description page of a book, and in general wherever *tags* appear, users must be able to click on one of them to automatically start a search for all the associated books.

* On the description page of a book, users must read the number of copies in the library and the number of those copies which are currently free (not borrowed). *Optionally,* if all the copies are on loan, the site may indicate the expected return date of the first copy, calculated from the date of the loan and the maximum loan duration.

* Librarians, after having looked up a particular book (using the search functions listed above) must be able to register a loan on behalf of a user known to the system.

* Registered users can view the list of books that they have borrowed and the corresponding return date. The books whose return date has expired should be appropriately marked. Users may also view the entire list of books already borrowed and returned (*loan history*).

* Librarians must be able, from the description page of a book, to view all the related loans, past or present. In addition, librarians can view a list of all the books on loan, where those whose return date is expired are suitably highlighted.

* The site homepage shows some general information, such as the most borrowed books and the books recently added to the library. For registered users, the homepage also reminds the books to be returned shortly.

* The site must be provided with adequate *backoffice,* accessible only to librarians, which allows to enter and edit all the data associated with the books.

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
