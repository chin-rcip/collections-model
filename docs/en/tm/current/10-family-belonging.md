---
layout: page
language: en
title: Family Belonging
permalink: /en/target-model/current/family-belonging
other_link: /fr/modele-cible/actuel/appartenance-familiale
sidebar: tm22
date: 2022-03-31
description: The Actors Target Model Specification semantically models actors in a heritage context. Patterns most relevant to actors' lives are presented along with diagrams and examples illustrating them, as well as a record and explanation of relevant decisions that were made when developing said patterns. This is a theoretical documentation that has never been tested or implemented.
---

Version 2.2 ([Previous versions](/collections-model/en/versions))

## At Glance

This pattern can be used to document the belonging of an individual to a family. It includes: 

* The appellation of the family (usually the family name);
* The dates of the joining (usually by birth or adoption) or leaving (usually by divorce or death) of the family.

It pertains specifically to the belonging to a family, and not to:

* A family branch belonging to a main family branch;
* The description of relationships among family members or different individuals (i.e. their role, for this specific case use the [Relationship](/collections-model/en/target-model/current/relationship) pattern instead);
* The belonging to other kinds of groups (use the [Group Belonging](/collections-model/en/target-model/current/group-belonging) pattern instead).

## Introduction and Context

### Theoretical Background

The concept of "family" can vary temporally and socially as different practices and beliefs can coexist or be opposed, either from one family to another or among cultures. The definition of family is therefore manifold as well as subject to change.

It is important to differentiate the concept of family from that of household. Contrary to households which are determined by the geographical location of actors, families are determined by the relationships between actors (Allan 2007, 1619). Moreover, people sharing a household don’t necessarily belong to the same family.

Even within the concept of family, there is often an informal distinction between different variations, for example the nuclear family and the extended family. It is generally accepted that the nuclear family is composed of parents and their children, while the extended family includes other individuals spanning more than two generations and linked through filiation or alliance (Bruce & Yearley 2006).

However, nuclear and extended conceptions of the family are not universal. In some societies, the nuclear family is not composed solely of parents and their children but includes other kins (Boudon & Bourricaud 2003, 170-171) while in others, the distinction between household, nuclear family, and extended family is not meaningful. For example, roman society had three different conceptions of family that coexisted and overlapped (Parkin & Pomeroy 2007, 72-73; Saller 1986; Smith 2006, 15-16): 

* *familia*, which included the *pater familias*, his wife, his children, and his slaves; 
* *domus*, which included the physical house itself in addition to the *familia*, but also referred to individuals outside of the household such as close friends; 
* *gens*, which referred to individuals sharing the same *nomen* or family name, stemming exclusively from the male line so that the *gens* included multiple families whose members were not sharing the same *gens*.

This example illustrates how the prevalent understanding of family is not entirely applicable to every society and might be misleading when used in a historical context as it cannot fully encompass changing ideas and conceptions of the family unit across cultures. 

### Statement of Need

In some heritage domains that focus on human relationships, such as genealogy, sociology, social history, etc., it is beneficial to identify the belonging of an individual to a specific family, especially when the family is particularly preeminent (e.g. the Julii in Roman Antiquity or the Medici in Renaissance Italy), or for specific research questions (e.g. onomastic or demographic research). Moreover, in some cultures, family as a concept is at the centre of social and/or political life (Bruce & Yearley 2006). 

It is relevant to document families as specific entities so that they can be described and linked to individuals belonging to them. Such a pattern enables the linking of individuals to families even when the specific nature of their relationship to the family remains unknown. In addition to relationships, family data is valuable for social network analysis.

## Description of the Pattern

As stated in the CIDOC CRM ontology, families are regarded as particular examples of the class `E74_Group` (Bekiari et al. 2021, 44-45). Therefore, it is appropriate to consider individuals as members of a family group, and joining and leaving events can help document the moment a person enters and leaves this same family. 

Accordingly, an instance of `E74_Group` is first linked to an instance of `E55_Type` (a specified qualifier node) labelled "Family" through the property `P2_has_type` in order to differentiate families from other kinds of instances of `E74_Group` in the knowledge graph.

