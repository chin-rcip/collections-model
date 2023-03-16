---
layout: page
language: en
title: Staying Event
permalink: /en/target-model/current/staying-event
other_link: /fr/modele-cible/actuel/evenement-de-sejour
sidebar: tm22
date: 2022-03-31
description: The Actors Target Model Specification semantically models actors in a heritage context. Patterns most relevant to actors' lives are presented along with diagrams and examples illustrating them, as well as a record and explanation of relevant decisions that were made when developing said patterns. This is a theoretical documentation that has never been tested or implemented.
---

Version 2.2 ([Previous versions](/collections-model/en/versions))

## At Glance

This pattern can be used to represent the information pertaining to the physical presence of actors somewhere for a prolonged or temporary duration, including at their customary residence/geographical location. It includes: 

* The geographical location where an actor stayed;
* The time during which an actor stayed at the geographical location;
* The appellation·s that an actor used during their stay at the geographical location;
* In the case of groups, the staying event can be defined as headquarters.

This pattern should not be used to represent:

* The geographical location and dates of an actor’s occupation (use the [Occupation](/collections-model/en/target-model/current/occupation) pattern instead);
* The geographical location and dates of an actor’s "floruit" (use the [Flourishing](/collections-model/en/target-model/current/flourishing) pattern instead);
* The geographical location and dates of an actor’s social status (use the [Social Status](/collections-model/en/target-model/current/social-status) pattern instead);
* The burial location of an actor (use the [Birth and Death of a Person](/collections-model/en/target-model/current/birth-and-death) pattern instead).

## Introduction and Context

### Theoretical Background

People individually or in groups move through space primarily for professional, leisure, or educational activities and sometimes out of necessity (e.g. wars), and corporate entities can expand or move in space by acquiring new real estate. Knowing the location of an actor at a specific time helps to better understand their life stories and the cultures they came into contact with. On a larger scale, this location makes it possible to identify issues, particularly political ones, such as colonization and deportation, with which they may have had to deal with and that contribute to understanding migratory flows.

By monitoring the places visited by actors, it is possible to study the globalization phenomena and understand how each geographical jurisdiction contributes positively and negatively to it (e.g. sharing of expertise, internship offer, opening of new markets, tourism, border closures, embargoes, alliances, etc.). Globalization "is not an omnipotent, unidirectional force levelling everything in its path" (Editors of Encyclopædia Britannica n.d.), its analysis inevitably goes through the particular aspects of life that are affected by this process. Therefore, the reasons that lead an actor to move or stay in the same place are multiple and rarely attributable to a single issue.

### Statement of Need

Throughout their life or activities, an actor may travel, live, or be present in various locations. Such information can be recorded as it provides knowledge about the cultural context in which the actor evolved. Staying at a certain place and during a certain period of time might not directly connect to any specific activity or event such as an occupation (including both professional and recreational activities), but documenting an actor’s staying activities provides a continuous timeline of their life history. As such, information pertaining to this type of activity should be modelled in a dedicated pattern.

Another element that links to the geographical location of the actor’s physical presence is the actor appellation which is used to indicate the appellation·s used at this location, especially in the case of groups (see the [Actor Identifiers and Appellations](/collections-model/en/target-model/current/actor-identifiers-and-appellations) pattern). For example, a company could have used two different registered names which were associated with two different addresses. One of them could be the location used for the purpose of headquarters activity. 

## Description of the Pattern 

For each stay, an instance of `E39_Actor` is first linked by the property `P14_carried_out_by` to an instance of `E7_Activity`, which is then qualified by an instance of `E55_Type` (a specified qualifier node) labelled "Stay" through the property `P2_has_type`.

