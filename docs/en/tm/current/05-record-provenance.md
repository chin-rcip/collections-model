---
layout: page
language: en
title: Record Provenance
permalink: /en/target-model/current/record-provenance
other_link: /fr/modele-cible/actuel/provenance-de-lenregistrement
sidebar: tm22
date: 2022-03-31
description: The Actors Target Model Specification semantically models actors in a heritage context. Patterns most relevant to actors' lives are presented along with diagrams and examples illustrating them, as well as a record and explanation of relevant decisions that were made when developing said patterns. This is a theoretical documentation that has never been tested or implemented.
---

Version 2.2 ([Previous versions](/collections-model/en/versions))

## At Glance

This pattern can be used to represent the information pertaining to the documentation of a record by an organization or a person responsible for either its creation or its latest update. It includes: 

* The record contributor appellation;
* The record creation date·s (including the latest updates).

This pattern pertains specifically to the documentation of the record itself, and not to the dataset it comes from, or to the contents of its data. Thus, it should not be used to record: 

* Where an artefact comes from;
* Where the original data is hosted;
* The primary source of information (e.g. books, archives, articles, etc.);
* The dataset provider appellation (see the [Dataset Provenance](/collections-model/en/target-model/current/dataset-provenance) pattern);
* The dataset provision dates and updates (see the [Dataset Provenance](/collections-model/en/target-model/current/dataset-provenance) pattern).

## Introduction and Context

### Theoretical Background

The term "record", originating from the legal domain as the oral recollection of court proceedings, evolved to encompass evidence of, information about, and representations of activities, transactions, or events and documents related to something (Duranti & Franks 2015). The term was then used in the computer sciences where it represents a grouping of data into a structural unit centered around an entity of interest (Henderson 2009). Originally, in a flat file database model, the record is associated with the row or column of a table. It contains data about an entity that has been structured into fields. Such a structure is useful for adding, updating, retrieving, manipulating, and reporting on data, and has been widely used in different domains, including the heritage sector (Bruseker et al. 2021). 

Because of its graph-like structure, Linked Open Data does not rely on records as a unit of structure. While until recently records were defined by the structure of the flat file database (the row or column), it is no longer the case with graphs. In order to account for the existence of the record, its structure must now be conceptually represented rather than structurally. This conceptual representation relies on the identification of the group of nodes that originally constituted the record, or on the creation of a node that conceptually acts as the record to enable the documentation of related information (centering it on an entity of interest which in an actors-focused project is most often the actor).

### Statement of Need

The goal of the DOPHEDA project is to aggregate–in a single knowledge graph​​–data from heritage institutions in Canada as well as from other relevant sources that might inform or illuminate these foundational datasets. The reasons for documenting the provenance of such datasets is detailed in the [Dataset Provenance](/collections-model/en/target-model/current/dataset-provenance) pattern. For reasons described in that pattern, CHIN has elected to document the provenance and temporal bounds information from the provider by applying it to the entire submitted dataset rather than to each record submitted (e.g. tabular ensembles of information).

However, a more granular description of the provenance and temporal bounds information is occasionally relevant. Traditionally, information in institutions has been structured at the record level where, consequently, most updates are made by providers of data (Bruseker et al. 2021). Some information such as update dates or sources are thus linked to specific records.

In order to keep track of information related specifically to records, a unit of information (representing the record itself) must be linked to the entity of interest. This unit of information, represented in the diagram below, can document the creator of the record as well as its temporal bounds. 

## Description of the Pattern

As mentioned above, the Target Model Specification applies named graphs at the dataset level (Bruseker et al. 2021) and, as a result, represents records using a conceptual entity. 

