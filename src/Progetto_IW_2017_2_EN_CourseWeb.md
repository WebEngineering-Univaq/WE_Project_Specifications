---
titolo: CourseWeb
numero: 2
versione 2.0
lingua: EN
anno: 2017
materia: IW
mainfile: Progetto_Master.rcp
thisfile: specifica
---

-------

{#specifiche}

*After a decade spent trying to find the best way to organize online information about university courses, satisfying the wishes of students, teachers and administrative staff as well as the various regulations on this field, your teacher has (temporarily) run out of ideas, and decided to ask you to realize your " ideal teaching website", hoping to find new inspiration* *J*

The *CourseWeb* site provides an online catalog of university courses, suitably simplified but still meeting the main requirements of transparency and completeness required for this type of website.

The site has to support **bilingual publication** (Italian and English) of all its content. Therefore you should have, for each view, at least two templates (one in Italian and one in English), and you should design the site so that it allows to enter information in both languages in the back-office and select which language to display in the front-office (*optionally*, if the content is not available in a language, the other language available will be always used).

Each course has to be necessarily associated to the following information. Any extra, arising from your personal experience, will be appreciated and perhaps may become an inspiration for the future.

· Basic data: name, code, scientific sector (SSD, for example INF / 01), language, semester

· Lecturers list

· Course description: prerequisites, learning outcomes, assessment method, teaching method, syllabus/analytical program (in general, one point for each credit)

· Textbooks (author, title, volume, year, publisher, web link if available)

· Relations with other courses: introductory courses, same-as courses, modules (for integrated courses)

· External links: course homepage, external resources, forum/eLearning

· Notes (for any detail that does not belong to one of the items above)

*Optionally* , the *learning outcomes* mentioned in the list can be structured according to the so-called *Dublin descriptors* , required by the European standardization process. The descriptors the course objectives to be described thorugh of the results achieved in five areas: *knowledge* (what knowledge is acquired through the course?), *Application* (how and where the knowledge arising from the course can be applied?), *Evaluation* (if and how the knowledge gained can help in evaluating, judging, comparing ...?), *Communication* (if and how students can share the knowledge gained?), *Lifelong learning
skills* (the course provides tools to continue learning certain topics? ).

Finally, the following information, while needed in a realistic course catalogue, in our project will be *optional*: the more you add, the more your project will have value.

· The list of degrees/curriculums where the course is taught, with indication of its value in credits (ECTS), and the respective type (A, B, C, D, F).

· List of teaching support items (with name, description and size) that can be downloaded from the website (such as PDF documents).

In order to create a "virtual guide" **the system must collect all this information year
by year** . This means that you should **create a system where all the
information above is associated with an academic year**, and there can be several copies for different academic years.

-------

{#operazioni}

- The system has three types of users: *anonymous* , *teacher* and *administrator*. Only administrators can register new users and assign them a type.

- All the users can view the complete list of courses, possibly filtered by name (also partial), code, SSD, semester, teacher, language and degrees for which it is available (if you have modeled such information). Clicking on a course will display its full record.

- Of course, the course page must be very well-finished, to make the contained information as clear and accessible as possible. You can split the data across multiple pages, remembering, however, that the essential information must be accessible with a small number of clicks.

- Site administrators can create courses (with at least the essential information: name code) and assign them to the teachers.

- Teachers can enter and edit all information belonging to their assigned courses, while administrators can modify all the courses.

- The back-office for teachers should also be very intuitive. It may be useful to provide contextual help to clarify the meaning of the various fields, and possibly split the course information into logical segments to be compiled in a wizard-style process. Where possible (e.g., in the selection of related courses, of languages, semesters, SSD, types of credits, etc.) the input should be assisted or guided.

- The site must have a log where all transactions carried out through the back-office are recorded (such as "User X has changed the course Y": you can decide which level of detail to include in these entries).

- Finally, to realize the "virtual guide" described above, the site should behave as follows:
1. the information presented in a course page are, by default, those related to the last academic year (which must be indicated on the page) where the course has been updated.

2. the user should be able to choose an academic year and read the course information related to such academic year, if available (e.g., through controls on the course page, or using suitable filters on the course list).

3. in the back office, the information entered or edited by the teacher are always related to the current academic year. When a teacher tries to change the information of a course, and no information is available for the current year, the information belonging to the closest past year are automatically copied to the current year. *Optionally*, administrators may be able change the course information for any academic year.  
