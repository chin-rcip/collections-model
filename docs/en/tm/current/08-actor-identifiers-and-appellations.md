---
layout: page
language: en
title: Actor Identifiers and Appellations
permalink: /en/target-model/current/actor-identifiers-and-appellations
other_link: /fr/modele-cible/actuel/identifiants-et-appellations-de-lactant
sidebar: tm22
date: 2022-03-31
description: The Actors Target Model Specification semantically models actors in a heritage context. Patterns most relevant to actors' lives are presented along with diagrams and examples illustrating them, as well as a record and explanation of relevant decisions that were made when developing said patterns. This is a theoretical documentation that has never been tested or implemented.
---

Version 2.2 ([Previous versions](/collections-model/en/versions))

## At Glance

This pattern can be used to represent the information pertaining to who or what a person or a group is through markers such as names, numbers, etc. It includes: 

* The unique identifiers assigned to an actor in an information system and their associated types;
* The appellations attributed to an actor including honorifics, titles, etc., and their associated types;
* The language used for appellations;
* The precedence of an appellation over others as it is determined by the provider of the dataset;
* The context and time in which an appellation is used;
* The parts that compose an appellation and their associated types.

This pattern does not cover the identifiers and appellations of objects or artefacts (see the [Artefact](/collections-model/en/target-model/current/artefact) pattern instead). 

## Introduction and Context

### Theoretical Background

Appellations are an essential component of identification and information retrieval as well as communication. This is especially so for proper nouns and alphanumeric identifiers which are harder to establish using external hierarchical vocabularies relying on labels to document common nouns. 

Appellations and identifiers play a double role:

* Denotation, which makes it possible to identify a given element according to a given context; 
* Meaning, which makes it possible to communicate something that the term conveys or is associated with (Granger 1982). 

Naming or assigning an identifier to someone is a social act that carries with it context and meaning. For example, assigning a number to a prisoner is not just an administrative process, it is also a form of dehumanization of interactions with the individual on the part of those "numbering" the prisoner. Likewise, naming someone is socially meaningful in that an appellation might carry expectations of masculinity or femininity that are context and society-dependent. Thus, the act of naming imbues the identification of the person with an identity component that goes beyond the simple need for denotation (Granger 1982).

From a historical standpoint, the perception a society has of an appellation or the meaning it ascribes to it (Lecolle, Paveau, and Reboul-Touré 2009) may evolve significantly enough that it is heavily dependent on its spatio-temporal context. For example, the name of a group is sometimes chosen to evoke something in the mind of potential stakeholders (e.g. Greenpeace evoking environmentalism through the association of the words "green" with nature, and "peace" with communion), as is the case of etymologically evocative first names (e.g. Victoria evoking victory) (Lecolle, Paveau, and Reboul-Touré 2009). Because names carry meaning specific to their social context, they cannot be considered unique to an entity they denote which indicates that several entities can be associated to the same appellation. As the context gets broader, an appellation alone is often not sufficient to precisely identify an actor. For example, within the context of a family’s homelife, the first name of a child might be enough to identify them unambiguously, but this might not be the case in the context of their classroom where a classmate might also be the bearer of the same first name. In this latter context, a combination of different other elements such as birth dates, club membership, etc. is necessary (Granger 1982).

This question of uniqueness of appellations and identifiers is even more important when their social context cannot be intuitively detected by a machine (Green and Bide 1997). In this case, URIs are the most promising mechanism to ensure that the machine can process information unambiguously. A set of principles, which ensure the development of unique and sustainable identifiers, has been developed by CHIN. An overview of these principles is presented in the [URIs Technical Report](/collections-model/en/technical-reports/current/uris-technical-report).

### Statement of Need

An actor’s primary identifier in the context of a knowledge graph is its URI. However, prior to the assignment of this URI in the context of data provision, most data providers have themselves assigned dedicated identifiers meant to uniquely identify the actor in their information system (e.g. relational database, Excel sheet, etc.) in order to support search, query, and cross-reference. Thus, a single actor can have several identifiers whose purpose is determined by the organization, division, or user they were intended for. To preserve the integrity of original data provided, identifiers must be carefully recorded, maintained, and tracked. 

Besides these identifiers, a person or a group is typically identified through their appellations which can vary in spelling and script based on the language used. For example, *Leonardo da Vinci* (in English) refers to the same person as *Léonard de Vinci* (in French), and *Montreal Museum of Fine Arts* (in English) refers to the same institution as *Musée des beaux-arts de Montréal* (in French). Therefore, it is necessary to indicate the language in which an appellation was documented.

