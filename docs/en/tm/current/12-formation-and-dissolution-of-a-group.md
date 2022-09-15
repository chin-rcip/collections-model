---
layout: page
language: en
title: Formation and Dissolution of a Group
permalink: /en/target-model/current/formation-and-dissolution-of-a-group
other_link: /fr/modele-cible/actuel/formation-et-dissolution-dun-groupe
sidebar: tm22
date: 2022-03-31
description: The Actors Target Model Specification semantically models actors in a heritage context. Patterns most relevant to actors' lives are presented along with diagrams and examples illustrating them, as well as a record and explanation of relevant decisions that were made when developing said patterns. This is a theoretical documentation that has never been tested or implemented.
---

Version 2.2 ([Previous versions](/collections-model/en/versions))

## At Glance

This pattern can be used to represent the information pertaining to the beginning and ending of a group of persons (formation and dissolution). It includes: 

* The date and location of the formation of a group (its beginning);
* The actor·s mainly responsible for the formation of a group; 
* The date and location of the dissolution of a group (its ending); 
* The actor·s mainly responsible for the ending of a group.

It pertains specifically to the vital information of groups and not to their nature, their networks, or the vital information of the persons that comprise them (e.g. founding actor’s birth date, legal statute authorizing the creation of a group, etc.). As such, it does not include: 

* The formation or dissolution of groups of objects (such as collections);
* The nature of a group;
* The belonging of a member to a group (use the [Group Belonging](/collections-model/en/target-model/current/group-belonging) pattern instead);
* The name, date, and location of the birth or death of the members of a group (use the [Actor Identifiers and Appellations](/collections-model/en/target-model/current/actor-identifiers-and-appellations) and the [Birth and Death of a Person](/collections-model/en/target-model/current/birth-and-death) patterns instead);
* The relationships between members of a group, or between a group to other groups of persons (use the [Relationship](/collections-model/en/target-model/current/relationship) pattern instead);
* The roles endorsed by the members of a group, apart from founding and dissolving roles which are accounted for in this pattern;
* The cause of the formation or dissolution of a group.

## Introduction and Context

### Theoretical Background

The recording of information pertaining to the formation and dissolution of groups is a statistically and culturally important part of heritage research and relies on groups either self-identifying or being identified later on by experts. As such, this information is often used to situate actors within larger societal trends as a key element of historical research (Yntema 2009, 145; Brumberg et al. 2012, 407). 

Such information is not only meaningful, but also crucial to the disambiguation of actors (i.e. two different groups might have the same name by happenstance, or a single group might be associated to several names or spellings of a name) as it can be used to confirm a group’s identity (OCLC 2019, 4). 

Data on the formation and dissolution of groups, however, is likely to be very fuzzy and entails expert assessments that might differ greatly in determining who constitutes a group, when it was formed and dissolved, and who was instrumental in forming and dissolving it, or even if a founding or dissolution event even happened. It relies on the perception of the subject matter expert or of the members themselves as having a cohesiveness and a unity as a group that is distinct from that of the individuals that comprise it (Lickel et al. 2000, 223). 

### Statement of Need

Because information about the formation and dissolution of a group is commonly used by heritage institutions as well as relied upon for disambiguation purposes, it is likely to be among the most widely documented. This, in turn, means that such vital data will predictably be among the most subject to exchange and mobilization by several providers. Thus, interoperability with other relevant models is of importance in the development of these patterns. This indicates a need to identify when, where, and by whom a group was formed or dissolved.

## Description of the Pattern

The formation of a group is modelled as follows: 

