---
layout: page
language: en
title: Artefact
permalink: /en/target-model/current/artefact
other_link: /fr/modele-cible/actuel/artefact
sidebar: tm22
date: 2022-03-31
description: The Actors Target Model Specification semantically models actors in a heritage context. Patterns most relevant to actors' lives are presented along with diagrams and examples illustrating them, as well as a record and explanation of relevant decisions that were made when developing said patterns. This is a theoretical documentation that has never been tested or implemented.
---

Version 2.2 ([Previous versions](/collections-model/en/versions))

## At Glance

This pattern can be used to minimally identify a tangible artefact. It includes: 

* The main identification numbers of an artefact (e.g. accession number, database specific number, etc.);
* The appellation of an artefact.

Even though this pattern can be linked to the [Artefact Production](/collections-model/en/target-model/current/artefact-production) pattern in order to account for further information involving actors, it does not include: 

* Intangible artefacts;
* The maker·s of an artefact (use the [Artefact Production](/collections-model/en/target-model/current/artefact-production) pattern instead); 
* The creation or production dates and places (use the [Artefact Production](/collections-model/en/target-model/current/artefact-production) pattern instead). 

The information pertaining to artefacts themselves, as well as to their collecting, researching, handling, and preserving is currently not accounted for in this pattern. Minimal information necessary to identify rather than describe artefacts has been prioritized. Similarly, only tangible artefacts are modelled in this pattern. 

In addition, it is important to point out that the [Visual Item](/collections-model/en/target-model/current/visual-item) pattern cannot be used to refer to artefacts or to their reproductions because it exclusively accommodates actors' representations for the moment. 

## Introduction and Context

### Theoretical Background

Fundamentally, heritage producing, researching, and collecting is a form of human-object relation that is increasingly understood beyond the status of the human as the producer of meaning and the object as an illustrative production (Macdonald 2011, 93). Rather, artefacts are more and more considered as spaces of interrelated meanings with value (Bann 2003, 120). As such, the understanding of what qualifies as an artefact has greatly evolved in the past twenty years to include intangible cultural heritage as well as material objects. Because the relationship between human and artefacts is meaningful to the heritage sector, it is the subject of a multiplicity of researches and practices, especially in the case of intangible heritage which is often embodied in human and living ways (Đerić, Neyrinck, & Seghers 2020, 11).

### Statement of Need

In the context of the current DOPHEDA model, artefacts are understood to encompass material objects, which are often the central unit of heritage database records. For such purposes, a number of core informations are typically used across disciplines. An assessment of what they are has been done by the J. Paul Getty Trust when establishing the Object ID, an international standard for cultural goods intended to prevent the illicit trade of artefacts worldwide (ICOM 2021). These standard identificatory fields are the: 

* Type of object;
* Materials and techniques;
* Measurement;
* Inscriptions and markings;
* Distinguishing features;
* Title;
* Subject;
* Date or period;
* Maker. 

Because the sole function of the Artefact pattern is to account for objects as the core unit of recording in heritage collections, not all of these elements are addressed in the model; only titles and identifiers are taken into consideration. The maker’s role and the date or period are addressed in the [Artefact Production](/collections-model/en/target-model/current/artefact-production) pattern. 

## Description of the Pattern

There are two main ensembles to this pattern: the identifiers of the artefact and its title. Both relate directly to an instance of `E22_Human-Made_Object` which is the central unit of this pattern and encapsulates the artefact. 

