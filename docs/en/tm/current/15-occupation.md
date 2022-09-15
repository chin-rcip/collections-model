---
layout: page
language: en
title: Occupation
permalink: /en/target-model/current/occupation
other_link: /fr/modele-cible/actuel/occupation
sidebar: tm22
date: 2022-03-31
description: The Actors Target Model Specification semantically models actors in a heritage context. Patterns most relevant to actors' lives are presented along with diagrams and examples illustrating them, as well as a record and explanation of relevant decisions that were made when developing said patterns. This is a theoretical documentation that has never been tested or implemented.
---

Version 2.2 ([Previous versions](/collections-model/en/versions))

## At Glance

This pattern can be used to represent the information pertaining to the occupation·s of a person or a group, in a broader sense, as primary endeavours in their life. It includes: 

* The type of occupation of an actor, which could be a paid or unpaid activity, business, profession or another labour-related endeavour;
* The time during which an actor assumed the occupation;
* The place where an actor performed the occupation.

This pattern should not be used to represent:

* The specific role an actor played in the creation of an artefact (use the [Artefact Production](/collections-model/en/target-model/current/artefact-production) pattern instead);
* The techniques an actor employed in the creation of an artefact (use the [Artefact Production](/collections-model/en/target-model/current/artefact-production) pattern instead);
* The techniques for which an actor is known (use the [Technique Used](/collections-model/en/target-model/current/techniques-used) pattern instead);
* The recreational and professional activities of an individual that is part of a group (e.g. an employed musician in an orchestra), including their education (e.g. student or teacher of an educational institution) (use the [Group Belonging](/collections-model/en/target-model/current/group-belonging) pattern instead);
* The social status an actor held (use the [Social Status](/collections-model/en/target-model/current/social-status) pattern instead).

## Introduction and Context

### Theoretical Background

An actor performs many significant and defining activities throughout their lives, especially when it requires training, skills, and qualifications that can be paid (e.g. employed by a company) or unpaid (e.g. volunteering). These activities are usually considered by either the actor or an expert community to be one of their primary endeavours in life (i.e. as a source of income or for other purposes such as a hobby). 

In addition, occupations are an important identity marker for several communities, even if there is a slight decrease in its importance over time compared to other markers such as gender or nationality. Furthermore, social status is often intimately linked to occupation and plays a central role in self-identification, particularly with communities of practice sharing similar issues and needs (Ulfsdotter Eriksson and Linde 2014).

Documenting one occupation rather than another can therefore help better understand the values held by the community of practice of an actor. These values can either be perceived by the community contemporary to the element described or by the community to which the cultural heritage institution that maintains this information belongs.

### Statement of Need

This essential metadata is often documented by cultural heritage institutions as a way to differentiate an actor from other actors as well as to document their lives.

Moreover, an actor can hold more than one occupation, each of which can be assumed within a definite time frame and in one or multiple places. For example, Yousuf Karsh, before starting a 60-year career as a professional portrait photographer in 1932 with his own studio in Ottawa, CA-ON, was an apprentice in Boston, US-MA, from 1928 to 1931 (Wikipedia 2021). This detailed data enriches the actor’s metadata, and is of significance to research (e.g. chronological and/or geographical analysis). 

Documenting the time frame and places of an occupation can also provide useful information about its context which can help to better understand human practices, such as the evolution of occupations through time or space, or their importance in specific periods and/or places.

## Description of the Pattern