* An instance of `E74_Group` is linked to an instance of `E66_Formation` by the property `P95_has_formed`. The instance of `E66_Formation` is linked to the group’s founder (an instance of `E39_Actor`) by the property `P14_carried_out_by` which is linked to an instance of both `E41_Appellation` and `E33_Linguistic_Object` by the property `P1_is_identified_by`. This instance is then linked to the literal value of the [Founding Actor Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#founding-actor-appellation) through the property `P190_has_symbolic_content`;
* The place where the formation occurred is indicated by linking the instance of `E66_Formation` to the [Formation Place](/collections-model/en/semantic-paths-specification/current/entry-nodes#formation-place) value (an instance of `E53_Place`) value mobilized through the property `P7_took_place_at`;
* The time when the formation occurred is indicated by using the [Temporal Bounds](/collections-model/en/target-model/current/temporal-bounds) pattern linked to the instance of `E66_Formation` through the property `P4_has_time-span` with values extracted from the [Formation Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#formation-date-begin), [Formation Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#formation-date-begin-qualifier), [Formation Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#formation-date-end), and [Formation Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#formation-date-end-qualifier) entry nodes. 

The dissolution of a group is modelled as follows: 

* An instance of `E74_Group` is linked to an instance of `E68_Dissolution` by the property `P99_dissolved`. The instance of `E68_Dissolution` is linked to the group’s actor responsible for the dissolution (an instance of `E39_Actor`) using the property `P14_carried_out_by` which is linked to an instance of both `E41_Appellation` and `E33_Linguistic_Object` by the property `P1_is_identified_by`. From this instance, the literal value of the [Dissolving Actor Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#dissolving-actor-appellation) is qualified through the property `P190_has_symbolic_content`;
* The place where the dissolution occurred is indicated by linking the instance of `E68_Dissolution` to the [Dissolution Place](/collections-model/en/semantic-paths-specification/current/entry-nodes#dissolution-place) value (an instance of `E53_Place`) through the property `P7_took_place_at`;
* The time when the dissolution occurred is indicated using the [Temporal Bounds](/collections-model/en/target-model/current/temporal-bounds) pattern linked to the instance of `E68_Dissolution` through the property `P4_has_time-span` extracted from the [Dissolution Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#dissolution-date-begin), [Dissolution Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#dissolution-date-begin-qualifier), [Dissolution Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#dissolution-date-end), and [Dissolution Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#dissolution-date-end-qualifier) entry nodes. 

## Diagram

<a name="042_Pattern_GroupFormationDissolution_p"></a>042_Pattern_GroupFormationDissolution_p

<iframe frameborder="0" style="width:100%;height:500px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=042_Pattern_GroupFormationDissolution_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1mJslFryfSj3ddEj9DNzPIMn8lIvV7LeP%26export%3Ddownload"></iframe>

## Examples

### Example 1

Yousuf Karsh is a Companion of the Order of Canada (`P190_has_symbolic_content`, Actor Appellation) which was established on the 1st of July 1967 (`P82a_begin_of_the_begin`, Formation Date Begin; `P82b_end_of_the_end`, Formation Date End) by then Governor General Roland Michener (`P190_has_symbolic_content`, Founding Actor Appellation) in Ottawa (ON, Canada) (`P7_took_place_at`, Formation Place) (Hillmer 2018; Skidmore 2015). 

<div id="0001_110_formation" class="example"></div>

### Example 2

The Canadian Group of Painters (`P190_has_symbolic_content`, Actor Appellation) was formed in Toronto (ON, Canada) (`P7_took_place_at`, Formation Place) in 1933 (`P82a_begin_of_the_begin`, Formation Date Begin; `P82b_end_of_the_end`, Formation Date End) by 28 canadian artists, among which A. J. Casson (`P190_has_symbolic_content`, Founding Actor Appellation) (depicted alone in the following example for simplicity purposes). It was dissolved in 1969 (`P82a_begin_of_the_begin`, Dissolution Date Begin; `P82b_end_of_the_end`, Dissolution Date End) at an unknown place by an unknown actor (Toronto Public Library 2016).

<div id="0001_112_formation-dissolution" class="example"></div>

## Related Documentation

### External Models

* Linked.art: [Birth and Death/Formation and Dissolution](https://linked.art/model/actor/#birth-and-death-formation-and-dissolution)
* SARI: [Group Reference Data Model – Existence](https://docs.swissartresearch.net/et/group/#existence)

### Entry Nodes

* [Formation Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#formation-date-begin) \| Checklist
* [Formation Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#formation-date-begin-qualifier) \| Checklist
* [Formation Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#formation-date-end) \| Checklist
* [Formation Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#formation-date-end-qualifier) \| Checklist
* [Formation Place](/collections-model/en/semantic-paths-specification/current/entry-nodes#formation-place) \| Checklist
* [Founding Actor Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#founding-actor-appellation) \| Checklist
* [Dissolution Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#dissolution-date-begin) \| Checklist
* [Dissolution Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#dissolution-date-begin-qualifier) \| Checklist
* [Dissolution Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#dissolution-date-end) \| Checklist
* [Dissolution Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#dissolution-date-end-qualifier) \| Checklist
* [Dissolution Place](/collections-model/en/semantic-paths-specification/current/entry-nodes#dissolution-place) \| Checklist
* [Dissolving Actor Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#dissolving-actor-appellation) \| Checklist

### CIDOC CRM Entities

* `E9_Move` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E9)]
* `E39_Actor` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E39)]
* `E41_Appellation` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E41)]
* `E52_Time-Span` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E52)]
* `E53_Place` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E53)]
* `E66_Formation` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E66)]
* `E68_Dissolution` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E68)]
* `E74_Group` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E74)]
* `P1_is_identified_by (identifies)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P1)]
* `P4_has_time-span (is_time-span_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P4)]
* `P7_took_place_at (witnessed)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P7)]
* `P14_carried_out_by (performed)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P14)]

`P79_beginning_is_qualified_by` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P79)]

