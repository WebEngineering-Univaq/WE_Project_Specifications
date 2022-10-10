---
titolo: Collectors Site
versione: 2.0
numero: 2
lingua: EN
anno: 2021
materia: IW
mainfile: Progetto_Master.rcp
thisfile: specifica
---

-------

{#specifiche}

The *Collectors Site* website is a meeting point for record collectors (although the same type of site could fit almost any type of collection, we will use the records as a case study so we can add more details to the specification).

Once registered, the users of this site, or *collectors* , will be able to enter all the data relating to their record *collections* (each collector can create multiple collections, each with a distinct name). For each *disc* in a collection, the collector should provide the authors, the title, the release year, the publisher, the genre (chosen from a predefined list of musical genres), the status (of conservation of the object, chosen from a predefined list), the format (vinyl, CD, digital, ...), the *barcode* number, if available (the barcodes guarantee the unique identification of the element), and then obviously the track list, each with title, duration, and information on composer and performer (singer, musician), if different from those of the entire disc. Finally, each disc can be associated with one or more images (cover, back, booklet pages, etc.). In short, try to be as realistic as possible.

For each disc, the collector will also be able to indicate the possible number of *duplicates* owned (maybe since they are expected to be resold).

Collectors can decide to *share* their collection with specific users or in a public way. Each collector will therefore have a panel with a list of the collections shared specifically with him, which he can freely view.

The site should have an advanced search function (by artist, title, collector, etc.), also available to anonymous users, which will consider all public collections and, for a logged in user, also the personal collections and all collections shared with him *(tip: you
can perform the same search on every collection accessible by the user and then
merge the results)*.

It is important that, in the system, the same discs, even if belonging to different collections and collectors, should be linked in some way, so that they can be grouped together if necessary, e.g., to answer questions such as "who owns this disc?". To this aim, always try, when a new disc is added, to "suggest" to the collector to import (as initial values) the data of the same disk, if already present in the system in other collections. By doing so, you will internally create a connection between the "same" discs, even if the collector will then be free to edit the data of his copy. Furthermore, it would be helpful to use auto-completion wherever possible, using the data of the same field already present in the database as a source: for example, by entering the name of a singer, the system should suggest the completions using the names of the singers already known. This trick not only has the purpose of speeding up the input, but it is also useful to avoid the same object (in this case, a singer) to be entered several times with small variations (for example spaces, apostrophes , etc.).

-------

{#operazioni}

- Collectors register in the system by providing a nickname and an email address. It is not required, even if possible, to enter the real name and surname.

- Each collector has a public profile, also visible to anonymous users, containing the personal data entered and the list of his public collections.

- Once authenticated, collectors can manage their collections, and in particular create or delete a collection and insert/delete/modify the individual discs contained in a collection, as described above.

- The site must provide (at least) two views on the collections: list of the entire collection and detail of a disc contained in a collection. Either way, you'll need to decide what information to show and how to organize it. Obviously, the view on the collection and its contents will be accessible to the owner and to all those who have access rights to the collection itself (for public or shared collections).

- An important element of the site will be the search functionality. It must be possible to search for author/composer/performer names, titles and collector nicknames. The results may be of different types based on the elements found: single discs, entire collections, collector profiles. The user can include in the search results only his own collections (if logged in) or also the shared/public ones.

- A collector has a panel with the list of collections shared with him, from which it is possible to directly access the view of the related collection.

- A collector can decide whether to make each of his collections private (default), public, or share it with other specific users. When sharing a collection with a user, he will receive an email notification *(tip: you can simulate such an action, you don't really need to
  send an email).*

- The site must provide statistics, public or personal (per collector). You are free to define the most interesting ones. Suggestions can be the number of discs by author, by genre, etc. (in a collection, for the collector, or in the whole system, as a global statistic)  
