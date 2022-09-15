---
layout: page
language: en
title: Reference Document Location
permalink: /en/target-model/current/reference-document-location
other_link: /fr/modele-cible/actuel/emplacement-du-document-de-reference
sidebar: tm22
date: 2022-03-31
description: The Actors Target Model Specification semantically models actors in a heritage context. Patterns most relevant to actors' lives are presented along with diagrams and examples illustrating them, as well as a record and explanation of relevant decisions that were made when developing said patterns. This is a theoretical documentation that has never been tested or implemented.
---

Version 2.2 ([Previous versions](/collections-model/en/versions))

## At Glance

This pattern can be used to represent the basic information pertaining to the identification of a document containing information about an actor for reference purposes. It includes: 

* The call number assigned to a reference document by its archiving institution;
* The appellation of the archiving institution of a reference document;
* The physical location of a reference document.

This pattern should not be used to represent:

* The detailed description of a reference document;
* The location of a reference document’s digital representation.

## Introduction and Context

### Theoretical Background

In 1993, Margaret Hedstrom forecasted that the arrival of information technologies would induce a paradigm shift in information sciences; archivists’ main practice of augmenting scarce descriptive information would adapt in order to focus on the identification, selection, and retrieval of knowledge (Hedstrom 1993, 59). This evolution of practices, combined with the digitization of information that has led to users becoming increasingly global, has put an increased focus on the location of the physical embodiment of information as a way to classify documents, to distinguish them from one another, and to retrieve them (Hjørland & Gnoli 2016). 

Heritage organizations such as museums often organize their core data on the basis of principles that differ from those of archives and libraries, such as subject- or exhibition-specific classification systems rather than systems that would be discipline- or phenomena-specific. Nonetheless, they often mobilize relevant standards from libraries and archives to organize information such as reference materials, for instance, bibliographies used in the context of research (Hjørland & Gnoli 2016). As such, the proper documentation of the location of a document is crucial and, even though it is sometimes intricately linked to the concept of provenance (see the [Dataset Provenance](/collections-model/en/target-model/current/dataset-provenance) and [Record Provenance](/collections-model/en/target-model/current/record-provenance) patterns), it should be distinguished from it as the location pertains to the physical place a document is situated, no matter its custodian (Tognoli & Guimaraes 2018).

Recording the physical location of a stored document is even more important considering it is often necessary for practitioners to consult originals. The location of a document or its main custodian might sometimes differ from where the document is stored. Thus, there is a need to identify and locate the physical document embodying heritage reference information for accurate information description as well as retrieval. 

It is important to identify: 

* Who manages (as opposed to owns) the document (i.e. the name of the archiving institution managing the document) so that they can be contacted if need be; 
* Where its storage facility is located (i.e. the address of the archiving institution managing the document) so the practitioner can access the document; 
* Where to retrieve the document within this facility (i.e. the location of the document in storage) so that it can be consulted by the practitioner. 

### Statement of Need

Most museums as well as other heritage organizations hold records about the actors they document. For example, the [Artists in Canada](https://app.pch.gc.ca/application/aac-aic/description-about.app?lang=en) database documents the primary sources of its records information in the data field "File Location". This information can provide access to other resources in which more data about the actor might be documented.

There are three basic information required to quickly identify and potentially access such reference source·s. First and foremost, which institution is holding the record, i.e. its appellation, should be indicated. The institution itself might have multiple branches at different locations, but the specific location where the record is kept should be documented. Also, processed archives and their items are always assigned call numbers for the purposes of identification and retrieval. 

## Description of the Pattern

The reference documentary object, an instance of `E22_Human-Made_Object`, is linked to:

* An instance of `E55_Type` (a specified qualifier node) labelled "Reference Document" by the property `P2_has_type`;
* The [Reference Document Place](/collections-model/en/semantic-paths-specification/current/entry-nodes#reference-document-place) value (an instance of `E53_Place`) through the property `P54_has_current_permanent_location`;
* The custodian institution, which is an instance of `E74_Group`, by the property `P49_has_current_or_former_keeper`. This instance of `E74_Group` is linked to an instance of both `E41_Appellation` and `E33_Linguistic_Object` through the property `P1_is_identified_by` which renders the literal value of the [Reference Document Institution Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#reference-document-institution-appellation) through the property `P190_has_symbolic_content`;
* An instance of `E42_Identifier` by the property `P1_is_identified_by`. This instance of `E42_Identifier` is qualified by an instance of `E55_Type` (a specified qualifier node) labelled "Call Number" by the property `P2_has_type`. The same instance of `E42_Identifier` also renders the literal value of the [Reference Document Call Number](/collections-model/en/semantic-paths-specification/current/entry-nodes#reference-document-call-number) through the property `P190_has_symbolic_content`;
* An instance of `E31_Document` by the property `P128_carries`. This instance of `E31_Document` then connects to the actor documented in the reference documentary object (an instance of `E39_Actor`) by the property `P70_documents` and is qualified by an instance of `E55_Type` (a specified qualifier node) labelled "Record" by the property `P2_has_type`.

## Diagram

<a name="074_Pattern_DocumentLocation_p"></a>074_Pattern_DocumentLocation_p

<iframe frameborder="0" style="width:100%;height:500px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=074_Pattern_DocumentLocation_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1SV-iF2aYJUqwDYMJt4ZujjlDVJM8Jasn%26export%3Ddownload"></iframe>

## Examples

The archives of Yousuf Karsh can be found at Library and Archives of Canada (`P190_has_symbolic_content`, Reference Document Institution Appellation) at 625 Carr Boulevard, Gatineau QC Canada (`P54_has_current_permanent_location`, Reference Document Place). Its reference number is R613-0-5-E (`P190_has_symbolic_content`, Reference Document Call Number) (Library and Archives Canada 2022). 

<div id="0001_100_reference-document-location" class="example"></div>

## Related Documentation

### External Models

* Linked.art: [Texts and Documents](https://linked.art/model/document/)
* SARI: [Archival Unit Reference Data Model](https://docs.swissartresearch.net/et/archival/) 

### Entry Nodes

* [Reference Document Call Number](/collections-model/en/semantic-paths-specification/current/entry-nodes#reference-document-call-number) \| Checklist
* [Reference Document Institution Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#reference-document-institution-appellation) \| Checklist
* [Reference Document Place](/collections-model/en/semantic-paths-specification/current/entry-nodes#reference-document-place) \| Checklist

### CIDOC CRM Entities

* `E22_Human-Made_Object` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E22)]
* `E31_Document` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E31)]
* `E33_Linguistic_Object` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E33)]
* `E39_Actor` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E39)]
* `E41_Appellation` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E41)]
* `E42_Identifier` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E42)]
* `E53_Place` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E53)]
* `E55_Type` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E55)]
* `E74_Group` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E74)]
* `P1_is_identified_by (identifies)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P1)]
* `P2_has_type (is_type_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P2)]
* `P49_has_former_or_current_keeper (is_former_or_current_keeper_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P49)]
* `P54_has_current_permanent_location (is_current_permanent_location_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P54)]
* `P70_documents (is_documented_in)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P70)]
* `P128_carries (is_carried_by)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P128)]
* `P190_has_symbolic_content` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P190)]

