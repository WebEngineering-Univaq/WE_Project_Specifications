---
titolo: Internship tutor
numero: 2
versione 2.0
lingua: EN
anno: 2018
materia: IW
mainfile: Progetto_Master.rcp
thisfile: specifica
---

-------

{#specifiche}

The *Internship
tutor* site is a web system for managing the complete process related to university internships. In particular, the system should allow companies to register and, with the administrator approval, sign an agreement with the university and independently publish internship proposals. Students will be able to freely access these proposals, contact the company, print all the documentation necessary for the start-up and conclusion of the internship itself, and finally provide their opinion on the company and the internship.

A company must be registered with the following information (see the agreement template downloadable from http://www.disim.univaq.it/didattica/risorsa-1632): company name, address, tax code / VAT number, name and surname of the legal representative, name, surname, telephone number and e-mail address of the contact person for the internships.

An internship offer must specify (see the first pages of the internship project template downloadable from http://www.disim.univaq.it/didattica/risorsa-2767): the location where it will take place (which can be also "at home", if it can be carried out remotely), the work schedule (if provided), the number of months/hours of internship, the internship objectives and interaction modalities (e.g., teamwork, remote freelance work, etc.), the presence of any reimbursement of expenses or other benefits.

The interested student will also have to register to the system (or update his registration), entering the data required by the first page of the internship project, i.e., name, date and place of birth, address, tax code, telephone number and degree in which he/she is enrolled.

At the time of the internship activation, the student will finally have to provide all the other data required by the first three pages of the internship project *that are
not already deductible from the company registration, from his personal data,
or from the internship offer*.

At the end of the internship, the company will have to enter the information necessary to complete the last page of the internship project, i.e., the internship hours actually carried out, the detailed description of the activity and the final judgment.

-------

{#operazioni}

- The system must manage four types of users: *anonymous* , *student* , *company* and *administrator*.

- Companies can register freely by providing the data seen above. At the time of registration, the company will not be visible to students nor will it be able to publish proposals. The registration will be notified to the administrator who will take care of completing the agreement process.

- The administrator, after a new company has registered, verifies (manually) the data entered and automatically generate the agreement document (http://www.disim.univaq.it/didattica/risorsa-1632). *Tip:
  you can simply transform the indicated document into an HTML template, which
  you will automatically fill with the data provided by the company, then
  allowing it to be printed from the browser. Optionally, you can try to generate
  a PDF directly or by converting the generated HTML.*Once the agreement has been signed and returned (manual step: assume it happens), the administrator will upload a scan of the signed agreement (for example a PDF), associating it with the company data, to finally allow the company to publish its proposals.

- An authorized company can publish internship proposals directly from the web, using the credentials provided during the registration process, and specifying all the information required.

- Students initially access the site anonymously. In this way, they are able to read the list of companies and their internship proposals, which can be searched with criteria such as the city where the internship will take place, the minimum/maximum duration, the keywords contained in the objectives, etc.

- When a student decides to apply for an internship, he/she will be asked to log in (if already registered) or register, providing the data described in the initial paragraphs of this specification. The student must also specify the number of credits requested and the data (name and email) of the chosen university tutor. At this point, the system will send an email to the contact person of the company (specified during registration) and another one to the tutor, with the details of the offer and all the student's data. *Tip:
  use a template to fill in the text of this mail. It is not necessary for your
  application to actually send them: you can simulate it, for example by writing
  the email to a file.*

- The companies should have a summary panel available with the list of published proposals. They will be able to disable a proposal (i.e., make it invisible to students) and view the list of students who applied for each one.

- At the end of an "agreement" phase external to our site, during which the applicant and the company discuss the details of the internship, the company will reject or approve the application with appropriate controls available in the "candidate list" just described.

- If the application is accepted, the company must also specify the internship dates (start-end), and this will automatically generate the first three pages of the internship project (http://www.disim.univaq.it/didattica/resource-2767), allowing it to be downloaded by both the company and the student. *Tip: here
  you can proceed as in the case of the automatic generation of the agreement
  seen above.* The usual offline phase will follow, at the end of which one of the two subjects has to upload into the system a scan of the signed and approved document.

- At the end of the internship, as defined in the previous step, the company will be requested to complete the final report. As usual, this procedure will be carried out online, and will generate a document similar to the last page of the internship project, which the student can download, print and take to the secretariat.

- *Optionally* , after completing the internship, the student may have the opportunity to rate the company by using the classic 0-5 stars scale (which may be in some way associated with the public profile of the company)

- *Optionally* , the administrator may be able to view some statistics such as the most requested tutors, the companies that host more students, the companies with better / worse ratings, and so on.  
