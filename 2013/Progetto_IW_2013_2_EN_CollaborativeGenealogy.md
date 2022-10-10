# Web Engineering Course
*Final Projects A.Y. 2013/2014* - Specification #2

## Project "CollaborativeGenealogy"

> Version 1.0

### Preamble

The course projects are inspired by real-world needs, and they usually refer to similar sites already on the web. Students must follow the specifications given by this document, but they can also refine them through an interaction with the teacher and the analysis of similar websites. The final website must be completely original, well organized and easily accessible to all the users.

### Site Specifications

*CollaborativeGenealogy* is a social site to build your own family tree while contributing to the refinement of other users' one.

The site is accessible to registered users only. When registering, a new user must supply (and won't be able to change later) his/her full personal details, including date/place of birth and email address. Users can also provide their contact information (address, phone numbers, etc.) and, *optionally*, write and update a short textual biography and upload a photo for their profile. The "social" aspect of the system lies in the way family trees are built.

The following list contains a brief description of the contents and functionalities required by this site. Obviously, any further refinement or enrichment of these specifications will increase the value of the project.
* Anonymous users (the ones accessing to the site without logging in) can only see a simple presentation page, a login/registration form and a search form. The search is performed on first and last names of registered users, and the results only show the full name of the found users and the number of "relatives" in their family tree . In this way, anonymous users are able to "test" the usefulness of the service, without violating the privacy of registered users, and then register to use all the site functionalities.

* Registered users, on the other hand, can search for other users by specifying different parameters, including first and last name (finding people with your last name is a good starting point to search for a possible relationship!), date and place of birth. The user should be able to combine these parameters to perform refined searches. The search results contain, in this case, name, surname, date and place of birth of each user found.

* To create a family tree, the user can proceed in three ways. *Note* : to simplify the system, we assume that the user can add only direct relatives, i.e., *father, mother, sons* and*brothers/sisters* of people already in his/her family tree. Thus, to add the maternal grandfather, the user must first add his/her mother and then her father.

  1. After performing a search and identifying some possible relatives, the user can add them to the family tree.
  2. If a relative is not registered in the system, the user can create his/her basic profile (name, email address, date and place of birth) and add him/her to the family tree.
  3. Finally, to handle relatives cannot be reached (or are dead), the user can also create a basic profile as specified above, *but without an email address* , and add it to the family tree. In this case, the added relationship will always be displayed by the system as "*unverified*".
* In all cases, to actually add an relative to the family tree, the user must specify the tree position to attach the new relative to and the corresponding relationship (*father, mother, son, brother/sister*).

* In cases 1 and 2, i.e., when adding a system-registered relative or manually specifying new one, the possible new family member has to approve the declared relationship. The relationship will not be considered effective and will not be shown in the genealogy of the user until the new relative validates it. Once the relationship is verified, the two users become part of the same "family" and can see all the biographical data of the other, as well as navigate his/her family tree.

* The potential relative is notified by email (*hint: you don't need to send a real email, in this prototype it will be enough to show the text that you would send...* ) with the information of the "proposer" and the type of relationship proposed, which can be approved or rejected. Registered users (added as in case 1) will be able to log into their account and make this choice. Unregistered users (added as in step 2) will receive in the notification email an invitation to register and approve the relationship .

* The system will eventually allow registered users to "navigate" their family tree, showing first the direct relationships and allowing the user to expand step by step the "relatives of relatives", and so on. This navigation will include the tree directly built by the user as well as the sub-trees built by his/her verified relatives. A *breadcrumb* system, i.e., a navigation path, will allow to derive the family relationship of the currently selected relative. As an example, on the main page of my profile, I click on my father, "Tom". The page then shows the path to the current relative "Me \> Tom (father)", the Tom's biographical data and all his direct relatives (mother, father, sons, brothers/systers). Then, clicking on his father "Dick" displays a page whose path is "Me \> Tom (father) \> Dick (father)", and so on. *Optionally*, you may attempt to automatically derive the overall relationship of the selected relative based on this path: in this case, for example, the page may show "Dick is your paternal grandfather".

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
