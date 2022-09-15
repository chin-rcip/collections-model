---
layout: page
language: en
title: Artefact Production
permalink: /en/target-model/current/artefact-production
other_link: /fr/modele-cible/actuel/production-dartefact
sidebar: tm22
date: 2022-03-31
description: The Actors Target Model Specification semantically models actors in a heritage context. Patterns most relevant to actors' lives are presented along with diagrams and examples illustrating them, as well as a record and explanation of relevant decisions that were made when developing said patterns. This is a theoretical documentation that has never been tested or implemented.
---

Version 2.2 ([Previous versions](/collections-model/en/versions))

## At Glance

This pattern can be used to minimally record the information pertaining to the production of a tangible artefact. It includes: 

* The producer·s’ role·s in the creation of an artefact; 
* The moment when an artefact was created; 
* The place where an artefact was created;
* The level of priority of its producer.

It does not include: 

* The title of the artefact (refer to the [Artefact](/collections-model/en/target-model/current/artefact) pattern instead); 
* Other identifiers of the artefact (refer to the [Artefact](/collections-model/en/target-model/current/artefact) pattern instead). 

The information pertaining to artefacts themselves, as well as to their collecting, researching, handling, and preserving is currently not accounted for in this pattern. Minimal information necessary to identify rather than describe artefacts has been prioritized.

## Introduction and Context

### Theoretical Background

Fundamentally, heritage producing, researching, and collecting is a form of human-object relation that is increasingly understood beyond the status of the human as meaning-maker and the object as illustrative production (Macdonald 2011, 93). Rather, artefacts are more and more considered as spaces of interrelated meanings with value (Bann 2003, 120). As such, the understanding of what qualifies as an artefact has greatly evolved in the past twenty years to include intangible cultural heritage as well as material objects. Because the relationship between human and artefacts is meaningful to the heritage sector, it is the subject of a multiplicity of researches and practices, especially in the case of intangible heritage, which is often embodied in human and living ways (Đerić, Neyrinck, & Seghers 2020, 11).

### Statement of Need

In the context of the DOPHEDA model, artefacts are understood to encompass both material objects and intangible constructs. Minimal identificatory information should be documentable so that physical artefacts, which are often the central unit of heritage database records, can be represented in the model. For such purposes, a number of core informations are typically used across disciplines. An assessment of what they are has been done by the J. Paul Getty Trust when establishing the Object ID, an international standard for cultural goods intended to prevent the illicit trade of artefacts worldwide (ICOM 2021). These standard identificatory fields are the: 

* Type of object;
* Materials and techniques;
* Measurement;
* Inscriptions and markings;
* Distinguishing features;
* Title;
* Subject;
* Date or period;
* Maker. 

Because the sole function of the Artefact Production pattern is to account for objects as the core unit of recording in heritage collections, not all of these elements are addressed in the model; only the maker’s role and the date or period are taken into consideration. Titles and identifiers are addressed in the [Artefact](/collections-model/en/target-model/current/artefact) pattern.

## Description of the Pattern

The information pertaining to the maker of the artefact’s identification and role is centered around an instance of `PC14_carried_out_by` linked to an instance of `E12_Production` through the property `P01_has_domain`. This instance of `PC14_carried_out_by` points to an instance of `E39_Actor` identifying the maker through the property `P02_has_range`. 

