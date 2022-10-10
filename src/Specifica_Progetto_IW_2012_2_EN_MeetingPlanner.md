---
titolo: MeetingPlanner
numero: 2
vestione: 1.0
lingua: EN
anno: 2012
materia: IW
mainfile: Progetto_Master.rcp
thisfile: specifica
---

-------
{#specifiche}

The *MeetingPlanner* site is an easy way to arrange meetings.

The site can be accessed by three types of users: *administrators* , *organizers* and *participants*. The participants, as we shall see, are not registered in the system, but can access specific site pages by invitation only, and for a limited time.

The site database contains information about all the meetings being organized or already arranged. The database also contains a list of available meeting rooms. Each room is associated with its name, location, capacity and equipments, chosen from a predefined list (e.g., projector, air conditioning, microphone, etc.).

Organizers can create meeting proposals by specifying when and where the meeting could take place and inviting a number of participants. Participants will receive an invitation via email and will be able to use the provided link to enter the site and declare their availability. Finally, organizers, given the participants preferences, will define the meeting time and location, and the system will send a notification to all the participants with the final meeting information.

-------
{#operazioni}

- The site homepage should not contain any relevant information: it must only allow the login of registered administrators and organizers. The rest of the site must not be accessible to anonymous users.
- Administrators can register new administrators and organizers (therefore a default, initial administrator must be always defined in the system).
- Administrators can define and edit meeting rooms information, as described above.
- Organizers can create meeting proposals. To this aim, they must specify a description of the meeting and the list of participants, with their full name and email address. They must also define a set of possible dates, time intervals and locations for the meeting, such as "3/4/2014 from 15 to 18 in meeting room 2, or 7/6/2015 from 9.30 to 13.30 in Via Garibaldi 12".
- Organizers may ask the system to check the availability in a certain date/time of a meeting room with specific features. In this case the system, based on its data, indicates which free meeting rooms have the required characteristics (including a capacity compatible with the number of invited participants). Organizers may then choose one of the proposed rooms as the location of the meeting on that date/time. However, organizers are not restricted in their choice by the meeting rooms indicated by the system, but can freely specify any other place or address as the meeting location.
- Meeting proposals can be optionally accompanied by one or more files in text or PDF format, which organizers can upload during the meeting definition.
- When the meeting proposal is complete, organizers can ask the system to send email invitations to all the participants. In this "toy" application it is not required to really send the emails: you may, e.g., simply print the email text on the screen.
- Emails sent to potential participants must contain a description of the meeting, the name of its organizer and a link to click in order to express their preferences and availability. This link is automatically generated and contains enough information (e.g., as parameters in a *query string* ) for the system to identify the meeting and the invited user. *Tip*: instead of directly including information such as the meeting ID or the name of the participant in the link, making it very fragile and easy to tamper, you should put in the link a unique, randomly generated alphanumeric string, which is associated with all the necessary information in site database.
- Users invited to a meeting can access the system via the provided link, and are presented with an overview of all the possible date/time/location options defined by the organizer. Users can then check their preferred options and optionally leave a note. They may also download and read the documents attached to the meeting invitation. Once an user has expressed his preferences, he will not be able to change them, and the link used to access the system will be no longer valid.
- Organizers, at any time, can check which participants answered and how. The system also calculates and displays the date/time/location combinations which are compatible with all (or the majority of) the participants preferences.
- Organizers can finally choose the final date/time/location for the meeting, whose details are recorded in the system database (this is very useful to determine the available meeting rooms, as described above)
- When a meeting is finally arranged, the system sends a confirmation email to all participants who declared their availability for the selected date/time/location, and an email with apologies to all the invited users who won't be able to attend.  