Moreover, throughout their lifetime, an actor will be referred to using more than a single appellation. For example, when adopting a spouse’s last name through marriage, when acquiring a new title through recognized achievements such as PhDs, when using pseudonyms in the context of specific occupations such as writing under pen names, or when adopting a new name or making other public facing changes to better reflect one's personal or group identity. To further qualify the identification of an actor, it is necessary to record the type of an appellation, as well as the context and time in which it has been used. 

Although CHIN is an aggregator, it does not adjudicate appellation precedence. Most providers use preferred and alternative names in their information system which this model must account for in order to preserve the integrity of the original data.

In addition, an appellation is often composed of many parts that are meaningful in the context of their respective category (e.g. a person might have a first, middle, and last name, and any of these could be John), so that partitions of an appellation and their associated types are necessary to prevent information loss or inaccuracy as well as retain the richness of a dataset. 

Another element that links to an actor’s appellation is the geographical location of their physical presence and where the appellation was used, especially for groups (see the [Staying Event](/collections-model/en/target-model/current/staying-event) pattern). For example, a company could have used two different registered names, associated with two different addresses. 

Documenting appellations is also essential for onomastic and genealogic research. Not only does it normally help to identify actors and groups of actors, but it also provides important information on name trends and, in some cases, contributes to the identification of name origins and family history (e.g. in retracing migratory flux).

## Description of the Pattern

An actor’s unique identifier is rendered by linking an instance of `E39_Actor` by the property `P1_is_identified_by` to an instance of `E42_Identifier` which is qualified by the [Actor ID Type](/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-id-type) value (an instance of `E55_Type`) through the property `P2_has_type`. That same instance of `E42_Identifier` is also linked to the literal value of the [Actor ID](/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-id) by the property `P190_has_symbolic_content`. 

For each appellation, the instance of `E39_Actor` is linked by the property `P1_is_identified_by` to an instance of both `E41_Appellation` and `E33_Linguistic_Object` which in turn is linked to:

* The literal value of the [Actor Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-appellation) by the property `P190_has_symbolic_content`;
* The [Actor Appellation Language](/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-appellation-language) value (an instance of `E56_Language`) by the property `P72_has_language`;
* The [Actor Appellation Type](/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-appellation-type) value (an instance of `E55_Type`) by the property `P2_has_type`. This instance is further qualified by an instance of `E55_Type` (a specified qualifier node) labelled "Type of Appellation" through the property `P2_has_type`;
* The [Actor Appellation Precedence](/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-appellation-precedence) value (an instance of `E55_Type`) by the property `P2_has_type`. This instance is further qualified by an instance of `E55_Type` (a specified qualifier node) labelled "Precedence" through the property `P2_has_type`;
* An instance of both `E41_Appellation` and `E33_Linguistic_Object` linked by the property `P106_is_composed_of` for each part that makes up the appellation. From this instance, the properties `P190_has_symbolic_content` and `P2_has_type` are used to respectively render the literal value of the [Actor Appellation Part](/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-appellation-part) and the [Actor Appellation Part Type](/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-appellation-part-type) value (an instance of `E55_Type`) which is further qualified by another instance of `E55_Type` (a specified qualifier node) labelled "Type of Appellation Part" through the property `P2_has_type`;
* An instance of `F52_Name_Use_Activity` linked by the property `R64i_was_name_used_by`. From this instance, the [Actor Appellation Use Context](/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-appellation-use-context) value (an instance of `E55_Type`) is rendered by the property `R61_occurred_in_kind_of_context`, and the time frame during which the context was used is indicated using the [Temporal Bounds](/collections-model/en/target-model/current/temporal-bounds) pattern through the property `P4_has_time-span` with values extracted from the [Actor Appellation Use Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-appellation-use-date-begin), [Actor Appellation Use Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-appellation-use-date-begin-qualifier), [Actor Appellation Use Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-appellation-use-date-end), and [Actor Appellation Use Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-appellation-use-date-end-qualifier) entry nodes.

## Diagram

<a name="020_Pattern_IdentifiersAppellations_p"></a>020_Pattern_IdentifiersAppellations_p

<iframe frameborder="0" style="width:100%;height:500px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=020_Pattern_IdentifiersAppellations_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1l8ZWjB5N1nxPOqI5WRMOa4fJxJITWTGc%26export%3Ddownload"></iframe>

