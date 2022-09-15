---
layout: page
language: en
title: Messy Data
permalink: /en/target-model/current/messy-data
other_link: /fr/modele-cible/actuel/donnees-desordonnees
sidebar: tm22
date: 2022-03-31
description: The Actors Target Model Specification semantically models actors in a heritage context. Patterns most relevant to actors' lives are presented along with diagrams and examples illustrating them, as well as a record and explanation of relevant decisions that were made when developing said patterns. This is a theoretical documentation that has never been tested or implemented.
---

Version 2.2 ([Previous versions](/collections-model/en/versions))

## At Glance

This pattern has been developed to facilitate the mapping of data that does not follow DOPHEDA’s recommendations. It is a technical solution to accommodate—in a knowledge graph—unstructured data. This pattern covers:

* The data itself, in literal form;
* The language in which the data is recorded.

It does not cover:

* The provenance of the data, which is documented using the [Dataset Provenance](/collections-model/en/target-model/current/dataset-provenance) pattern;
* The semantic valuation of the data;
* The notes or comments containing textual information about an entity, which are documented using the [Curatorial Note](/collections-model/en/target-model/current/curatorial-note) pattern;
* Data fields that do not correspond to any pattern of the Target Model Specification.

## Introduction and Context

### Theoretical Background

Messy data is a significant issue faced by heritage institutions. A report of the Heritage Data Research Workshop shows that a major concern of heritage data experts is tackling complex and messy data, either because of a multitude of formats or of a lack of standardization (Harrison et al. 2017, 32). Although it is hard to quantify the proportion of messy data in heritage digital collections, a survey on the database of the Dutch National Museum of Natural History shows that it contains around 5% of spelling and wrong-column errors, and about 34% of content errors (van den Bosch et al. 2009, 55-56). However, the ongoing cleaning of entire datasets is impractical for most institutions, as it is a long and resource intensive process (CrowdFlower 2016, 6). Thus, it is reasonable to believe that other institutions face similar challenges and that messy data must be accounted for and accommodated. 

### Statement of Need

Even if the provision of data should follow strict structure and standardization rules to ensure the seamless transformation of providers’ datasets into RDF format, the resource-intensive data cleaning exercise this involves is often an unrealistic expectation. This results in unstructured—often called messy—data that must be accommodated, even at the expense of semantics. This enables users to access the entirety of information provided by an institution, as well as future tools to parse and clean messy data. Even if it would facilitate the mapping process, discarding messy data from the DOPHEDA knowledge graph would lead to a significant loss of relevant information that is undesirable; this is why this pattern has been developed. 

## Description of the Pattern

