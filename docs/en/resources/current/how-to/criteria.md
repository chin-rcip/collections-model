---
layout: page
language: en
title: How-To - CRITERIA
permalink: /en/resources/current/how-to/criteria
other_link: /fr/ressources/actuel/mode-demploi/criteria
sidebar: criteriaen
group: resources
subgroup: how-to
date: 2022-11-17
description: This document details an overview of CRITERIA, its usage, and instructions.
---

**Version** 2.0

**Created date**: 2021-04-19

**Last update**: 2022-11-17

**Contact**: For questions or comments regarding CRITERIA, please consult the [Issues](https://github.com/chin-rcip/CRITERIA/issues) section (and open an Issue if it is relevant) or contact us by email at the following address: [pch.RCIP-CHIN.pch@canada.ca](mailto:pch.RCIP-CHIN.pch@canada.ca) with "CRITERIA" in the subject line.


## Main Use

  - To convert RDF files (based on the [CIDOC CRM model](http://www.cidoc-crm.org/)) into [Mermaid](https://mermaid-js.github.io/mermaid/#/) markdown syntax.

## Context

**C**idoc c**R**m **I**n **T**riples m**ER**maid d**I**agr**A**ms (**CRITERIA**) is a Python tool that converts RDF files (based on the [CIDOC CRM model](http://www.cidoc-crm.org/)) in any format (.json-ld, .ttl, etc.) into [Mermaid](https://mermaid-js.github.io/mermaid/#/) markdown syntax (file with .mmd extension), which is then rendered as a (flowchart) diagram by Mermaid javascript.

## Essential Vocabularies and Prior Knowledge

Users should have a good understanding of the following terminologies and technologies before proceeding further:

  - [Instance](https://chin-rcip.github.io/collections-model/en/resources/current/glossary#instance-noun)

  - [Ontology](https://chin-rcip.github.io/collections-model/en/resources/current/glossary#ontology-noun)

  - [Pattern](https://chin-rcip.github.io/collections-model/en/resources/current/glossary#pattern-noun)

  - [Data model](https://chin-rcip.github.io/collections-model/en/resources/current/glossary#model-noun)

  - [Class](https://chin-rcip.github.io/collections-model/en/resources/current/glossary#class-noun) and [Property](https://chin-rcip.github.io/collections-model/en/resources/current/glossary#property-noun)

  - [RDF](https://www.w3.org/RDF/) and its formats, especially [Turtle](https://www.w3.org/TR/turtle/) and [JSON-LD](https://json-ld.org/)

  - [URI](https://en.wikipedia.org/wiki/Uniform_Resource_Identifier)

CRITERIA can generate two types of diagrams from the same RDF data, for example, the following RDF data pertaining to Marc-Aurèle Fortin’s birth and death events:

```turtle
@prefix actor: <https://dopheda.info/crm_e39/> .
@prefix crm: <http://www.cidoc-crm.org/cidoc-crm/> .
@prefix geoname: <http://www.geonames.org/> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

actor:0001 a crm:E21_Person ;
	rdfs:label "Marc-Aurèle Fortin (1888-1970)"^^xsd:string ;
	crm:P98i_was_born <https://dopheda.info/crm_e2/0001> ;
	crm:P100i_died_in <https://dopheda.info/crm_e2/0002> .

<https://dopheda.info/crm_e2/0001> a crm:E67_Birth ;
	crm:P4_has_time-span <https://dopheda.info/crm_e52/0001> ;
	crm:P7_took_place_at geoname:6050610 ;
	crm:P96_by_mother actor:0002 ;
	crm:P97_from_father actor:0003 .

<https://dopheda.info/crm_e2/0002> a crm:E69_Death ;
	crm:P4_has_time-span <https://dopheda.info/crm_e52/0002> ;
	crm:P7_took_place_at geoname:6062563 .

<https://dopheda.info/crm_e52/0001> a crm:E52_Time-Span ;
	crm:P82a_begin_of_the_begin "1888-03-14T00:00:00"^^xsd:dateTime ;
	crm:P82b_end_of_the_end "1888-03-14T23:59:59"^^xsd:dateTime .

<https://dopheda.info/crm_e52/0002> a crm:E52_Time-Span ;
	crm:P82a_begin_of_the_begin "1970-03-02T00:00:00"^^xsd:dateTime ;
	crm:P82b_end_of_the_end "1970-03-02T23:59:59"^^xsd:dateTime .

geoname:6050610 a crm:E53_Place ;
	rdfs:label "Laval, Québec"@fr, "Laval, Quebec"@en .

geoname:6062563 a crm:E53_Place ;
	rdfs:label "Macamic, Québec"^^xsd:string .

actor:0002 a crm:E21_Person ;
	crm:P1_is_identified_by <https://dopheda.info/crm_e41/0002> .

actor:0003 a crm:E21_Person ;
	crm:P1_is_identified_by <https://dopheda.info/crm_e41/0003> .

<https://dopheda.info/crm_e41/0002> a crm:E41_Appellation, crm:E33_Linguistic_Object;
	crm:P190_has_symbolic_content "Amanda Fortier (1861-1953)"^^xsd:string .

<https://dopheda.info/crm_e41/0003> a crm:E41_Appellation, crm:E33_Linguistic_Object;
	crm:P190_has_symbolic_content "Thomas Fortin (1853-1933)"^^xsd:string .

```

  - **Instance**: this type of diagram includes all the "instances" of the RDF, meaning both URIs and literal values.

![](/collections-model/images/criteria_1.png)

  - **Ontology**: this type of diagram includes ONLY the classes and the properties, i.e. the ontological part "ontology" of the pattern. Class means the (triple) object of the property `rdf:type`. Thus, this diagram cannot be generated if an instance does not have a class.

![](/collections-model/images/criteria_2.png)

## Intended Audiences

CRITERIA is a visualization tool for linked data. However, it is not suitable for visualizing an entire dataset, or even an entire data model pertaining to an entity, for the following reasons:

1. Mermaid handles nodes of the same level in its flowchart by spreading them either horizontally or vertically so that the result quickly becomes crowded;

2. The levels flow in either top-down or left-right directions, making the connections between nodes in non-consecutive levels difficult to read.

For example, all data pertaining to Canadian artist Emily Carr (appellation, birth, death, nationality, etc.) should not be visualized in a single diagram using CRITERIA. In other words, this tool is designed to illustrate individual patterns in a data model (e.g. appellations, birth, or death patterns) through diagrams. Thus, the tool is of most interest and use to the following user groups:

  - *Ontologist/Data modeller*: users who are responsible for the design/construction of a data model can use CRITERIA to visualize data in order to check and validate their modelling.

  - *CIDOC CRM user/learner*: users who would like to have a better understanding of CIDOC CRM ontologies through the visualization of an available RDF serialization; CRITERIA is currently built on top of the CIDOC CRM base and its selected extensions. The CIDOC CRM’s colour scheme is the default style.

  - *Developer (technical and/or content)*: users who are responsible for documenting a data model and/or maintaining its digital presence can use CRITERIA to programmatically integrate the visualization of patterns into their ecosystem. This user group would be more interested in the instruction for the [Command Line Interface](#command-line-interface-cli).

## Instructions

CRITERIA can be used in two ways, via either the live demonstrator or the command line interface (CLI).
> **Note**: The script processes triples in random order, meaning the user would not have control on the order of statements in the mermaid output. It also means that running the script over the same RDF file would generate slightly different Mermaid files (i.e. different order of statements), meaning different graphs (i.e. nodes of the same level in different positions). However, the top node’s position and the hierarchy will remain the same.

### Live Demonstrator

The live demonstrator is [available here](http://chinrcip.pythonanywhere.com).

This option is of most interest to users who want to generate diagrams on the go and quickly.

For JSON-LD data, the live demonstrator can process both [contexts](https://w3c.github.io/json-ld-syntax/#the-context) that are embedded in the document or are referenced remotely using URL (such as [Linked.art context](https://linked.art/ns/v1/linked-art.json)).

#### Recommended Browsers

  - **MacOS**: Safari, Chrome, Firefox

  - **Windows**: Firefox

#### Usage

After launching the Live Demonstrator:

1. Click on the `Example` button or paste the RDF data into the editor box under the `RDF input` tab, which can also highlight any syntax errors.

2. Select RDF format from the drop-down menu.

3. Select the type of diagram: instance or ontology.

4. If `ontology` is selected and node annotation is necessary, click on the `SHACL` tab and add your annotation SHACL shape following the syntax as described in the [Node annotation](#node-annotation) section.
5. To add your own configuration, click on the `Configuration` tab and edit or overwrite the JSON configuration following the structure described in the [Configuration](#configuration) section. 

6. Click the `Convert` button.

7. Click on the generated diagram to zoom in or out if needed.

8. To download the diagram as either a PNG, a SVG, or a mermaid markdown file, click on the corresponding button.

![](/collections-model/images/criteria_3.png)

### Command Line Interface (CLI)

This method is of interest to users who want to use CRITERIA programmatically, for example, for batch process and/or implementation purposes in a larger system.

#### Installation

The tool can be installed by cloning [the repository](https://github.com/chin-rcip/CRITERIA) or downloading it as a ZIP file.

#### Requirements

The following programming language versions and libraries are necessary to run this tool:

  - [Python 3.7.0](https://www.python.org/downloads/release/python-370/) and above

  - [rdflib 6.1.1](https://rdflib.readthedocs.io/en/6.1.1/) ([BSD-3-Clause License](https://github.com/RDFLib/rdflib/blob/master/LICENSE)) and above


#### Usage {#usage-1}

##### criteria.py

1. Go to the `/CRITERIA` folder you just cloned or downloaded locally.
	`$ cd /path/to/CRITERIA`

2. Run: `$ python criteria.py Type rdf mmd [-sh SHACL] [-conf CONFIGFILE]`

	- `Type` (***required***): Type of the diagram; the values must be either **instance** or **ontology**.
	- `rdf` (***required***): `/path/to/RDF/input/file`. The downloaded CRITERIA comes with a folder named **rdf** where you can store your RDF files, and simply call `./rdf/your_rdf_input.ttl`. However, you can also call the input file outside of CRITERIA by providing its absolute path, e.g. `/path/to/directory/your_rdf_input.ttl`. The tool can process **several RDF formats** such as Turtle, NTriples, RDF/XML, Trig, JSON-LD, etc.
	- `mmd` (***required***): `/path/to/mmd/output/file`. The downloaded CRITERIA comes with a folder named **mmd** where you can store your mermaid (.mmd) files, and simply provide `./mmd/your_mmd_output.mmd`. However, you can also choose a file location outside of CRITERIA by providing its absolute path, e.g. `/path/to/directory/your_mmd_output.mmd`.
	- `[-sh, --shacl SHACL]` (***optional***): `/path/to/shacl/shape/file`. CRITERIA utilizes the SHACL syntax to annotate a node in the ontological diagram, such as node name, example value, or link to node documentation. See the [Node Annotation](#node-annotation) section for more information on the required syntax. 
	- `[-conf, --configFile CONFIGFILE]` (***optional***): `/path/to/JSON/configuration/file`. This argument allows you to customize your diagram style (color) and declare your ontology·ies. The downloaded CRITERIA comes with a default configuration file `config.json`, which you can use if no configuration JSON file is provided. See the [Configuration](#configuration) section for more information on the required JSON structure. 

3. After the mermaid output is created, the diagram can be generated by:

	- Pasting the entire mermaid markdown file into the code box on [Mermaid Live Editor](https://mermaid-js.github.io/mermaid-live-editor), which offers the option to download it in PNG or SVG;
	- Embedding the mermaid markdown in the web site source code and [using Mermaid.js to render](https://mermaid-js.github.io/mermaid/#/n00b-gettingStarted?id=_3-deploying-mermaid-on-the-browser).
	
Example:

- To generate a diagram rendering instances using the RDF file `BirthDeath_Fortin.ttl` in the `./rdf` folder and the mermaid output to be stored in folder `./mmd`, the command is as follows:
  ```shell
  $ python criteria.py instance ./rdf/BirthDeath_Fortin.ttl ./mmd/BirthDeath_Fortin.mmd
  ```

- To generate a diagram rendering only the ontology without annotated nodes using the same RDF file and folder as above, the command is as follows:
  ```shell
  $ python criteria.py ontology ./rdf/BirthDeath_Fortin.ttl ./mmd/BirthDeath_onto.mmd
  ```

- To generate a diagram rendering only the ontology with annotated nodes using the same RDF file and folder as above, the command is as follows:
    ```shell
    $ python criteria.py ontology ./rdf/BirthDeath_Fortin.ttl ./mmd/BirthDeath_onto.mmd -sh ./rdf/demo_shape.shacl
    ```

#### Node annotation

The SHACL template for ***each annotated node*** is as follows:

```turtle
{shape-URI} a sh:NodeShape ; # Shape of the subject node of the triple in which the annotated node is the object
        skos:example {URI-of-the-subject-node-from-the-input-rdf} ;
	sh:property [
		sh:path {predicate-URI} ;
		sh:defaultValue {value-of-annotated-node} ;
		sh:name "{node-label}" ;
		sh:description "{URL-to-node-documentation}" ;
	] .
```
 
The RDF snippet below is used for demonstration:
 
```turtle
<https://dopheda.info/crm_e2/0001> a crm:E67_Birth ;
	crm:P7_took_place_at geoname:6050610.
```
 
- The node being annotated is `Birth Place`, i.e `geoname:6050610`. However, the defined `sh:NodeShape` is the subject node of the triple in which the annotated node is the object, the URI of Birth `<https://dopheda.info/crm_e2/0001>`.
- `skos:example` (**required**): This property is used to add the subject node's URI, e.g. `<https://dopheda.info/crm_e2/0001>`. This property will not interfere with the actual SHACL validation.
- For the [PropertyShape](https://www.w3.org/TR/shacl/#property-shapes), besides the property `sh:path` which describes the predicate of the triple, the other SHACL properties are non-validating, i.e. not interfering with the actual SHACL validation. Although these SHACL properties describe the property shape, not the annotated node per se, it is valid for CRITERIA usage. For example, the name of `crm:P7_took_place_at` in this particular pattern indicates that its usage is for `Birth Place`.
- `sh:path` (**required**): Predicate URI, e.g. `crm:P7_took_place_at`.
- `sh:name`: Annotated node label, e.g. `"Birth Place"`.
- `sh:describe`: URL of the annotated node's documentation. This value is embedded to the annotated node in the diagram as a link.
- `sh:defaultValue`: Specific value of the annotated node, which could be either URI or literal, e.g. `geoname:6050610`. If URI, this value is embedded to the value node in the diagram as a link, if applicable.
**Note**: *Annotated nodes sharing the same subject node can be grouped together, see the example for `Birth Date` in the [demo_shape.shacl](https://github.com/chin-rcip/CRITERIA/rdf/demo_shape.shacl).*
 
SHACL example:
 
```turtle
ex:BirthPlace a sh:NodeShape ;
	skos:example <https://dopheda.info/crm_e2/0001> ;
	sh:property [
		sh:path crm:P7_took_place_at ;
		sh:defaultValue geoname:6050610 ;
		sh:name "Birth Place" ;
		sh:description "https://chin-rcip.github.io/collections-model/en/semantic-paths-specification/current/entry-nodes#birth-place" ;
	] .
```

#### Configuration

CRITERIA comes with a default configuration including the colour scheme of CIDOC CRM (as proposed by George Bruseker) as well as CIDOC CRM core and some of its extensions that are available in RDF as source ontologies.

To apply your own configuration, prepare a JSON file per below structure:

```json
{
	"style": {},
	"onto": {},
	"prefix": {}
}
```

##### Colour Scheme

Currently, you can customize the background colour, the border colour, and the font color of class nodes and instance nodes.

The **JSON structure** for `"style"` is as below:

```json
"style": {
	"{class-type}": {
		"classColor": "{class-node-background-colour}",
		"classStroke": "{class-node-border-colour}",
		"classFontColor": "{class-node-font-colour}",
		"instanceColor": "{instance-node-background-colour}",
		"instanceStroke": "{instance-node-border-colour}",
		"instanceFontColor": "{instance-node-font-colour}",
		},
}
```
- `{class-type}`: The class, of which nodes are styled accordingly, including prefix, e.g. `crm_E53_Place`, `schema_Thing`. The style is also applied to nodes of its sub-classes. NOTE:
		- For nodes of `rdf:Literal`, ALWAYS use the key **`"Literal"`**.
		- For nodes of more than one class, ALWAYS use the key **`"Multi"`**.
		- ALWAYS use **underscore** as separator between ontology prefix and class name.
- Use **CSS colour value**, e.g. `#90EE09`, or `lightgreen`.

Example:

```json
{
	"style": {
		"Literal": {"classColor": "#ffffff", "classStroke": "#000000", "instanceColor": "#ffffff", "instanceStroke": "#000000"},
		"crm_E53_Place": {"classColor": "#94cc7d", "classStroke": "#000000", "classFontColor": "#000080", "instanceColor": "#e1f1da", "instanceStroke": "#000000", "instanceFontColor":"navy"}
	}
}
```

##### Source Ontologies

CRITERIA comes with several default (CIDOC CRM) ontologies (in RDF), which are stored in the folder `/src/ontologies/`.

  - [CIDOC CRM (v7.1.1)](http://www.cidoc-crm.org/Version/version-7.1.1)

  - [FRBRoo (v2.4)](http://www.cidoc-crm.org/frbroo/ModelVersion/frbroo-v.-2.4)

  - [CRMpc (v7.1.1)](https://cidoc-crm.org/rdfs/7.1.1/CIDOC_CRM_v7.1.1_PC.rdfs)

  - CRMdig (v3.2.2) (retrieved from [[FORTH's 3M](https://isl.ics.forth.gr/3M/)])

  - [CRMarcheo (v1.4.1)](https://www.cidoc-crm.org/crmarchaeo/ModelVersion/version-1.4.1)

  - [CRMsci (1.2.6)](https://cidoc-crm.org/crmsci/ModelVersion/version-1.2.6)

To overwrite the default ontologies, prepare your JSON configuration file following the structure for the keys `"onto"` and `"prefix"` as follows:

```json
	"onto": {
		"{core-ontology}": {
			"core": "{link-or-path-to-core-ontology}",
			"extensions": {
				"{extension-ontology}": "{link-or-path-to-extension-ontology}"			}
		}
	},
	"prefix": {
		"{ontology-prefix}": "{ontology-base-url}"
	}
```

- `{core-ontology}`, `{extension-ontology}`: Acronyms or name of the core ontology and its extension ontologies respectively. The value could be the same as the ontology prefix. 
- `{ontology-prefix}`: Prefix of each ontology, e.g. `crm`, `frbroo`, `schema`. 
- `{link-or-path-to-core-ontology}`: URL or full path to the core ontology RDF file.
- `"extensions"`: Only add this group if extension ontology of the core ontology is used.
		- `{link-or-path-to-extension-ontology}`: URL or full path to the extension ontology RDF file.
- `{ontology-base-url}`: The base URL of each ontology.

Example:

```json
{
"onto": {
		"crm": {
			"core": "https://cidoc-crm.org/rdfs/7.1.1/CIDOC_CRM_v7.1.1.rdfs",
			"extensions": {
				"crmpc": "https://cidoc-crm.org/rdfs/7.1.1/CIDOC_CRM_v7.1.1_PC.rdfs"
			}
		},
		"schema": {
			"core": "https://schema.org/version/latest/schemaorg-current-https.jsonld"
		}

	},
	"prefix": {
		"crm": "http://www.cidoc-crm.org/cidoc-crm/",
		"schema":"https://schema.org/"
	}
}
```

## Memory Aids

  - [Link to Live Demonstrator](http://chinrcip.pythonanywhere.com)

  - Command for CLI: `$ python criteria.py Type rdf mmd [-sh SHACL] [-conf CONFIGFILE]`

## For More Information

  - [Mermaid](https://mermaid-js.github.io/mermaid/#/)

  - [RDFLib](http://rdflib.readthedocs.org)

## Licence

CRITERIA is under the [MIT License](https://github.com/chin-rcip/CRITERIA/blob/master/LICENSE). To meet the attribution requirements of this licence, you must indicate the copyright holder using the following:

> Copyright (c) 2020-2022 Canadian Heritage Information Network, Canadian Heritage, Government of Canada – Réseau Canadien d'information sur le patrimoine, Patrimoine canadien, Gouvernement du Canada

## Notable Users

CHIN would like to recognize the projects and institutions that use CRITERIA, which make it possible for CHIN to improve the tool. If you use CRITERIA and your project is not listed below, please feel free to [contact us](mailto:pch.RCIP-CHIN.pch@canada.ca).

**Project: [Reference Data Models](http://docs.swissartresearch.net/)**

Organization: [Swiss Art Research Infrastructure, University of Zurich](http://swissartresearch.net/)

Description ([Source](https://docs.swissartresearch.net/)):

> The Semantic Reference Data Models project aims to create a series of re-usable templates of semantic patterns to facilitate the integration and querying of cultural heritage data sources. Each template is a collection of semantic patterns and is based on the analysis of selected sources determined to be of relevance to an entity. The developed semantic patterns are mapped to the CIDOC CRM ontology to ensure compatibility across the heritage domain. The patterns can be used to provide reference implementations for institutions and projects not familiar with CIDOC CRM, to create usable guidelines to generate input interfaces for born-CRM semantic data, and to guide mapping processes from extant sources into the CRM conformant reference model using tools such as 3M.

**Project: [Census](http://census.de) - Semantic Census**

Organizations:
- [Humboldt University](https://www.hu-berlin.de/en)
- [Warburg Institute](https://warburg.sas.ac.uk/)
- [Bibliotheca Hertziana - Max-Planck-Institut für Kunstgeschichte](https://www.biblhertz.it/en/home)
- [Hambourg University - Kunstgeschichtliches Seminar](https://www.kulturwissenschaften.uni-hamburg.de/ks.html) (Deutsch only)
- [Getty Research Institute](https://www.getty.edu/research/)

Description:

> The Semantic Census project is a part of a broader long term strategy of the Census project to make this rich research resource on antiquity and the renaissance available to a broader audience. By creating a semantic representation of this catalogue of knowledge, the Census project aims to open the dataset to reuse by scholars in fashions not originally envisioned. Moreover, in publishing a full and rich documentation of its own semantic model, Semantic Census wishes to make it easier for scholars to understand and interrogate the semantic version of the Census data as well as to potentially add to and enrich it, crossing it with their own research and other datasets. The CRITERIA tool has aided the project in auto generating consistent and legible data graphs for representing and understanding the model structures. The Semantic Census data model documentation can be found at: [https://census-antiquity-renaissance.github.io/census-csdm/](https://census-antiquity-renaissance.github.io/census-csdm/).

## Bibliography

Beckett, David, Tim Berners-Lee, Eric Prud’hommeaux, and Gavin Carothers. n.d. "RDF 1.1 Turtle." Accessed May 28, 2021. [https://www.w3.org/TR/turtle/](https://www.w3.org/TR/turtle/).

Canadian Heritage Information Network (CHIN). 2021a. "class (noun)." *Glossary*. Ottawa, ON: Government of Canada/Gouvernement du Canada. [https://chin-rcip.github.io/collections-model/en/resources/current/glossary#class-noun](https://chin-rcip.github.io/collections-model/en/resources/current/glossary#class-noun).

———. 2021b. "instance (noun)." *Glossary*. Ottawa, ON: Government of Canada/Gouvernement du Canada. [https://chin-rcip.github.io/collections-model/en/resources/current/glossary#instance-noun](https://chin-rcip.github.io/collections-model/en/resources/current/glossary#instance-noun).

———. 2021c. "model (noun)." *Glossary*. Ottawa, ON: Government of Canada/Gouvernement du Canada. [https://chin-rcip.github.io/collections-model/en/resources/current/glossary#model-noun](https://chin-rcip.github.io/collections-model/en/resources/current/glossary#model-noun).

———. 2021d. "ontology (noun)." *Glossary*. Ottawa, ON: Government of Canada/Gouvernement du Canada. [https://chin-rcip.github.io/collections-model/en/resources/current/glossary#ontology-noun](https://chin-rcip.github.io/collections-model/en/resources/current/glossary#ontology-noun).

———. 2021e. "pattern (noun)." *Glossary*. Ottawa, ON: Government of Canada/Gouvernement du Canada. [https://chin-rcip.github.io/collections-model/en/resources/current/glossary#pattern-noun](https://chin-rcip.github.io/collections-model/en/resources/current/glossary#pattern-noun).

———. 2021f. "property (noun)." *Glossary*. Ottawa, ON: Government of Canada/Gouvernement du Canada. [https://chin-rcip.github.io/collections-model/en/resources/current/glossary#property-noun](https://chin-rcip.github.io/collections-model/en/resources/current/glossary#property-noun).

JSON-LD Working Group. 2014. "JSON-LD - JSON for Linking Data." JSON-LD. January 16, 2014. [https://json-ld.org/](https://json-ld.org/).

linked.art. 2020. "Linked Art." Linked Art. January 30, 2020. [https://linked.art/](https://linked.art/).

RDF Working Group. 2014. "RDF - Semantic Web Standards." W3C. February 25, 2014. [https://www.w3.org/RDF/](https://www.w3.org/RDF/).

RDFLib Team. n.d. "Rdflib 5.0.0 — Rdflib 5.0.0 Documentation." Accessed May 28, 2021. [https://rdflib.readthedocs.io/en/stable/](https://rdflib.readthedocs.io/en/stable/).

Sveidqvist, Knut. n.d. "Mermaid - Markdownish Syntax for Generating Flowcharts, Sequence Diagrams, Class Diagrams, Gantt Charts and Git Graphs." Accessed May 28, 2021. [https://mermaid-js.github.io/mermaid/#/](https://mermaid-js.github.io/mermaid/#/).

Swiss Art Research Infrastructure. n.d. "SARI Documentation." Accessed May 28, 2021. [https://docs.swissartresearch.net/](https://docs.swissartresearch.net/).

Wikipedia. 2020. "Uniform Resource Identifier." *Wikipedia*. San Francisco, CA: Wikipedia. [https://en.wikipedia.org/w/index.php?title=Uniform_Resource_Identifier&oldid=960824188](https://en.wikipedia.org/w/index.php?title=Uniform_Resource_Identifier&oldid=960824188).