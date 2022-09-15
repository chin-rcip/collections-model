---
layout: page
language: en
title: Group Belonging
permalink: /en/target-model/current/group-belonging
other_link: /fr/modele-cible/actuel/appartenance-a-un-groupe
sidebar: tm22
date: 2022-03-31
description: The Actors Target Model Specification semantically models actors in a heritage context. Patterns most relevant to actors' lives are presented along with diagrams and examples illustrating them, as well as a record and explanation of relevant decisions that were made when developing said patterns. This is a theoretical documentation that has never been tested or implemented.
---

Version 2.2 ([Previous versions](/collections-model/en/versions))

## At Glance

This pattern can be used to represent the information pertaining to the official association of a person (or group) with a·nother group, most often in the form of a membership or registration record. It includes: 

* The group with which there is an association; 
* The role an actor endorsed in the context of a group; 
* The dates indicating the moment an actor joined and left a group (beginning and end of the group belonging).

It pertains specifically to the belonging in the context of persons and groups of persons, and not to the nature of a group. This pattern does not include: 

* The affiliation (and role) of actors with groups whose boundaries are not formally defined;
* The unbelonging (e.g. rejection from a group from which one has never been a member);
* The belonging to stylistic movements (e.g. the period during which the principles of a stylistic movement are most visible and common in artefacts); 
* The belonging of non-human agents (e.g. an animal used in the context of research is not part of the research team); 
* The family of an actor (use the [Family Belonging](/collections-model/en/target-model/current/family-belonging) pattern instead);
* The culture an actor associates or is associated with, such as "Etruscan";
* The unformalized belonging of the actor to a community, such as "LGBTQIA+"; 
* The formalized or official belonging to a nation that is legal in nature, such as "Canadian";
* The formalized or official belonging to a nation that is not legal in nature, such as "Hñähñu". 

## Introduction and Context

### Theoretical Background

Belonging to groups, solidarities, and collectivities or organizations is an intrinsic part of the social world that is at the intersection of the self and the social as people coalesce around shared commonalities. The belonging operates at different scales from the domestic family unit to global, international communities. Such belonging has been recorded and studied by humans since at least Antiquity, as records of agreements, compacts, conventions, and laws demonstrate (Epstein & Zalta 2018). 

A number of group belonging types are commonly represented in museum datasets in dedicated fields (e.g. community, cultural affiliation, family, nationhood, nationality). Yet, belonging can be much more varied and rich than these fields allow as the understanding of this concept has drastically evolved as a result of globalizing processes and societal changes that have disrupted typical bonds between identity, citizenship, and place in favour of more flexible affiliations to social entities (Halse 2018). 

In addition, belonging to a solidarity is often not limited to humans who can have feelings of group belonging towards or encompassing other entities or agents that include but are not limited to: 

* Land and/or territory; 
* Domesticated animals and/or wildlife; 
* Conceptual narratives and/or traditions (Wright 2015, 392-393). 

Important elements that determine how group belonging operates and what it encompasses include: 

* The location and era in which a person evolves (i.e. their social context);
* How they identify as a member of a group, most often through social practices or mores that link them to a particular solidarity or sociocultural space (i.e. their role); 
* What values they display in the context of cultural and geographic boundaries (i.e. their worldview) (Halse 2018). 

Finally, it is important to recognize that group belonging fundamentally operates as a force of both inclusion and exclusion. Scrutiny over this matter illuminates how the status of *not belonging* or *unbelonging* (i.e. being rejected by a group without having ever been a member of it) can also in and of itself be meaningful as it can be symptomatic of an individual or collective agency (Halse 2018).

### Statement of Need

Belonging to groups is often thought of in terms of having dealings or interactions with others that range in duration from brief to enduring. A brief review of terms pertaining to such dealings in thesauri and dictionaries indicates that they often reflect a set of connected behaviours, rights, obligations, beliefs, and norms that are determined by how members behave towards each other, their mutual interests or commonalities, and the function of the group itself (Art & Architecture Thesaurus 2019; Free Dictionary 2019b; 2019c; 2019a; Wikipedia 2019e; 2019a; 2019c; 2019b; 2019d). 

