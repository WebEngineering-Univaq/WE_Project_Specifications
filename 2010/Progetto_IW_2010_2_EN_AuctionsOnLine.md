# Web Engineering Course
*Final Projects A.Y. 2010/2011* - Specification #2

## Project "AuctionsOnLine"

> Version 1.0

### Preamble

The course projects are inspired by real-world needs, and they usually refer to similar sites already on the web. Students must follow the specifications given by this document, but they can also refine them through an interaction with the teacher and the analysis of similar websites. The final website must be completely original, well organized and easily accessible to all the users.

### Site Specifications

## Site Specifications

The *AuctionsOnLine* site represents a simple auction system, where sellers offer some objects and buyers make bids to buy them.

Each object has a dedicated page on the site, which shows basic information like name, description and conditions (new, used, damaged, etc..), together with optional elements such as a set of links and a photo. A set of *tags* , i.e., words or short phrases, may be associated with the objects to classify them, in order to facilitate the searches. Finally, the object pages show the corresponding auction status: beginning and end of the auction period, delivery method (mail, courier, etc..) and payment modality (cash, credit card, wire transfer, etc.), base price and minimum raise.

The site is accessed by two types of users: *anonymous* users and *registered* users. Appropriate registration and login functionalities must be provided. Anonymous users can only search the site, while registered users can act both as sellers and as buyers.

The following list contains a brief description of the contents and functionalities required by this site. Obviously, any further refinement or enrichment of these specifications will increase the value of the project.
* All the users must be able to search for objects based on: (1) words or phrases in their name or description, (2) the associated *tags* , (3) the seller's name, (4) the (base) price. The completeness and versatility of the search function, which is an essential element of this kind of site, are left to the initiative of the students. The search results should be presented as a list showing name, seller's name, auction start and end date of each object found. Clicking on an object opens the corresponding description page.

* On the description page of an object, users must be able to click the seller's name to display his/her profile (personal details, email address, etc.) and the list of all the items he/she has put for auction.

* On the description page of an object, and in general wherever *tags* appear, users must be able to click on one of them to automatically start a search for all the associated objects.

* Registered users can add new objects to be put on auction, entering all the required information (as described above), edit their own objects, but only up to the start date of the auction, and remove (delete) their objects, even during the auction.

* Registered users can view the list of their objects and, for the ones currently auctioned, read how many offers there have been so far, the remaining time until the auction closes, and the date, user and amount of the last bid.

* Registered users can join an arbitrary number of active auctions, bidding more than or equal to the base bid and increasing the preceding offer by an amount at least corresponding to the minimum raise.

* Registered users can view the list of objects they make a bid for, together with the time remaining before the end of the corresponding auction. If there was an higher bid from another user, the system will display its amount and give the user the opportunity to make a new bid.

* When the auction ends, the corresponding object is no longer visible in the searches. The higher bidder will receive a notification (on the homepage after the login, and *optionally* via email) of his/her victory, with attached payment information. Similarly, the seller will be notified of the purchase and given the buyer information. If an object did not receive any offer, however, the seller can update its information and possibly set the dates of a new auction.

* The homepage of the site shows some general information, such as the latest objects put for auction, the ones with higher raises, etc.

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
