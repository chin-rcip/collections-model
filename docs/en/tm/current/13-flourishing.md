---
layout: page
language: en
title: Flourishing
permalink: /en/target-model/current/flourishing
other_link: /fr/modele-cible/actuel/floruit
sidebar: tm22
date: 2022-03-31
description: The Actors Target Model Specification semantically models actors in a heritage context. Patterns most relevant to actors' lives are presented along with diagrams and examples illustrating them, as well as a record and explanation of relevant decisions that were made when developing said patterns. This is a theoretical documentation that has never been tested or implemented.
---

Version 2.2 ([Previous versions](/collections-model/en/versions))

## At Glance

This pattern can be used to represent the information pertaining to the period of highest productivity and excellence or influence of an actor in a field during their lifetime. It is often referred to as a "floruit". It includes: 

* The dates indicating the beginning and end of a flourishing; 
* The place most associated with a flourishing. 

It pertains specifically to a flourishing in the context of persons and groups of persons, and not to the nature of a flourishing. This pattern does not include: 

* The recognition and influential period of artist·s;
* The flourishing of stylistic movements (e.g. the period during which the principles of a stylistic movement are most visible and common in artefacts); 
* The flourishing of phenomena (e.g. a certain type of exercise that was most widely used at a specific time); 
* The flourishing of objects (e.g. the period during which a literary text was most widely recognized as a masterpiece or important text); 
* The flourishing of concepts or periods (e.g. the advent of modern-day science or of the industrial age);
* The expert·s making the flourishing assessment; 
* The discipline in the context of which the flourishing is assessed;
* The documentation of the occupation of an actor (see the [Occupation](/collections-model/en/target-model/current/occupation) pattern).

## Introduction and Context

### Theoretical Background

Several heritage disciplines are concerned with the most recognized period of activity attributed to a person or group. Because each discipline has a specific focus, how the concept is understood and used varies significantly. For example, in genealogy it is most often associated with the period during which an actor was active, and is used to indicate when they are known to have been alive if there are no records of their birth and/or death (World Heritage Encyclopedia 2021). 

In art history and literature, an artist/creator/thinker or movement’s flourishing refers to the period during which they were producing their most accomplished or widely known work. The flourishing is thus not identified by the artist or movement themselves; it is rather an expert assessment that is made by historians retrospectively and qualitatively (Naas 2016, 1). 

Because it is a specific assessment, it is often used to resolve ambiguity between actors much like the [Birth and Death of a Person](/collections-model/en/target-model/current/birth-and-death) pattern (i.e. two different people might have the same name by happenstance, or a single person might be associated to several names or spellings of a name) as it can be used to confirm someone’s identity (OCLC 2019, 4).

### Statement of Need

The use of this concept by several disciplines establishes a need to represent several of its aspects and associated elements. In particular, it can be applicable not only to persons and groups of persons but also to stylistic movements and cultural works as they can also have revivals or be widely recognized and celebrated at a different date than their initial publication (Naas 2016, 1). Thus, there is a need to indicate which aspects and associated elements the flourishing pertains to, the years during which this flourishing happens as well as the location it is most associated with. 

## Description of the Pattern

The current pattern only applies to actors so that the person or group of persons whose flourishing is depicted is identified as an instance of `E39_Actor` linked by the property `P11_had_participant` to an instance of `E5_Event` which is the central node of this pattern and represents the flourishing itself:

