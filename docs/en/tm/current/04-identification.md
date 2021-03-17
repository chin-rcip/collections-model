---
layout: page
language: en
title: Identification
permalink: /en/target-model/current/identification
other_link: /fr/modele-cible/actuel/introduction
sidebar: tm
---
<!-- [Back to the Table of Contents](/collections-model/en/target-model/current/information#table-of-contents)
 -->


## Identifiers and Appellations

The primary identifier of an actor is its URI, but there are other identifiers associated to it as well, such as the identifiers assigned by providers, or others applied by CHIN. They must be carefully recorded, maintained, and tracked in order to preserve the integrity of original data. To render these identifiers, the property `P1_is_identified_by` is used along with the class `E42_Identifier`.



| 💡  Example: <br/><br/>For example, Jean Paul Riopelle's URI would be <mic.ca/uri/actor/1234> whilst his CHIN ID would be 1234, and his ID from Artists in Canada would be 13904. |


In the case of names, CIDOC CRM suggests the use of `E41_Appellation`. However, the `E41_Appellation` cannot be linked to a `P72_has_language` tag. Usually, names do not need language tags (Stephen is still written Stephen in French and in English), but some of the most famous ones do have specific variations (e.g. *Leonardo da Vinci* is *Léonard de Vinci* in French) that must be accounted for as well as group names that sometimes vary per language (e.g. *Montreal Museum of Fine Arts* is *Musée des beaux-arts de Montréal* in French). It is possible to tag a label with a language, but adding the language directly to the entity with the property `P72_has_language` facilitates the scripting of SPARQL queries and thus appears to be a better option. This is why the double instantiation of an `E39_Actor` (with both an `E41_Appellation` and an `E33_Linguistic_Object`) appears most appropriate. 

Even if CHIN does not adjudicate appellation precedence, most providers have preferred and alternative names for actors, which can be rendered using the `E55_Type` class (linked to a controlled vocabulary such as the AAT). CIDOC CRM also offers the `P139_has_alternative_form` property, a pattern that will not be used here as it is more complex and makes the preferred appellation dependant on the existence of an alternative one (for more information, see [Appendix B: Appellations](/collections-model/en/target-model/current/appendix-b-appellations)).

In addition, the precedence of an appellation should be distinguished by relying on a controlled vocabulary rather than on a boolean since precedence nodes are more meaningful than a yes or no (e.g. this allows to search for all preferred appellations across actors, see the closed [issue #24](https://github.com/chin-rcip/chin-rcip/issues/24) on GitHub for more details).

<a name="020_Pattern_IdentifiersAppellations_p"></a>020_Pattern_IdentifiersAppellations_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=020_Pattern_IdentifiersAppellations_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1Na5HNOLWpr2fcpOFvw9Gr1MCSurMrnHT%26export%3Ddownload"></iframe>


| 💡  Example 1:  <br/><br/>Jean Paul Riopelle's IDs could be: <br/>Different Identifiers <br/>URI: mic.ca/uri/actor/1234 <br/>CHIN ID: 1234 <br/>Artist in Canada ID: 13904 |

<a name="021_Example_IdentifierRiopelle_p"></a>021_Example_IdentifierRiopelle_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=021_Example_IdentifierRiopelle_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1dDstiGxnpsmqzr0O-aRHCYp6IwqAmWPD%26export%3Ddownload"></iframe>

| Different appellations: <br/>	Jean Paul Riopelle <br/>Jean-Paul Riopelle <br/>Jean P. Riopelle <br/> |

<a name="022_Example_AppellationRiopelle_p"></a>022_Example_AppellationRiopelle_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=022_Example_AppellationRiopelle_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1ePf29iGmYuXjRl3V63DQs5XctkIcPOUe%26export%3Ddownload"></iframe>

Some appellations may have been used at a specific moment (e.g. the King is only called so as long as he is the reigning king) or may have evolved (e.g. companies that change their name). Such evolutions can be represented, as FRBRoo does, using the `F52_Name_Use_Activity` event linked to an `E41_Appellation` with the property `R56_used_name`. This `F52_Name_Use_Activity` event can then be placed temporarily and qualified with the `R61_occured_in_kind_of_context` property to specify in which context the name has been used (e.g. Charles Lutwidge Dodgson used the name ‘Lewis Carroll’ when writing children's books; for more details on this, please see the closed [issue #35](https://github.com/chin-rcip/chin-rcip/issues/35) on GitHub):  


| 💡  Example 2: <br/><br/>Charles Lutwidge Dodgson used the pen name 'Lewis Carroll' from 1856 to his death in 1898 when publishing children's books whilst his work as a mathematician was published under his birth name Charles Lutwidge Dodgson. |

<a name="023_Example_AppellationCarroll_p"></a>023_Example_AppellationCarroll_p
<iframe frameborder="0" style="width:100%;height:900px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=023_Example_AppellationCarroll_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1krJ7vWTrqMbxaEsV4Bog7XryrdjbF7-P%26export%3Ddownload"></iframe>

| ![GitHub Mark](https://user-images.githubusercontent.com/48293227/104475587-49182180-558d-11eb-87fc-9f95190cb332.png) *Related Github Issue*<br/><br/>This topic is discussed in [Issue #25](https://github.com/chin-rcip/chin-rcip/issues/25) |


All the appellations and IDs of actors related to the documented actor use the Appellation patterns presented above. These include the following nodes:

*   [Actor ID](/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-id) (to record the dataset provider ID)
*   [Dataset Creation Participant Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#dataset-creation-participant-appellation)
*   [Record Contributor Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#record-contributor-appellation)
*   [Mother Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#mother-appellation)
*   [Father Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#father-appellation)
*   [Founding Actor Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#founding-actor-appellation)
*   [Dissolving Actor Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#dissolving-actor-appellation)
*   [Related Actor Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#related-actor-appellation)
*   [Group Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#group-appellation)


## Identity


### Definitions

The term “identity” can encompass, in the context of this model, six fields that can define the identity of an individual or group:

*   [*Gender Type*](/collections-model/en/semantic-paths-specification/current/entry-nodes#gender-type): This node documents the cultural gender (not the biological one) that a person identifies as. As a socio-cultural concept it refers to a state or condition associated with a range of characteristics having to do with a person’s behaviour, mannerisms, interests, and appearance, and the way they are associated with gendered categories in a particular cultural context.

*   [*Nationality*](/collections-model/en/semantic-paths-specification/current/entry-nodes#nationality): This node indicates the status of belonging (by origin, birth, or naturalization) to a politically autonomous entity endowed with national independence. Unlike cultural affiliation, which relies on self-association with a culture, nationality refers to the legal status of being a citizen or a subject of a recognised state. 

*   [*Cultural Affiliation Type*](/collections-model/en/semantic-paths-specification/current/entry-nodes#cultural-affiliation-type): This node indicates cultural, rather than legal, belonging to a group that is characterized by shared customs, mores, and practices revolving around common elements such as location, history, language, beliefs, culinary practices, etc. It revolves around collective values and identities and, as such, it is possible to have multiple affiliations at once.
    This belonging is not official in the sense that assent from the concerned group is not formalized or explicit. It is distinct from and broader than nationality, which is a strictly legal concept independent of an actors’ explicit or implicit identification with a culture. For example, an artist born in France and endowed with the French nationality could live in Canada for most of their life and claim Canadian cultural affiliation despite not having Canadian citizenship.

*   [*Nationhood*](/collections-model/en/semantic-paths-specification/current/entry-nodes#nationhood): This node indicates the status of belonging to an autonomous polity endowed with official structures or institutionalized hierarchy (whether formalized or not) as well as shared customs, mores, and practices revolving around common elements such as location, history, language, beliefs, culinary practices, etc. Unlike cultural affiliation-which relies on (self-)identification-or nationality-which refers to the legal status of being a citizen or a subject of a recognised state-,Nationhood describes official belonging with implicit or explicit assent from the group (as represented by its officials or influential members). It refers to the nation the actor identifies/is identified with regardless of their nationality or culture. 

    This node accommodates various types of nationhood, including ethnic, civic, tribal, and multicultural nationhood. Nationhood often revolves around shared practices and traditions transmitted from one generation to another, although it is not exclusively the case. 

    CHIN does not recommend using this field to record association with a religious order (which should be recorded under “Community”) as the latter revolves around an individual conviction and faith in the truthfulness of specific beliefs  more so than belonging to the group itself.

    Polities’ official structures can take the form of different political units such as civil or local government bodies, tribal assemblies, band councils, etc. Although polities often have control of a geographic area or resources, it is not always the case.

*   [*Community*](/collections-model/en/semantic-paths-specification/current/entry-nodes#community): This node indicates the status of belonging to a group or social unit with common norms, values, customs, practices and identities, along with shared beliefs, preferences, needs, and risks. This belonging does not have to be formalised through a governmental body and revolves, rather, around participation and fellowship (although official belonging can occur, such as in the case of Religious communities). 

    Belonging to a community revolves around four major elements that can be used to assess it: membership (the actor shares a sense of personal relatedness); influence (the actor matters to the group and the group matters to the actor); reinforcement (the group contributes to the integration of the actor and the fulfillment of their needs); emotional connection.

*   [*Group Type*](/collections-model/en/semantic-paths-specification/current/entry-nodes#group-type): This node conceptually characterizes organisations in order to categorize them in ensembles based on their formally or informally stated mission or function.

    This refers to two broad categories of groups, each with more precise lists: social groups (crew, gang, team, etc.) and organizational groups (museum, university, company, government, etc.).


    Families are not represented as groups: rather, familial relationships should be represented as ties between actors using [relationship nodes](/collections-model/en/semantic-paths-specification/current/entry-nodes#relationship-actor-role).


| 🔎  *To Be Discussed*<br/><br/>CHIN is currently debating whether it would be best to offer a dedicated Indigenous community field, or if other fields would be necessary to adequately answer the needs of Indigenous Peoples. |


For more details on this, please see [Appendix F: Discussions, Identity Definitions](/collections-model/en/target-model/current/appendix-f-discussions#discussion-identity-definitions).


| 💡 Example:<br/><br/>Jean Paul Riopelle would currently be described as such:<br> * Gender Type: Male <br/> * Nationality: Canadian, Québécois <br/> * Cultural Affiliation Type: Canadian <br/> * Nationhood: n/a <br/> * Community: n/a |


Even though the identity nodes might seem redundant, they are interesting when documenting artists who have typologically complex identities. Generally speaking, nationality is a legally determined field, whereas nationhood is a formally determined one that does not rely on legal procedures; a community entails bidirectional (implicit or explicit) association between the group and the individual, whilst cultural affiliation pertains to an individual’s unidirectional association with a group. These subtle distinctions illustrate the need for several nodes that can account for the diversity and multitude of cultural identification. 


| 💡  Example: <br/><br/>An Otomí black creator born in Mexico, who came as an undocumented refugee to the United States as a child and identifies as gender fluid could benefit from all of the following fields:  <br/> * Gender Type: Gender Fluid <br/> * Nationality: Mexican <br/> * Cultural Affiliation Type: American, Otomí <br/> * Nationhood: Hñähñu <br/> * Community: Hñähñu, African-American, LGBTQIA <br/><br/>Historically, a Community field might also be useful in the case of a missionary painter who practiced on the Canadian territory before the constitution of the state: <br/> * Gender Type: Male <br/> * Nationality: French <br/> * Cultural Affiliation Type: Canadian <br/> * Nationhood: n/a <br/> * Community: Jesuits, Nouvelle-France |


| 🔎  *To Be Discussed*<br/><br/>Whether it is best to assign provincial cultural information to Nationhood or Community is up for debate; additional input on this matter would be welcome. <br/><br/>CHIN is also debating whether historical territorial information (e.g. Nouvelle-France) should be assigned to the Cultural Affiliation Type, Nationhood, or Community nodes. The best terms to use, according to their definition, are also elements that are under discussion (culture / cultural affiliation, Indigenous cultural affiliation / Indigenous nationhood). Indigenous Cultural Affiliation is the term used in the [First Nations, Inuit and Métis Ontology](https://nationalindigenousknowledgeandlanguagealliance.home.blog/author/natindigenousknowledgelanguagealliance/), which is why it was first selected, although this field has in the end been expanded to cultural affiliations in general. However, the term nationhood seems better suited to this category as well as more representative of how it is intended to be used (considering a Community node, that entails a form of cultural affiliation, is offered as well). Naming and defining those terms will thus be crucial and input on this matter will be most welcomed. |


### Identity Patterns

There are three possible ways to render genders, communities, and nationalities in CIDOC CRM: with an `E55_Type`, with an `E5_Event`, or with the use of `E74_Group`. It is also possible to use external ontologies, like [Bio CRM](https://helda.helsinki.fi//bitstream/handle/10138/236822/paper10.pdf?sequence=1) or [ORE Aggregation](http://www.openarchives.org/ore/1.0/datamodel).

For the moment, CHIN has decided to use the simple `E55_Type` pattern to identify gender and cultural affiliation whilst `E74_Group` will be used to identify nationality, nationhood and community. The `E55_Type` class will be used in conjunction with it to render what the type of the group is (see below). 

See [Appendix C: Identity](/collections-model/en/target-model/current/appendix-c-identity) for a description of the rejected [E5 Event](/collections-model/en/target-model/current/appendix-c-identity#with-e5-event), [Bio CRM](/collections-model/en/target-model/current/appendix-c-identity#with-bio-crm) and [ORE Aggregation](/collections-model/en/target-model/current/appendix-c-identity#with-oreaggregation) patterns.


### Rendering Gender and Cultural Affiliation with `E55_Type` 

The easiest and simplest way to render [gender](/collections-model/en/semantic-paths-specification/current/entry-nodes#gender-type) is to add an `E55_Type` to an `E21_Person`. However, the simplicity of this pattern has one significant drawback: there is no way to determine when the element started or ended, because types are not dated. This makes it impossible to track peoples’ changes in gender over time. Moreover gender is not an inherent attribute of an individual. From a non-binary and non-biological perspective, gender is evolving and does not necessarily constitute a person’s definite attribute so that typing this person as such would be problematic. 

For more details on this please see [Appendix F: Discussions, Identity Patterns](/collections-model/en/target-model/current/appendix-f-discussions#discussion-identity-patterns).

Despite this, considering institutions currently hold little data pertaining to actors’ genders—and even less so data recording when these changes occurred—an `E55_Type` pattern seems sufficient as it makes the model simpler and more efficient by removing the need for unnecessary complexity. However, should it become necessary or useful, this position can be revised in favour of a more complex pattern or the use of `ore:aggregation`.

<a name="024_Pattern_Gender_p"></a>024_Pattern_Gender_p
<iframe frameborder="0" style="width:100%;height:300px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=024_Pattern_Gender_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1VPdvrCqlBYG62QWKne3TKj6XbrjqmY5L%26export%3Ddownload"></iframe>


| ![GitHub Mark](https://user-images.githubusercontent.com/48293227/104475587-49182180-558d-11eb-87fc-9f95190cb332.png) *Related Github Issue*<br/><br/>This topic is discussed in [Issue #13](https://github.com/chin-rcip/chin-rcip/issues/13) |


| 💡  Example:<br/><br/>In the case of Jean Paul Riopelle, the artist would have as gender "Male". |

<a name="025_Example_GenderRiopelle_p"></a>025_Example_GenderRiopelle_p
<iframe frameborder="0" style="width:100%;height:400px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=025_Example_GenderRiopelle_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1PZzHbKs9k8R1rNukxShCdhZQBGlYf8uJ%26export%3Ddownload"></iframe>

| Kent Monkman could be described as having the gender "Two-Spirit"|

<a name="026_Example_GenderMonkman_p"></a>026_Example_GenderMonkman_p
<iframe frameborder="0" style="width:100%;height:400px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=026_Example_GenderMonkman_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1DdzMhxXriGaOnfaUA5sWoaU7BWrSJNX-%26export%3Ddownload"></iframe>


### Nationality, Nationhood and Community With `E74_Group`

Identifying (or being identified) as a member of a [community](/collections-model/en/semantic-paths-specification/current/entry-nodes#community), [nationhood](/collections-model/en/semantic-paths-specification/current/entry-nodes#nationhood) or [nationality](/collections-model/en/semantic-paths-specification/current/entry-nodes#nationality) is conceptually similar to joining an `E74_Group` of people bound together by this shared nationality, nationhood or community belonging. 

CIDOC CRM’s `E39_Actor` (a super-class of `E74_Group`) “comprises people, either individually or in groups, who have the potential to perform intentional actions of kinds for which someone may be held responsible” [(Le Boeuf et al. 2015, sec. E39 Actor)](/collections-model/en/target-model/current/bibliography#le-boeuf-et-al-2015). Some believe, as stated in the linked.art issue 152, that all of the people who have had a particular nationality cannot take action as a *single coherent entity*, which would seem to disqualify `E74_Group` from representing the Identity fields [(Conal-Tuohy 2018)](/collections-model/en/target-model/current/bibliography#conal-tuohy-2018). However, a group, at any moment, is composed of people that can act collectively. Because using `E74_Group` enables datation, it is a preferable approach when documenting nationality as well as community belonging. This is the approach CHIN has elected to use at the moment, more out of convenience and efficacy than out of philosophical accuracy (this is not the case for gender, which does not represent a cohesive group and thus cannot be modelled as an `E74_Group`).  

For more details on this, please see [Appendix F: Discussions, Nationality, Nationhood and Community With E74 Group](/collections-model/en/target-model/current/appendix-f-discussions#discussion-nationality-nationhood-and-community-with-e74-group). 

| ![GitHub Mark](https://user-images.githubusercontent.com/48293227/104475587-49182180-558d-11eb-87fc-9f95190cb332.png) *Related Github Issue*<br/><br/>This topic is discussed in [Issue #13](https://github.com/chin-rcip/chin-rcip/issues/13) |

<a name="027a_Pattern_Identity_Nationality_p"></a>027a_Pattern_Identity_Nationality_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=027_Pattern_Identity_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1LEawkI5ayALX1OORfR6exLOCSOPccyeD%26export%3Ddownload"></iframe>

<a name="027b_Pattern_Identity_Nationhood_p"></a>027a_Pattern_Identity_Nationhood_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=027b_Pattern_Identity_Nationhood_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1K79JTFXTMacM-lyGjr6yNxC-t9YTR3UK%26export%3Ddownload"></iframe>

<a name="027c_Pattern_Identity_Community_p"></a>027c_Pattern_Identity_Community_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=027c_Pattern_Identity_Community_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1I59CaWE-bj2nxJkbQtQeUMfp6KpJOM5n%26export%3Ddownload"></iframe>

| 💡 Example:<br/><br/>In the case of Jean Paul Riopelle, the artist is Canadian since his birth on the 7th of October 1923. |

<a name="028_Example_NationalityRiopelle_p"></a>028_Example_NationalityRiopelle_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=028_Example_NationalityRiopelle_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1ZwohesWAtWQuip1ew4fMim4p3iyMWPuu%26export%3Ddownload"></iframe>

### Group Type with `E55_Type`

A [group type](/collections-model/en/semantic-paths-specification/current/entry-nodes#group-type) is a qualifier assigned to organizations in order to categorize them in ensembles based on their formally or informally stated mission or function.  It is intended to facilitate the recognition of entities and determine whether a specific group is a museum, a company, a group of artists, etc. by using of a controlled vocabulary to ensure consistency in the types proposed. 

It is an `E55_Type` linked to an `E74_Group` with the property `P2_has_type`, with a metatype being applied to this `E55_Type` in order to distinguish it from other `E55_Type` elements linked to the same `E74_Group`.

<a name="029_Pattern_GroupType_p"></a>029_Pattern_GroupType_p
<iframe frameborder="0" style="width:100%;height:400px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=029_Pattern_GroupType_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1XNASQ6iuZl3sMyMbMfs6RlWd3AX49Sg5%26export%3Ddownload"></iframe>

| 💡 Example:<br/><br/> The Group of Seven has "Group of Artists" as a group type. |

<a name="030_Example_GroupTypeGroup7_p"></a>030_Example_GroupTypeGroup7_p
<iframe frameborder="0" style="width:100%;height:400px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=030_Example_GroupTypeGroup7_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1udaOnfqEnDQ-hPQpFcg5v-Sb1UQoDNAX%26export%3Ddownload"></iframe>


> Previous: [General Concepts](/collections-model/en/target-model/current/general-concepts)<br>Next: [Life Events](/collections-model/en/target-model/current/life-events)
