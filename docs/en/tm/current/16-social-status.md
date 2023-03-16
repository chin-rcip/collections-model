---
layout: page
language: en
title: Social Status
permalink: /en/target-model/current/social-status
other_link: /fr/modele-cible/actuel/statut-social
sidebar: tm22
date: 2022-03-31
description: The Actors Target Model Specification semantically models actors in a heritage context. Patterns most relevant to actors' lives are presented along with diagrams and examples illustrating them, as well as a record and explanation of relevant decisions that were made when developing said patterns. This is a theoretical documentation that has never been tested or implemented.
---

Version 2.2 ([Previous versions](/collections-model/en/versions))

## At Glance

This pattern can be used to represent the information pertaining to the social status·es of a person or a group of persons. It includes: 

* The type of social status (e.g. elder, member elect of an order, etc.), which includes the relative rank and possible honour or prestige an actor holds relative to how well they are perceived to match society’s goals and ideals, as well as their hierarchical position in the group’s social stratification;
* The time during which an actor assumed the status;
* The place where an actor assumed the status;
* The appellation of an actor that assigned the status to its holder.

This pattern should not be used to represent:

* The activities, businesses, professions, and other labour-related roles of an actor (use the [Occupation](/collections-model/en/target-model/current/occupation) pattern instead);
* The activities of an actor as an individual that is part of a group (use the [Group Belonging](/collections-model/en/target-model/current/group-belonging) pattern instead). 

## Introduction and Context

### Theoretical Background

Social status is a relative social rank that an individual holds within a social stratification based upon honour or prestige. Status reflects a set of connected behaviours, activities, functions, rights, obligations, duties, beliefs, lifestyle, and norms. It can either be ascribed or achieved. Ascribed status is assigned to individuals at birth and usually involuntary (e.g. being the first-born son of a family, or a prince by birth). In contrast, achieved status is acquired through individuals’ effort and actions, usually requiring special qualities, and based on education, occupation, relationships, achievements, etc. (Editors of Encyclopædia Britannica 2019). For example, the photographer Yousuf Karsh acquired the status of Companion of the Order of Canada for his contributions to the nation. 

As such, the occupation of an individual, whether it is a paid or unpaid activity, business, profession, or other labour-related role, can be a variable to adjudicate their social status. Equivalently, the act of joining a group in a certain role can also establish one’s status. For example, Helen Keller, photographed by Yousuf Karsh, founded and was a member of several militant groups (e.g. Helen Keller International) throughout her career, which allowed her to obtain the social status "political activist" to the eyes of some of her contemporaries.

### Statement of Need

While actors have professional or artistic occupations, they also hold social status·es, like being a leader, an elder, or a knight. Status can be acquired upon birth or awarded as a result of some activities and/or events, such as contribution to society, life achievements, significant works, etc. As such, the information on social status can be considered as a distinctive quality of an actor. 

Additionally, status is gained through an official recognition and assignment by an·other actor·s who represent·s the community that confers it. Therefore, it is important to capture the assignor of the social status in order to further document the social context of the status.

Also, geographical and temporal information about the assignment of a social status needs to be captured because such information brings data enrichment and more information about the context of the status. In terms of time, a social status can have an end date as some statuses cease to be recognized upon the death of the status holder, or are transferred to a succeeding holder. In other cases, it can be revoked by another actor, who is usually the same actor that has attributed the status, or the status holder voluntarily resigns. 

As social statuses are an important aspect of human lives, such information can be the object of numerous studies, such as documenting the official recognition of artists from minorities, the evolution of certain statuses through time or space, etc.

## Description of the Pattern

