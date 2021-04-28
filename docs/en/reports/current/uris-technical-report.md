---
layout: page
language: en
title: URIs Technical Report
permalink: /en/technical-reports/current/uris-technical-report
other_link: /fr/rapports-techniques/actuel/rapport-technique-sur-les-uris
sidebar: urireport
group: technical reports
---

**Version**: 2.1

**Authors**: Trang Dang, Stephen Hart, Karine Léonard Brouillet, Philippe Michon

**Created date**: 2020-04-24

**Last update**: 2021-04-27


## Abstract

This technical report details the (1) organizing principles that dictate the (2) recommended CHIN URI specification template and the (3) management of these URIs (currently under development and projected to be released here in a subsequent version). As such, it is focused on the elements that are directly relevant to CHIN as an organization and is directed at decision-makers it reports to. That said, the current document can be used by other heritage or governmental organizations to derive internal guidelines for the publication of URIs.

## Context

### CHIN Linked Open Data Work

CHIN, in keeping with its mandate to “assist Canadian museums in documenting, managing, and sharing information about their collections”, is currently developing resources for Canadian data to enter the Linked Open Data (LOD) ecosystem, which is increasingly used by heritage professionals across the world to document cultural artefacts. The objectives of CHIN projects include the:

1.  Identification of heritage entities (actors<sup>[1](#note-1)</sup>, objects) through the use of unique resource identifiers (URIs);

2.  Representation of the relationships amongst actors and/or objects;

3.  Enhancement of information readily available about material culture by reconciling data from different sources.

Targeted users include researchers and professionals from the heritage, academic and semantic sectors; galleries, libraries, archives and museums; as well as software tools suitable to the interpretation and mobilization of such data. The heritage industry will also benefit from this new data ecosystem suitable through access to open and reusable data when developing application interfaces that can in turn serve the general public.

The main benefit of LOD is their potential to disperse CHINs’ and stakeholders’ burden of caring for data by:

1.  Facilitating research by users;

2.  Encouraging open documentation and its consumption;

3.  Facilitating the linking of information by researchers, publics, and members of specific or marginalized communities in a co-documentational approach whereas all are welcome to reuse the models and thus make their data accessible and open;

4.  Making explicit the meaning and structure of linked open databases through meaningful links across datasets, rather than relying solely on catalogers’ local and implicit understanding of the data.

### Statement of Intent

This technical report is a foray into the considerations and principles that underpin the management of URIs at CHIN. As such, it is focused on the elements that are directly relevant to CHIN as an organization and is directed at decision-makers the agency reports to. That said, the current document can be used by other heritage or governmental organizations to derive internal guidelines for the publication of URIs.

Even though best practices and general consensus on how best to manage URIs will certainly evolve with time, because URIs are intended to be reused by external stakeholders as part of the semantic web community, it is crucial that published (and thus potentially reused) URIs remain unchanged in order to ensure usability and relevance as well as functionality of both CHIN and those who (will) reuse its URIs.

The main objective of this report is thus to determine how to best name and manage URIs. It is divided into three main sections:

1.  Organizing Principles—an explanation of core concepts and best practices for naming and managing URIs based on a literature review of leading organizations current practices and recommendations;

2.  CHIN Specification—an examination of how CHIN names and handles URIs;

3.  Management—a presentation of issues relevant to the creation, publication, and maintenance of URIs (currently under development and projected to be released here in a subsequent version).

## Organizing Principles

A Unique Resource Identifier (URI) is composed of four main parts:

1.  Scheme: the part of the URI that precedes the `:` and specifies the type of application to be used (the most common schemes are http and https); URI schemes should be registered with the [Internet Assigned Numbers Authority (IANA)](https://www.iana.org/).

2.  Domain: the part of the URI that typically follows the scheme and identifies ownership or control of a resource (the most common format is `domainName.something`); domain name format must be compliant with the domain name system as well as the policies of the organization storing and managing the URIs (as well as owning the domain name).

3.  Segment(s): the strings of characters that follow the domain name and are bound by `/`; the segments specify the categorization of a resource within a system and are preferably human-readable in order to facilitate understanding on the part of professionals (typically, segments facilitate navigation by identifying which elements of a system a resource belongs to).

4.  Slug: the final segment is the segment that is specific to the resource and is most often opaque; it is sometimes called the “final segment”.

The syntax of a URI thus goes as follows:

```
scheme://domainName.lod/segment1/segment2/slug
```

There are several ways to structure URIs so that they are consistent with the system or organization in which they fit. A review of internal directives and specifications should be done in order to ensure compliance with an organization’s data best practices.

In addition to these recommendations, URIs should be compliant with the following three principles ([Berners-Lee 1998](#berners-lee-1998); [Sauermann and Cyganiak 2008](#sauermann-cyganiak-2008)):

1.  *Stability*: Because the purpose of the URI is to consistently identify a resource, it should remain unchanged so that it can easily be retrieved. As such, it is recommended to keep implementation-specific units such as `.php` or `.asp` out of URIs so that they remain unaffected by operational or technological changes.

2.  *Simplicity*: Because URIs are used by multiple users across an LOD ecosystem, and sometimes beyond an organization, it is best to use short and mnemonic segments in order to facilitate sharing, use, and maintenance on the part of practitioners.

3.  *Manageability*: URIs should be issued in a manner consistent with the organization’s maintenance and management needs (e.g. storing all 303 URIs on a dedicated subdomain to facilitate the migration of the URI-handling subsystem later on).

Moreover, it is not always necessary to create new URIs, especially in the case of common concepts (e.g. locations, roles, materials, etc.) that are already part of dedicated controlled vocabularies maintained by reputable organizations ([Archer, Goedertier, and Loutas 2013, 41](#archer-et-al-2013)). In such cases, it is advisable to reuse established URIs in order to minimize the maintenance responsibilities of the organization as well as support interoperability.

Finally, for organizations that only want to generate URIs for their content without managing how their content will be presented, it is possible to use basic persistent identifier generation and management tools such as [ARK](http://n2t.net/e/ark_ids.html), [Handle](https://www.handle.net), or [DOI](http://www.doi.org/) ([Koster 2020](#koster-2020)).

However, for organizations that wish to manage what representation of a resource will be delivered based on context (i.e. content negotiation), such tools are insufficient and a dedicated URI generation system is advisable (this is CHIN’s case).

## CHIN Recommended Specification 

Whilst there is no particular policy pertaining to URIs, the Canadian Government recommends alignment with the United Kingdom’s [Designing URI Sets for the UK Public Sector: A report from the Public Sector Information Domain of the CTO Council’s cross-Government Enterprise Architecture](https://assets.publishing.service.gov.uk/government/uploads/system/uploads/attachment_data/file/60975/designing-URI-sets-uk-public-sector.pdf). The latter indicates, amongst other things, that:

1.  The expected longevity and potential for re-use of URIs should be published, and URI sets promoted for re-use should be designed to last for at least 10 years ([Chief Technology Officer Council 2009, 3](#chief-technology-officer-council-2009)).

2.  The department or agency responsible for defining and naming instances should be responsible for it, but its name should not appear in the URI ([Chief Technology Officer Council 2009, 4](#chief-technology-officer-council-2009)). That said, the publisher must have content-control of the sub-domain the URI set resolves to, and the domain must have service-levels and scalability in conjunction with an understanding that the domain will be maintained in perpetuity; in other words, the “domain itself should convey an assurance of quality and longevity” ([Chief Technology Officer Council 2009, 5](#chief-technology-officer-council-2009)).

3.  At least one semantic representation must enable the construction of an RDF graph, although offering additional formats is recommended ([Chief Technology Officer Council 2009, 10](#chief-technology-officer-council-2009)).

In addition, Government of Canada general guidelines pertaining to the publication of other content dictate that bilingualism should be embedded in naming conventions as much as possible, although this does not seem to be mandatory in the case of URIs.

For these reasons, CHIN recommends a project-based naming convention for its URIs, whereas bilingual acronyms, abbreviations, and codes will be favoured over monolingual ones (as long as they facilitate rather than hinder understanding).

This approach is applicable to URIs assigned to different types of data an organization manages ([Henderson, Earley, and Sebastian-Coleman 2017, 422](#henderson-et-al-2017)), namely:

  - *Descriptive*: data that describes a resource and enables identification and retrieval (e.g. definitions and descriptions of data sets, data models and standards, usage notes and issues, etc.).

  - *Structural*: data that describes relationships within and amongst resources and their component parts (table and column names, access permissions, file format schema definitions, mapping documentation, update schedules and dependencies, recovery and backup rules, etc.).

  - *Operational*: data used to manage resources over their lifecycle (logs of job execution of batch programs, schedule abnormalities, error logs, volumetric and usage patterns, etc.).

For all of these, content negotiation will be implemented.

### Content Negotiation - URLs Derived from URIs. 

Content negotiation’s fundamental concept is the distinction between the URI of an entity and its manifestations, which typically take the form of uniform resource locators (URLs, whose forms are not governed by the same principles as those of URIs). This enables many renderings of information based on the needs of the user querying it.

For example, the semantic rendering of an ensemble will be a replica of the RDF graph where each instance will have an HTML page displaying the entirety of statements involving the instance. On the other hand, a public interface displays only information determined to be relevant by the query (e.g. there is no need to display the URI of the *event* of a birth in addition to that of the birth *itself*).

In order to differentiate the various representations of information associated with a URI, these representations should use the shortest URI path and append URL relevant information atop of it. There are two types of representations that should be made accessible to the public: data format specific representations and human readable interfaces.

#### Data Format Specific Representations

Data format specific representations of entities enable a user to consume information in the data format that best suits their needs, which can be specified by appending the file format extension to the end of the URI per the following template:

```
scheme://domainName.lod/segment/slug.fileExtension

https://nameOfProject.lod/ontologyCode_classCode/providerID_randomNumber.fileExtension
```

For a URI that would go as follows:

```
scheme://domainName.lod/segment/slug

https://nameOfProject.lod/ontologyCode_classCode/providerID_randomNumber
```

Possible representations would be as follows:

```
scheme://domainName.lod/segment/slug.html

https://nameOfProject.lod/ontologyCode_classCode/providerID_randomNumber.html
```
```
scheme://domainName.lod/segment/slug.jsonld

https://nameOfProject.lod/ontologyCode_classCode/providerID_randomNumber.jsonld
```
```
scheme://domainName.lod/segment/slug.rdf

https://nameOfProject.lod/ontologyCode_classCode/providerID_randomNumber.rdf
```
```
scheme://domainName.lod/segment/slug.ttl

https://nameOfProject.lod/ontologyCode_classCode/providerID_randomNumber.ttl
```

Such representations would display only the direct links of a targeted entity. For example when displaying data about the birth of a person, the representation would only include the statement linking the person to the *event* of their birth; in order to know what *date* this event took place, a user would have to follow the URI path leading to this information.

#### Human-Readable Interfaces

Human-readable interfaces of the entities and knowledge graphs enable a user-friendly consumption of the information by users and can be specified by inserting an additional segment in the URI right after the domain name:

```
scheme://domainName.lod/webPage/segment/slug

https://nameOfProject.lod/webPage/ontologyCode_classCode/providerID_randomNumber
```

Links to the aforementioned RDF representations can be displayed on the human-readable web page of an entity in addition to other RDF representations. This could include representations that would embed in a single file all semantic statements and entities required to capture the information displayed on a web page (to offer the full path from the person to their birthdate for example).

Note that it is advisable to have a main interface that is not specific to any entity for the users to come back to should they wish to do so:

```
scheme://domainName.lod/webPage

https://nameOfProject.lod/webPage
```

### URI Template

A single URI template can be used to accommodate several types of data (descriptive, structural, operational). That said, different types of URIs might require a targeted template for implementation purposes. In the context of heritage information, the three types of URIs most likely to be encountered are:

  - Content URIs: used to store descriptive data (submitted core data and its metadata) in a dataset.

  - Vocabulary URIs: used to identify the terms of a corresponding vocabulary or thesaurus.

  - Ontological URIs: used to identify the classes and properties of an ontology. Because they create the fundamental linking layer of the model, ontological URIs often use a different template to other business (content and vocabulary) URIs (e.g. they are typically created using \# signs rather than / signs).

All of these can be generated using the following template<sup>[2](#note-2)</sup>:

```
https://nameOfProject.lod/ontologyCode_classCode/providerID_randomNumber
```

#### Scheme - Secure Protocole

In order to ensure security across the network and comply with current best practices, URIs will be accessed under Hypertext Transfer Protocol Secure (https).

#### Domain - Project Oriented

CHIN recommends using the name of the overarching organization or project that oversees the management the URIs as a domain name for several reasons:

1.  The organization managing the URIs is made clear in the URI itself, which facilitates work for practitioners who would need to identify it or communicate with it;

2.  Accessing the project page from the URIs is thus easier as the user can simply refer to the main URL;

3.  The domain name of a project is typically stable and will not change over time, which ensures the stability of the URIs.

Because CHIN is located under the canada.ca domain and does not have an independent and dedicated domain name, it is not advisable to use CHIN’s current position in the canada.ca website as a starting point. It is inadvisable to use the name of departments or agencies as the domain or URIs because they are subject to change both in terms of their official name and in terms of their position within the governmental website and organizational chart.

CHIN has thus elected to use a shortened version of the name of its project dedicated to collections data management as a domain name, DOnnées Patrimoniales HEritage DAta (DOPHEDA): `dopheda.info`. The latter has been selected because it is bilingual/alingual, short, easily retrieved by search engines, and independent of the canada.ca infrastructure (i.e. hosted on a dedicated domain).

#### Segments - Meaningful to the Organization

The segments are the elements of the URI’s path where, typically, a negotiation occurs between meaningfulness (which confers readability) and opaqueness (which confers sustainability by isolating the element from its conceptual understanding, which might change over time).

A URI is considered meaningful when it contains legible data describing the resource it identifies (e.g. a meaningful URI for the city Ottawa could contain “ottawa” or a postal code) so that it is easily readable and understandable by practitioners. However, solely relying on meaningful elements for the segments onwards induces the risk of ambiguity (e.g. mistaking the city of Ottawa, located in Canada, and that of the same name located in Illinois, US). This is also of concern for any data that is subject to change, as the name of the city might change over time (e.g. what was formerly the city of Vanier is now part of the city of Ottawa).

A URI is considered opaque when its segments are completely disconnected from the content the resource identifies (e.g. a random string of numbers) so that it is perennial and alingual by easily encompassing several appellations of a single entity (e.g. a random number can be used to refer to Istanbul, Constantinopolis and Byzantium at once). However, fully opaque URIs are difficult to read, understand, and manage for practitioners, especially so in contexts where they must mobilize LOD technologies without having expert knowledge of them.

CHIN thus recommends the use of a combination of meaningful and opaque segments to ensure both practitioner readability and technical sustainability. The best way to implement this is by choosing a classification system that is complementary to the organization’s data ecosystem and using a concise version of it to specify content segments, with the last part of the URI (the one most specific to the resource) being an opaque number.

In CHIN’s case, content URIs will be using ontology abbreviations and class codes in order to clarify how the resource is categorized in the DOPHEDA ecosystem (using the `ontologyAbbreviation_classCode` syntax). That way, entities of a specific class will share the same path, which is consistent with CIDOC CRM’s event-oriented model (which is the basis of DOPHEDA).

In most cases, this will mean reusing CIDOC CRM class codes (using the `crm_exx` syntax). In cases when other ontologies that do not have official codes are used, a directory will be maintained by CHIN using the `ontologyAbbreviation_classNumber` syntax. This will facilitate use at the same time as it will address bilingualism concerns and resolve any issues that might arise from the ontology changing the name of the class. For the same reasons, it is advisable to prioritize the use of meaningful superclass codes in the URIs rather than overarching higher-level classes (that encompass so many concepts they convey no substantial understanding) or more specific subclasses (that are more subject to change). Examples of such segments would be:

```
/crm_e39/
/prov_1/
/skos_1/
```

The main classes that are most likely to be used are the following:

  - `E4_Period` (`/crm_e4/`)

  - `E5_Event` (`/crm_e5/`)

  - `E18_Physical_Thing` (`/crm_e18/`)

  - `E28_Conceptual_Object` (`/crm_e28/`)

  - `E39_Actor` (`/crm_e39/`)

  - `E41_Appellation` (`/crm_e41/`)

  - `E52_Time-Span` (`/crm_e52/`)

  - `E53_Place` (`/crm_e53/`)

  - `E55_Type` (`/crm_e55/`)

  - `E63_Beginning_of_Existence` (`/crm_e63/`)

  - `E64_End_of_Existence` (`/crm_e64/`)

In cases where multiple classes are used to identify a unique entity, a single URI should be created per rules established by the organization. In the case of CHIN, because such double instantiation is rare and will likely occur infrequently, this will be determined on a case by case basis<sup>[3](#note-3)</sup>.

#### Slug - Semi-Opaque

The same considerations that apply to the segments apply to the slug. In the case of CHIN’s descriptive URIs there are two main needs that must be accounted for in the slug: the possibility to identify the provider of the data associated with the URI, and the necessity to uniquely identify the resource. Slugs will thus have the `providerID_randomNumber` format, whereas CHIN will maintain a directory of data provider IDs (assigned on an incremental basis) and random numbers will be assigned to the last part of the slug to establish uniqueness (several tools, such as [NOID](https://n2t.net/e/noid.html) and [UUID](https://www.uuidgenerator.net/), can be used to generate such random numbers). This will:

  - Ensure the non-duplicity of the identifiers created;

  - Streamline queries pertaining to the provenance of data;

  - Facilitate maintenance and update protocols of datasets.

It is recommended to use a unique number (whether randomly or incrementally assigned) as the complete slug, or as part of it. If a legible part is added to the slug, it should be meaningful to the managing organization and fulfill a clear need on their part.

## Management

This question is currently being examined by CHIN and will be added once its writing has been completed. It will address :

  - What URIs will be under CHIN’s custodianship and which will only be mobilized by it;

  - How URIs will be exploited in CHIN’s LOD ecosystem;

  - Creation and maintenance principles;

  - Relevant envisioned integrity and security principles and/or protocols.

For comments or inquiries, please do not hesitate to contact us at <pch.RCIP-CHIN.pch@canada.ca> with the subject “URI Technical Report”.


## Bibliography

<a name="archer-et-al-2013"></a>Archer, Phil, Stijn Goedertier, and Nikolaos Loutas. 2013. ‘Study on Persistent URIs, with Identification of the Best Practices and Recommendations on the Topic for the MSs and the EC’. D7.1.3. ISA - Interoperability Solutions for European Public Administrations. Brussels, BE: European Commission. [https://joinup.ec.europa.eu/sites/default/files/document/2013-02/D7.1.3%20-%20Study%20on%20persistent%20URIs.pdf](https://joinup.ec.europa.eu/sites/default/files/document/2013-02/D7.1.3%20-%20Study%20on%20persistent%20URIs.pdf).

<a name="berners-lee-1998"></a>Berners-Lee, Tim. 1998. ‘Cool URIs Don’t Change’. W3C Style. 1998. [https://www.w3.org/Provider/Style/URI](https://www.w3.org/Provider/Style/URI).

<a name="ca-digital-library-2020a"></a>California Digital Library. 2020a. ‘Archival Resource Key (ARK) Identifiers’. N2T (Name to Thing). 2020. [http://n2t.net/e/ark\_ids.html](http://n2t.net/e/ark_ids.html).

<a name="ca-digital-library-2020b"></a>———. 2020b. ‘Nice Opaque Identifiers (NOID)’. N2T (Name to Thing). 2020. [https://n2t.net/e/noid.html](https://n2t.net/e/noid.html).

<a name="chief-technology-officer-council-2009"></a>Chief Technology Officer Council. 2009. ‘Designing URI Sets for the UK Public Sector: A Report from the Public Sector Information Domain of the CTO Council’s Cross-Government Enterprise Architecture’. United Kingdom Chief Technology Officer Council. [https://assets.publishing.service.gov.uk/government/uploads/system/uploads/attachment\_data/file/60975/designing-URI-sets-uk-public-sector.pdf](https://assets.publishing.service.gov.uk/government/uploads/system/uploads/attachment_data/file/60975/designing-URI-sets-uk-public-sector.pdf).

<a name="corp-national-research-initiatives-2020"></a>Corporation for National Research Initiatives. 2020. ‘Handle Registry’. Handle. 2020. [https://www.handle.net/](https://www.handle.net/).

<a name="henderson-et-al-2017"></a>Henderson, Deborah, Susan Earley, and Laura Sebastian-Coleman, eds. 2017. *DAMA-DMBOK: Data Management Body of Knowledge*. 2nd ed. Basking Ridge, NJ: Technics Publications.

<a name="doi-2020"></a>International DOI Foundation. 2020. ‘DOI’. DOI. 2020. [https://www.doi.org/](https://www.doi.org/).

<a name="icann-2020"></a>Internet Corporation for Assigned Names and Numbers (ICANN). 2020. ‘Internet Assigned Numbers Authority (IANA)’. IANA. 2020. [https://www.iana.org/](https://www.iana.org/).

<a name="koster-2020"></a>Koster, Lukas. 2020. ‘Persistent Identifiers for Heritage Objects’. *The Code4Lib Journal*, no. 47 (February). [https://journal.code4lib.org/articles/14978](https://journal.code4lib.org/articles/14978).

<a name="uuid-generator-2020"></a>‘Online UUID Generator Tool’. 2020. UUID Generator. 2020. [https://www.uuidgenerator.net/api](https://www.uuidgenerator.net/api).

<a name="sauermann-cyganiak-2008"></a>Sauermann, Leo, and Richard Cyganiak. 2008. ‘Cool URIs for the Semantic Web’. W3C Interest Group Note. 2008. [https://www.w3.org/TR/cooluris/](https://www.w3.org/TR/cooluris/).

<a name="w3c-2014"></a>W3C. 2014. ‘URI Design and Management for Persistence’. Data on the Web Best Practices. 2014. [https://www.w3.org/2013/dwbp/wiki/URI\_Design\_and\_Management\_for\_Persistence](https://www.w3.org/2013/dwbp/wiki/URI_Design_and_Management_for_Persistence).

---

**Notes**

<a name="note-1"></a>1.  Actors are understood here as people, companies, groups, institutions and other acting agents.

<a name="note-2"></a>2.  This is the approach CHIN will take for the moment, although further research on ontology URIs will be conducted in the coming months, and a dedicated template might be devised as a result of this research.

<a name="note-3"></a>3.  Once the model has been expanded and more use cases emerge, a hierarchy of classes might be established for this purpose.
