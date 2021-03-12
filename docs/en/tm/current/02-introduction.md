---
layout: page
language: en
title: Target Model
permalink: /en/target-model/current/introduction
other_link: /fr/modele-cible/actuel/introduction
sidebar: tm
---
<!-- [Back to the Table of Contents](/collections-model/en/target-model/current/information#table-of-contents)
 -->
Version 2.1 ([Previous versions](/collections-model/en/versions))

> DISCLAIMER: The documentation hereby accessible is a collection of working documents. As such, although it is publically released, it does not constitute an official publication and changes are made on an ongoing basis. Because of these regular modifications, <span class="disclaimer">the majority of this content is presented in **English** and will only be translated once a stable and official publication occurs<span>.
	
## Dates 

Created date: 2019-05-13

Last Update: 2021-03-12

## Abstract 

The Actors Target Model is intended to model the Actors facet of CHIN’s Collections Model (that will cover collections data more broadly). Patterns most relevant to actors' lives are presented along with diagrams and examples illustrating them, as well as a record and explanation of relevant decisions that were made when developing said patterns.  

The current document is a work in progress and, as such, will be enhanced periodically. Elements currently under development or review are listed as [issues](https://github.com/chin-rcip/collections-model/issues).  


## Purpose of the Target Model

In keeping with its mandate to “assist Canadian museums in documenting, managing, and sharing information about their collections”, the Canadian Heritage Information Network (CHIN) plans to provide the resources it creates and the data it aggregates in linked open data (LOD) [(Canadian Heritage Information Network (CHIN) 2019)](/collections-model/en/target-model/current/bibliography#canadian-heritage-information-network-chin-2019) in an effort to give better access to Canadian heritage information online. Work on the Actors facet of CHIN's larger Collections model, intended to support a future LOD deployment of Artefacts Canada, is documented here. 

The scope of this project is to consolidate, in unique records, the information pertaining to actors related to objects from Canadian museums collections. An actor includes any individual (artist, artisan, etc.) or group (manufacturer, group of artists, etc.) who took part in the creation of or is related to artefacts collected by Canadian museums. 

That said, specific museums may document targeted or niche aspects of an actor's life or object, aspects that are relevant solely to that museum (e.g. a museum dedicated to firefighters might document the level of first-aid training an actor received). The Actors and/or Collections models will not model such specific information in order to avoid unnecessary complexity as many museums will have individual needs that are not shared by their counterparts (for a detailed discussion of this issue, see Issue #19).

| ![GitHub Mark](https://user-images.githubusercontent.com/48293227/104475587-49182180-558d-11eb-87fc-9f95190cb332.png) *Related Github Issue*<br/><br/>This topic is discussed in [Issue #19](https://github.com/chin-rcip/collections-model/issues/19) |

The objective of the model is to collect, standardize, and aggregate data that is varied in structure, format and languages. This will involve reconciling data coming from numerous and varied sources through two main steps:

1. Identifying single entities amongst different entries that contain the same information; 
2. Attributing unique identifiers to these entries in order to relate them to said single entities.

This, in turn, will require the:

1. Conversion of inputed GLAM data to a unique format and structure (XML);
2. Conversion of uniquely formatted data to structured RDF.

In this process, data that is generally structured in tables or arborescences is converted into a [Knowledge Graph](https://en.wikipedia.org/wiki/Knowledge_Graph) using [CIDOC CRM](http://www.cidoc-crm.org/) and [FRBRoo](http://www.cidoc-crm.org/frbroo/home-0), although other ontologies such as [FOAF](http://xmlns.com/foaf/spec/) or [Schema.org](https://schema.org/) might be used eventually). 

## Methods and Sources

In order to facilitate collaboration and reuse, a transparent approach to development has been adopted whereas issues pertaining to the model are publically displayed and discussed on [Github](https://github.com/chin-rcip/chin-rcip), along with relevant sources and documentation. 

CHIN intends to develop a model that will account for Objects and Actors facets equally and inter-relatedly as part of a single semantic structure. Development is done using a prototyping and iterative approach whereas a first version will be tested in the following manner:

1. Releasing a first version of the Actors facet of the Target Model and submitting it to advice from targeted experts; 
2. Revising the model accordingly;
3. Testing the model with suitable open datasets in order to test CHIN’s [Data Pipeline](https://drive.google.com/open?id=1W_vsT_Br86BRR92SWEqFX90861Nu3mUTmx_fAyuOE5A) and model, from the ingestion of the data to its publication; 
4. Revising the model accordingly;
5. Testing the model with a second open dataset to validate reconciliation, and revising accordingly as many times as necessary; 
6. Releasing the data in LOD (SPARQL endpoint, public interface); 
7. Expanding the model with relevant fields using the same methods, eventually expanding it with an Objects Facet using the same approach and having learned from the development of the Actors Facet (this will likely entail starting over this same process at a larger scale as well as updating the Actors Facet where necessary). 

CHIN has elected to develop the Actors facet first as it is a smaller ensemble of data to model. For the purposes of this model, an actor encompasses any individual or group who took part in the creation of or is related to cultural artefacts documented by a submissioner. This includes creators (artists, artisans, manufacturers, groups of artists, etc.) as well as other important actors such as owners, patrons, persons depicted, etc. (please note that although all such profiles will be accounted for, only data that is compliant with privacy and legal legislation as well as submissioner’s wishes will be published).

Because this Actors facet will be a small but determining aspect of the Collections model in general, it has been developed accordingly and the choice of an ontology has been reliant on three key factors that take the whole model into consideration:

1. Adoption by the heritage semantic community in order to foster interoperability; 
2. Richness and sustainability of the ontology; 
3. Adequate representation of institutional data that is largely focused on objects rather than people. 

In this context, CHIN elected to work with the [CIDOC CRM ontology](http://www.cidoc-crm.org/versions-of-the-cidoc-crm). Because it has been developed by the [International Council of Museums](https://icom.museum/en/) (ICOM) for heritage institutions and with their needs in mind, it is by far the most used within this field. For this reason and because it is under ICOM’s custody through the special interest group dedicated to it ([CIDOC Conceptual Reference Model Special Interest Group, CRM SIG](http://network.icom.museum/cidoc/working-groups/crm-special-interest-group/)), CIDOC CRM also appears to be a sustainable choice. It is regularly updated and adapted to the needs of said community, thus offering a rich and precise framework to work with. Finally, as an event-based ontology, it is suited to adequately represent both Actors and Objects by linking instances (people, objects, etc.) together through events that can be situated in time and space. 

Historically, CIDOC CRM has a strong focus on the recorded history of objects through time. As such, the Objects Facet will be more in line with what CIDOC CRM is traditionally used for. Treating the Actors facet first offers more time to examine the complex variety of human activity documented in relation to actors, which is a significant challenge to represent accurately and semantically (e.g. social relationships are amongst the most difficult elements to represent in CIDOC CRM as their complexity and the multiple understandings of a single event they carry renders several patterns suitable to the representation of a single event). 

More information about CIDOC CRM can be found on their [website](http://www.cidoc-crm.org/).

The current model is meant to consolidate the information pertaining to actors in unique, non-authoritative records. Although CHIN is the custodian of submitted data, the latter is owned by external contributors (museums, libraries, researchers, etc.). As such, CHIN does not claim authority over the data content of records, nor does it intervene in submissioners’ data beyond mapping, cleaning, reconciliation, and the creation of unique identifiers. CHIN’s role in cohering these data will be that of a custodian with no expert status on the information they represent.


## Modelling Conventions

The following conventions will be used when representing patterns in this document.

### Patterns

The ontological relationships between classes have been represented diagrammatically where the structure of triples is visualized instead of the triples themselves. 

For clarity and visibility sake, modelling patterns do not display instances (though they are represented in examples) even though in reality it is the instances that are connected to each other through properties, not the classes themselves (which the diagrams could imply).  

<a name="001_Convention_ClassesAndProperties_p"></a>001_Convention_ClassesAndProperties_p
<iframe frameborder="0" style="width:100%;height:200px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=001_Convention_ClassesAndProperties_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1tP4V68oU1n7l5HedZXb5nFrfnYu2yHXg%26export%3Ddownload"></iframe>

For example, the diagram below illustrates that any instance of the class `E21_Person` can be linked to an instance of the class `E55_Type` through the property `P2_has_type`.

<a name="002_Convention_ClassesAndPropertiesExample_p"></a>002_Convention_ClassesAndPropertiesExample_p
<iframe frameborder="0" style="width:100%;height:200px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=002_Convention_ClassesAndPropertiesExample_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1gr88pIpcq9FVA0Md9fZ74rwIPlAJi-4t%26export%3Ddownload"></iframe>

*Two* different classes mentioned in the same box (e.g. `E33_Linguistic_Object` and `E41_Appellation`) indicate multi-instantiation (i.e. two classes are used to define a single instance).

To facilitate understanding and visually convey how CIDOC CRM entities are used to model different kinds of information, the colour conventions below have been adopted to represent top-level classes along with their subclasses. 

<a name="003_Convention_Colors_p"></a>003_Convention_Colors_p
<iframe frameborder="0" style="width:100%;height:300px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=003_Convention_Colors_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1LMF5iRQKFyNoq5BkehhjQUy8xv1HVs8u%26export%3Ddownload"></iframe>

In addition, [entry nodes](/collections-model/en/semantic-paths-specification/current/introduction#entry-node) defined in the [Semantic Paths Specification](/collections-model/en/semantic-paths-specification/current/introduction) are indicated in bold above their respective class name, as shown below:

<a name="004_Convention_Field_p"></a>004_Convention_Field_p
<iframe frameborder="0" style="width:100%;height:400px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=004_Convention_Field_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1HILva7PuFDfsCg5daNYxTva-BtlwTjBg%26export%3Ddownload"></iframe>

In the above diagram, bolded styling denotes the [Birth/Formation Place](/collections-model/en/semantic-paths-specification/current/entry-nodes#birthformation-place),  [Birth/Formation Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#birthformation-date-begin) and [Birth/Formation Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#birthformation-date-end) nodes. In addition to facilitating understanding, this also illustrates how the translation of inputed data to a semantic framework generates several new elements such as `E67_Birth` and `E52_Time-Span`. 

Occasionally, an `E55_Type` can only have a single instance in a specific pattern. In such a case, it is named in quotation marks underneath the name of the class, as follows:

<a name="005_Convention_Metatype_p"></a>005_Convention_Metatype_p
<iframe frameborder="0" style="width:100%;height:200px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=005_Convention_Metatype_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1qnZZqU6wsy-5dMs86vKqeWtJ-iuNHTlS%26export%3Ddownload"></iframe>

The diagram above represents the gender pattern: the middle element corresponds to the [Gender Type](/collections-model/en/semantic-paths-specification/current/entry-nodes#gender-type) entry node (bolded), which records the gender of the actor (e.g. male, female, two-spirit, etc.). This information is then designated as pertaining to gender by another `E55_Type` that always has the value "Gender". For example, Jean Paul Riopelle is typed as "Male", and this information is designated as being of the type “Gender”. 

When nothing follows parentheses, the data format is `xsd:string`; otherwise, the data format is specified (e.g. dates using `xsd:dateTime`). 

### Examples

Each example is represented with a pattern where instances are illustrated in ovals rather than rectangles. For example, triples mapped to the gender pattern mentioned above:

<a name="006_Convention_Instances_p"></a>006_Convention_Instances_p
<iframe frameborder="0" style="width:100%;height:300px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=006_Convention_Instances_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1C8p1lpiLNDykkf1HUK4SVfJ6jf0p6UQ5%26export%3Ddownload"></iframe>

In this diagram, each instance (Jean Paul Riopelle, Male, Gender Type) are linked together through properties in accordance with the structure of the corresponding pattern in the model.

## A-Z Diagram

Below is an overview diagram that includes **all current patterns** in the Target Model. Each pattern is enclosed in a blue-dotted bubble, the title of which is linked to its corresponding section in the Target Model. Also, each shape in the diagram is linked to its corresponding node in the [Semantic Paths Specification](/collections-model/en/semantic-paths-specification/current/introduction).

<a name="000_Patterns_2.1_p"></a>000_Patterns_2.1_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=000_Patterns_2.1_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D125_6c1wx8iNrqSgqioi3HjvpqTbmyWlM%26export%3Ddownload"></iframe>

> Next: [General Concepts](/collections-model/en/target-model/current/general-concepts)