<html>
<head>
<meta charset="UTF-8"/>
<title>${nomecorso}: Final Course Projects</title>
<style>${css?no_esc}</style>
</head>

<body>

<div class="intestazione">
<div class="nprogetto">${numero!""}</div>
<div class="ncorso">${nomecorso} Course</div>
<div class="aa">Final Projects A.Y. ${anno}/${(anno?number)+1}</div>
</div>

<h1>Project "${titolo}" <span class="versione">Version ${versione!"1.0"}</span></h1>

## Preamble

The course projects are inspired by real-world needs, and they usually refer to similar sites already on the web. Students must follow the specifications given by this document, but they can also refine them through an interaction with the teacher and the analysis of similar websites. The final website must be completely original, well organized and easily accessible to all the users.  

## Site Specifications

<div>${body_specifiche?no_esc}</div>

The following list contains a brief description of the contents and functionalities required by this site. Obviously, any further refinement or enrichment of these specifications will increase the value of the project.

<div>${body_operazioni?no_esc}</div>

## Technologies

- The basic structure of the site must be created using HTML5.The validation of all the site pages with respect to the chosen HTML flavour is an important part of the development and **must**be reported in the documentation.
- The site layout must be realised using CCS style sheets. The layout can be freely based on third party layouts available on the web or shown during the lectures. In this case, the degree of **customization**of the layout will be taken into account in the final project assessment. **A responsive layout is not
required, but strongly suggested.**
- For the *client-side* programming, JavaScript is the required language. It is possible to include libraries developed by third parties, provided that they have suitable cross-browser portability and that they are described in the project documentation. However, **any
abuse of these technologies is not recommended** , especially when they can be replaced with a suitable use of HTML, CSS, etc. **In general, your site should
be functional also with JavaScript disabled** . The site without scripts may be less "friendly" or allow the access to "core" functionalities only, but sites whose dynamics is entirely script-based are not allowed. However, **scripts
can play a more important a role in the functionalities whose users are restricted
and pre-determined** (e.g., in the *back-end* functionalities for administrators, but not in the public *front-end*or in the login procedure).
- For the *server-side* programming, Java *(servlets,
JSP)* is the **required** language*.* Any DBMS and template engine can be employed, if required*.*Again, it is possible to rely on
external libraries.
- In general, the site must work and have a good *rendering* on the latest versions of Edge, Firefox and Chrome, and *possibly* be compatible with older browsers (in this case it should at least *degrade
well)*and with the latest versions of other browsers, like Opera. Browser
compatibility **must**be explicitly stated in the documentation.  

## Project Development and Documentation

The specifications may not be exhaustive or completely defined. Every feature added or refined, also through an interaction with the stakeholder or the site end users, should be adequately discussed. All the design choices must be discussed and motivated.

The final project, developed following the guidelines given by the present specification, must be a fully functional website, whose contents and features will be assessed during the examination. The specification parts marked as *optional*, if not developed, will not make the project insufficient but, on the other hand, they will not allow your project to reach the highest mark. If you choose to implement an optional feature, the result should not be necessarily perfect or complete: it must only show your commitment to deal with an advanced issue.

The documentation (**in electronic format** ) which accompanies the project **must**contain at least the following information:
- Indication of software dependencies (which libraries are required on the client and server side?).
- Indication of the functionalities that have been developed or not developed. Detailed description of any extra or optional functionality added to the project.
- Diagram showing the site structure.
- Relational schema of the database (if any).
- Analytical description of the site layout, also indicating its static/dynamic components.
- Description of any advanced technology (language, framework, plugin, library, etc.) used in the project, specifying the reason of its adoption and the actual contribution given to the project development.
- Description of *any*cross-browser programming/rendering problem encountered, list of compatible browsers.
- Screenshots of the most important website pages (*optional*).

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

<#if (scheda??)>
## Project Summary Card
{.break}

This summary should be compiled and sent to the teacher, in electronic format, *before* the examination. A copy of this form should be also attached to the project documentation.

**Project name:**   &nbsp;
{.linetocompile}

**Authors**:  

<table>
<thead>
<tr><th style="width:20%">Nome</th><th style="width:20%">Cognome</th><th style="width:10%">Matricola</th><th>Ruolo nello sviluppo del progetto</th></tr>
</thead>
<tbody>
<tr><td> </td><td> </td><td> </td><td> </td></tr>
<tr><td> </td><td> </td><td> </td><td> </td></tr>
<tr><td> </td><td> </td><td> </td><td> </td></tr>
<tr><td> </td><td> </td><td> </td><td> </td></tr>
<tr><td> </td><td> </td><td> </td><td> </td></tr>
</tbody>
</table>

**Client-side technologies/libraries/frameworks:** (HTML5, CSS 2/3, Javascript, JQuery, Bootstrap...)   &nbsp;
{.linetocompile}

  &nbsp;
{.linetocompile}

  &nbsp;
{.linetocompile}

**Server-side technologies/libraries/frameworks:** (e.g., JSP, MySQL, JPA, template engines...)   &nbsp;
{.linetocompile}

  &nbsp;
{.linetocompile}

  &nbsp;
{.linetocompile}

**Compatible browsers:**  

| **Browser**                    | **Version** | **Compatible** | **Degrading** | **Not compatible** | **Not tried** |
|--------------------------------|-------------|----------------|---------------|--------------------|---------------|
| **Internet Explorer**/**Edge** |             |                |               |                    |               |
| **Mozilla Firefox**            |             |                |               |                    |               |
| **Google Chrome**              |             |                |               |                    |               |
| **Opera**                      |             |                |               |                    |               |
| **Safari**                     |             |                |               |                    |               |
| &nbsp;                               |             |                |               |                    |               |
| &nbsp;                               |             |                |               |                    |               |

**Project discussion date:**   &nbsp;
{.linetocompile}


</#if>


</body>
</html>