This is done using an instance "record" of `E73_Information_Object` linked to an instance of `E39_Actor` through the property `P67_refers_to`. This instance of `E73_Information_Object` is also linked to an instance of `E55_Type` (a specified qualifier node) labelled "Record" through the property `P2_has_type`. This same instance of `E73_Information_Object` is also linked by the property `P94_created` to an instance of `E65_Creation` which in turn points to the record contributor (another instance of `E39_Actor`) through the property `P14_carried_out_by`. This second instance of `E39_Actor` is linked by the property `P1_is_identified_by` to an instance of both `E41_Appellation` and `E33_Linguistic_Object` which in turn is linked to the literal value of the [Record Contributor Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#record-contributor-appellation) through the property `P190_has_symbolic_content`.

The time at which the contribution was made is indicated using the [Temporal Bounds](/collections-model/en/target-model/current/temporal-bounds) pattern linked to the instance of `E65_Creation` through the property `P4_has_time-span` with values extracted from the [Record Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#record-date-begin) and [Record Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#record-date-end) entry nodes.

As CHIN has not yet determined how to document updates of information, the creation date currently stands for the last modified version of the record.

## Diagram

<a name="015a_Pattern_RecordProvenance_Actor_p"></a>015a_Pattern_RecordProvenance_Actor_p

<iframe frameborder="0" style="width:100%;height:400px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=015a_Pattern_RecordProvenance_Actor_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1KGXyt67vO4KcsuWzHjqOo2APEKs1sQ9N%26export%3Ddownload"></iframe>

<a name="015b_Pattern_RecordContributor_Artefact_p"></a>015b_Pattern_RecordContributor_Artefact_p

<iframe frameborder="0" style="width:100%;height:400px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=015b_Pattern_RecordContributor_Artefact_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1GSyyT1mAf2clR3okusE938in91NPUPEt%26export%3Ddownload"></iframe>

## Examples

[Artists in Canada](https://app.pch.gc.ca/application/aac-aic/description-about.app?lang=en) is a bilingual union list that identifies the location of documentation files on artists mentioned in the records of institutions located in Canada, who themselves submit their information (National Gallery of Canada 2019a; National Gallery of Canada 2019b). In this list, the record about Yousuf Karsh indicates that the information: 

* Has been contributed by the National Gallery of Canada Library and Archives/Canadian Museum of Contemporary Photography (`P190_has_symbolic_content`, Record Contributor Appellation); 
* Was created on 1985-03-13 (`P82a_begin_of_the_begin`, Record Date Begin); 
* Was last updated on 2011-06-03 (`P82b_end_of_the_end`, Record Date End) (Canadian Heritage, Government of Canada 2011).

<div id="0001_100_record-provenance" class="example"></div>

## Related Documentation

### External Models

* CIDOC CRM: [Digital Provenance Ontology](http://www.cidoc-crm.org/Resources/a-digital-provenance-ontology-0)
* Nomisma.org: [VoID RDF](http://nomisma.org/documentation/contribute)

### Entry Nodes

* [Record Contributor Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#record-contributor-appellation) \| Checklist
* [Record Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#record-date-begin) \| Checklist
* [Record Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#record-date-end) \| Checklist

### CIDOC CRM Entities

* `E33_Linguistic_Object` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E33)]
* `E39_Actor` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E39)]
* `E41_Appellation` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E41)]
* `E52_Time-Span` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E52)]
* `E55_Type` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E55)]
* `E65_Creation` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E65)]
* `E73_Information_Object` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E73)]
* `P1_is_identified_by (identifies)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P1)]
* `P2_has_type (is_type_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P2)]
* `P4_has_time-span (is_time-span_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P4)]
* `P14_carried_out_by (performed)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P14)]
* `P67_refers_to (is_referred_to_by)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P67)]
* `P82a_begin_of_the_begin`
* `P82b_end_of_the_end`
* `P94_created (was_created_by)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P94)]
* `P190_has_symbolic_content` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P190)]

## Discussion

### Rationale

The reasons for developing a provenance data structure revolving around datasets rather than records is documented in the [Dataset Provenance](/collections-model/en/target-model/current/dataset-provenance) pattern. However, the high reliance of providers on the record structure results in the need for a dedicated pattern. The difference between a tabular database and a semantic model is that the original structure of the record does not endure in the knowledge graph: rather, it can be modelled as a semantic and conceptual element, as well as symbolized by the use of an instance of `E73_Information_Object` regarding the entity of interest, as presented above.

### Limitations

Because the record is a conceptual element regarding the entity of interest (an instance of `E39_Actor` in this case) and because it is not modelled as a named graph, it cannot be a set of triples concerning a specific entity. This induces several limitations:

* It complexifies the querying of triples belonging specifically to an entity of interest because every triple pertaining to this entity cannot be retrieved simply by using the URI of the record (instance of `E73_Information_Object`) in a `GRAPH` clause, unlike datasets for which this is possible (see the [Dataset Provenance](/collections-model/en/target-model/current/dataset-provenance) pattern). To retrieve these triples, a more complex query must be written which includes a series of connected triple patterns as well as other specific conditions. For example:

```

prefix crm:   <http://www.cidoc-crm.org/cidoc-crm/> 

prefix g:     <https://dopheda.info/graph/> 

prefix actor: <https://dopheda.info/e39/>





CONSTRUCT {

    actor:163 ?p1 ?o1.

    ?o1 ?p2 ?o2.

    ?o2 ?p3 ?o3.

    ?o3 ?p4 ?o4.

    ?o4 ?p5 ?o5.

    ?o5 ?p6 ?o6. #the number of triples patterns depends on the pattern with the deepest hierarchy.

  }

WHERE {

         actor:163 ?p1 ?o1.

         OPTIONAL {?o1 ?p2 ?o2. FILTER (!regex(str(?o1),"/e39/") || (regex(str(?o1),"/e39/") && (?p2=rdf:type || ?p2=rdfs:label)))

      OPTIONAL {?o2 ?p3 ?o3. FILTER (!regex(str(?o2),"/e39/") || (regex(str(?o2),"/e39/") && (?p3=rdf:type || ?p3=rdfs:label)))

         OPTIONAL {?o3 ?p4 ?o4. FILTER (!regex(str(?o3),"/e39/") || (regex(str(?o3),"/e39/") && (?p4=rdf:type || ?p4=rdfs:label)))

            OPTIONAL {?o4 ?p5 ?o5.

                      FILTER (!regex(str(?o4),"/e39/") || (regex(str(?o4),"/e39/") && (?p5=rdf:type || ?p5=rdfs:label)))

                      OPTIONAL {?o5 ?p6 ?o6.

                      FILTER (!regex(str(?o5),"/e39/") || (regex(str(?o5),"/e39/") && (?p6=rdf:type || ?p6=rdfs:label)))

                     } } } } } 

}

```

