---
layout: page
language: en
title: Biography
permalink: /en/target-model/current/biography
other_link: /fr/modele-cible/actuel/biographie
sidebar: tm22
date: 2022-03-31
description: The Actors Target Model Specification semantically models actors in a heritage context. Patterns most relevant to actors' lives are presented along with diagrams and examples illustrating them, as well as a record and explanation of relevant decisions that were made when developing said patterns. This is a theoretical documentation that has never been tested or implemented.
---

Version 2.2 ([Previous versions](/collections-model/en/versions))

## At Glance

This pattern can be used to represent the textual information pertaining to the biography of an actor (person or group of persons). It includes:

* The text of a biography;
* The language in which the text of a biography is written;
* The sources and references that have been used to write the text of a biography.

This pattern does not contain:

* The tabular data represented elsewhere in the model; 
* The person or group of persons responsible for the creation of the text; only the documentation of the provenance of a whole dataset is modelled with the [Dataset Provenance](/collections-model/en/target-model/current/dataset-provenance) pattern;
* The curatorial notes about the actor, which should be documented using the [Curatorial Note](/collections-model/en/target-model/current/curatorial-note) pattern. 

## Introduction and Context

### Theoretical Background

Biographies typically portray the life of a human being using literal text, a practice that can be traced back to Antiquity with Plutarch’s *Parallel Lives* (Kendall 2019; Viala 2021). Unlike heritage research that focuses on periods of time or groups, biographies are concerned with the life of particular individuals which themselves can be contextualized through a period or group description.

### Statement of Need

Written biographies are an important part of research and documentation and are routinely employed by historians and sociologists to put the life of individuals and groups in chronological, geographical, or sociological context (Levallois 2002). This in part depends on the recording of the authorship of the sources, primary or original, used in the recording process (sources that pertain to the biographical information itself, and not to the dataset in general; for the latter, refer to the [Dataset Provenance](/collections-model/en/target-model/current/dataset-provenance) pattern).

Even if the development of complex biographical queries relies on structured, linked, and semantic data, a literal text field to accommodate lengthy natural language texts is also required as it answers the immediate needs of data providers who rely mostly on texts to precisely and originally document the lives of actors. In addition, this literal text field could eventually be analyzed using natural language processing tools in order to generate structured and semantic data based on its contents. 

## Description of the Pattern

