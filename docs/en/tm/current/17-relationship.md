---
layout: page
language: en
title: Relationship
permalink: /en/target-model/current/relationship
other_link: /fr/modele-cible/actuel/relation
sidebar: tm22
date: 2022-03-31
description: The Actors Target Model Specification semantically models actors in a heritage context. Patterns most relevant to actors' lives are presented along with diagrams and examples illustrating them, as well as a record and explanation of relevant decisions that were made when developing said patterns. This is a theoretical documentation that has never been tested or implemented.
---

Version 2.2 ([Previous versions](/collections-model/en/versions))

## At Glance

This pattern can be used to represent the information pertaining to the relationship (i.e. association or acquaintance) between two actors. It includes: 

* The type of the relationship;
* The appellations of the related actors;
* The time during which the actors associated with each other;
* The roles that each actor assumed within the relationship.

This pattern should not be used to represent:

* The participation/joining of an actor in a group (use the [Group Belonging](/collections-model/en/target-model/current/group-belonging) pattern instead);
* The belonging of an individual to a family (use the [Family Belonging](/collections-model/en/target-model/current/family-belonging) pattern instead);
* The parents-child relationship under a biological perspective (use the [Birth and Death of a Person](/collections-model/en/target-model/current/birth-and-death) pattern instead).

## Introduction and Context

### Theoretical Background

Since birth, a person’s life experience is predominantly shaped by their interpersonal relationships, namely their associations, connections, and interactions with others. A relationship is characterized by several dimensions such as degree of intimacy, duration, reciprocity, power distribution, frequency, spatiality, and regulation (Rashid and Blanco 2017). 

Also, interpersonal relationships are viewed as "dynamic systems that can change continuously throughout their existence" (Wikipedia 2019). They have a lifespan with a beginning and an end. Throughout their lifespan, each actor in a relationship assumes a role that can be changed according to the shifts in the relationship’s dimensions, with the exception of roles in familial relationships. For example, if due to various factors and circumstances, two actors who were friends have become enemies, the nature of their relationship and their roles have changed.

### Statement of Need

One of the most important aspects of an actor’s life is their association with other people and groups, whether it is family, friends, or other consequential relationships. Linking actors with one another helps to build a virtual network that allows serendipitous discovery and research in different fields such as genealogy, sociology, etc. Therefore, it is crucial to model those relationships in a precise, meaningful, and flexible manner.

Two elements of a relationship should be captured: its type and the roles each actor played, as an actor can have multiple relationships with various actors as well as with a single actor, and hold a specific role in each relationship. For example, to Yousuf Karsh, George Nakash was an uncle in the context of their familial relationship, but he was also his employer in the context of their professional relationship. 

In addition, a relationship has a start and an end date that are often determined by external factors, and this temporality is often necessary to disambiguation and data gathering on actors.

## Description of Pattern

For each relationship, an instance of `E39_Actor` is first linked to an instance of `PC14_carried_out_by` (representing the actor in a role) by the property `P02_has_range`. The instance of `PC14_carried_out_by` is then linked to an instance of `E7_Activity` by the property `P01_has_domain`. 

