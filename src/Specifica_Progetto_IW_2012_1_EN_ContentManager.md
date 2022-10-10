---
titolo: ContentManager
numero: 1
vestione: 1.0
lingua: EN
anno: 2012
materia: IW
mainfile: Progetto_Master.rcp
thisfile: specifica
---

-------
{#specifiche}

The *ContentManager* site is a simple web-based system for creating static mini-websites without the need for programming or writing of HTML/CSS.

Each mini-site is identified by its author's username and has a tree structure corresponding to the logical structure of the site navigation, with an HTML page associated to each node. The root node always corresponds to the homepage. For example:

Homepage  
   \> About  
   \> Interests  
   \> Ski  
   \> Photography  
   \> Links  
   \> Contacts  

All the pages of the mini-site are identified by a numeric code, share the same header and footer, and are displayed using the same stylesheet.

Header, footer, and bodies of HTML pages are stored in the site database, whereas stylesheets are saved on the file system. The system has a default set of stylesheets, each associated with a name and a description, which define the appearance of all major HTML elements (headings, paragraphs, tables, lists, etc.).

The homepage of the mini-site for a particular user can be requested with an URL like http://\<web_application_base_URL\>/site?user=\<*username* \>, whereas any other page with identifier *X* on same site should correspond to the URL http://\<web_application_base_URL\>/site?user=\<*username* \>\&page=*X.*

To answer these URLs, the system dynamically composes the final web page and, in particular, inserts in its body the following four parts: the common header of the mini-site, followed by the contents of the requested page, then a navigation menu (which could appear anywhere on the final page), and finally the common footer. The generated page head should also contain a reference to the stylesheet chosen by the user.

The navigation menu is created automatically from the tree structure of the site, and contains at least a link to the parent of the current page (if it is not the homepage) and links to all its child pages. For example, the menu for the *Interests* page in the structure above should contain links to *Homepage* , *Ski* and *Photography*.

The user can also upload images in the web space, following a suitable procedure, and up to a given maximum size (that is, until the total size of the uploaded images is below a certain limit). Each image is associated to a numeric identifier *Y* , in such a way that it can be downloaded (for example, within a page of the mini-site, with an *img* tag) using a URL like http://\<web_application_base_URL\>/image?user=\<*username* \>\&image=*Y.
Tip*: To create a servlet that allows to "download" an image and to figure out how to upload a binary file on the server, see the examples developed during the lectures. Images can be stored in user-specific separate directories or in the same directory, renaming each file so that their names do not conflict. Each numeric identifier must then be mapped on the correct file name on the file system.

-------
{#operazioni}

- Users can register on *ContentManager* by providing their data and a valid email address (the validity check, which can be performed by sending an email with a link to click, is *optional*), and receiving the corresponding login credentials. The system initializes the user web space by creating the homepage (the root of the navigation tree), initially containing a predefined text, and generating a default header/footer for the mini-site (e.g., with the user name, the creation date, etc.).
- Registered users can access their web space, view the site tree structure, edit or delete each page, and create new pages at any level of the tree. When creating a new page, after specifying where it should appear within the tree, the user can choose whether to start from a blank page or from a page template (see below).
- *Optionally* , the user may also have the ability to move a subtree (i.e., a page and all its descendants) in a different position of the navigation tree.
- Registered users can also modify the header and footer of their mini-site.
- Editing of pages and header/footer contents must be performed through a WYSIWYG HTML editor like *ckeditor* (http://ckeditor.com/) or *tinymce* (http://www.tinymce.com/).
- Registered users can view a list of all the images they uploaded in the site, delete some of them or add new ones. The list should clearly show the link (as the one above) to be used to embed or download the image.
- Registered users can view the list of predefined system stylesheets and choose which one to apply to their site.
- Finally, users may make "public" one or more of their pages by marking them as *templates*, so that other users can use them to start new pages of their mini-site, as described above.
- The application homepage should contain, besides the register and login controls, the names of the last created mini-sites, which can be clicked to access the mini-site homepages and then browse them using either the navigation menu or any internal link.  
