---
layout: page
language: en
title: 101 - Choosing a LOD Model
permalink: /en/resources/current/how-to/choosing-lod-model
other_link: /fr/ressources/actuel/mode-demploi/choix-modele-dol
sidebar: choosingmodel
group: resources
subgroup: how-to
date: 2022-03-22
description: This document presents an overview of the elements that should be taken into consideration when choosing a linked open data model.
---

**Version 1.0**

**Author:** Marie-Pier Blain, Karine Léonard Brouillet

**Intended audience:** General Public

**Created date:** 2021-05-10

**Last update:** 2022-03-22

**Abstract:** This document presents an overview of the elements that should be taken into consideration when choosing a linked open data model. 

## Choosing a Model

When establishing a Linked Open Data (LOD) ecosystem, the development of an internal systems architecture should rely in large part on the selection of a single or of several compatible data model·s intended to map and understand the local information landscape. Two main options are possible in this regard: 

* Choosing an ontology or ontologies and developing a dedicated applied model internally; 

* Selecting a data model or a combination of data models that suit the needs of the organization.

In both cases, the criteria presented below should be taken into consideration (although in the first case they would be development requirements rather than selection requirements). 

It is likely that an organization must combine several models targeted to the subject domains their information landscape encompasses. When doing so, the criteria below remain relevant in the selection of said models although it is important to make sure that the selected models are compatible with one another and can be linked when and if it is relevant. 