From the first instance of `PC14_carried_out_by`, the [Relationship Actor Role](/collections-model/en/semantic-paths-specification/current/entry-nodes#relationship-actor-role) value (an instance of `E55_Type`) is rendered by the property `P14.1_in_the_role_of`.

Similarly, the [Related Actor Role](/collections-model/en/semantic-paths-specification/current/entry-nodes#related-actor-role) value (an instance of `E55_Type`) is rendered from the second instance of `PC14_carried_out_by` by the property `P14.1_in_the_role_of`. The instance of `E39_Actor` identifying the related actor is linked to an instance of both `E41_Appellation` and `E33_Linguistic_Object` through the property `P1_is_identified_by`. From this instance, the literal value of the [Related Actor Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#related-actor-appellation) is rendered by the property `P190_has_symbolic_content`.

The duration of the relationship activity is indicated using the [Temporal Bounds](/collections-model/en/target-model/current/temporal-bounds) pattern linked to the instance of `E7_Activity` by the property `P4_has_time-span` with values extracted from the [Relationship Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#relationship-date-begin), [Relationship Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#relationship-date-begin-qualifier), [Relationship Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#relationship-date-end), and [Relationship Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#relationship-date-end-qualifier) entry nodes. 

In addition, the activity is qualified by the [Relationship Type](/collections-model/en/semantic-paths-specification/current/entry-nodes#relationship-type) value (an instance of `E55_Type`) through the property `P2_has_type`. This instance of `E55_Type` is further qualified by an instance of `E55_Type` (a specified qualifier node) labelled "Relationship" through the property `P2_has_type`.

## Diagram

<a name="056_Pattern_Relationship_p"></a>056_Pattern_Relationship_p

<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=056_Pattern_Relationship_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1j_CpqlOBaLRUp0aQ_XHbwQEW0SbPGJaW%26export%3Ddownload"></iframe>

## Examples

Armenian-Canadian photographer Yousuf Karsh was married (`P2_has_type`, Relationship Type "Marriage") to Solange Gauthier (`P190_has_symbolic_content`, Related Actor Appellation) from 1939 (`P82a_begin_of_the_begin`, Relationship Date Begin) to 1961 (`P82b_end_of_the_end`, Relationship Date End). Both had the role "Spouse" (`P14.1_in_the_role_of`, Relationship Actor Role) in the relationship (Wikipedia 2021).

<div id="0001_100_relationship" class="example"></div>

## Related Documentation

### External Models

* CRMbio: [Relationship Classes and Properties](http://ldf.fi/schema/bioc/)
* SARI: [Person Reference Data Model – Social Relations](https://docs.swissartresearch.net/et/persons/#social-relations)
* AgRelOn: [Relationship Classes and Properties](https://d-nb.info/standards/elementset/agrelon)
* ULAN: [Relationship Properties](http://vocab.getty.edu/ontology)
* Wikidata: ["significant person" (P3342)](https://www.wikidata.org/wiki/Property:P3342) and the majority of its [sub-properties](https://w.wiki/3nYP); [Properties for Human Relationships](https://w.wiki/3nYf); ["object has role" (P3831)](https://www.wikidata.org/wiki/Property:P3831) and its [sub-properties](https://w.wiki/3nYh).

### Entry Nodes

* [Related Actor Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#related-actor-appellation) \| Checklist
* [Related Actor Role](/collections-model/en/semantic-paths-specification/current/entry-nodes#related-actor-role) \| Checklist
* [Relationship Actor Role](/collections-model/en/semantic-paths-specification/current/entry-nodes#relationship-actor-role) \| Checklist
* [Relationship Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#relationship-date-begin) \| Checklist
* [Relationship Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#relationship-date-begin-qualifier) \| Checklist
* [Relationship Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#relationship-date-end) \| Checklist
* [Relationship Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#relationship-date-end-qualifier) \| Checklist
* [Relationship Type](/collections-model/en/semantic-paths-specification/current/entry-nodes#relationship-type) \| Checklist

### CIDOC CRM Entities

* `E7_Activity` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E7)]
* `E33_Linguistic_Object` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E33)]
* `E39_Actor` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E39)]
* `E41_Appellation` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E41)]
* `E52_Time-Span` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E52)]
* `E55_Type` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E55)]
* `PC14_carried_out_by`
* `P01_has_domain` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P01)]
* `P02_has_range` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P02)]
* `P1_is_identified_by (identifies)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P1)]
* `P2_has_type (is_type_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P2)]
* `P4_has_time-span (is_time-span_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P4)]
* `P14_carried_out_by (performed)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P14)]
* `P14.1_in_the_role_of` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P14.1)]
* `P79_beginning_is_qualified_by` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P79)]
* `P80_end_is_qualified_by` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P80)]
* `P82a_begin_of_the_begin`
* `P82b_end_of_the_end`
* `P190_has_symbolic_content` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P190)]