* `P80_end_is_qualified_by` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P80)]
* `P82a_begin_of_the_begin`
* `P82b_end_of_the_end`
* `P95_has_formed (was_formed_by)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P95)]
* `P99_dissolved (was_dissolved_by)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P99)]
* `P190_has_symbolic_content` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P190)]

## Discussion

### Rationale

There is a substantive difference between belonging to a group and being an active founder or dissolver of that group. This is why founding and dissolving actor·s information is embedded in this pattern rather than in the [Group Belonging](/collections-model/en/target-model/current/group-belonging) one. Hence, only founding and/or dissolving instances of `E39_Actor` should be represented in this pattern knowing that, occasionally, founding actors might not be active members of a group.

In addition, what qualifies as a group and should be recorded as such can be subject to debate (see the [Differences Between `E39_Actor`, `E21_Person`, and `E74_Group`](/collections-model/en/target-model/current/general-concepts#differences-between-e39_actor-e21_person-and-e74_group) section). This pattern exclusively concerns groups of persons and does not pertain to groups of objects such as collections or other heritage holdings. However, it might be difficult to determine whether certain groupings should be mapped to this pattern. For example, an art movement might be considered a group and modelled as such, but it can also be considered an interpretation of an ensemble of works by specialists (see [Issue #21](https://github.com/chin-rcip/collections-model/issues/21)). 

At the moment, even when a group can easily be ascertained as such, for example in the case of the Order of Canada, it remains undetermined, whether its members leave the group upon its dissolution or persist as members of that group (see [Issue #36](https://github.com/chin-rcip/collections-model/issues/36)). 

### Limitations

The best way to record the existence and evolution of less formalized groups which exist but do not have recorded members, or only have a fraction of their members knowingly and officially recorded as such, is also a challenge. For example, movements such as [Black Lives Matter](https://blacklivesmatter.com/), the [Sunrise Movement](https://www.sunrisemovement.org/), the [Occupy Movement](http://occupywallst.org/), or other activist groups are notoriously decentralized and encompass a wide range of people who espouse their values and affiliate with them without having a formal membership or being donors. People who are part of such movements are often anonymous for personal or systemic reasons (e.g. Sunrise is a youth-led movement that makes financial and official involvement more complicated for teenagers if they do not have the support of their parents). Leaders can be documented, but establishing official founders can in some cases be difficult, even more so for people who affiliate with a movement and are activists but do not hold a formally or informally recognized position with regards to the movement. Currently, because the scope note of the class `E74_Group` only includes formal groups that act collectively, those informal groups and the members associated with them are not addressed by this pattern, nor are they addressed by the [Group Belonging](/collections-model/en/target-model/current/group-belonging) pattern. 

### Related GitHub Issues

* [Issue #11 "Should the school years be model[l]ed as being a member of a group? Would it be the same for professors?"](https://github.com/chin-rcip/collections-model/issues/11)
* [Issue #21 "How to model [an] Artistic Movement?"](https://github.com/chin-rcip/collections-model/issues/21)
* [Issue #36 "Does the dissolution of a group implies the leaving of its members?"](https://github.com/chin-rcip/collections-model/issues/36)

### Edge Cases

#### Example 1 {#edge-cases-example-1}

In 2008 (Formation Date Begin; Formation Date End), Yousuf Karsh’s wife, Estrellita Karsh (Founding Actor Appellation), endowed the Estrellita and Yousuf Karsh Assistant Curator of Photographs (Actor Appellation) position at the Museum of Fine Arts (Founding Actor Appellation) in Boston (MA, United States) (Formation Place). The curators that endorsed that position formed a group by the name "Estrellita and Yousuf Karsh Assistant Curator of Photographs" which is also an occupation they have all held (using the Occupation pattern would be possible, but the group would never be "created"). The endowment is ongoing and, as such, the group remains active (Estate of Yousuf Karsh 2021). Yet, an important question remains: can the members of the group (i.e. the curators) act collectively (thus qualifying as a group) even if only one of them endorses the title at once? In this context, how to treat the group remains unclear. 

#### Example 2 {#edge-cases-example-2}

The Abitibi Power and Paper Company was acquired by Price Brothers in 1974. Price Brothers was then merged with Stone Consolidated in 1997 which was in turn merged with Bowater to form AbitibiBowater in 2007, now known under Resolute Forest Products (Wikipedia 2021). In the case of such mergers and acquisitions, what would be considered to be the dissolution of the company is unclear.

#### Example 3 {#edge-cases-example-3}

A group might not have a single Formation Place as its members can consider themselves part of a collective without sharing a common space. Also, when an event takes place online or in a virtual universe, it could become difficult to determine its physical location. For example, an artist might found a purely online group from a computer in Winnipeg yet use a gathering platform accessible on a web server that could also be considered as the location of the formation of the group. The location of each member can similarly be problematic (e.g. each participating player’s physical location in an online game).

## Bibliography

Black Lives Matter. *Black Lives Matter*. Black Lives Matter, June 28, 2021. [https://blacklivesmatter.com/](https://blacklivesmatter.com/).

Brumberg, H. L., D. Dozor, and S. G. Golombek. "History of the Birth Certificate: From Inception to the Future of Electronic Data." *Journal of Perinatology* 32, no. 6 (2012): 407–411. [https://doi.org/10.1038/jp.2012.3](https://doi.org/10.1038/jp.2012.3).

Doerr, Martin, and Christian Emil Ore, eds. *Definition of the CIDOC Conceptual Reference Model*. CIDOC CRM Documentations, 7.0.1. Paris, FR-IDF: International Council of Museums (ICOM), 2020. [http://www.cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.0.1_%2018-10-2020.pdf](http://www.cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.0.1_%2018-10-2020.pdf).

Editors of Encyclopædia Britannica. "Yousuf Karsh." *Encyclopædia Britannica*. London, UK-LND: Encyclopædia Britannica, n.d. [https://www.britannica.com/biography/Yousuf-Karsh](https://www.britannica.com/biography/Yousuf-Karsh).

Estate of Yousuf Karsh. *Yousuf Karsh*. Yousuf Karsh, 2021. [https://karsh.org/](https://karsh.org/).

Hillmer, Norman. "Roland Michener." *The Canadian Encyclopedia*. Toronto, CA-ON: Historica Canada, 2018 [2008]. [https://www.thecanadianencyclopedia.ca/en/article/daniel-roland-michener](https://www.thecanadianencyclopedia.ca/en/article/daniel-roland-michener).

Lickel, B., D. Hamilton, G. Wieczorkowska, A. Lewis, S. Sherman, and A. N. Uhles. "Varieties of Groups and the Perception of Group Entitativity." *Journal of Personality and Social Psychology* 78, no. 2 (2000): 223–246. [https://doi.org/10.1037/0022-3514.78.2.223](https://doi.org/10.1037/0022-3514.78.2.223).

Linked.art. *Linked Art Data Model*. Linked.art, 2021. [https://linked.art/model/index.html](https://linked.art/model/index.html).

OCLC. *Virtual International Authority File Guidelines*. Dublin, US-OH: OCLC, 2019 [2015]. [https://www.oclc.org/content/dam/oclc/viaf/VIAF%20Guidelines.pdf](https://www.oclc.org/content/dam/oclc/viaf/VIAF%20Guidelines.pdf).

Skidmore, Colleen. "Yousuf Karsh." *The Canadian Encyclopedia*. Toronto, CA-ON: Historica Canada, 2015 [2010]. [https://www.thecanadianencyclopedia.ca/en/article/yousuf-karsh](https://www.thecanadianencyclopedia.ca/en/article/yousuf-karsh).

Sunrise Movement. *Sunrise Movement - We Are The Climate Revolution*. Sunrise Movement, June 28, 2021. [https://www.sunrisemovement.org/](https://www.sunrisemovement.org/).

Toronto Public Library. « February 20: Remembering A. J. Casson and the Group of Seven. » *Toronto Public Library Snapshots in History* (blog). February 20, 2016. [https://torontopubliclibrary.typepad.com/arts_culture/2016/02/snapshots-in-history-february-20-remembering-a-j-casson-and-the-group-of-seven.html](https://torontopubliclibrary.typepad.com/arts_culture/2016/02/snapshots-in-history-february-20-remembering-a-j-casson-and-the-group-of-seven.html).

Wikipedia. "Resolute Forest Products." *Wikipedia*. San Francisco, US-CA: Wikipedia, 2021. [https://en.wikipedia.org/w/index.php?title=Resolute_Forest_Products&oldid=1032134351](https://en.wikipedia.org/w/index.php?title=Resolute_Forest_Products&oldid=1032134351).

Yntema, Douwe. "Material Culture and Plural Identity in Early Roman Southern Italy." *Ethnic Constructs in Antiquity: The Role of Power and Tradition*, edited by Ton Derks and Nico Roymans. Amsterdam Archæological Studies 13. Amsterdam, NL: Amsterdam University Press, 2009: 145–166. [https://www.jstor.org/stable/j.ctt46n1n2.9](https://www.jstor.org/stable/j.ctt46n1n2.9).

