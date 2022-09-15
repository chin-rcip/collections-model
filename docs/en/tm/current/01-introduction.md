---
layout: page
language: en
title: Target Model Specification
permalink: /en/target-model/current/introduction
other_link: /fr/modele-cible/actuel/introduction
sidebar: tm22
group: specifications
date: 2022-03-31
description: The Actors Target Model Specification semantically models actors in a heritage context. Patterns most relevant to actors' lives are presented along with diagrams and examples illustrating them, as well as a record and explanation of relevant decisions that were made when developing said patterns. This is a theoretical documentation that has never been tested or implemented.
---

Version 2.2 ([Previous versions](/collections-model/en/versions))

> <span class="disclaimer">DISCLAIMER:</span> This documentation is a collection of theoretical documents developed in the context of a pilot project where testing and implementation never occurred. As such, although it is publically released in both French and English, it does not constitute an official publication.

## Dates

Created date: 2019-05-13

Last Update: 2022-03-31

## Abstract

The Target Model Specification semantically models actors (persons and groups) in a heritage context. Patterns most relevant to actors' lives are presented along with diagrams and examples illustrating them, as well as a record and explanation of relevant decisions that were made when developing said patterns. This is a theoretical documentation that has never been tested or implemented. Elements currently under development or review are listed as [issues](https://github.com/chin-rcip/collections-model/issues).  

## Purpose of the Target Model

In keeping with its mandate to "assist Canadian museums in documenting, managing, and sharing information about their collections," the Canadian Heritage Information Network (CHIN) established a pilot project to determine whether it has the capacity to make the resources it creates and the data it aggregates available in Linked Open Data (LOD) (Canadian Heritage Information Network 2019). The objective was to consolidate, in unique records, the information pertaining to actors. Within the framework of this project, an actor encompasses any individual or group who took part in the creation of or is related to cultural artefacts documented by a data provider. This includes creators (artists, artisans, manufacturers, groups of artists, etc.) as well as other important actors such as owners, patrons, persons depicted, etc. who took part in the creation of or is related to artefacts collected by heritage institutions located in Canada.

This project is intended to evaluate and, eventually, support the development of a future, larger model and semanticization environment that would encompass heritage records of all sorts (tangible and intangible, collections, events, etc.). The initial focus was on the collection, standardization, and aggregation of actors' data that varies in structure, format, language, and origin. To fulfill this goal, reconciliation and conversion into a [knowledge graph](https://en.wikipedia.org/wiki/Knowledge_Graph) using [CIDOC CRM](http://www.cidoc-crm.org/) and its [extensions](https://cidoc-crm.org/collaborations) was envisioned. Important intended milestones were:

* Modellisation of information pertaining to persons and groups (actors);

* Documentation of the resulting model and data pipeline; 

* Testing; 

* Implementation in the form of a submission interface as well as a querying interface with a SPARQL endpoint. 

Though the modellisation and documentation did occur and are presented here, the subsequent procedures necessary to testing, implementation, and completion have not been accomplished. It is thus particularly important to take into consideration that this documentation is purely theoretical and that the model it describes has neither been tested nor implemented. Thus, practitioners reusing it should ensure its workability through extensive controlled vocabularies selection (for every node containing instances of `E55_Type`), model testing, and implementation phases. 

At the moment, there is no intention to manage data or further use it based on the Target Model Specification. This is in part because the Target Model Specification is intended to be a potential application profile developed and revised on an ever evolving and ongoing basis with no forecasted deployment or end to the theorisation phase. Rather, the focus is currently on the development of further content based on the review of existing patterns from other projects in order to enhance them for the documentation of the Target Model Specification.

In addition, it is important to consider that there is no system embedded in the design of the Target Model Specification patterns that adjudicates the veracity or value of content data. Rather, authority over data is that of the owner who is to be documented using the [Dataset Provenance](/collections-model/en/target-model/current/dataset-provenance) pattern. 

## Choice of an Ontology

