# Web Engineering Course<br/>*Final Projects A.Y. 2023/2024* - Specification #1

<section class="specifica">

## Project "WebMarket"
> Version 1.0

### Preamble

The course projects are inspired by real-world needs, and they usually refer to similar sites already published on the web. 
Students must follow the specifications given by this document, but they can also refine them through an interaction 
with the teacher and the analysis of similar websites. 
The final website must be completely original, well organized and easily accessible to all the users.  

### Site Specifications

<section class="descrizione">




The *WebMarket* site represents an online purchasing system similar to the various eCommerce that we all know, but *constrained* and *guided*, as it is designed to be used within a public organisation.

The site has two types of users: *purchasers* and *technicians*. The system will also include an *administrator* with the sole purpose of registering other users.

The system works as follows (obviously we will simplify many steps to avoid making the project too heavy, so some points may be unrealistic... you are free to make them more complete and complex!).

1. **Definition of the *purchase request*.** The purchaser is initially guided in the selection of a *category* (for example *Desktop PC*, *Notebook*, *Desktop*,...) that identifies the type of product to purchase (*optionally the categories may have a tree structure, for example IT > Computer > Notebook*). Each product category has a series of specific *features* associated with it (e.g. amount of RAM and type of CPU for a PC, etc.). The purchaser has then to enter the values of all the desired characteristics relating to the selected product category (for each characteristic the *indifferent* option will always be provided). There is also be a *note* space to add any peculiar features not included among the standard ones.

2. **Definition of the *purchase proposal*.** The *purchase request* defined in point 1 is forwarded to the technical staff, who receives a notification. A member of the staff takes then charge of the request, becoming the *technician in charge* of the request. The technician in charge views the category and characteristics requested by the purchaser and then searches (externally to the system) for an actual product to order (which we shall call *purchase proposal*), associating its description (which includes at least manufacturer name, product name, product code, price, URL for further information and a notes) to the *purchase request*.

3. **Review of the purchase proposal.** The purchaser, notified of the entry by the technician in charge of the proposal relating to his request, reviews and *approves* or *rejects* it, providing a motivation in the latter case. In the event of a rejected request, the process resumes from step 2, considering that the technician in charge will always be the same. The motivation for the refusal will be shown together with the request information, and the technician in charge will be able to modify the proposed product and forward it again to the purchaser.

4. **Execution of the *purchase order*.** If the purchaser approves the purchase proposal in step 3, this is be notified to the technical staff who will then proceed to define the corresponding *purchase order* (this part will not be managed by our application).

5. **Delivery and verification of the *purchase order*.** When the product is delivered (sooner or later!), the purchaser has to *close* the corresponding purchase request indicating whether the product received has been *accepted*, *rejected because non-compliant* or *rejected because not working*.


</section>


The following list contains a brief description of the contents and functionalities required by this site. Obviously, any further refinement or enrichment of these specifications will increase the value of the project.


<section class="operazioni">
  


- Access to the application will be restricted to registered users only. An administrator must be provided, with the role of registering new purchasers and new technicians in the system.

- After logging in, users will see a dashboard containing

    - for purchasers, purchase requests in progress and already closed. Purchase requests for which there is an associated proposal (not yet accepted) will be highlighted.
   
    - for technicians, the list of requests not yet assigned and those for which they are in charge. Requests with accepted or rejected proposals will be highlighted.

- Purchasers will be able to create a new purchase request at any time, as indicated in point 1 of the previous procedure.

- The technicians will be able to take charge of the requests not yet assigned and, later, insert the proposal details in the requests assigned to them, as described in point 2.

- Purchasers will be able to view the details of their requests and any associated proposal, with the option to accept or reject them as described in point 3.

- Technicians will be able to mark a purchase request with an accepted proposal as "ordered" (point 4) to update the purchaser on the *status* of his request (always visible together with the request itself in the dashboards).

- Once their request has been placed in "ordered" status, the purchasers will be able to proceed with the closure at any time as described in point 5.

