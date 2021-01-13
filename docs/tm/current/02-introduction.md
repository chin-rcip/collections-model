---
layout: page
title: Target Model
permalink: /target-model/current/introduction
sidebar: tm
---
<!-- [Back to the Table of Contents](/collections-model/target-model/current/information#table-of-contents)
 -->
Version 2.1 ([Previous versions](/collections-model/versions))

<div class="hidden-content">
## On This Page

* [Abstract](#abstract)
* [Foreword](#foreword)
* [Purpose of the Target Model](#purpose-of-the-target-model)
* [Methods and Sources](#methods-and-sources)
* [Modelling Conventions](#modelling-conventions)
	* [Patterns](#patterns)
	* [Examples](#examples)
</div>

## Dates 

Created date: 2019-05-13

Last Update: 2020-12-22

## Abstract 

This documents the Actors Target Model, which is intended to model the Actors Facet of CHIN’s Collections Model (that will cover collections data more broadly). It details what choices were made when developing patterns as well as why they were made, and offers diagrams representing these patterns. 

## Foreword

This document is based on the Artefact Semantic Reference Data Model by George Bruseker and follows a similar structure [(Bruseker 2019)](/collections-model/target-model/current/bibliography#bruseker-2019). This work is also indebted to the [linked.art](https://linked.art/) project whose scope differs from that of CHIN’s, but whose review and discussions of issues are beneficial [(linked.art 2019a)](/collections-model/target-model/current/bibliography#linked-art-2019a).

The current document is a work in progress and, as such, will be enhanced periodically. Elements currently missing include: 

*   *A chapter on PC14 and property chains.* As this pattern is used throughout the Target Model, it would be nice to have an explanation on how it works at the beginning. This will be done when [CHIN’s Github Issue #30](https://github.com/chin-rcip/chin-rcip/issues/30) is solved.
*   *A complete mapping table.* The mapping table, which indicates how the Reference Documentation and Target Models concur, is not yet finished but will be added to the current document when it is finalised.

## Purpose of the Target Model

In keeping with its mandate to “assist Canadian museums in documenting, managing, and sharing information about their collections”, the Canadian Heritage Information Network (CHIN) plans to provide the resources it creates and the data it aggregates in linked open data (LOD) [(Canadian Heritage Information Network (CHIN) 2019)](/collections-model/target-model/current/bibliography#canadian-heritage-information-network-chin-2019). This is in order to contribute to the breaking of data silos and give better access to Canadian heritage information online. Before modernising Artefacts Canada (AC) by converting it in accordance with LOD principles, CHIN will work on a smaller scale project titled *Actors* (Actors), which will later be part of the larger Collections model supporting Artefacts Canada.

The scope of this project is to consolidate, in unique records, the information pertaining to actors related to objects from Canadian museums collections. An actor includes any individual (artist, artisan, etc.) or group (manufacturer, group of artists, etc.) who took part in the creation of or is related to artefacts collected by Canadian museums. 

That said, specific museums may document targeted or niche aspects of an actor's life or object, aspects that are relevant solely to that museum (e.g. a museum dedicated to firefighters might document the level of first-aid training an actor received). The Actors and/or Collections models will not model such specific information in order to  avoid unnecessary complexity as many museums will have individual needs that are not shared by their counterparts. See the closed Issue #19 for the detailed discussion about this topic.

| ![GitHub Mark](https://user-images.githubusercontent.com/48293227/104475587-49182180-558d-11eb-87fc-9f95190cb332.png) *Related Github Issue*<br/><br/>This topic is discussed in [CHIN’s Github Issue #19](https://github.com/chin-rcip/collections-model/issues/19) |

The first challenge will be to standardize into a single format data that will be varied in structure, format and languages when collecting and aggregating them. The second and most ambitious challenge will be to reconcile data coming from numerous and varied sources. Reconciling, here, implies two main steps:

1. Identifying single entities amongst different entries that manifest the same information; 
2. Attributing to these entries unique identifiers that relate them to those single entities.

To succeed in those objectives, two major steps are required:

1. Conversion of inputed GLAM data to a unique format and structure (XML);
2. Conversion of uniquely formatted data to structured RDF.

To accomplish these successfully, CHIN has already developed an intended Data Pipeline [Documentation](https://drive.google.com/open?id=1W_vsT_Br86BRR92SWEqFX90861Nu3mUTmx_fAyuOE5A) and [Schema](https://drive.google.com/open?id=1qalobG-9YmV3cQ9-pBRYxRW9wQP2PrAg). This process relies on three major tools: the [Reference Checklist](https://drive.google.com/open?id=1Rnlreq5FlHxMu4oHFvahXakIVtAc4VqdoNoJ-3PagnU), the [Semantic Paths Specification](/collections-model/semantic-paths-specification/current/introduction), and the Target Model. 

The Reference Checklist will be the reference for Canadian institutions to map their data to. It briefly describes the fields needed by CHIN to convert structural data to LOD standards through the Target Model and allows them to establish concordance with their own fields The Reference Checklist will guide the mapping of museums’ data—whose structures and formats are varied—to a single framework (whether it be in JSON-LD, RDF/XML or other formats). The main benefit of the Reference Checklist is its user-friendliness: by not relying directly on complex LOD structures, it makes the mapping process easier for non-specialists.  

The Reference Documentation details the fields listed in the Reference Checklist and further documents them by providing, in addition to brief definitions, more precise scope notes detailing the information a field can accommodate as well as a bibliography for each definition. It also provides information pertaining to the field’s use, its hierarchical position within CHIN’s model structure and the associated mandatory fields that must be filled for the data to be properly processed. It also presents the types of values the field accommodates and expects along with technical field requirements. Finally, in addition to relevant comments and details, the Reference Documentation offers descriptions of typical and edge cases that exemplify how institutions might document information with regards to other fields. 

The Target Model complies with LOD standards and, as such, will guide the transfer from the aforementioned unique format to RDF. In this process, museums’ data that is generally represented in tables or arborescences will be converted into a [Knowledge Graph](https://en.wikipedia.org/wiki/Knowledge_Graph) in accordance with the structure and rules of Semantic Web Ontologies (using [CIDOC CRM](http://www.cidoc-crm.org/) and [FRBRoo](http://www.cidoc-crm.org/frbroo/home-0), although other ontologies such as [FOAF](http://xmlns.com/foaf/spec/), [Schema.org](https://schema.org/) might be used later). 

## Methods and Sources

This model has been developed using an incremental modeling framework informed by Linked Open Data principles, most notably interoperability, semantic richness and meaningfulness, shareability, usability, transparency, and collaboration. In accordance with the latter, the following best practices were adopted from the start:

1. Use [URIs](https://en.wikipedia.org/wiki/Uniform_resource_identifier) to identify elements; 
2. Use open standards such as [RDF](https://en.wikipedia.org/wiki/Resource_Description_Framework) or [SPARQL](https://en.wikipedia.org/wiki/SPARQL); 
3. Refer to other elements using their [URIs](https://en.wikipedia.org/wiki/HTTP) whenever possible. 

In addition, in order to facilitate collaboration and reuse, a transparent approach to development has been adopted whereas issues pertaining to the model are publically displayed and discussed on [Github](https://github.com/chin-rcip/chin-rcip), along with relevant documentation. 

This model is being developed using a prototyping and iterative approach whereas a first version will be tested in the following manner:

1. Releasing a first version of the model documentation and submitting it to advice from targeted experts. 
2. Revising the model accordingly. 
3. Testing the model with suitable open dataset in order to test CHIN’s [Data Pipeline](https://drive.google.com/open?id=1W_vsT_Br86BRR92SWEqFX90861Nu3mUTmx_fAyuOE5A) and model, from the ingestion of the data to its publication. 
4. Revising the model accordingly. 
5. Testing the model with a second open dataset to validate reconciliation, and revising accordingly as many times as necessary. 
6. Releasing the data in LOD (SPARQL endpoint, public interface). 
7. Expanding the model with relevant fields using the same methods, eventually expanding it with an Objects Facet using the same approach and having learned from the development of the Actors Facet. This will likely entail starting over this same process at a larger scale as well as updating the Actors Facet where necessary. 

Even though CHIN intends to develop a model that will account for both Objects and Actors from Canadian collections, it has for now focused on the representation of Actors in order to allow for an incremental development of the Collections model where Actors and Objects facets will be equal and interrelated. 

For the purposes of this model, an actor encompasses any individual or group who took part in the creation of or is related to artefacts collected by museums. This includes creators (artists, artisans, manufacturers, groups of artists, etc.) as well as other important actors such as owners, patrons, persons depicted, etc. (please note that although all such profiles will be accounted for, only data that is compliant with privacy and legal legislation as well as the data provider’s wishes will be published). 

CHIN has elected to develop a semantic model for Actors first as it is a smaller ensemble of data to model and also because the social relationships are likely to be amongst the most semantically complex parts of the final model. In addressing these first, CHIN will build experience and gain a good overview of the challenges to come. 

Because this Actors Facet will be a small but determining aspect of the Collections model (which will also include an Objects facet) in general, it has been developed accordingly and the choice of an ontology has been reliant on three key factors that take the whole model into consideration:

1. Adoption by the heritage semantic community in order to foster interoperability; 
2. Richness and sustainability of the ontology; 
3. Adequate representation of institutional data that is largely focused on objects rather than people. 

In this context, CHIN elected to work with the [CIDOC CRM ontology](http://www.cidoc-crm.org/versions-of-the-cidoc-crm). Because it has been developed by the [International Council of Museums](https://icom.museum/en/) (ICOM) for museums and with their needs in mind, it is by far the most used within this field. For this reason and because it is under ICOM’s custody through the special interest group dedicated to it ([CIDOC Conceptual Reference Model Special Interest Group, CRM SIG](http://network.icom.museum/cidoc/working-groups/crm-special-interest-group/)), CIDOC CRM also appears to be a sustainable choice. It is regularly updated and adapted to the needs of said community, thus offering a rich and precise framework to work with. Finally, as an event-based ontology, it is suited to adequately represent both Actors and Objects by linking instances (people, objects, etc.) together through events that can be situated in time and space. 

The complex variety of human activity documented in relation to actors is a significant challenge to represent accurately and semantically. For instance, social relationships are amongst the most difficult events to represent in CIDOC CRM as their complexity renders many patterns suitable to represent a single event. While the event modelling of CIDOC CRM provides the means in principle to represent such information, in practice the modelling developed there has a strong focus on the history of objects through time. As such, treating the Actors Facet first seems to be preferable considering the Objects Facet will be more in line with what CIDOC CRM is usually utilised for: representing data pertaining to heritage or historical objects. 

More information about CIDOC CRM can be found on their [website](http://www.cidoc-crm.org/).

The current model, focused on actors related to objects from Canadian museums’ collections, consolidates the information pertaining to them in unique, non-authoritative records. Although CHIN is the custodian of the data that will be submitted to the model, this data will be provided by outside contributors (museums, libraries, researchers, etc.). As such, CHIN does not claim authority over the data content of records, nor does it intervene in museums’ data beyond mapping, cleaning and reconciliation as well as the creation of unique identifiers. CHIN’s role in cohering these data will be that of a custodian with no expert status on the information they represent.

## Modelling Conventions

The following conventions will be used when representing modeling patterns in this document.

### Patterns

The ontological relationships between classes have been represented diagrammatically where the structure of triples is visualised instead of the triples themselves. 

It is important to note that in reality it is the instances that are connected to each other through properties, not the classes themselves like the diagrams might imply. For clarity and visibility sake however, modeling patterns will not display instances (they will be represented in examples however, as shown below). 

<a name="001_Convention_ClassesAndProperties_p"></a>001_Convention_ClassesAndProperties_p
<iframe frameborder="0" style="width:100%;height:200px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=001_Convention_ClassesAndProperties_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1tP4V68oU1n7l5HedZXb5nFrfnYu2yHXg%26export%3Ddownload"></iframe>

For example, the diagram below illustrates that any instance of the class `E21_Person` can be linked to an instance of the class `E55_Type` through the property `P2_has_type`.

<a name="002_Convention_ClassesAndPropertiesExample_p"></a>002_Convention_ClassesAndPropertiesExample_p
<iframe frameborder="0" style="width:100%;height:200px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=002_Convention_ClassesAndPropertiesExample_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1gr88pIpcq9FVA0Md9fZ74rwIPlAJi-4t%26export%3Ddownload"></iframe>

In some rare cases, two different classes are mentioned in the same box (e.g. `E33_Linguistic_Object` and `E41_Appellation`) in order to represent a multi-instantiation, meaning that two classes are used to define a single instance.

To facilitate understanding and visually convey how CIDOC CRM entities are used to model different kinds of information, the colour conventions below have been adopted to represent top-level classes along with their subclasses. 

<a name="003_Convention_Colors_p"></a>003_Convention_Colors_p
<iframe frameborder="0" style="width:100%;height:300px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=003_Convention_Colors_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1LMF5iRQKFyNoq5BkehhjQUy8xv1HVs8u%26export%3Ddownload"></iframe>

In addition, fields defined in the Reference Documentation are indicated in bold above their respective class name, as shown below:

<a name="004_Convention_Field_p"></a>004_Convention_Field_p
<iframe frameborder="0" style="width:100%;height:400px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=004_Convention_Field_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1HILva7PuFDfsCg5daNYxTva-BtlwTjBg%26export%3Ddownload"></iframe>

In the above diagram, the “Birth Place”,  “Birth Date Begin” and “Birth Date End” fields from the Reference Documentation are denoted in bold. In addition to facilitating the understanding of both the Target Model and its Reference Documentation, this also illustrates how the translation of the data to a semantic framework generates several new elements such as `E67_Birth` event and `E52_Time-Span`. 

Sometimes, an `E55_Type` can only have a single instance in a specific pattern. In such a case, it is named in quotation marks underneath the name of the class, as follows:

<a name="005_Convention_Metatype_p"></a>005_Convention_Metatype_p
<iframe frameborder="0" style="width:100%;height:200px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=005_Convention_Metatype_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1qnZZqU6wsy-5dMs86vKqeWtJ-iuNHTlS%26export%3Ddownload"></iframe>

The diagram above represents the gender pattern. The middle element corresponds to the Reference Documentation “Gender” field (hence it is in bold) to signal that the content found in this field indicates the gender of the person (e.g. male, female, two-spirit, …). This information is then typed with another `E55_Type` that always has the “Gender” value to indicate that the aforementioned data (e.g. male, female, two-spirit, …) concerns gender. For example, Jean Paul Riopelle has the type “Male”, and this type has the type “Gender”. When nothing follows the parentheses, it means that the data format is `xsd:string`. For example, the dates will be defined as `xsd:dateTime`. 

### Examples

Throughout the documentation each example is represented in a pattern where instances are illustrated (in ovals rather than rectangles) in addition to their structured diagrams. Instances are represented in the examples, unlike in the modeling patterns where they are not.

For example, the triples mapped to the gender pattern mentioned above would look like the following:

<a name="006_Convention_Instances_p"></a>006_Convention_Instances_p
<iframe frameborder="0" style="width:100%;height:300px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=006_Convention_Instances_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1C8p1lpiLNDykkf1HUK4SVfJ6jf0p6UQ5%26export%3Ddownload"></iframe>

In this diagram, each instance (the instances of Jean Paul Riopelle, of the gender Male, and of the type Gender) are linked together through properties in accordance with the structure of the corresponding pattern in the model.

> Next: [General Concepts](/collections-model/target-model/current/general-concepts)