* This complexifies the updating of triples belonging to a particular entity of interest and increases the potential for errors. As with the example above, retrieving what information is to be updated and what the impacts of such updates are is a precise and complex process involving intricate SPARQL queries. Therefore, it is more straightforward to update the entire dataset rather than specific records, even when little information has changed (Gearson et al. 2013).

At the moment, no roles have been specified for the actor·s involved in the creation or update of the record. In the case where multiple actors have been responsible for the creation or update of the record (e.g. with different roles such as writer or researcher), it is not possible to identify and document such roles, and all actors are simply linked to the creation or update event without further qualification. If such detailed information becomes necessary to document, a review of the pattern might become imperative.

### Related GitHub Issues

* [Issue #14 "We need to manage the updates of records (and Named Graphs?)"](https://github.com/chin-rcip/collections-model/issues/14)
* [Issue #34 "Should Cataloguers be documented in the Record pattern?"](https://github.com/chin-rcip/collections-model/issues/34)
* [Issue #45 "Named Graphs: Record vs. Dataset"](https://github.com/chin-rcip/collections-model/issues/45)

### Edge Cases

Some heritage institutions may have entities of interest other than actors or objects. For example, some institutions might focus on places and primarily describe their locations, their appellations, their descriptions, etc., so that records would be focused on places rather than on actors or objects. Documenting such cases would necessitate the acceptance of other sub-classes of `E1_CRM_Entity` to be linked to instances of `E73_Information_Object` beyond instances of `E39_Actor` and `E22_Human-Made_Object`.

Recently created records will most likely have specific dates, but older ones created when collections management relied on paperwork rather than databases might have blurrier dates referring to periods of the institution’s history, such as "Under the curatorship of Curator X" or "Before the museum was instituted". It is also debatable whether a record can end since, as long as there is a date, there is still a documented record. In addition, the scope of what a contributor is could be blurry and include data that CHIN could retrieve for enrichment purposes (e.g. Wikidata could have a Record Contributor Appellation).

## Bibliography

Bruseker, George, Trang Dang, Philippe Michon, and Stephen Hart. *Cultural Heritage Named Graph Usage Survey Report (Part 1)*. DOPHEDA Technical Reports. Ottawa, CA-ON: Canadian Heritage Information Network (CHIN), 2021. [/collections-model/en/technical-reports/current/named-graph-survey-report-1](/collections-model/en/technical-reports/current/named-graph-survey-report-1).

Canadian Heritage, Government of Canada. "Karsh, Yousuf." *Artists in Canada*. Ottawa, CA-ON: Government of Canada, 2011. [https://app.pch.gc.ca/application/aac-aic/artiste_detailler_bas-artist_detail_bas.app?lang=en&rID=8494](https://app.pch.gc.ca/application/aac-aic/artiste_detailler_bas-artist_detail_bas.app?lang=en&rID=8494).

Duranti, Luciana, and Patricia C. Franks, eds. "Record·s." *Encyclopedia of Archival Science*. Lanham, US-MD; London, UK-LDN: Rowman & Littlefield, 2015: 315-319.

Gearson, Paula, Alexandre Passant, and Axel Polleres. "SPARQL 1.1 Update." W3C Recommendation. March 21, 2013. [https://www.w3.org/TR/sparql11-update/](https://www.w3.org/TR/sparql11-update/).

Henderson, Harry. "Data." *Encyclopedia of Computer Science and Technology, Revised Edition* 128. New York, US-NY: Facts on File, Inc., 2009.

National Gallery of Canada. "Artists in Canada." Governmental. Government of Canada Website. December 12, 2019a. [https://app.pch.gc.ca/application/aac-aic/description-about.app?lang=en](https://app.pch.gc.ca/application/aac-aic/description-about.app?lang=en).

———. "Artists in Canada Copyrights." Governmental. Government of Canada Website. December 12, 2019b. [https://app.pch.gc.ca/application/aac-aic/droit_auteur-copyright.app?lang=en](https://app.pch.gc.ca/application/aac-aic/droit_auteur-copyright.app?lang=en).