For each social status, an instance of `E39_Actor` is first linked by the property `P11_had_participant` to an instance of `E5_Event` which is qualified by the [Social Status Type](/collections-model/en/semantic-paths-specification/current/entry-nodes#social-status-type) value (an instance of `E55_Type`) using the property `P2_has_type`. This instance of `E55_Type` is further qualified by an instance of `E55_Type` (a specified qualifier node) labelled "Social Status" through the property `P2_has_type`.

The duration of the event is indicated using the [Temporal Bounds](collections-model/en/target-model/current/temporal-bounds) pattern linked to the instance of `E5_Event` through the property `P4_has_time-span`, with values extracted from the [Social Status Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#social-status-date-begin), [Social Status Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#social-status-date-begin-qualifier), [Social Status Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#social-status-date-end), and [Social Status Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#social-status-date-end-qualifier) entry nodes. 

In addition, the event is linked to the [Social Status Place](/collections-model/en/semantic-paths-specification/current/entry-nodes#social-status-place) value (an instance of `E53_Place`) by the property `P7_took_place_at`.

The instance of `E5_Event` that represents the social status is triggered by (CRMsci property `O13i_is_triggered_by`) a social status assignment event (an instance of `E13_Attribute_Assignment`). Through the property `P14_carried_out_by`, this attribution activity is linked to an instance of `E39_Actor` that represents the actor that ascribed the social status. This instance of `E39_Actor` is then linked to an instance of both `E41_Appellation` and `E33_Lingusitic_Object` through the property `P1_is_identified_by`. From this instance, the literal value of the [Social Status Ascribing Actor Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#social-status-ascribing-actor-appellation) is rendered by the property `P190_has_symbolic_content`.

The instance of `E13_Attribute_Assignment` is also linked to the same instance of `E5_Event` by the property `P141_assigned` as well as linked to the first instance of `E39_Actor` (who received the status) by the property `P140_assigned_attribute_to`.

## Diagram

<a name="035_Pattern_SocialStatus_p"></a>035_Pattern_SocialStatus_p

<div class="mxgraph" style="max-width:100%;border:1px solid #cccccc;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;target&quot;:&quot;blank&quot;,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom layers lightbox&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;xml&quot;:&quot;&lt;mxfile modified=\&quot;2023-03-15T17:12:28.716Z\&quot; host=\&quot;app.diagrams.net\&quot; agent=\&quot;5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) draw.io/20.3.0 Chrome/104.0.5112.114 Electron/20.1.3 Safari/537.36\&quot; etag=\&quot;2qA6pIs2p5VvZHwHRIIU\&quot; version=\&quot;20.3.0\&quot;&gt;&lt;diagram id=\&quot;Vnz9Qq2Wo0vU6o8shjVE\&quot; name=\&quot;Page-1\&quot;&gt;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&lt;/diagram&gt;&lt;/mxfile&gt;&quot;}"></div>

## Examples

### Example 1

In 1990 (`P82a_begin_of_the_begin`, Social Status Date Begin), Yousuf Karsh was awarded the Companion of the Order of Canada (`P2_has_type`, Social Status Type) by Queen Elizabeth II (`P190_has_symbolic_content`, Social Status Ascribing Actor Appellation) in Ottawa, CA-ON (`P7_took_place_at`, Social Status Place). The social status was maintained even after Yousuf Karsh’s death in 2002 (Hillmer 2018; Skidmore 2015). 

<div id="0001_100_social-status" class="example"></div>

### Example 2

Aung San Suu Kyi was awarded an honorary Canadian citizenship (`P2_has_type`, Social Status Type) in 2007 (`P82a_begin_of_the_begin`, Social Status Date Begin) CE (`P79_beginning_is_qualified_by`, Social Status Date Begin Qualifier) by the Parliament of Canada (`P190_has_symbolic_content`, Social Status Ascribing Actor Appellation). The honour was revoked by the House of Commons on September 27, 2018 and by the Senate (`P7_took_place_at`, Social Status Place "Canada") on October 2, 2018 (`P82b_end_of_the_end`, Social Status Date End (debatable); `P80_end_is_qualified_by`, Social Status Date End Qualifier "Before" (debatable)) due to human rights concerns over her treatment of the Rohingya (Wikipedia 2022a).

<div id="0001_129_social-status" class="example"></div>

## Related Documentation

### External Models

External Models links

### Entry Nodes

* [Social Status Type](/collections-model/en/semantic-paths-specification/current/entry-nodes#social-status-type) \| Checklist
* [Social Status Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#social-status-date-begin) \| Checklist
* [Social Status Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#social-status-date-begin-qualifier) \| Checklist
* [Social Status Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#social-status-date-end) \| Checklist
* [Social Status Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#social-status-date-end-qualifier) \| Checklist
* [Social Status Place](/collections-model/en/semantic-paths-specification/current/entry-nodes#social-status-place) \| Checklist
* [Social Status Ascribing Actor Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#social-status-ascribing-actor-appellation) \| Checklist

### CIDOC CRM Entities

* `E5_Event` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E5)]
* `E13_Attribute_Assignment` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E13)]
* `E33_Linguistic_Object` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E33)]
* `E39_Actor` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E39)]
* `E41_Appellation` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E41)]
* `E52_Time-Span` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E52)]
* `E53_Place` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E53)]
* `E55_Type [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E55)]
* `O13_triggers (is_triggered_by)`
* `P1_is_identified_by (identifies)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P1)]
* `P2_has_type (is_type_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P2)]
* `P4_has_time-span (is_time-span_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P4)]
* `P7_took_place_at (witnessed)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P7)]
* `P11_had_participant (participated_in)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P11)]
* `P14_carried_out_by (performed)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P14)]
* `P79_beginning_is_qualified_by` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P79)]
* `P80_end_is_qualified_by` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P80)]
* `P82a_begin_of_the_begin`
* `P82b_end_of_the_end`
* `P140_assigned_attribute_to (was_attributed_by)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P140)]
* `P141_assigned (was_assigned_by)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P141)]
* `P190_has_symbolic_content` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P190)]

## Discussion

### Rationale

The class `E5_Event` is used to represent the social status for the following reasons:

* Unlike occupation, social status is a social position that an actor might not have actively and intentionally pursued themselves; thus, it is beyond the scope of the class `F51_Pursuit`. Nonetheless, there are several occupations that can also be considered as social statuses and therefore documented in both patterns (e.g. Prime Minister);
* Often, social status is not "intentionally carried out by" (Le Bœuf et al. 2015, sect. E7 Activity) the described actor. It is more of a "change of state in cultural, social or physical systems" (Le Bœuf et al. 2015, sect. E5 Event) in which the described actor participated.

In addition, the social status of an actor is usually awarded or assigned by another actor who is socially empowered to do so. In CIDOC CRM, the class `E13_Attribute_Assignment` is deemed the most suitable to represent this action as it "comprises the actions of making assertions about properties of an object or any relation between two items or concepts. This class allows the documentation of how the respective assignment came about, and whose opinion it was" (Le Bœuf et al. 2015, sect. E13 Attribute Assignment). However, this relies on a more specific use of the class `E13_Attribute_Assignment`, as it only describes the socially empowered attribution event, and not just the act of recording the status.

Of course, the social status gain and its assignment are not two isolated events. In fact, the latter precedes the former. To capture this sequential link, the property `O13_triggers` from the extension CRMsci is used to indicate the causality relationship between the two events (Doerr et al. 2015, sect. O13 triggers (is triggered by)).

Moreover, to differentiate this type of activity from other types, in particular when running queries, a specified qualifier node is necessary. In the version 1.5 of the Target Model, the social status was further qualified by two more levels of the class `E55_Type`, for example `E55_Type` ("Companion of the Order of Canada") -> `P2_has_type` -> `E55_Type` ("Honorific Title") -> `P2_has_type` -> `E55_Type` ("Social Status"). However, three levels of `E55_Type` can quickly inflate the data model and complicate its maintenance and management for a simple need of qualifying the social status. Therefore, two levels of the class `E55_Type` (the entry node for Social Status Type and the specified qualifier node labelled "Social Status") are deemed sufficient. If further hierarchization of the social status is needed (for instance distinguishing different kinds of social status), this should be handled by the vocabulary of that status. 

### Limitations

Even though it is possible to document the assignor and the end of the social status in this version of the DOPHEDA model, there is no way of documenting the actor who removed the status.

It should be noted that the above described pattern is only a temporary solution to capture the information on social status of an actor, while waiting for an official version of the [CIDOC CRM Social Extension](http://www.cidoc-crm.org/crmsoc/). The extension, which is still under development, will likely have a class akin to a "Phase" that could document the statuses.

### Related GitHub Issues

* [Issue #27 "How should we model social status pattern·s?"](https://github.com/chin-rcip/collections-model/issues/27)
* [Issue #29 "Do we need three levels of types in the occupation pattern?"](https://github.com/chin-rcip/collections-model/issues/29)
* [Issue #37 "Usefulness of E55_Type"](https://github.com/chin-rcip/collections-model/issues/37)

### Edge Cases

#### Example 1 {#edge-cases-example-1}

Yousuf Karsh’s social status as Companion of the Order of Canada can also be considered as a membership which can be modelled with the Group Belonging pattern.

#### Example 2 {#edge-cases-example-2}

The example of Helen Keller mentioned above is also an edge case since it is possible to consider her activism as an occupation and not as a social status. In such a case, a social status can be attributed by a general understanding, and not during a specific event by a specific actor, but it becomes difficult to know who is the actor in charge of ascribing the social status.

#### Example 3 {#edge-cases-example-3}

Alice Ann Munro is a Canadian short story writer and recipient of the Nobel Prize in Literature (Social Status Type "Nobel Laureate"), which she was awarded in Stockholm (Social Status Place) in 2013 (Social Status Date Begin). Munro died in 2013 shortly after having received the award (Social Status Date End; Social Status Date End Qualifier "After"). It is debatable whether there is a natural end to a status (i.e. when the actor dies) or if the only way to end a status is by the official revocation of that status (i.e. those that conferred it strip the recipient of it) (Wikipedia 2022b).

## Bibliography

Bekiari, Chryssoula, George Bruseker, Martin Doerr, Christian-Emil Ore, Stephen Stead, and Athanasios Velios, eds. *Definition of the CIDOC Conceptual Reference Model*. CIDOC CRM Documentations, 7.1. Paris, FR-IDF: CIDOC CRM Special Interest Group, 2021. [http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf](http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf)

Doerr, Martin, Athina Kritsotaki, Yannis Rousakis, Gerald Hiebel, and Maria Theodoridou. "O13 triggers (is triggered by)." *Definition of the CRMsci: An Extension of CIDOC-CRM to Support Scientific Observation. 1.2.8*. Heraklion, GR: CIDOC CRM, 2020. [http://www.cidoc-crm.org/crmsci/sites/default/files/CRMsci%20v.1.2.8.pdf](http://www.cidoc-crm.org/crmsci/sites/default/files/CRMsci%20v.1.2.8.pdf).

Editors of Encyclopædia Britannica. "Social Status." *Encyclopædia Britannica*. London, UK-LDN: Encyclopædia Britannica, 2019. [https://www.britannica.com/topic/social-status](https://www.britannica.com/topic/social-status).

Hillmer, Norman. "Roland Michener." *The Canadian Encyclopedia*. Toronto, CA-ON: Historica Canada, 2018 [2008]. [https://www.thecanadianencyclopedia.ca/en/article/daniel-roland-michener](https://www.thecanadianencyclopedia.ca/en/article/daniel-roland-michener).

Le Bœuf, Patrick, Martin Doerr, Christian Emil Ore, and Stephen Stead, eds. "E5 Event." *Definition of the CIDOC Conceptual Reference Model*. CIDOC CRM Documentations, 6.2.1. Paris, FR-IDF: International Council of Museums (ICOM), 2015. [http://www.cidoc-crm.org/sites/default/files/cidoc_crm_version_6.2.1.pdf](http://www.cidoc-crm.org/sites/default/files/cidoc_crm_version_6.2.1.pdf).

–––. "E7 Activity." *Definition of the CIDOC Conceptual Reference Model*. CIDOC CRM Documentations, 6.2.1. Paris, FR-IDF: International Council of Museums (ICOM), 2015. [http://www.cidoc-crm.org/sites/default/files/cidoc_crm_version_6.2.1.pdf](http://www.cidoc-crm.org/sites/default/files/cidoc_crm_version_6.2.1.pdf).

–––. "E13 Attribute Assignment." *Definition of the CIDOC Conceptual Reference Model*. CIDOC CRM Documentations, 6.2.1. Paris, FR-IDF: International Council of Museums (ICOM), 2015. [http://www.cidoc-crm.org/sites/default/files/cidoc_crm_version_6.2.1.pdf](http://www.cidoc-crm.org/sites/default/files/cidoc_crm_version_6.2.1.pdf).

Skidmore, Colleen. "Yousuf Karsh." *The Canadian Encyclopedia*. Reprint, Toronto, CA-ON: Historica Canada, March 4, 2015 [2010]. [https://www.thecanadianencyclopedia.ca/en/article/yousuf-karsh](https://www.thecanadianencyclopedia.ca/en/article/yousuf-karsh).

Wikipedia. "Aung San Suu Kyi." *Wikipedia*. San Francisco, US-CA: Wikipedia, 2022a. [https://fr.wikipedia.org/wiki/Aung_San_Suu_Kyi](https://fr.wikipedia.org/wiki/Aung_San_Suu_Kyi).

Wikipedia. "Alice Munro." *Wikipedia*. San Francisco, US-CA: Wikipedia, 2022b. [https://fr.wikipedia.org/wiki/Alice_Munro](https://fr.wikipedia.org/wiki/Alice_Munro).

