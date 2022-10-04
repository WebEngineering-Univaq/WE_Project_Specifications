---
titolo: CollaborativeGenealogy
numero: 2
vestione: 1.0
lingua: EN
anno: 2013
materia: IW
mainfile: Progetto_Master.rcp
thisfile: specifica
---

-------

{#specifiche}

*CollaborativeGenealogy* is a social site to build your own family tree while contributing to the refinement of other users' one.

The site is accessible to registered users only. When registering, a new user must supply (and won't be able to change later) his/her full personal details, including date/place of birth and email address. Users can also provide their contact information (address, phone numbers, etc.) and, *optionally*, write and update a short textual biography and upload a photo for their profile. The "social" aspect of the system lies in the way family trees are built.

-------

{#operazioni}

- Anonymous users (the ones accessing to the site without logging in) can only see a simple presentation page, a login/registration form and a search form. The search is performed on first and last names of registered users, and the results only show the full name of the found users and the number of "relatives" in their family tree . In this way, anonymous users are able to "test" the usefulness of the service, without violating the privacy of registered users, and then register to use all the site functionalities.

- Registered users, on the other hand, can search for other users by specifying different parameters, including first and last name (finding people with your last name is a good starting point to search for a possible relationship!), date and place of birth. The user should be able to combine these parameters to perform refined searches. The search results contain, in this case, name, surname, date and place of birth of each user found.

- To create a family tree, the user can proceed in three ways. *Note* : to simplify the system, we assume that the user can add only direct relatives, i.e., *father, mother, sons* and*brothers/sisters* of people already in his/her family tree. Thus, to add the maternal grandfather, the user must first add his/her mother and then her father.
1. After performing a search and identifying some possible relatives, the user can add them to the family tree.

2. If a relative is not registered in the system, the user can create his/her basic profile (name, email address, date and place of birth) and add him/her to the family tree.

3. Finally, to handle relatives cannot be reached (or are dead), the user can also create a basic profile as specified above, *but
   without an email address* , and add it to the family tree. In this case, the added relationship will always be displayed by the system as "*unverified*".
- In all cases, to actually add an relative to the family tree, the user must specify the tree position to attach the new relative to and the corresponding relationship (*father, mother, son, brother/sister*).

- In cases 1 and 2, i.e., when adding a system-registered relative or manually specifying new one, the possible new family member has to approve the declared relationship. The relationship will not be considered effective and will not be shown in the genealogy of the user until the new relative validates it. Once the relationship is verified, the two users become part of the same "family" and can see all the biographical data of the other, as well as navigate his/her family tree.

- The potential relative is notified by email (*hint:
  you don't need to send a real email, in this prototype it will be enough to show
  the text that you would send...* ) with the information of the "proposer" and the type of relationship proposed, which can be approved or rejected. Registered users (added as in case 1) will be able to log into their account and make this choice. Unregistered users (added as in step 2) will receive in the notification email an invitation to register and approve the relationship .

- The system will eventually allow registered users to "navigate" their family tree, showing first the direct relationships and allowing the user to expand step by step the "relatives of relatives", and so on. This navigation will include the tree directly built by the user as well as the sub-trees built by his/her verified relatives. A *breadcrumb* system, i.e., a navigation path, will allow to derive the family relationship of the currently selected relative. As an example, on the main page of my profile, I click on my father, "Tom". The page then shows the path to the current relative "Me \> Tom (father)", the Tom's biographical data and all his direct relatives (mother, father, sons, brothers/systers). Then, clicking on his father "Dick" displays a page whose path is "Me \> Tom (father) \> Dick (father)", and so on. *Optionally*, you may attempt to automatically derive the overall relationship of the selected relative based on this path: in this case, for example, the page may show "Dick is your paternal grandfather".