The pilot nature of this project has imposed the choice of a limited subset of data to model as a way to assess the feasibility of a larger scale semanticization environment.  CHIN has elected to work with actors' patterns first knowing there are few heritage datasets focused on persons and groups (as opposed to artefacts). This is because actors’ information constitutes a self-contained and meaningful ensemble (i.e. information about persons and groups is understandable and significant even if the objects they are related to are not extensively modelled). As such, not every information about actors can be represented using this model, and specific institutions may document targeted or niche aspects of an actor's life or object, aspects that are relevant solely to them (e.g. a museum dedicated to firefighters might document the level of first-aid training an actor received). Such specific information has not been modelled here in order to avoid unnecessary complexity (as many collecting institutions have individual needs that are not shared by their counterparts; for a detailed discussion of this, see [Issue #19](https://github.com/chin-rcip/collections-model/issues/19)). 

The ontology these patterns are based on has been selected on the basis of larger criteria affecting the entirety of a potential model that would encompass heritage data in general. Three main criteria have been taken into account: 

* Adoption by the heritage semantic community in order to foster interoperability;

* Richness and sustainability of the ontology;

* Adequate representation of institutional data that is largely focused on objects rather than people.

In this context, CHIN elected to work with the [CIDOC CRM ontology](http://www.cidoc-crm.org/versions-of-the-cidoc-crm). Because it has been developed by the [International Council of Museums](https://icom.museum/en/) (ICOM) for heritage institutions with their needs in mind, it is by far the most used within this field. For this reason and because it is under ICOM’s custody through the Special Interest Group (CRM SIG) dedicated to it ([CIDOC Conceptual Reference Model Special Interest Group](http://network.icom.museum/cidoc/working-groups/crm-special-interest-group/)), CIDOC CRM appears to be a sustainable choice. It is regularly updated and adapted to the needs of the heritage community, thus offering a rich and precise framework to work with. Finally, as an event-based ontology, it is suited to the representation of both actors’ and objects' information as it can link instances of both through instances of events that can be situated in time and space.

The downside to this choice is that CIDOC CRM has a strong focus on the recorded history of objects. Social relationships are among the most difficult elements to represent because of their complexity and of the multiple understandings of a single event they carry. 

## Diagram Conventions

Patterns are conceptual descriptions of the core knowledge relevant to a heritage-specific element (e.g. how to represent the fact that a person used a specific technique to create an object). In order to understand patterns more easily, diagrams are often used. In this Target Model Specification, two types of diagrams are presented: 

* Ontological diagrams are representations of the data model that supports the knowledge graph; 

* Instance diagrams illustrate examples as a way to represent a knowledge graph itself (data that is modelled according to the data model).

If the model was to be implemented, labels could be attached to any instance across the knowledge graph, but these would not be displayed in the diagrams to facilitate readability. Moreover, to facilitate understanding, both types of diagrams share colour and styling conventions typically used by CIDOC CRM and suggested by George Bruseker, Chief Executive Officer at Takin.Solutions. DOPHEDA model's use of these conventions is described below. 

### Ontological Diagrams

For clarity and visibility sake, instances have been omitted in ontological diagrams to focus on the representation of relationships between classes, even though in the knowledge graph it is the instances that are connected to each other through properties, not the classes themselves (which the ontological diagrams could imply). 

Classes are represented by boxes with the name of the class inscribed in it, while properties are represented by arrows going from domain to range, with their name written on the arrow, as shown in the diagram below:

<a name="001_Convention_ClassesAndProperties_p"></a>001_Convention_ClassesAndProperties_p

<iframe frameborder="0" style="width:100%;height:200px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=001_Convention_ClassesAndProperties_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1ucfiOX84MV6y8ZwuGI-OqotYCUm_hiUE%26export%3Ddownload"></iframe>

For example, the diagram below illustrates that any instance of the class `E21_Person` can be linked to an instance of the class `E55_Type` through the property `P2_has_type`:

<a name="002_Convention_ClassesAndPropertiesExample_p"></a>002_Convention_ClassesAndPropertiesExample_p

<iframe frameborder="0" style="width:100%;height:200px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=002_Convention_ClassesAndPropertiesExample_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1VwLADOk9toVMBiiF1dRi7zoY8TtdChiy%26export%3Ddownload"></iframe>

In some cases, a single instance can be defined by two classes (e.g. names of actors that are instances of both `E33_Linguistic_Object` and `E41_Appellation`); this is called a double instantiation. This is illustrated diagrammatically by having *two* different classes written in a single box (e.g. both `E33_Linguistic_Object` and `E41_Appellation` are written in the box).

To facilitate understanding and visually convey how CIDOC CRM entities are used to model different kinds of information, the colour conventions below have been adopted to represent top-level classes along with their sub-classes. Expected instances of `rdfs:Literal` are also represented in ontological diagrams in the form of a white box containing the data type expected (i.e. `xsd:string` or `xsd:dateTime`). 

<a name="003_Convention_Colors_p"></a>003_Convention_Colors_p

<iframe frameborder="0" style="width:100%;height:300px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=003_Convention_Colors_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1g9K6QYy9C6JkCR2gsmrDtmH3abKKMx5t%26export%3Ddownload"></iframe>

All provided data is expected to be submitted as values through [entry nodes](/collections-model/en/semantic-paths-specification/current/introduction#entry-node) defined in the [Semantic Paths Specification](/collections-model/en/semantic-paths-specification/current/introduction). The name of the entry node is indicated in bold above its associated class name or data type, as shown below:

<a name="004_Convention_Field_p"></a>004_Convention_Field_p

<iframe frameborder="0" style="width:100%;height:400px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=004_Convention_Field_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1bGAeyfZyefD19pTgLr8-Jg6Kews6irtw%26export%3Ddownload"></iframe>

In the diagram above, bold styling denotes [Birth Place](/collections-model/en/semantic-paths-specification/current/entry-nodes#birth-place),  [Birth Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#birth-date-begin), and [Birth Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#birth-date-end) nodes. In addition to facilitating understanding, this illustrates how the semanticization of inputed data generates several new elements such as `E67_Birth` and `E52_Time-Span`.

Occasionally, an `E55_Type` in a specific pattern is only intended to accommodate a fixed instance. Such specified qualifier nodes are named in quotation marks underneath the name of the class, as in the following example:

<a name="005_Convention_Metatype_p"></a>005_Convention_Metatype_p

<iframe frameborder="0" style="width:100%;height:200px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=005_Convention_Metatype_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1_wvBOxh09c5uxmSaOvz9Kb4RZ916DC1C%26export%3Ddownload"></iframe>

The diagram above represents the Technique Used pattern: the middle element corresponds to the [Technique Used Type](/collections-model/en/semantic-paths-specification/current/entry-nodes#technique-used-type) entry node (bolded), which records the technique used by the actor (e.g. watercolouring, wood working, etc.). This information is then designated as pertaining to techniques by another `E55_Type` that always has the value "Technique Used". For example, Yousuf Karsh is typed as using the technique "Gelatin silver print", and this information is designated as being of the type "Technique Used".

### Instance Diagrams

Each example is illustrated with a textual description of the use case followed by an instance diagram (generated using CHIN's [CRITERIA](https://chin-rcip.github.io/collections-model/en/resources/current/how-to/criteria) tool), as well as JSON-LD and Turtle expressions. 

The instance diagrams are visual representations of the knowledge graph: instances, in addition to classes and properties, are thus illustrated in the diagrams. Classes and properties follow the same conventions as for the ontological diagrams. Instances are documented in a stadium shape using the colour of their associated class at a lesser saturation (i.e. paler). Example data of the instances are illustrated in a stadium shape with a URI or literal values in quotation marks, as seen below:

<div id="0001_100_technique-used-inst-diagram" class="example"></div>

In this diagram, instances (Yousuf Karsh, Gelatin silver print, Technique Used) are linked together through properties in accordance with the structure of the corresponding Technique Used pattern found in the Target Model Specification.

## A-Z Diagram

An ontological overview of the entirety of the patterns developed is also available. 

* Each pattern is enclosed in a blue-dotted bubble, the title of which leads to its corresponding section in the Target Model Specification when clicked on;

* Each entry node recipient class (with the entry node name bolded within its container) leads to its corresponding node in the [Semantic Paths Specification](/collections-model/en/semantic-paths-specification/current/introduction) when clicked on. 

<a name="000_Patterns_2.2_p"></a>000_Patterns_2.2_p

<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=000_Patterns_2.2_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D19Du-R8yhx0MbpxfnMtyTwNGstsmnqOo9%26export%3Ddownload"></iframe>

## Bibliography

Canadian Heritage Information Network (CHIN). 2019. "Canadian Heritage Information Network." Governmental. Government of Canada Website. October 23, 2019. [https://www.canada.ca/en/heritage-information-network.html](https://www.canada.ca/en/heritage-information-network.html).



