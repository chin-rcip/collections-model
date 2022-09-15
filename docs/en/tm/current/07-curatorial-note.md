---
layout: page
language: en
title: Curatorial Note
permalink: /en/target-model/current/curatorial-note
other_link: /fr/modele-cible/actuel/note-curatoriale
sidebar: tm22
date: 2022-03-31
description: The Actors Target Model Specification semantically models actors in a heritage context. Patterns most relevant to actors' lives are presented along with diagrams and examples illustrating them, as well as a record and explanation of relevant decisions that were made when developing said patterns. This is a theoretical documentation that has never been tested or implemented.
---

Version 2.2 ([Previous versions](/collections-model/en/versions))

## At Glance

This pattern can be used to represent the information associated with an actor that cannot be recorded through structured fields, but that pertains to another data node represented elsewhere in the model. It can be general or more specific, and is primarily meant to offer further knowledge. It comprises comments, remarks, or descriptions such as explanations, notes, grades, evaluations, etc. This pattern includes: 

* The content of a curatorial note;
* The author of a curatorial note;
* The language in which a curatorial note was recorded.

This pattern should not be used to represent:

* The annotations that pertain to the model itself and arise during the mapping process (e.g. data quality assessments, modelling, and/or mapping issues, documentation, information that the provider wishes to submit alongside the dataset) (the [General Concepts – Annotations or Comments](/collections-model/en/target-model/current/general-concepts#annotations-or-comments) pattern should be used instead);
* The unstructured contents (e.g. textual) of a data field (the [Messy Data](/collections-model/en/target-model/current/messy-data) pattern should be used instead);
* The biographical description·s of an actor (the [Biography](/collections-model/en/target-model/current/biography) pattern should be used instead);
* The data that is not covered by the Target Model Specification, in which case proposals for new semantic patterns can be submitted to CHIN via the [GitHub Issues](https://github.com/chin-rcip/collections-model/issues) section.

## Introduction and Context

### Theoretical Background

Most museums have a remark or note field containing information that can be supplemental to either the actors and objects in general, or to a specific data field. For example, a note might clarify that the date of birth of an artist is estimated to be at least 15 years before the production of the artist’s earliest-known work. Such notes are often textual elements that are distinct from descriptive texts intended to be published (e.g. captions). Such curatorial note contents can help contextualize the data they document and are, as such, a necessary element of heritage data models.

In order to adequately answer the needs of diverse users–most often determined by the fields of activity and target communities that typically circumscribe model development (Bruseker 2017)–, an aggregating model must accommodate the widest range of information from a field of activity possible, and account for variability in the nature, format, and understanding of the data. As a result, it is customary to have a combination of precise patterns to ensure a minute representation of structured information, along with broader patterns to accommodate unanticipated information that cannot be integrated into existing metadata fields (Allemang, Hendler, and Gandon 2020, 26-34). 

### Statement of Need

Curatorial notes qualify as such unanticipated information that must be accounted for and can be useful to identify potential additions or enhancements to a model (e.g. new patterns or revisions of more precise ones). 

By default, the creator of a curatorial note is considered to be the institution or person providing the data (see the [Dataset Provenance](/collections-model/en/target-model/current/dataset-provenance) pattern). However, if a curator or expert was explicitly recorded as the note’s author/creator, this information should also be modelled in this pattern.

In addition, because of their textual form, it is essential to document the language in which curatorial notes are written to facilitate further potential retrieval and analysis of information. 

## Description of the Pattern

For each curatorial note, an instance of `E39_Actor` or one of its sub-classes is first linked by the property `P67i_is_referred_to_by` to an instance of `E33_Linguistic_Object` which is then connected to:

* An instance of `E55_Type` (a specified qualifier node) labelled "Curatorial Note" by the property `P2_has_type`;
* The literal value of the [Curatorial Note Content](/collections-model/en/semantic-paths-specification/current/entry-nodes#curatorial-note-content) by the property `P190_has_symbolic_content`;
* The [Curatorial Note Language](/collections-model/en/semantic-paths-specification/current/entry-nodes#curatorial-note-language) value (an instance of `E56_Language`) by the property `P72_has_language`;
* An instance of `E65_Creation` by the property `P94i_was_created_by` which is linked to an instance of `E39_Actor` that represents the author of the curatorial note by the property `P14_carried_out_by`. This instance of `E39_Actor` is also linked by the property `P1_is_identified_by` to an instance of both `E33_Linguistic_Object` and `E41_Appellation` which is qualified by the literal value of the [Curatorial Note Author Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#curatorial-note-author-appellation) by the property `P190_has_symbolic_content`.

## Diagram

<a name="068_Pattern_CuratorialNote_p"></a>068_Pattern_CuratorialNote_p

<iframe frameborder="0" style="width:100%;height:500px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=068_Pattern_CuratorialNote_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1HZiNbXGEGpA1TsVFiOX7GQerGYjzVKnM%26export%3Ddownload"></iframe>

## Examples

### Example 1

The record of Yousuf Karsh in Artists in Canada includes a *Remarks* field with the value "Immigrated to Canada in 1924" (`P190_has_symbolic_content`, Curatorial Note Content) (Canadian Heritage, Government of Canada 2011).

<div id="0001_100_curatorial-note" class="example"></div>

### Example 2

Greg A. Hill (`P190_has_symbolic_content`, Curatorial Note Author Appellation), as Audain Senior Curator of Indigenous Art at the National Gallery of Canada, might want to comment on an actor.

<div id="0001_126_curatorial-note" class="example"></div>

### Example 3

The note "Rebecca Belmore was the first Indigenous woman to present at the Canadian pavilion of the Venice Biennale in 2005" (`P190_has_symbolic_content`, Curatorial Note Content) is written in English (`P72_has_language`, Curatorial Note Language) (Berlin and Baird 2014).

<div id="0001_127_curatorial-note" class="example"></div>

## Related Documentation

### External Models

* Linked.art: [Baseline Patterns ​​– Statements about a Resource](https://linked.art/model/base/#statements-about-a-resource) 
* SARI: [Person Reference Data Model – Description](https://docs.swissartresearch.net/et/persons/#description)

### Entry Nodes

* [Curatorial Note Content](/collections-model/en/semantic-paths-specification/current/entry-nodes#curatorial-note-content) \| Checklist
* [Curatorial Note Language](/collections-model/en/semantic-paths-specification/current/entry-nodes#curatorial-note-language) \| Checklist
* [Curatorial Note Author Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#curatorial-note-author-appellation) \| Checklist

### CIDOC CRM Entities

* `E33_Linguistic_Object` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E33)]
* `E39_Actor` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E39)]
* `E41_Appellation` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E41)]
* `E55_Type` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E55)]
* `E56_Language` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E56)]
* `E65_Creation` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E65)]
* `P1_is_identified_by (identifies)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P1)]
* `P2_has_type (is_type_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P2)]
* `P14_carried_out_by (performed)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P14)]
* `P72_has_language (is_language_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P72)]
* `P94_has_created (was_created_by)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P94)]
* `P190_has_symbolic_content` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P190)]

## Discussion

### Rationale

In most cases, curatorial note values will be unstructured text which is why the class `E33_Linguistic_Object` is used in conjunction with the property `P190_has_symbolic_content`. However, since this class is also employed in other patterns, it must be identified as pertaining to a curatorial note by identifying it as an instance of `E55_Type` with a fixed label "Curatorial Note". This clarifies the nature of the information and facilitates queries.

Because the note is considered to be the product of an action done by its author, it can be regarded as being "created" (`E65_Creation`); this is why the class `E65_Creation` should be used rather than its more broadly defined super-class `E7_Activity`.

### Limitations

It is possible to extract meaningful data from curatorial notes, but this is labour intensive and/or requires technological resources and expertise most heritage institutions do not have (e.g. natural language processing). This is the case with the current DOPHEDA environment; for the time being, such contents cannot be further structured.

In addition, there is no way to identify or categorize curatorial notes by subject. If a user is interested in a particular topic, they cannot filter the curatorial notes in order to narrow their search (see [Issue #63](https://github.com/chin-rcip/collections-model/issues/63)). 

### Related GitHub Issues

* [Issue #20 "What to do with the 'Remarks' field in some museums?"](https://github.com/chin-rcip/collections-model/issues/20) 
* [Issue #63 "Curatorial Note Topic"](​​https://github.com/chin-rcip/collections-model/issues/63) 

### Edge Cases

#### Example 1 {#edge-cases-example-1}

Using the same example above about the remarks in the Artists in Canada’s record of Yousuf Karsh, the value "Immigrated to Canada in 1924" can be considered as a note of a staying activity in Canada starting in 1924.

#### Example 2 {#edge-cases-example-2}

Marie-Guillemine Benoist’s *Portrait of Madeleine* was formerly titled using a racial description. Recent scholarship has established the sitter’s name as "Madeleine", although her last name remains unknown. An Annotation could be placed on its artefact appellations (with "Portrait of Madeleine" as the preferred appellation (Artefact Appellation Precedence), "Former title displaying insensitive racial language" Annotation; the former title as a non-preferred appellation (Artefact Appellation Precedence), "Now titled Portrait of Madeleine" Annotation; "Portrait d’une femme noire", non-preferred appellation (Artefact Appellation Precedence), "Former title displaying insensitive racial language" Annotation), but a Curatorial Note Content might also be used on the actor "Madeleine" who is depicted ("Sitter in *Portrait of Madeleine*, former title displaying insensitive racial language with the sitter identified as being named "Madeleine" by Viktoria Schmidt-Linsenhoff"). The same Curatorial Note Content could also be applied to Marie-Guillemine Benoist. Whether the Curatorial Note Content is related to the artist, the person depicted, or both, depends on the provider's wording (Schmidt-Linsenhoff 2013; Waller 2018).

## Bibliography

Allemang, Dean, James A. Hendler, and Fabien Gandon. *Semantic Web for the Working Ontologist: Effective Modeling for Linked Data, RDFS, and OWL*. Third Edition. ACM Books 33. New York, US-NY: ACM Books, 2020.

Bekiari, Chryssoula, George Bruseker, Martin Doerr, Christian-Emil Ore, Stephen Stead, and Athanasios Velios, eds. *Definition of the CIDOC Conceptual Reference Model*. CIDOC CRM Documentations, 7.1. Paris, FR-IDF: CIDOC CRM Special Interest Group, 2021. [http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf](http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf.).

Berlin, Mira, and Daniel Baird. "Rebecca Belmore." *The Canadian Encyclopedia*. Toronto, CA-ON: Historica Canada, 2016 [2014]. [https://www.thecanadianencyclopedia.ca/en/article/rebecca-belmore](https://www.thecanadianencyclopedia.ca/en/article/rebecca-belmore).

Bruseker, George. "Principles for Modelling Ontologies: A Short Reference Guide." *Parthenos Project*. 17 (2017): 72.

Canadian Heritage, Government of Canada. "Karsh, Yousuf." *Artists in Canada*. Ottawa, CA-ON: Government of Canada, 2011. [https://app.pch.gc.ca/application/aac-aic/artiste_detailler_bas-artist_detail_bas.app?lang=en&rID=8494](https://app.pch.gc.ca/application/aac-aic/artiste_detailler_bas-artist_detail_bas.app?lang=en&rID=8494).

Schmidt-Linsenhoff, Viktoria. "Who Is the Subject? Marie-Guillemine Benoist’s Portrait d’une Négresse." *Slave Portraiture in the Atlantic World*, edited by Agnes Lugo-Ortiz and Angela Rosenthal. Paperback. Cambridge, UK-CAM: Cambridge University Press, 2013: 315-345.

Waller, Susan. « Marie-Guillemine Benoist, Portrait de Madeleine. » *Smarthistory* (blogue). 26 septembre 2018. [https://smarthistory.org/benoist-portrait/](https://smarthistory.org/benoist-portrait/).