The instance of `E74_Group` is then linked to an instance of both `E41_Appellation` and `E33_Linguistic_Object` by the property `P1_is_identified_by` which renders the literal value of the [Family Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#family-appellation) by the property `P190_has_symbolic_content`.

The central unit of the joining part of the pattern represents the main actor (an instance of `E21_Person`) entering the family (an instance of `E85_Joining`) through the property `P143i_was_joined_by`. This instance of `E85_Joining` points to the family group it relates to (an instance of `E74_Group`) through the property `P144_joined_with`. 

The central unit of the leaving part of the pattern represents the main actor (an instance of `E21_Person`) leaving the family (an instance of `E86_Leaving`) through the property `P145i_left_by`. This instance of `E86_Leaving` points to the family group it relates to (an instance of `E74_Group`) through the property `P146_separated_from`.

Each event is linked to its respective instance of `E52_Time-Span` by the property `P4_has_time-span` in order to document the moment the individual joined and left the family (see the [Temporal Bounds](/collections-model/en/target-model/current/temporal-bounds) pattern) with values extracted from the [Family Joining Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#family-joining-date-begin), [Family Joining Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#family-joining-date-begin-qualifier), [Family Joining Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#family-joining-date-end), [Family Joining Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#family-joining-date-end-qualifier), [Family Leaving Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#family-leaving-date-begin), [Family Leaving Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#family-leaving-date-begin-qualifier), [Family Leaving Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#family-leaving-date-end), and [Family Leaving Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#family-leaving-date-end-qualifier) entry nodes. 

## Diagram

<a name="098_Pattern_Identity_Family_p"></a>098_Pattern_Identity_Family_p

<div class="mxgraph" style="max-width:100%;border:1px solid #cccccc;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;target&quot;:&quot;blank&quot;,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom layers lightbox&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;xml&quot;:&quot;&lt;mxfile host=\&quot;app.diagrams.net\&quot; modified=\&quot;2023-03-15T17:12:33.231Z\&quot; agent=\&quot;5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) draw.io/20.3.0 Chrome/104.0.5112.114 Electron/20.1.3 Safari/537.36\&quot; etag=\&quot;WF74B9FBRrJJTmr9K-it\&quot; version=\&quot;20.3.0\&quot;&gt;&lt;diagram id=\&quot;M10G-2mTQvHYUXy7SPrL\&quot; name=\&quot;Page-1\&quot;&gt;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&lt;/diagram&gt;&lt;/mxfile&gt;&quot;}"></div>

## Examples

### Example 1

Yousuf Karsh became a member of the Karsh (`P190_has_symbolic_content`, Family Appellation) family by birth on 1908-12-23 (`P82a_begin_of_the_begin`, Family Joining Date Begin; `P82b_end_of_the_end`, Family Joining Date End) and left the family by death on 2002-07-13 (`P82a_begin_of_the_begin`, Family Leaving Date Begin; `P82b_end_of_the_end`, Family Leaving Date End).

<div id="0001_100_family-belonging" class="example"></div>

### Example 2

In 1981 (`P82a_begin_of_the_begin`, Family Joining Date Begin; `P82b_end_of_the_end`, Family Joining Date End), Lady Diana Spencer joined the British royal (`P190_has_symbolic_content`, Family Appellation) family by marrying Charles, Prince of Wales; she can be considered to have left the family through divorce in 1996 (`P82a_begin_of_the_begin`, Family Leaving Date Begin; `P82b_end_of_the_end`, Family Leaving Date End).

<div id="0001_122_family-belonging" class="example"></div>

## Related Documentation

### External Models

* SARI: [Person Reference Data Model – Social Relations](https://docs.swissartresearch.net/et/persons/#social-relations)

### Entry Nodes

* [Family Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#family-appellation) \| Checklist
* [Family Joining Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#family-joining-date-begin) \| Checklist
* [Family Joining Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#family-joining-date-begin-qualifier) \| Checklist
* [Family Joining Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#family-joining-date-end) \| Checklist
* [Family Joining Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#family-joining-date-end-qualifier) \| Checklist
* [Family Leaving Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#family-leaving-date-begin) \| Checklist
* [Family Leaving Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#family-leaving-date-begin-qualifier) \| Checklist
* [Family Leaving Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#family-leaving-date-end) \| Checklist
* [Family Leaving Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#family-leaving-date-end-qualifier) \| Checklist

### CIDOC CRM Entities

* `E39_Actor` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E39)]
* `E52_Time-Span` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E52)]
* `E55_Type` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E55)]
* `E74_Group` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E74)]
* `E85_Joining` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E85)]
* `E86_Leaving` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E86)]
* `P2_has_type (is_type_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P2)]
* `P4_has_time-span (is_time-span_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P4)]
* `P79_beginning_is_qualified_by` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P79)]
* `P80_end_is_qualified_by` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P80)]
* `P82a_begin_of_the_begin`
* `P82b_end_of_the_end`
* `P143_joined (was_joined_by)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P143)]
* `P144_joined_with (gained_member_by)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P144)]
* `P145_separated (left_by)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P145)]
* `P146_separated_from (lost_member_by)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P146)]
* `P190_has_symbolic_content` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P190)]

