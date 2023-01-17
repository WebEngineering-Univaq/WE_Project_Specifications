# Web Engineering Course
*Final Projects A.Y. 2018/2019* - Specification #2

## Project "Internship tutor"

> Version 1.0

### Preamble

The course projects are inspired by real-world needs, and they usually refer to similar sites already on the web. Students must follow the specifications given by this document, but they can also refine them through an interaction with the teacher and the analysis of similar websites. The final website must be completely original, well organized and easily accessible to all the users.

### Site Specifications

The *Internship tutor* site is a web system for managing the complete process related to university internships. In particular, the system should allow companies to register and, with the administrator approval, sign an agreement with the university and independently publish internship proposals. Students will be able to freely access these proposals, contact the company, print all the documentation necessary for the start-up and conclusion of the internship itself, and finally provide their opinion on the company and the internship.

A company must be registered with the following information (see the agreement template downloadable from http://www.disim.univaq.it/didattica/risorsa-1632): company name, address, tax code / VAT number, name and surname of the legal representative, name, surname, telephone number and e-mail address of the contact person for the internships.

An internship offer must specify (see the first pages of the internship project template downloadable from http://www.disim.univaq.it/didattica/risorsa-2767): the location where it will take place (which can be also "at home", if it can be carried out remotely), the work schedule (if provided), the number of months/hours of internship, the internship objectives and interaction modalities (e.g., teamwork, remote freelance work, etc.), the presence of any reimbursement of expenses or other benefits.

The interested student will also have to register to the system (or update his registration), entering the data required by the first page of the internship project, i.e., name, date and place of birth, address, tax code, telephone number and degree in which he/she is enrolled.

At the time of the internship activation, the student will finally have to provide all the other data required by the first three pages of the internship project *that are not already deductible from the company registration, from his personal data, or from the internship offer*.

At the end of the internship, the company will have to enter the information necessary to complete the last page of the internship project, i.e., the internship hours actually carried out, the detailed description of the activity and the final judgment.

The following list contains a brief description of the contents and functionalities required by this site. Obviously, any further refinement or enrichment of these specifications will increase the value of the project.
* The system must manage four types of users: *anonymous* , *student* , *company* and *administrator*.

* Companies can register freely by providing the data seen above. At the time of registration, the company will not be visible to students nor will it be able to publish proposals. The registration will be notified to the administrator who will take care of completing the agreement process.

* The administrator, after a new company has registered, verifies (manually) the data entered and automatically generate the agreement document (http://www.disim.univaq.it/didattica/risorsa-1632). \*Tip: you can simply transform the indicated document into an HTML template, which you will automatically fill with the data provided by the company, then allowing it to be printed from the browser. Optionally, you can try to generate a PDF directly or by converting the generated HTML.\*Once the agreement has been signed and returned (manual step: assume it happens), the administrator will upload a scan of the signed agreement (for example a PDF), associating it with the company data, to finally allow the company to publish its proposals.

* An authorized company can publish internship proposals directly from the web, using the credentials provided during the registration process, and specifying all the information required.

* Students initially access the site anonymously. In this way, they are able to read the list of companies and their internship proposals, which can be searched with criteria such as the city where the internship will take place, the minimum/maximum duration, the keywords contained in the objectives, etc.

* When a student decides to apply for an internship, he/she will be asked to log in (if already registered) or register, providing the data described in the initial paragraphs of this specification. The student must also specify the number of credits requested and the data (name and email) of the chosen university tutor. At this point, the system will send an email to the contact person of the company (specified during registration) and another one to the tutor, with the details of the offer and all the student's data. *Tip: use a template to fill in the text of this mail. It is not necessary for your application to actually send them: you can simulate it, for example by writing the email to a file.*

* The companies should have a summary panel available with the list of published proposals. They will be able to disable a proposal (i.e., make it invisible to students) and view the list of students who applied for each one.

* At the end of an "agreement" phase external to our site, during which the applicant and the company discuss the details of the internship, the company will reject or approve the application with appropriate controls available in the "candidate list" just described.

* If the application is accepted, the company must also specify the internship dates (start-end), and this will automatically generate the first three pages of the internship project (http://www.disim.univaq.it/didattica/resource-2767), allowing it to be downloaded by both the company and the student. *Tip: here you can proceed as in the case of the automatic generation of the agreement seen above.* The usual offline phase will follow, at the end of which one of the two subjects has to upload into the system a scan of the signed and approved document.

* At the end of the internship, as defined in the previous step, the company will be requested to complete the final report. As usual, this procedure will be carried out online, and will generate a document similar to the last page of the internship project, which the student can download, print and take to the secretariat.

* *Optionally* , after completing the internship, the student may have the opportunity to rate the company by using the classic 0-5 stars scale (which may be in some way associated with the public profile of the company)

* *Optionally* , the administrator may be able to view some statistics such as the most requested tutors, the companies that host more students, the companies with better / worse ratings, and so on.

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