## Examples

### Identifiers

In Artists in Canada, the identifier (`P2_has_type`, Actor ID Type "Artists in Canada Identifier") of Yousuf Karsh (`P190_has_symbolic_content`, Actor Appellation) is 8494 (`P190_has_symbolic_content`, Actor ID) (Canadian Heritage, Government of Canada 2011).

<div id="0001_100_identifier" class="example"></div>

### Appellations

Yousuf Karsh (`P190_has_symbolic_content`, Actor Appellation) is the English spelling (`P72_has_language`, Actor Appellation Language) of the Armenian-Canadian photographer’s full name (`P2_has_type`, Actor Appellation Type), whereas, Յուսուֆ Քարշ (`P190_has_symbolic_content`, Actor Appellation) is the Armenian spelling (`P72_has_language`, Actor Appellation Language). Yousuf Karsh is his preferred name (`P2_has_type`, Actor Appellation Precedence) by the National Gallery of Canada (the contributor of Yousuf Karsh’s record in Artists in Canada). Yousuf (`P190_has_symbolic_content`, Actor Appellation Part) is his first name (`P2_has_type`, Actor Appellation Part Type) and Karsh (`P190_has_symbolic_content`, Actor Appellation Part) is his surname (`P2_has_type`, Actor Appellation Part Type) (Canadian Heritage, Government of Canada 2011).

<div id="0001_100_appellations" class="example"></div>

### Name Use

Charles Lutwidge Dodgson used the pen name (`P2_has_type`, Actor Appellation Type) Lewis Carroll (`P190_has_symbolic_content`, Actor Appellation) from 1856 (`P82a_begin_of_the_begin`, Actor Appellation Use Date Begin) to his death in 1898 (`P82b_end_of_the_end`, Actor Appellation Use Date End) when publishing children's books (`R61_occurred_in_kind_of_context`, Actor Appellation Use Context "Children’s Book Writing") while his work as a mathematician (`R61_occurred_in_kind_of_context`, Actor Appellation Use Context "Mathematics Treatises Author") was published under his birth name (`P2_has_type`, Actor Appellation Type) Charles Lutwidge Dodgson (`P190_has_symbolic_content`, Actor Appellation) (Wikipedia 2022a).

<div id="0001_102_name-use" class="example"></div>

## Related Documentation

### External Models

* Linked.art: [Names and Identifiers for a Resource](https://linked.art/model/base/#names-and-identifiers-for-a-resource)
* SARI: [Person Reference Data Model – Names and Classifications](https://docs.swissartresearch.net/et/persons/#names-and-classifications)

### Entry Nodes

* [Actor Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-appellation) \| Checklist
* [Actor Appellation Language](/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-appellation-language) \| Checklist
* [Actor Appellation Part](/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-appellation-part) \| Checklist
* [Actor Appellation Part Type](/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-appellation-part-type) \| Checklist
* [Actor Appellation Precedence](/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-appellation-precedence) \| Checklist
* [Actor Appellation Type](/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-appellation-type) \| Checklist
* [Actor Appellation Use Context](/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-appellation-use-context) \| Checklist
* [Actor Appellation Use Date Begin](/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-appellation-use-date-begin) \| Checklist
* [Actor Appellation Use Date Begin Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-appellation-use-date-begin-qualifier) \| Checklist
* [Actor Appellation Use Date End](/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-appellation-use-date-end) \| Checklist
* [Actor Appellation Use Date End Qualifier](/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-appellation-use-date-end-qualifier) \| Checklist
* [Actor ID](/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-id) \| Checklist
* [Actor ID Type](/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-id-type) \| Checklist

Plus, all the appellations and IDs of other actors related to the documented actor use the entry nodes presented above. In other words, the following nodes can also be described as being an [Actor ID](/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-id), an [Actor Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-appellation), or an [Actor Appellation Part](/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-appellation-part) depending on the recorded content. These include the following nodes:

* [Curatorial Note Author Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#curatorial-note-author-appellation) \| Checklist
* [Dataset Creation Participant Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#dataset-creation-participant-appellation) \| Checklist
* [Dissolving Actor Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#dissolving-actor-appellation) \| Checklist
* [Family Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#family-appellation) \| Checklist
* [Father Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#father-appellation) \| Checklist
* [Founding Actor Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#founding-actor-appellation) \| Checklist
* [Group Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#group-appellation) \| Checklist
* [Mother Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#mother-appellation) \| Checklist
* [Record Contributor Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#record-contributor-appellation) \| Checklist
* [Related Actor Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#related-actor-appellation) \| Checklist
* [Social Status Ascribing Actor Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#social-status-ascribing-actor-appellation) \| Checklist

### CIDOC CRM Entities

* `E7_Activity` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E7)]
* `E33_Linguistic_Object` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E33)]
* `E39_Actor` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E39)]
* `E41_Appellation` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E41)]
* `E42_Identifier` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E42)]
* `E52_Time-Span` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E52)]
* `E55_Type` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E55)]
* `E56_Language` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E56)]
* `F52_Name_Use_Activity`
* `P1_is_identified_by (identifies)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P1)]
* `P2_has_type (is_type_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P2)]
* `P4_has_time-span (is_time-span_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P4)]
* `P16_used_specific_object (was_used_for)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P16)]
* `P72_has_language (is_language_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P72)]
* `P79_beginning_is_qualified_by`[[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P79)]
* `P80_end_is_qualified_by` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P80)]
* `P82a_begin_of_the_begin`
* `P82b_end_of_the_end`
* `P106_is_composed_of (forms_part_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P106)]
* `P190_has_symbolic_content` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P190)]
* `R61_occurred_in_kind_of_context (was_kind_of_context_for)`
* `R64_used_name (was_name_used_by)`

