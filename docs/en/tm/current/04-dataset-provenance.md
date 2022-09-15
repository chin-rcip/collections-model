---
layout: page
language: en
title: Dataset Provenance
permalink: /en/target-model/current/dataset-provenance
other_link: /fr/modele-cible/actuel/provenance-du-jeu-de-donnees
sidebar: tm22
date: 2022-03-31
description: The Actors Target Model Specification semantically models actors in a heritage context. Patterns most relevant to actors' lives are presented along with diagrams and examples illustrating them, as well as a record and explanation of relevant decisions that were made when developing said patterns. This is a theoretical documentation that has never been tested or implemented.
---

Version 2.2 ([Previous versions](/collections-model/en/versions))

## At Glance

This pattern can be used to represent the information pertaining to the submission of a dataset by an organization or a person responsible for its creation, provision, and/or update. It includes:

* The dataset provider appellation;
* The dataset provision date·s (including updates).

It pertains specifically to the submission of datasets and not to their contents or to the records they comprise. As such, this pattern should not be used to record: 

* Where an artefact comes from;
* Where the original data is hosted; 
* What originally constituted the record in which an information is found; 
* Where such records originate from. 

## Introduction and Context

### Theoretical Background

Named graphs, as sets of statements federated under a single URI, enable the description of a dataset. They can be applied at different levels of an ensemble of data to structure it and are useful to document provenance (Semantic Web Interest Group 2019). This is especially the case in an aggregation context such as that of DOPHEDA whose goal is to support the aggregation–in a single knowledge graph–of data from heritage institutions in Canada as well as from other relevant sources that might inform or illuminate these foundational datasets. 

### Statement of Need

This objective is directly impacted by a set of features that characterize the heritage milieu: 

* The context from which datasets emanate or in which they are presented is crucial to their understanding. This context is often significant in and of itself to end users who are interested in the historicity of cultural information (i.e. who says what, in which circumstances or environment, and at what time);
* Information on a single artefact can be held by several providers who might not interpret it the same way and provide either complementary or conflicting information about it (the heritage domain typically values and encourages a multiplicity of views and understandings of its artefacts);
* Providers of data can have different profiles, with some being data "owners" (e.g. a museum submitting its collections dataset) and others being data "gatherers" who select specific data from data owners to create new datasets focused on specific aspects or themes (e.g. researchers, aggregators);
* Data providers generally want to retain authority over their data and its integrity when contributing it to larger aggregate knowledge graphs; analogously, adjudicating the veracity or value of content data is not an intended aim of the DOPHEDA project. 

For these reasons, incorporating only the latest versions of datasets into the DOPHEDA knowledge graph would disregard the historicity and contextual features of these datasets and, as such, deprive users of relevant data as well as factual agreements and/or disagreements about it when assessing information they query. Thus, there is a need to record who created what and when, namely the person or organization (who) that provided or updated the dataset (what) and the time at which they did so (when). This is called Dataset Provenance in the Target Model Specification. 

## Description of the Pattern

A named graph is applied at the dataset level which enables the treatment of said dataset as a single instance of `D1_Digital_Object` so that information pertaining to the digital object provision (e.g. author, date) can be appended to it. This named graph is an instance of `D1_Digital_Object` linked to an instance of `E65_Creation` by the property `P94_has_created`. This same instance of `E65_Creation` is linked to the provider (an instance of `E39_Actor`) by an instance of `PC14_carried_out_by` whose domain is indicated by the property `P01_has_domain` linked to the instance of `E65_Creation`, and whose range is indicated by the property `P02_has_range` linked to the instance of `E39_Actor`. 

