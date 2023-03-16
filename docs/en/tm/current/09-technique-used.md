---
layout: page
language: en
title: Technique Used
permalink: /en/target-model/current/technique-used
other_link: /fr/modele-cible/actuel/technique-utilisee
sidebar: tm22
date: 2022-03-31
description: The Actors Target Model Specification semantically models actors in a heritage context. Patterns most relevant to actors' lives are presented along with diagrams and examples illustrating them, as well as a record and explanation of relevant decisions that were made when developing said patterns. This is a theoretical documentation that has never been tested or implemented.
---

Version 2.2 ([Previous versions](/collections-model/en/versions))

## At Glance

This pattern can be used to represent the information on the technique·s employed by an actor that is·are not recorded as part of the production of a specific object. It is especially useful when a data provider does not have any object produced by the actor of interest or has a dedicated field to describe the actor by the type of technique·s they used or for which they were known. 

This pattern should not be used to represent:

* The medium of an artefact, i.e the substance or material;
* The techniques employed in the production of an artefact;
* The field of discipline in which an actor was involved;
* The occupation of an actor (see the [Occupation](/collections-model/en/target-model/current/occupation) pattern.

## Introduction and Context

### Theoretical Background

A technique is "the manner in which technical details are treated (as by a writer) or basic physical movements are used (as by a dancer)–also: ability to treat such details or use such movements (good piano technique)" (Merriam-Webster 2021a), whereas the term *technical* is defined as "marked by or characteristic of specialization" (Merriam-Webster 2021b). This definition seems to be adopted by several cultural institutions such as the Getty Research Institute (Art & Architecture Thesaurus 2021), the Museum of Modern Art (MoMA 2019), the Société des musées du Québec (SMQ 2020) and the Canadian Heritage Information Network (CHIN 1999).

In addition, depending on how the technique is defined, the use of different materials could require different skill sets. For example, in a vocabulary, the concept "wood engraving" could be defined with processes and skills different from those of "copper engraving", whereas another vocabulary could define them as the same technique (i.e. engraving) used with different materials. The definition of the term *technique* in the Art & Architecture Thesaurus confirms this inclusion of material: "The Processes and Techniques hierarchy contains terms for actions and methods performed physically on or with materials and objects [...]" (Art & Architecture Thesaurus 2019). 

### Statement of Need

In the heritage sector, there are cases where an actor is known for having used certain techniques which are recorded as metadata directly associated with the actor (e.g. in a biography) rather than with a specific artefact (i.e. techniques used in a production). For example, in Artists in Canada, *Technique* is one of the descriptive elements pertaining to an actor ("Photography" is the technique of Yousuf Karsh) (Canadian Heritage, Government of Canada 2011). 

An institution can perceive data on techniques used as a form of categorization of actors. In addition, an institution might not have objects that represent the technique·s employed by the actor; thus, not having this field would lead to missing information. For example, a museum that only has paintings of an artist in its collections can record the technique of painting through all its objects; however, this artist might have also been well-known for their sculptures. Therefore, a dedicated field would enable the museum to record the technique of sculpting even though it collects no example of the artist’s production. Such metadata should not be discarded or merged with the production of artefacts as it would be semantically inaccurate and could be hard to document if the institution does not have any object produced by the described actor. Thus, this pattern was developed by CHIN in order to independently capture the techniques of an actor in the DOPHEDA model. 

## Description of the Pattern

The [Technique Used Type](/collections-model/en/semantic-paths-specification/current/entry-nodes#technique-used-type) value is mapped as an instance of `E55_Type` linked to an instance of `E39_Actor` by the property `P2_has_type`. This instance of `E55_Type` is further qualified by an instance of `E55_Type` (a specified qualifier node) labelled "Technique Used" through the property `P2_has_type`.

## Diagram

<a name="031_Pattern_TechniqueUsed_p"></a>031_Pattern_TechniqueUsed_p

<div class="mxgraph" style="max-width:100%;border:1px solid #cccccc;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;target&quot;:&quot;blank&quot;,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom layers lightbox&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;xml&quot;:&quot;&lt;mxfile host=\&quot;app.diagrams.net\&quot; modified=\&quot;2023-03-15T17:12:28.241Z\&quot; agent=\&quot;5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) draw.io/20.3.0 Chrome/104.0.5112.114 Electron/20.1.3 Safari/537.36\&quot; etag=\&quot;5RxCKo5LY8tz6QS_-KtT\&quot; version=\&quot;20.3.0\&quot;&gt;&lt;diagram id=\&quot;9k90kyf8VMb0ZACqADbf\&quot; name=\&quot;Page-1\&quot;&gt;5VZtb5swEP41fKTiRWTdxzRN2m2dNimp2u5L5MAFuzU+akwS9utnBwNhtNGqNfsyKQq+x3d+eZ67AyecZLsrSXL6FRPgTuAlOye8dIIgcMzPS6ra9GszlSwZAHP2EyzoWbRkCRQ9R4XIFcv7YIxCQKx6GJESt323NfL+rjlJYQDMY8KH6B1LFK3R88jr8GtgKW129j07k5HG2QIFJQluD6Bw6oQTiajqUbabADe8NbzUcbNXZtuDSRDqTwKeP5y77k3+xf10e0cWafXEZtQN61U2hJf2wt+DJSXFUlU52HOrqiEDEs2NNVEqiikKwqcdeiGxFAmYHT1tdT43iLkGfQ0+glKVFZqUCjVEVcbtrL6MrO5N/FnUmA92ub1xuetZlbWGbFiCCixlDEcoaLKKyBTUET+bxoaDgw0s11eAGejzaAcJnCi26ecPsWmYtn6dUnpgxXqDcP5AuGn4cTmOFcqBbJ0ohuEtZQrmOdmTstUF2xdgzTifINfLmNhwvV4lMXmV3Q1IBbujfDRd4NzWgW0DbV1su7LyG4welNTI+3sKN/PJQ3LPftxHYlw9+tfjS/m5EfR/zv1gmPsvUuX/o9y/LUB+Wz2aRh54nKyA16FOMOL6fBcrPUjNYAExFexZCxd4OijRj8VetdpPL9u6trGyQaZRtFy0GnMmnupdqFLmrTI2pwtmMWXClTHLz1KmaLk6Y2hQ5Fwfj6Eo3Kx+0c1A6L8CMiIUi91cN/7CLXKI2ZrFxLiauFLu5THemgNXoHmtBaFqLuKW+hpul3pHqz84oN+m+nvVO1lFo+gE9R6OTlfv2jzInDe0gBe6aJsbv2eNfj6X+HLyNTPv23pPJUXknVSK7pNmP3fwTRhOfwE=&lt;/diagram&gt;&lt;/mxfile&gt;&quot;}"></div>

## Examples

In Artists in Canada, the main technique associated with Yousuf Karsh is photography (`P2_has_type`, Technique Used Type "Photography") (Canadian Heritage, Government of Canada 2011).

<div id="0001_100_technique-used" class="example"></div>

## Related Documentation

### External Model

* SARI: [Person Reference Data Model – Knowledge](https://docs.swissartresearch.net/et/persons/#knowledge)

### Entry Nodes

* [Technique Used Type](/collections-model/en/semantic-paths-specification/current/entry-nodes#technique-used-type) \| Checklist

### CIDOC CRM Entities

* `E39_Actor` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E39)]
* `E55_Type` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E55)]
* `P2_has_type (is_type_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P2)]

## Discussion

### Rationale

To capture the technique·s data directly linked to an actor, three options were considered by CHIN:

* The first is to treat the technique·s as the skill·s an actor used in the pursuit of an occupation. Each technique is modelled as an instance of `E55_Type` that is linked to the same instance of `F51_Pursuit` by the property `P32_used_general_technique`, and this instance of `F51_Pursuit` is carried out by the actor. However, this path asserts that the actor pursued an occupation that was not originally assigned by the provider. In addition to inaccurate information, the addition of these unnecessary nodes would lead to more complicated and cumbersome querying.
* The second option is to model each technique as an instance of `E55_Type` that is directly linked to an instance of `E39_Actor` by a new property that could be labelled "Composed of knowledge" or "Have skill". However, this implies the creation of a new property, a process that should be avoided for the reasons detailed in the [Prioritization of `E55_Type` and `P2_has_type` over New Classes and Properties](/collections-model/en/target-model/current/general-concepts#prioritization-of-e55_type-and-p2_has_type-over-new-classes-and-properties) section. 
* The last and selected option, similar to the second one above, is to model each technique as an instance of `E55_Type` that is directly linked to an instance of `E39_Actor` using the property `P2_has_type` rather than creating a new property. The property `P2_has_type` appears to be semantically inaccurate as it implies that an actor is of a type, for instance, "Oil painting". However, the CRM SIG considers this practice acceptable when it comes to languages spoken by actors (see [CRM SIG's Issue #429](http://www.cidoc-crm.org/Issue/ID-429-p72-has-language). Moreover, the categorization of an actor appears useful as it provides information on how the actor is perceived by different institutions.

### Limitations

As mentioned in the Rationale, this pattern is still not semantically ideal. Two alternatives are currently being developed and could eventually be leveraged: <a href="https://github.com/linked-art/linked.art/issues/237#issuecomment-611035443">Linked.art’s E13_Attribute_Assignment relationship strategy</a> or <a href="http://www.cidoc-crm.org/crmsoc/sites/default/files/CRMsoc_20190326.pdf">CRMsoc’s Phase class</a>. 

In addition, because the Technique Used Type entry node is linked directly to the actor, there is still question over its "correct" vocabulary (see [Issue #76](https://github.com/chin-rcip/collections-model/issues/76)).

### Related GitHub Issues

* [Issue #1 "Techniques vs Occupations"](https://github.com/chin-rcip/collections-model/issues/1)
* [Issue #74 "Is it necessary to add an E13_Attribute_Assignment in the technique used pattern?"](https://github.com/chin-rcip/collections-model/issues/74)
* [Issue #76 "What vocabulary terms should be used to distinguish the different techniques and occupations documented?"](https://github.com/chin-rcip/collections-model/issues/76)

### Edge Cases

Yousuf Karsh was known in particular for his portraits. As mentioned in the Theoretical Background, depending on the classification chosen, a vocabulary could define portrait photography as a technique, like the AAT with "Commercial portraiture" (AAT 2019), or simply stop at "Photography" without any child terms. The latter implies that producing a portrait does not require different skills than producing any type of photograph. In this case, the techniques can be specified through the description of artefacts, and the information concerning the portrait can be managed via the subjects of the photograph produced by Yousuf Karsh or the description of its composition.

## Bibliography

Art & Architecture Thesaurus. "Processes and Techniques." *Art & Architecture Thesaurus Online Full Record Display*. September 25, 2019. [http://www.getty.edu/vow/AATFullDisplay?find=technique&logic=AND&note=&page=1&subjectid=300053001](http://www.getty.edu/vow/AATFullDisplay?find=technique&logic=AND&note=&page=1&subjectid=300053001).

Art & Architecture Thesaurus. "Technique (Concept)." *Art & Architecture Thesaurus Online Full Record Display*. September 13, 2021. http://www.getty.edu/vow/AATFullDisplay?find=%22technique%22&logic=AND&note=&english=N&prev_page=1&subjectid=300055843.

Bekiari, Chryssoula, George Bruseker, Martin Doerr, Christian-Emil Ore, Stephen Stead, and Athanasios Velios, eds. *Definition of the CIDOC Conceptual Reference Model*. CIDOC CRM Documentations, 7.1. Paris, FR-IDF: CIDOC CRM Special Interest Group, 2021. [http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf](http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf).

Canadian Heritage, Government of Canada. "Karsh, Yousuf." *Artists in Canada*. Ottawa, CA-ON: Government of Canada, 2011. [https://app.pch.gc.ca/application/aac-aic/artiste_detailler_bas-artist_detail_bas.app?lang=en&rID=8494](https://app.pch.gc.ca/application/aac-aic/artiste_detailler_bas-artist_detail_bas.app?lang=en&rID=8494).

Canadian Heritage Information Network (CHIN). "CHIN Data Dictionaries." *CHIN Data Dictionary*. February 9, 1999. [https://app.pch.gc.ca/application/ddrcip-chindd/field_detailler_rechercher-search_field_detail.app?rID=1032&dd=sh-hs&ac=false&rac=false&lang=en&qlang=en&sub=technique&mne=&pID=1](https://app.pch.gc.ca/application/ddrcip-chindd/field_detailler_rechercher-search_field_detail.app?rID=1032&dd=sh-hs&ac=false&rac=false&lang=en&qlang=en&sub=technique&mne=&pID=1).

CIDOC CRM Special Interest Group. "Issue 429: P72 Has Language." *CIDOC CRM*. 2019. [http://www.cidoc-crm.org/Issue/ID-429-p72-has-language](http://www.cidoc-crm.org/Issue/ID-429-p72-has-language).

Merriam-Webster. "Technical." *Merriam-Webster.com Dictionary*. Springfield, US-MA: Merriam-Webster, 2021a. [https://www.merriam-webster.com/dictionary/technical](https://www.merriam-webster.com/dictionary/technical).

Merriam-Webster. "Technique." *Merriam-Webster.com Dictionary*. Springfield, US-MA: Merriam-Webster, 2021b. [https://www.merriam-webster.com/dictionary/technique](https://www.merriam-webster.com/dictionary/technique).

Museum of Modern Art. "Technique." *Museum of Modern Art Glossary of Art Terms*. September 25, 2019. [https://www.moma.org/learn/moma_learning/glossary/#t](https://www.moma.org/learn/moma_learning/glossary/#t).

Société des musées du Québec. "Technique de Fabrication (Description Physique)." *Guide de documentation du Réseau Info-Muse*. December 9, 2020. [https://www.musees.qc.ca/fr/professionnel/guidesel/doccoll/fr/ethno-art-techno/tf.htm](https://www.musees.qc.ca/fr/professionnel/guidesel/doccoll/fr/ethno-art-techno/tf.htm).