* The flourishing event is qualified as such by an instance of `E55_Type` (a specified qualifier node) labelled "Flourishing" that is linked to the instance of `E5_Event` by the property `P2_has_type`;
* The flourishing event (the instance of `E5_Event`) is situated in time using the [Temporal Bounds](/collections-model/en/target-model/current/temporal-bounds) pattern through the property `P4_has_time-span`, with values extracted from the [Flourishing Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#flourishing-date-begin), [Flourishing Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#flourishing-date-begin-qualifier), [Flourishing Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#flourishing-date-end), and [Flourishing Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#flourishing-date-end-qualifier) entry nodes;
* It is also situated in space by linking the instance of `E5_Event` to the [Flourishing Place](/collections-model/en/semantic-paths-specification/current/entry-nodes#flourishing-place) value (an instance of `E53_Place`) through the property `P7_took_place_at`.

## Diagram

<a name="037_Pattern_Flourishing_p"></a>037_Pattern_Flourishing_p

<iframe frameborder="0" style="width:100%;height:500px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=037_Pattern_Flourishing_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1aT6ayVw8YY5SfmeWooo8ekLKCjq-QPVV%26export%3Ddownload"></iframe>

## Examples

### Example 1

Yousuf Karsh is considered to have been one of the most important photographers during the peak of photojournalism in the 1940s (`P82a_begin_of_the_begin`, Flourishing Date Begin "1940-01-01T00:00:00") and 1950s (`P82b_end_of_the_end`, Flourishing Date End "1959-12-31T23:59:59"), working with such magazines as *Life* (Allen 2014).

<div id="0001_100_flourishing" class="example"></div>

### Example 2

Cyril Henry Barraud, an English painter who participated in World War I as a war artist for the Canadian army, is considered by Artists in Canada to have flourished between 1913 (`P82a_begin_of_the_begin`, Flourishing Date Begin) and 1915 (`P82b_end_of_the_end`, Flourishing Date End) (Canadian Heritage, Government of Canada 2021). 

<div id="0001_114_flourishing" class="example"></div>

### Example 3

Tom Thomson’s artistic peak is considered to have occurred in Canada (`P7_took_place_at`, Flourishing Place) and have run from March 1916 (`P82a_begin_of_the_begin`, Flourishing Date Begin) until his death on July 8, 1917 (`P82b_end_of_the_end`, Flourishing Date End) (Silcox 2015, 16).

<div id="0001_115_flourishing" class="example"></div>

## Related Documentation

### External Models

* Linked.art: [Active Dates](https://linked.art/model/actor/#active-dates)
* SARI: [Person Reference Data Model – Activities](https://docs.swissartresearch.net/et/persons/#activities)
* SARI: [Group Reference Data Model – Activities](https://docs.swissartresearch.net/et/group/#activities) 

### Entry Nodes

* [Flourishing Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#flourishing-date-begin) \| Checklist
* [Flourishing Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#flourishing-date-begin-qualifier) \| Checklist
* [Flourishing Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#flourishing-date-end) \| Checklist
* [Flourishing Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#flourishing-date-end-qualifier) \| Checklist
* [Flourishing Place](/collections-model/en/semantic-paths-specification/current/entry-nodes#flourishing-place) \| Checklist

### CIDOC CRM Entities

* `E5_Event` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E5)]
* `E39_Actor` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E39)]
* `E52_Time-Span` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E52)]
* `E53_Place` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E53)]
* `E55_Type` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E55)]
* `P2_has_type (is_type_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P2)]
* `P4_has_time-span (is_time-span_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P4)]
* `P7_took_place_at (witnessed)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P7)]
* `P11_had_participant (participated_in)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P11)]
* `P79_beginning_is_qualified_by` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P79)]
* `P80_end_is_qualified_by` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P80)]
* `P82a_begin_of_the_begin`
* `P82b_end_of_the_end`

## Discussion

### Rationale

Because the current development of the model is focused on actors rather than objects and collections, the flourishing of non-human agents (e.g. artistic movements, intelligent life, etc.) cannot be documented at the moment. This is why the flourishing is linked to an instance of `E39_Actor` rather than another entity. 

The flourishing event could have been modelled as an instance of `E7_Activity` linked to the actor through the property `P14_carried_out_by`, but this would have entailed considering the flourishing as an active and intentional pursuit on the part of the actor. Because the flourishing of an actor is typically a subjective event determined *a posteriori* by researchers, it cannot be intentionally and actively carried out. Thus, it is more accurate to consider the actor as a participant to their own flourishing which is represented in this pattern using an instance of `E5_Event` linked to the concerned actor using the property `P11_has_participant`. Unfortunately, the specific experts making the flourishing assessment are not currently addressed by this pattern beyond the more generic provenance of the information (through the use of the [Dataset Provenance](/collections-model/en/target-model/current/dataset-provenance) or [Record Provenance](/collections-model/en/target-model/current/record-provenance) pattern). 

### Limitations

The flourishing instance is qualified in this pattern with an instance of `E55_Type` containing the URI for the value "Flourishing", so that it can easily be retrieved in a SPARQL query. However, no further vocabulary terms can be associated with this flourishing instance. Therefore, it is not possible to describe in which field an actor has been flourishing. If the need for such a descriptive term arises, another instance of `E55_Type`, linked to an instance of `E5_Event` through the property `P2_has_type`, could be added to the pattern.

### Related GitHub Issues

