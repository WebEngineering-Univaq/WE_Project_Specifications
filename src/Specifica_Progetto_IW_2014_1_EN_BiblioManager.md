---
titolo: BiblioManager
numero: 1
vestione: 1.0
lingua: EN
anno: 2014
materia: IW
mainfile: Progetto_Master.rcp
thisfile: specifica
---

-------

{#specifiche}

The *BiblioManager* site represents a simple online bibliographical catalogue.

The catalogue contains a number of *publications* , each characterized by a *title* , a list of *authors* , a *publisher* , a set of *metadata* (see below) and, optionally, a textual *description* (publication summary or presentation), an *index* (i.e., the chapter/section titles, numbered and sorted) and a set of online *sources* which can be used to access the publication or parts of it. Each source is characterized by a *type* , a *URI* , a *format* and a *description*. Examples of valid sources could be the following:

- type="image", URI ="http://server.net/cover.jpg", format= "image/jpeg", description="cover"

- type="download", URI="http://server.net/book.pdf", format="application/pdf", description="free electronic version"

- type="purchase", URI="http://www.amazon.it/xyz", format="paper, hardcover", description="buy online"

Finally, publication metadata consist of (at least) the following information: *ISBN* , number of *pages* , *language* , *date* of publication, list of *reprints* (number and date) and *keywords* (zero or more).

-------

{#operazioni}

- There will be two classes of users: *active* and *passive* . Passive users can only view the catalogue, whereas the active ones can also update it. *Anonymous* users can view the site homepage, but a login is required in order to access all the other content.

- Passive users can register on the site using a form, filling it with their personal information, an email address (which will be used as their username) and, of course, the chosen password. Active users can "promote" any registered passive user, making it active. Thus, the system will provide a default pre-registered active user.

- The site homepage lists the latest publications added and/or recently updated. The page also presents a list of the more "collaborative" active users (i.e., the ones who entered more publications): by clicking on their name, users will be able to view the list of publications they added to the catalogue (*optionally* formatted as the search results described in the following paragraphs).

- Users can browse the complete catalogue in a paginated list, showing all the publications with their title, author, publisher and year of publication. The list should be orderable using title and year as the key (the title will be the default-ordering key) and *optionally* using all the other columns. Selecting a publication, the user accesses its complete bibliographic record.

- Obviously, the site must offer also a search system in order to allow users to find their publications of interest using various criteria, without necessarily navigating the complete list described in the previous point. The search criteria to support are ISBN, title, author, publisher, year of publication, keywords, language, presence of sources of type "download" (indicating free publications). The user should be able to specify one or more of the above criteria, which will be AND-combined. The search results list should have the same format and functionalities of the complete catalogue listing described in the previous point. Obviously, any improvement to this search functionality, for example with the addition of further criteria, will increase the value of the project.

- The bibliographic record must show, in the clearest and well-structured way possible, all the information related to the publication. If required, you can also use sub-pages, accessible from the main bibliographic record, to better organize the information. Sources of "image" type, if present in the publication data, must be used to create a image gallery displayed in the bibliographic record or in an appropriate sub-page. In particular, a source of "image" type with description "cover", if available, should be shown at the beginning of the bibliographic record, next to the title.

- There will be also a social section, where (active and passive) users should be able to *recommend* the reading of a publication or enter a *review* . The number of "recommendations" given to a publication is displayed in the bibliographic record together with its most recent review, and the complete (*optionally* paged) list of reviews is available in a suitable sub-page. The reviews, however, will not be immediately visible, but will be subject to moderation, as described later.

- Active users can update the publications. Thus, you should provide appropriate forms through which to enter, edit and delete every detail of the publications. In particular, the "edit" and "delete" functions should be accessible via appropriate links added to the bibliographic records when accessed by an active user. Similarly, the "add" links should be shown to active users at the beginning of the main catalogue listing.

- Active users, when accessing a bibliographic record, should also see how many new reviews (for that publication) are waiting to be approved. These reviews are visible, in their case, along with the approved reviews, but suitably highlighted as "awaiting moderation" and including a link to approve them (i.e., make them visible to all), or delete them permanently.

- To keep track of the changes made to the bibliography by active users, the system must maintain a "history" of each bibliographic record. Each entry of this history contains a timestamp, the username and a description of the modifications. You can decide the detail level of this description: descriptions like "changed the publication", "added the publication", "approved a review of user X", etc. are also acceptable. This publication history, properly formatted, should be visible to all the active users from the corresponding bibliographic record.