## Discussion

### Rationale

The modelling of the family as an instance of `E74_Group` respects the constraints of CIDOC CRM’s scope note which is limited to the gathering of human individuals that can act collectively on behalf of the relationship that unites them (Bekiari et al. 2021, 44-45).

For the moment, the role of a person within a family has not been included in this pattern but in the [Group Belonging](/collections-model/en/target-model/current/group-belonging) pattern instead because familial roles, like a family unit itself, are fluctuating as a family is subjected to events that affect its dynamics. Because the property `P144.1_kind_of_member` is of an invariable nature, it would be misleading to use it for this pattern. As such, familial roles should be documented using the [Relationship](/collections-model/en/target-model/current/relationship) pattern or the [Group Belonging](/collections-model/en/target-model/current/group-belonging) pattern. This absence of a person’s role within a family is what differentiates this pattern from the Group Belonging one.

### Limitations

As stated in the Theoretical Background, the "family" concept encompasses different meanings across time and cultures. What members a family comprises can vary greatly, ranging from a rather small unit limited to parents and their children, to larger structures including several other units or individuals at the service of a primary unit. Handling such variability is in large part dependent on the use of controlled vocabularies. Two options are possible:

* Always use a broad definition of family so that all concepts akin to it are encompassed by a single term (e.g. *gens*, *familia*, and *domus* would all be categorized as family, and the preciseness of such terms would be collapsed under the usefulness of the broader family);
* Use precise terms (either developed or reused) in order to distinguish different understandings of a larger overarching concept (e.g. *gens*, *familia*, and *domus* would all be treated as concepts in and of themselves but would often not be linked to other homologous family concepts because of the complexity inherent in identifying and handling equivalencies and hierarchies in a wide array of definitions, and subsequently in mapping and querying data). 

For the time being, because it is more straightforwardly implementable, the first option has been selected. 

### Related GitHub Issues

* [Issue #16 "Do we need a family relationship pattern? And what to do with parents?"](https://github.com/chin-rcip/collections-model/issues/16)
* [Issue #57 "What fields do we need to manage the identity of an actor?"](https://github.com/chin-rcip/collections-model/issues/57)

### Edge Cases

#### Example 1 {#edge-cases-example-1}

The scope of the class `E74_Group` dictates that a family is a gathering of individuals that can act collectively (Bekiari et al. 2021, 44-45). However, other groups, either formal or informal, could be considered as comparable to a family (e.g. when individuals raise a child that is not formally adopted, or a group of very close friends). Whether or not such groups should be documented using the Family Belonging pattern or the Group Belonging pattern is determined by the cataloguer or data expert as the distinction between these two patterns can be blurry.

#### Example 2 {#edge-cases-example-2}

It could be argued that a person’s role within a family could remain the same no matter the current members of the family. For instance, an adopted child could be documented as bearing the role "Adopted" with the whole family group. In such a case, it would imply the use of the Group Belonging pattern and the addition of the family type to the group.

## Bibliography

Allan, Graham. "Family Structure." *The Blackwell Encyclopedia of Sociology*, edited by George Ritzer. Malden, USA; Oxford, UK-OXF; Carlton, AUS-VIC: Blackwell Publishing, 2007: 1618-1621.

Bekiari, Chryssoula, George Bruseker, Martin Doerr, Christian-Emil Ore, Stephen Stead, and Athanasios Velios, eds. *Definition of the CIDOC Conceptual Reference Model*. CIDOC CRM Documentations, 7.1. Paris, FR-IDF: CIDOC CRM Special Interest Group, 2021. [http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf](http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf).

Boudon, Raymond, and François Bourricaud. "Family." *A Critical Dictionary of Sociology*, translated by Peter Hamilton. UK-LDN: Routledge, 1999: 169-176.

Bruce, Steve, and Steven Yearly. "Family." *The SAGE Dictionary of Sociology*. UK-LDN: SAGE Publication Ltd., 2006: 103-104.

Parkin, Tim G., and Arthur J. Pomeroy. *Roman Social History. A Sourcebook*. Abingdon, US-NY: Routledge, Taylor & Francis Group, 2007.

Saller, Richard P. "'Familia, Domus', and the Roman Conception of Family." *Phoenix* 38, no. 4 (1984): 336-355.

Smith, C. J. *The Roman Clan: The Gens from Ancient Ideology to Modern Anthropology*. Cambridge, UK-CAM: Cambridge University Press, 2006.