The duration of the stay is rendered using the [Temporal Bounds](/collections-model/en/target-model/current/temporal-bounds) pattern linked to the instance of `E7_Activity` by the property `P4_has_time-span` with values extracted from the [Stay Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#stay-date-begin), [Stay Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#stay-date-begin-qualifier), [Stay Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#stay-date-end), and [Stay Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#stay-date-qualifier) entry nodes.

In addition, the instance of `E7_Activity` is linked to:

* The [Stay Place](/collections-model/en/semantic-paths-specification/current/entry-nodes#stay-place) value (an instance of `E53_Place`) by the property `P7_took_place_at`;
* The [Stay Type](/collections-model/en/semantic-paths-specification/current/entry-nodes#stay-type) value (an instance of `E55_Type`) by the property `P21_had_general_purpose`;
* An instance of both `E41_Appellation` and `E33_Linguistic_Object` by the property `P16_used_specific_object` which is linked to the literal value of the [Stay Used Appellation]((/collections-model/en/semantic-paths-specification/current/entry-nodes#stay-used-appellation) through the property `P190_has_symbolic_content`.

## Diagram

<a name="052_Pattern_Stay_p"></a>052_Pattern_Stay_p

<div class="mxgraph" style="max-width:100%;border:1px solid #cccccc;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;target&quot;:&quot;blank&quot;,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom layers lightbox&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;xml&quot;:&quot;&lt;mxfile modified=\&quot;2023-03-15T17:12:29.690Z\&quot; host=\&quot;app.diagrams.net\&quot; agent=\&quot;5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) draw.io/20.3.0 Chrome/104.0.5112.114 Electron/20.1.3 Safari/537.36\&quot; etag=\&quot;XQVxubL1PieqNOB-luU4\&quot; version=\&quot;20.3.0\&quot;&gt;&lt;diagram id=\&quot;Vnz9Qq2Wo0vU6o8shjVE\&quot; name=\&quot;Page-1\&quot;&gt;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&lt;/diagram&gt;&lt;/mxfile&gt;&quot;}"></div>

## Examples

### Example 1

Upon his arrival to Canada on December 31, 1924 (`P82a_begin_of_the_begin`, Stay Date Begin "1924-12-31T00:00:00"), Yousuf Karsh moved to Sherbrooke, CA-QC (`P7_took_place_at`, Stay Place) to live with his maternal uncle George Nakash until 1928 (`P82b_end_of_the_end`, Stay Date End "1928-12-31T23:59:59") before he left for Boston, USA-MA (`P7_took_place_at`, Stay Place). He stayed there until 1931 (`P82a_begin_of_the_begin`, Stay Date Begin "1928-01-01T00:00:00"; `P82b_end_of_the_end`, Stay Date End "1931-12-31T23:59:59") (Karsh n.d.).

<div id="0001_100_staying-event" class="example"></div>

### Example 2

The Royal Canadian Academy of Arts (Stay Used Appellation), an organization of which Yousuf Karsh was an Academician member, relocated its headquarters (`P21_had_general_purpose`, Stay Type) to 50 Sussex Dr, Ottawa, ON K1M 2K1 (`P7_took_place_at`, Stay Place) on September 1, 2020 (`P82a_begin_of_the_begin`, Stay Date Begin) (The Royal Canadian Academy of Arts 2020).

<div id="0001_119_staying-event" class="example"></div>

## Related Documentation

### External Models

* Linked.art: [Actors: People and Organizations – Addresses](https://linked.art/model/actor/#addresses)

### Entry Nodes

* [Stay Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#stay-date-begin) \| Checklist
* [Stay Date Begin Qualifier ](/collections-model/en/semantic-paths-specification/current/entry-nodes#stay-date-begin-qualifier) \| Checklist
* [Stay Date End ](/collections-model/en/semantic-paths-specification/current/entry-nodes#stay-date-end) \| Checklist
* [Stay Date End Qualifier ](/collections-model/en/semantic-paths-specification/current/entry-nodes#stay-date-end-qualifier) \| Checklist
* [Stay Place ](/collections-model/en/semantic-paths-specification/current/entry-nodes#stay-place) \| Checklist
* [Stay Type ](/collections-model/en/semantic-paths-specification/current/entry-nodes#stay-type) \| Checklist
* [Stay Used Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#stay-used-appellation) \| Checklist

### CIDOC CRM Entities

* `E7_Activity` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E7)]
* `E33_Linguistic_Object` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E33)]
* `E39_Actor` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E39)]
* `E41_Appellation` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E41)]
* `E52_Time-Span` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E52)]
* `E53_Place` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E53)]
* `E55_Type` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E55)]
* `P1_is_identified_by (identifies)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P1)]
* `P2_has_type (is_type_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P2)]
* `P4_has_time-span (is_time-span_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P4)]
* `P7_took_place_at (witnessed)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P7)]
* `P14_carried_out_by (performed)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P14)]
* `P16_used_specific_object (was_used_for)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P16)]
* `P21_had_general_purpose (was_purpose_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P21)]
* `P79_beginning_is_qualified_by` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P79)]
* `P80_end_is_qualified_by` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P80)]
* `P82a_begin_of_the_begin`
* `P82b_end_of_the_end`
* `P190_has_symbolic_content` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P190)]

## Discussion

### Rationale

In CIDOC CRM, there are two ways of documenting the location of a physical object:

* The first one is to link a physical object directly to an instance of `E53_Place` through the properties `P53_has_former_or_current_location`, `P54_has_current_permanent_location`, or `P55_has_current_location`. Those properties only allow to document the temporal bounds of the current location;
* The second option is to document the action of movement through the class `E9_Move`, because CIDOC CRM does not document states but only the defined action of moving an object from one place to another one. In this option, the changing of location can be dated. However, heritage institutions usually do not record the moving of actors, which complexifies the mapping of such data.

Both options are only applicable to physical objects which are instances of `E21_Person` but not instances of `E74_Group`. According to CIDOC CRM, groups do not move; only their members have the ability to do so. For example, the Beatles as a group cannot be present in a concert in London, only its four members can be documented as being there.

To indicate the location of a group, it can be inferred through the location of its members during the same period of time. However, it could be inaccurate as a group can be considered being somewhere even if not all members are present.

For groups that own real estates, their location can be inferred by using the class `E8_Acquisition` to record their title transfers which can then be dated and located geographically. This enables the tracing of buildings a group occupied and makes it possible to situate them on a map. Nonetheless, this pattern can only be applied to cases where the group was/is indeed the legal owner of these real estates. As such, the pattern cannot be used for cases where there is no ownership or the ownership is uncertain. Most of the time, unless it is the main element of data providers’ documentation, such information would not be recorded.

Therefore, for the sake of simplicity and accuracy, the above options are not implemented in the DOPHEDA model. The use of the class `E7_Activity` to render the action of being somewhere, called Staying Event, has been adopted as it can account for the location of all kinds of actors. 

Some groups use a place for the specific purpose of making it their headquarters. The term "headquarter" stands for the type of highest authority from which orders are issued rather than referring to a physical location (Free Dictionary 2020). As such, rather than the property `P2_has_type`, the property `P21_had_general_purpose` is employed as it helps to identify the goals and purposes of the activity instead of categorizing it. 

In addition, an actor’s specific appellation is sometimes used at a specific location. To indicate this specific location,​​ it is possible to construct a query to infer the place by finding the overlapping time between a name use activity and one or more staying activities using the [Stay Place](/collections-model/en/semantic-paths-specification/current/entry-nodes#stay-place) entry node. However, this can only work under the false assumption that the temporal data would always be recorded and available. Moreover, if an actor bears two different names at the same time, it would be impossible to use an algorithm to determine which one was used for which location. Thus, modelling the connection between the appellation and its location is deemed to be a better solution. Two options appear:

* The property `P16_used_specific_object (was_used_for)` is used to connect the appellation and the staying activity, from which the information on the place is rendered by using the property `P7_took_place_at`. It means that during the stay at this place, the actor used this appellation;
* The property `P7_took_place_at` is used to directly connect the use activity of the appellation to the place. It means that the appellation was used for this activity that occured in one or more places.

Though these differ slightly in terms of semantics, both allow to indicate the location associated with the appellation. However, the name use activity itself might not be situated in space per se. For example, Charles Dodgson used the pseudonym Lewis Carroll for his writing activity, and he also stayed at a place under this name. A direct link between the name use activity and the place implies that the use of that name for writing actually happened in that place, but it might not be the case. On the other hand, it is more accurate to say that while staying at this place, the actor has gone by this appellation which was used in this activity. Thus, the first option (i.e. linking the staying event to the appellation) should be applied. 

### Limitations

The DOPHEDA model cannot adequately accommodate the description of migratory flows since it only defines the moments between several moves. According to the open world assumption, it is impossible to determine the duration of a trip by comparing the end date of a staying event (Stay Date End) to the beginning date of the next (Stay Date Begin) since there may be other events between the two.

### Related GitHub Issues

* [Issue #18 "How to model groups that are present at different places at the same time?"](https://github.com/chin-rcip/collections-model/issues/18)
* [Issue #31 "Move, Sojourn, Acquisition, Establishing: how to model the geographical presence of Actors?"](https://github.com/chin-rcip/collections-model/issues/31)
* [Issue #49 "How to model Legal Headquarter Attribution?"](https://github.com/chin-rcip/collections-model/issues/49)

### Edge Cases

Yousuf Karsh spent 29 days on the liner Versailles when he left Lebanon to immigrate to Canada (Karsh n.d.). He therefore stayed for 29 days in the same place (i.e. the boat). However, in practice, this is a trip, so it might be fairer to document Karsh's time spent in Lebanon and Canada respectively. Obviously, by doing this, the data does not document the travel, which was certainly very impactful on the artist's life. This edge case shows that the line between moving and staying is blurred. If an archive indicates someone's presence somewhere, it may be that they lived there, or that they were simply travelling to another place.

## Bibliography

Bekiari, Chryssoula, George Bruseker, Martin Doerr, Christian-Emil Ore, Stephen Stead, and Athanasios Velios, eds. *Definition of the CIDOC Conceptual Reference Model*. CIDOC CRM Documentations, 7.1. Paris, FR-IDF: CIDOC CRM Special Interest Group, 2021. [http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf](http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf).

Editors of Encyclopædia Britannica. "Cultural Globalization - The Persistence of Local Culture." *Encyclopædia Britannica*. London, UK-LDN: Encyclopædia Britannica, n.d. [https://www.britannica.com/science/cultural-globalization](https://www.britannica.com/science/cultural-globalization).

Free Dictionary. "Headquarters." *The Free Dictionary*. Huntington Valley, US-PA: Farlex, 2020. [https://www.thefreedictionary.com/headquarters](https://www.thefreedictionary.com/headquarters).

Karsh, Yousuf. "A Brief Biography." *Yousuf Karsh* (blog). n.d. [https://karsh.org/a-brief-biography/](https://karsh.org/a-brief-biography/).

The Royal Canadian Academy of Arts (RCA). "News." RCA/ARC, 2020. [https://rca-arc.ca/en/news](https://rca-arc.ca/en/news).

