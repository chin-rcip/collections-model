---
layout: page
language: en
title: Birth and Death of a Person
permalink: /en/target-model/current/birth-and-death-of-a-person
other_link: /fr/modele-cible/actuel/naissance-et-mort-dune-personne
sidebar: tm22
date: 2022-03-31
description: The Actors Target Model Specification semantically models actors in a heritage context. Patterns most relevant to actors' lives are presented along with diagrams and examples illustrating them, as well as a record and explanation of relevant decisions that were made when developing said patterns. This is a theoretical documentation that has never been tested or implemented.
---

Version 2.2 ([Previous versions](/collections-model/en/versions))

## At Glance

This pattern can be used to represent the information pertaining to the lifespan of a person (birth and death). It includes: 

* The date and location of the birth of a person;
* The biological parents of a person; 
* The date and location of the death of a person; 
* The location of the remains of a person (burial place). 

It pertains specifically to the vital information of persons and not to their relationships, or to the vital information of non-human agents (e.g. animals or groups) or non-living humans (e.g. human remains). As such, it does not include: 

* The adoptive parents of a person (use the [Relationship](/collections-model/en/target-model/current/relationship) pattern instead); 
* The relationship of a person to their parents (i.e. this pattern describes the biological parenthood rather than the social bond between the person and their parents) (use the [Relationship](/collections-model/en/target-model/current/relationship) pattern instead);
* The belonging of a person to a family (use the [Family Belonging](/collections-model/en/target-model/current/family-belonging) pattern instead);
* The cause of a person’s death;
* The date and location of the birth and death of a non-human agent such as an animal or thing; 
* The location of the remains of a non-human agent such as an animal or thing (burial place).

## Introduction and Context

### Theoretical Background

The recording of vital statistics pertaining to the birth and death of people dates back to Antiquity when such information was used by states to determine taxation and estimate military manpower (Brumberg et al. 2012, 407). It is a statistically and culturally important part of heritage data that is often used to situate actors within larger societal and demographic trends, and is a key element of genealogy and family history research (Library and Archives Canada 2020). 

