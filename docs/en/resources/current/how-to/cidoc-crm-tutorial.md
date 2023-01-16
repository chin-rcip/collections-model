---
layout: page
language: en
title: CIDOC CRM Tutorial
permalink: /en/resources/current/how-to/cidoc-crm-tutorial
other_link: /fr/ressources/actuel/mode-demploi/tutoriel-cidoc-crm
sidebar: tutcidocen
group: resources
subgroup: how-to
date: 2022-03-08
description: This document explains how to use the CIDOC CRM specification to identify entities that may address an identified need. To this end, brief definitions are provided for certain concepts associated with ontologies that leverage open and linked data.
---

**Version:** 2.0

**Authors:** Marie-Pier Blain, Karine Léonard Brouillet, Philippe Michon

**Creation date:** 2021-02-01

**Update date:** 2022-03-08

**Abstract:** This document explains how to use the CIDOC CRM specification to identify entities that may address an identified need. To this end, brief definitions are provided for certain concepts associated with ontologies that leverage open and linked data.

**For information:** If you have any questions or comments about the CIDOC CRM Tutorial, please visit the [Issues](https://github.com/chin-rcip/collections-model/issues) section (and open an Issue if relevant) or send us an email at [rcip-chin@pch.gc.ca](mailto:rcip-chin@pch.gc.ca) with "CIDOC CRM Tutorial" in the subject line.


## Main Uses

* Become familiar with the main terms used in the CIDOC CRM;
* Understand and use the CIDOC CRM specification;
* Identify entities that may address a specific need.

## Context

The International Committee for Documentation's *Conceptual Reference Model* (CIDOC CRM) is a formal ontology that facilitates the integration, mediation, and exchange of heterogeneous heritage information. More specifically, it defines the underlying semantics of database schemes and structured documents used by museum and heritage institutions. In addition, it explains the logic of what those institutions document, thereby supporting semantic interoperability.

## Essential Vocabularies and Prior Knowledge

Before proceeding, anyone using CIDOC CRM, whether for modelling purposes or not, needs to understand the following terms:

* [Class](https://chin-rcip.github.io/collections-model/en/resources/current/glossary#class-noun)
* [Entity](https://chin-rcip.github.io/collections-model/en/resources/current/glossary#entity-noun)
* [Instance](https://chin-rcip.github.io/collections-model/en/resources/current/glossary#instance-noun)
* [Property](https://chin-rcip.github.io/collections-model/en/resources/current/glossary#property-noun)

## Intended Audience and Section Description

### Audience

This tutorial is intended for people who have a background knowledge of information technology and techniques, and are interested in learning about CIDOC CRM.

### Sections

* Directions for use: the versions and extensions of CIDOC CRM, the structure of the entities and the naming conventions used, the model’s conceptual framework, as well as the method of identifying appropriate entities are defined;
* Aide-mémoire: key elements and important actions are detailed;
* For more information: suggestions for further reading are provided;
* Bibliography: bibliographic sources used in the preparation of this tutorial are documented. 

## How-To

### Versions and Extensions

CIDOC CRM is updated on a regular basis. When using CIDOC CRM for research, please refer to the latest published version. When using CIDOC CRM for model implementation, you should refer to the latest version encoded in RDF. As of October 31, 2021, that is version 7.1.1.

A list of all versions is available [here](http://www.cidoc-crm.org/versions-of-the-cidoc-crm).

The CIDOC CRM also serves as the foundation for other auxiliary models, some of which have been approved by the CRM SIG, called extensions. Those extensions, compatible with the CIDOC CRM, can be found [here](http://www.cidoc-crm.org/collaborations). After selecting a model, click "Resources" in the upper right corner to view all of its versions. For example, [CRMgeo](http://www.cidoc-crm.org/crmgeo/) is the model used to manage geospatial data.

### Structure of CIDOC CRM Entities

CIDOC CRM is not designed to be read from start to finish. To effectively navigate this reference document, an understanding of the following concepts is necessary.

#### CIDOC CRM Naming Conventions

The main part of the document is divided into two large sections: "CIDOC CRM Class Declarations" and "CIDOC CRM Property Declarations." In CIDOC CRM, classes are always preceded by an identifier starting with the letter "E" followed by a number. For example, the class "Place" is preceded by its identifier, "E53": `E53_Place`. The same applies to properties, whose identifier always begins with the letter "P" followed by a number (there are more properties than classes in CIDOC CRM). For example, the property "took place at" is preceded by its identifier, "P7": `P7_took_place_at`.

There is also another style distinction between these two categories of entities; in French, the first word in a class name is capitalized (e.g. `E10_Transfert_de_la_garde`), while lower case is used in property names (e.g. `P28_a_mis_fin_à_la_garde_par`). In English (the original version), title case (except for "of" and "or") is used in class names (e.g. `E10_Transfer_of_Custody`) and lower case is used in property names (e.g. `P28_custody_surrendered_by`).

#### Classes

Classes are entities used to categorize a set of instances based on a common definition. For example, the value "Montreal" may be considered an instance of the class `E53_Place`. In addition to sharing a common definition, instances of the same class can be linked to other instances via the same set of properties.

#### Properties

Properties are used to link two instances together. Those linkages show the semantics associated with the data. For example, the property `P122_borders_with` can be used between the values "Montreal" and "St. Lawrence River" to indicate that these instances of the class `E53_Place` share a common geographic boundary.

#### Domain and Range

Properties do not automatically apply to all instances. There are two fundamental concepts that determine which properties are applicable to which instances: *domain* and *range*.

The domain indicates the class of the instance with which a property can be used. Similarly, the range indicates the class of the instance that serves as the endpoint of that same property. For example, the property `P122_borders_with` has the class `E53_Place` as both its domain and its range, which validates the previous example since the values "Montreal" and "St. Lawrence River" are both instances associated with `P122_borders_with`.

Note that it is possible, and even common, for the domain and range to differ. A case in point is `P7_took_place_at`, which has for domain `E4_Period` and for range `E53_Place`.

#### Super-class/Sub-class and Super-property/Sub-property

Another important concept of CIDOC CRM is the hierarchy of entities (classes and properties). A class can be designated as a sub-class of another class (which then becomes its super-class). This hierarchy is very important because a sub-class inherits the properties of all of its super-classes. For example, the property `P7_took_place_at` can be applied to the class `E12_Production` even though its domain is the class `E4_Period` because the following sub-class chain exists: `E4_Period`, `E5_Event`, `E7_Activity`, `E11_Modification`, and `E12_Production` (each class in this list is the super-class of the following class).

This hierarchy also allows a person using the model to identify the level of precision they should seek. By choosing the most precise class possible, a wide variety of properties can be used, which facilitates more specific searches within a corpus.

Properties can be hierarchical as well, allowing more general queries to be made with super-properties rather than their sub-properties, which have more restrictive scope notes. This is useful to achieve, through the use of the appropriate property, the right level of precision to meet the need.

### CIDOC CRM Conceptual Framework

You can explore the hierarchy of classes and sub-classes using domains and ranges, and their associated properties without having to read the entire document. However, it is useful to know CIDOC CRM’s conceptual principles to more quickly identify the relevant entities for a job without always referring to the class `E1_CRM_Entity`, which is very generic.

#### Temporal Entities

CIDOC CRM is structured around the concept of temporal entity (`E2_Temporal_Entity`). As a result, modelling information from a dataset frequently requires the use of a sub-class of `E2_Temporal_Entity`. For example, to indicate an object’s production date, a date must be associated with the event of its production, and not with the object produced. Consequently, it is helpful to know the main sub-classes of `E2_Temporal_Entity`.

These temporal entities are called "perduring", because they evolve over time, so that the entirety of a temporal entity cannot be reduced to time *t* (unlike an "enduring" entity which contains all of its characteristics at time *t*). CIDOC CRM uses the class `E77_Persistent_Item` to define enduring entities, which are mainly individuals or groups (sub-classes of `E39_Actor`) and things (including physical objects and concepts).

Some entities do not belong to either of these two categories; that is the case for time intervals (e.g. `E52_Time-Span`) and places (e.g. `E53_Place`).

#### CIDOC CRM Main Classes

To facilitate searches in the CIDOC CRM specification, certain classes can be used as a starting point to identify the entity best-suited to a need. The following diagram shows CIDOC CRM main classes:

Diagram of the CIDOC CRM’s main classes

<iframe frameborder="0" style="width:100%;height:363px;" src="https://viewer.diagrams.net/?tags=%7B%7D&target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=CRM_MainClasses_2019-12-08#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1FCeNoxLPlfJ5Kc0IcMmN3pcJPJPNzgwg%26export%3Ddownload"></iframe>

The class `E2_Temporal_Entity` and its sub-classes make it possible to link the individuals or groups that participated in an event to the physical or conceptual objects used or created during the event. The event’s duration can be indicated using the class `E52_Time-Span` and identify the places where the action occurs using the class `E53_Place`.

In general, two essential classes run through the entire model and are useful for naming an instance (`E41_Appellation`) or specifying its nature (`E55_Type` associated with external vocabularies). 

#### Management of Temporality in CIDOC CRM

The management of temporality in CIDOC CRM is often difficult to understand for first-time users. First of all, it is important to know that CIDOC CRM uses only *intervals* to document the passage of time. This key principle allows to properly account for the vagueness that surrounds the temporality of an event. Heritage data provides only an approximation (no matter how precise) of the exact time an event occurred in the world the data describes. Even knowing the exact time (to the second) when an event started, it is almost impossible to determine to the tenth of a second when it took place, and so on for ever shorter intervals. The time period during which an event occurred may also be known, but just as imprecisely.

Three properties (shown below) are used to document the time interval during which an event occurred.

Time interval diagram

<iframe frameborder="0" style="width:100%;height:302px;" src="https://viewer.diagrams.net/?tags=%7B%7D&target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=005_CRM_Temporalite_2021-11-04-EN.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1wk1lohCuGxyHgo1pPKMZ6ZZn0720M94d%26export%3Ddownload"></iframe>

First, the property `P191_had_duration` allows to indicate for how long the event took place: for example, the event lasted three days.

Second, the property `P81_ongoing_throughout`—or its more precise functional equivalents `P81a_end_of_the_begin` and `P81b_begin_of_the_end`—allows to indicate the time at which the event occurred: for example, the event took place on February 2, 2020 (it may have started before or ended after, but it is known to have been in progress on February 2, 2020).

Third, the properties `P82a_begin_of_the_begin` and `P82b_end_of_the_end` allow to indicate the temporal limits of the period during which the whole event occurred. The use of these more precise properties replaces that of `P82_at_some_time_within` and makes it possible to indicate the periods when the event is known *not* to have taken place. This third option is the most commonly used in the heritage sector.

Note that the specializations of `P81_ongoing_throughout` and `P82_at_some_time_within` (`P81a_end_of_the_begin`, `P81b_begin_of_the_end`, `P82a_begin_of_the_begin`, and `P82b_end_of_the_end`) are not listed in the current CIDOC CRM specification, although they are frequently used and listed in its latest RDF version.

### Identify the Right Entity

There are several interfaces for viewing the CIDOC CRM specification. Some versions (such as [version 7.1.1](http://www.cidoc-crm.org/Version/version-7.1.1)) were generated in HTML so that each entity can be viewed on a dedicated web page. They show all the properties that a class can use, including those associated with its super-classes. This makes it easy to identify the properties that can be used with a given class.

However, the most recent versions are available only in .docx or .pdf format as working documents (this is the case for [version 7.2](http://www.cidoc-crm.org/Version/version-7.2)).

Each entity is described using a series of fields. The main ones are listed below.

**For classes**

* "Sub-class of" and "Super-class of" identify classes hierarchically above or below the class being viewed. An overview of the entire hierarchy can be found on pages 48 to 54 of the document ([version 7.1.1](http://www.cidoc-crm.org/Version/version-7.1.1)).
* "Scope note" defines the class and the instances that are part of it.
* "Examples" contains possible instances of the class.
* "Properties" identifies the properties immediately associated with the class being viewed (in other words, this class is the domain). The properties associated with the super-classes of a class can also be used by the class even if they are not listed in this field. The same is true for the inverse properties. For an overview of all properties and their domains and ranges, see the [property hierarchy](http://www.cidoc-crm.org/Version/version-7.1.1). 

**For properties**

* "Domain" and "Range" quickly identify the domain and range of the property being viewed.
* "Sub-property of" and "Super-property of" help you navigate through the property hierarchy.
* "Scope note" defines the nature of the link between two instances.
* "Examples" contains possible links between two instances.

## Aide-mémoire {#aide-memoire}

* It is not necessary to read the entire document. Experimenting with sub-classes, super-classes, sub-properties, super-properties, domains, and ranges is the most efficient way to find CRM CIDOC entities capable of meeting specific implementation needs. 
* For the complete hierarchy of classes and properties, see the introduction to the CIDOC CRM specification. It provides a good overview of the entities that can be used to leverage this standard.
* The properties associated with a specific class do not necessarily constitute all the properties that can be used with the class, so it is necessary to study the properties of its super-classes and the inverse properties that may be associated with it.
* Temporal entities are central to CIDOC CRM; it is relevant to refer to them frequently to identify entities that meet specific implementation needs.
* CIDOC CRM may not address all needs; examining existing extensions or creating a local extension are good ways to meet specific needs.

## For More Information

* [CIDOC CRM Game](http://www.cidoc-crm-game.org/)
* [Tutorials on specific aspects of the CIDOC CRM](http://www.cidoc-crm.org/tutorialPageRes)
* [Canadian CIDOC CRM Translation Working Group website](https://chin-rcip.github.io/cidoc_crm_fr-ca/)
* [CIDOC CRM introduction video](http://www.cidoc-crm.org/cidoc-crm-tutorial)

## Bibliography

Bekiari, Chryssoula, George Bruseker, Martin Doerr, Christian-Emil Ore, Stephen Stead, and Athanasios Velios, eds. *Definition of the CIDOC Conceptual Reference Model*. CIDOC CRM Documentations, 7.1. Paris, FR-IDF: CIDOC CRM Special Interest Group, 2021. [http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf](http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf).

CIDOC CRM. "CRMgeo." 2021. [http://www.cidoc-crm.org/crmgeo/home-5](http://www.cidoc-crm.org/crmgeo/home-5).

CIDOC CRM Special Interest Group. "Tutorials." CIDOC CRM. October 2021. [http://www.cidoc-crm.org/tutorialPageRes](http://www.cidoc-crm.org/tutorialPageRes).

FORTH. *CRMgeo: A Spatiotemporal Model: An Extension of CIDOC CRM to Link the CIDOC CRM to GeoSPARQL through a Spatiotemporal Refinement*. GR. 2015. [http://www.cidoc-crm.org/crmgeo/sites/default/files/CRMgeo1_2.pdf](http://www.cidoc-crm.org/crmgeo/sites/default/files/CRMgeo1_2.pdf).

Canadian CIDOC CRM Translation Working Group. "Traduction en français du CIDOC CRM." French translation of the CIDOC CRM. June 3, 2021. [https://chin-rcip.github.io/cidoc_crm_fr-ca/](https://chin-rcip.github.io/cidoc_crm_fr-ca/).

Guillem, Anaïs, and George Bruseker. "CIDOC CRM Game." CIDOC CRM Game. 2021. [http://www.cidoc-crm-game.org/](http://www.cidoc-crm-game.org/).

Stead, Stephen. "CIDOC CRM Tutorial." CIDOC CRM. November 2008. [http://www.cidoc-crm.org/cidoc-crm-tutorial](http://www.cidoc-crm.org/cidoc-crm-tutorial).