A review of other heritage models concerned with such dealings reveals they have mostly focused on organizations as an operating principle around which to document belonging with concepts such as [organization membership](https://linked.art/model/actor/#organization-membership) (Linked.art) or [institutional affiliation and association](https://docs.swissartresearch.net/et/persons/#social-relations) (Person Reference Data Model). 

In all cases, group belonging has exclusively been envisioned as a human-to-human space of interaction whereas individuals are joined in relationships either directly (i.e. members are known to each other) or indirectly (i.e. members do not necessarily have personal interactions but operate based on commonalities). The latter can include "societies of strangers" who have dispersed relations in networks that can be far-ranging and diverse and do not rely on people "knowing each other" such as forums, fanbases, etc. (Amin 2012, 12-13).

This general overview illuminates the need for a model that addresses the role an actor endorses as part of a group and, as previously mentioned, the temporal context in which they do so. 

## Description of the Pattern

There are three main ensembles to this pattern: the description of a group, the joining of an actor in a group, and the leaving of a group by an actor. 

The information pertaining to a group is concentrated around an instance of `E74_Group` pointing to an instance of both `E41_Appellation` and `E33_Linguistic_Object` through the property `P1_is_identified_by` which renders the literal value of the [Group Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#group-appellation) by the property `P190_has_symbolic_content`. 

The information pertaining to the enlisting of an actor in a group is concentrated around an instance of `E85_Joining` which operates as a joining node between an instance of `E39_Actor` and an instance of `E74_Group`. The joining of an actor in a group is modelled as follows: 

* An instance of `E39_Actor` is linked to an instance of `E85_Joining` by the property `P143_joined`;
* The moment at which an actor joined a group is indicated using the [Temporal Bounds](/collections-model/en/target-model/current/temporal-bounds) pattern linked to the instance of `E85_Joining` through the property `P4_has_time-span` with values extracted from the [Group Joining Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#group-joining-date-begin), [Group Joining Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#group-joining-date-begin-qualifier), [Group Joining Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#group-joining-date-end), and [Group Joining Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#group-joining-date-end-qualifier) entry nodes. The instance of `E85_Joining` is also linked by the property `P01_has_domain` to an instance of `PC144_joined_with` which is also linked to the instance of `E74_Group` through the property `P02_has_range`;
* In which role an actor enlisted as a member is indicated by linking the instance of `PC144_joined_with` to the [Group Member Role](/collections-model/en/semantic-paths-specification/current/entry-nodes#group-member-role) value (an instance of `E55_Type`) through the property `P144.1_kind_of_member`.

The information pertaining to an actor dissociating from a group is concentrated around an instance of `E86_Leaving` which operates as a leaving node between an instance of `E39_Actor` and an instance of `E74_Group`. The leaving of a group by an actor is modelled as follows: 

* An instance of `E39_Actor` is linked to an instance of `E86_Leaving` by the property `P145_separated`;
* The moment at which an actor left a group is indicated using the [Temporal Bounds](/collections-model/en/target-model/current/temporal-bounds) pattern linked to the instance of `E86_Leaving` through the property `P4_has_time-span` with values extracted from the [Group Leaving Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#group-leaving-date-begin), [Group Leaving Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#group-leaving-date-begin-qualifier), [Group Leaving Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#group-leaving-date-end), and [Group Leaving Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#group-leaving-date-end-qualifier) entry nodes. The instance of `E86_Leaving` is also linked by the property `P146_separated_from` to the instance of `E74_Group`.

## Diagram

<a name="059_Pattern_GroupBelonging_p"></a>059_Pattern_GroupBelonging_p

<iframe frameborder="0" style="width:100%;height:500px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=059_Pattern_GroupBelonging_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1r-9SGEmpEU-_RmXwX5rsa3gBR2Jh_iqg%26export%3Ddownload"></iframe>

## Examples

### Example 1

Yousuf Karsh is a Companion (`P144.1_kind_of_member`, Group Member Role) of the Order of Canada (`P190_has_symbolic_content`, Group Appellation) which was established on the 1st of July 1967 (`P82a_begin_of_the_begin`, Formation Date Begin; `P82b_end_of_the_end`, Formation Date End) by then Governor General Roland Michener (`P190_has_symbolic_content`, Founding Actor Appellation) in Ottawa (ON, Canada) (`P7_took_place_at`, Formation Place) (Hillmer 2018; Skidmore 2015). Karsh became a Companion in 1990 (`P82a_begin_of_the_begin`, Group Joining Date Begin; `P82b_end_of_the_end`, Group Joining Date End). 

<div id="0001_100_group-belonging" class="example"></div>

### Example 2

A. J. Casson (`P190_has_symbolic_content`, Actor Appellation) joined in 1933 (`P82a_begin_of_the_begin`, Group Joining Date Begin; `P82b_end_of_the_end`, Group Joining Date End) the Canadian Group of Painters (`P190_has_symbolic_content`, Group Appellation) (Toronto Public Library 2016).

<div id="0001_113_group-belonging" class="example"></div>

## Related Documentation

### External Models

* Linked.art: [Organization Membership](https://linked.art/model/actor/#organization-membership)
* SARI: [Group Reference Data Model – Member (Actor Relations)](https://docs.swissartresearch.net/et/group/#actor-relations)
* SARI: [Person Reference Data Model – Institutional Affiliation (Social Relations)](https://docs.swissartresearch.net/et/persons/#social-relations)
* SARI: [Person Reference Data Model – Associate (Social Relations)](https://docs.swissartresearch.net/et/persons/#social-relations)

### Entry Nodes

* [Group Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#group-appellation) \| Checklist
* [Group Joining Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#group-joining-date-begin) \| Checklist
* [Group Joining Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#group-joining-date-begin-qualifier) \| Checklist
* [Group Joining Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#group-joining-date-end) \| Checklist
* [Group Joining Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#group-joining-date-end-qualifier) \| Checklist
* [Group Leaving Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#group-leaving-date-begin) \| Checklist
* [Group Leaving Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#group-leaving-date-begin-qualifier) \| Checklist
* [Group Leaving Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#group-leaving-date-end) \| Checklist
* [Group Leaving Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#group-leaving-date-end-qualifier) \| Checklist
* [Group Member Role](/collections-model/en/semantic-paths-specification/current/entry-nodes#group-member-role) \| Checklist

### CIDOC CRM Entities

* `E33_Linguistic_Object` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E33)]
* `E39_Actor` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E39)]
* `E41_Appellation` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E41)]
* `E52_Time-Span` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E52)]
* `E55_Type` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E55)]
* `E74_Group` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E74)]
* `E85_Joining` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E85)]
* `E86_Leaving` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E86)]
* `PC144_joined_with`
* `P01_has_domain (is_domain_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P01)]
* `P02_has_range (is_range_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P02)]
* `P1_is_identified_by (identifies)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P1)]
* `P4_has_time-span (is_time-span_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P4)]
* `P79_beginning_is_qualified_by` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P79)]
* `P80_end_is_qualified_by` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P80)]
* `P82a_begin_of_the_begin`
* `P82b_end_of_the_end`
* `P143_joined (was_joined_by)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P143)]
* `P144.1_kind_of_member` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P144.1)]
* `P145_separated (left_by)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P145)]
* `P146_separated_from (lost_member_by)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P146)]
* `P190_has_symbolic_content` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P190)]

## Discussion

### Rationale

In CIDOC CRM, the property `P107_has_current_or_former_member` allows to directly link an instance of `E39_Actor` to an instance of `E74_Group`. However, such a path would prevent the documentation of the joining and leaving dates of the group, and the role of the member. To enable a more granular description using the DOPHEDA model, CHIN decided to implement the longest path by using the `E85_Joining` and `E86_Leaving` classes. This longest path is recommended as it is always possible to downsize the model, whereas using the shortest option would result in missing datation. The longest path also allows the recording of the role of the member with the use of the property-class `PC144_joined_with`.

### Limitations

The only way to document the evolution of the role of a member is to record a leaving event followed by a new joining event for the newest role of the actor. The addition of instances of `E86_Leaving` and `E85_Joining` is problematic because these additional events never actually occurred: in reality, the actor remained in the group and their role changed.

Though there is a mechanism in this pattern to represent the leaving of a group by an actor, there is no modelization for the unbelonging of an actor to a group which would have to be documented in a dedicated pattern. The latter could represent the act of rejection as an instance of `E5_Event`. For example, a refugee having their application rejected by an asylum country would not be recorded as a status of unbelonging but as an action by the country in question. This is not covered by this pattern. 

The best way to record the existence and evolution of less formalized groups which exist but do not have recorded members, or only have a fraction of their members knowingly and officially recorded as such, is also a challenge. For example, movements such as [Black Lives Matter](https://blacklivesmatter.com/), the [Sunrise Movement](https://www.sunrisemovement.org/), the [Occupy Movement](http://occupywallst.org/), or other activist groups are notoriously decentralized and encompass a wide range of people who espouse their values and affiliate with them without having a formal membership or being donors. People who are part of such movements are often anonymous for personal or systemic reasons (e.g. Sunrise is a youth-led movement that makes financial and official involvement more complicated for teenagers if they do not have the support of their parents). Leaders can be documented, but establishing official founders can in some cases be difficult, even more so for people who affiliate with a movement and are activists but do not hold a formally or informally recognized position with regards to the movement. Currently, because the scope note of the class `E74_Group` only includes formal groups that act collectively, those informal groups and the members associated with them are not addressed by this pattern, nor are they addressed by the [Formation and Dissolution of a Group](/collections-model/en/target-model/current/formation-and-dissolution) pattern.

Similarly, the scope note of the class `E74_Group` also restricts the group belonging to a person or a group of persons which therefore limits the possibility to document the membership of non-humans, despite what current research highlights (see [Issue #21](https://github.com/chin-rcip/collections-model/issues/21)). 

### Related GitHub Issues

* [Issue #21 "How to model [an] artistic movement?"](https://github.com/chin-rcip/collections-model/issues/21)
* [Issue #36 "Does the dissolution of a group implies the leaving of its members?"](https://github.com/chin-rcip/collections-model/issues/36)
* [Issue #66 "PC11_had_participant and P11.1_in_the_role_of creation proposal"](https://github.com/chin-rcip/collections-model/issues/66)

### Edge Cases

#### Example 1 {#edge-cases-example-1}

The Abitibi Power and Paper Company was acquired by Price Brothers in 1974. Price Brothers was then merged with Stone Consolidated in 1997 which was in turn merged with Bowater to form AbitibiBowater in 2007, now known under the name Resolute Forest Products (Wikipedia 2021). In the case of such mergers and acquisitions, what would be considered to be the leaving of a group and the joining of another, when the dissolution of the company itself is up for debate, would be unclear.

#### Example 2 {#edge-cases-example-2}

The recipient of an award might be considered as part of a group that includes all of the recipients of this specific award, although it is not a formal group. In such a case, the founder of the group might be considered to be the first recipient just as much as the granting organism. For example, the Governor General's Literary Awards were conceived and inaugurated in 1937 by John Buchan, 1st Baron Tweedsmuir who was then acting as 15th Governor General of Canada. He awarded the award for Fiction to Laura G. Salverson for *The Dark Weaver*, for Poetry of drama to E.J. Pratt for *The Fable of the Goats*, and for Non-fiction to Stephen Leacock for *My Discovery of the West* (Canada Council for the Arts n.d.). Considering the group would be the "Recipients of the Governor General of Canada Literary Awards", the original founder·s could either be solely John Buchan, 1st Baron Tweedsmuir, or the first recipients, arguing they played a concrete role in the foundation of the group.

## Bibliography

Amin, Ash. *Land of Strangers*. Cambridge, UK-CAM: Polity, 2012.

Art & Architecture Thesaurus. "Roles." *Art & Architecture Thesaurus Online Full Record Display*. September 27, 2019. [http://www.getty.edu/vow/AATFullDisplay?find=role&logic=AND&note=&english=N&prev_page=1&subjectid=300435108](http://www.getty.edu/vow/AATFullDisplay?find=role&logic=AND&note=&english=N&prev_page=1&subjectid=300435108).

Bruseker, George, and Nicola Carboni. *Digital Object Reference Data Model (SARI Documentation)*. Swiss Art Research Infrastructure, December 8, 2020. [https://docs.swissartresearch.net/et/do/](https://docs.swissartresearch.net/et/do/).

Canada Council for the Arts. "Governor General’s Literary Awards." Canada Council for the Arts. n.d. [https://canadacouncil.ca/funding/prizes/governor-generals-literary-awards](https://canadacouncil.ca/funding/prizes/governor-generals-literary-awards).

Canada Council for the Arts. "Past GGBooks Winners and Finalists." Governor General’s Literary Awards. n.d. [https://ggbooks.ca/past-winners-and-finalists](https://ggbooks.ca/past-winners-and-finalists).

Doerr, Martin, and Christian Emil Ore, eds. *Definition of the CIDOC Conceptual Reference Model*. CIDOC CRM Documentations, 7.0.1. Paris, FR-IDF: International Council of Museums (ICOM), 2020. [http://www.cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.0.1_%2018-10-2020.pdf](http://www.cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.0.1_%2018-10-2020.pdf).

Epstein, Brian. "Social Ontology." *The Stanford Encyclopedia of Philosophy*, edited by Edward N. Zalta. Standford, US-CA: Metaphysics Research Lab, Stanford University, 2018. [https://plato.stanford.edu/archives/sum2018/entries/social-ontology/](https://plato.stanford.edu/archives/sum2018/entries/social-ontology/).

Free Dictionary. "Role." *The Free Dictionary*. Huntington Valley, US-PA: Farlex, 2019a. [https://www.thefreedictionary.com/role](https://www.thefreedictionary.com/role).

–––. "Member." *The Free Dictionary*. Huntington Valley, US-PA: Farlex, 2019b. [https://www.thefreedictionary.com/member](https://www.thefreedictionary.com/member).

–––. "Membership." *The Free Dictionary*. Huntington Valley, US-PA: Farlex, 2019c. [https://www.thefreedictionary.com/membership](https://www.thefreedictionary.com/membership).

Halse, Christine. "Theories and Theorising of Belonging." *Interrogating Belonging for Young People in Schools*, edited by Christine Halse. Intercultural Relations in Education. London, UK-LDN: Palgrave Macmillan, 2018. [https://doi.org/10.1007/978-3-319-75217-4_1](https://doi.org/10.1007/978-3-319-75217-4_1).

Hillmer, Norman. "Roland Michener." *The Canadian Encyclopedia*. Toronto, CA-ON: Historica Canada, 2018 [2008]. [https://www.thecanadianencyclopedia.ca/en/article/daniel-roland-michener](https://www.thecanadianencyclopedia.ca/en/article/daniel-roland-michener).

Linked.art. *Linked Art Data Model*. Linked.art, 2021. [https://linked.art/model/index.html](https://linked.art/model/index.html).

Skidmore, Colleen. "Yousuf Karsh." *The Canadian Encyclopedia*. Toronto, CA-ON: Historica Canada, 2015 [2010]. [https://www.thecanadianencyclopedia.ca/en/article/yousuf-karsh](https://www.thecanadianencyclopedia.ca/en/article/yousuf-karsh).

Toronto Public Library. "February 20: Remembering A. J. Casson and the Group of Seven." *Toronto Public Library Snapshots in History* (blog). February 20, 2016. [https://torontopubliclibrary.typepad.com/arts_culture/2016/02/snapshots-in-history-february-20-remembering-a-j-casson-and-the-group-of-seven.html](https://torontopubliclibrary.typepad.com/arts_culture/2016/02/snapshots-in-history-february-20-remembering-a-j-casson-and-the-group-of-seven.html).

Varley, Christopher. "Contemporary Arts Society." *The Canadian Encyclopedia*. Toronto, CA-ON: Historica Canada, 2015 [2006]. [https://www.thecanadianencyclopedia.ca/en/article/contemporary-arts-society](https://www.thecanadianencyclopedia.ca/en/article/contemporary-arts-society).

Wikipedia. "Organizational Founder." *Wikipedia*. San Francisco, US-CA: Wikipedia, 2019a. [https://en.wikipedia.org/w/index.php?title=Organizational_founder&oldid=906165130](https://en.wikipedia.org/w/index.php?title=Organizational_founder&oldid=906165130).

–––. "Role." *Wikipedia*. San Francisco, US-CA: Wikipedia, 2019b. [https://en.wikipedia.org/w/index.php?title=Role&oldid=913886933](https://en.wikipedia.org/w/index.php?title=Role&oldid=913886933).

–––. "Peer Group." *Wikipedia*. San Francisco, US-CA: Wikipedia, 2019c. [https://en.wikipedia.org/w/index.php?title=Peer_group&oldid=917584897](https://en.wikipedia.org/w/index.php?title=Peer_group&oldid=917584897).

–––. "Social Movement." *Wikipedia*. San Francisco, US-CA: Wikipedia, 2019d. [https://en.wikipedia.org/w/index.php?title=Social_movement&oldid=917693866](https://en.wikipedia.org/w/index.php?title=Social_movement&oldid=917693866).

–––. "Organization." *Wikipedia*. San Francisco, US-CA: Wikipedia, 2019e. [https://en.wikipedia.org/w/index.php?title=Organization&oldid=918006362](https://en.wikipedia.org/w/index.php?title=Organization&oldid=918006362).

–––. "Resolute Forest Products." *Wikipedia*. San Francisco, US-CA: Wikipedia, 2021. [https://en.wikipedia.org/w/index.php?title=Resolute_Forest_Products&oldid=1032134351](https://en.wikipedia.org/w/index.php?title=Resolute_Forest_Products&oldid=1032134351).

Wright, Sarah. "More-Than-Human, Emergent Belongings: A Weak Theory Approach." *Progress in Human Geography* 39, no. 4 (2015): 391–411. [https://doi.org/10.1177/0309132514537132](https://doi.org/10.1177/0309132514537132).

