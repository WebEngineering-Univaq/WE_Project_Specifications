---
titolo: AuctionsOnLine
numero: 2
vestione: 1.0
lingua: EN
anno: 2010
materia: IW
mainfile: Progetto_Master.rcp
thisfile: specifica
---

-------

{#specifiche}

## Site Specifications

The *AuctionsOnLine* site represents a simple auction system, where sellers offer some objects and buyers make bids to buy them.

Each object has a dedicated page on the site, which shows basic information like name, description and conditions (new, used, damaged, etc..), together with optional elements such as a set of links and a photo. A set of *tags* , i.e., words or short phrases, may be associated with the objects to classify them, in order to facilitate the searches. Finally, the object pages show the corresponding auction status: beginning and end of the auction period, delivery method (mail, courier, etc..) and payment modality (cash, credit card, wire transfer, etc.), base price and minimum raise.

The site is accessed by two types of users: *anonymous* users and *registered* users. Appropriate registration and login functionalities must be provided. Anonymous users can only search the site, while registered users can act both as sellers and as buyers.

-------

{#operazioni}

- All the users must be able to search for objects based on: (1) words or phrases in their name or description, (2) the associated *tags* , (3) the seller's name, (4) the (base) price. The completeness and versatility of the search function, which is an essential element of this kind of site, are left to the initiative of the students. The search results should be presented as a list showing name, seller's name, auction start and end date of each object found. Clicking on an object opens the corresponding description page.

- On the description page of an object, users must be able to click the seller's name to display his/her profile (personal details, email address, etc.) and the list of all the items he/she has put for auction.

- On the description page of an object, and in general wherever *tags* appear, users must be able to click on one of them to automatically start a search for all the associated objects.

- Registered users can add new objects to be put on auction, entering all the required information (as described above), edit their own objects, but only up to the start date of the auction, and remove (delete) their objects, even during the auction.

- Registered users can view the list of their objects and, for the ones currently auctioned, read how many offers there have been so far, the remaining time until the auction closes, and the date, user and amount of the last bid.

- Registered users can join an arbitrary number of active auctions, bidding more than or equal to the base bid and increasing the preceding offer by an amount at least corresponding to the minimum raise.

- Registered users can view the list of objects they make a bid for, together with the time remaining before the end of the corresponding auction. If there was an higher bid from another user, the system will display its amount and give the user the opportunity to make a new bid.

- When the auction ends, the corresponding object is no longer visible in the searches. The higher bidder will receive a notification (on the homepage after the login, and *optionally* via email) of his/her victory, with attached payment information. Similarly, the seller will be notified of the purchase and given the buyer information. If an object did not receive any offer, however, the seller can update its information and possibly set the dates of a new auction.

- The homepage of the site shows some general information, such as the latest objects put for auction, the ones with higher raises, etc.  