* [Issue #2 "Flourished Dates"](https://github.com/chin-rcip/collections-model/issues/2)

### Edge Cases

There are three main cases where there could be more than a single flourishing for an artist: flourishing in different fields, in different mediums, and in a single field and medium interspersed by calmer or inactive periods of production. For example, Marc Séguin has had success both in visual, literary, and cinematographic endeavours. How would each of these flourishings be represented is unclear. In addition, Jean Paul Riopelle’s sculptural flourishing would be considered different from his painting flourishing. Another example: Harper Lee was widely recognized as an accomplished author after the publication of *To Kill a Mockingbird*, but published very little for a long period of time before writing its sequel *Go Set a Watchman* (Editors of Encyclopædia Britannica 2021). This could either be considered to be a long period of flourishing spanning the majority of her career as a writer, or two related flourishing years apart.

## Bibliography

Allen, Evanne. "Tales of a Historic Career: Yousuf Karsh." *National Portrait Gallery, Smithsonian* (blog). 2014. [https://npg.si.edu/blog/tales-historic-career-yousuf-karsh](https://npg.si.edu/blog/tales-historic-career-yousuf-karsh).

Art & Architecture Thesaurus. "Flourishing." *Art & Architecture Thesaurus Online Full Record Display*. October 1, 2019. [http://www.getty.edu/vow/AATFullDisplay?find=flourished&logic=AND&note=&english=N&prev_page=1&subjectid=300393178][http://www.getty.edu/vow/AATFullDisplay?find=flourished&logic=AND&note=&english=N&prev_page=1&subjectid=300393178].

Bruseker, George, and Nicola Carboni. "Digital Object Reference Data Model (SARI Documentation)." *Swiss Art Research Infrastructure*. December 8, 2020. [https://docs.swissartresearch.net/et/do/](https://docs.swissartresearch.net/et/do/).

Canadian Heritage, Government of Canada. "Barraud, Cyril Henry." *Artists in Canada*. Ottawa, CA-ON: Government of Canada, 2021. [https://app.pch.gc.ca/application/aac-aic/artiste_detailler_bas-artist_detail_bas.app?rID=34489&fID=2&lang=en&qlang=en&pID=1&an=barraud&ps=50&sort=AM_ASC](https://app.pch.gc.ca/application/aac-aic/artiste_detailler_bas-artist_detail_bas.app?rID=34489&fID=2&lang=en&qlang=en&pID=1&an=barraud&ps=50&sort=AM_ASC).

Doerr, Martin, and Christian Emil Ore, eds. *Definition of the CIDOC Conceptual Reference Model*. CIDOC CRM Documentations, 7.0.1. Paris, FR-IDF: International Council of Museums (ICOM), 2020. [http://www.cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.0.1_%2018-10-2020.pdf](http://www.cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.0.1_%2018-10-2020.pdf).

Dunn, Stuart, and Simon Mahoney, eds. *The Digital Classicist. Bulletin of the Institute of Classical Studies Supplement 122*. London, UK-LND: University of London Press, 2019 [2013]. [https://library.oapen.org/handle/20.500.12657/39396](https://library.oapen.org/handle/20.500.12657/39396).

Editors of Encyclopædia Britannica. "Harper Lee." *Encyclopædia Britannica*. London, UK-LND: Encyclopædia Britannica, 2021a. [https://www.britannica.com/biography/Harper-Lee](https://www.britannica.com/biography/Harper-Lee).

–––. "Johann Sebastian Bach." *Encyclopædia Britannica*. London, UK-LDN: Encyclopædia Britannica, 2021b. [https://www.britannica.com/biography/Johann-Sebastian-Bach](https://www.britannica.com/biography/Johann-Sebastian-Bach).

Free Dictionary. "Flourishing." *The Free Dictionary*. Huntingdon Valley, US-PA: Farlex, 2019. [https://www.thefreedictionary.com/flourishing](https://www.thefreedictionary.com/flourishing).

Linked.art. *Linked Art Data Model*. Linked.art, 2021. [https://linked.art/model/index.html](https://linked.art/model/index.html).

Merriam-Webster. "Floruit." *Merriam-Webster*. Springfield, US-MA: Merriam-Webster, 2021. [https://www.merriam-webster.com/dictionary/floruit](https://www.merriam-webster.com/dictionary/floruit).

Naas, Michael. "Floruit." *Derrida Today* 9, no. 1 (2016): 1–20. [https://doi.org/10.3366/drt.2016.0116](https://doi.org/10.3366/drt.2016.0116).

OCLC. *Virtual International Authority File Guidelines*. Dublin, US-OH: OCLC, 2019 [2015]. [https://www.oclc.org/content/dam/oclc/viaf/VIAF%20Guidelines.pdf](https://www.oclc.org/content/dam/oclc/viaf/VIAF%20Guidelines.pdf).

Silcox, David P. *Tom Thomson: Life & Work. Canadian Online Art Book Project*. Toronto, CA-ON: Art Canada Institute, 2015. [https://www.aci-iac.ca/art-books/tom-thomson/](https://www.aci-iac.ca/art-books/tom-thomson/).

Whitney Museum of American Art. "David Wojnarowicz: History Keeps Me Awake at Night." *Whitney Exhibitions and Events* (blog). 2018. [https://whitney.org/exhibitions/david-wojnarowicz](https://whitney.org/exhibitions/david-wojnarowicz).

Wikipedia. "Floruit." *Wikipedia*. San Francisco, US-CA: Wikipedia, October 1, 2019. [https://en.wikipedia.org/w/index.php?title=Floruit&oldid=917796873](https://en.wikipedia.org/w/index.php?title=Floruit&oldid=917796873).

World Heritage Encyclopedia. "Floruit." *Project Gutenberg*. June 28, 2021. [http://www.self.gutenberg.org/articles/eng/floruit](http://www.self.gutenberg.org/articles/eng/floruit).