- All the main steps just described (request, proposal, acceptance or rejection, order, closure) should be appropriately notified to the parties involved, for example by email, as well as highlighted in the dashboard of interested parties.  
  </section>

<section class="indicazioni break">

# Directions for Project Development

### Technologies

- The basic *structure* of the site must be created using **HTML5**. The validation of the main site pages 
is important and must be reported in the documentation.

- The site *layout* must be realised using CCS style sheets. The layout can be freely based 
on third party layouts available on the web or shown during the lectures. In this case, 
the degree of **customization** of the layout will be taken into account in the final project assessment.
 **A responsive layout is not required, but strongly suggested.**
 
- For the *client-side* programming, JavaScript is the required language. It is possible to include 
libraries developed by third parties, provided that they have suitable cross-browser portability 
and that they are described in the project documentation. It is, in any case, **not recommended
the abuse of these technologies**, especially when it is possible to replace them
with adequate use of HTML, CSS, etc. Generally speaking, it is **admissible that
scripts play a more important role in the functionalities addressed to a
restricted and predetermined group of users**, for example in *back-end* functionalities
for administrators, but not in the public *front-end* of the site or in a
login procedure. On these pages, the site without scripts may be less "friendly" 
or allow the access to "core" functionalities only.

- For the *server-side* programming, Java *(servlets)* is the **required** language.
Any *DBMS* and *template engine*  (like *Freemarker*) can be employed, if required.
Again, it is possible to rely on external libraries.

- In general, the site must work and have a good *rendering* on the latest versions of Edge, 
Firefox and Chrome, and *possibly* be compatible with older browsers (in this case it should 
at least *degrade well*) and with the latest versions of other browsers, like Opera. Browser
compatibility **must** be explicitly stated in the documentation.  

### Project Development and Documentation

The specifications may not be exhaustive or completely defined. Every feature added or refined, also through an interaction with the stakeholder or the site end users, should be adequately discussed. All the design choices must be discussed and motivated.

The final project, developed following the guidelines given by the present specification, must be a fully functional website, whose contents and features will be assessed during the examination. The specification parts marked as *optional*, if not developed, will not make the project insufficient but, on the other hand, they will not allow your project to reach the highest mark. If you choose to implement an optional feature, the result should not be necessarily perfect or complete: it must only show your commitment to deal with an advanced issue.

The documentation (**in electronic format**) that accompanies the project **must** contain at least the following information:

- Indication of software dependencies (which libraries are required on the client and server side?).

- Indication of the functionalities that have been developed or not developed. Detailed description of any extra or optional functionality added to the project.

- Diagram showing the site structure (e.g. a *navigation diagram*).

- Relational schema of the database (if any).

- Analytical description of the site layout, also indicating its static/dynamic components.

- Description of any advanced technology (language, framework, plugin, library, etc.) used in the project, specifying the reason of its adoption and the actual contribution given to the project development.

- Description of any *possible* cross-browser programming/rendering problem encountered, list of compatible browsers.

- Screenshots of the most important website pages (*optional*).

*The actual contribution of each group member* to the project **must** be declared in the documentation (indicating, for example, the members that mainly worked on server and client side programming, the layout designer, etc.). During the examination, each group member will describe its part of the project.  

### Project Evaluation

To evaluate the project, the following aspects will be considered (in order of importance):
1. Compliance with the specifications.
2. Technical correctness.
3. Organizational clarity and correctness of the contents.
4. Accessibility and standards compliance.
5. Appropriate use of static and dynamic contents. 
6. Design quality.
7. Adequacy of the documentation.

This evaluation will be combined with the result of the project discussion.  

### Additional Information

This specification is available in Web Engineering course repository at the address https://github.com/WebEngineering-Univaq/WE_Project_Specifications. 
Additional information on the specifications can be obtained directly via email by writing to giuseppe.dellapenna@univaq.it.

Please note that projects should be carried out by *small* student groups (three members is the recommended number). 
Exceptions to this rule must be agreed with the teacher.  
</section>