For each occupation, an instance of `E39_Actor` is first linked by the property `P14_carried_out_by` to an instance of `F51_Pursuit` which is qualified by the [Occupation Type](/collections-model/en/semantic-paths-specification/current/entry-nodes#occupation-type) value (an instance of `E55_Type`) using the property `P2_has_type`. This instance of `E55_Type` is further qualified by an instance of `E55_Type` (a specified qualifier node) labelled "Occupation" through the property `P2_has_type`.

The duration of the pursuit is indicated using the [Temporal Bounds](/collections-model/en/target-model/current/temporal-bounds) pattern linked to the instance of `F51_Pursuit` through the property `P4_has_time-span` with values extracted from the [Occupation Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#occupation-date-begin), [Occupation Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#occupation-date-begin-qualifier), [Occupation Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#occupation-date-end), and [Occupation Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#occupation-date-end-qualifier) entry nodes. 

In addition, the instance of `F51_Pursuit` is linked to its [Occupation Place](/collections-model/en/semantic-paths-specification/current/entry-nodes#occupation-place) value (an instance of `E53_Place`) by the property `P7_took_place_at`.

## Diagram

<a name="033_Pattern_Occupation_p"></a>033_Pattern_Occupation_p

<iframe frameborder="0" style="width:100%;height:500px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=033_Pattern_Occupation_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1qhYk5MbLSKYNCBamWBXTEQEIRLr2WLOp%26export%3Ddownload"></iframe>

## Examples

### Example 1

Yousuf Karsh pursued a career as a photographer (`P2_has_type`, Occupation Type) spanning 60 years, from 1932 (`P82a_begin_of_the_begin`, Occupation Date Begin) to 1992 (`P82b_end_of_the_end`, Occupation Date End), mainly based in Ottawa (CA-ON) (`P7_took_place_at`, Occupation Place) (Wikipedia 2021a).

<div id="0001_100_occupation" class="example"></div>

### Example 2

Marc Séguin is a visual artist (`P2_has_type`, Occupation Type), novelist (`P2_has_type`, Occupation Type), and farmer (`P2_has_type`, Occupation Type). His first solo exhibition dates back to 1996 (`P2_has_type`, Occupation Type "Visual Artist"; `P82a_begin_of_the_begin`, Occupation Date Begin "1996"; `P79_beginning_is_qualified_by`, Occupation Date Begin Qualifier "Before") and he has practiced in Montreal, QC (`P7_took_place_at`, Occupation Place), Hemmingford, QC (`P7_took_place_at`, Occupation Place), and Brooklyn, NY (`P7_took_place_at`, Occupation Place). His first novel, *La Foi du braconnier*, was published in 2009 (`P2_has_type`, Occupation Type "Novelist"; Occupation Date Begin "2009"; `P79_beginning_is_qualified_by`, Occupation Date Begin Qualifier "Before"). He owns a family farm in Hemmingford, QC (`P2_has_type`, Occupation Type "Farmer"; `P82a_begin_of_the_begin`, Occupation Date Begin "2008"; `P79_beginning_is_qualified_by`, Occupation Date Begin Qualifier "Before"; `P7_took_place_at`, Occupation Place "Hemmingford, QC") (Wikipedia 2022).

<div id="0001_128_occupation" class="example"></div>

## Related Documentation

### External Models

* Linked.art: [Active Dates](https://linked.art/model/actor/#active-dates)
* SARI: [Person Reference Data Model – Activities](https://docs.swissartresearch.net/et/persons/#activities)
* Schema.org: [`hasOccupation` property](https://schema.org/hasOccupation)
* Wikidata: [`P106`(occupation)](https://www.wikidata.org/wiki/Property:P106) 

### Entry Nodes

* [Occupation Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#occupation-date-begin) \| Checklist
* [Occupation Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#occupation-date-begin-qualifier) \| Checklist
* [Occupation Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#occupation-date-end) \| Checklist
* [Occupation Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#occupation-date-end-qualifier) \| Checklist
* [Occupation Place](/collections-model/en/semantic-paths-specification/current/entry-nodes#occupation-place) \| Checklist
* [Occupation Type](/collections-model/en/semantic-paths-specification/current/entry-nodes#occupation-type) \| Checklist

### CIDOC CRM Entities

* `F51_Pursuit`
* `E39_Actor` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E39)]
* `E52_Time-Span` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E52)]
* `E53_Place` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E53)]
* `E55_Type` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E55)]
* `P2_has_type_(is_type_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P2)]
* `P4_has_time-span (is_time-span_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P4)]
* `P7_took_place_at (witnessed)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P7)]
* `P14_is_carried_out_by (performed)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P14)]
* `P79_beginning_is_qualified_by` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P79)]
* `P80_end_is_qualified_by` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P80)]
* `P82a_begin_of_the_begin`
* `P82b_end_of_the_end`

## Discussion

### Rationale

Modelling an occupation as a classification of an actor, meaning an instance of `E39_Actor` directly linked to an instance of `E55_Type`, can become restrictive as temporal and geographical data pertaining to the occupation cannot be recorded. The class `F51_Pursuit` from the CIDOC CRM extension FRBRoo provides more flexibility in that aspect. 

Also, by definition, the class `F51_Pursuit` "comprises periods of continuous activity of an actor in a specific professional or creative domain or field" (Bekiari et al. 2015a, sect. F51 Pursuit). As its scope is semantically closer to the general definition of occupation, which encompasses both professional and recreational activities, it was selected to model occupation·s rather than its super-class `E7_Activity`. 

In the mapping table from FRAD to FRBRoo of the FRBRoo documentation (v2.4) (Bekiari et al. 2015b), the path `F51_Pursuit` -> `P2_has_type` -> `E55_Type` is one of the suggested mappings for units of information such as *Person: Field of Activity*, *Person: Profession/Occupation*, and *Corporate Body: Field of Activity*. By definition, an instance of `F51_Pursuit` can be directly linked to an instance of `E1_CRM_Entity` or its sub-classes by the property `R59_had_typical_subject`. However, the example for `R59_had_typical_subject` found in the FRBRoo documentation ("John Dover Wilson’s activity as a Shakespeare scholar (F51) R59 had typical subject William Shakespeare (F10)") shows that this property seems to identify the subject rather than the type of the pursuit. Hence, the property `P2_has_type` and the class `E55_Type` are considered more suitable to classify the occupational type of the pursuit, whereas the property `R59_had_typical_subject` can be used to represent its subject, though this is not currently done.

