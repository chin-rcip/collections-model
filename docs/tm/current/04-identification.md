---
layout: page
title: Identification
permalink: /target-model/current/identification
---
[Back to the Table of Contents](/target-model/current/information#table-of-contents)

## On This Page

* [Identifiers and Appellations](#identifiers-and-appellations)
* [Identity](#identity)
* [Definitions](#definitions)
* [Identity Patterns](#identity-patterns)
* [Rendering Gender and Cultural Affiliation with E55 Type](#rendering-gender-and-cultural-affiliation-with-e55-type)
* [Nationality, Nationhood and Community With E74 Group](#nationality-nationhood-and-community-with-e74-group)
* [Group Type with E55 Type](#group-type-with-e55-type)

## Identifiers and Appellations

The primary identifier of an actor is its URI, but there are other identifiers associated to it as well, such as the identifiers assigned by contributing museums, or others applied by CHIN. They must be carefully recorded, maintained, and tracked in order to preserve the integrity of museum data. To render these identifiers, we use the property `P1 is identified by` and the class `E42 Identifier`.



| 💡  Example: <br/><br/>For example, Jean Paul Riopelle's URI would be <mic.ca/uri/actor/1234> whilst his CHIN ID would be 1234, and his ID from Artists in Canada would be 13904. |


In the case of names, CIDOC CRM suggests the use of `E41 Appellation`. However, the `E41 Appellation` cannot receive a `P72 has language` tag that would be linked to it, as opposed to the `E33 Linguistic Object`. Usually, names do not need language tags (Stephen is still written Stephen in French and in English), but some of the most famous ones do have specific variations (e.g. *Leonardo da Vinci* is *Léonard de Vinci* in French). Moreover, group names change according to language (e.g. *Montreal Museum of Fine Arts* is *Musée des beaux-arts de Montréal* in French). It is possible to tag a label with a language, but adding the language directly to the entity with the property `P72 has language` facilitates the scripting of SPARQL queries. This is why having a double instantiation for an `E39 Actor`, with both an `E41 Appellation` and an `E33 Linguistic Object`, is useful. 

Even if CHIN does not decide which name is preferred, most museums have preferred and alternative names for actors. To render this choice, this model will specify which appellation is preferred by which institution by using the `E55 Type` class (linked to a controlled vocabulary such as the AAT). CIDOC CRM also offers the `P139 has alternative form` property, a pattern that will not be used here as it is more complex and makes the preferred appellation dependant on the existence of an alternative one (for more information, see [Appendix B: Appellations](/target-model/current/appendix-b-appellations)).

The preference of an appellation should be distinguished by relying on an authority vocabulary rather than a boolean because preference nodes are more meaningful than a yes or no (e.g. this allows to search for all preferred appellations across actors, see the closed [issue #24](https://github.com/chin-rcip/chin-rcip/issues/24) on GitHub for more details).



<p id="gdcalert20" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-113.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert21">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-113.png "image_tooltip")



| 💡  Example 1:  <br/><br/>Jean Paul Riopelle's IDs could be: <br/>Different Identifiers <br/>URI: mic.ca/uri/actor/1234 <br/>CHIN ID: 1234 <br/>Artist in Canada ID: 13904 <br/> <br/>Different appellations: <br/>	Jean Paul Riopelle <br/>Jean-Paul Riopelle <br/>Jean P. Riopelle <br/> |




Some appellations may have been used at a specific moment (e.g. the King is only called so as long as he is the reigning king) or may have evolved (e.g. companies that change their name). Such evolutions can be represented, as FRBRoo does, using the `F52 Name Use Activity` event linked to an `E41 Appellation` with the property `R56 used name`. This `F52 Name Use Activity` event can then be placed temporarily and typed with the `R61 occured in kind of context` property to specify in which context the name has been used (e.g. Charles Lutwidge Dodgson used the name ‘Lewis Carroll’ when writing children's books; for more details on this, please see the closed [issue #35](https://github.com/chin-rcip/chin-rcip/issues/35) on GitHub):  


| 💡  Example 2: <br/><br/>Charles Lutwidge Dodgson used the pen name 'Lewis Carroll' from 1856 to his death in 1898 when publishing children's books whilst his work as a mathematician was published under his birth name Charles Lutwidge Dodgson. |





| 🔎  *To Be Discussed* <br/><br/>It is debated whether an appellation is unique to it bearer (the URI of the appellation would be &lt;mic.ca/uri/appellation/0014582> and only linked to John Doe) or if this appellation is shared by all its bearer (the URI of that appellation would then be &lt;mic.ca/uri/appellation/john_doe> and shared by every John Doe).<br/><br/>This is discussed on <a href="https://github.com/chin-rcip/chin-rcip/issues/25"> CHIN’s Github Issue #25</a>.|


All the appellations and IDs of actors related to the documented actor will use the Appellation and Identifier patterns presented above. This includes the following fields as they appear in the Reference Documentation:


*   Dataset Provider ID
*   Dataset Provider Appellation
*   Actor Record Contributor Appellation
*   Mother Appellation
*   Father Appellation
*   Founding Actor Appellation
*   Dissolving Actor Appellation
*   Related Actor Appellation
*   Group Appellation


## Identity


### Definitions

We gather under the term “identity” six fields that can define the identity of an individual or group:

*   *Gender*: This field documents the cultural gender (not the biological one) that a person identifies as. As a socio-cultural concept it refers to a state or condition associated with a range of characteristics having to do with a person’s behaviour, mannerisms, interests, and appearance, and the way they are associated with gendered categories in a particular cultural context.

*   *Nationality*: This field indicates the status of belonging (by origin, birth, or naturalisation) to a politically autonomous entity endowed with national independence. Unlike cultural affiliation, which relies on self-association with a culture, nationality refers to the legal status of being a citizen or a subject of a recognised state. 

*   *Cultural Affiliation*: This field indicates cultural, rather than legal, belonging to a group that is characterised by shared customs, mores, and practices revolving around common elements such as location, history, language, beliefs, culinary practices, etc. It revolves around collective values and identities and, as such, it is possible to have multiple affiliations at once.
    This belonging is not official in the sense that assent from the concerned group is not formalised or explicit. It is distinct from and broader than nationality, which is a strictly legal concept independent of an actors’ explicit or implicit identification with a culture. For example, an artist born in France and endowed with the French nationality could live in Canada for most of their life and claim Canadian cultural affiliation despite not having Canadian citizenship.

*   *Nationhood*: This field indicates the status of belonging to an autonomous polity endowed with official structures or institutionalised hierarchy (whether formalised or not) as well as shared customs, mores, and practices revolving around common elements such as location, history, language, beliefs, culinary practices, etc. Unlike cultural affiliation--which relies on (self-)identification--or nationality--which refers to the legal status of being a citizen or a subject of a recognised state--,Nationhood describes official belonging with implicit or explicit assent from the group (as represented by its officials or influential members). It refers to the nation the actor identifies / is identified with regardless of their nationality or culture. 

    This field accommodates various types of nationhood, including ethnic, civic, tribal, and multicultural nationhood. Nationhood often revolves around shared practices and traditions transmitted from one generation to another, although it is not exclusively the case. 

    CHIN does not recommend using this field to record association with a religious order (which should be recorded under “Community”) as the latter revolves around an individual conviction and faith in the truthfulness of specific beliefs  more so than belonging to the group itself.

    Polities’ official structures can take the form of different political units such as civil or local government bodies, tribal assemblies, band councils, etc. Although polities often have control of a geographic area or resources, it is not always the case.

*   *Community*: This field indicates the status of belonging to a group or social unit with common norms, values, customs, practices and identities, along with shared beliefs, preferences, needs, and risks. This belonging does not have to be formalised through a governmental body and revolves, rather, around participation and fellowship (although official belonging can occur, such as in the case of Religious communities). 

    Belonging to a community revolves around four major elements that can be used to assess it: membership (the actor shares a sense of personal relatedness); influence (the actor matters to the group and the group matters to the actor); reinforcement (the group contributes to the integration of the actor and the fulfillment of their needs); emotional connection.

*   *Group Type*: This field conceptually characterizes organisations in order to categorize them in ensembles based on their formally or informally stated mission or function.

    This refers to two broad categories of groups, each with more precise lists: social groups (crew, gang, team, etc.) and organisational groups (museum, university, company, government, etc.).


    Families are not represented as groups. Family ties should be represented as ties between actors using relationships fields instead.


| 🔎  *To Be Discussed*<br/><br/>We are currently debating whether it would be best to offer a dedicated Indigenous community field, or if other fields would be necessary to adequately answer the needs of Indigenous Peoples. |


For more details on this, please see [Appendix F: Discussions, Identity Definitions](/target-model/current/appendix-f-discussions#discussion-identity-definitions).


| 💡 Example:<br/><br/>Jean Paul Riopelle would currently be described as such:<br> * Gender: Male <br/> * Nationality: Canadian, Québécois <br/> * Cultural Affiliation: Canadian <br/> * Nationhood: n/a <br/> * Community: n/a |



Even though the identity fields might seem redundant, they are interesting when documenting artists who have typologically complex identities. Generally speaking, nationality is a legally determined field, whereas nationhood is a formally determined one that does not rely on legal procedures; a community entails bidirectional (implicit or explicit) association between the group and the individual, whilst cultural affiliation pertains to an individual’s unidirectional association with a group. 


| 💡  Example: <br/><br/>An Otomí black creator born in Mexico, who came as an undocumented refugee to the United States as a child and identifies as gender fluid could benefit from all of the following fields:  <br/> * Gender: Gender Fluid <br/> * Nationality: Mexican <br/> * Cultural Affiliation: American, Otomí <br/> * Nationhood: Hñähñu <br/> * Community: Hñähñu, African-American, LGBTQIA <br/><br/>Historically, a Community field might also be useful in the case of a missionary painter who practiced on the Canadian territory before the constitution of the state: <br/> * Gender: Male <br/> * Nationality: French <br/> * Cultural Affiliation: Canadian <br/> * Nationhood: n/a <br/> * Community: Jesuits, Nouvelle-France |




| 🔎  *To Be Discussed*<br/><br/>Whether it is best to assign provincial cultural information to Nationhood or Community is up for debate. Your input on this matter would be welcome. <br/><br/>We are also debating whether historical territorial information (e.g. Nouvelle-France) should be assigned to the Cultural Affiliation, Nationhood, or Community field. The best terms to use, according to their definition, is also something we are unsure of (culture / cultural affiliation, Indigenous cultural affiliation / Indigenous nationhood). Indigenous Cultural Affiliation is the term used in the First Nations, Inuit and Métis Ontology, which is why it was first selected, although this field has in the end been expanded to cultural affiliations in general. However, the term nationhood seems better suited to this category as well as more representative of how it is intended to be used (considering a Community field, that entails a form of cultural affiliation, is offered as well). Naming and defining those terms will thus be crucial and input on this matter will be most welcomed. |


### Identity Patterns

There are three possible ways to render genders, communities, and nationalities in CIDOC CRM: with an `E55 Type`, with an `E5 Event`, or with the use of `E74 Group`. It is also possible to use external ontologies, like [bio CRM](https://helda.helsinki.fi//bitstream/handle/10138/236822/paper10.pdf?sequence=1) or [ORE Aggregation](http://www.openarchives.org/ore/1.0/datamodel).

For the moment, CHIN has decided to use the simple `E55 Type` pattern to identify gender and cultural affiliation whilst `E74 Group` will be used to identify nationality, nationhood and community. The `E55 Type` class will be used in conjunction with it to render what the type of the group is (see below). 

See [Appendix C: Identity](/target-model/current/appendix-c-identity) for a description of the rejected [E5 Event](/target-model/current/appendix-c-identity#with-e5-event), [Bio CRM](/target-model/current/appendix-c-identity#with-bio-crm) and [ore:Aggregation](/target-model/current/appendix-c-identity#with-oreaggregation) patterns.


#### Rendering Gender and Cultural Affiliation with `E55 Type` 

The easiest and simplest way to handle the gender field is to add an `E55 Type` to an `E21 Person`. The simplicity of this pattern has one significant drawback: there is no way to determine when the element started or ended, because types are not dated. This makes it impossible to track peoples’ changes in gender over time. Moreover gender is not an inherent attribute of an individual. From a non-binary and non-biological perspective, gender is evolving and does not necessarily constitute a person’s definite attribute. 

For more details on this please see [Appendix F: Discussions, Identity Patterns](/target-model/current/appendix-f-discussions#discussion-identity-patterns).

At this time, an `E55 Type` pattern seems sufficient because museums currently do not, for the most part, hold data pertaining to creators’ genders, and even less so data recording when these changes occurred. This is thus the approach that will be adopted as it makes the model simpler and more efficient by removing the need for unnecessary complexity. 


<p id="gdcalert27" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-114.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert28">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-114.png "image_tooltip")


Should it become necessary or useful, it would be possible to adopt a more complex approach in the future with `ore:aggregation` or another pattern.


| 🔎  *To Be Discussed* <br/><br/> Several discussions on this topic highlighted that modeling fields that contribute to diminishing marginalisation should be considered like one of CHIN’s collaborator mentioned:<br/><br/> “So long as it is clear that multiple E55 gender identities can be related to a given E21 Person, this could provide a smoothest route to representing complexity of identity with limited museum data. whilst "model the documentation" is a key rule to follow, it should not be an excuse to continue marginalisation, and I think MiC can strike a balance between the data that there is, and the data that arguably there should be made space for” <br/><br/>Philippe Michon agreed and replied the following: <br/><br/>"You're right, I think we have to provide a more complex pattern eventually to demonstrate the need of more relevant data around this reality."<br/><br/>CHIN is thus wondering whether it would be necessary to adopt this more complex  <code>ore:aggregation</code> approach and would appreciate your input on this matter.<br/><br/>Some of the  issues related to this identity pattern are discussed on <a href="https://github.com/chin-rcip/chin-rcip/issues/13"> CHIN’s Github Issue #13</a>. |



| 💡  Example:<br/><br/>In the case of Jean Paul Riopelle, the artist would have as gender "Male". <br/><br/>Kent Monkman would be described as having the gender "Two-Spirit"|





#### Nationality, Nationhood and Community With `E74 Group`

Identifying (or being identified as) a member of a community or nationality is conceptually similar to joining an `E74 group` of people bound together so that it could be an appropriate way to render such concepts. 

CIDOC CRM’s `E39 Actor` (a superclass of `E74 Group`) “comprises people, either individually or in groups, who have the potential to perform intentional actions of kinds for which someone may be held responsible” [(Doerr and Ore 2019c, 22)](https://www.zotero.org/google-docs/?bwiwUZ). Some believe, as stated in the linked.art issue 152, that all of the people who have had a particular nationality cannot take action as a single coherent entity, which would seem to disqualify `E74 Group` from representing the Identity fields [(Conal-Tuohy 2018)](https://www.zotero.org/google-docs/?riTc3L). However, a group, at any moment, is composed of some people and it is those people in that relevant time that can act collectively. Because using `E74 Group` enables datation, it is a preferable approach when documenting nationality as well as community membership. This is the approach that CHIN is considering at the moment, more out of convenience and efficacy than out of philosophical accuracy. As gender is not a cohesive group, it cannot be modeled as an `E74 Group`. 

For more details on this, please see [Appendix F: Discussions, Nationality, Nationhood and Community With E74 Group](/target-model/current/appendix-f-discussions#discussion-nationality-nationhood-and-community-with-e74-group). 


| 🔎  *To Be Discussed* <br/><br/>Some issues about this pattern are discussed on <a href="https://github.com/chin-rcip/chin-rcip/issues/13"> CHIN’s Github Issue #13</a>. |


<p id="gdcalert29" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-115.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert30">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-115.png "image_tooltip")



| 💡 Example:<br/><br/>In the case of Jean Paul Riopelle, the artist is Canadian since his birth on the 7th of October 1923. |



#### Group Type with `E55 Type`

The Group Type is a qualifier assigned to organisations in order to categorize them in ensembles based on their formally or informally stated mission or function.  It is intended to ease recognition of entities and determine whether a specific group is a museum, a company, a group of artists, etc. It will rely on the use of a controlled vocabulary to ensure consistency in the types proposed. 

The Group Type is an `E55 Type` linked to an `E74 Group` with the property `P2 has type`. It is important to also type this `E55 Type` in order to distinguish it from other `E55 Type` elements linked to the same `E74 Group`.



<p id="gdcalert30" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-116.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert31">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-116.png "image_tooltip")



| 💡 Example:<br/><br/> The Group of Seven has "Group of Artists" as a group type. |