## Discussion

### Rationale

The CIDOC CRM ontology does not have classes or properties intended to specifically manage the relationships between actors, mainly because it is oriented towards objects. Other ontologies have tried to deal with this issue, most notably the [Agent Relationship Ontology](https://d-nb.info/standards/elementset/agrelon) (AgRelOn) (Löhden 2019) and CRMbio (Tuominen and Hyvönen 2020), but their approaches are not satisfactory.

The AgRelOn developed by the Deutsche National Bibliothek is designed to describe and represent complex relationships among people and groups by using various properties and classes. However, the use of a property-based ontology entails the modification of the Target Model Specification by adding a new property everytime a new kind of relationship has to be represented. A model with too many properties can quickly become overly complicated and hard to manage.

CRMbio, an unofficial extension of CIDOC CRM, enables the representation of complex relationships, but still causes querying issues and complicates the model for little semantic benefits. In CRMbio, the class `bioc:Actor` (a sub-class of `E39_Actor`) does not directly link to a `bioc:Event` (a sub-class of `E5_Event`) relationship. Rather, these entities are linked through the intermediary entity `bioc:Actor_Role` (a direct sub-class of `E1_CRM_Entity`) which specifies the role of the `bioc:Actor` in the relationship in conjunction with the class `E55_Type`. By using the class `E55_Type` with a controlled vocabulary, it is possible to represent multiple relationship types without adding new entities to the model. However, the class `bioc:Actor_Role` is not a sub-class of `bioc:Actor` nor of `E39_Actor`. Hence, it cannot be semantically linked to the class `E5_Event` by the property `P11_has_participant`. In addition, this pattern relies on a role to participate in events, which is problematic in and of itself because a person might be involved without having a definite role documented. 

The relationship has been modelled as a single event rather than two for the following reasons:

* Not linking the beginning and the end of the relationship together may induce querying problems. Although this proposal respects the scope note of the class `E5_Event`, it is difficult to identify a clear instance representing the connection between the two events;
* To connect the two events, the class `E70_Thing` could be used which would be created at the beginning of the relationship as a stand-in for the relationship itself. However, this would significantly complicate the model by creating, for a single relationship, two instances of `E5_Event` plus another instance of `E70_Thing` without the latter adding any information that is not already rendered by other entities. 

Meanwhile, [property-classes](/collections-model/en/target-model/current/general-concepts#property-classes) have been developed by the CRM SIG in 2014 as part of an extension that enables the reification of specific properties (i.e. they have been transformed into classes) so that instances of these property-classes can become the subject of other triples without compromising the logics of the rest of the ontology. This is useful when modelling the role of an actor in the production of an artefact (see the [Artefact](/collections-model/en/target-model/current/artefact) pattern), but it can also be used to indicate the role of an actor within a relationship.

In order to do so, relationships have to be considered as activities performed consciously or unconsciously by actors. An instance of `E7_Activity` is linked to an instance of `E39_Actor` representing the actor involved using the property-class `PC14_carried_out_by` which is assigned a type by the property `P14.1_in_the_role_of` and an instance of `E55_Type` specifying the role of each party involved. 

The use of this pattern has a few advantages as it: 

* Is compliant with CIDOC CRM, thus ensuring consistency within the model;
* Does not require the creation of new classes, which is best for reusability;
* Is egalitarian and does not structurally induce an artificial hierarchy between actors;
* Is bi-directional so that the path "Actor A is linked to Actor B" is as true as "Actor B is linked to Actor A". 

More information about the rationale of this pattern can be found in the [CIDOC 2020 Conference Proceedings](https://cidoc.mini.icom.museum/cidoc-2020-conference-papers-published/). 

### Limitations

Being unconscious of performing an activity could arguably be considered to go against the scope note of the class `E7_Activity` which dictates that the activity must be performed intentionally. To model relationships, the other option would be to use the class `E5_Event` whose properties do not enable the modelling of roles, thus compromising significantly the granularity of the information that could be accommodated by such a pattern. As such, it seems preferable to use the class `E7_Activity` until the CRMsoc (a CIDOC CRM extension for integrating data about social phenomena) working group develops a more suitable framework for the representation of relationships.

### Related GitHub Issues

* [Issue #16 "Do we need a family relationship pattern? And what to do with parents?"](https://github.com/chin-rcip/chin-rcip/issues/16)

### Edge Cases

#### Example 1 {#edge-cases-example-1}

Mapping can become tricky when one of the actors in the relationship is a group and both the Relationship and Group Belonging patterns could be used.

For example, the Portrait Gallery of Canada and its Advisory Group can be considered to be either:

* In an "Advisory" relationship (Relationship Type), the Portrait Gallery of Canada (Related Actor Appellation) being the "Advisee" (Related Actor Role) and the Advisory Group (Actor Appellation) being the "Advisor" (Relationship Actor Role);
* In a group belonging dynamic, the Advisory Group (Actor Appellation) having joined the Portrait Gallery of Canada (Group Appellation) as an "Advisor" (Group Member Role).

#### Example 2 {#edge-cases-example-2}

A dataset that would document a person as being the father or the mother figure of a family would be difficult to record since the family may contain several members and the parental role might not apply to all. In such a case, it would be possible to either document the fact that the person belongs to the family through the Family Belonging pattern or establish their relationship with each member of the said family through the Relationship pattern. However, it is impossible to document the role of the person in the first scenario, and in the second one, it is highly probable that the data provider does not know all the members of the family, so that they cannot establish beyond any doubt their relationship.

## Bibliography

Bekiari, Chryssoula, George Bruseker, Martin Doerr, Christian-Emil Ore, Stephen Stead, and Athanasios Velios, eds. *Definition of the CIDOC Conceptual Reference Model*. CIDOC CRM Documentations, 7.1. Paris, FR-IDF: CIDOC CRM Special Interest Group, 2021. [http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf](http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf).

Deutsche National Bibliothek. "AgRelOn." *AgRelOn, an Agent Relationship Ontology*. October 2, 2019. [https://d-nb.info/standards/elementset/agrelon](https://d-nb.info/standards/elementset/agrelon).

Löhden, Aenne. *AgRelOn: An Agent Relationship Ontology*. Frankfurt, DE-BB; Leipzig, DE-SN: Deutsche Nationalbibliothek, 2019. [https://d-nb.info/standards/elementset/agrelon_20190618](https://d-nb.info/standards/elementset/agrelon_20190618).

Rashid, Farzana, and Eduardo Blanco. "Dimensions of Interpersonal Relationships: Corpus and Experiments." *Proceedings of the 2017 Conference on Empirical Methods in Natural Language Processing*. Copenhagen, DEN: Association for Computational Linguistics, 2017. [https://doi.org/10.18653/v1/D17-1244](https://doi.org/10.18653/v1/D17-1244).

Tuominen, Jouni, and Eero Hyvönen. *Bio CRM: A Data Model for Representing Biographical Information for Prosopography*. Aalto University, Semantic Computing Research Group (SeCo). 2020. [https://seco.cs.aalto.fi/projects/biographies/biocrm-2020-05-28.pdf](https://seco.cs.aalto.fi/projects/biographies/biocrm-2020-05-28.pdf).

Wikipedia. "Interpersonal Relationship." *Wikipedia*. San Francisco, US-CA: Wikipedia, 2019. [https://en.wikipedia.org/w/index.php?title=Interpersonal_relationship&oldid=918983104](https://en.wikipedia.org/w/index.php?title=Interpersonal_relationship&oldid=918983104).

Wikipedia. "Yousuf Karsh." *Wikipedia*. San Francisco, US-CA: Wikipedia, 2021. [https://fr.wikipedia.org/wiki/Yousuf_Karsh](https://fr.wikipedia.org/wiki/Yousuf_Karsh).