To differentiate this type of activity from other activities, in particular when running queries, a specified qualifier node is necessary. In the version 1.5 of the Targel Model Specification, the occupation was further qualified by two more levels of the class `E55_Type`, for example `E55_Type` ("Painter") -> `P2_has_type` -> `E55_Type` ("Profession") -> `P2_has_type` -> `E55_Type` ("Occupation"). However, three levels of `E55_Type` can quickly inflate the data model and complicate its maintenance and management for a simple need of qualifying the type of occupation. Therefore, two levels of the class `E55_Type` (the entry node for Social Status Type and the specified qualifier node labelled "Social Status") are deemed sufficient. If further hierarchization of social status is needed (for instance distinguishing different kinds of social status), this should be handled by the vocabulary of that status.

### Limitations

As mentioned in the Rationale, some occupations can be further qualified by documenting the subject of the occupation through the property `R59_had_typical_subject`. However, this information is not yet accounted for in the DOPHEDA model due to insufficient use cases.

### Related GitHub Issues

* [Issue #1 "Techniques vs occupations"](https://github.com/chin-rcip/collections-model/issues/1)
* [Issue #11 "Should the school years be model[l]ed as being a member of a group? Would it be the same for professors?](https://github.com/chin-rcip/collections-model/issues/11)
* [Issue #27 "How should we model social status pattern·s?"](https://github.com/chin-rcip/collections-model/issues/27)
* [Issue #29 "Do we need three levels of types in the occupation pattern?"](https://github.com/chin-rcip/collections-model/issues/29)
* [Issue #37 "Usefulness of E55_Type"](https://github.com/chin-rcip/collections-model/issues/37)

### Edge Cases

#### Example 1 {#edge-cases-example-1}

Elizabeth II, the person who was in charge of officially granting the social status "Companion of the Order of Canada" to Yousuf Karsh, is known as being the Queen of the United Kingdom and 15 other Commonwealth realms. While some might see "being the queen" as an occupation that comes with very specific activities and tasks, others would see it as a social status. To this duality is added the possibility of documenting the term "Queen" as a title/prefix to the name of the person. If the data does not specify how the information is understood within the framework of a specific dataset, the modelling could lead to uncertainty and misinterpretation of the matter.

#### Example 2 {#edge-cases-example-2}

Molly Bobak sketched in her diaries throughout the war and it is only three years after her enrollment that she was officially made a war artist (Occupation Type) by the Canadian War Artists Selection Committee (Wikipedia 2021b). In this case, it is unclear how best to record the information as the beginning date of the Occupation Type would be after the end of her serving. It is also unclear if the Occupation Type is determined by the act of completing tasks or by the holding of a position.

## Bibliography

Bekiari, Chryssoula, Martin Doerr, Patrick Le Bœuf, and Pat Riva, eds. "F51 Pursuit." *FRBR Object-Oriented Definition and Mapping from FRBRER, FRAD and FRSAD*. FRBRoo Documentations, 2.4. International Council of Museums (ICOM), 2015. [http://www.cidoc-crm.org/frbroo/sites/default/files/FRBRoo\_V2.4.pdf](http://www.cidoc-crm.org/frbroo/sites/default/files/FRBRoo_V2.4.pdf).

Bekiari, Chryssoula, Martin Doerr, Patrick Le Bœuf, and Pat Riva, eds. "3.5. FRAD to FRBROO Mappings." *FRBR Object-Oriented Definition and Mapping from FRBRER, FRAD and FRSAD*. FRBRoo Documentations, 2.4. International Council of Museums (ICOM), 2015. [http://www.cidoc-crm.org/frbroo/sites/default/files/FRBRoo\_V2.4.pdf](http://www.cidoc-crm.org/frbroo/sites/default/files/FRBRoo_V2.4.pdf).

Bekiari, Chryssoula, George Bruseker, Martin Doerr, Christian-Emil Ore, Stephen Stead, and Athanasios Velios, eds. *Definition of the CIDOC Conceptual Reference Model*. CIDOC CRM Documentations, 7.1. Paris, FR-IDF: CIDOC CRM Special Interest Group, 2021. [http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf](http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf).

Free Dictionary. "Occupation." *The Free Dictionary*. Huntington Valley, US-PA: Farlex, 2021. [https://www.thefreedictionary.com/role](https://www.thefreedictionary.com/role).

Ulfsdotter Eriksson, Ylva, and Malin Linde. "'Being' or 'Doing' a Profession: Work as a Matter of Social Identity." *The International Journal of Interdisciplinary Cultural Studies* 8, no. 1 (2014): 33‑43.

Wikipedia. "Yousuf Karsh." *Wikipedia*. San Francisco, US-CA: Wikipedia, 2021a. [https://fr.wikipedia.org/wiki/Yousuf_Karsh](https://fr.wikipedia.org/wiki/Yousuf_Karsh).

–––. "Molly Lamb Bobak." *Wikipedia*. San Francisco, US-CA: Wikipedia, 2021b. [https://fr.wikipedia.org/wiki/Molly_Lamb_Bobak](https://fr.wikipedia.org/wiki/Molly_Lamb_Bobak). 

\_\_\_. "Marc Séguin." *Wikipedia*. San Francisco, US-CA: Wikipedia, 2022. [https://fr.wikipedia.org/wiki/Marc_Séguin](https://fr.wikipedia.org/wiki/Marc_Séguin).

