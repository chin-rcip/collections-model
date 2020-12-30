---
layout: page
title: Appendix F - Discussions 
permalink: /target-model/current/appendix-f-discussions
sidebar: tm
---
<!-- [Back to the Table of Contents](/collections-model/target-model/current/information#table-of-contents)
 -->
## On This Page

* [Discussion: The Differences Between `E39 Actor`, `E21 Person` and `E74 Group`](#discussion-the-differences-between-e39-actor-e21-person-and-e74-group)
* [Discussion: Semantic Differences Between Contents, Labels, Notes and Comments, and Descriptive Texts](#discussion-semantic-differences-between-contents-labels-notes-and-comments-and-descriptive-texts)
* [Discussion: Challenges When Representing Indigenous Realities](#discussion-challenges-when-representing-indigenous-realities)
* [Discussion: Identity Definitions](#discussion-identity-definitions)
    * [Pertaining to Culture](#pertaining-to-culture)
    * [Pertaining to Community](#pertaining-to-community)
* [Discussion: Identity Patterns](#discussion-identity-patterns)
* [Discussion: Nationality, Nationhood and Community With `E74 Group`](#discussion-nationality-nationhood-and-community-with-e74-group)
* [Discussion: Birth/Death of People and Formation/Dissolution of Groups](#discussion-birthdeath-of-people-and-formationdissolution-of-groups)
* [Discussion: Biography](#discussion-biography)


## Discussion: The Differences Between `E39 Actor`, `E21 Person` and `E74 Group`

| 💬 | *This discussion pertains to the aforementioned [section](/collections-model/target-model/current/general-concepts#the-differences-between-e39-actor-e21-person-and-e74-group)*. |
| --- | --- |
| | Heather Dunn (18:14 22 Jul): if we know that some datasets have only e21 person (or if there are few E74 groups that are easily identified) we can still use those subclasses, right? Thinking of the AIC dataset - I think we could pretty easily identify the groups ("General Idea" and a couple of others) |
| | Philippe Michon (10:58 24 Jul): Of course, our process should always allows us to use the subclasses. That said, in our current pipeline (Stephen correct me if I'm wrong) we will have an XML/JSON file for managing e21 (persons) and another one for the e74 (groups). So the first step of the first script must be to segregate the Persons from the groups. <br/><br/>Heather, the reason why we think it's a good idea to have two different files is that there are quite a lot of differences between the person modeling and the group modeling.<br/><br/>Stephen and +george.bruseker@gmail.com, any comments on that? |
| | Stephen Hart (20:20 24 Jul): Indeed, it is essential, for mapping reason, to manage differently groups and persons. Nonetheless, it would also be possible to have an "Actor" file for the cases where we either don't know or not sure if it's a person or a group. This last solution should really be the last resort, as once it has been mapped as an Actor, it would be resourceful to change it to a person or group. |
| | George Bruseker (02:42 25 Jul): If you have a marker in the source dataset that allows you to distinguish E21 from E74 from E39 then you can either split the data (as it seems you suggest above) and do transforms separately OR, as if using 3M, can also just bake in 'if' statements, to determine how the mapping works for the different cases, loading all data in from one source file. |
| | Philippe Michon (07:30 25 Jul): I think it something painful to do with Karma Tool unless we didn't find the correct feature. Happy to hear that 3M can handle this! |
| | Stephen Hart (11:58 25 Jul): Following the discussion with George Bruseker on the 25.07: If there is a field distinguishing the E21 Person from the E74 Group, then it's easy to have a script or use an "if" command in 3M.<br/><br/>If it's not distinguished in the museum data set, then we could try to reconcile with other datasets (ULAN, etc.) for well known artist, and then manually differentiate the rest.<br/><br/>E39 should be use in the last resort. But it is still possible to do a query to modify and update from a E39 actor to an E21 Person or E74 Group. |

    
## Discussion: Semantic Differences Between Contents, Labels, Notes and Comments, and Descriptive Texts

| 💬 | *This discussion pertains to the aforementioned [section](/collections-model/target-model/current/general-concepts#semantic-differences-between-contents-labels-notes-and-comments-and-descriptive-texts)*. |
| --- | --- |
| | Philippe Michon (14:58 15 Jul): I wonder if we should create new patterns rather than adding comments. Perhaps, we should let the opportunity to use rdfs:comment or crm:p3_hasNote and look at the values there to enhance our model. |
| | George Bruseker (07:11 22 Jul): It is an interesting case of where you actually really do want to 'comment'. Comment is the edge case when you really can't express something the model because of its complexity and subtlety. It seems that this shouldn't be cut off entirely, just used with "extreme caution". For example, in this case, another potential would be to model using P130 shows features of. Sometimes, however, if something is really extraneous to the model but not to understanding, p3/comment has a validity. |
| | Philippe Michon (08:21 22 Jul): Stephen, I think it's important to add this to the text and keep the thread open for more discussions. |


## Discussion: Challenges When Representing Indigenous Realities

| 💬 | *This discussion pertains to the aforementioned [section](/collections-model/target-model/current/general-concepts#challenges-when-representing-indigenous-realities)*. |
| --- | --- |
| | Philippe Michon (08:10 16 Jul): Throughout the model, do we identify clearly which parts of the model and especially which vocabularies are concerned? I think it's important to point out where the vocabularies need to align with Indigenous realities. |
| | George Bruseker (17:50 16 Jul): Who will mark/say this? Would there eventually be the possibility to have a dialogue/dialogues over this with different communities in relation to real use cases? <br/><br/>Vocabularies are arguably relatively 'easy' in a semantic perspective, since the same object can be classified as having a different meaning by different communities and these classifications need not be commensurable. There can simply be parallel, unreconciled vocabularies. Where this perspective breaks down, however, is if there is an ontological mismatch of commitments. If one group relates to the object a mere object and another relates to it as something endowed with agency, then we have a more complex level of disagreement. Are there already obvious examples? |
| | Stephen Hart (10:26 17 Jul): We are still looking for some use cases. At the moment, we have indigenous data coming from western museums that do not fully answer indigenous needs, and none from indigenous communities. We are in discussion with members of those communities to identify relevant challenges. So far, it mostly appears to be a vocabulary issue. The display of data will also be a challenge:<br/><br/>some appellations are disrespectful (for example eskimo, savage, indians, etc.); <br/><br/>some data should not be displayed in accordance with indigenous practices (belonging to a clan is a private information that should only be managed by said clan). <br/><br/>When it comes to the ontological mismatch, we do not have data yet, but it is something that could happen. |
| | George Bruseker (07:33 22 Jul): Sounds like you are on a good path |
| | Philippe Michon (09:47 22 Jul): I think Stephen did a good summary of where we are. My first comment was there to remember us that we should already identify the fields where we need to reflect Indigenous realities. We are not at the stage of selecting the right vocabularies though. | 


## Discussion: Identity Definitions

### Pertaining to Culture: 

| 💬 | *This discussion pertains to the aforementioned [section](/collections-model/target-model/current/identification#definitions)*. |
| --- | --- |
| | Philippe Michon (13:41 16 Jul): Should we remove "Indigenous" as anyone can be part of a community? |
| | Stephen Hart (09:36 22 Jul): In my opinion, there is a huge difference between an Indigenous community, which seems part of there cultural way of dividing populations, and our western way of "community". That is why I have included the "culture" field, to represent other belonging feeling that is not the nationality. |
| | Philippe Michon (11:58 22 Jul): There is no belonging feeling to a community in the western vision? Everything is covered by "Culture"? |
| | Stephen Hart (21:09 24 Jul): It is just that it is something very precise in Indigenous culture that has no equivalent in Western cultures. I would not like to put together, in the same field, an Indigenous community like the Abenaki, and the Montreal community. For me it's 2 different things completely different, that should stay separated |
| | Philippe Michon (09:44 25 Jul): We might need more data to understand exactly the needs here. I'll still argue that we should avoid, as much as possible, to have specific Indigenous fields in order to ease cross-search. |
| | Karine Léonard Brouillet (11:07 12 Aug): I am not sure why the community has to be Indigenous. I think as long as Indigenous vocabularies are made available to document an artefact appropriately the field itself does not have to be. For example, a religious artist that belongs to a religious community might want to be affiliated with it. |

### Pertaining to Community: 

| 💬 | *This discussion pertains to the aforementioned [section](/collections-model/target-model/current/identification#definitions)*. |
| --- | --- |
| | Philippe Michon (13:40 16 Jul): Should we create one field with a clear scope and specific vocabularies? |
| | George Bruseker (07:46 22 Jul): seems like it would help with equivocation issues. |
| | Philippe Michon (11:54 22 Jul): Stephen and Karine, what do you think? No matter what, I would keep this thread open for discussion. |
| | Stephen Hart (21:14 24 Jul): As I did understood, the Indigenous Cultural Affiliation (term that comes from Stacy vocabulary, but we could also use the term Nation), for example being an Inuit or an Algonquin, is felt as a nationhood belonging, like Canadian or French (and some indigenous rejects the Canadian citizenship). But, for political reasons, it is better not to put nationality and cultural affiliation in the same field. It is also different from a Culture, as you could be Inuit, but adopted in a Western family and of Montreal or Canadian Culture, but still an Inuit. |
| | George Bruseker (03:12 25 Jul): Reading the continuation of your conversation, I see the problems that arise. The distinction of 'culture' in the sense of general background set of practices and beliefs etc (where one could belong to many cultures in principle) does then also seem distinct to me from the question of a culture that is considered as the foundation of a nationality in the sense of a political feeling/claim. <br/><br/>Maybe we have to look for a better definition of nationality that would be broader than country/state and allow for both under one umbrella without thereby being politically too volatile? |
| | Philippe Michon (09:37 25 Jul): I will argue that the best approach here would be to identify the vocabulary for each field. If it's easy to draw the line then the field is manageable and this will ease the scope note writing. |
| | Karine Léonard Brouillet (09:15 12 Aug): I am sorry I just saw this thread was partly addressed to me! I feel one of the important things here would be to properly name these fields so that they are representative of their intended use: I think Culture could maybe be Cultural Affiliation since it would be weird to have French nationality paired with Canadian Culture. Indigenous Cultural Affiliation might be Indigenous Nationhood since this is what is meant and what we would be looking for would be a Nationhood vocabulary in the end (as opposed to a cultural one that might be used for communities more broadly). Indigenous Community could stay the same. |
| | George Bruseker (7:16 4 sept): Mapping the historical territorial affiliation does not seem to semantically equate with 'community'. Nouvelle France could be an E53 which is the max extent of the E74 Group that was Nouvelle France qua legal entity and possibly also E3 Period to indicate the temporal spatial extents of the E74's claim. There is a long scope note discussion of this in E4 |


## Discussion: Identity Patterns

| 💬 | *This discussion pertains to the aforementioned [section](/collections-model/target-model/current/identification#identity-patterns)*. |
| --- | --- |
| | Philippe Michon (13:48 16 Jul): Add: “Remember that e55 is considered as something unchangeable and always true.” |
| | George Bruseker (18:10 16 Jul): Adding a type to something doesn’t mean that you are asserting that this is its natural kind. It is just that you don't have a way to say when it started and when it stopped. This is a problem if you want to trace changes in people's gender or sexuality over time. Do you have that data though? |
| | Stephen Hart (10:40 17 Jul): For the moment we do not have that data, that's why we've adopted the e55 pattern. However, museums do not often record those gender changes, as there system is not flexible enough, which could perhaps lead to gender identification problems in the future if we do not have a more flexible model (and it is a specifically sensitive topic) |
| | Philippe Michon (12:00 22 Jul): I cannot edit my sentence without removing these comments and it might be good to keep them. Stephen, I let you make the changes. :) |


## Discussion: Nationality, Nationhood and Community With `E74 Group`

| 💬 | *This discussion pertains to the aforementioned [section](/collections-model/target-model/current/identification#nationality-nationhood-and-community-with-e74-group)*. |
| --- | --- |
| | George Bruseker (18:08 16 Jul): They don’t have to. A group at any moment is composed of some people and it’s those people in that relevant time that can act collectively. |
| | Stephen Hart (09:48 17 Jul): But what about former generations? Someone's death does not mean he loses his nationality (or gender), he is still a member of that group, but unable to act. That's why in my opinion the group pattern is not suitable. |
| | George Bruseker (07:52 22 Jul): This is a nice one Stephen! Worthy of a chat. It does get to the heart of the dynamics of the group. If one modelled the nationality as a group and you used p107 has current or former member then you are always correct to assert this of an E21 person if they actually were a member. By being born in Canada, for example I joined the Canadian Nationals group,, which itself came to be in 1867(?). IMy join date can be specified as the same date as my birth (because of Canadian law). When I die, I will actually leave the group, because I can't contribute anymore as an agent. That being said, I will have been and so p107 will still be valid. So I think the modeling works, although I see the complication you raise as quite valid. Do you find the above convincing? |
| | Philippe Michon (16:51 24 Jul): +george.bruseker@gmail.com Both paths will bring us to the same kind of query. The main goal here is to be able to identify all the Canadians. I still think the scope note is not enough inclusive. Is it true that all males act collectively? I'm not sure.<br/><br/>That said, I understand that it's always more powerful to use an event and if we want to date it's a must but I don't think we will have this kind of data.<br/><br/>If we decide to use the e74 pattern for these topics, should we use p107 and the joining and leaving events or only one option? I'm not sure yet that I understand how the shortcuts are working. |
| | George Bruseker (03:19 25 Jul): All males together don't constitute a CRM E74 Group because they share an attribute but they don't have the ability to act collectively. Canadians, arguably do constitute an E74 Group because they share attributes (respect for the law, general adherence to 'peace order and good government') and via their parliament can act collectively (only the live ones). So if you encode with p107 to join someone to the group of Canadians then it will only allow a search to provide you with every Canadian that ever was. If you want to know which Canadians were alive and actively members of their group (by being alive and respecting the law etc) then you would also have to encode the join path and end path. Probably this implicit information most of the time. It could be a project to do some analysis on the data and add properties of joining and leaving based on things you know about E21 persons in the dataset. Anyone born in Canada after this time MUST be a Canadian, you might reason, because of the law, so we can add 'joined' Canadian group clause based on birth and ended based on death (the latter being a bigger assumption since perhaps they abandoned their nationality beforehand by taking up another citizenship or so). |
| | Philippe Michon (09:48 25 Jul): +george.bruseker@gmail.com So according to you being a male will be a type? and being Canadian will be a "membership" to a group. But someone could argue that being transgender could also bring the "members" to this group to act collectively no?|
| | George Bruseker (10:01 25 Jul): Basically yes. Identifying as male or transgender does put someone in a set of people who share that identification, but not likely so close a bond that there could be collective action. It could be the case that because of having a certain identity someone would join some group, the community organisation for x which can act collectively, but usually this kind of identification is not broad enough and socially strong enough to allow us to believe in total collective action. It is like the dream of the workers of the world uniting. Presently there is no collective function that allows people to claim justice. Maybe there could be... but it's more likely someone just belongs to a local union because of shared qualities with some other local people. |
| | Stephen Hart (12:19 25 Jul): Following the discussion with George Bruseker on the 25.07:<br/><br/>E74 works well for Nationality, communities, etc. It is more a question of being convenient rather than philosophically right. Genders will still be rendered with E55 Type. For the identification event, that is for another time |
| | Stephen Hart (16:31 1 Aug): +philippe.michon@canada.ca On valide donc l'utilisation de groupes pour la nationalité, la communautés, etc.? Qu'en est-il pour le genre? |
| | Philippe Michon (07:27 6 Aug): Agree with the e74 for nationalities and communities. For social gender, I would keep it as a type for the moment with a note that we could create our own e7 subclass for it. |
| | Stephen Hart (09:49 6 Aug): Perfect |


## Discussion: Birth/Death of People and Formation/Dissolution of Groups

| 💬 | *This discussion pertains to the aforementioned [section](/collections-model/target-model/current/life-events#birthdeath-of-people-and-formationdissolution-of-groups)*. |
| --- | --- |
| | George Bruseker (09:48 22 Jul): yes crm only has properties for the brute physical facts right now. But CRMsoc will try to expand expressivity range. CHIN probably has great examples and would be welcome to participate.|
| | George Bruseker (09:50 22 Jul): The mother relationship is biological so it is properly modelled relative to the birth (your mom must have been there). The father and other relationships are more social (dad doesn't need to be there at the birth and until recently it was quite difficult to know who the father was |


## Discussion: Biography

| 💬 | *This discussion pertains to the aforementioned [section](/collections-model/target-model/current/descriptive-information#biography)*. |
| --- | --- |
| | George Bruseker (08:05 4 Sept.): I am not sure about this pattern. If you have a chunk of text from a biography cut and paste into a field in a db, then you have an E73 which p190 has symbolic content (the stuff you pasted in the database) and the relationship to the source, ie original document is p106 or p148 part of. The original document is also an E73 or E33 as you like.|
| | Philippe Michon (09:17 4 Sept.): I agree, +stephen.h.hart@gmail.com we will have to review this pattern. |
| | Stephen Hart (14:13 15 Nov.): The pattern has been corrected (I made a mistake by inverting “biography text” and “source”. The use of p106 and p148 for the sources can still be an option. |

> Previous: [Appendix E](/collections-model/target-model/current/appendix-e-moving-events)
