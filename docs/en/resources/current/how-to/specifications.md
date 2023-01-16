---
layout: page
language: en
title: How-to - Target Model and Semantic Paths Specifications
permalink: /en/resources/current/how-to/specifications
other_link: /fr/ressources/actuel/mode-demploi/specifications
sidebar: specs
group: resources
subgroup: how-to
date: 2022-12-10
description: This document explains how to use the Target Model and Semantic Paths Specifications individually or jointly in order to develop a new data model or to structure data in alignment with CHIN's DOPHEDA documentation, to carry out a mapping process, or to perform relevant SPARQL queries.
---

**Version**: 1.0

**Author:** Marie-Pier Blain, Karine Léonard Brouillet, Trang Dang, Stephen Hart, Philippe Michon

**Created date**: 2022-09-20

**Last update**: 2022-12-10

**Abstract**: This document explains how to use the Target Model and Semantic Paths Specifications individually or jointly in order to develop a new data model or to structure data in alignment with CHIN's DOPHEDA documentation, to carry out a mapping process, or to perform relevant SPARQL queries. 

**Contact**: If you have any questions or comments about the How-to: Target Model and Semantic Paths Specifications, please visit the [Issues](https://github.com/chin-rcip/collections-model/issues) section (and open an Issue if relevant) or send us an email at [rcip-chin@pch.gc.ca](mailto:rcip-chin@pch.gc.ca) with "How-to: TM and SP Specifications" in the subject line.

## Main Uses

This document is intended to:

* Vulgarize the main terms used in the Target Model and Semantic Paths Specifications;
* Facilitate the reading and understanding of the Target Model and Semantic Paths Specifications;
* Explain how to use the Target Model and Semantic Paths Specifications individually or jointly.

## Context

The Target Model Specification (TMS) semantically models actors (persons and groups) in a heritage context by documenting patterns most relevant to actors’ lives through descriptions, diagrams, and examples, as well as rationales behind their development. 

The Semantic Paths Specification (SPS) presents the semantic relationships between CIDOC CRM entities constituting the Target Model Specification's patterns. 

Both specifications are meant to be used in conjunction with the other in order to address Linked Open Data (LOD) projects' use cases in the heritage domain. 

## Essential Vocabularies and Prior Knowledge

Throughout the Target Model and Semantic Paths Specifications, different technical terms are employed. The user should have prior understanding of the following concepts:

* [Class](https://chin-rcip.github.io/collections-model/en/resources/current/glossary#class-noun)
* [Instance](https://chin-rcip.github.io/collections-model/en/resources/current/glossary#instance-noun)
* [Knowledge Graph](https://chin-rcip.github.io/collections-model/en/resources/current/glossary#knowledge-noun)
* [Model](https://chin-rcip.github.io/collections-model/en/resources/current/glossary#model-noun)
* [Named Graph](https://chin-rcip.github.io/collections-model/en/resources/current/glossary#named-graph-noun)
* [Node](https://chin-rcip.github.io/collections-model/en/resources/current/glossary#node-noun)
* [Pattern](https://chin-rcip.github.io/collections-model/en/resources/current/glossary#pattern-noun)
* [Property](https://chin-rcip.github.io/collections-model/en/resources/current/glossary#property-noun)
* [Property-Class](https://chin-rcip.github.io/collections-model/en/resources/current/glossary#property-noun)
* [Specification](https://chin-rcip.github.io/collections-model/en/resources/current/glossary#specification-noun)

The term "Target Model" is used as a shorthand for CHIN's LOD model, to which users' datasets can be mapped (hence the term "target").

In addition, anyone using the Target Model and Semantic Paths Specifications, whether for modelling purposes or not, should be familiar with basic notions of LOD. It is therefore recommended for new users to have a look at the following resources:

* [101 – Choosing a LOD Model](https://chin-rcip.github.io/collections-model/en/resources/current/how-to/choosing-lod-model)
* [RDF model](https://www.w3.org/RDF/)
* [Turtle language](https://www.w3.org/TR/turtle/)
* [JSON-LD format](https://json-ld.org)

It is also recommended to read the targeted [glossary](https://chin-rcip.github.io/collections-model/en/semantic-paths-specification/current/introduction#glossary) of the SPS to better grasp the difference between concepts associated with the notion of "node" in CHIN's data model's context.

Furthermore, because CHIN's model is reliant on the CIDOC CRM ontology, the user should have a basic understanding of it. Useful resources can be found here:

* [CIDOC CRM website](https://www.cidoc-crm.org/)
* [CIDOC CRM Tutorial](https://chin-rcip.github.io/collections-model/en/resources/current/cidoc-crm-tutorial)

## Intended Audience·s and Section Description

Typical users are expected to have a background knowledge of information technology and techniques (e.g. museum cataloguers, programmers, model/ontology experts). 

This How-to is divided into four sections:

1. **How-to**: the usefulness and structure, and navigation of the TMS and SPS are presented, as well as different ways to use them together (three personas are featured as examples);
2. **Memory Aids**: key elements and important actions are detailed;
3. **For more information**: relevant external links are provided;
4. **Bibliography**: bibliographic sources used in the preparation of this How-to are documented. 

## How-to

### Target Model Specification

#### Usefulness {#tms-usefulness}

The Target Model Specification explains the structure of the data model that represents the backbone of the DOPHEDA documentation. The objective is to help users identify, document, describe, and consolidate, in unique records, the information pertaining to people and groups (i.e. actors) related to objects from heritage collections, the main events that typically punctuate their lives, as well as their relationships to one another. 

Another intention behind the TMS is to encourage and help users develop their LOD infrastructure, and possibly their own Target Model. 

These specifications are not necessarily meant to be read in their entirety and should rather be used as reference documents. For users interested in the **creation of a data model**, it may be useful to consult the [introduction of the TMS](https://chin-rcip.github.io/collections-model/en/target-model/current/introduction). 

#### Structure {#tms-structure}

##### Chapter Division {#tms-chapter-division}

The Target Model Specification is divided into 23 chapters. The framework of the document has been designed to facilitate the research of information, to help explore the context of a specific topic, or to structure information in a LOD context.   

1. [Introduction](https://chin-rcip.github.io/collections-model/en/target-model/current/introduction): this section presents the general information pertaining to the current version of the Target Model, the methodology employed for its development, as well as the description of the styling and ontological conventions used in the diagrams throughout the model.
2. [General Concepts](https://chin-rcip.github.io/collections-model/en/target-model/current/general-concepts): this chapter regroups relevant notions, concepts, and entities used throughout the TMS and present in most patterns. For example, the purpose of reifying specific properties so that instances of property-classes become the subject of other triples is explained in the [property-classes](https://chin-rcip.github.io/collections-model/en/target-model/current/general-concepts#property-classes) section.

Each of the following chapters refers to a particular pattern.

3. [Messy Data](https://chin-rcip.github.io/collections-model/en/target-model/current/messy-data): this pattern has been developed to facilitate the mapping of unstructured data, namely data that does not follow DOPHEDA's recommendations. For example, the Yukon Arts Centre could use this pattern to document that the artist Ted Harrison is of English ancestry and that after settling in Carcross, Yukon in 1968, he obtained Canadian citizenship in 1973. Since no other pattern accommodates this type of data, it is recommended to use the Messy Data pattern.
4. [Dataset Provenance](https://chin-rcip.github.io/collections-model/en/target-model/current/dataset-provenance): this pattern was designed for the representation of the information pertaining to the submission of a dataset by an organization or a person responsible for its creation, provision, and/or update. For example, the Canadian Museum of History could use this pattern to document that Sophie Piedmont (fictive) was the cataloguer of the museum's dataset when it was submitted to a shared knowledge graph on October 31, 2020.
5. [Record Provenance](https://chin-rcip.github.io/collections-model/en/target-model/current/record-provenance): this pattern is intended to represent the information pertaining to the documentation of a record by an organization or a person responsible for either its creation or its latest update. For example, the Canadian Museum of History could use this pattern to document that cataloguer Maximilian Dunham (fictive) created Medalta Potteries Ltd.'s record in the museum database on July 15, 1996.
6. [Temporal Bounds](https://chin-rcip.github.io/collections-model/en/target-model/current/temporal-bounds): this pattern was created to ease the recording of dates for significant events described in the TMS. All patterns of the Target Model that enable the documentation of start and end dates use the same basic structure presented in this pattern.
7. [Curatorial Note](https://chin-rcip.github.io/collections-model/en/target-model/current/curatorial-note): this pattern pertains to the information associated with an actor that cannot be recorded through structured fields, but that relates to another data node represented elsewhere in the model. It is particularly useful to users that wish to model information in the form of comments, remarks, or descriptions such as explanations, notes, grades, or evaluations. For example, the Winnipeg Art Gallery could use this pattern to document a note written in English by Martin Jutt, the assistant curator of decorative arts (fictive), assessing the monetary value and condition of the artwork *Buttermere Bridge* by W.T. Copeland & Sons.
8. [Actor Identifiers and Appellations](https://chin-rcip.github.io/collections-model/en/target-model/current/actor-identifiers-and-appellations): this pattern is one of the most important patterns of the TMS since it refers to basic identification information about actors that the majority of, if not all, heritage institutions document, such as identifiers or appellations. For example, the Royal Ontario Museum could use this pattern to document the different appellations of the artist Michelangelo (e.g. Michelangelo, Michel-Ange, Michelangelo di Lodovico Buonarroti Simoni, etc.), as well as specify their type (e.g. first name, customary name, full name, etc.), use context, language (e.g. English, French, Italian, etc.), and precedence.
9. [Technique Used](https://chin-rcip.github.io/collections-model/en/target-model/current/technique-used): this pattern enables the representation of information on techniques employed by an actor in an act of production, or that they are known to have used generally. For example, the Orillia Museum of Art & History could use this pattern to document that Sylvia Tesori, the artist of the painting *Cockpit*, has made some sculpted works during her career even though she is primarily known for her painted works.
10. [Family Belonging](https://chin-rcip.github.io/collections-model/en/target-model/current/family-belonging): this pattern can be used to document the belonging of an individual to a family. For example, the National Gallery of Canada could use this pattern to indicate that the painter and printmaker Jan Brueghel the Elder, who painted *View of the Ponte Rotto in Rome* in 1593-1596, belongs to the Brueghel family, which also has as members Pieter Brueghel the Younger and Pieter Bruegel the Elder, both famous painters of the Dutch and Flemish Renaissance.
11. [Birth and Death of a Person](https://chin-rcip.github.io/collections-model/en/target-model/current/birth-and-death-of-a-person): this pattern is useful to delimit an actor's lifespan (i.e. their birth and death). For example, the Beaverbrook Art Gallery could use this pattern to document that the artist Clarence Gagnon was born on November 8, 1881 in Laval, CA-QC, died on January 5, 1942 in Montreal, CA-QC, and was buried in Notre-Dame-des-Neiges Cemetery.
12. [Formation and Dissolution of a Group](https://chin-rcip.github.io/collections-model/en/target-model/current/formation-and-dissolution-of-a-group): this pattern was designed for the documentation of the beginning and ending of a group (i.e. their formation and dissolution), as well as the responsible actors. For example, the Art Gallery of Hamilton could use this pattern to document the creation of the Contemporary Arts Society by John Lyman, its founder and first president, in Montreal, CA-QC, in 1939.
13. [Flourishing](https://chin-rcip.github.io/collections-model/en/target-model/current/flourishing): this pattern has been developed to facilitate the mapping of the information pertaining to the period of highest productivity and excellence or influence of an actor in a field during their lifetime. For example, the Museum of Anthropology at UBC could use this pattern to document that the Portuguese folk artist Domingos Gonçalves Lima, also known as Mistério, was particularly active between 1950 and 1990 in Barcelos.
14. [Group Belonging](https://chin-rcip.github.io/collections-model/en/target-model/current/group-belonging): this pattern can be used to document an official association of an actor with a group. For example, the Art Gallery of Hamilton could use this pattern to document that Fritz Brandtner joined the Contemporary Arts Society in 1939 as a member.
15. [Occupation](https://chin-rcip.github.io/collections-model/en/target-model/current/occupation): this pattern pertains to information on the occupations of an actor—which could be a paid or unpaid business, profession, or otherwise labour-related activity—as primary endeavours in their life. For example, the McCord Stewart Museum could use this pattern to document that, in addition to working as a silversmith, Pierre Huguet dit Latour was also a merchant and wigmaker.
16. [Social Status](https://chin-rcip.github.io/collections-model/en/target-model/current/social-status): this pattern enables the representation of the information pertaining to the social statuses of an actor, which includes the relative rank and possible honour or prestige an actor holds relative to how well they are perceived. For example, the Musée national des beaux-arts du Québec could use this pattern to document that the Quebec sculptor Louis Archambault was awarded the Officer of the Order of Canada by Queen Elizabeth II in Ottawa, CA-ON, in 1974.
17. [Relationship](https://chin-rcip.github.io/collections-model/en/target-model/current/relationship): this pattern is particularly useful for the documentation of the information pertaining to the relationship of association or acquaintance between two actors. For example, the Dalhousie Art Gallery could use this pattern to document the relationship between the artist Marcel Barbeau and his teacher, the artist Paul-Émile Borduas, when the former studied at École du meuble de Montréal between 1942 and 1946.
18. [Staying Event](https://chin-rcip.github.io/collections-model/en/target-model/current/staying-event): this pattern can be used to represent the information pertaining to the physical presence of an actor somewhere for a prolonged or temporary duration, including at their customary residence/geographical location. For example, the Vancouver Art Gallery could use this pattern to document that the painter Lawren Harris stayed in Berlin between 1904 and 1908 to study art, philosophy, and theosophy.
19. [Biography](https://chin-rcip.github.io/collections-model/en/target-model/current/biography): this pattern details how to represent the textual information pertaining to the biography of an actor. For example, the Art Gallery of Nova Scotia could use this pattern to document that "Maud Lewis (1901-1970) was born to John and Agnes Dowley [... and the house she painted] is on permanent display in Halifax at the Art Gallery of Nova Scotia", which is accessible on its website at [https://artgalleryofnovascotia.ca/maud-lewis](https://artgalleryofnovascotia.ca/maud-lewis), is the artist Maud Lewis' biography.
20. [Artefact](https://chin-rcip.github.io/collections-model/en/target-model/current/artefact): this pattern is one of the most important patterns of the TMS since it refers to basic identification information on objects that the majority of, if not all, heritage institutions document, such as their accession numbers and appellations. For example, the Montreal Museum of Fine Arts could use this pattern to document that *Midnight Sun (Quartet in White)* is the English title of an artwork by the artist Jean Paul Riopelle that is preserved under the accession number 2001.161.1-4.
21. [Artefact Production](https://chin-rcip.github.io/collections-model/en/target-model/current/artefact-production): this pattern can be used to minimally record the information pertaining to the production of a tangible artefact, such as the producers' role in its creation and their level of priority, as well as the moment and place it was created. For example, Power Corporation of Canada could use this pattern to document that Jean Paul Riopelle is the sole artist of the painting *Iceberg no. 5* and that this artwork was painted in 1977 in the artist's studio located in Estérel, CA-QC.
22. [Visual Item](https://chin-rcip.github.io/collections-model/en/target-model/current/visual-item): this pattern can be used to represent the information pertaining to the visual representation of an actor in a digital form or depicted on a physical object, whether it is an image (e.g. Albrecht Dürer in one of his many self-portraits) or a mark (e.g. silversmith Carl Poul Petersen's hallmark under the foot of an ewer), as well as their type and bibliographical statement.
23. [Reference Document Location](https://chin-rcip.github.io/collections-model/en/target-model/current/reference-document-location): this pattern pertains to reference documents related to an actor, as well as information indicating where these documents are located. For example, the Musée national des beaux-arts du Québec could use this pattern to document that the exhibition catalog "Jean Paul Lemieux au Musée du Québec", in which a specific artefact from its collection is depicted, is preserved under the reference number 700 L554m 2001-3 and available for consultation at the museum's library.

#### Pattern Template

Each pattern modellized and described in the TMS follows the same description template to facilitate the identification of useful information related to a specific need. The template is the following:

* **At Glance**: this section describes the usefulness of the pattern, what type of information it can represent, as well as its limits; 
* **Introduction and Context**: this section defines the concepts on which the pattern is based and presents the context that justifies its development by CHIN;
* **Description of the Pattern**: this section provides a precise description of the semantic links between entry nodes, classes, and properties included in the proposed pattern;
* **Diagram**: this section provides a visual representation of the pattern, in which styling and ontological [conventions](https://chin-rcip.github.io/collections-model/en/target-model/current/introduction#diagram-conventions) of other important Linked Open Data heritage projects, such as SARI and Linked.art, were used. CHIN has developed a [diagrams.net](https://chin-rcip.github.io/collections-model/en/resources/current/tools) libraries for museums that would like to develop their own model based on CIDOC CRM;
* **Examples**: this section presents instance diagrams (generated by [CRITERIA](https://github.com/chin-rcip/CRITERIA)) that help to illustrate the use of the pattern with one or more concrete use cases (i.e. how specific data is modelled according to the data model) so that the developer can quickly test the pattern in their data model thanks to the representations in Turtle and JSON-LD;
* **Related Documentation**: this section refers to external models that were useful for the conceptualization and development of the pattern, as well as lists the pattern's entry nodes and CIDOC CRM entities that the pattern mobilizes;
* **Discussion**: this section discusses why the pattern was modelled in a certain way (i.e. the pros and cons), explores its issues and limitations, as well as present edge cases in order to accommodate less common circumstances in the actors' life (e.g. when an artist experiences more than one flourishing, whether it be in the same or different fields/mediums/periods), or data that is difficult to record (e.g. the father of a family is not necessarily the father of all the members of this family);
* **Bibliography**: this section documents in alphabetical order all the bibliographical sources that allowed the conceptualization and development of the pattern.

### Semantic Paths Specification

#### Usefulness {#sps-usefulness}

The Semantic Paths Specification (SPS) provides a semantic description of each entry node that forms the patterns of the TMS. This description contains the information (i.e. data) expected to be documented in the node, semantic paths to query it, as well as tiers to assess the expected quality of recorded data.

The SPS can serve as a reference document for any mapping process. For example, a museum that wishes to transform existing data recorded in its institutional database into another data structure that better meets the requirements of the semantic web can rely on the DOPHEDA model to develop its own model.

A user that does not have preliminary data can build their own database and/or data model directly from the SPS.

#### Structure {#sps-structure}

##### Chapter Division {#sps-chapter-division}

The Semantic Paths Specification is divided into three chapters:

1. [Introduction](https://chin-rcip.github.io/collections-model/en/semantic-paths-specification/current/introduction): this section documents relevant information on the use of the specification, a glossary clarifying the various terms related to the concept of "node", and a description of the structure adopted for the presentation of all the model's entry nodes.

2. [Entry Nodes](https://chin-rcip.github.io/collections-model/en/semantic-paths-specification/current/entry-nodes): this section is the body of the documentation; it contains tables describing each of the entry nodes of the SPS, placed in alphabetical order to facilitate their tracking on the sidebar (on the left-hand side).

3. [Bibliography](https://chin-rcip.github.io/collections-model/en/semantic-paths-specification/current/bibliography): this section documents in alphabetical order the bibliographical sources that allowed the conceptualization and development of the entry nodes.

#### Entry Node Template

Each entry node is characterized by a set of descriptive features gathered in a table. 

Each entry node is defined by a precise scope note detailing the data values it can accommodate, as well as by its generated bonds, semantic valuation, and controlled list/terms. The context of each node can be explored through its dependencies, its related specified qualifier nodes, its full path, its visualized position in the TMS, and its value origins. In addition to relevant comments and potential errors, the SPS lists typical and edge cases that exemplify how heritage institutions might document information with regards to other fields. References for each node are also included.

A detailed description of each descriptive feature can be found in the [Documentation Structure](https://chin-rcip.github.io/collections-model/en/semantic-paths-specification/current/introduction#documentation-structure) section of the SPS.

### Using the TMS and SPS together

#### Complementary Specifications

The Target Model and Semantic Paths Specifications have been thought out, conceptualized, and developed in a logic of complementarity, and thus, should be used in conjunction with one another. While the TMS presents the data model, the context for each entry node, and the relations between all entry nodes through a set of patterns, the SPS describes each entry node in detail, the information they should contain, and the paths to query them. 

In other words, the information presented in the TMS is more theoretical and is particularly useful for understanding the semantics underlying the model, the reasons justifying the design of the patterns, as well as the interactions between CIDOC CRM entities within a single pattern. The TMS is also useful for validating user interpretations or determining what can be done with an existing dataset. Additionally, the introduction of the TMS is an essential starting point for anyone who is unfamiliar with the DOPHEDA documentation; CHIN recommends reading it before heading to the SPS. 

In contrast, the information included in the SPS is presented in an applied way to facilitate implementation. It enables users, once engaged in a process of mapping or implementing a data model, to assess the semantic potential of their data based on their capacity and to develop a functional mapping process accordingly (e.g. making sure nodes are connected to relevant entities). 

#### Navigation

There are multiple ways of searching and navigating the Target Model and Semantic Paths Specifications. Since they do not have to be read linearly (from start to finish), their searchability is an important feature. There are three ways of searching the TMS and SPS: through the chapter organization visible on the sidebar, through the search box, or through the A-Z diagram.

##### Sidebar

The chapter structure of the TMS and SPS is visible on the sidebar of the platform documentation (on the left-hand side). By navigating in it, it is possible to reach specific chapters of the documentation and find the information needed.

The use of the sidebar is the best way to have a general look at the specifications' hierarchy and have an overview of the different topics covered by the model as well as the structure of each pattern (TMS) and entry node (SPS). 

##### Search Tool

A search tool is also available in the top menu of the DOPHEDA website (the magnifying glass icon). Through this search tool, it is possible to retrieve specific words present throughout the entire website. Once keywords are typed into the search tool, some example queries are displayed in order to help users select the most fitting search results for their needs.

This tool is particularly useful to users who already know what they are searching for, who want to find meaningful terms in sections that they could have otherwise missed, who need to gather all the information pertaining to a particular topic, or who wish to confirm that all relevant patterns to a modelling need were examined.

##### A-Z Diagram

For more advanced users, the A-Z diagram found in the introduction of the TMS is a helpful tool to quickly access specific patterns (by clicking on their title) and search through it as it does not require navigating through the hierarchy of the TMS.

In addition, each node present in the SPS with bold text on the A-Z diagram can be accessed by clicking on it. Those links are the best way for users to navigate between the TMS and the SPS. 

#### Personas

To illustrate various ways of consulting the specifications and using them for various purposes, the following examples have been devised. They are purely *fictional* and serve to demonstrate **three** of **several** ways of using the TMS and SPS together. 

The common thread that unites these three personas is the development of a knowledge graph by the fictional Canadian Association for the Advancement of Open Humanities (CAAOH) that brings together open and linked data from several museums and heritage institutions located across the country.

##### Museum Cataloguer

Abigail is a museum cataloguer at the Eureka Art Museum (EAM), which was recently founded through the patronage of the Eureka family and the donation of its exceptional private collection to the City of Ottawa. The museum wishes to incorporate its collection within the ecosystem set up by the CAAOH, which is based mainly on the DOPHEDA semantic model. On the one hand, Abigail was given the mandate to ensure that the meaning of the institution's data is preserved when integrating it into the CAAOH's knowledge graph. On the other hand, she must also respect the semantic rules proposed by the DOPHEDA model in order to ensure the interoperability of the institution's data with all the data collected by the CAAOH.

As such, Abigail needs to prepare a mapping template (table) including all entry nodes with the following fields while consulting the information from these SPS’ features, for example:

|Pattern|Entry Node|Definition|Data Format|Example|Museum data field name|Notes|
|---|---|---|---|---|---|
|[Actor Identifiers and Appellations](https://chin-rcip.github.io/collections-model/en/target-model/current/actor-identifiers-and-appellations)|[Actor Appellation](https://chin-rcip.github.io/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-appellation)|the entire identifying word·s, number·s, symbol·s, or code·s by which an actor (person or group) is distinguished from others, such as the name, title, or designation as it has been attributed by a contributing institution|string|"Emily Carr"|||
|[Actor Identifiers and Appellations](https://chin-rcip.github.io/collections-model/en/target-model/current/actor-identifiers-and-appellations)|[Actor Appellation Language](https://chin-rcip.github.io/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-appellation-language)|the natural language the Actor Appellation is written in|URI or value that could be reconciled to a URI of lexvo vocabulary|"English","eng","en","http://www.lexvo.org/page/iso639-3/eng" |||

Based on this template, Abigail can create a mapping profile for the EAM by identifying which data field from its dataset corresponds to which entry node. Since Abigail is familiar with the EAM database and the description of each field it contains, she can use her knowledge to determine which data field matches to which entry node. For example, the metadata description of the field describing the appellation of artists in the EAM database is the following:

|field_name|definition|format|
|---|---|---|
|artist_name_en|Full name of artist in English|last name, first name|

Though the mapping template does include brief descriptions of the entry nodes, Abigail can further consult their full descriptions in the SPS, especially the  Semantic Valuation, Typical Cases and Comments sections, as well as the Examples section in the TMS, to ensure the accuracy of the mapping and to determine if further data manipulation is required. In this example, Abigail decides that:

- the data in `artist_name_en` should be reformatted to `first name last name`, and be typed as "full name";
- the data should be splitted into two Actor Appellation Parts with "first name" and "last name" Types;
- the Language of both Actor Appellation and Actor Appellation Parts should be recorded as "English". 

Upon her analysis of the EAM data field `artist_name_en`, if there was any anomaly and/or inconsistency in the data, Abigail could have consulted the Edge Cases sections in both the TMS and SPS to determine whether they could have been mapped at all. Here is a part of the EAM's mapping profile after the analysis:

|Pattern|Entry Node|Definition|Data Format|Example|Museum data field name|Notes|
|---|---|---|---|---|---|
|[Actor Identifiers and Appellations](https://chin-rcip.github.io/collections-model/en/target-model/current/actor-identifiers-and-appellations)|[Actor Appellation](https://chin-rcip.github.io/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-appellation)|the entire identifying word·s, number·s, symbol·s, or code·s by which an actor (person or group) is distinguished from others, such as the name, title, or designation as it has been attributed by a contributing institution|string|"Emily Carr"|artist_name_en|to be reformatted from "last name, first name" to "first name last name"|
|[Actor Identifiers and Appellations](https://chin-rcip.github.io/collections-model/en/target-model/current/actor-identifiers-and-appellations)|[Actor Appellation Language](https://chin-rcip.github.io/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-appellation-language)|the natural language the Actor Appellation is written in|URI or value that could be reconciled to a URI of lexvo vocabulary|"English","eng","en","http://www.lexvo.org/page/iso639-3/eng"||"English" as fixed value|
|[Actor Identifiers and Appellations](https://chin-rcip.github.io/collections-model/en/target-model/current/actor-identifiers-and-appellations)|[Actor Appellation Part 1](https://chin-rcip.github.io/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-appellation-part)|the units that compose the Actor Appellation|string|"Carr"|artist_name_en["last name"]|first part of museum data<br>comma separator|
|[Actor Identifiers and Appellations](https://chin-rcip.github.io/collections-model/en/target-model/current/actor-identifiers-and-appellations)|[Actor Appellation Part 2](https://chin-rcip.github.io/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-appellation-part)|the units that compose the Actor Appellation|string|"Emily"|artist_name_en["first name"]|second part of museum data<br>comma separator|

Once the mapping profile is completed, Abigail can send it to the CAAOH along with the EAM's exported dataset.

##### Developer

Ronaldo is a developer who was hired by the CAAOH to build a knowledge graph that can be used by museums and heritage institutions to share and disseminate data about their collections. His role also consists of transforming the partner institutions' data while respecting their mapping profile. The CAAOH wants the knowledge graph to be based on CHIN's Target Model. Thus, one of Ronaldo’s main tasks is to prepare the transformation of partner institutions’ submitted datasets (e.g. in CSV) to LOD following the Target Model.

In his work plan, the first step is to familiarize himself with the patterns of the TMS by consulting the A-Z diagram found in the introduction. Then, Ronaldo decides to start with the most important pattern, Actor Identifiers and Appellations. From the A-Z diagram, he clicks on the title of the pattern and is redirected to the appropriate chapter, where he pays attention to the At Glance, Description of the Pattern, Diagram, Examples, and Entry Nodes sections. 

- The At Glance section gives him a general understanding of the pattern, as well as what it does and does not represent. It helps him discover that this pattern covers actor identifiers, but not any information identifying an artefact.
- The Description of the Pattern and Diagram sections help Ronaldo understand the underlying semantic structure of the pattern. They both contain clickable links to the description of each entry node in the SPS, as well as several descriptive features which help solidify the datasets transformation. On the one hand, the Generated Bonds, Dependencies, Full Path, and Related SQNs help him validate the correct transformation of each node. On the other hand, the Semantic Valuation informs him what data value is required for the transformation following the designed semantic structure of the pattern; if not, Ronaldo needs to add the Messy Data pattern in the transformation.
- The Examples section provides the exemplary LOD results of the transformation that can be downloaded in Ronaldo's own ecosystem for testing purposes.

With the transformation scripts ready, submitted datasets can be semi-automatically converted to LOD and ingested into the knowledge graph. Ronaldo then has to discuss with all museum cataloguers involved, including Abigail (see first persona), to ensure that his transformation process will generate the data desired by the institutions. 

##### Researcher

Gabriele is a researcher who wishes to identify all the artists represented in the permanent collections of the Museum of Humanities and the Eureka Art Museum that used sculpture as their main technique. Gabriele has some knowledge of LOD and wants to easily find the information they need without having to understand the whole data model mobilized by the CAAOH's knowledge graph. 

To determine how to build their query efficiently, Gabriele uses the search tool of the DOPHEDA website and types in keywords relating to sculpture, i.e. "technique", "medium", and "material". Example results displayed allow them to find the [Technique Used](https://chin-rcip.github.io/collections-model/en/target-model/current/technique-used), [Occupation](https://chin-rcip.github.io/collections-model/en/target-model/current/occupation), and [Artefact Production](https://chin-rcip.github.io/collections-model/en/target-model/current/artefact-production) patterns in the TMS. 

To make sure that they rely on the right patterns and use them in an efficient way, Gabriele reads the At Glance, Theoretical Background, and Statement of Need sections. This first familiarization with patterns enables them to eliminate the Artefact Production pattern, which museums can only use to document information pertaining to the producers’ roles in the creation of an artefact, the place where and moment when the artefact was created, as well as the level of priority of its producers. 

However, the Technique Used pattern can be used by museums to represent the information on the techniques employed by an actor that are not recorded as part of the production of a specific object, more specifically by using the [Technique Used Type](https://chin-rcip.github.io/collections-model/en/semantic-paths-specification/current/entry-nodes#technique-used-type) entry node (e.g. the Technique Used Type "Sculpture" would enable Gabriele to find all the artists associated with this technique). Likewise, the Occupation pattern can be used by museums to represent the information on the activities, businesses, professions, and other labour-related roles of an actor, more specifically by using the [Occupation Type](https://chin-rcip.github.io/collections-model/en/semantic-paths-specification/current/entry-nodes#occupation-type) entry node (e.g. the Occupation Type "Sculptor" would enable Gabriele to find all the artists associated with this profession).

Since Gabriele is interested in data from two specific datasets, they also check if a provenance pattern exists. They discover that the [Dataset Provenance](https://chin-rcip.github.io/collections-model/en/target-model/current/dataset-provenance) pattern would allow them to adequately target specific institutional datasets. The [Record Provenance](https://chin-rcip.github.io/collections-model/en/target-model/current/record-provenance) pattern would not apply in this example since it only allows to target the provenance of a particular record within a database. Here, Gabriele only needs to know the provenance of the dataset itself and not of each of its records.

Once these three patterns have been identified and their usefulness validated, Gabriele reads the Descriptions of the Pattern (TMS), checks the Diagrams (TMS), explores the Examples (TMS), and analyses the Full Paths (SPS) in order to identify all relevant semantic constructs to take into consideration while building their query. The examples are particularly useful to them since they can have a look at the knowledge graph serializations in Turtle and JSON-LD.

With all this information in hand, Gabriele is now able to create the following SPARQL query that helps them find all the people with "Sculptor" as an occupation and "Sculpture" as a technique used within two specific datasets:

```sparql

prefix crm: <http://www.cidoc-crm.org/cidoc-crm/> .

prefix crmdig: <http://www.ics.forth.gr/isl/CRMext/CRMdig.rdfs/> .

prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .



SELECT ?actor ?technique ?occupation ?providerName

WHERE{

        ?g a crmdig:D1_Digital_Object ;
                crm:P94i_was_created_by/crm:P01i_is_domain_of/crm:P02_has_range/crm:P1_is_identified_by/crm:P190_has_symbolic_content ?providerName .
        FILTER (CONTAINS(lcase(?providerName),"museum of humanities") || CONTAINS(lcase(?providerName),"eureka art museum"))
        GRAPH ?g {
                optional{
                        ?actor crm:P2_has_type ?techniqueURI.
                        ?techniqueURI crm:P2_has_type/rdfs:label "Technique Used"@en.
                        ?techniqueURI rdfs:label ?technique.
                        FILTER(lang(?technique)="en")
                        FILTER REGEX(?technique,"sculpt","i")
                }
                optional{
                        ?actor crm:P14i_performed/crm:P2_has_type ?occupationURI.
                        ?occupationURI crm:P2_has_type/rdfs:label "Occupation"@en.
                        ?occupationURI rdfs:label ?occupation.
                        FILTER(lang(?occupation)="en")
                        FILTER REGEX(?occupation,"sculpt","i")
                }
        }
}

```

Note that the query developed by Gabriele could be improved to be more efficient, but this is outside the scope of this document.

## Memory Aids

Searching the SPS can be complex if the user is unfamiliar with the adopted structure. For this reason, CHIN has listed common searches.

* How to find the proper node? You can :
   	* do a keyword search using the search tool;
	* go through the dependencies;
	* look at the related nodes;
	* go through the patterns of the TMS.
* How to understand the semantic path of a node? You can look at :
	* its Full Path. Some of the nodes have longer paths because they request one or more Specified Qualifier Node·s;
	* the TMS through the Target Model View·s link to acknowledge the context of the node within a pattern;
	* its Semantic Valuation to know what type of data is expected, especially when writing queries that could rely on logic algorithms or on some controlled vocabularies;
	* its Comment·s.
* How to determine the expected content of a node? You can read:
	* its Scope to understand what this node is about;
	* its Semantic Valuation to know what type of data is expected to be documented;
	* its Typical Cases to have an example of documented data;
	* its Edge Cases to understand the limits of this node.
* How to establish the context of a node? You can look at its:
	* dependencies;
	* related SQNs;
	* Target Model views;
	* value origin·s in the checklist unavailable at the moment.
* How to assess the quality of your data? You can refer to the Semantic Valuation of each entry node.

## For more information

Relevant external links:

* [101 – Choosing a LOD Model](https://chin-rcip.github.io/collections-model/en/resources/current/how-to/choosing-lod-model)
* [RDF model](https://www.w3.org/RDF/)
* [Turtle language](https://www.w3.org/TR/turtle/)
* [JSON-LD format](https://json-ld.org)
* [CIDOC CRM website](https://www.cidoc-crm.org/)
* [CIDOC CRM Tutorial](https://chin-rcip.github.io/collections-model/en/resources/current/cidoc-crm-tutorial)

## Bibliography

Art Gallery of Nova Scotia. "Maud Lewis." Art Gallery of Nova Scotia – Collection. 2022. [https://artgalleryofnovascotia.ca/maud-lewis](https://artgalleryofnovascotia.ca/maud-lewis).

Derome, Robert and Norma Morgan. "HUGUET, Latour, PIERRE." Dictionary of Canadian Biography. 1983. [http://www.biographi.ca/en/bio/huguet_pierre_5F.html](http://www.biographi.ca/en/bio/huguet_pierre_5F.html).

Gagnon, François-Marc. "Jean Paul Riopelle: Life and Work by François-Marc Gagnon." Art Canada Institute. 2019. [https://www.aci-iac.ca/art-books/jean-paul-riopelle/key-works/iceberg-no-1/](https://www.aci-iac.ca/art-books/jean-paul-riopelle/key-works/iceberg-no-1/).

Ministère de l'Emploi et de la Solidarité sociale. "Jean Paul Lemieux au Musée du Québec / Michèle Grandbois. –." Catalogue CUBIQ. 2022. [https://www.cubiq.ribg.gouv.qc.ca/notice?id=p%3A%3Ausmarcdef_0000639862](https://www.cubiq.ribg.gouv.qc.ca/notice?id=p%3A%3Ausmarcdef_0000639862).

Montreal Museum of Fine Arts. "Jean Paul Riopelle." Montreal Museum of Fine Arts – Montreal Museum of Fine Arts' Collections. 2022. [https://www.mbam.qc.ca/en/works/35801/](https://www.mbam.qc.ca/en/works/35801/).

Museum of Anthropology at UBC. "Lima, Domingos Goncalves (1921 - 1995)." Museum of Anthropology at UBC – Collection Online. 2022. [http://collection-online.moa.ubc.ca/search/person?person=5504&tab=biography](http://collection-online.moa.ubc.ca/search/person?person=5504&tab=biography).

National Gallery of Canada. "Jan (the Elder) Brueghel." National Gallery of Canada – Search the Collection. 2022. [https://www.gallery.ca/collection/artist/jan-the-elder-brueghel](https://www.gallery.ca/collection/artist/jan-the-elder-brueghel).

National Library of Canada. "Ted Harrison, 1926-." Collections Canada. March 12, 1997. [https://www.collectionscanada.gc.ca/eppp-archive/100/200/301/nlc-bnc/art_illustrations-ef/magic/fharris2.htm](https://www.collectionscanada.gc.ca/eppp-archive/100/200/301/nlc-bnc/art_illustrations-ef/magic/fharris2.htm).

Orillia Museum of Art & History. "The Man Who Could Fly; The Girl Who Flies in her Dreams by Sylvia Tesori." Orillia Museum of Art & History – Current Exhibitions. 2022. [https://www.orilliamuseum.org/project/the-man-who-could-fly-and-the-girl-who-flies-in-her-dreams-by-sylvia-tesori/](https://www.orilliamuseum.org/project/the-man-who-could-fly-and-the-girl-who-flies-in-her-dreams-by-sylvia-tesori/).

The Governor General of Canada. "Mr. Louis Archambault." The Governor General of Canada. 2022. [https://www.gg.ca/en/honours/recipients/146-99](https://www.gg.ca/en/honours/recipients/146-99).

Wikipedia. "Clarence Gagnon." Wikipedia. November 18, 2022. [https://en.wikipedia.org/wiki/Clarence_Gagnon](https://en.wikipedia.org/wiki/Clarence_Gagnon).

Wikipedia. "John Goodwin Lyman." Wikipedia. November 21, 2022. [https://en.wikipedia.org/wiki/John_Goodwin_Lyman](https://en.wikipedia.org/wiki/John_Goodwin_Lyman).

Wikipedia. "Lawren Harris." Wikipedia. November 18, 2022. [https://en.wikipedia.org/wiki/Lawren_Harris](https://en.wikipedia.org/wiki/Lawren_Harris).

Wikipedia. "Marcel Barbeau." Wikipedia. October 23, 2022. [https://en.wikipedia.org/wiki/Marcel_Barbeau](https://en.wikipedia.org/wiki/Marcel_Barbeau).

Wikipedia. "Michelangelo." Wikipedia. December 1, 2022. [https://en.wikipedia.org/wiki/Michelangelo](https://en.wikipedia.org/wiki/Michelangelo).

Winnipeg Art Gallery. "W.T. Copeland & Sons." Winnipeg Art Gallery – Search the Collections. 2022. [https://www.wag.ca/art/collection/item/34378/?from=art-search](https://www.wag.ca/art/collection/item/34378/?from=art-search).