The information pertaining to the identifiers is concentrated around an instance of `E42_Identifier` which is linked to the instance of `E22_Human-Made_Object` through the property `P1_is_identified_by`. This instance of `E42_Identifier` is linked to the literal value of the [Artefact ID](/collections-model/en/semantic-paths-specification/current/entry-nodes#artefact-id) through the property `P190_has_symbolic_content` as well as to the [Artefact ID Type](/collections-model/en/semantic-paths-specification/current/entry-nodes#artefact-id-type) value through the property `P2_has_type`.

The information pertaining to the appellation of the artefact is rendered with the same logic as the [Actor Identifiers and Appellations](/collections-model/en/target-model/current/actor-identifiers-and-appellations) pattern. An instance of both `E41_Appellation` and `E33_Linguistic_Object` is linked to:

* The literal value of the [Artefact Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#artefact-appellation) by the property `P190_has_symbolic_content`;
* The [Artefact Appellation Language](/collections-model/en/semantic-paths-specification/current/entry-nodes#artefact-appellation-language) value (an instance of `E56_Language`) by the property `P72_has_language`;
* The [Artefact Appellation Type](/collections-model/en/semantic-paths-specification/current/entry-nodes#artefact-appellation-type) value (an instance of `E55_Type`) by the property `P2_has_type` which is qualified by an instance of `E55_Type` (a specified qualifier node) labelled "Type of Appellation" through the property `P2_has_type`;
* The [Artefact Appellation Precedence](/collections-model/en/semantic-paths-specification/current/entry-nodes#artefact-appellation-precedence) value (an instance of `E55_Type`) by the property `P2_has_type` which is qualified by an instance of `E55_Type` (a specified qualifier node) labelled "Precedence" through the property `P2_has_type`.

The instance of both `E41_Appellation` and `E33_Linguistic_Object` is also linked to the instance of `E22_Human-Made_Object` by the property `P1_is_identified_by`. 

## Diagram

<a name="072_Pattern_Artefact_p"></a>072_Pattern_Artefact_p

<div class="mxgraph" style="max-width:100%;border:1px solid #cccccc;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;target&quot;:&quot;blank&quot;,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom layers lightbox&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;xml&quot;:&quot;&lt;mxfile modified=\&quot;2023-03-15T17:12:31.574Z\&quot; host=\&quot;app.diagrams.net\&quot; agent=\&quot;5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) draw.io/20.3.0 Chrome/104.0.5112.114 Electron/20.1.3 Safari/537.36\&quot; etag=\&quot;UvAuHbsVk5RzEVSERrbH\&quot; version=\&quot;20.3.0\&quot;&gt;&lt;diagram id=\&quot;2xT8YsmRYOj1Pd-nPkiT\&quot; name=\&quot;Page-1\&quot;&gt;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&lt;/diagram&gt;&lt;/mxfile&gt;&quot;}"></div>

## Examples

### Example 1

Yousuf Karsh’s [*Self-Portrait*](https://upload.wikimedia.org/wikipedia/commons/3/3a/Yousuf-Karsh.jpg) (`P190_has_symbolic_content`, Artefact Appellation) is titled (`P2_has_type`, Artefact Appellation Type "Title") in English (`P72_has_language`, Artefact Appellation Language) and this title is the main one used to refer to the artefact (`P2_has_type`, Artefact Appellation Precedence "Preferred"). It is also sometimes titled *Self Portret* (`P190_has_symbolic_content`, Artefact Appellation; `P2_has_type`, Artefact Appellation Type "Title"), but this appellation is not preferred (`P2_has_type`, Artefact Appellation Precedence "Non-Preferred"). The reproduction’s Library and Archives Canada identification number (`P2_has_type`, Artefact ID Type "Identification Number") is PA-212511 (`P190_has_symbolic_content`, Artefact ID "PA-212511") (Karsh 1938). 

<div id="0001_500_artefact" class="example"></div>

### Example 2

[*Flightstop*](https://commons.wikimedia.org/wiki/File:Flight_stop.jpg) (`P190_has_symbolic_content`, Artefact Appellation; `P72_has_language`, Artefact Appellation Language "English"; `P2_has_type`, Artefact Appellation Type "Title"; `P2_has_type`, Artefact Appellation Precedence "Preferred") is a sculpture by artist Michael Snow, sometimes titled *Flight Stop* (`P190_has_symbolic_content`, Artefact Appellation; `P72_has_language`, Artefact Appellation Language "English"; `P2_has_type`, Artefact Appellation Type "Title"; `P2_has_type`, Artefact Appellation Precedence "Non-Preferred") (Law 2011; Snow 1979; Wikipedia 2021).

<div id="0001_501_artefact" class="example"></div>

### Example 3

John William Waterhouse’s [*"I am half sick of shadows, said The Lady of Shalott" (Alfred, Lord Tennyson, The Lady of Shalott, Part II)*](https://en.wikipedia.org/wiki/File:John_William_Waterhouse_-_I_am_half-sick_of_shadows,_said_the_lady_of_shalott.JPG) is a 1915 painting in the Art Gallery of Ontario’s collection with the object number 71/18 (`P190_has_symbolic_content`, Artefact ID) assigned by the cataloguer (`P2_has_type`, Artefact ID Type "AGO_ID") (Waterhouse 1915; Wikipedia 2018). 

<div id="0001_502_artefact" class="example"></div>

## Related Documentation

### External Models

* Linked.art: [Object Names and Identifiers](https://linked.art/model/base/)
* SARI: [Artwork Reference Data Model – Names and Classifications](https://docs.swissartresearch.net/et/artwork/#names-and-classifications)

### Entry Nodes

* [Artefact Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#artefact-appellation) \| Checklist
* [Artefact Appellation Language](/collections-model/en/semantic-paths-specification/current/entry-nodes#artefact-appellation-language) \| Checklist
* [Artefact Appellation Precedence](/collections-model/en/semantic-paths-specification/current/entry-nodes#artefact-appellation-precedence) \| Checklist
* [Artefact Appellation Type](/collections-model/en/semantic-paths-specification/current/entry-nodes#artefact-appellation-type) \| Checklist
* [Artefact ID](/collections-model/en/semantic-paths-specification/current/entry-nodes#artefact-id) \| Checklist
* [Artefact ID Type](/collections-model/en/semantic-paths-specification/current/entry-nodes#artefact-id-type) \| Checklist

### CIDOC CRM Entities

* `E22_Human-Made_Object` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E22)]
* `E33_Linguistic_Object`[[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E33)]
* `E41_Appellation` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E41)]
* `E42_Identifier` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E42)]
* `E55_Type` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E55)]
* `E56_Language` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E56)]
* `P1_is_identified_by (identifies)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P1)]
* `P2_has_type (is_type_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P2)]
* `P72_has_language (is_language_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P72)]
* `P190_has_symbolic_content` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P190)]

## Discussion

### Rationale

Most heritage databases center their record around a collected object rather than its producer. For functional implementation purposes, it is thus necessary to create a pattern that enables the identification of the artefact. The sole purpose of the Artefact pattern is to account for objects as the core unit of recording in heritage collections.

In addition, because most institutions at the moment focus on tangible objects rather than intangible artefacts as the central units of their records, this pattern only offers the possibility to document physical objects. This explains the use of the class `E22_Human-Made_Object` which is intended to be used for physical products rather than living practices. 

### Limitations

This is only intended to minimally identify artefacts without describing them and is lacking in everything having to do with the object itself (see [Issue #71](https://github.com/chin-rcip/collections-model/issues/71)). 

### Related GitHub Issues

* [Issue #69 "Records for the Object Facet"](https://github.com/chin-rcip/collections-model/issues/69)
* [Issue #71 "Fields and concepts to model for the Object Facet"](https://github.com/chin-rcip/collections-model/issues/71)

### Edge Cases

#### Example 1 {#edge-cases-example-1}

Marie-Guillemine Benoist’s *Portrait of Madeleine* was formerly titled using a racial description. Recent scholarship has established the sitter’s name as "Madeleine", although her last name remains unknown. Curatorial notes or annotations could be placed on the artefact appellation:

* "Portrait of Madeleine" as the preferred appellation and "Former title displaying insensitive racial language" as the curatorial note;
* The former title as the non-preferred appellation and "Now titled Portrait of Madeleine" as the curatorial note;
* The former title as the non-preferred appellation and "Former title displaying insensitive racial language" as the annotation.

A curatorial note might also be used on the actor appellation "Madeleine" or the actor ("Sitter in Portrait of Madeleine, former title displaying insensitive racial language with the sitter identified as being named "Madeleine" by Viktoria Schmidt-Linsenhoff"). There are a number of works in Canadian collections that have offensive or otherwise insensitive titles fraught with racist and/or colonialist terminology (Schmidt-Linsenhoff 2013; Waller 2018). 

#### Example 2 {#edge-cases-example-2}

Institutions categorize objects differently. For example, on the one hand, the Tom Thomson Memorial Art Gallery records Don Phillips’ *Triptych* as three objects in [Artefacts Canada](https://app.pch.gc.ca/application/artefacts_hum/indice_index.app?lang=fr):

* Artefact Appellation: *Triptych (1978) (left panel)*
  * Artefact ID: 994.039.1
  * Artefact ID Type: TTMAG_ID
* Artefact Appellation: *[Triptych (1978) (centre panel)*
  * Artefact ID: 994.039.2
  * Artefact ID Type: TTMAG_ID
* Artefact Appellation: *Triptych (1978) (right panel)*
  * Artefact ID: 994.039.3
  * Artefact ID Type: TTMAG_ID

On the other hand, the Vancouver Art Gallery records B.C. Binning’s *Mariner’s Triptych: For Night Navigation* as a single work in Artefacts Canada:

* Artefact Appellation: *Mariner’s Triptych: For Night Navigation*
  * Artefact ID: 65.11
  * Artefact ID Type: VAG_ID

Such cases indicate how multi-parts artefacts might be problematic to record both in terms of IDs, but also in the case of other fields such as appellations. For the moment, the ID becomes the bearer of the federation of the objects. 

## Bibliography

Artefacts Canada. 2006. [https://app.pch.gc.ca/application/artefacts_hum/indice_index.app?lang=fr](https://app.pch.gc.ca/application/artefacts_hum/indice_index.app?lang=fr).

Bann, Stephen. "The Return to Curiosity: Shifting Paradigms in Contemporary Museum Display." *Art and Its Publics: Museum Studies at the Millennium*, edited by Andrew McClellan. New Interventions in Art History 2. Malden, US-MA: Blackwell Pub. Co., 2003: 117-132.

Đerić, Tamara Nikolić, Jorjin Neyrinck, and Evelyne Seghers. *Museums and Intangible Cultural Heritage: Towards a Third Space in the Heritage Sector, A Companion to Discover Transformative Heritage Practices for the 21st Century*. Intangible Cultural Heritage & Museums Project. Anderlecht, BE-BRU: Werkplaats immaterieel erfgoed, 2020. [https://www.ichandmuseums.eu/en/toolbox/book-museums-and-intangible-cultural-heritage/success#details](https://www.ichandmuseums.eu/en/toolbox/book-museums-and-intangible-cultural-heritage/success#details).

Doerr, Martin, and Christian Emil Ore, eds. *Definition of the CIDOC Conceptual Reference Model*. CIDOC CRM Documentations, 7.0.1. Paris, FR-IDF: International Council of Museums (ICOM), 2020. [http://www.cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.0.1_%2018-10-2020.pdf](http://www.cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.0.1_%2018-10-2020.pdf).

International Council of Museums. *Object ID*. ICOM. July 19, 2021. [https://icom.museum/en/resources/standards-guidelines/objectid/](https://icom.museum/en/resources/standards-guidelines/objectid/).

Karsh, Yousuf. *Self Portret*. Photography. 1938. This image is available from Library and Archives Canada under the reproduction reference number PA-212511 and under the MIKAN ID number 3198631. This tag does not indicate the copyright status of the attached work. A normal copyright tag is still required. See Commons: Licensing for more information. Library and Archives Canada does not allow free use of its copyrighted works. See Category: Images from Library and Archives Canada. [https://commons.wikimedia.org/wiki/File:Yousuf-Karsh.jpg](https://commons.wikimedia.org/wiki/File:Yousuf-Karsh.jpg).

Law, Simon. *Toronto Eaton Centre, Toronto, Canada*. Photography. Flickr. 2006. [https://commons.wikimedia.org/wiki/File:Flight_stop.jpg](https://commons.wikimedia.org/wiki/File:Flight_stop.jpg).

MacDonald, Sharon, ed. "Collecting Practices." *A Companion to Museum Studies*. Blackwell Companions in Cultural Studies. Malden, US-MA: John Wiley & Sons, 2011: 81-97.

Schmidt-Linsenhoff, Viktoria. "Who Is the Subject? Marie-Guillemine Benoist’s Portrait d’une Négresse." *Slave Portraiture in the Atlantic World*, edited by Agnes Lugo-Ortiz and Angela Rosenthal. Paperback. Cambridge, UK-CAM: Cambridge University Press, 2013: 315-345.

Snow, Michael. *Flight Stop*. Sculpture. Flickr. 1979. [https://commons.wikimedia.org/wiki/File:Flight_stop.jpg](https://commons.wikimedia.org/wiki/File:Flight_stop.jpg).

Waller, Susan. "Marie-Guillemine Benoist, Portrait of Madeleine." *Smarthistory* (blog). September 26, 2018. [https://smarthistory.org/benoist-portrait/](https://smarthistory.org/benoist-portrait/).

Waterhouse, John William. *"'I Am Half Sick of Shadows,' Said The Lady of Shalott" (Alfred, Lord Tennyson, The Lady of Shalott, Part II)*. Painting. 1915. [https://en.wikipedia.org/w/index.php?title=File:John_William_Waterhouse\_-\_I_am_half-sick_of_shadows,\_said_the_lady_of_shalott.JPG&oldid=838315116](https://en.wikipedia.org/w/index.php?title=File:John_William_Waterhouse_-_I_am_half-sick_of_shadows,_said_the_lady_of_shalott.JPG&oldid=838315116).

Wikipedia. "Flight Stop." *Wikipedia*. San Francisco, US-CA: Wikipedia, 2021. [https://en.wikipedia.org/w/index.php?title=Flight_Stop&oldid=1021679066](https://en.wikipedia.org/w/index.php?title=Flight_Stop&oldid=1021679066).

Wikipedia. "John William Waterhouse - I Am Half-Sick of Shadows, Said the Lady of Shalott.JPG." *Wikipedia*. San Francisco, US-CA: Wikipedia, 2018. [https://en.wikipedia.org/w/index.php?title=File:John_William_Waterhouse\_-\_I_am_half-sick_of_shadows,\_said_the_lady_of_shalott.JPG&oldid=838315116](https://en.wikipedia.org/w/index.php?title=File:John_William_Waterhouse_-_I_am_half-sick_of_shadows,_said_the_lady_of_shalott.JPG&oldid=838315116).

