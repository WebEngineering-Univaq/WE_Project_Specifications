---
titolo: Web of Forms
numero: 1
lingua: EN
anno: 2021
materia: IW
mainfile: Progetto_Master.rcp
thisfile: specifica
---

-------

{#specifiche}

The *Web of Forms* website is a handy way to generate formatted forms (standard letters, public forms, etc.) without using a word processor. The idea is to exploit the potential of HTML and templates, which we learned to use for the creation of web pages, also to generate forms printable or otherwise exportable in common document formats such as PDF. To this aim, users-authors will be able to create templates for standard documents *(tip: starting from a document you already have in a word processor
format, you can use the common "save as HTML" function to generate an
initial draft of such template)* and define the name and type of the placeholder fields they contain. Other users of the site will then be able to fill in these fields and view (as HTML) or download (as PDF) the resulting formatted document. In particular, the system will support (with the suitable form controls) the input of text fields, numbers, and textual values chosen from a list. For sake of simplicity, we omit tables (for example the rows of an invoice), but if you try to include them, it will be a great added value for your project! *Tip: study in-depth how to combine, in
your template engine, a data model with a template loaded as a string from the
database, and how to have the output written to a second string. For HTML-PDF
conversion, use the converter provided by iText
(https://itextpdf.com/en/products/itext-7/convert-html-css-to-pdf-pdfhtml,
https://itextpdf.com/en/blog/technical-notes/pdfhtml-configuration-options).*

-------

{#operazioni}

- Users will be able to register in the system by providing a nickname and an email address.

- Once authenticated, users will be able to upload a template in three steps: 1) provide its name and description, 2) upload the HTML template (file upload and/or direct input in a text field), 3) provide name, type, descriptive text and internal name (the one used in the template and to be inserted in the data model) for each of the placeholder fields in the template.

- A new template will be accessible only to administrative users (which we simply assume to be users with special privileges) until one of them, having tested it, will make it public.

- Authors of a template can delete or modify it at any time. The system will keep track of the last modification date and include a version counter to be incremented with each modification. This information should be clearly presented to users, so that they know if and when the template has been changed.

- The process of filling out the form by users (*even
  anonymous*) will be as follows:
  1. Users will be able to choose a module from a list. *Optionally, to help users make their choice, you could provide a
   preview of the form by filling it in "on the fly" with random data
   associated with all of its fields.*

  2. Once a form has been selected, the system must generate and show to the user an appropriate form in which to enter the values of all the fields required by the form itself*. In this phase,
   try to assist users as much as possible, e.g., use the right controls for each
   type of field and provide some kind of validation, also on the client side.*

  3. Once the field values have been sent (and validated on the server), the server will combine them with the template, providing the user with a final HTML version of the completed form.

  4. After examining the result, the user can choose to go back (to step 2 to change the values of the fields or to step 1 to choose another template) or download the completed template both in HTML format (the same displayed ) and in PDF format (converted from HTML as explained above).

- The user should also be able to download, in step 3, a file in JSON format containing the definition of the completed form, that is, the name of the template and the list of fields with their values. The system should provide a way to load this kind of file in step 1, going directly to the final preview (step 4), with the ability to go back and correct the choices, as already illustrated.

- Finally, registered users should be able to send feedback to the form authors by sending them text messages that can be read by the authors themselves, once authenticated, in a special personal area.  