A standard solution to process messy data in knowledge graphs is to consider such data as strings which amounts to the creation of an instance of `E33_Linguistic_Object`. The [Messy Data Statement Type](/collections-model/en/semantic-paths-specification/current/entry-nodes#messy-data-statement-type) value (an instance of `E55_Type`) is linked to that instance of `E33_Linguistic_Object` by the property `P2_has_type` in order to indicate the general kind of information held by the instance of `E33_Linguistic_Object` based on the entry node that would have accommodated the data had its semantic value been higher, as well as to distinguish it from other instances of `E33_Linguistic_Object`, such as biographies. The instance of `E55_Type` is then qualified by another instance of `E55_Type` (a specified qualifier node) labelled "Messy Data Statement" through the property `P2_has_type`.

The [Messy Data Statement Language](/collections-model/en/semantic-paths-specification/current/entry-nodes#messy-data-statement-language) value (an instance of `E56_Language`) is linked to the instance of `E33_Linguistic_Object` by the property `P72_has_language`, and the literal value of the [Messy Data Statement Content](/collections-model/en/semantic-paths-specification/current/entry-nodes#messy-data-statement-content) is connected to that same instance of `E33_Linguistic_Object` through the property `P190_has_symbolic_content`. The instance of `E33_Linguistic_Object` representing the literal data is finally linked through the property `P67_refers_to` to the concerned instance of `E39_Actor`.

## Diagram

<a name="011_Pattern_MessyData_p"></a>011_Pattern_MessyData_p

<iframe frameborder="0" style="width:100%;height:400px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=011_Pattern_MessyData_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1wMPUk3zYiEvdb5Ez6KP_HmxpPf8fGNFZ%26export%3Ddownload"></iframe>

## Examples

Information detailing the beginning of Yousuf Karsh's occupation as an established studio photographer could take the following form: "Returning to Canada in 1931, Karsh soon established a studio with financial help from his uncle" (Editors of Encyclopædia Britannica n.d.)" (`P190_has_symbolic_content`, Messy Data Statement Content). Had the data been standardized, it could have been submitted using the Occupation Date Begin entry node, but because the data is not standard, the Messy Data Statement Content entry node must be used instead, with a label indicating it is an "Occupation Date Begin Statement" (`P2_has_type`, Messy Data Statement Type) written in English (`P72_has_language`, Messy Data Statement Language).

<div id="0001_100_messy-data" class="example"></div>

## Related Documentation

### External Models

* Linked.art: [Statements about a Resource](https://linked.art/model/base/#statements-about-a-resource)

### Entry Nodes

* [Messy Data Statement Content](/collections-model/en/semantic-paths-specification/current/entry-nodes#messy-data-statement-content) \| Checklist
* [Messy Data Statement Language](/collections-model/en/semantic-paths-specification/current/entry-nodes#messy-data-statement-language) \| Checklist
* [Messy Data Statement Type](/collections-model/en/semantic-paths-specification/current/entry-nodes#messy-data-statement-type) \| Checklist

### CIDOC CRM Entities

* `E33_Linguistic_Object` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E33)]
* `E39_Actor` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E39)]
* `E55_Type` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E55)]
* `E56_Language` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E56)]
* `P2_has_type (is_type_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P2)]
* `P67_refers_to (is_referred_to_by)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P67)]
* `P72_has_language (is_language_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P72)]
* `P190_has_symbolic_content` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P190)]

## Discussion

### Rationale

This pattern is not designed to document a specific kind of information, unlike most of the Target Model Specification. Rather, it is a technical solution to the problem of unstructured and non-standard data. Most LOD projects focus on the development of a data model rather than on its implementation; this is why this pattern is often not encountered in other projects. Yet, it is essential for an environment like DOPHEDA that aims to aggregate and map the data of numerous providers. Realistically, not all providers will have the resources to clean their data before contributing to the DOPHEDA environment, and CHIN must accommodate the needs of its various stakeholders. 

This pattern is structurally similar to the [Curatorial Note](/collections-model/en/target-model/current/curatorial-note) pattern. Both have as a central node an instance of `E33_Linguistic_Object` that is linked to the node it documents through the property `P67_refers_to`. Messy data and curatorial notes can, nevertheless, be differentiated from each other via the use of an appropriate designated type. Both `E55_Type` nodes, called [specified qualifier nodes](/collections-model/en/semantic-paths-specification/current/introduction#specified-qualifier-node-sqn), rely on the use of specific vocabularies that have yet to be determined. 

### Limitations

As stated above, because of its nature, the messy data accommodated in the DOPHEDA knowledge graph remains semantically poor. Even if messy data is available in the DOPHEDA environment, extracting information from it through queries is difficult. Only humans reading the content of textual nodes can ascertain the meaning of such data. This can be a lengthy process because of its sheer amount. Until tools can clean messy data, it will remain difficult to access and hard to exploit.

In order to use the mapping of information, the Messy Data pattern has to be linked to the root entity (the instance of `E39_Actor` or `E22_Human-Made_Object`). However, the Messy Data Statement might not refer directly to the actor but to another entry node, such as the Family Joining Date Begin. This could create confusion for the user, either by not knowing to which node the messy data statement refers to, or by thinking that only information pertaining to the main actor can be modelled with the Messy Data pattern.

### Related GitHub Issues

* [Issue #20 "What to do with the “Remarks” field in some museums?"](https://github.com/chin-rcip/collections-model/issues/20)
* [Issue #32 "Should we use `P3 has note` or `rdfs:comment`?"](https://github.com/chin-rcip/collections-model/issues/32)
* [Issue #63 "Curatorial Note Topic"](https://github.com/chin-rcip/collections-model/issues/63)

### Edge Cases

#### Example 1 {#edge-cases-example-1}

Yousuf Karsh has used the "Photography" technique throughout his career. An institution that documents this technique using a controlled vocabulary will be able to account for this information according to the Technique Used pattern. However, despite the fact that the information transmitted is structured, the provider could be reluctant to categorize a person based on the techniques they used. In such a case, the Messy Data pattern could be used to accommodate the provider's point of view. 

#### Example 2 {#edge-cases-example-2}

A single Messy Data Statement Content could include more than a single language. In such a case, a provider could choose to list languages in a single entry, or create an entry per language and associate all of these to the content.

## Bibliography

CrowdFlower. *Data Science Report*. CrowdFlower, 2016. [https://visit.figure-eight.com/rs/416-ZBE-142/images/CrowdFlower_DataScienceReport_2016.pdf](https://visit.figure-eight.com/rs/416-ZBE-142/images/CrowdFlower_DataScienceReport_2016.pdf).

Editors of Encyclopaedia Britannica. "Yousuf Karsh." *Encyclopædia Britannica*. London, UK-LDN: Encyclopædia Britannica, n.d. [https://www.britannica.com/biography/Yousuf-Karsh](https://www.britannica.com/biography/Yousuf-Karsh).

Harrison, Rodney, Hana Morel, Maja Mericevic, and Sefryn Penrose. *Heritage and Data: Challenges and Opportunities for the Heritage Sector*. Heritage Data Research Workshop. London, UK-LDN: Arts and Humanities Research Council, 2017. [https://heritage-research.org/app/uploads/2017/11/Heritage-Data-Challenges-Opportunities-Report.pdf](https://heritage-research.org/app/uploads/2017/11/Heritage-Data-Challenges-Opportunities-Report.pdf).

Van den Bosch, Antal, Marieke van Erp, and Caroline Sporleder. "Making a Clean Sweep of Cultural Heritage." *Intelligent Systems, IEEE* 24, no. 2 (2009): 54-63.

