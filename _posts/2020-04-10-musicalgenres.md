---
layout: post
title: "Musical Genres: Use, Questions, and Challenges"
---


Recently we looked at genre and how it is used and applied to Carnegie Hall's performance history data. With data visualizations in mind, Rob Hudson (Manager, Archives) created a [genre chart](/experiments/chdl-0006.md) to show non-classical music genre labels and percentage counts, relative to the number of performance history events that have a genre assigned to them. 

With this chart and explanation, we hope to be transparent about the angle from which we are approaching genres in the Carnegie Hall Archives and the way we will approach future genre classification. While we’re looking at our current data critically, we’re also deciding how to improve our current classification process and how to move the genre conversation forward both from within and outside of our organization.

## Genre and the Carnegie Hall Archives

The decision to add genre to our performance history database was born out of utility. People would ask questions such as “When was the first rock concert at Carnegie Hall?” and, in order to provide answers, we started tagging genre keywords on events. This is a good time to remind folks that we are not musicologists and we do not have collaborative catalog records or a standardized genre terminology to describe this stuff. Most available genre vocabularies are tailored to describing bibliographic materials and not performance records, so we either adapted from these sources or created our own terms. With limited time and resources to apply to this classification project, we released genre as part of our dataset “as is” using The Music Ontology’s “genre” property. We have not classified the entirety of Carnegie Hall’s events: there are gaps in genre coverage, very little detailed “subgenre” coverage, and no classical music genres other than opera. We also do not classify individual artists with genre terminology, so genre is limited to the event record level.

We understand that none of this is perfect, but we do want to share some minor success stories (and hope to have many more!). Generally, our genre categorizations have answered many internal and external research requests and more.

Our genres – jazz in particular – aided in the development of Carnegie Hall’s previous <a href="http://honor.carnegiehall.org/honor/" target="_blank">Timeline of African American History</a> (2009) and its <a href="https://securegrants.neh.gov/publicquery/main.aspx?f=1&gn=MT-263969-19" target="_blank">planned reboot</a>, which both serve to clarify the differences and similarities of multiple African American musical genres and subgenres. The original timeline was created based on the work of subject matter academics, and the reboot plans to include expanded and updated professional research on African American culture.

In terms of the classical opera genre, we participated in a project with an external academic researcher to sort through opera performances at Carnegie Hall, most of which were not complete stage productions but rather semi-staged and concert productions, or artists performing arias or scenes. This project allowed us to take a closer look at how we use opera as a genre, and how we should use and engage with it more intentionally it in the future.

## Challenges

We face several genre challenges related to the limits of our database and to the inconsistencies of the overall genre discussion.

### In Archives

To start with our own limitations, we do not currently have the resources to classify every single one of the 50,000+ concerts that have taken place at Carnegie Hall. We do not have the staff to do this, and our performance history database, which was designed as a concert planning tool for symphony orchestras, is not designed to store data about genres. Typically, symphony orchestras don't often present the wide variety of events Carnegie Hall does; many orchestras and presenting organizations approach genre from a marketing or operations standpoint. It's not that we can't include genre terms in our internal performance history database (we do, of course), but we're co-opting an unrelated data table to do this. In our case, it has been more a question of resources (too many concerts to tag) than an issue with the database. Because of this, we may tackle smaller genre projects at different times, and some records are cleaner (more complete) than others. This points to how the tools we have at our disposal impact the practices we develop and maintain.

Beyond staff and database limitations, we face the challenge of describing our extremely wide range of event types, which often mix performers representative of many genres on a single event. For those records that do have genre keywords, often more than one genre keyword is needed to describe an event, which may skew numbers in our genre chart. For example, the annual <a href="https://www.carnegiehall.org/About/History/Performance-History-Search?q=Tibet%20House%20U.S.%20Benefit%20Concert&dex=prod_PHS" target="_blank">Tibet House Benefit</a> or events produced by <a href="https://www.carnegiehall.org/About/History/Performance-History-Search?q=%22Michael%20Dorf%22&dex=prod_PHS" target="_blank">Michael Dorf</a>
 include various performers whose music ranges from rock to soul to hip hop, requiring multiple genre keywords to characterize the event. We also recognize that the genre vocabularies are ever-changing, and overly generic or outdated terms like “world music,” which we previously used to describe many events, are no longer relevant or appropriate. The granularity of genre classification reflects the changing needs and requirements of our data and will continue to prove challenging with future event classification.

### External Challenges

In addition to our own obstacles, the topic of genre in general provokes strong opinions, especially within open data communities such as Wikipedia and Wikidata. There is not a lot of agreement on standardized vocabularies, and there is a huge need for genre to become more interoperable in the data world. Many use genre and subgenre as platforms for arguing over-categorization, as many artists, instruments, and events do not cleanly fit into one mold over another. The lack of organized discussion and output around musical genres inhibits a lot of the work that we do to classify our events and share relevant data. Examples of these discussions are in WikiProjects like <a href="https://en.wikipedia.org/wiki/Category:WikiProject_Music_genres" target="_blank">Music genre</a>, which itself is divided into 24 sub-categories referencing genres and sub-genres.

## Questions and How to Proceed

Clearly there’s a lot of work to be done with genres in the Carnegie Hall Archives and throughout the cultural heritage community. A big challenge for us is **how can we capture musical genres in our dataset while making the argument for more exploration to expand our understanding of genre?**

To start tackling this question, we must think about genre classification as a service, and determine the main purposes, audiences, and users. For example, how could capturing musical genre in our performance history data be useful at Carnegie Hall to departments besides Archives? We must also re-examine and further develop our own understanding of musical genres. Could we use genres to exemplify artists, and by extension the events in which they participate? Do we focus on genre categories, or focus our energy on building up our program information so that the works represent themselves, regardless of genre? And what do we do about genre blending, or genres that overlap, interweave, and evolve over time? What are the possible downstream uses and impacts of the Archives retroactively applying these genre classifications and associations to artists, works, and events?

Once we have a better understanding of why we want more genre classification and how to represent genre more properly in our dataset, we must think about resources: who will implement this work, and how will it be vetted? Can existing vocabularies and discussions inform our work, and how do we open a larger discussion with like-minded institutions? Do we have the staff and institutional backing to create an interoperable vocabulary, to share and compare with others?

We’re still wrapping our heads around our own internal discussion of genre and ask for feedback and/or responses to any of these questions and talking points. If you have done work similar to this or have also been tossing around these questions in your mind, [contact us](/contact.md) or tweet using <a href="https://twitter.com/search/?q=%23CHDataLab" target="_blank">#CHDataLab</a> – we look forward to hearing from you!