This instance of `E39_Actor` is also linked by the property `P1_is_identified_by` to an instance of both `E41_Appellation` and `E33_Linguistic_Object` which in turn is linked to the literal value of the [Dataset Creation Participant Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#dataset-creation-participant-appellation) through the property `P190_has_symbolic_content`. The role of the provider is indicated by linking the instance of `PC14_carried_out_by` to the [Dataset Creation Participant Role](/collections-model/en/semantic-paths-specification/current/entry-nodes#dataset-creation-participant-role) value (an instance of `E55_Type`) through the property `P14.1_in_the_role_of`.

The time at which the provision was made is indicated using the [Temporal Bounds](/collections-model/en/target-model/current/temporal-bounds) pattern linked to the instance of `E65_Creation` through the property `P4_has_time-span` with values extracted from the [Dataset Creation Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#dataset-creation-date-begin) and [Dataset Creation Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#dataset-creation-date-end) entry nodes.

## Diagram

<a name="014_Pattern_DatasetProvenance_p"></a>014_Pattern_DatasetProvenance_p

<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=014_Pattern_DatasetProvenance_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1RFjwIOuaIoTKDCJIYg-_04LzN3fsqKEk%26export%3Ddownload"></iframe>

## Examples

The National Gallery of Canada (`P190_has_symbolic_content`, Dataset Creation Participant Appellation "National Gallery of Canada") could have submitted a dataset (P14.1_in_the_role_of, Dataset Creation Participant Role "Provider") that would have been mapped to DOPHEDA's Target Model Specification (P14.1_in_the_role_of, Dataset Creation Participant Role "Creator") by CHIN (`P190_has_symbolic_content`, Dataset Creation Participant Appellation "CHIN") on January 15, 2021 (`P82a_begin_of_the_begin`, Dataset Creation Date Begin; `P82b_end_of_the_end`, Dataset Creation Date End). This would be illustrated as the following, with the NGC being the provider of data (i.e. having authority over the contents and ownership of the dataset), and CHIN being the creator (i.e. being in charge of mapping the input dataset to the model):

<div id="0001_3_dataset-prov" class="example"></div>

Such named graphs can be expressed in various syntaxes such as [NQuads](https://www.w3.org/2009/07/NamedGraph.html#syntax-1), [TRiG](https://www.w3.org/2009/07/NamedGraph.html#syntax-1), or [JSON-LD](https://www.w3.org/TR/json-ld11/#named-graphs). The following is an example in JSON-LD format: 


```

{

  "@context": {

    "rdf": "http://www.w3.org/1999/02/22-rdf-syntax-ns#",

    "rdfs": "http://www.w3.org/2000/01/rdf-schema#",

    "xsd": "http://www.w3.org/2001/XMLSchema#",

    "crm": "http://www.cidoc-crm.org/cidoc-crm/",

    "crmdig": "http://www.ics.forth.gr/isl/CRMext/CRMdig.rdfs/",

    "frbroo": "http://iflastandards.info/ns/fr/frbr/frbroo/"

  },

  "@id": "https://www.dopheda.info/d1//001_1234",

  "@type": "crmdig:D1_Digital_Object",

  "crm:P94i_was_created_by": {

            "@id": "https://www.dopheda.info/e65/001_5678",

            "@type": "crm:E65_Creation",

            "crm:P4_has_time-span": {

                      "@id": "https://www.dopheda.info/e52/001_9101",

                      "@type": "crm:E52_Time-Span",

                       "crm:P82a_begin_of_the_begin": {

                                "@value": "1665-04-24T00:00:00",

                                "@type": "xsd:dateTime"

                      },

                      "crm:P82b_end_of_the_end": {

                              "@value": "1665-04-24T23:59:59",

                              "@type": "xsd:dateTime"

                    }

            }

  },

  "@graph": [

    {

              "@id": "https://www.dopheda.info/e39/001_9999",

              "@type": "crm:E21_Person"    }

          ]

}





```

To retrieve provenance data, a `GRAPH` clause must be included in the SPARQL query (SPARQL Working Group 2013).

## Related Documentation

### External Models

* Nomisma.org: [VoID RDF](http://nomisma.org/documentation/contribute)

### Entry Nodes

* [Dataset Creation Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#dataset-creation-date-begin) \| Checklist
* [Dataset Creation Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#dataset-creation-date-end) \| Checklist
* [Dataset Creation Participant Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#dataset-creation-participant-appellation) \| Checklist
* [Dataset Creation Participant Role](/collections-model/en/semantic-paths-specification/current/entry-nodes#dataset-creation-participant-role) \| Checklist

### CIDOC CRM Entities

* `D1_Digital_Object`
* `E33_Linguistic_Object` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E33)]
* `E39_Actor` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E39)]
* `E41_Appellation` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E41)]
* `E52_Time-Span` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E52)]
* `E55_Type` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E55)]
* `E65_Creation` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E65)]
* `PC14_carried_out_by`
* `P01_has_domain (is_domain_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P01)]
* `P02_has_range (is_range_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P02)]
* `P1_is_identified_by (identifies)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P1)]
* `P4_has_time_span (is_time-span_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P4)]
* `P14.1_in_the_role_of` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P14.1)]
* `P82a_begin_of_the_begin`
* `P82b_end_of_the_end`
* `P94_created (was_created_by)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P94)]
* `P190_has_symbolic_content` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P190)]

## Discussion

### Rationale

There are two main approaches to documenting provenance information: 

* Appending a provenance pattern centered around the use of an instance of `E13_Attribute_Assignment` to each triple; 
* Using a named graph applied either on the provider record or on its dataset. 

The use of the class `E13_Attribute_Assignment` across the knowledge graph has the advantage of increasing precision when establishing provenance information. However, it also makes the model in general much heavier as each triple must be assigned to this pattern. This is notwithstanding that when multiple and contradictory statements are made about a resource, various and distinct instances of `E13_Attribute_Assignment` have to be created and linked to their respective statement. From a processing standpoint, this would become increasingly burdensome as the amount of data would grow exponentially. This is why this approach is not adopted by CHIN in the DOPHEDA environment. 

Considering each triple in the named graph inherits the graph’s information, what ensemble to apply it to (record or dataset) is debatable. This is especially important because it directly impacts the granularity of the provenance information a dataset structure enables. A provider’s dataset-based named graph might be better for data provenance documentation and information management, but a more granular record-based named graph might be preferable from a technical standpoint.

To determine which approach is preferable, a survey on the implementation of named graphs in the CIDOC CRM community and a [technical report](/collections-model/en/technical-reports/current/named-graph-survey-report-1) on the matter have been made. Based on the results and discussions with CHIN’s Semantic Committee, the decision to implement named graphs at the dataset level has been made. The following elements have heavily influenced this decision:

* It is the most common practice, at least within the CIDOC CRM community;
* It entails a lower technological barrier than a record-based approach, as not all available software and processes are able to support a more granular record-level structure;
* It prevents the issue of border entities (i.e. shared entry nodes of multiple entities such as [birth](/collections-model/en/semantic-paths-specification/current/entry-nodes#birth-and-death) entry nodes that are shared between an actor and their parents) since, as all entities from a provider are placed in a single and shared named graph, information is uniformly applied;
* Even though there are concerns over the possibility of missing information that might not be included in a query, the entirety of the data provided is mapped to the Target Model so that it is not complicated to set a SPARQL query retrieving the data of a single entity (i.e. all triples pertaining to such entity, mainly an actor or an object).

The named graph is modelled as an instance of `D1_Digital_Object` because, as a sub-class of `E73_Information_Object`, it is the most precise entity that can be used. In addition, because it is part of the [CIDOC CRM Model for the Provenance of Metadata](http://www.cidoc-crm.org/crmdig/) (CRMdig) extension dedicated to the representation of digital contents, `D1_Digital_Object` is intended to be used with several dedicated properties. These, however, cannot be used in conjunction with the class `E73_Information_Object` which is less expressive. Even if there is no need to use these dedicated properties at the moment, it is likely that the need will arise in the future and, as such, the use of `D1_Digital_Object` is the most sustainable.  

### Limitations

Each triple within a named graph inherits the graph’s appended information. Subsets (e.g. targeted triples) can be queried specifically by using graph identifiers (Dodds and Davis 2019, 53). Because the provenance is managed at the dataset level, the same provenance information is applied to every triple in the graph. To express complex information pertaining to a specific entity (e.g. indicating that a date attribution is uncertain), another pattern must be used, either the:

* [Record Provenance](/collections-model/en/target-model/current/record-provenance) pattern when indicating the provenance of a predetermined record; 
* [Curatorial Note](/collections-model/en/target-model/current/curatorial-note) pattern when indicating the provenance of a specific triple which is an unusual but acceptable use of the field.

However, these options apply to a specific entity but never to a group of entities or triples. This implies that the provenance of any complex statement modelled with multiple triples cannot be documented.

### Related GitHub Issues

* [Issue #14 "We need to manage the updates of records (and Named Graphs?)"](https://github.com/chin-rcip/collections-model/issues/14)
* [Issue #34 "Should Cataloguers be documented in the Record [Provenance] pattern?"](https://github.com/chin-rcip/collections-model/issues/34)
* [Issue #45 "Named Graphs: Record vs. Dataset"](https://github.com/chin-rcip/collections-model/issues/45)

### Edge Cases

In the case of a single provider sending multiple and separate files of their dataset (such as one for the groups and one for the persons), it is either possible to create a named graph for each file, or unite them in a single named graph. The first option provides a more granular description of the provider's data, especially if the files contain different provenance information (such as creation and/or update dates). The second option helps simplify the named graph management by reducing the number of named graphs.

Therefore, the choice between documenting the submission of new data about a specific entity as a new named graph or as further provenance information on the record can become difficult to make depending on the ecosystem governance in place. As another example, in a context where a museum offers a crowdsourcing platform to enrich its content and an independent expert contributes to a record, the data provider could include the provenance of this information in the Record Provenance pattern, but could also prefer that external data be managed in a different named graph. As such, there could be a named graph that only represents the information submitted by the external expert.

## Bibliography

Bruseker, George, and Nicola Carboni. "Digital Object Reference Data Model (SARI Documentation)." *Swiss Art Research Infrastructure*. December 8, 2020. [https://docs.swissartresearch.net/et/do/#existence](https://docs.swissartresearch.net/et/do/#existence).

Bruseker, George, Trang Dang, Philippe Michon, and Stephen Hart. *Cultural Heritage Named Graph Usage Survey Report (Part 1)*. DOPHEDA Technical Reports. Ottawa, CA-ON: Canadian Heritage Information Network (CHIN), 2020. [/collections-model/en/technical-reports/current/named-graph-survey-report-1](/collections-model/en/technical-reports/current/named-graph-survey-report-1).

Dodds, Leigh, and Ian Davis, eds. "Named Graph." *Linked Data Patterns: A Pattern Catalogue for Modelling, Publishing, and Consuming Linked Data*. 2019: 53–54. [https://patterns.dataincubator.org/book/named-graphs.html](https://patterns.dataincubator.org/book/named-graphs.html).

Doerr, Martin. "A Digital Provenance Ontology." Tutorial presented at the *International Conference on Theory and Practice of Digital Libraries*. Berlin, DE-BE, September 25, 2011. [http://www.cidoc-crm.org/Resources/a-digital-provenance-ontology-0](http://www.cidoc-crm.org/Resources/a-digital-provenance-ontology-0).

Doerr, Martin, and Christian Emil Ore, eds. *Definition of the CIDOC Conceptual Reference Model*. CIDOC CRM Documentations, 7.0.1. Paris, FR-IDF: International Council of Museums (ICOM), 2020. [http://www.cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.0.1_%2018-10-2020.pdf](http://www.cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.0.1_%2018-10-2020.pdf).

Doerr, Martin, Stephen Stead, and Maria Theodoridou. *Definition of the CRMdig: An Extension of CIDOC-CRM to Support Provenance Metadata*. CRMdig, 3.2.1. Heraklion, GR-CR: CIDOC CRM, 2016. [http://www.cidoc-crm.org/crmdig/ModelVersion/version-3.2.1](http://www.cidoc-crm.org/crmdig/ModelVersion/version-3.2.1).

Semantic Web Interest Group. "Named Graphs." *W3*. September 27, 2019. [https://www.w3.org/2004/03/trix/](https://www.w3.org/2004/03/trix/).

SPARQL Working Group. "SPARQL 1.1 Query Language." W3C Recommendation. March 21, 2013. [https://www.w3.org/TR/sparql11-query/](https://www.w3.org/TR/sparql11-query/).

