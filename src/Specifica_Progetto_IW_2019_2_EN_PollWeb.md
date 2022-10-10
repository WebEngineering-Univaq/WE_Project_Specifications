---
titolo: PollWeb
numero: 2
lingua: EN
anno: 2019
materia: IW
mainfile: Progetto_Master.rcp
thisfile: specifica
---

-------

{#specifiche}

The *PollWeb* site is a simple system for conducting online surveys. Each survey has a *manager* user, a title, an opening and a closing text, and consists of a series of questions. Each question, in turn, can be of one of the following types:

1) *Short text*: a line of text;
2) *Long text*: multiple lines of text;
3) *Number*: numbers only;
4) *Date*: only dates, optionally with associated time;
5) *Single choice*: a series of options are presented and the user must choose exactly one of them;
6) *Multiple choice*: a series of options are presented and the user can choose one or more of them.

All the question types above have some common attributes: *code* (used to uniquely identify the question), *text* (the text of the question, optionally in HTML), *note* (an explanatory note that might appear after the question text to guide the compilation), *mandatory* (if set, indicates that the user must necessarily answer the question, or choose (at least) one of the answers in the case of multiple choice questions). Other attributes can be added to each question type to further specify it, for example

- Minimum and maximum length of a text field;
- *Minimum and maximum value* for numeric fields (and maybe also for dates);
- *Regular expression* that must match a text field;
- Minimum and/or maximum number of selectable options for multiple choices.

These attributes are all optional, but the more you add, the more realistic your project will be.

*Tip* : a very important part of this project will be, clearly, the definition and implementation of a data structure that can model the surveys by aggregating questions that, in turn, can be defined, each with its own characteristics, in the most efficient way, and associated with responses in an equally effective manner.

-------

{#operazioni}

- The system must manage three types of users: *participant* , *manager* and *administrator*. The types are cascaded so, for example, a manager can also be a participant. The data associated with each user must include at least a valid email address.

- The *administrator* is unique and we assume he/she is pre-registered in the system. Managers must be registered by administrators. Later we will see the registration procedure for participants.

- Each *manager* user can create new surveys, to which he will be associated. When creating a survey, all the textual fields (see above) must be provided, and then the questions are defined, as described in the following points.

- To compose the survey, the manager adds the individual questions one at a time, in a sequence. It must be possible to review the sequence of questions already entered in a summary screen, where the most important features of each question are also presented.

- The manager e must be able to modify, delete or rearrange (move up or down in the sequence) the questions.

- Each type of question should have its own insert/modify page, although the various pages should maintain a certain uniformity, at least for the attributes common to all types.

- The survey can be *reserved* or *public* . In the former case (*reserved* survey), the manager must manually enter the data (name, email, password) of the participants who can access the survey. *Optionally* , this data could also be imported from a CSV file. *Please
  note: each survey will have its own participants, so users included in a survey
  will not be able to access other surveys, unless they are registered (by
  repeating the data) also in the latter.* On the other hand, if the survey is *public* anyone can access it, i.e., there will be no authentication procedure.

- Once satisfied with the definition of the survey, the manager can *activate* it, making it fillable. Upon activation, the URL that the participants can use to access the survey will be presented. *Optionally*, in the case of reserved surveys, upon activation the system could send an invitation email, with access URL and credentials, to all registered participants.

- By accessing the survey URL (the one presented to the manager at the time of activation), participants of *reserved* surveys will be asked to authenticate themselves, and then proceed to the compilation. In *public* surveys, the participants will go directly to the compilation. *Please note: in reserved surveys, each user will be able to participate only
  once, so after a successful compilation, his credentials must be disabled.*

- The survey will take place by showing the user all the questions, in the sequence set. You should choose the input technique most suited to each type of question. *Optionally*, you can also present a paged survey, grouping questions.

- Once the answers to the survey have been submitted, the server will carry out all the necessary checks on the validity and on the constraints set on the individual questions, and if successful it will save the answers. In case of error, the user will be asked to repeat the compilation.

- The manager should be able to *close* the survey at any time, inhibiting access to other participants.

- The manager should be able to *export the answers* in CSV format and/or in other useful formats. You can choose the data format to make this file as clear and informative as possible. *Optionally*, the manager may also be able to view the individual answers directly on the web.  
