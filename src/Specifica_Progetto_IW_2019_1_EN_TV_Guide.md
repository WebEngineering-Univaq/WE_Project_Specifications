---
titolo: TV Guide
numero: 1
versione: 1.0
lingua: EN
anno: 2019
materia: IW
mainfile: Progetto_Master.rcp
thisfile: specifica
---

-------

{#specifiche}

The "TV Guide" site is an online guide to television shows. The site will show the schedule of a certain number of television channels, listing the shows available day by day. In particular, the site should provide information about the shows up to seven days in the future (there may be fewer, based on the data provided by the broadcasters). Information about the past shows should be also available, but in this case, you should set a time limit and delete all the older entries from the database, to avoid unnecessary load.

For each television show, the site will store the start and end time, the name, a brief description and the type (the types are taken from a predefined list). If the show represents an episode of a series, it will also have associated the season number and the episode number within the season. There could be also a link to an in-depth information page (not necessarily internal to the site itself: it may be a Wikipedia page, for example) as well as an image. The latter may be internal to the site or connected though an external link.

Users should be able to read the schedule of each channel (shows of a certain day) and perform searches by title and/or type, possibly restricted to a specific channel. The user may also specify the time interval of these searches.

Tip: consider that the same shows or the same episodes of the same series may appear several times in the schedules. In designing the data model, and therefore the operations that use it, try to optimize the structure based on this consideration. For example, if a show is broadcast on two different days, the database should not contain all its basic information twice (title, description, link ...): only the airing data (channel, time, etc.), which are the only ones that change, should exist in two different versions.

Any user will be able to register on the site by entering an email and password. Registered users, once logged in, can specify how to receive a daily email with the latest updates to the schedule. The email may contain today's shows for selected channels, possibly only for certain time slots (morning / afternoon / evening / night) and/or the results of a saved search (of the type described above), to be notified, for example, when a show he wants to follow appears on the schedule. *Note: the
application created for the project will not necessarily have to send these
emails, but you will still have to write all the code to create the email
content and then transfer it, in the demo phase, to an external file.*

Please note: since this site will be often accessed from mobile devices, pay particular attention to the *responsiveness* of its layout.

-------

{#operazioni}

- The homepage has to show the list of available channels, as well as the shows currently broadcast on each of them.

- From the homepage, it should be possible to access a second view, similar to the homepage itself, which however lists, for each channel, all the shows in the daily schedule *relative to a specific time
  slot (morning / afternoon / evening / night).*

- In any view, by clicking on a channel, it should be possible to view its complete schedule for the current day. In this view, the classic "TV guide" view, the shows should appear (sorted!) together with their start time, end time, type and title. If available, the related image (appropriately scaled) may be shown alongside a show.

- In any view, by clicking on a show the user should access the corresponding details page: larger image (if available), description, in-depth link.

- If the show is part of a series, in its detail page it should be possible to view the broadcasting date/time and channel of all the related episodes in the last month.

- The search functionality, accessible on every page of the site, should allow to specify one or more of the following criteria, combined in AND: (part of) title, type, maximum and minimum start time, channels, time interval (dates). The search results will be then shown in a "TV guide"-like view, in this case sorted by date, start time and channel.

- A user can register by providing a valid email and a password of his choice. The email must be confirmed by clicking on a link sent to the same address. *Note: write the code to generate the validation
  link and manage its click, but during the demo, you can simply print the link
  somewhere and enter it in the browser, without having to actually send the email*.

- In his profile, the user can enable the daily schedule email, described above, possibly specifying a list of channels and one or more time slots of interest.

- Furthermore, the authenticated user, once a search has been performed as seen above, should be able to save the criteria (by clicking on an appropriate button), so that they can be used to generate further information to be included in his daily email, as already illustrated.

- Obviously, the registered user should be also able to stop the sending of the search results and/or of the daily schedule.

- The site administrator, who we will suppose unique and pre-registered in the system, should be able to insert, modify or delete the channels and the relative schedules, that is, the shows and the information about their broadcasting.  