## Discussion

### Rationale

In CIDOC CRM, there is a distinction between the information and the physical carrier of this information (such as a book, a document, etc.) (Bekiari et al. 2021, sect. E73 Information Object). It is therefore necessary to employ the class `E22_Human-Made_Object` in conjunction with the class `E31_Document` to document the actor of reference (`E39_Actor`) using the property `P70_documents`.

The class `E73_Information_Object` encompasses a large set of concepts that have an "objectively recognizable structure and are documented as single units" (Le Bœuf et al. 2015, sect. E73 Information Object)]. However, it is also advised that "instances of `E73_Information_Object` of a documentary nature [...] be declared as instances of the `E31_Document` sub-class" (Le Bœuf et al. 2015, sect. E73 Information Object), which is why the latter has been preferred for the DOPHEDA model. 

Regarding the institution holding the reference documentary object, there is a distinction between its physical location (e.g. the city, address, or building where it is established–which is documented as an instance of `E53_Place`) and the institution itself (i.e. an instance of `E74_Group`). 

### Limitations

At the moment, this pattern is modelled to capture the minimum data pertaining to the reference document in relation to the concerned actor. Thus, other descriptive details about the reference document are not accounted for. 

### Related GitHub Issues

[Issue #4 "Paper Files Location & AiC"](https://github.com/chin-rcip/chin-rcip/issues/4)

### Edge Cases

A reference document call number refers to a document’s identifier which in turn determines its location within an institution. However, an archival institution might have multiple physical addresses or branches. If the building where the reference document is held has no assigned documentation field, it could either be documented under the Reference Document Call Number entry node (e.g. "PS8576 U57 W46 1979 - Wellington General Collection"), the Reference Document Place entry node (e.g. "395 Wellington St, Ottawa, ON K1A 0N4 - Wellington General Collection"), or the Reference Document Institution Appellation entry node (e.g. "Library and Archives Canada - Wellington General"). This might be problematic in terms of data entry, but is mitigated by the fact that all such information is represented in a single pattern. It might, however, create conflicting or confusing information. 

## Bibliography

Bekiari, Chryssoula, George Bruseker, Martin Doerr, Christian-Emil Ore, Stephen Stead, and Athanasios Velios, eds. *Definition of the CIDOC Conceptual Reference Model*. CIDOC CRM Documentations, 7.1. Paris, FR-IDF: CIDOC CRM Special Interest Group, 2021. [http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf](http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf).

Hedstrom, Margaret. "Descriptive Practices for Electronic Records: Deciding What Is Essential and Imagining What Is Possible." Archivaria 36 (January 1, 1993): 53‑63.

Hjørland, Birger, and Claudio Gnoli. "Knowledge Organization." *Encyclopedia of Knowledge Organization*. Nancy, FR-GES: International Society for Knowledge Organization, 2016. [https://www.isko.org/cyclo/knowledge_organization](https://www.isko.org/cyclo/knowledge_organization).

Le Bœuf, Patrick, Martin Doerr, Christian Emil Ore, and Stephen Stead, eds. "E73 Information Object." *Definition of the CIDOC Conceptual Reference Model*. CIDOC CRM Documentations, 6.2.1. Paris, FR-IDF: International Council of Museums (ICOM), 2015. [http://www.cidoc-crm.org/sites/default/files/cidoc_crm_version_6.2.1.pdf](http://www.cidoc-crm.org/sites/default/files/cidoc_crm_version_6.2.1.pdf).

Library and Archives Canada. "Yousuf Karsh Fonds [Multiple Media]." Library and Archives Canada, 2022. [https://recherche-collection-search.bac-lac.gc.ca/eng/home/record?app=fonandcol&IdNumber=138136](https://recherche-collection-search.bac-lac.gc.ca/eng/home/record?app=fonandcol&IdNumber=138136).

Tognoli, Natália Bolfarini, and José Augusto Chaves Guimarães. "Provenance." *Encyclopedia of Knowledge Organization*. Nancy, FR-GES: International Society for Knowledge Organization, 2018. [https://www.isko.org/cyclo/provenance](https://www.isko.org/cyclo/provenance).