In any case, the [model](https://chin-rcip.github.io/collections-model/en/resources/current/glossary#model-noun) best suited to a project is determined by several elements pertaining to its purpose, scope, and features. As such, the choice of a model is highly dependent on an assessment of the project itself to ensure concordance with the stated needs of an organization. The following section focuses on elements it might be useful to consider when assessing a project from the standpoint of data model selection. 

The following elements are not guidelines for the assessment of a project as a whole and, if this information might be useful to the establishment of a project charter, it should not be considered to be sufficient to such an endeavour. The choice of a model is also impacted by the specific and distinctive characteristics of organizations which should, of course, take their unique profile into consideration. 

### Project Assessment

#### Project Purpose

The use of LOD in an organization can be affected by several elements, including technological readiness, resource availability, and organizational culture. As such, each organization must [determine what the fundamental usefulness of LOD](https://chin-rcip.github.io/collections-model/en/resources/current/lod-benefits-challenges) might be for itself both at the organizational and project levels. Frequent objectives of mobilizing LOD in the heritage sector include: 

* Gaining a practical understanding of LOD and building capacity internally;

* Developing exchange protocols with partners; 

* Modernizing documentation infrastructure so that records are richer and more searchable;

* Gaining visibility online (for a collection or institution).  

#### Project Resources

Similarly, the organization selecting a model should consider their particular resources and constraints to determine the best way to establish their LOD ecosystem. Four development approaches are commonly used by heritage organizations: 

* Using a "ready-made" applied model without adapting it:

  * This is the least demanding approach in terms of modelling as it only requires maintaining compliance with the current version of a single standard; 

  * Only existing classes, properties, patterns, and/or fields can be used, and they must be used in the way they were intended by the model developer which might require resources to adapt the data (or limiting the scope of the project to the model itself);

  * This has the disadvantage of enabling little customization so that the model must reasonably fit the needs of the projects; 

  * The development of such an ecosystem is most often the work of small-sized organizations with general needs (e.g. community centers). 

* Using a "ready-made" applied model and adapting it as little as possible whilst still allowing for the creation of new classes, properties, patterns, and/or fields in compliance with the standard it is based on (i.e. an ontology) to simplify the data conversion process:

  * This is a moderately demanding approach whereas new classes, properties, patterns, and/or fields are created when a specific need that cannot otherwise be addressed emerges;

  * This has the advantage of addressing specific needs, but new classes, properties, patterns, and/or fields will likely not be semantically rich outside the organization;

  * This requires a capacity to standardize local classes, properties, patterns, and/or fields by clearly defining them in a manner coherent with the rest of the model so that they can be used by internal and external stakeholders; 

  * This requires a capacity to publicize local classes, properties, patterns, and/or fields so that they are used by internal and external stakeholders; 

  * This requires a capacity to maintain local classes, properties, patterns, and/or fields up-to-date and aligned with the "main" model so that they can be used by internal and external stakeholders; 

  * The development of such an ecosystem is most often the work of medium-sized organizations with specific needs (e.g. specialized museums). 

* Using several compatible models whilst planning time and resources to routinely update the links amongst them to reflect updates and/or to account for changes made to the models. This approach could include the creation of new classes and/or properties and, if so, the considerations mentioned above should be taken into account. In addition: 

  * This is a highly demanding approach as it requires the development of a master model to standardize alignment between models; 

  * This requires a team dedicated to the update and maintenance of the implemented model·s and the links amongst them; 

  * The development of such an ecosystem is most often the work of larger organizations with varied but interconnected needs (e.g. encyclopedic museums). 

* Developing a model in-house: 

  * This is the most demanding approach as it requires the dedication of an entire team to the acquisition of expertise as well as the development of the model and of its documentation, testing, publicizing, etc.; 

  * This requires a capacity to standardize and clearly define the model so that it can be used by internal and external stakeholders; 

  * This requires a capacity to publicize and make available the model so that it can be used by internal and external stakeholders; 

  * This requires the capacity to contextualize the model, maintain it, and offer support to its users; 

  * The development of such an applied model is most often the work of an overarching organization (e.g. research centers) servicing several smaller stakeholders whose needs and requirements should be taken into consideration in the process. 

#### Semanticization Objectives

Determining what the purpose of the project is directly impacts the domain the model should cover. This is thus a foundational step that should not be underestimated because it also determines who is involved and what the scope of the project is in terms of deliverables and resources. For example, the above objectives might take different forms when thought of as projects per se: 

* Gaining a practical understanding of LOD and building capacity internally by doing a small-scale proof of concept in a specific department with the intention to eventually adopt open data at scale throughout the organization:

  * A project testing scalability should adopt a model that will fit the needs of the end project rather than those of the proof of concept; 

  * If building capacity is one of the aims of the project, a model thoroughly documented (i.e. with examples, 101 resources, etc.) should be selected; 

  * If developing data harmonization and sharing partnerships is an end goal of the project, prioritizing the opening of relevant data will be of importance and, as such, the model should be determined based on these data

* Developing exchange protocols with partners through a pilot project: 

  * A project testing collaboration should adopt a model that covers the needs of all the parties involved; 

  * If working with a partner that already uses an LOD model, it is important to ensure that it is compatible with the one selected by the project (if need be). 

* Modernizing documentation infrastructure so that records are richer (thanks to enrichment and crowdsourcing for example) by targeting a collection to enrich through crowdsourcing: 

    * A project testing enrichment should adopt a model that covers multiple relevant domains so that it can accommodate the variety of information that might be submitted by users; 

    * A model that can accommodate free-text is also useful in this context;

    * A model that can be searchable through simple and complex queries facilitates work and supports efficiency in the context of such a project. 

* Gaining visibility online (for a collection or institution) by creating or reusing URIs to identify or describe artefacts, submitting them to large repositories such as Wikidata, and actively promoting them: 

  * A project centered on the creation of URIs will not guarantee visibility as much as accessibility and, as such, the chosen model should be selected based on its use by the rest of the community more than on enrichment of the original dataset·s; 

  * Larger and well-known repositories are useful for URIs but might not bring much more so that it might be interesting to use them in conjunction with other compatible models.

#### Dataset Features

The scope of the project dictates what the organizational or business needs are and, along with these, what dataset·s should be semanticized. An assessment of the chosen dataset·s should include an evaluation of the following aspects: 

* Subject and/or domain covered: 

  * The model’s domain should cover that of the dataset·s, and would ideally be either larger (covering more subjects than only the available data) or more granular (covering the subjects reflected in the available data very precisely) than that of the dataset·s for the semanticization to be relevant; 

  * There is sufficient information in both the dataset and selected model documentation to adequately map them to each other. 

* Messiness level of the dataset·s and necessary data cleaning (as a messy dataset will likely only generate a series of free-text nodes of little semantic value): 

  * If added semantic value is not the aim of the project and a series of free-text nodes is deemed relevant (such as when only creating URIs), it is important to select a model that can accommodate such nodes so that they can be retrieved even if their contents cannot easily be searched; 

  * Usable data not only amounts to cleanliness but also standardization through other tools and resources such as controlled vocabularies that should be compatible with the selected model’s fields or nodes; 

  * Since the data will inevitably evolve on that front, update recording should be taken into account if this is an important element to the project. 

* Information represented in the dataset·s (i.e. what data is found in the fields to be semanticized): 

  * The data might cover domains different from the primary subject of the dataset·s and should thus be taken into consideration so that the model·s account·s for variability and cover·s it adequately; 

  * Information intended to be ingested through semanticization (i.e. what data would subject matter experts like to gain from the process) should also be taken into consideration, as well as any data said experts would be interested in having access to as a result of the semanticization process; 

  * Organization-specific needs (in terms of specialized or legal information) should be covered by the model, or the latter should be adaptable to cover these.

* Breadth of the model and of the dataset·s are comparable: 

  * A very precise dataset mapped to a very broad model (and vice versa) will be of little semantic value so that the expressivity levels should be on par to adequately answer the dataset’s descriptive needs; 

  * In any case a model that is more expressive than not is always preferable as long as it can be maintained. 


### Model Assessment

#### Patterns Coverage

The previous assessment illuminates the elements that are most important to the success of the project data-wise, which in turn establishes which [patterns](https://chin-rcip.github.io/collections-model/en/resources/current/glossary#pattern-noun) should imperatively be covered by the chosen model, and which are ancillary. It is advisable to identify a sample of core patterns to look at more closely when comparing models in order to ensure that the intended meaning of the data is adequately represented by the semantics of the model. 

Relevant elements to consider in this context include: 

* Is the pattern well documented and defined so that it can be easily assessed by subject domain experts? This is typically reflected, amongst other things, in: 

  * Thorough documentation that is consistent and well-organized; 

  * Examples that illustrate good use of the pattern; 

  * Explicit indication of potential pitfalls or limitations of the pattern. 

* Does the pattern handle data in a way that is consistent with the intended meaning of the data it will accomodate? This can typically be assessed by: 

  * Looking at the use cases and examples that lead to the creation of the pattern and determining whether they mobilize similar concepts to the data; 

  * Evaluating how information is treated (based on the documentation) rather than the name of the pattern (which is a good indicator, but might sometimes be misleading). 

* Is the data format of the values accommodated by the patterns (e.g. dates, geographical locations)? In many cases, patterns accommodate several data formats:  

  * More precise and structured formats enable more semanticization whereas free-form text generates little semantic links; 

  * If the data include several formats and cleaning is not possible or intended, the pattern should accommodate all of these formats. 

* Does the use of the pattern necessitate cleaning, enhancing, or enriching the data (e.g. more consistent date formats, more precise geographical locations)?

* Is the pattern consistent with the rest of the model and does the general structure and worldview it presents align with those of the data?

In many cases, this examination might reveal discrepancies between the precision levels of the dataset·s and of the semantic model. Whilst the model might be more detailed for certain aspects (e.g. dates, geographical locations), the data might be more precise on others (e.g. occupations, statuses). In such a case, it might be relevant to select and use several semantically (i.e. the entities’ scope notes have the same inherent meaning) and technically (i.e. the minimal requirements must be the same in terms of format and specification) compatible models dedicated to specific aspects of the dataset·s in order to adequately represent its richness and intricacy.  

When the model is the most detailed, the data can be cleaned and enriched before mapping in order to have better results. Still, there can be instances in which the most precise information is not available so that it is important to assess how broader information is treated by a precise model: the chosen model should accommodate different data granularities without inducing falsities. 

On the other hand, when the data is more detailed than the pattern, it is important to determine whether the information it contains is covered elsewhere in the model through another pattern (i.e. mapping must be fine-tuned, which might require data cleaning if several pieces of information are found in a single field), or not at all (in which case the importance of that information must be assessed in order to determine if the model is still adequate).

#### Relevancy

The adequacy of the model to the project relies heavily on its patterns covering the representation needs of intended users. That said, other elements might impact the usefulness of a model. The following questions should be considered: 

* Is the model also adopted by or adequate to the needs of partners, stakeholders, and/or the rest of the community? This is important because: 

  * In domains where LOD adoption is still in its infancy, most stakeholders might be internal to the organization, but eventually lead larger-scale adoption; 

  * A high adoption rate by the people involved will likely lead to more inter-institutional linking and, as a result, to better semanticization and enrichment. 

* Are issues adequately and openly discussed and, when need be, resolved to the benefit of the community? This is essential because: 

  * The issues the project will face might have already been resolved by others; 

  * Any issues that would not have been addressed can be submitted. 

* Is the model adequately addressing the evolution of practices in the domain covered by the project? This is reflected in whether: 

  * Information that has recently become standard to document is represented or discussed; 

  * Domain of practice specific concerns are reflected in the documentation; 

  * New entities can be linked to through controlled vocabularies or added through a clear submission protocol.

* In the case of heritage projects, the following elements are often important: 

  * Provenance of the data: it is often necessary to indicate or verify who created or recorded an information, especially when there are conflicting viewpoints on a subject (e.g. disagreement on the date of the birth of a person); 

  * Datation of the contents: information pertaining to when something occurred is often crucial yet it is rarely precise enough to identify a date and time so that having the possibility to use time intervals is important (i.e. for a stylistic period); 

  * Fuzziness of the data: a certain data field in the original database might contain several data formats (e.g. textual descriptions of dates such as "during the spring of 1992" and structured dates such as "1992-05-14") so that it is often necessary to accommodate textual contents in addition to structured contents (this also applies when there are several levels of data cleanliness). 

#### Adaptability

In addition, even if the model is both relevant and adequate in terms of domain coverage, it must be adaptable to the particularities of the dataset·s contents which, for example, might change over time as a collection grows. In order to ensure that it is so, the following elements should be taken into consideration: 

* Is the model flexible enough to meet local requirements? This is reflected in whether: 

  * It is compatible with other relevant models that are compatible with it semantically (i.e. the entities’ scope notes have the same inherent meaning) and technically (i.e. the minimal requirements must be the same in terms of format and specification);

  * It is extensible in the sense that local fields, classes, properties, and/or patterns can easily be developed and added to suit specific needs whilst respecting the standard’s constraints; 

  * It can be used in conjunction with controlled vocabularies and thesauri to enhance the precision-level of the classes, properties, and/or patterns to suit specific needs that cannot be addressed otherwise. 

* Is the model accommodating both unstructured (i.e. internal descriptive text, etc.) and structured data (i.e. controlled vocabularies, etc.) so that both can be represented in it? This is typically reflected in: 

  * The presence of data patterns and/or fields that are intended to accommodate and handle unstructured long-form content, typically identified by the terms "linguistic object", "textual data", "description", etc.; 

  * The presence of data patterns and/or fields that are intended to accommodate and handle structured content, typically identified by terms such as "controlled vocabulary", "thesaurus", or the use of URIs; 

  * The use of "string" as a minimal requirement format for the submitted values. 

* Are there structures that enable the handling of more precise or broad information? This is usually reflected in: 

  * The presence of a hierarchy of classes, properties, patterns, and/or fields that allow the use of higher-level concepts to still meaningfully represent information when the more precise classes and properties are not adequately representing the data contents; 

  * The availability of both general and precise patterns and/or fields that can be used in conjunction with one another; 

  * Recommendations concerning the use of controlled vocabularies and thesauri to further qualify information. 

#### Sustainability and Maintenance

Finally, it is crucial to ensure that the chosen model can be used for the entirety of the anticipated project and, possibly, any deployment that might follow. Although certainty on this matter is never possible, the custodian of the model should: 

* Be a well-established and reputable organization that dedicates resources to the model’s maintenance and development, which is typically established by: 

  * Mentions in the organization’s strategic planning or mission statement; 

  * Involvement in the community; 

  * Regular upkeep and improvement of the model; 

  * Clear contact point where to signal issues or make enquiries. 

* Establish its governance principles and policies clearly: 

  * These should align with those of the project; 

  * The licence of the model should be in concordance with the needs of the project (ideally an open licence such as CC0 or CC-BY).

* Document its modellization process and render its results usable by offering the model in relevant formats such as XML or RDF. 

* Make consistent and relevant updates that keep the model current, as demonstrated by: 

  * Updates mentions on the website (with the date and nature of the update stated); 

  * Discussion of issues (as discussed in dedicated forums, comments sections, or others); 

  * Development of new patterns or adjustments to already existing patterns to align with the general evolution of the practice domain covered. 

## Bibliography

Bailey, Jason. "Solving Art’s Data Problem - Part One, Museums." *Artnome* (blog). April 29, 2019. [https://www.artnome.com/news/2019/4/29/solving-arts-data-problem-part-one-museums](https://www.artnome.com/news/2019/4/29/solving-arts-data-problem-part-one-museums).

Data, Open Art. "Museums: Interactive Map with Wikidata." *Open Data Art* (blog). December 16, 2018. [https://www.openartdata.org/2018/12/museums-map-wikidata.html](https://www.openartdata.org/2018/12/museums-map-wikidata.html).

Edson, Michael Peter. "Wikimania 2019 Keynote Address." Keynote presented at *Wikimania 2019*, Stockholm, SE, April 29, 2019. [https://www.youtube.com/watch?v=9NBonp9KLz8](https://www.youtube.com/watch?v=9NBonp9KLz8).

Frosterus, Matias, David Hansson, Maral Dadvar, Ilias Kyriazis, Sofia Zapounidou, and Friedel Grant. "Best Practices for Library Linked Open Data (LOD) Publication." The Hague, NL-ZH: LIBER (Ligue des bibliothèques européennes de recherche - Association of European Research Libraries), 2021. [https://libereurope.eu/article/libers-linked-open-data-working-group-publishes-best-practices-for-library-linked-open-data-lod-publication/](https://libereurope.eu/article/libers-linked-open-data-working-group-publishes-best-practices-for-library-linked-open-data-lod-publication/).

Goldman, Kathryn. "Open Access Images of Public Domain Work." *Creative Law Center* (blog). 2018. [https://creativelawcenter.com/museums-open-access-images/](https://creativelawcenter.com/museums-open-access-images/).

Hyland, Bernadette, Ghislain A. Atemezing, and Boris Villazón-Terrazas. "Best Practices for Publishing Linked Data." W3C Working Group Note. January 9, 2014. [https://www.w3.org/TR/ld-bp/](https://www.w3.org/TR/ld-bp/).

Kela, Riitta. "Opening Collections as Open Data: Challenges and Possibilities." *Documenting Culture: A Culture of Documentation*. Tokyo, JP: International Council of Museums (ICOM), 2019.

McCarthy, Douglas. "Licensing Policy and Practice in Open Glam." *Medium*. May 30, 2019. [https://medium.com/open-glam/licensing-policy-and-practice-in-open-glam-49c867b49de8](https://medium.com/open-glam/licensing-policy-and-practice-in-open-glam-49c867b49de8).

Oomen, Johan, Enno Meijers, and Wilbert Helmus. "Network Digital Heritage: Towards A Distributed Network of Heritage Information." *International Conference on Digital Preservation* (IPRES). Amsterdam, NL: Dutch Digital Heritage Network, 2016. [https://www.netwerkdigitaalerfgoed.nl/wp-content/uploads/2018/02/NDE_PositionPaper_NetworkHeritageInformation-EN-v2.pdf](https://www.netwerkdigitaalerfgoed.nl/wp-content/uploads/2018/02/NDE_PositionPaper_NetworkHeritageInformation-EN-v2.pdf).

Open GLAM. *Declaration on Open Access for Cultural Heritage*. January 21, 2020. [https://docs.google.com/document/d/1CpDGlWLgkEYJC5A2HJ_Os8XYEv7ONOIBYAobSFzWm14/edit?usp=embed_facebook](https://docs.google.com/document/d/1CpDGlWLgkEYJC5A2HJ_Os8XYEv7ONOIBYAobSFzWm14/edit?usp=embed_facebook).

Open Knowledge Foundation. "Resources." *OpenGLAM*. November 27, 2012. [https://openglam.org/resources/](https://openglam.org/resources/).

Openness: Politics, Practices, Poetics. *Living Archives*. Malmˆ, SE: Malmˆ University, 2017. [http://muep.mau.se/bitstream/handle/2043/23606/openness_final.pdf?sequence=2\&isAllowed=y#page=14](http://muep.mau.se/bitstream/handle/2043/23606/openness_final.pdf?sequence=2\&isAllowed=y#page=14).

Sanderhoff, Merete, ed. *Sharing Is Caring: Openness and Sharing in The Cultural Heritage Sector*. Translated by Néné La Beet and René Lauritsen. Copenhagen, DK: Statens Museum for Kunst, 2014. [https://www.smk.dk/en/article/the-sharing-is-caring-anthology/](https://www.smk.dk/en/article/the-sharing-is-caring-anthology/).

Schrier, Bill. "Government Open Data: Benefits, Strategies, and Use." *The Evans School Review*, Alumni Perspective, 4, no. 1 (2014): 12‑27.

Stimler, Neal, and Louise Rawlinson. "Where Are The Edit and Upload Buttons? Dynamic Futures for Museum Collections Online." *MuseWeb*. Boston, MA: MuseWeb, 2019. [https://mw19.mwconf.org/paper/where-are-the-edit-and-upload-buttons-dynamic-futures-for-museum-collections-online/](https://mw19.mwconf.org/paper/where-are-the-edit-and-upload-buttons-dynamic-futures-for-museum-collections-online/).

Stinson, Alex. "Wikidata in Collections: Building a Universal Language for Connecting GLAM Catalogs." *Medium* (blog). April 9, 2018. [https://medium.com/freely-sharing-the-sum-of-all-knowledge/wikidata-in-collections-building-a-universal-language-for-connecting-glam-catalogs-59b14aa3214c](https://medium.com/freely-sharing-the-sum-of-all-knowledge/wikidata-in-collections-building-a-universal-language-for-connecting-glam-catalogs-59b14aa3214c).

Vathana, Anly, and Dev Pramil Audsin. "An Open Analysis on Open Data." Submission paper. *Open Data on the Web*, 4. London, GB: W3C, 2013. [https://www.w3.org/2013/04/odw/odw13_submission_33.pdf](https://www.w3.org/2013/04/odw/odw13_submission_33.pdf).

Wallace, Andrea. « Access and the Digital Surrogate: Openness as a Philosophy ». Presented at *National Digital Forum*, Wellington, NZ, November 27, 2017. [https://www.youtube.com/watch?v=crKUIxIX3sY](https://www.youtube.com/watch?v=crKUIxIX3sY).

