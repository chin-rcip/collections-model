---
layout: page
language: en
title: General Concepts
permalink: /en/target-model/current/general-concepts
other_link: /fr/modele-cible/actuel/concepts-generaux
sidebar: tm22
date: 2022-03-31
description: The Actors Target Model Specification semantically models actors in a heritage context. Patterns most relevant to actors' lives are presented along with diagrams and examples illustrating them, as well as a record and explanation of relevant decisions that were made when developing said patterns. This is a theoretical documentation that has never been tested or implemented.
---

Version 2.2 ([Previous versions](/collections-model/en/versions))

## Prioritization of `E55_Type` and `P2_has_type` over New Classes and Properties

### Context {#prioritization-of-e55_type-and-p2_has_type-over-new-classes-and-properties-context}

Because CIDOC CRM is an ontology developed to serve the cultural sector as a whole, its entities are intentionally general in scope to adequately answer the needs and understandings of various heritage disciplines (e.g. archæology, art, history, sociology). However, such generality can become a limitation when modelling complex concepts (e.g. relationships, techniques, occupations) which themselves encompass other concepts and carry numerous characteristics. This complexity can hinder recording and querying processes that would otherwise be semantically straightforward. Thus, it is advisable to simplify these processes by further qualifying complex classes in order to enhance their semantic preciseness (Bekiari et al. 2021, sect. About Types). This can be done one of two ways. 

