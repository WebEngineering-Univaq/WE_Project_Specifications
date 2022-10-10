---
titolo: SimplestNote
numero: 1
vestione: 1.0
lingua: EN
anno: 2013
materia: IW
mainfile: Progetto_Master.rcp
thisfile: specifica
---

-------

{#specifiche}

SimplestNote is a simple online notepad with note-sharing features.  
The site is accessible to registered users only. Each user has a virtual notebook, consisting of an arbitrary number of pages, which we shall call *notes* in the following. Each note has a title and a content (both plain text). The length of the title may be limited, whereas the content length should be unlimited. Notes are also associated with their creation date, last modification date, version number (corresponding to the number of times the note has been updated) and an arbitrary number of tags, defined as words or short sequences of words (e.g., "*news* ", "*work* " or "*private messages* ").  
The system stores all the versions of each note, so as to prevent unwanted changes and provide a note history. It will be possible to share a note with other users of the system, making it appear in their notepads and possibly allowing them to modify it.

-------

{#operazioni}

- Users can register on *SimplestNote* providing their own personal data (name, surname, etc.) and a valid email address (the email verification, which can be performed by sending an email with a link to click to verify the address, is *optional*) and getting their access credentials. The email address will be used as the username and the password will be randomly generated at registration time.

- Once logged in, the user can see his/her list of notes (with title and last modification date). Selecting a note opens the reading/editing view. The interface should also allow the user to create new notes (with an initial default title, e.g., the current date/time) and delete existing ones.

- The reading/editing view of a note enables the user to change the note title, content and tags. *Optionally*, when adding a tag, the system may suggest one of the tags already used by the user in other notes, as well as allow the definition of a new tag.

- When a note is updated (changing its title, content or tags), the system saves its current state (title, content, tags, last modification date) in the note *history*, and then applies the required changes (saving the new state of the note, increasing the version number and updating the last modification date). In this way, the history will be gradually populated with all previous versions of the note.

- The user can access the history of a note, displaying the version number and the date of modification of all of its previous versions. Clicking on an history item displays (*as read-only*) the title, content and tags of the note for that version.

- A note can be shared with other users of the same system by specifying the user's email address. The share can be configured as read-only or read/write. Shared notes are displayed within the user's note list in such a way as to make clear their origin (email of the owner) and access permissions (read or read/write). Notes shared as read-only can be viewed but not modified. On the other hand, the user should be able to make any kind of change on notes shared in read/write mode, just like on his own notes. The owner of a shared note can cancel the share at any time.

- *Optionally* , you can try to implement the connection endpoint for a mobile client of our service: a simple system to export the note data in JSON format. To this aim, the site should expose two special URLs, which we shall denote respectively with *http://server.it/notepad/getList?user=email\&pass=password* and *http://server.it/notepad/getNote?user=email\&pass=password\&note=ID* . When requesting the first URL, the server must return a JSON structure (pay attention to the *content type* !) that represents the list of notes belonging to the user with the specified *email* , authenticated using the given *password* . Obviously, if the authentication fails, the response should be empty. The list must contain, for each note, its ID (of course your system will provide every note with an identifier, e.g., the primary key used to insert it into the database) and its title. On the other hand, when requesting the second URL, the server must return a JSON structure containing the creation date, modification date, version number, title, content and tags of the note whose *ID* is indicated in the URL, belonging to the user with the specified *email* , authenticated using the given *password* . *Note*: in a real application, sending username and password in every service call would be very inefficient and unsafe, but here we use this approach to simplify the implementation.
