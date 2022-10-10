---
titolo: BooksOnLine
numero: 1
vestione: 1.0
lingua: EN
anno: 2010
materia: IW
mainfile: Progetto_Master.rcp
thisfile: specifica
---

-------

{#specifiche}

The *BooksOnLine* websiteis a simple web interface for a library.

The website database contains information on the books, the library (registered) users and the book loans. In particular, for every book we have the ISBN, title, language, publisher, year of publication, the names of all authors and, *optionally*, a review or a short description (like the one that often appears on the back cover of the book). A set of *tags* , i.e. words or short phrases (e.g., "computer", "programming", "C++ language", etc.), is also associated to each volume and can be, e.g., extracted from the book title and/or entered by librarians. Each book has a maximum loan duration (default: one month) and may be present in the library in multiple copies. Finally, some books are marked "free to read" and therefore accessible directly online in the form of downloadable text or PDF files. For each book, the site generates a description page containing all the above information, suitably organized.

The site is accessed by of three types of users: *librarians, registered users* and *anonymous* *users* . Appropriate login procedures must be provided. **We assume that only librarians can add new users (including
other librarians) to the system** (which is initialized with a single default "root librarian"), e.g., it may be possible to register a new user when he/she deposits his/her credentials to the library. Each registered user is associated with a profile containing some basic personal data, an email address and a phone number.

-------

{#operazioni}

- Users must be able to search for books based on: (1) their title or part of it, (2) the associated *tags* , (3) one or more of the authors, (4) the ISBN. The completeness and versatility of the search function, which is an essential element of this kind of site, are left to the initiative of the students. The search results should be presented as a list showing title, author, publisher and year of each book found. Clicking on a listed book opens the corresponding description page.

- On the description page of a book, users must be able to click on an author's name to automatically start a search for all the books written by him/her (i.e., his/her complete bibliography).

- On the description page of a book, and in general wherever *tags* appear, users must be able to click on one of them to automatically start a search for all the associated books.

- On the description page of a book, users must read the number of copies in the library and the number of those copies which are currently free (not borrowed). *Optionally,* if all the copies are on loan, the site may indicate the expected return date of the first copy, calculated from the date of the loan and the maximum loan duration.

- Librarians, after having looked up a particular book (using the search functions listed above) must be able to register a loan on behalf of a user known to the system.

- Registered users can view the list of books that they have borrowed and the corresponding return date. The books whose return date has expired should be appropriately marked. Users may also view the entire list of books already borrowed and returned (*loan
  history*).

- Librarians must be able, from the description page of a book, to view all the related loans, past or present. In addition, librarians can view a list of all the books on loan, where those whose return date is expired are suitably highlighted.

- The site homepage shows some general information, such as the most borrowed books and the books recently added to the library. For registered users, the homepage also reminds the books to be returned shortly.

- The site must be provided with adequate *backoffice,* accessible only to librarians, which allows to enter and edit all the data associated with the books.  
