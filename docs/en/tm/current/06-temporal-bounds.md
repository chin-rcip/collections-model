---
layout: page
language: en
title: Temporal Bounds
permalink: /en/target-model/current/temporal-bounds
other_link: /fr/modele-cible/actuel/limites-temporelles
sidebar: tm22
date: 2022-03-31
description: The Actors Target Model Specification semantically models actors in a heritage context. Patterns most relevant to actors' lives are presented along with diagrams and examples illustrating them, as well as a record and explanation of relevant decisions that were made when developing said patterns. This is a theoretical documentation that has never been tested or implemented.
---

Version 2.2 ([Previous versions](/collections-model/en/versions))

## At Glance

This pattern can be used to record dates for events recorded in the DOPHEDA knowledge graph. It includes:

* The date boundaries for the time-span of events;
* The qualifiers for those dates.

This pattern covers dates in a specific format. Therefore, it does not cover: 

* Dates in strings (see the [Messy Data](/collections-model/en/target-model/current/messy-data) pattern);
* The relative chronology of events (e.g. this happened before that); 
* A datation process (e.g. radiocarbon dating). 

## Introduction and Context

### Theoretical Background

Understandings of time differ across societies and can be linear, cyclical, or include coexisting understandings of past, present, and future (Fuentes 2009; Peer 2009; Simonton 2009). Even though a linear and continuous approach is common today (Pollard 2009, 126-127; Emery et al. 2020; Savitt 2017), with the Gregorian calendar being the main business calendar internationally, other calendars are frequently used locally (see a current list on [Wikipedia](https://en.wikipedia.org/wiki/Calendar_era)), and sometimes simultaneously as populations might employ more than a single calendar in their everyday lives. This also applies historically as different methods of recording time (e.g. solar or lunar calendar) result in substantial challenges when it comes to heritage datation (e.g. there is a difference of approximately 11 days between a solar and a lunar year, the Gregorian and Hijri calendars do not coincide with one another) (Richards 1999, 89-100).

This is challenging historically because the date of an event provides information on its context that is crucial to its adequate understanding. Social sciences interested in the past such as history or archæology, especially, rely heavily on understandings of time when creating timelines or locating historical events in a measured chronological sequence and have developed two kinds of chronology to address the sequencing of events: relative and absolute chronology.

* Relative chronology is the structuration of events or periods in relation to one another, independently of their respective dates. It is especially useful in archæology where stratigraphic or typologic sequences help understand the history of a site or structure the periodization of a period. Establishing relationships between different relative chronologies (such as two different and distant stratigraphies within an archæological site, or between multiple typologies) is however difficult without absolute chronologies.
* Absolute chronology is the location in time of any particular event or the measuring of the time lapse between events. It helps establish where, in a timeline, an event occured in order to better contextualize it with regards to other contemporaneous events. Absolute chronology can be obtained by analyzing recorded events in textual sources, or with the help of modern dating sciences such as radiocarbon dating.

To fully understand past events, both types of chronology should be used together, placing events in a sequence to one another (relative chronology), as well as refining the sequence through precise dating (absolute chronology). 

### Statement of Need

In the heritage sector, like in the social sciences, chronological data is fundamental to the contextualization and understanding of information. Domain experts routinely need to temporally situate events and relate them to other entities to ascertain the relevance and validity of information. Moreover, especially in historical fields such as art history or archæology, date fuzziness is not only frequent, but also meaningful so that chronological uncertainty must be adequately reflected in datasets and the models they are mapped to.

In addition, with the advent of quantitative analysis in the social and cultural sciences, researchers often need to query and mobilize such data to offer statistical perspectives on it or to visualize it in the form of timelines, for example. To facilitate such work at scale, it is best to encode dates in a homogeneous and standardized fashion.

There is a distinction between the act of dating an event and the date that results from the datation process. While the activity of datation can also be expressed in a semantic knowledge graph, the focus of this pattern is about the date itself and how to represent it in a knowledge graph, without a semantic representation of relative chronologies. 

## Description of the Pattern

Time intervals in CIDOC CRM are modelled using the class `E52_Time-Span`. Each instance of `E2_Temporal_Entity` or of one of its sub-classes is linked to an instance of `E52_Time-Span` through the property `P4_has_time-span`.

This instance of `E52_Time-Span` can be delimited through the use of at least one of four properties representing specific dates: 

* `P82a_begin_of_the_begin` indicates that the time-span of the event may at the earliest have started on that date;
* `P81a_end_of_the_begin` indicates that the time-span of the event has at the latest started on that date;
* `P81b_begin_of_the_end` indicates that the time-span of the event lasted at least until that date;
* `P82b_end_of_the_end` indicates that the time-span of the event may have lasted until that date.

Because the properties `P82a_begin_of_the_begin` and `P82b_end_of_the_end` are the most encompassing delimiters of the event, they should be used systematically. The properties `P81a_end_of_the_begin` and `P81b_begin_of_the_end` should only be used when such precise information is available.

Structured dates must be formatted using the `xsd:dateTime` standard. For more information on this standard, see the [W3C Specification](https://www.w3.org/TR/xmlschema-2/#isoformats).

It is also possible to add qualifiers to dates with the properties `P79_beginning_is_qualified_by` and `P80_end_is_qualified_by` in conjunction with an instance of `rdfs:Literal`. Such qualifiers can include commentaries (e.g. presumed date) or typically used qualifiers (e.g. circa, BC, etc.). Instead of adding qualifiers to express time (such as before, after, etc.), cataloguers are encouraged to document time intervals solely with the CIDOC CRM properties in order to allow better time interval computation mechanisms. For example, if an event happened before a specific day, only the property `P82b_end_of_the_end` should be used, without the need to qualify it with the string "Before". Similarly, if a date is qualified as "Circa", it is best to document its temporal bounds with the appropriate time interval based on the data context.

## Diagram

<a name="018_Pattern_TemporalBounds_p"></a>018_Pattern_TemporalBounds_p

<iframe frameborder="0" style="width:100%;height:400px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=018_Pattern_TemporalBounds_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1UZlP5AcGE-fv4-lFiW6jO126kS3mp6id%26export%3Ddownload"></iframe>

## Examples

### Example 1

Yousuf Karsh was born at some time on the 23rd of December 1908. The earliest moment at which his birth event might have happened is on the first minute of that day (`P82a_begin_of_the_begin`, Birth Date Begin "1908-12-23T00:00:00"), and the latest moment at which his birth event might have ended is on the last minute of that day (`P82b_end_of_the_end`, Birth Date End "1908-12-23T23:59:59).

<div id="0001_100_temporal-bounds" class="example"></div>

### Example 2

Appius Claudius Cæcus, responsible for the construction of Ancient Rome's Via Appia, is often mentioned in literary sources though his birth date is unknown. The earliest recorded date at which he is considered to have been alive is when he was made censor in 312 BCE, which indicates that his birth happened before this date (`P82b_end_of_the_end`, Birth Date End "-312-12-31T23:59:59") (Humm 2005).

<div id="0001_101_temporal-bounds" class="example"></div>

## Related Documentation

### External Models

* Linked.art: [Time-Span](https://linked.art/model/base/#time-span-details)
* SARI: [Event Reference Data Model – Existence](https://docs.swissartresearch.net/et/event/#existence)

### Entry Nodes

* [Actor Appellation Use Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-appellation-use-date-begin) \| Checklist
* [Actor Appellation Use Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-appellation-use-date-begin-qualifier) \| Checklist
* [Actor Appellation Use Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-appellation-use-date-end) \| Checklist
* [Actor Appellation Use Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-appellation-use-date-end-qualifier) \| Checklist
* [Birth Date Begin](link to come) \| Checklist
* [Birth Date Begin Qualifier](link to come) \| Checklist
* [Birth Date End](link to come) \| Checklist
* [Birth Date End Qualifier](link to come) \| Checklist
* [Dataset Creation Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#dataset-creation-date-begin) \| Checklist
* [Dataset Creation Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#dataset-creation-date-end) \| Checklist
* [Death Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#death-date-begin) \| Checklist
* [Death Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#death-date-begin-qualifier) \| Checklist
* [Death Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#death-date-end) \| Checklist
* [Death Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#death-date-end-qualifier) \| Checklist
* [Dissolution Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#dissolution-date-begin) \| Checklist
* [Dissolution Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#dissolution-date-begin-qualifier) \| Checklist
* [Dissolution Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#dissolution-date-end) \| Checklist
* [Dissolution Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#dissolution-date-end-qualifier) \| Checklist
* [Family Joining Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#family-joining-date-begin) \| Checklist
* [Family Joining Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#family-joining-date-begin-qualifier) \| Checklist
* [Family Joining Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#family-joining-date-end) \| Checklist
* [Family Joining Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#family-joining-date-end-qualifier) \| Checklist
* [Family Leaving Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#family-leaving-date-begin) \| Checklist
* [Family Leaving Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#family-leaving-date-begin-qualifier) \| Checklist
* [Family Leaving Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#family-leaving-date-end) \| Checklist
* [Family Leaving Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#family-leaving-date-end-qualifier) \| Checklist
* [Formation Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#formation-date-begin) \| Checklist
* [Formation Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#formation-date-begin-qualifier) \| Checklist
* [Formation Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#formation-date-end) \| Checklist
* [Formation Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#formation-date-end-qualifier) \| Checklist
* [Flourishing Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#flourishing-date-begin) \| Checklist
* [Flourishing Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#flourishing-date-begin-qualifier) \| Checklist
* [Flourishing Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#flourishing-date-end) \| Checklist
* [Flourishing Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#flourishing-date-end-qualifier) \| Checklist
* [Group Joining Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#group-joining-date-begin) \| Checklist
* [Group Joining Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#group-joining-date-begin-qualifier) \| Checklist
* [Group Joining Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#group-joining-date-end) \| Checklist
* [Group Joining Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#group-joining-date-end-qualifier) \| Checklist
* [Group Leaving Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#group-leaving-date-begin) \| Checklist
* [Group Leaving Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#group-leaving-date-begin-qualifier) \| Checklist
* [Group Leaving Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#group-leaving-date-end) \| Checklist
* [Group Leaving Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#group-leaving-date-end-qualifier) \| Checklist
* [Occupation Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#occupation-date-begin) \| Checklist
* [Occupation Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#occupation-date-begin-qualifier) \| Checklist
* [Occupation Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#occupation-date-end) \| Checklist
* [Occupation Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#occupation-date-end-qualifier) \| Checklist
* [Production Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#production-date-begin) \| Checklist
* [Production Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#production-date-begin-qualifier) \| Checklist
* [Production Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#production-date-end) \| Checklist
* [Production Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#production-date-end-qualifier) \| Checklist
* [Record Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#record-date-begin) \| Checklist
* [Record Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#record-date-end) \| Checklist
* [Relationship Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#relationship-date-begin) \| Checklist
* [Relationship Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#relationship-date-begin-qualifier) \| Checklist
* [Relationship Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#relationship-date-end) \| Checklist
* [Relationship Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#relationship-date-end-qualifier) \| Checklist
* [Social Status Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#social-status-date-begin) \| Checklist
* [Social Status Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#social-status-date-begin-qualifier) \| Checklist
* [Social Status Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#social-status-date-end) \| Checklist
* [Social Status Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#social-status-date-end-qualifier) \| Checklist
* [Stay Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#stay-date-begin) \| Checklist
* [Stay Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#stay-date-begin-qualifier) \| Checklist
* [Stay Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#stay-date-end) \| Checklist
* [Stay Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#stay-date-end-qualifier) \| Checklist

### CIDOC CRM Entities

* `E52_Time-Span` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E52)]
* `P4_has_time-span (is_time-span_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P4)]
* `P79_beginning_is_qualified_by` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P79)]
* `P80_end_is_qualified_by` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P80)]
* `P81a_end_of_the_begin`
* `P81b_begin_of_the_end`
* `P82a_begin_of_the_begin`
* `P82b_end_of_the_end`

## Discussion

### Rationale

Temporal entities (i.e. perdurant ones such as events or periods) are at the core of the CIDOC CRM ontology. They gather actors and objects (conceptual or physical), and serve as geographical and temporal constraints to endurant entities (i.e. said actors and objects). The description of time in CIDOC CRM is always made through time-spans and nothing can be defined by a single point in time (Bekiari et al. 2021, 34-46; CRM SIG 2020). Two ways of defining time-spans are possible in CIDOC CRM: 

* By documenting the duration of an event;
* By documenting the boundaries of a time-span. There are four possible boundaries:

  * `P82a_begin_of_the_begin`, which indicates that the time-span of an event may at the earliest have started on that date;

  * `P81a_end_of_the_begin`, which indicates that the time-span of an event has at the latest started on that date;

  * `P81b_begin_of_the_end`, which indicates that the time-span of an event lasted at least until that date;

  * `P82b_end_of_the_end`, which indicates that the time-span of an event may have lasted until that date.

The diagram below illustrates the differences between these four properties (see the [CIDOC CRM documentation](http://www.cidoc-crm.org/guidelines-for-using-p82a-p82b-p81a-p81b) for more information):

<a name="017_Pattern_E2TemporalEntities_p"></a>017_Pattern_E2TemporalEntities_p

<iframe frameborder="0" style="width:100%;height:400px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=017_Pattern_E2TemporalEntities_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1QIVzLVjvu4H8v_sU63j4BttQrpq9FhwA%26export%3Ddownload"></iframe>

In the DOPHEDA model, events are defined by two external boundaries: the earliest moment at which an event might have started, and the lastest moment at which it might have ended. The interval between these two boundaries can be as long as necessary to represent the uncertain nature of a piece of information (e.g. if one only knows that something occurred in 1999, the time-span can be as precise as 1999-01-01 to 1999-12-31, and then specified through qualifiers). 

The properties `P82a_begin_of_the_begin` and `P82b_end_of_the_end` are by default used as boundaries to describe time-spans, rather than the properties `P81a_end_of_begin` and `P81b_begin_of_the_end` because:

* It is easier for the user to simply rely on two properties rather than four, especially when the distinction between all of them is not easy to grasp;
* Relying on the uttermost boundaries is less likely to produce errors as they are the most encompassing properties, a practice that also produces less Temporal Bounds entry nodes. 

For example, when dating a birth date, it is more in line with the majority of available data to use the properties `P82a_begin_of_the_begin` and `P82b_end_of_the_end`, and to state that the event happened at some time between the first second of the day and the last second of the day than to use the properties `P81a_end_of_begin` and `P81b_begin_of_the_end`.

However, in some cases, the sole use of the properties `P82a_begin_of_the_begin` and `P82b_end_of_the_end` would be problematic. For example, the existence of an occupation as painter could be known only by the publication of an artwork. In such a case, the beginning of the occupation would be dated at some unknown time before the publication of this first artwork and at the latest just before it. It is therefore only possible to document the latest moment when the beginning of the occupation happened; in other words, the property `P81a_end_of_the_begin` can be used, but the property `P82a_begin_of_the_begin` cannot because the earliest moment of the beginning of the occupation is unknown.

For the sake of simplicity and for limiting the number of nodes for the Temporal Bounds pattern, CHIN recommends to only rely on the properties `P82a_begin_of_the_begin` and `P82b_end_of_the_end`. Should a user wish to implement the properties `P81a_end_of_the_begin` and `P81b_begin_of_the_end`, a discussion with CHIN should happen beforehand (see [Issue #80](https://github.com/chin-rcip/collections-model/issues/80)). 

By relying on the `xsd:dateTime` standard, some specific rules must be applied on dates that are before the common era (BCE), but these differ depending on the version of `xsd:dateTime` used:

* Version 1.0: In this version, the value "0001" is interpreted as being year 1 CE, and "-0001" as being year 1 BCE. As there is no year 0, the value "0000" is considered as an invalid lexical representation (Biron & Malhotra 2004);
* Version 1.1: In this more recent version, the value "0000" is accepted and valid, and represents the year 1 BCE. The value "-0001" thus represents year 2 BCE. This representation is said to simplify the interval arithmetic, but can obviously create some difficulties in the recording and mapping of dates before the common era (Peterson et al. 2012) (see [Issue #81](https://github.com/chin-rcip/collections-model/issues/81)). 

As explained in the Description of the Pattern, each date can be qualified by the addition of a string attached to an instance of `E52_Time-Span`. This enables more expressiveness in the description of time because any kind of textual information linked to the dates can be added, such as "Circa", "Around", "Unsure", etc. However, because these qualifiers are strings and not instances of `E55_Type`, it is not possible to directly use URIs for them, so that no LOD vocabulary can be used for qualifiers, even though it is possible to limit the number of terms employed as qualifiers.

### Limitations

Relying mainly on the properties `P82a_begin_of_the_begin` and `P82b_end_of_the_end` is easiest when managing dates, and less of a burden to users who do not need to understand the complexity of the different temporal properties of CIDOC CRM. However, this default option is less semantically versatile.

Using the `xsd:dateTime` standard has significant benefits because it enables complex computational queries relying on dates. However, this standard cannot manage unstructured formats such as strings (e.g. "the duration of the Ming Dynasty") which must then be documented using the [Messy Data](/collections-model/en/target-model/current/messy-data) pattern. Moreover, the `xsd:dateTime` standard relies on a year/month/day structure which is not in use in many cultures (e.g. the USA where the structure is year/day/month or cultures using a different calendar). This could lead to errors if dates are not carefully mapped or converted by the provider.

The use of the `xsd:dateTime` standard also imposes the use of the Gregorian calendar to document time which indicates that it is mandatory to convert all dates to their Gregorian calendar equivalent before mapping the information to the Target Model Specification. In addition to this technical difficulty, the cultural diversity of the information displayed is limited.

Because datation information is often uncertain, the use of qualifiers (the properties `P79_beginning_is_qualified_by` and `P80_end_is_qualified_by`) as strings is sometimes necessary. However, this is less semantically rich than if qualifiers were relying on controlled vocabularies in addition to being interpretable only by humans. As a result, such information is lost in the context of quantitative queries.

This pattern does not represent relative chronologies and its function is to aid in translating known dates within a date system. There are properties dedicated to relative chronology representation in CIDOC CRM, but they have not been mobilized here (Bekiari 2021, 43-47) (see [Issue #79](https://github.com/chin-rcip/collections-model/issues/79)).

### Related GitHub Issues

* [Issue #51 "Should we try to avoid date qualifiers?"](https://github.com/chin-rcip/collections-model/issues/51)
* [Issue #79 "Is There a Need for a Relative Chronology Pattern?"](https://github.com/chin-rcip/collections-model/issues/79)
* [Issue #80 "How to handle the use of P81a and P81b in the Target Model?"](https://github.com/chin-rcip/collections-model/issues/80)
* [Issue #81 "How to use XSD:dateTime for BCE dates?"](https://github.com/chin-rcip/collections-model/issues/81)

### Edge Cases

#### Example 1 {#edge-cases-example-1}

The production of certain objects, such as the white and blue porcelain bowl n°G01.2.20 of the Ming Dynasty Wanli Period from the Gardiner Museum (Gardiner Museum 2021), could be dated with the name of a period when the date of the production itself is unknown. Such use of a period’s name for delimiting the time-span of an event could also occur for periods that do not have clear chronological limits (i.e. whose boundaries might be updated or documented more precisely with additional research on the period rather than on the object). This pattern does not allow such relative documentation, and the name of a period should be modelled according to the [Messy Data](/collections-model/en/target-model/current/messy-data) pattern (see [Issue #79](https://github.com/chin-rcip/collections-model/issues/) for discussions about relative chronology).

#### Example 2 {#edge-cases-example-2}

Since the date associated with the property `P82b_end_of_the_end` is inclusive, the end date is included in the time-span described (see [Linked.art’s Issue #371](https://github.com/linked-art/linked.art/issues/371) and [CRM SIG’s Issue #417](http://www.cidoc-crm.org/Issue/ID-417-beginofthebegin-endoftheend-is-excluded-from-time-range)). This can lead to some confusion when events continue into the very last moments in time. For example, it is impossible to document the time interval that marks the end of Yousuf Karsh's year of birth. The moment associated with `P82b_end_of_the_end` would be indicated by the value "1908-12-31T23:59:59" and therefore, anything that happened in the last moments of the year 1908 would not be captured by the model. To include the last moments of the year 1908, it would be necessary to use the value "1909-01-01T00:00:00", but in this case the start of 1909 would be part of the year-end event of 1908. Events that involve change from one period to another can therefore be categorized in different ways depending on the understanding of the person entering the information.

## Bibliography

Bekiari, Chryssoula, George Bruseker, Martin Doerr, Christian-Emil Ore, Stephen Stead, and Athanasios Velios. *Definition of the CIDOC Conceptual Reference Model*. CIDOC CRM Documentations, 7.1.1. Paris, FR-IDF: International Council of Museums (ICOM), 2021. [http://www.cidoc-crm.org/sites/default/files/cidoc_crm_v.7.1.1.pdf](http://www.cidoc-crm.org/sites/default/files/cidoc_crm_v.7.1.1.pdf)

Biron, Paul V., and Malhotra Ashok. *XML Schema Part 2: Datatypes Second Edition*. W3C Recommendation, 2004. [https://www.w3.org/TR/xmlschema-2/#dateTime](https://www.w3.org/TR/xmlschema-2/#dateTime).

CIDOC CRM Special Interest Group. "Issue 417: begin_of_the_begin /end_of_the_end is Excluded from Time Range?" *CIDOC CRM Issues*. 2020. [http://www.cidoc-crm.org/Issue/ID-417-beginofthebegin-endoftheend-is-excluded-from-time-range](http://www.cidoc-crm.org/Issue/ID-417-beginofthebegin-endoftheend-is-excluded-from-time-range).

Emery, Nina, Ned Markosian, and Meghan Sullivan. "Time." *The Stanford Encyclopedia of Philosophy*. Stanford, US-CA: Metaphysics Research Lab, Stanford University, 2020.

Fuentes, Catherine M. Mitchell. "Dreamtime, Arboriginal." *Encyclopedia of Time: Science, Philosophie, Theology, & Culture*, edited by H. James Birx. Thousand Oaks, US-CA: Sage Publications, 2009: 346-348.

Gardiner Museum. *Bowl with Fruit and Lotus*. Gardiner Museum. 2021. [http://emuseum.gardinermuseum.com/objects/2005/bowl-with-fruit-and-lotus](http://emuseum.gardinermuseum.com/objects/2005/bowl-with-fruit-and-lotus).

Hornung, Erik, Rolf Krauss, and David A. Warburton, eds. *Ancient Egyptian Chronology*. Leiden, NL-ZH; Boston, US-MA: Brill, 2006.

Humm, Michel. "Les sources littéraires sur Appius Claudius Cæcus." *Appius Claudius Cæcus : La République accomplie*. Rome, ITA-RM: Publications de l’École française de Rome, 2005: 35–97.

Linked.art. "Issue 371: End_of_the_end Is Included, Not Excluded." Issues. GitHub. 2020. [https://github.com/linked-art/linked.art/issues/371](https://github.com/linked-art/linked.art/issues/371).

Peer, Bethany. "Calendar, Mayan." *Encyclopedia of Time: Science, Philosophy, Theology, & Culture*, edited by H James Birx. Thousand Oaks, US-CA: Sage Publications, 2009: 134–135.

Peterson, David, Shudi (Sandy) Gao, Ashok Malhotra, C. M. Sperberg-McQueen, and Henry S. Thompson. *W3C XML Schema Definition Language (XSD) 1.1 Part 2: Datatypes*. W3C Recommendation, April 5, 2012. [https://www.w3.org/TR/xmlschema11-2/#dateTime](https://www.w3.org/TR/xmlschema11-2/#dateTime).

Phillips, Jocelyn. "Calendar, Astronomical." *Encyclopedia of Time: Science, Philosophy, Theology, & Culture*, edited by H James Birx. Thousand Oaks, US-CA: Sage Publications, 2009: 124-125.

Pollard, A. M. "Measuring the Passage of Time: Achievements and Challenges in Archæological Dating." *The Oxford Handbook of Archæology*, edited by Chris Gosden, Barry Cunliffe, and Rosemary A. Joyce. New York, US-NY; Oxford, UK-OXF: Oxford University Press, 2009: 123–139.

Railways Archive. "Statutes (Definition of Time) Act." *Railways Archive*. 2021. [https://www.railwaysarchive.co.uk/docsummary.php?docID=929](https://www.railwaysarchive.co.uk/docsummary.php?docID=929).

Richards, E. G. *Mapping Time: The Calendar and Its History*. Oxford, UK-OXF: Oxford University Press, 1999.

Salmon, Helena Theresa. "Calendar, Islamic." *Encyclopedia of Time: Science, Philosophy, Theology, & Culture*, edited by H James Birx. Thousand Oaks, US-CA: Sage Publications, 2009: 131–132.

Savitt, Steven. "Being and Becoming in Modern Physics." *The Stanford Encyclopedia of Philosophy*. Stanford, US-CA: Metaphysics Research Lab, Stanford University, 2017. [https://plato.stanford.edu/entries/spacetime-bebecome/](https://plato.stanford.edu/entries/spacetime-bebecome/).

Simonton, Michæl J. "Calendar, Megalithic." *Encyclopedia of Time: Science, Philosophy, Theology, & Culture*, edited by H James Birx. Thousand Oaks, US-CA: Sage Publications, 2009: 137–141.

Smyntyna, Olena V. "Chronology." *Encyclopedia of Time: Science, Philosophy, Theology, & Culture*, edited by H James Birx. Thousand Oaks, US-CA: Sage Publications, 2009: 183–186.

Wikipedia. "Calendar Era." *Wikipedia*. San Francisco, US-CA: Wikipedia, 2022. [https://en.wikipedia.org/w/index.php?title=Calendar_era&oldid=1096791211](https://en.wikipedia.org/w/index.php?title=Calendar_era&oldid=1096791211).