## Discussion

### Rationale

CIDOC CRM suggests the use of the class `E41_Appellation` in conjunction with the property `P1_is_identified_by` to represent names which typically do not need the language used to be specified as most often a single spelling is employed for all languages. However, an actor’s name might have been translated or adapted, e.g. *Leonardo da Vinci* is *Léonard de Vinci* in French. All variations are necessary for research and data analysis, as well as reconciliation so that they must be accounted for in combination with their respective language. To do so, it is possible to tag a literal value with a language tag (e.g. @en, @fr), but adding the language directly to the appellation pattern through the property `P72_has_language` increases the SPARQL queries’ speed and thus appears to be a better practice. However, an instance of `E41_Appellation` alone cannot be linked to a language value by the property `P72_has_language`. This is why an instance for both `E41_Appellation` and `E33_Linguistic_Object` is more appropriate. 

In the DOPHEDA model, each appellation is treated as unique to its bearer rather than shared among different actors, even though the "shared appellation" approach is theoretically more compatible with linked data principles; each appellation should be represented as a unique URI which is linked to multiple actors that bear the same name. As explained in the Theoretical Background, an appellation carries meaning inflected by its social context. However, this approach can be challenging in terms of implementation. For example, reconciliation to the URI of the same appellation must be done for each mapping. Plus, CHIN has yet to identify any immediate and foreseeable use of the "shared appellation approach" (see [Issue #25](https://github.com/chin-rcip/collections-model/issues/25)).

In terms of precedence, the property `P139_has_alternative_form` can be used, but it will make the preferred appellation dependent on the existence of an alternative appellation which significantly complexifies the pattern and the management of the data it accommodates. This approach significantly complicates SPARQL queries as, when looking for the different appellations of a single actor, the same appellation recurs several times. Moreover, when searching for a specific appellation, the differentiation of preferred from non-preferred appellations is difficult. 

That being said, the `P2_has_type` and `E55_Type` path provides a simple solution to indicate which appellation an organization prefers while still displaying alternative names of an actor (`E39_Actor`). The precedence of an appellation should be distinguished by relying on a controlled vocabulary rather than on a boolean since precedence nodes are more meaningful than "yes" or "no" (e.g. this allows to search for all preferred appellations across actors).

For the partitions of appellations, two options were considered. The first possibility was to directly append the different parts of the appellations (`E33_Linguistic_Object` and `E41_Appellation`) of the actor (`E39_Actor`) by using the properties `P1_is_identified_by` and `P2_has_type` with an instance of `E55_Type` in order to specify which part of the name is represented. However, this would have made it impossible to know which parts of the non-preferred appellation should be combined together to create a full appellation. Whereas the other option, suggested by the [Linked.art](https://linked.art/model/actor/#parts-of-names) project, was to link the full appellation to the actor to subsequently partition it with the property `P106_is_composed_of`. This second solution was adopted by CHIN as it facilitates querying and reduces performance costs. 

To determine the location associated with the appellation, [Stay Place](/collections-model/en/semantic-paths-specification/current/entry-nodes#stay-place) entry node values can be queried to identify the overlap between the use of the appellation during a certain time and where and when that stay event occured; this overlap could amount to the location with which an appellation is associated. However, this can only work under the false assumption that temporal data is always recorded and available. Moreover, if an actor bears two different names at once, it would be impossible to use an algorithm to determine which one was used for which location. Thus, modelling the connection between an appellation and its associated location is deemed to be a better solution than relying on queries to do so, and two options appear:

* The property `P16_used_specific_object (was_used_for)` is employed to connect the appellation to its staying activity, from which the information of the place is rendered, by using the property `P7_took_place_at`. This indicates that during the stay at this place, the actor used this appellation;
* The property `P7_took_place_at` is used to directly connect the use activity of the appellation to the place where it occurred. It suggests that the appellation was used for this activity which took place in one or more places.

Though these options differ slightly in terms of semantics, both can be used to indicate the location associated with an appellation. However, the name use activity itself might not be situated in space per se. For example, Charles Dodgson used the pseudonym Lewis Carroll for his writing activity, and he also stayed at a place under this name. A direct link between the name use activity and the place implies that the use of that name for writing actually happened in that place, but it might not be the case. On the other hand, it is more accurate to say that while staying at this place, the actor has gone by this appellation which was used in this activity. Thus, linking the staying event to the appellation (option one) is recommended by CHIN for the DOPHEDA environment. 

### Limitations

Even if the model does not require documenting both the [Actor Appellation](/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-appellation) and the [Actor Appellation Part](/collections-model/en/semantic-paths-specification/current/entry-nodes#actor-appellation-part), the presence of these two pieces of information allows greater flexibility in drafting requests while simplifying them. However, if either one of them is not documented and categorized in the source dataset, it is hardly possible to properly generate instances from one to the other automatically.

Adding to this, the inability of the model to manage appellations that are socially shared is an important aspect of the field of genealogy. Currently, the same first name used by two different people has two different URIs. This particular aspect is due to the complexity of distinguishing between the information that applies to the shared name and the one that applies specifically to the name of a particular actor. As such, CHIN decided to attribute one URI per name and per actor since the use cases did not present data about the generic name *per se*. In consequence, the information pertaining to the appellation can only be found in the context of a specific actor, rather than its actor-independent historical context which limits genealogical and onomastic research.

### Related GitHub Issues

* [Issue #24 "Should we use Boolean for the preference or just a controlled vocabulary?"](https://github.com/chin-rcip/chin-rcip/issues/24)
* [Issue #25 "Is an appellation unique to its bearer?"](https://github.com/chin-rcip/chin-rcip/issues/25)
* [Issue #35 "Should we date the appellations?"](https://github.com/chin-rcip/chin-rcip/issues/35)

### Edge Cases

#### Example 1 {#edge-cases-example-1}

Queen Elizabeth II, the appellation of the person who was in charge of officially granting the social status "Companion of the Order of Canada" to Yousuf Karsh, is often used to identify the currently reigning monarch of the United Kingdom. While the appellation parts "Elizabeth" and "II" (Actor Appellation Parts) can be easily categorized as "First name" and "Suffix" respectively (Actor Appellation Part Type), the part of the value "Queen" can become quite tricky when mapping. Indeed, "Queen" could be treated as either the "Title" attached to a name or the "Social status" of the actor bearing that name. In such a case, the modeller should respect the original cataloguing intention of the source provider. For example, if "Queen" was recorded as a value in the field pertaining to appellation, it can be considered as "Title" (Actor Appellation Part Type).

#### Example 2 {#edge-cases-example-2}

If a war artist was assigned the number M32 435 C84 (his military registration number), this number would qualify as the Actor Appellation and the Actor Appellation Type would be "Military Registration Number" or "Military ID". If the War Museum is related to the Department of National Defence or uses the same numbers to identify artists, this number would qualify both as the Actor Appellation (the number assigned by the Department of National Defence) and as the Actor ID (the same number used by the War Museum).

#### Example 3 {#edge-cases-example-3}

The French appellation of Power Corporation of Canada is Power Corporation du Canada. An institution wanting to record both these appellations could either create two Actor Appellations (one for Power Corporation of Canada indicated as English in the Actor Appellation Language node, and one for Power Corporation du Canada indicated as French in the Actor Appellation Language node) or a single, bilingual one (Power Corporation of Canada/Power Corporation du Canada).

#### Example 4 {#edge-cases-example-4}

The same applies to many governmental bodies in Canada such as PCH Canadian Heritage/Patrimoine canadien where, in addition, the question of the language of the acronym is unclear: if PCH is the Actor Appellation with an Actor Appellation Type labelled "Acronym", it is possible to consider this as a single, bilingual appellation.

#### Example 5 {#edge-cases-example-5}

Some institutions need to document animals as actors and although the current definition could accommodate this, the CIDOC CRM model might not. For example, Wojtek was a bear officially enlisted in the Polish army (Wikipedia 2022b).

#### Example 6 {#edge-cases-example-6}

An IP address might be considered to be an ID that refers to the actor but does not represent it. It is unclear if the Actor ID Type would accommodate the IP address considering multiple actors can use a single computer, especially if it is a duo using the computer to semi-automatically create an object so that the computer takes part in the creation. In the case of media-generated art, it is also unclear if the IP address would be part of the Artefact IDs, the Actor IDs, or both in such a case.

#### Example 7 {#edge-cases-example-7}

SAMO is a graffiti tag that was used in New York from 1977 to 1980, primarily by Jean-Michel Basquiat and Al Diaz. It could be considered an Actor Appellation (Actor Appellation Type "Pseudonym"); if so, the dates would not be problematic (Actor Appellation Use Date End "1980-12-31T23:59:59"). However, it could also be considered an Artefact (as SAMO was graffitied across the city), thus possibly used by multiple actors (Wikipedia 2021). This begs the question of whether an appellation use date has an end when people continue to use the appellation well after the actor’s death. There could be, in this case, an Artefact Appellation and an Actor Appellation of the same name, but the way to handle the dates for each would have to be clarified.

## Bibliography

Bekiari, Chryssoula, Martin Doerr, Patrick Le Bœuf, and Pat Riva, eds. *FRBR Object-Oriented Definition and Mapping from FRBRER, FRAD and FRSAD*. FRBRoo Documentations, 2.4. International Council of Museums (ICOM), 2015. [http://www.cidoc-crm.org/frbroo/sites/default/files/FRBRoo\_V2.4.pdf](http://www.cidoc-crm.org/frbroo/sites/default/files/FRBRoo_V2.4.pdf).

Bekiari, Chryssoula, George Bruseker, Martin Doerr, Christian-Emil Ore, Stephen Stead, and Athanasios Velios, eds. *Definition of the CIDOC Conceptual Reference Model*. CIDOC CRM Documentations, 7.1. Paris, FR-IDF: CIDOC CRM Special Interest Group, 2021. [http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf](http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf).

Canadian Heritage, Government of Canada. "Karsh, Yousuf." *Artists in Canada*. Ottawa, CA-ON: Government of Canada, 2011. [https://app.pch.gc.ca/application/aac-aic/artiste_detailler_bas-artist_detail_bas.app?lang=en&rID=8494](https://app.pch.gc.ca/application/aac-aic/artiste_detailler_bas-artist_detail_bas.app?lang=en&rID=8494).

Granger, Gilles Gaston. "À quoi servent les noms propres?" *Langages* 16, no. 66 (1982): 21–36. [https://doi.org/10.3406/lgge.1982.1124](https://doi.org/10.3406/lgge.1982.1124).

Green, Brian, and Mark Bide. *Unique Identifiers: A Brief Introduction*. 2Rev e. edition. London, UK-LDN: Book Industry Communication, 1997.

Lecolle, Michelle, Marie-Anne Paveau, and Sandrine Reboul-Touré. "Les sens des noms propres en discours." *Les Carnets du Cediscor*. Publication du Centre de recherches sur la didacticité des discours ordinaires, 11 (March 2009): 9–20.

Wikipedia. "SAMO." *Wikipedia*. San Francisco, US-CA: Wikipedia, 2021. [https://fr.wikipedia.org/wiki/SAMO](https://fr.wikipedia.org/wiki/SAMO).

Wikipedia. "Lewis Caroll." *Wikipedia*. San Francisco, US-CA: Wikipedia, 2022a. [https://en.wikipedia.org/wiki/Lewis_Carroll](https://en.wikipedia.org/wiki/Lewis_Carroll).

Wikipedia. "Wojtek." *Wikipedia*. San Francisco, US-CA: Wikipedia, 2022b. [https://fr.wikipedia.org/wiki/Wojtek](https://fr.wikipedia.org/wiki/Wojtek).