To clarify the role of this maker, the same instance of `PC14_carried_out_by` is linked to the [Production Actor Role](/collections-model/en/semantic-paths-specification/current/entry-nodes#production-actor-role) value (an instance of `E55_Type`) by the property `P14.1_in_the_role_of`. This instance of `E55_Type` is qualified by another instance of `E55_Type` (a specified qualifier node) labelled "Actor Role" through the property `P2_has_type`. 

To clarify the priority of the actor in the production of the artefact, the same instance of `PC14_carried_out_by` is also linked to the [Production Actor Priority](/collections-model/en/semantic-paths-specification/current/entry-nodes#production-actor-priority) value (an instance of `E55_Type`) by the property `P14.1_in_the_role_of`. This instance of `E55_Type` is qualified by another instance of `E55_Type` (a specified qualifier node) labelled "Actor Priority" by the property `P2_has_type`. 

Where and when the artefact was made are centered around an instance of `E12_Production` that points to the created object (an instance of `E22_Human-Made_Object`) through the property `P108_has_produced`.

The [Production Place](/collections-model/en/semantic-paths-specification/current/entry-nodes#production-place) value (an instance of `E53_Place`) is linked to that instance of `E12_Production` by the property `P7_took_place_at`. 

The time the production occurred is indicated using the [Temporal Bounds](/collections-model/en/target-model/current/temporal-bounds) pattern linked to the instance of `E12_Production` through the property `P4_has_time-span` with values extracted from the [Production Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#production-date-begin), [Production Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#production-date-begin-qualifier), [Production Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#production-date-end), and [Production Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#production-date-end-qualifier) entry nodes. 

## Diagram

<a name="070_Pattern_Production_p"></a>070_Pattern_Production_p

<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=070_Pattern_Production_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1c87fCMFEouMSzw6gRC_kiUT3IFqG8iOu%26export%3Ddownload"></iframe>

## Examples

### Example 1

*Canadissimo* (`P190_has_symbolic_content`, Artefact Appellation) was made by art collective BGL (`P190_has_symbolic_content`, Production Actor Appellation) and presented at the Canada Pavilion of the Venice Biennale (`P7_took_place_at`, Production Place) in 2015 (`P82a_begin_of_the_begin`, Production Date Begin; `P79_beginning_is_qualified_by`, Production Date Begin Qualifier "or before"; `P82b_end_of_the_end`, Production Date End; `P80_end_is_qualified_by`, Production Date End Qualifier "or before"). BGL is comprised of Jasmin Bilodeau (`P2_has_type`, Production Actor Role "Creator"; `P2_has_type`, Production Actor Priority "1"), Sébastien Giguère (`P2_has_type`, Production Actor Role "Creator"; `P2_has_type`, Production Actor Priority "1"), and Nicolas Laverdière (`P2_has_type`, Production Actor Role "Creator"; `P2_has_type`, Production Actor Priority "1") (Wikipedia 2022

<div id="0001_503_artefact-production" class="example"></div>

### Example 2

Yousuf Karsh’s [*Self-Portrait*](https://upload.wikimedia.org/wikipedia/commons/3/3a/Yousuf-Karsh.jpg) (`P190_has_symbolic_content`, Artefact Appellation) was taken in Ottawa, CA-ON (`P7_took_place_at`, Production Place) in 1938 (`P82a_begin_of_the_begin`, Production Date Begin; `P82b_end_of_the_end`, Production Date End) by Karsh (`P2_has_type`, Production Actor Role "Creator") who was its sole creator (`P2_has_type`, Production Actor Priority "1") (Karsh 1938). 

<div id="0001_500_artefact-production" class="example"></div>

### Example 3

[*Flightstop*](https://commons.wikimedia.org/wiki/File:Flight_stop.jpg) (`P190_has_symbolic_content`, Artefact Appellation) by artist Michael Snow (`P2_has_type`, Production Actor Role "Creator"; `P2_has_type`, Production Actor Priority "1") has been displayed at the Toronto Eaton Centre since 1979 (`P82a_begin_of_the_begin`, Production Date Begin; `P82b_end_of_the_end`, Production Date End) when it was made and installed. The image available in Wikimedia Commons has been taken by Simon Law (Law 2011; Snow 1979; Wikipedia 2021). 

<div id="0001_501_artefact-production" class="example"></div>

### Example 4

John William Waterhouse’s [*"I am half sick of shadows, said The Lady of Shalott" (Alfred, Lord Tennyson, The Lady of Shalott, Part II)*](https://en.wikipedia.org/wiki/File:John_William_Waterhouse_-_I_am_half-sick_of_shadows,_said_the_lady_of_shalott.JPG) (`P190_has_symbolic_content`, Artefact Appellation) is a 1915 (`P82a_begin_of_the_begin`, Production Date Begin; `P82b_end_of_the_end`, Production Date End) painting done solely by the artist (`P2_has_type`, Production Actor Role "Creator"; `P2_has_type`, Production Actor Priority "1") (Waterhouse 1915; Wikipedia 2018). 

<div id="0001_502_artefact-production" class="example"></div>

## Related Documentation

### External Models

* Linked.art: [Object Names and Identifiers](https://linked.art/model/base/)
* SARI: [Artwork Reference Data Model – Existence](https://docs.swissartresearch.net/et/artwork/#existence)
* SARI: [Artwork Reference Data Model – Actor Relations](https://docs.swissartresearch.net/et/artwork/#actor-relations) 

### Entry Nodes

* [Production Actor Priority](/collections-model/en/semantic-paths-specification/current/entry-nodes#production-actor-priority) \| Checklist
* [Production Actor Role](/collections-model/en/semantic-paths-specification/current/entry-nodes#production-actor-role) \| Checklist
* [Production Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#production-date-begin) \| Checklist
* [Production Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#production-date-begin-qualifier) \| Checklist
* [Production Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#production-date-end) \| Checklist
* [Production Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#production-date-end-qualifier) \| Checklist
* [Production Place](/collections-model/en/semantic-paths-specification/current/entry-nodes#production-place) \| Checklist

### CIDOC CRM Entities

* `E12_Production` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E12)]
* `E22_Human-Made_Object` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E22)]
* `E39_Actor` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E39)]
* `E52_Time-Span` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E52)]
* `E53_Place` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E53)]
* `E55_Type` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E55)]
* `PC14_carried_out_by`
* `P01_has_domain (is_domain_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P01)]
* `P02_has_range (is_range_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P02)]
* `P2_has_type (is_type_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P2)]
* `P4_has_time-span (is_time-span_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P4)]
* `P7_took_place_at (witnessed)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P7)]
* `P14.1_in_the_role_of` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P14.1)]
* `P79_beginning_is_qualified_by` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P79)]
* `P80_end_is_qualified_by` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P80)]
* `P82a_begin_of_the_begin`
* `P82b_end_of_the_end`
* `P108_has_produced (was_produced_by)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P108)]

## Discussion

### Rationale

Most heritage databases center their record around a collected object rather than its producer. For functional implementation purposes, it is thus necessary to create a pattern that enables the identification of the object (the Artefact pattern) and another one for the production of the object (the Artefact Production pattern). The sole purpose of the Artefact Production pattern is to account for objects and their production as the core relation of the object to its maker.

In addition, because most institutions at the moment focus on tangible objects rather than intangible artefacts as the central units of their records, this pattern only offers the possibility to document physical objects. This explains the use of the class `E22_Human-Made_Object` which is intended to be employed for physical products rather than living practices. 

### Limitations

In addition, in the case of an artefact whose production can be decomposed into multiple sub-events (e.g. a sculpture produced with the lost-wax process could be decomposed into many events), it is not yet possible to connect several events to a unique instance of `E12_Production`. Moreover, based on the quantification of the property `P108_has_produced (was_produced_by)` in CIDOC CRM, it is not allowed to connect multiple instances of `E12_Production` to the same artefact.

### Related GitHub Issues

* [Issue #7 "E39 Creators Identification"](https://github.com/chin-rcip/collections-model/issues/7)
* [Issue #12 "How to model the priority of an actor in the production of an artefact?"](https://github.com/chin-rcip/collections-model/issues/12)
* [Issue #66 "PC11_had_participant and P11.1_in_the_role_of creation proposal"](https://github.com/chin-rcip/collections-model/issues/66)
* [Issue #69 "Records for the Object Facet"](https://github.com/chin-rcip/collections-model/issues/69)
* [Issue #71 "Fields and concepts to model for the Object Facet"](https://github.com/chin-rcip/collections-model/issues/71)

### Edge Cases

#### Example 1 {#edge-cases-example-1}

Even though this pattern enables the recording of some form of role in the production of an artefact, how to consistently and meaningfully record this information is unclear. How to determine the role and the priority will likely rely on each node in relation to the other. For example, Jeff Koons could be ranked with the highest Production Actor Priority for any of his works despite the fact that he does not physically participate in the making of them most of the time. The designers, engineers, etc. he employs would have a lower Production Actor Priority.

Also, it is unclear if the production of a work begins with its ideation or with its physical *making* into the world. What about performance or intangible productions? The use of a conceptual qualifier ascribed to dates could potentially be assessed.

#### Example 2 {#edge-cases-example-2}

A missing/unknown value for the Production Actor Role for an actor participating in a collective production can greatly limit the semantic scope of the prioritization of all actors involved. If in a production by three makers only two are prioritized, it becomes impossible to know where the non-prioritized actor is situated in relation to the others.

#### Example 3 {#edge-cases-example-3}

When an event takes place online or in a virtual universe, it could become difficult to determine its physical location. For example, an artist might produce a purely online work from a computer in Winnipeg (CA-ON), yet use a gathering platform accessible on a web server that could also be considered as the location of the production.

#### Example 4 {#edge-cases-example-4}

*Canadissimo* was made by art collective BGL and presented at the Canada Pavilion of the Venice Biennale in 2015. It could be argued that the Venice Biennale is the Exhibition Place rather than the production place, or both considering it is an installation.

## Bibliography

Bann, Stephen. "The Return to Curiosity: Shifting Paradigms in Contemporary Museum Display." *Art and Its Publics: Museum Studies at the Millennium*, edited by Andrew McClellan. New Interventions in Art History 2. Malden, US-MA: Blackwell Pub. Co, 2003: 117-132.

Đerić, Tamara Nikolić, Jorjin Neyrinck, and Evelyne Seghers. *Museums and Intangible Cultural Heritage: Towards a Third Space in the Heritage Sector, A Companion to Discover Transformative Heritage Practices for the 21st Century*. Intangible Cultural Heritage & Museums Project. Anderlecht, BE-BRU: Werkplaats immaterieel erfgoed, 2020. [https://www.ichandmuseums.eu/en/toolbox/book-museums-and-intangible-cultural-heritage/success#details](https://www.ichandmuseums.eu/en/toolbox/book-museums-and-intangible-cultural-heritage/success#details).

Doerr, Martin, and Christian Emil Ore, eds. *Definition of the CIDOC Conceptual Reference Model*. CIDOC CRM Documentations, 7.0.1. Paris, FR-IDF: International Council of Museums (ICOM), 2020. [http://www.cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.0.1_%2018-10-2020.pdf](http://www.cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.0.1_%2018-10-2020.pdf).

International Council of Museums. *Object ID*. ICOM. July 19, 2021. [https://icom.museum/en/resources/standards-guidelines/objectid/](https://icom.museum/en/resources/standards-guidelines/objectid/).

Karsh, Yousuf. *Self Portret*. Photography. 1938. This image is available from Library and Archives Canada under the reproduction reference number PA-212511 and under the MIKAN ID number 3198631. This tag does not indicate the copyright status of the attached work. A normal copyright tag is still required. See Commons: Licensing for more information. Library and Archives Canada does not allow free use of its copyrighted works. See Category: Images from Library and Archives Canada. [https://commons.wikimedia.org/wiki/File:Yousuf-Karsh.jpg](https://commons.wikimedia.org/wiki/File:Yousuf-Karsh.jpg).

Law, Simon. *Toronto Eaton Centre, Toronto, Canada*. Photography. Flickr. 2006. [https://commons.wikimedia.org/wiki/File:Flight_stop.jpg](https://commons.wikimedia.org/wiki/File:Flight_stop.jpg).

MacDonald, Sharon, ed. "Collecting Practices." *A Companion to Museum Studies*. Blackwell Companions in Cultural Studies. Malden, US-MA: John Wiley & Sons, 2011: 81–97.

Snow, Michael. *Flight Stop*. Sculpture. Flickr. 1979. [https://commons.wikimedia.org/wiki/File:Flight_stop.jpg](https://commons.wikimedia.org/wiki/File:Flight_stop.jpg).

Waterhouse, John William. *"'I Am Half Sick of Shadows,' Said The Lady of Shalott" (Alfred, Lord Tennyson, The Lady of Shalott, Part II)*. Painting, 1915. [https://en.wikipedia.org/w/index.php?title=File:John_William_Waterhouse\_-\_I_am_half-sick_of_shadows,\_said_the_lady_of_shalott.JPG&oldid=838315116](https://en.wikipedia.org/w/index.php?title=File:John_William_Waterhouse_-_I_am_half-sick_of_shadows,_said_the_lady_of_shalott.JPG&oldid=838315116).

Wikipedia. "John William Waterhouse - I Am Half-Sick of Shadows, Said the Lady of Shalott.JPG." *Wikipedia*. San Francisco, US-CA: Wikipedia, 2018. https://en.wikipedia.org/w/index.php?title=File:John_William_Waterhouse_-_I_am_half-sick_of_shadows,_said_the_lady_of_shalott.JPG&oldid=838315116.

\_\_\_. "Flight Stop." *Wikipedia*. San Francisco, US-CA: Wikipedia, 2021. [https://en.wikipedia.org/w/index.php?title=Flight_Stop&oldid=1021679066](https://en.wikipedia.org/w/index.php?title=Flight_Stop&oldid=1021679066).

\_\_\_. "BGL (artists)." *Wikipedia*. San Francisco, US-CA: Wikipedia, 2022. [https://en.wikipedia.org/wiki/BGL_(artists)](https://en.wikipedia.org/wiki/BGL_(artists)).