One option is to create new classes and properties. However, this practice is not recommended by CHIN as it leads to a convoluted model (hence complexifying the mapping process) and to a larger number of entities to manage (thus complicating practitioners' queries). In addition, to ensure a model's effectiveness, the technological and human resources it requires have to be kept to a minimum throughout its life cycle (development, implementation, and maintenance phases), a principle the creation of classes and properties contravenes. It is thus recommended to:

* Limit the fields of expertise a model accommodates and represents (Bruseker 2017, 25);
* Avoid the inclusion of patterns that address *technological* rather than *informational* imperatives (Gruber 1995, 910); 
* Prioritize the use of pre-existing classes and properties over the creation, documentation, and maintenance of new ones. 

A common practice to address this challenge is to employ external vocabularies to categorize generic entities. This approach has several advantages: 

* It requires less resources than the internal maintenance and management of specialized entities (Doerr et al. 2020, xxxviii); 
* It facilitates interoperability between models as the reconciliation of specialized entities among different models is more complicated than that of common vocabularies terms; 
* It enables organizations to rely on a skillset their professionals already have (i.e. vocabulary management). 

For these reasons, CHIN has decided to rely heavily on the use of external vocabularies rather than on the creation of new entities.

### Description {#prioritization-of-e55_type-and-p2_has_type-over-new-classes-and-properties-description}

Hence, the class `E55_Type` and the property `P2_has_type` are used to specify entities rather than create new sub-classes and sub-properties. 

For instance, in the [Actor Identifiers and Appellations](/collections-model/en/target-model/current/actor-identifiers-and-appellations) pattern, the appellation of an actor is qualified by the property `P2_has_type` and a controlled vocabulary is used to designate the type of this appellation which is an instance of `E55_Type`.

<a name="095_Convention_E55_Type_p"></a>095_Convention_E55_Type_p

<iframe frameborder="0" style="width:100%;height:200px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=095_Convention_E55_Type_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1wWq106w7u6iZgk8uIH_slffcP8xBDL-O%26export%3Ddownload"></iframe>

**Example**: Yousuf Karsh is the full name (`E55_Type`) of this Armenian-Canadian photographer.

<div id="0001_100_appellation-full-name" class="example"></div>

In addition to this consideration, when several instances of `E55_Type` accommodating different kinds of information are attached to the same entities, another level of `E55_Type` designates the first `E55_Type` with a second `E55_Type` "metatype" which is used to easily retrieve comparable information at the querying stage.

For instance, in the [Actor Identifiers and Appellations](/collections-model/en/target-model/current/actor-identifiers-and-appellations) pattern, the appellation of an actor is qualified both by a type of appellation value selected from an associated vocabulary (e.g. Full name, Pseudonym) and a type of precedence value also selected from an associated vocabulary (e.g. Preferred, Non-preferred). Each of these selected type values, instances of `E55_Type`, is further qualified using the property `P2_has_type` and vocabulary labels describing their respective broader categories, "Precedence" and "Type of Appellation", which are also instances of `E55_Type` (so that the type of information found in each `E55_Type` can easily be identified by the user).

<a name="096_Convention_E55_Metatype_p"></a>096_Convention_E55_Metatype_p.drawio

<iframe frameborder="0" style="width:100%;height:300px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=096_Convention_E55_Metatype_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1irtCvRIwl1ewYE3FRzm3zu02s0VUOu6X%26export%3Ddownload"></iframe>

### Examples {#prioritization-of-e55_type-and-p2_has_type-over-new-classes-and-properties-examples}

Yousuf Karsh is the preferred (`E55_Type`, Actor Appellation Precedence) full name (`E55_Type`, Actor Appellation Type) of this Armenian-Canadian photographer.

<div id="0001_100_appellation-precedence" class="example"></div>

### Related GitHub Issues {#prioritization-of-e55_type-and-p2_has_type-over-new-classes-and-properties-related-github-issues}

* [Issue #37 "Usefulness of `E55_Type`"](https://github.com/chin-rcip/collections-model/issues/37)

## Differences Between `E39_Actor`, `E21_Person`, and `E74_Group`

Most heritage data pertaining to individuals or groups centers around the *creators* of artefacts and, as such, the actors patterns of the Target Model Specification are centered around the class `E39_Actor` which "comprises people, either individually or in groups, who have the potential to perform intentional actions of kinds for which someone may be held responsible" (Le Bœuf et al. 2015, sect. E39 Actor).

There are two sub-classes to `E39_Actor`: 

* `E21_Person`, which comprises real persons;
* `E74_Group`, which accounts for any type of gathering or organization of instances of `E39_Actor` acting collectively. As stated in CIDOC CRM, "a gathering of people becomes an `E74_Group` when it exhibits organizational characteristics usually typified by a set of ideas or beliefs held in common, or actions performed together" (Le Bœuf et al. 2015, sect. E74 Group).

In terms of mapping, whenever it is possible to distinguish a person from a group in a source dataset, the use of the more specific sub-classes `E21_Person` and `E74_Group` should be prioritized over that of the class `E39_Actor` for the following reasons:

* Maintenance of the mapping process is more efficient as the modelling of an instance of `E21_Person` is not completely identical to the modelling of an instance of `E74_Group`;
* Data cleaning is facilitated through more precise reconciliation that is more effective in the long-term.

However, in some cases, it is acceptable to use the class `E39_Actor` (`E77_Persistent_Item`) rather than one of its sub-classes:

* When it is uncertain whether the actor is a person, an organization, or a group (Linked.art 2019);
* When a dataset might contain data pertaining to both actors and groups in a single field.

If a source dataset originally mapped using the class `E39_Actor` is updated to distinguish between persons and groups, its mapping should be updated to use the sub-classes of the class `E39_Actor` (`E21_Person` and `E74_Group`). This can be done with a SPARQL Update query.

Although the Target Model Specification technically offers the flexibility to use either `E39_Actor`, `E21_Person`, or `E74_Group`, the Semantic Paths Specification does not offer this latitude.

## Semantic Differences Between Labels, Annotations, or Comments, and Literal Contents

Literal heritage data (e.g. text content) can generally be classified into three kinds of strings: 

* Labels;
* Annotations or comments;
* Literal content.

There are various ways to link such data, each of which is intended to account for a specific type of human-readable statement. The choice of which property to assign to a resource indicates what kind of statement it is and how data is managed. 

### Labels

#### Context {#labels-context}

Labels are used to provide a human-readable version of a resource’s identification in addition to its Uniform Resource Identifier (URI). A resource can have more than one label, especially due to the languages used to refer to it (e.g. one label in French, a second one in English). 

#### Description {#labels-description}

Labels are rendered with the property `rdfs:label`.

<a name="007_Pattern_Labels_p"></a>007_Pattern_Labels_p

<iframe frameborder="0" style="width:100%;height:200px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=007_Pattern_Labels_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1OpP-BrB0ZPTxuxnHGj7eBnWQ8nFfSqAK%26export%3Ddownload"></iframe>

#### Examples {#labels-examples}

For example, if the occupation of a photographer is documented using an [Art & Architecture Thesaurus (AAT) URI](http://vocab.getty.edu/aat/300025687), the label "Photographers" should be added to this URI so that humans can understand what that occupation is without referring to the Getty website. 

<div id="aat_300025687_label" class="example"></div>

Another example is in the case of birth events where concatenation mechanisms (at the mapping stage) can provide useful descriptive labels such as "Yousuf Karsh Birth" for an instance of `E67_Birth` representing the birth of Yousuf Karsh; that way, the function of the node is easily understandable to humans.

### Annotations or Comments

#### Context {#annotations-or-comments-context}

As heritage data is generated from intensive research, annotations and comments are integral to qualifying a record or even a specific piece of data. They are distinguished in two types:

* Annotations that arise during the mapping process and, for example, concern data quality, modelling, and/or mapping issues, or information that the provider wishes to submit to the DOPHEDA environment alongside the dataset;
* Annotations that are part of the original dataset, such as curatorial or research notes.

The former type is described in this section, whereas the [Curatorial Note](/collections-model/en/target-model/current/curatorial-note) pattern must be used for the latter.

#### Description {#annotations-or-comments-description}

Depending on what is commented upon, annotations on a resource are rendered by either:

* The CIDOC CRM property `P3_has_note`, which is used for [annotations](/collections-model/en/semantic-paths-specification/current/entry-nodes#annotation) regarding specific data values (e.g. "the image URL is not valid/working"); or
* The RDFS property [`rdfs:comment`](https://www.w3.org/TR/rdf-schema/#ch_comment), which is used for comments with regards to classes and properties of a data model (e.g. "This property identifies the instance E24 Physical Human-Made Thing that was diminished by an instance of E80 Part Removal").

Both `P3_has_note` and `rdfs:comment` properties make statements about the resource’s content but do not comprise its content. For example, the property `P3_has_note` applied to an instance of `E33_Linguistic_Object` allows to annotate the text, but does not include it (for information on the content, see the [Literal Content](collections-model/en/target-model/current/general-concepts#literal-content) section.

#### Diagram {#annotations-or-comments-diagram}

<a name="008_Pattern_AnnotationsComments_p"></a>008_Pattern_AnnotationsComments_p

<iframe frameborder="0" style="width:100%;height:300px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=008_Pattern_AnnotationsComments_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1vDwx2giefS8bHl7q249cxQ5imwAVOzyV%26export%3Ddownload"></iframe>

#### Examples {#annotations-or-comments-examples}

The [AAT URI](http://vocab.getty.edu/aat/300025687) is used as an instance of the occupation "Photographers", but only an English label is available, with no French equivalent already established. This information can be mentioned as part of an annotation to the AAT URI (`E33_Linguistic_Object`, `P3_has_note`).

<div id="aat_300025687_label-note" class="example"></div>

#### Discussion {#annotations-or-comments-discussion}

The [Annotation](/collections-model/en/semantic-paths-specification/current/entry-nodes#annotation) entry node, which relies on the property `P3_has_note`, has to be used in edge cases when something is too complex and subtle to be adequately accounted for by current patterns, and too specific to warrant the creation of a new pattern. This should be used by data providers to clarify information on a data value, whereas the property `rdfs:comment` should be used by the creator of a model to add information about it directly. 

#### Entry Nodes {#annotations-or-comments-entry-nodes}

*There are no entry nodes for comments because they do not pertain to data values themselves (hence they do not come from the data provider and/or the data mapping process)*. 

* [Annotation](/collections-model/en/semantic-paths-specification/current/entry-nodes#annotation) \| Checklist

#### Related GitHub Issues {#annotations-or-comments-related-github-issues}

* [Issue #32 "Should we use `P3 has note` or `rdfs:comment`?"](https://github.com/chin-rcip/collections-model/issues/32)

### Literal Content

#### Context {#literal-content-context}

Heritage datasets often, if not always, contain contents describing resources such as appellations, biographies, or descriptions that are too complex or detailed to be fully semanticized and whose textual or "free form" must thus be retained. In addition, unstructured data that cannot be properly "cleaned" with current technology and resources is also treated as literal textual content (for more information, see the [Messy Data](/collections-model/en/target-model/current/messy-data) pattern). Literal values describe a resource and, as such, must be properly captured by the model and distinguished from other kinds of strings such as labels, annotations, or comments.

#### Description {#literal-content-description}

These literal contents are values from entry nodes linked to their corresponding class instance by the property `P190_has_symbolic_content`.

#### Examples {#literal-content-examples}

The biography of Yousuf Karsh could have:

* A label "Biography of Yousuf Karsh";
* A note from the data provider assessing the biography, stating that it has to be revised;
* The contents of the biography.

<div id="0001_100_literal-content-bio" class="example"></div>

#### Discussion {#literal-content-discussion}

The properties `rdfs:comment` and `rdfs:label` are not suitable to capture literal contents.

Even though CIDOC CRM previously recommended the use of the property `P3_has_note` for heritage content (Le Bœuf et al. 2015, sect. E33 Linguistic Object), it is no longer the case as the property `P3_has_note` "is a container for all informal descriptions about an object that have not been expressed in terms of CRM constructs. In particular it captures the characterization of the item itself, its internal structures, appearance, etc." (Le Bœuf et al. 2015, sect. P3 Has Note). To address this, CIDOC CRM has developed the property `P190_has_symbolic_content` to associate an instance of `E90_Symbolic_Object` with a representation of its entire content in the form of a string of text (Bekiari et al. 2021, sect. P190 Has Symbolic Content).

The best way to semantically represent the content of a resource is to use the property `P190_has_symbolic_content` to render literal content rather than to rely on a custom-made property that would only be used locally. As is often the case with Linked Open Data, it is preferable to employ recognized and approved classes and properties rather than create new, single use ones.

## Property-Classes

### Context {#property-classes-context}

In CIDOC CRM, some properties can be qualified by a statement in order to describe more precisely the nature of the link between two entities. For example, one could wish to specify the role in which someone carried out an activity by pointing to a vocabulary term defining this role. To do so, it would be possible to use the property `P14.1_in_the_role_of`, but it would pose the following challenge: if the role of the actor carrying out an activity was to be qualified by the property `P14.1_in_the_role_of` applied directly to the property `P14_carried_out_by`, this property’s URI would always be qualified (no matter the context of its use). For example, if Role A is used to specify the property `P14_carried_out_by` that links Actor B to Activity C, other occurrences of the property `P14_carried_out_by` would also be linked to Role A even though this would be inaccurate. In other terms, CIDOC CRM tends to be implemented in RDF where properties cannot be qualified, leaving a gap between the ideal expressivity of the ontology and its expression in an actual implementation. In 2014, in order to address this issue, the CRM SIG developed property-classes (often called PC in the CIDOC CRM context) which are part of an [extension](http://www.cidoc-crm.org/sites/default/files/CRMpc_v1.0.rdfs). The latter enables the reification of specific properties so that instances of property-classes can become the subject of other triples without compromising the logics of the rest of the ontology.

### Description {#property-classes-description}

Coming back to the example above, the property-class `PC14_carried_out_by` can be used instead of the property `P14_carried_out_by`. An instance of the property-class `PC14_carried_out_by` can be qualified with a role (`E55_Type`, Relationship Actor Role) through the property `P14.1_in_the_role_of`. Because the instance of the property-class is used as the subject of the triple, the role only applies to that specific instance.

In order to link the domain and range of the previously used property `P14_carried_out_by`, two new properties (`P01_has_domain` and `P02_has_range`) have been created to connect the property-class `PC14_carried_out_by` to its corresponding domain (`E7_Activity`) and range (`E39_Actor`).

`E7_Activity → P14_carried_out_by → E39_Actor`

has been replaced by the following:

`E7_Activity ← P01_has_domain ← PC14_carried_out_by → P02_has_range → E39_Actor`

### Examples {#property-classes-examples}

Without the use of property-classes, the role of the actors involved in a relationship would be directly linked to the property `P14_carried_out_by`. Yousuf Karsh would be a participant of a relationship event with Solange Gauthier, both in the role of "Spouse", as shown in the diagram below:

<a name="097a_PC_Example_1_p"></a>097a_PC_Example_1_p

<iframe frameborder="0" style="width:100%;height:443px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=097a_PC_Example_1_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1RobfZr9lsTtSsOXc5oXxR-UBrfjGzLlp%26export%3Ddownload"></iframe>

However, such a representation would imply that any other occurence of the property `P14_carried_out_by` would also be linked to the role "Spouse". This would lead to the affirmation that, for example, Charles Lutwidge Dodgson, better known as Lewis Carroll, created the book *Alice’s Adventures in Wonderland* with the role "Spouse", as shown in the diagram below:

<a name="097b_PC_Example_2_p"></a>097a_PC_Example_2_p

<iframe frameborder="0" style="width:100%;height:423px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=097b_PC_Example_2_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1ngy8o3QIAwNz36acbLJrxO8nZwvAy8ow%26export%3Ddownload"></iframe>

With the use of property-classes, the property `P14_carried_out_by` would become an instance of `PC14_carried_out_by` which means that the role of "Spouse" of Yousuf Karsh would only be applicable to that particular instance of `PC14_carried_out_by` that is linking Yousuf Karsh to the relationship event with Solange Gauthier, as shown in the diagram below:

<a name="097c_PC_Example_3_p"></a>097c_PC_Example_3_p

<iframe frameborder="0" style="width:100%;height:463px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=097c_PC_Example_3_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1vfdjUVRCQN-iorgW1X9WF-e_pv45VCvy%26export%3Ddownload"></iframe>

### Limitation {#property-classes-limitation}

The hierarchy of the Property-Classes extension dictates that each new property-class is a sub-class of a root class called `PC0_Typed_CRM_Property`. This minimalistic hierarchy, however, does not follow the CRMbase hierarchy conventions according to which some of Pxx.1 properties would inherit the characteristics of their super-properties. For example, the property `P67.1_has_type` (domain `PC67_refers_to`) cannot be used with the property-class `PC138_represents` even though it is a sub-property of `P67_refers_to` in CRMbase. 

In addition, the property-class `PC0_Typed_CRM_Property` is not a sub-class of `E1_CRM_Entity` or of any other CRMbase entity which entails that the property-classes are technically not linked semantically to CIDOC CRM (although their use remains relatively widespread). 

### Related Internal Documentation {#property-classes-related-internal-documentation}

Property-classes used throughout the Target Model Specification are:

* `PC14_carried_out_by` in the [Relationship](/collections-model/en/target-model/current/relationship) and the [Artefact Production](/collections-model/en/target-model/current/artefact-production) patterns;
* `PC138_represents` in the [Visual Item](/collections-model/en/target-model/current/visual-item) pattern;
* `PC144_joined_with` in the [Group Belonging](/collections-model/en/target-model/current/group-belonging) pattern.

## Challenges When Representing Underserved Communities Realities 

The DOPHEDA project aims to document actors from cultural institutions located in Canada. As such, the Target Model Specification must render most, if not all, of the distinctive characteristics of communities across Canada, including the ones that are typically underserved by traditional models—most notably Indigenous and LGBTQIA+ communities.

A general overview of the data currently held by heritage organizations reveals a need to document several aspects of actors’ identity traits such as their cultural affiliation, gender, and national or communal belonging. These identity traits are increasingly relevant to the contextualization of actors’ work as well as collecting and documentation practices, especially when it comes to assessing (mis-)representation of marginalized communities in heritage collections. 

However, such information also has a high-risk of being problematic either at the recording (i.e. in the providers’ databases), structuring (i.e. in the DOPHEDA model), or mapping (i.e. when assigning values from the providers’ databases to the model) level. Identity traits of an actor are far more fluid and flexible than at first glance and the development of patterns that would be too simplistic to adequately account for this fluidity could lead to further misrepresentation of already marginalized communities.

### Concerned Patterns {#challenges-when-representing-underserved-communities-realities-concerned-patterns}

A review of current models and vocabularies indicates that they typically adopt a point of view that does not adequately represent the realities of peoples' lives and artefacts when it comes to identity. Thus, resulting patterns run the risk of being problematic and CHIN has decided to remove the following patterns and nodes from the version 2.2 of the Target Model Specification and the Semantic Paths Specification in order to fully assess the implications of their development, implementation, and deployment: 

* **Gender Type**: This node documents the cultural gender (as opposed to the biological one) that a person identifies with. As a socio-cultural concept, it refers to a state or condition associated with a range of characteristics having to do with a person’s behaviour, mannerisms, interests, and appearance, as well as the way they are associated with gendered categories in a particular cultural context.
* **Nationality**: This node indicates the status of belonging (by origin, birth, or naturalization) to a politically autonomous entity endowed with national independence. Unlike cultural affiliation, which relies on self-association with a culture, nationality refers to the legal status of being a citizen or a subject of a recognized state. It is possible to have multiple affiliations at once. 
* **Cultural Affiliation Type**: This node indicates cultural, rather than legal, belonging to a group that is characterized by shared customs, mores, and practices revolving around common elements such as location, history, language, beliefs, culinary practices, etc. It revolves around collective values and identities and, as such, it is possible to have multiple affiliations at once. This belonging is not official in the sense that assent from the concerned group is not formalized or explicit. It is distinct from and broader than nationality which is a strictly legal concept independent of an actors’ explicit or implicit identification with a culture. For example, an artist born in France and endowed with French nationality could live in Canada for most of their life and claim Canadian cultural affiliation despite not having Canadian citizenship.
* **Nationhood**: This node indicates the status of belonging to an autonomous polity endowed with official structures or institutionalized hierarchy (whether formalized or not) as well as shared customs, mores, and practices revolving around common elements such as location, history, language, beliefs, culinary practices, etc. Unlike cultural affiliation, which relies on (self-)identification or nationality (which refers to the legal status of being a citizen or a subject of a recognized state), Nationhood describes official belonging with implicit or explicit assent from the group (as represented by its official or influential members). It refers to the nation the actor identifies/is identified with regardless of their nationality or culture. This node accommodates various types of nationhood, including ethnic, civic, tribal, and multicultural. It often revolves around shared practices and traditions transmitted from one generation to another, although it is not exclusively the case. CHIN does not recommend using this node to record the association with a religious order which should be recorded using the Community node as it revolves around an individual conviction and faith in the truthfulness of specific beliefs more so than belonging to the group itself. Polities’ official structures can take the form of different political units such as civil or local government bodies, tribal assemblies, band councils, etc. Although polities often have control over a geographic area or resources, it is not always the case.
* **Community**: This node indicates the status of belonging to a group or social unit with common norms, values, customs, practices, and identities, along with shared beliefs, preferences, needs, and risks. This belonging does not have to be formalized through a governmental body; it revolves around participation and fellowship although official belonging can occur, such as in the case of religious communities. Four major elements can be used to assess the belonging to a community: membership (the actor shares a sense of personal relatedness), influence (the actor matters to the group and the group matters to the actor), reinforcement (the group contributes to the integration of the actor and the fulfillment of their needs), and emotional connection.
* **Group Type**: This node conceptually characterizes organizations in order to categorize them in ensembles based on their formally or informally stated mission or function. This refers to two broad categories of groups, each with more precise forms: social groups (crew, gang, team, etc.) and organizational groups (museum, university, company, government, etc.).

## Bibliography

Bekiari, Chryssoula, George Bruseker, Martin Doerr, Christian-Emil Ore, Stephen Stead, and Athanasios Velios, eds. *Definition of the CIDOC Conceptual Reference Model*. CIDOC CRM Documentations, 7.1. Paris, FR-IDF: CIDOC CRM Special Interest Group, 2021.[http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf](http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf).

–––. "P190 Has Symbolic Content." *Definition of the CIDOC Conceptual Reference Model*. CIDOC CRM Documentations, 7.1. Paris, FR-IDF: CIDOC CRM Special Interest Group, 2021. [http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf](http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf).

–––. "About Types." *Definition of the CIDOC Conceptual Reference Model*. CIDOC CRM Documentations, 7.1.1. Paris, FR-IDF: International Council of Museums (ICOM), 2021. [http://www.cidoc-crm.org/sites/default/files/cidoc_crm_v.7.1.1.pdf)](http://www.cidoc-crm.org/sites/default/files/cidoc_crm_v.7.1.1.pdf).

Brickley, Dan, and R. V. Guha. "rdfs:comment." *RDF Schema 1.1.*. W3C Recommendation, February 25, 2014. [https://www.w3.org/TR/rdf-schema/#ch_comment](https://www.w3.org/TR/rdf-schema/#ch_comment).

–––. "rdfs:label." *RDF Schema 1.1.*. W3C Recommendation, February 25, 2014. [https://www.w3.org/TR/rdf-schema/#ch_label](https://www.w3.org/TR/rdf-schema/#ch_label).

Bruseker, George. "Principles for Modelling Ontologies: A Short Reference Guide." *Parthenos Project* 17 (2017): 72.

Doerr, Martin, and Christian Emil Ore, eds. *Definition of the CIDOC Conceptual Reference Model*. CIDOC CRM Documentations, 7.0.1. Paris, FR-IDF: International Council of Museums (ICOM), 2020. [http://www.cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.0.1_%2018-10-2020.pdf](http://www.cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.0.1_%2018-10-2020.pdf).

FORTH-ICS. *CRMpc 1.0*. 2014. [http://www.cidoc-crm.org/sites/default/files/CRMpc_v1.0.rdfs](http://www.cidoc-crm.org/sites/default/files/CRMpc_v1.0.rdfs).

Gruber, Thomas R. "Toward Principles for the Design of Ontologies Used for Knowledge Sharing?" *International Journal of Human-Computer Studies* 43, no. 5 (1995): 907–28. [https://doi.org/10.1006/ijhc.1995.1081](https://doi.org/10.1006/ijhc.1995.1081).

Le Bœuf, Patrick, Martin Doerr, Christian Emil Ore, and Stephen Stead, eds. "E33 Linguistic Object." *Definition of the CIDOC Conceptual Reference Model*. CIDOC CRM Documentations, 6.2.1. Paris, FR-IDF: International Council of Museums (ICOM), 2015. [http://www.cidoc-crm.org/sites/default/files/cidoc\_crm\_version\_6.2.1.pdf](http://www.cidoc-crm.org/sites/default/files/cidoc_crm_version_6.2.1.pdf).

–––. "E39 Actor." *Definition of the CIDOC Conceptual Reference Model*. CIDOC CRM Documentations, 6.2.1. Paris, FR-IDF: International Council of Museums (ICOM), 2015. [http://www.cidoc-crm.org/sites/default/files/cidoc\_crm\_version\_6.2.1.pdf](http://www.cidoc-crm.org/sites/default/files/cidoc_crm_version_6.2.1.pdf).

–––. "E74 Group." *Definition of the CIDOC Conceptual Reference Model*. CIDOC CRM Documentations, 6.2.1. Paris, FR-IDF: International Council of Museums (ICOM), 2015. [http://www.cidoc-crm.org/sites/default/files/cidoc\_crm\_version\_6.2.1.pdf](http://www.cidoc-crm.org/sites/default/files/cidoc_crm_version_6.2.1.pdf).

–––. "P3 Has Note." *Definition of the CIDOC Conceptual Reference Model*. CIDOC CRM Documentations, 6.2.1. Paris, FR-IDF: International Council of Museums (ICOM), 2015. [http://www.cidoc-crm.org/sites/default/files/cidoc\_crm\_version\_6.2.1.pdf](http://www.cidoc-crm.org/sites/default/files/cidoc_crm_version_6.2.1.pdf).

Linked.art. "Actors: People and Organizations." *Linked.art*. December 11, 2019. [https://linked.art/model/actor/#types](https://linked.art/model/actor/#types).

The Getty Research Institute. "Photographers." *The Getty Vocabularies*. The Getty Research Institute, April 10, 2018. [http://vocab.getty.edu/aat/300025687](http://vocab.getty.edu/aat/300025687).