Such data is useful to visualize trends in family composition, genealogical lineage, localization of actors in space and time, or national belonging (since polities can change over time, for example Yousuf Karsh was born in modern-day Turkey at the time of the Ottoman Empire (Editors of Encyclopædia Britannica n.d.)). Burial locations, in particular, can be indicative of social mores and practices surrounding death, and are increasingly recorded by players interested in genealogy or heritage data such as [Wikidata](https://www.wikidata.org/wiki/Property:P119) (Wikidata 2021) or genealogical institutes, for example [Family Search](https://www.familysearch.org/wiki/en/Canada_Cemeteries) (FamilySearch 2020).

### Statement of Need

It is important to keep in mind that vital information is often inconsistently or problematically recorded, and census data is heavily framed by census methodology so that any use of vital information must be heavily pondered (Hamilton 2008). For example, colonial records of Indigenous ancestry are notoriously flawed and have often either not recorded Indigenous actors, or done so using colonial methods of collecting, recording, and archiving that do not encompass the traditions and concepts deemed relevant to their ancestry by Indigenous Peoples (Devlin & Cuggy 2017; Royal British Columbia Museum 2018). Such uses of vital records should be done critically and cautiously. 

Dates and places pertaining to births and deaths are not only statistically meaningful, but also crucial to the disambiguation of actors (i.e. two different people might have the same name by happenstance, or a single person might be associated to several names or spellings of a name) as they can be used to confirm someone’s identity (OCLC 2019, 4). 

Because such information is commonly used by heritage institutions as well as relied upon for disambiguation purposes, it is likely to be among the most widely documented. This means that such data will predictably be subject to exchange and mobilization by several providers. Thus, interoperability with other relevant models is of importance in the development of these patterns.

This indicates a need for an identification of who was born when, where, and to whom (biological mother and father), when and where they died, as well as where their remains are located. 

## Description of the Pattern

This pattern is based on a modelling approach in which an event embodies the "beginning" and "ending" of the entity (in this case an instance of `E21_Person`). 

The birth of a person is modelled as follows:

* An instance of `E21_Person` is linked to an instance of `E67_Birth` by the property `P98_brought_into_life`;
* The instance of `E67_Birth` is first linked to another instance of `E21_Person` representing the person’s biological mother using the property `P96_by_mother` which is linked to an instance of both `E41_Appellation` and `E33_Linguistic_Object` by the property `P1_is_identified_by`. From this instance, the literal value of the [Mother Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#mother-appellation) is qualified through the property `P190_has_symbolic_content`;
* Similarly, the same instance of `E67_Birth` is linked to another instance of `E21_Person` representing the person’s biological father using the property `P97_from_father` which is linked to an instance of both `E41_Appellation` and `E33_Linguistic_Object` by the property `P1_is_identified_by`. From this instance, the literal value of the [Father Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#father-appellation) is qualified through the property `P190_has_symbolic_content`;
* The place where the birth occurred is indicated by linking the instance of `E67_Birth` to the [Birth Place](/collections-model/en/semantic-paths-specification/current/entry-nodes#birth-place) value (an instance of `E53_Place`) through the property `P7_took_place_at`;
* The time when the birth occurred is indicated using the [Temporal Bounds](/collections-model/en/target-model/current/temporal-bounds) pattern linked to the instance of `E67_Birth` through the property `P4_has_time-span` with values extracted from the [Birth Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#birth-date-begin), [Birth Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#birth-date-begin-qualifier), [Birth Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#birth-date-end), and [Birth Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#birth-date-end-qualifier) entry nodes. 

The death of a person is modelled as follows: 

* An instance of `E21_Person` is linked to an instance of `E69_Death` by the property `P100_was_death_of`;
* The place where the death occurred is indicated by linking the instance of `E69_Death` to the [Death Place](/collections-model/en/semantic-paths-specification/current/entry-nodes#death-place) value (an instance of `E53_Place`) through the property `P7_took_place_at`;
* To capture the moving of the deceased’s body from their last location to their final disposition place, an instance of `E9_Move` is linked to the instance of `E53_Place` representing the place where the death occurred by the property `P27_moved_from`, as well as linked by the property `P26_moved_to` to the [Final Disposition Place](/collections-model/en/semantic-paths-specification/current/entry-nodes#final-disposition-place) value which is qualified by an instance of `E55_Type` (a specified qualifier node) labelled "Burial Place" using the property `P2_has_type`;
* To indicate that the death of the person necessarily occurred *before* the moving of their deceased body, the instance of `E69_Death` is also linked to the instance of `E9_Move` by using the CRMarcheo property `AP28_occurs_before`;
* The time when the death occurred is indicated using the [Temporal Bounds](/collections-model/en/target-model/current/temporal-bounds) pattern linked to the instance of `E69_Death` through the property `P4_has_time-span` with values extracted from the [Death Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#death-date-begin), [Death Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#death-date-begin-qualifier), [Death Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#death-date-end), and [Death Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#death-date-end-qualifier) entry nodes. 

## Diagram

<a name="039_Pattern_BirthDeath_p"></a>039_Pattern_BirthDeath_p

<div class="mxgraph" style="max-width:100%;border:1px solid #cccccc;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;target&quot;:&quot;blank&quot;,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom layers lightbox&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;xml&quot;:&quot;&lt;mxfile modified=\&quot;2023-03-15T17:12:29.208Z\&quot; host=\&quot;app.diagrams.net\&quot; agent=\&quot;5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) draw.io/20.3.0 Chrome/104.0.5112.114 Electron/20.1.3 Safari/537.36\&quot; etag=\&quot;JHDvSAnLLBQhxXYtatHT\&quot; version=\&quot;20.3.0\&quot;&gt;&lt;diagram id=\&quot;u8ZAdGQqbO1eaJdBns1q\&quot; name=\&quot;Page-1\&quot;&gt;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&lt;/diagram&gt;&lt;/mxfile&gt;&quot;}"></div>

## Examples

### Example 1

Yousuf Karsh (`P190_has_symbolic_content`, Actor Appellation) was born on the 23 of December 1908 (`P82a_begin_of_the_begin`, Birth Date Begin; `P82b_end_of_the_end`, Birth Date End) in Mardin (Ottoman Empire) (`P7_took_place_at`, Birth Place) to Bahiyah Nakash (`P190_has_symbolic_content`, Mother Appellation) and Massih Karsh (`P190_has_symbolic_content`, Father Appellation). He died on the 13th of July 2002 (`P82a_begin_of_the_begin`, Death Date Begin; `P82b_end_of_the_end`, Death Date End) in Boston (MA, United States) (`P7_took_place_at`, Death Place) and is buried at Notre-Dame Cemetery in Ottawa (ON, Canada) (`P26_moved_to`, Final Disposition Place; `P2_has_type`, "Burial Place") (Editors of Encyclopædia Britannica n.d).

<div id="0001_100_birth-death" class="example"></div>

### Example 2

Emily Carr (`P190_has_symbolic_content`, Actor Appellation) was born on the 13th of December 1871 (`P82a_begin_of_the_begin`, Birth Date Begin; `P82b_end_of_the_end`, Birth Date End) in Victoria (BC, Canada) (`P7_took_place_at`, Birth Place) to Emily (Saunders) Carr (`P190_has_symbolic_content`, Mother Appellation) and Richard Carr (`P190_has_symbolic_content`, Father Appellation). She died on the 2nd of March 1945 (`P82a_begin_of_the_begin`, Death Date Begin; `P82b_end_of_the_end`, Death Date End), also in Victoria (BC, Canada) (`P7_took_place_at`, Death Place), and was buried at Ross Bay Cemetery (BC, Canada) (`P26_moved_to`, Final Disposition Place; `P2_has_type`, "Burial Place") (Baldissera 2015, 4).

<div id="0001_106_birth-death" class="example"></div>

### Example 3

David Altmejd (`P190_has_symbolic_content`, Actor Appellation) was born in 1974 (`P82a_begin_of_the_begin`, Birth Date Begin; `P82b_end_of_the_end`, Birth Date End) in Montreal (QC, Canada) (`P7_took_place_at`, Birth Place) (Musée d’art contemporain de Montréal 2015). 

<div id="0001_109_birth" class="example"></div>

## Related Documentation

### External Models

* Linked.art: [Birth and Death/Formation and Dissolution](https://linked.art/model/actor/#birth-and-death-formation-and-dissolution)
* SARI: [Person Reference Data Model – Person Existence](https://docs.swissartresearch.net/et/persons/#existence)

### Entry Nodes

* [Birth Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#birth-date-begin) \| Checklist
* [Birth Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#birth-date-begin-qualifier) \| Checklist
* [Birth Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#birth-date-end) \| Checklist
* [Birth Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#birth-date-end-qualifier) \| Checklist
* [Birth Place](/collections-model/en/semantic-paths-specification/current/entry-nodes#birth-place) \| Checklist
* [Death Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#death-date-begin) \| Checklist
* [Death Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#death-date-begin-qualifier) \| Checklist
* [Death Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#death-date-end) \| Checklist
* [Death Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#death-date-end-qualifier) \| Checklist
* [Death Place](/collections-model/en/semantic-paths-specification/current/entry-nodes#death-place) \| Checklist
* [Father Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#father-appellation) \| Checklist
* [Final Disposition Place](/collections-model/en/semantic-paths-specification/current/entry-nodes#final-disposition-place) \| Checklist
* [Mother Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#mother-appellation) \| Checklist

### CIDOC CRM Entities

* `AP28_occurs_before (occurs_after)`
* `E9_Move` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E9)]
* `E21_Person` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E21)]
* `E33_Linguistic_Object` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E33)]
* `E41_Appellation` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E41)]
* `E52_Time-Span` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E52)]
* `E53_Place` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E53)]
* `E55_Type` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E55)]
* `E67_Birth` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E67)]
* `E69_Death` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E69)]
* `P1_is_identified_by (identifies)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P1)]
* `P2_has_type (is_type_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P2)]
* `P4_has_time-span (is_time-span_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P4)]
* `P7_took_place_at (witnessed)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P7)]
* `P25_moved (moved_by)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P25)]
* `P26_moved_to (was_destination_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P26)]
* `P27_moved_from (was_origin_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P27)]
* `P79_beginning_is_qualified_by` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P79)]
* `P80_end_is_qualified_by` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P80)]
* `P82a_begin_of_the_begin`
* `P82b_end_of_the_end`
* `P96_by_mother (gave_birth)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P96)]
* `P97_from_father (was_father_for)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P97)]
* `P98_brought_into_life (was_born)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P98)]
* `P100_was_death_of (died_in)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P100)]
* `P190_has_symbolic_content` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P190)]

## Discussion

### Rationale

The biological filiation (i.e. biologically being the mother and father of a person) and the parentship (i.e. the social relationship the person has to their parents and vice-versa) are considered distinct in the context of the DOPHEDA model so that each type of parental filiation can be precisely and accurately recorded. The recording of parental and family interactions is modelled using the [Relationship] (/collections-model/en/target-model/current/relationship) pattern. As such, the biological lineage modelling addressed in this pattern should be employed when the goal is to document genealogical information. 

The modelling of the final disposition place, and especially the use of an instance of `E9_Move`, is ontologically disputable. Representing the post-death move of the person (`E21_Person`) to their grave through an instance of `E9_Move` (move event) is the simplest modelling solution to the representation of the intentional moving of human remains. However, it is conceptually problematic since the remains of the dead person cannot technically be associated with an instance of `E21_Person`. The logic of CIDOC CRM dictates the creation of an instance of `E20_Biological_Object` to replace the instance of `E21_Person` through an instance of `E81_Transformation`. Otherwise, the pattern (as it currently stands) would indicate that the person was moved and buried alive. However, this longer and more precise modelling is highly complex and implies the creation of nodes that considerably weigh down the model, significantly complexify queries, and unnecessarily burden users. Because there are very few records of people being buried alive (especially as such) in heritage collections, it seems preferable to compromise on semantic preciseness and adopt a simpler solution, assuming actors will be buried while dead (see [Issue #72](https://github.com/chin-rcip/collections-model/issues/72)).

### Related GitHub Issues

* [Issue #16 "Do we need a family relationship pattern? And what to do with parents?"](https://github.com/chin-rcip/collections-model/issues/16)
* [Issue #72 "How to model Resting Place?"](https://github.com/chin-rcip/collections-model/issues/72)

### Edge Cases

#### Example 1 {#edge-cases-example-1}

The Unknown Soldier died in France as a soldier during the First World War. Their death occurred between the 3rd of October, 1914 (when the first Canadian contingent sailed for Europe) and the 11th of November, 1918 (when Canadians’ direct involvement in the fight ended), though the war ended officially with the Treaty of Versailles on the 28th of June, 1919. They were buried at the Cabaret-Rouge War Cemetery near Vimy (France) before their remains were moved in a commemorative sarcophagus in Ottawa (ON, Canada). In the DOPHEDA model, their move from their place of death to their burial place would not represent their passage in Cabaret-Rouge and only indicate a move from France (where they died between 1914 and 1918) to Canada in 2000 (Foot 2018). 

#### Example 2 {#edge-cases-example-2}

Ramses II died around 1213 BCE according to Egyptian chronology (Hornung et al. 2006, 476-478). His body was embalmed and deposited in tomb KV7 in the Valley of Kings (modern-day Egypt), but was soon moved and transferred into other tombs by Egyptian priests to protect it from looting. The body was finally uncovered in tomb TT320 in 1881 (Wikipedia 2021).

In this example, the mummy transferred, or at least discovered by archæologists, should not be considered a person (`E21_Person`) but rather a biological object (`E20_Biological_Object`) which can be moved. At the moment, this kind of transformation cannot be documented as part of the Birth and Death of a Person pattern.

#### Example 3 {#edge-cases-example-3}

Maud Kathleen Lewis was born in her South Ohio, NS (Birth Place) childhood home to John Dowley (Father Appellation) and Agnes Dowley (Mother Appellation) (Art Gallery of Nova Scotia n.d.). In addition to documenting the municipality where she was born, an institution might want to record that "She was born in her childhood home". The latter could be considered a Curatorial Note about Maud Kathleen Lewis. The same would apply to the death of a person happening in their childhood home.

## Bibliography

Art Gallery of Nova Scotia. "Maud Lewis." Art Gallery of Nova Scotia. n.d. [https://artgalleryofnovascotia.ca/maud-lewis](https://artgalleryofnovascotia.ca/maud-lewis).

Baldissera, Lisa. *Emily Carr: Life & Work*. Canadian Online Art Book Project. Toronto, CA-ON: Art Canada Institute, 2015. [https://www.aci-iac.ca/art-books/emily-carr/](https://www.aci-iac.ca/art-books/emily-carr/). 

Brumberg, H. L., D. Dozor, and S. G. Golombek. "History of the Birth Certificate: From Inception to the Future of Electronic Data." *Journal of Perinatology* 32, no. 6 (June 2012): 407–411. [https://doi.org/10.1038/jp.2012.3](https://doi.org/10.1038/jp.2012.3).

Devlin, Stacy, and Emily Cuggy. "Settler Records, Indigenous Histories: Challenges in Indigenous Genealogical Research." *Active History* (blog). December 7, 2017. [https://activehistory.ca/2017/12/settler-records-indigenous-histories-challenges-in-indigenous-genealogical-research/](https://activehistory.ca/2017/12/settler-records-indigenous-histories-challenges-in-indigenous-genealogical-research/).

Doerr, Martin, and Christian Emil Ore, eds. *Definition of the CIDOC Conceptual Reference Model*. CIDOC CRM Documentations, 7.0.1. Paris, FR-IDF: International Council of Museums (ICOM), 2020. [http://www.cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.0.1_%2018-10-2020.pdf](http://www.cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.0.1_%2018-10-2020.pdf).

Editors of Encyclopædia Britannica. "Yousuf Karsh." *Encyclopædia Britannica*. London, UK-LDN: Encyclopædia Britannica, n.d. [https://www.britannica.com/biography/Yousuf-Karsh](https://www.britannica.com/biography/Yousuf-Karsh).

FamilySearch. "Canada Cemeteries." *FamilySearch Wiki*. April 7, 2020. [https://www.familysearch.org/wiki/en/Canada_Cemeteries](https://www.familysearch.org/wiki/en/Canada_Cemeteries).

Foot, Richard. "Canada’s Unknown Soldier." *The Canadian Encyclopedia*. Reprint, Toronto, CA-ON: Historica Canada, October 3, 2018 [2014]. [https://www.thecanadianencyclopedia.ca/en/article/unknown-soldier](https://www.thecanadianencyclopedia.ca/en/article/unknown-soldier).

Hamilton, Michelle. "'Anyone Not on the List Might as Well Be Dead': Aboriginal Peoples and the Censuses of Canada, 1851–1916." *Journal of the Canadian Historical Association/Revue de la Société historique du Canada* 18, no. 1 (2007): 57–79. [https://doi.org/10.7202/018254ar](https://doi.org/10.7202/018254ar).

Hornung, Erik, Rolf Krauss, and David A. Warburton, eds. *Ancient Egyptian Chronology*. Leiden, NL-ZH; Boston, US-MA: Brill, 2006.

Library and Archives Canada. "Births, Marriages and Deaths Recorded in Canada." *Library and Archives Canada*. September 9, 2020. [https://www.bac-lac.gc.ca/eng/discover/vital-statistics-births-marriages-deaths/births-marriages-deaths-recorded/Pages/births-marriages-deaths-recorded.aspx](https://www.bac-lac.gc.ca/eng/discover/vital-statistics-births-marriages-deaths/births-marriages-deaths-recorded/Pages/births-marriages-deaths-recorded.aspx).

Linked.art. *Linked Art Data Model*. Linked.art, 2021. [https://linked.art/model/index.html](https://linked.art/model/index.html).

Musée d’art contemporain de Montréal (MACM). *David Altmejd*. MACM, 2015. [http://staging.macm.org/en/exhibitions/david-altmejd/](http://staging.macm.org/en/exhibitions/david-altmejd/).

OCLC. *Virtual International Authority File Guidelines*. Reprint, Dublin, US-OH: OCLC, 2019 [2015]. [https://www.oclc.org/content/dam/oclc/viaf/VIAF%20Guidelines.pdf](https://www.oclc.org/content/dam/oclc/viaf/VIAF%20Guidelines.pdf).

Royal British Columbia Museum. *Resources for First Nations Genealogical Research at the BC Archives*. Royal British Columbia Museum, November 2018. [https://royalbcmuseum.bc.ca/sites/default/files/sites/default/files/images/resources_for_first_nations_genealogical_research_at_the_bcarchives_2018.pdf](https://royalbcmuseum.bc.ca/sites/default/files/sites/default/files/images/resources_for_first_nations_genealogical_research_at_the_bcarchives_2018.pdf).

Shadbolt, Doris. "Emily Carr." *The Canadian Encyclopedia*. Reprint, Toronto, CA-ON: Historica Canada, August 28, 2015 [2013]. [https://www.thecanadianencyclopedia.ca/en/article/emily-carr](https://royalbcmuseum.bc.ca/sites/default/files/sites/default/files/images/resources_for_first_nations_genealogical_research_at_the_bcarchives_2018.pdf).

Skidmore, Colleen. "Yousuf Karsh." *The Canadian Encyclopedia*. Reprint, Toronto, CA-ON: Historica Canada, March 4, 2015 [2010]. [https://www.thecanadianencyclopedia.ca/en/article/yousuf-karsh](https://www.thecanadianencyclopedia.ca/en/article/yousuf-karsh).

Wikidata. "Place of Burial (P119)." *Wikidata*. April 9, 2021. [https://www.wikidata.org/wiki/Property:P119](https://www.wikidata.org/wiki/Property:P119).

Wikipedia. "Ramesses II." *Wikipedia*. San Francisco, US-CA: Wikipedia, 2021. [https://en.wikipedia.org/wiki/Ramesses_II](https://en.wikipedia.org/wiki/Ramesses_II).