Similarly to other textual information (see the [Literal Content](/collections-model/en/target-model/current/general-concepts#literal-content) section), the content of a biography is modelled as an instance of `E33_Linguistic_Object` linked to the literal value of the [Biography Content](/collections-model/en/semantic-paths-specification/current/entry-nodes#biography-content) through the property `P190_has_symbolic_content`. This instance of `E33_Linguistic_Object` is also linked to the actor depicted in the biography (an instance of `E39_Actor`) by the property `P67_refers_to`.

The simplest way to render the sources and bibliographical mentions used in the creation of a biography is to rely on the [Dublin Core](https://www.dublincore.org/specifications/dublin-core/dcmi-terms/) property `dct:source` linking the instance of `E33_Linguistic_Object` to the literal value of the [Biography Bibliographical Mention](/collections-model/en/semantic-paths-specification/current/entry-nodes#biography-bibliographical-mention). In addition, from the same instance of `E33_Linguistic_Object`, the [Biography Language](/collections-model/en/semantic-paths-specification/current/entry-nodes#biography-language) value (an instance of `E56_Language`) is rendered by the property `P72_has_language`.

## Diagram

<a name="061_Pattern_Biography_p"></a>061_Pattern_Biography_p

<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=061_Pattern_Biography_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D19wQ_jNhyQGHPGh6I-AULj9RGTreuLIoL%26export%3Ddownload"></iframe>

## Examples

### Example 1

The english-language (`P72_has_language`, Biography Language) biography of Yousuf Karsh on Wikipedia (Wikipedia 2021) is as follows:

"Yousuf Karsh CC (December 23, 1908 – July 13, 2002) was an Armenian-Canadian photographer known for his portraits of notable individuals. He has been described as one of the greatest portrait photographers of the 20th century.

An Armenian genocide survivor, Karsh migrated to Canada as a refugee. By the 1930s he established himself as a significant photographer in Ottawa, where he lived most of his adult life, though he travelled extensively for work. His iconic 1941 photograph of Winston Churchill was a breakthrough point in his 60-year career, through which he took numerous photos of known political leaders, men and women of arts and sciences. Over 20 photos by Karsh appeared on the cover of *Life* magazine, until he retired in 1992." (`P190_has_symbolic_content`, Biography Content).

It quotes the following works:

* Berman, Eliza. "Yousuf Karsh's Masterful Portraits From Churchill to Hepburn." *Time*. March 18, 2015 (`dct:source`, Biography Bibliographical Mention);
* Thurber, Jon. "Yousuf Karsh, 93; Photographs Captured Face of 20th Century." *Los Angeles Times*. July 14, 2002 (`dct:source`, Biography Bibliographical Mention).

<div id="0001_100_biography" class="example"></div>

### Example 2

The english-language (`P72_has_language`, Biography Language) biography of the Canadian Group of Painters by the Art Canada Institute (Art Canada Institute n.d.) is as follows:

"Founded in 1933 after the disbanding of the Group of Seven by former members and their associates, the Canadian Group of Painters championed modernist painting styles against the entrenched traditionalism of the Royal Canadian Academy of Arts. It provided a platform for artists across Canada who were pursuing a variety of new concerns, from the formal experimentation of Bertram Brooker to the modern-figure subjects of Prudence Heward and Pegi Nicol MacLeod and the expressive landscapes of Emily Carr." (`P190_has_symbolic_content`, Biography Content).

No works are cited as the source of the text.

<div id="0001_112_biography" class="example"></div>

## Related Documentation

### External Models

* SARI: [Information Carrier Reference Data Model – Description](https://docs.swissartresearch.net/et/carrier/#description)

### Entry Nodes

* [Biography Bibliographical Mention](/collections-model/en/semantic-paths-specification/current/entry-nodes#biography-bibliographical-mention) \| Checklist
* [Biography Content](/collections-model/en/semantic-paths-specification/current/entry-nodes#biography-content) \| Checklist
* [Biography Language](/collections-model/en/semantic-paths-specification/current/entry-nodes#biography-language) \| Checklist

### CIDOC CRM Entities

* `dct:source`
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

For the sake of simplicity, the Dublin Core ontology is used to document bibliographical mentions since it is the most in use by heritage libraries and archives when it comes to this purpose. The property `dct:source` linked to the descriptive string seems sufficient in this case. At the moment, authorship is by default ascribed to the dataset provider rather than to a person, as opposed to sources which are recorded. 

The distinction between a curatorial note concerning an actor and a biography can be difficult to assess. If a textual description solely contains accounts of the life of an actor, it should be modelled using the Biography pattern; if it contains other kinds of information, it should be modelled using the Curatorial Note pattern.

### Limitations

Because it relies on textual descriptions in the form of strings, the biography field contains a lot of unstructured information that can nonetheless, and even for this very reason, be particularly detailed. Thus, it is necessary to account for elements in the life of actors that could not be documented in structured and dedicated fields. However, such contents are difficult to query due to an inability to identify their nature without reading and understanding them which only human users or powerful artificial intelligence software can do. 

While the life of objects or other non-actor entities is of great interest, it has not been modelled in the Target Model Specification due to the limited scope of the project.

The class `E33_Linguistic_Object` includes written text in its scope note, but also recorded speech and sign language (Bekiari et al. 2021). However, the DOPHEDA model currently only accommodates textual contents for biographies, as there is no pattern to document any other kind of linguistic object (e.g. oral documentation or multimedia accounts). As a result, some testimonies (e.g. audio recordings or videos) cannot be documented.

### Edge Cases

#### Example 1 {#edge-cases-example-1}

A group’s biography could be categorized either as a Curatorial Note Content or as a Biography Content. In addition, a provider could decide to use a bibliography manager and link the bibliographical mention to the manager’s entry instead of copying it.

#### Example 2 {#edge-cases-example-2}

Bilingual considerations could apply to Biography Content so that it would either be two Biography Content nodes with the corresponding Language node for each, or one Biography Content node with two Language nodes.

#### Example 3 {#edge-cases-example-3}

Some text can be written in a specific dialect of a language (e.g. French-Canadian can be considered as a French dialect). Both languages and dialects are valid values, and the choice between documenting either of both depends on the vocabulary that is used by the institution.

## Bibliography

Art Canada Institute. "Glossary of Canadian Art History." Art Canada Institute. October 13, 2021. [https://www.aci-iac.ca/glossary/C/](https://www.aci-iac.ca/glossary/C/).

Bekiari, Chryssoula, George Bruseker, Martin Doerr, Christian-Emil Ore, Stephen Stead, and Athanasios Velios, eds. *Definition of the CIDOC Conceptual Reference Model*. CIDOC CRM Documentations, 7.1. Paris, FR-IDF: CIDOC CRM Special Interest Group, 2021. [http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf](http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf).

Kendall, Paul Murray. "Biography." *Encyclopædia Britannica*. London, UK-LDN: Encyclopædia Britannica, 2019. [https://www.britannica.com/art/biography-narrative-genre](https://www.britannica.com/art/biography-narrative-genre).

Levallois, Anne. "Le retour de la biographie historique. L’histoire et la psychanalyse s’y rejoindraient-elles?" *L’Homme & la Société* 146, no. 4 (2002): 127-140. [https://doi.org/10.3917/lhs.146.0127](https://doi.org/10.3917/lhs.146.0127).

National Women’s History Museum. *Biographies*. National Women’s History Museum. September 8, 2021. [https://www.womenshistory.org/students-and-educators/biographies](https://www.womenshistory.org/students-and-educators/biographies).

Viala, Alain. "Biographie." *Encyclopædia Universalis*, *Encyclopædia Britannica*. London, UK-LDN: Encyclopædia Britannica, 2021. [https://www.universalis.fr/encyclopedie/biographie/](https://www.universalis.fr/encyclopedie/biographie/).

Wikipedia. "Yousuf Karsh." *Wikipedia*. San Francisco, US-CA: Wikipedia, 2021. [https://fr.wikipedia.org/wiki/Yousuf_Karsh](https://fr.wikipedia.org/wiki/Yousuf_Karsh).

