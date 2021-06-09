---
layout: page
language: en
title: General Concepts
permalink: /en/target-model/current/general-concepts
other_link: /fr/modele-cible/actuel/introduction
sidebar: tm
date: 2021-03-12
description: The Actors Target Model is intended to model the Actors facet of CHIN’s DOPHEDA (that will cover collections data more broadly). Patterns most relevant to actors' lives are presented along with diagrams and examples illustrating them, as well as a record and explanation of relevant decisions that were made when developing said patterns. The current document is a work in progress and, as such, will be enhanced periodically. Elements currently under development or review are listed as issues.
---
<!-- [Back to the Table of Contents](/collections-model/en/target-model/current/information#table-of-contents)
 -->

## Prioritization of `E55_Type` and `P2_has_type` Over New Classes and Properties

CIDOC CRM is meant to facilitate the integration of heterogeneous cultural heritage data. As a result, the entities it offers are intentionally general in scope so that they can be used by professionals from various specialized heritage disciplines. To ensure a model's effectiveness, the technological and human resources necessary to its development, implementation, and maintenance should be kept to a minimum. This is not only done by limiting the field of expertise it represents (Bruseker 2017, 25), but also by avoiding the inclusion of patterns that address *technological* rather than *informational* imperatives (Gruber 1995, 910) by relying on the reuse of pre-existing classes and properties to limit the resources allocated to the creation, documentation, and maintenance of new ones. Yet, because complex concepts (e.g. relationships, techniques, etc.) encompass a variety of facets and characteristics, it is sometimes necessary to further qualify classes in order to facilitate the recording and querying processes. Although the creation of new classes and properties is encouraged by some authoritative institutions, it leads to a bulkier model (hence complexifying the recording process) and a larger number of classes to handle (thus complicating practitioners' queries). The use of a vocabulary to categorize generic entities is thus becoming indreasingly widespread because it requires less resources to rely on external vocabularies than to maintain and manage specialized entities internally (Doerr & al. 2020, xxxviii). Moreover, the use of external vocabularies facilitates interoperability between models as the reconciliation of specialized entities amongst different models is more complicated than that of high-level entities. It also enables organizations to rely on a skillset their professionals already have (i.e. vocabulary management). 

Hence, it appears preferable (and most often doable) to specify entities by using `E55_Type` rather than create new sub-classes and sub-properties. Should this need arise, CHIN intends to work in cooperation with the CRM SIG (or any other committee managing a relevant CIDOC CRM extension) to develop new entities rather than create homemade and local classes and properties. 

<a name="095_Convention_E55_Type_p"></a>095_Convention_E55_Type_p
<iframe frameborder="0" style="width:100%;height:200px;" src="https://viewer.diagrams.net/?highlight=0000ff&edit=_blank&layers=1&nav=1&title=095_Convention_E55_Type_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1zopvBo8SRO48ifxkokg3vJiboOvo35y2%26export%3Ddownload"></iframe>

In addition to this consideration, when several `E55_Type` of different kinds are attached to the same entities, another level of `E55_Type` designates the first `E55_Type` with a second `E55_Type` "metatype" which is used to easily retrieve comparable information at the querying stage.

<a name="096_Convention_E55_Metatype_p"></a>096_Convention_E55_Metatype_p.drawio
<iframe frameborder="0" style="width:100%;height:300px;" src="https://viewer.diagrams.net/?highlight=0000ff&edit=_blank&layers=1&nav=1&title=096_Convention_E55_Metatype_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1JIedt0kZZ2AEaW2nAwcpVoOb8vj00Wtr%26export%3Ddownload"></iframe>
 

## Differences Between `E39_Actor`, `E21_Person` and `E74_Group`

Most heritage data pertaining to individuals or groups centers around the *creators* of artefacts and, as such, the Actors facet is centered around the `E39_Actor` class, which “comprises people, either individually or in groups, who have the potential to perform intentional actions of kinds for which someone may be held responsible” [(Le Boeuf et al. 2015, sec. E39 Actor)](/collections-model/en/target-model/current/bibliography#le-boeuf-et-al-2015). There are two subclasses to `E39_Actor:` `E21_Person`, which comprises real persons; and `E74_Group`, which accounts for any type of gathering or organization of `E39_Actor` acting collectively. As stated in CIDOC CRM, "a gathering of people becomes an `E74_Group` when it exhibits organizational characteristics usually typified by a set of ideas or beliefs held in common, or actions performed together" [(Le Boeuf et al. 2015, sec. E74 Group)](/collections-model/en/target-model/current/bibliography#le-boeuf-et-al-2015). As linked.art points out, the class `E39_Actor` “might be used when it is not certain whether the actor is a Person or an Organisation or Group” [(linked.art 2019b)](/collections-model/en/target-model/current/bibliography#linked-art-2019b).

Some datasets might contain data pertaining to both actors and groups in a single field; in such a case, the use of the `E39_Actor` super-class rather than of its sub-classes is possible (although such a practice should be avoided in order to maintain an efficient mapping process, and cleaning the data would be both preferable and more effective in the long term). For more details on this, please refer to the [Appendix F: Discussions, The Differences Between E39 Actor, E21 Person, and E74 Group](/collections-model/en/target-model/current/appendix-f-discussions#discussion-the-differences-between-e39-actor-e21-person-and-e74-group). 


## Semantic Differences Between Contents, Labels, Notes and Comments, and Descriptive Texts

Literal Heritage data (e.g. text content) can generally be classified into three kinds of strings: 

*   Labels
*   Annotations and comments
*   Literal content

There are various ways to link such data in the context of the model, each of which is intended to account for a specific type of human-readable statement. The choice of which property to assign a resource will determine how data is managed and indicate what kind of statement it is. 

### Labels

Labels are used to provide a human-readable version of a resource’s content in addition to its URI, as well as to handle data in several languages (i.e. labelling a piece of information as being in French or in English for example). They are rendered with the property `rdfs:label`.

<a name="007_Pattern_Labels_p"></a>007_Pattern_Labels_p
<iframe frameborder="0" style="width:100%;height:200px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=007_Pattern_Labels_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D17oAGG4vgPUkCf0Nu3eOVwyMy4swS90a8%26export%3Ddownload"></iframe>

For example, if the occupation of an artist is documented using the AAT and has the URI [`http://vocab.getty.edu/page/aat/300411314`](http://vocab.getty.edu/page/aat/300411314), the “artist painters” label should be added so that humans can understand what that occupation is without going to the Getty website. Another example would be in the case of birth events where concatenation mechanisms (at the mapping stage) can provide useful descriptive labels such as “Birth of Jean Paul Riopelle"; that way, the function of the node is easily understandable to humans.


| 🚩  *Important Information*<br/><br/>Labels can be attached to any resource across the target model but will not be displayed in the diagrams to facilitate readability. |

### Annotations and Comments

Annotations to specific pieces of data—rendered by the CIDOC CRM `P3_has_note` property or by the [`rdfs:comment`](https://www.w3.org/TR/rdf-schema/#ch_comment) property in RDF—are used to describe or comment on a specific resource. 


<a name="008_Pattern_AnnotationsComments_p"></a>008_Pattern_AnnotationsComments_p
<iframe frameborder="0" style="width:100%;height:300px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=008_Pattern_AnnotationsComments_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1pI5Q8RfR8pKTsOM-fZD0dBwe9Z5ThBKL%26export%3Ddownload"></iframe>


`P3_has_note` is used to annotate extra information regarding the provider's *content* once the mapping process is completed (e.g. "the image URL is not valid/working"). If the note comes from the dataset itself, the [Curatorial Note](/collections-model/en/target-model/current/descriptive-information#curatorial-note) pattern must be used. For its part, `rdfs:comments` is used to add comments with regards to *classes* and *properties*. Both `P3_has_note` and `rdfs:comments` make statements *about* the resource’s content and *do not comprise* its content. For example, a `P3_has_note` applied to an `E33_Linguistic_Object` annotates the latter’s text, but does not include it (i.e. it does not contain the `E33_Linguistic_Object` content). 

| 💡  Example: <br/><br/>"Woodwork Construction Ltd." based its name on the owner's previous company name, an information that could be added through an annotation (`P3_has_note`). | 

<a name="009_Example_NoteWoodworkCompany_p"></a>009_Example_NoteWoodworkCompany_p
<iframe frameborder="0" style="width:100%;height:400px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=009_Example_NoteWoodworkCompany_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1j2ssBSw_wLQod0LROH4BxSR12MXomSGM%26export%3Ddownload"></iframe>

For more details on this, please see [Appendix F: Discussions, Semantic Differences Between Contents, Labels, Notes and Comments, and Descriptive Texts](/collections-model/en/target-model/current/appendix-f-discussions#discussion-semantic-differences-between-contents-labels-notes-and-comments-and-descriptive-texts).

The [**Annotation** Entry Nodes](https://chin-rcip.github.io/collections-model/en/semantic-paths-specification/current/entry-nodes#annotation) (`P3_has_note`) should be used in edge cases when something is too complex and subtle to be adequately accounted for by current patterns, and too specific to warrant the creation of a new pattern. Annotations should not be dismissed entirely, but should be used with caution. In the Woodwork example mentioned above, it would also be possible to use `P130_shows_features_of`. 

In the rare cases when something is really extraneous to the model but not to understanding, `P3_has_note` and `rdfs:comment` are valid choices. 

| 🚩  *Important Information*<br/><br/>Unless the creator of the annotation is impacting the model itself by their work, <code>rdfs:comment</code> should not be used and <code>P3 has note</code> should be preferred. |
 

### Literal Content

To represent the linguistic content of a resource—appellations, biographies or descriptions for example—`rdfs:comment` or `rdfs:label` are not suitable. Even though CIDOC CRM previously recommended the use of `P3_has_note` for heritage content [(Le Boeuf et al. 2015, sec. E33 Linguistic Object)](/collections-model/en/target-model/current/bibliography#le-boeuf-et-al-2015), it is no longer the case as `P3_has_note` “is a container for all informal descriptions about an object that have not been expressed in terms of CRM constructs. In particular it captures the characterization of the item itself, its internal structures, appearance, etc.”[(Le Boeuf et al. 2015, sec. P3 Has Note)](/collections-model/en/target-model/current/bibliography#le-boeuf-et-al-2015). To remedy this, CIDOC CRM has developed the `P190_has_symbolic_content` property to associate an instance of `E90_Symbolic_Object` with a representation of its entire content in the form of a string of text [(Le Boeuf et al. 2015, sec. P190 Has Symbolic Content)](/collections-model/en/target-model/current/bibliography#le-boeuf-et-al-2015).


| 💡  Example: <br/><br/>For example, the biography of Jean Paul Riopelle could have:<br/>- a label "Biography of Jean Paul Riopelle";<br/>- a note from the museum assessing the biography, stating that it has to be revised for example; <br/>- the content of the biography.<br/><br/>From a modeling standpoint, this would look like the following: |

<a name="010_Example_LiteralContentBiographyRiopelle_p"></a>010_Example_LiteralContentBiographyRiopelle_p
<iframe frameborder="0" style="width:100%;height:400px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=010_Example_LiteralContentBiographyRiopelle_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D10gUM2Jy9dQyNR8WIURdCtRWary6powUw%26export%3Ddownload"></iframe>

The best way to semantically represent the content of a resource is to use `P190_has_symbolic_content` rather than to rely on a homemade property that would only be used locally. As is often the case with LOD, it is preferable to employ recognized and approved classes and properties rather than create new, “single use” ones.


| ![GitHub Mark](https://user-images.githubusercontent.com/48293227/104475587-49182180-558d-11eb-87fc-9f95190cb332.png) *Related Github Issue*<br/><br/>This topic is discussed in [Issue #37](https://github.com/chin-rcip/chin-rcip/issues/37) |


## Mapping problems and `E33_Linguistic_Object`

If the data of the contributing institution is clean—in other words, if it is not mixing data types and/or contents within single fields—, CHIN’s [Pipeline](https://drive.google.com/open?id=1W_vsT_Br86BRR92SWEqFX90861Nu3mUTmx_fAyuOE5A) along with the [Semantic Paths Specification](/collections-model/en/semantic-paths-specification/current/introduction) and Target Model will successfully translate it from a relational to a semantic framework.  However, if the input data is messy—for example if it mixes different kinds of information within fields or if it contains heterogeneous natural language expressions—, it will not be possible to map it to semantic standards.

In such a case, a standard semantic mapping solution is to create an instance of `E33_Linguistic_Object` that is typed using `E55_Type` in order to: 

* indicate the general kind of information held by the `E33_Linguistic_Object`; 
* distinguish it from other `E33_Linguistic_Objects` such as biographies. 

The language of the content must also be indicated and the data must be instantiated into an `rdfs:Literal` and connected to the `E33_Linguistic_Object` instance through the `P190_has_symbolic_content` property. The instance of `E33_Linguistic_Object` itself should be linked back to the node that it describes using the `P67_refers_to` property. 

<a name="011_Pattern_MappingWithE33LinguisticObject_p"></a>011_Pattern_MappingWithE33LinguisticObject_p
<iframe frameborder="0" style="width:100%;height:400px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=011_Pattern_MappingWithE33LinguisticObject_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1-uzAimbVP_8WtWTXZlU0qUGWu9itlxEj%26export%3Ddownload"></iframe>

| 💡  Example:<br/><br/>For example, a museum could have recorded the birth of Jean Paul Riopelle with the following value:  "le septième jour du mois d'octobre 1923". Such a value could not be mapped as it is not compliant with XSD:Date format requirements. In order to nonetheless retain this information, an E33 Linguistic Object linked to an E52 Time-span can be created, as shown below: |

<a name="012_Example_MappingWithE33LinguisticObjectRiopelleBirth_p"></a>012_Example_MappingWithE33LinguisticObjectRiopelleBirth_p
<iframe frameborder="0" style="width:100%;height:500px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=012_Example_MappingWithE33LinguisticObjectRiopelleBirth_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1rFvm7LSMkLQMMEDGHJ2pJtMpSC5zDVtP%26export%3Ddownload"></iframe>

| Had the value been "07.10.1923", the dates could have been encoded properly using the XSD:DateTime format, as shown below: |

<a name="013_Example_TimeSpanRiopelleBirth_p"></a>013_Example_TimeSpanRiopelleBirth_p
<iframe frameborder="0" style="width:100%;height:500px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=013_Example_TimeSpanRiopelleBirth_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1x8Nml8JxDEPwpRsOBabsrlRov3yJhMOY%26export%3Ddownload"></iframe>


## Property-Classes

In the CIDOC CRM ontology, some properties can be qualified (by making a statement on a property) in order to describe more precisely the nature of the link between two entities. For example, the property `P14_carried_out_by` can be specified to indicate the role in which an actor is carrying out an activity by pointing to a vocabulary term defining this role through the property `P14.1_in_the_role_of`. However, this poses implementation challenges because even though classes can be instantiated in RDF, properties cannot. If the instance of a class can be the subject or the object of a triple these are always linked by the property’s URI itself. Hence, if a link necessitates qualification (e.g. that the carrying out of an activity is made in the context of a role endorsed by an actor in this context), using the property’s URI as subject of this qualifier triple would imply that the property itself is *always* qualified, even in the case of other instances of this property. For example, if a role A is used to specify a `P14_carried_out_by` property linking Actor B and Activity C, other instances of `P14_carried_out_by` would also be linked to this role A.

<a name="097a_PC_ClassesExamples_1_p"></a>097a_PC_ClassesExamples_1_p
<iframe frameborder="0" style="width:100%;height:423px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=097a_PC_ClassesExamples_1_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D11vR6__SHZCNhK0DGOh2jJnetnpp3i28L%26export%3Ddownload"></iframe>

Property-Classes (often called PC) have thus been developed by the CRM SIG in 2014 as part of an extension that enables the reification of specific properties (i.e. they have been transformed into classes) so that instances of these property-classes can become the subject of other triples without compromising the logics of the rest of the ontology.

For example, a new class, called `PC14_Carried_Out_By` can be used instead of the property `P14_carried_out_by`. An instance of that `PC14_Carried_Out_By` can then be qualified with a role through the property `P14.1_carried_out_by`. Because it is the *instance* of the property class that is used as the subject of the triple, the role only applies to that *specific instance*.
In order to link the domain and range of the previously used `P14_carried_out_by`, two new properties (`P01_has_domain` and `P02_has_range`) have been created so that the triple:
```
Actor A → P14_carried_out_by → Activity
```
has been replaced by the following (per the property-classes specification):
```
Actor A ← P01_has_domain ← PC14_Carried_Out_By → P02_has_range → Activity
```

<a name="097b_PC_ClassesExamples_2_p"></a>097b_PC_ClassesExamples_2_p
<iframe frameborder="0" style="width:100%;height:443px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=097b_PC_ClassesExamples_2_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1vqJBTUeb3RvLAvADWxUeLt69-TN51_uM%26export%3Ddownload"></iframe>

The hierarchy of the PC extension dictates that each new property class is a subclass of a root class called `PC0_CRM_Property`. This minimalistic hierarchy, however, does not follow the CRMbase hierarchy conventions according to which some of Pxx.1 properties would inherit the characteristics of their super-properties. For example, `P67.1_has_type` (domain `PC67_Refers_To`) cannot be used with the property-class `PC138_Represents` even though `P138_represents` is sub-property of `P67_refers_to` in CRMbase. In addition, `PC0_CRM_Property` is *not* a sub-class of `E1_CRM_Entity` or of any other CRMbase entity which entails that the property-classes are technically not linked semantically to CIDOC CRM (although their use remains relatively widespread). 

Property-classes used throughout the Target Model are:
- `PC14_Carried_Out_By`in the [Relationships](/collections-model/en/target-model/current/social-bonds#relationships) and [Artefact Production](/collections-model/en/target-model/current/artefacts) patterns;
- `PC138_Represents` in the [Visual Item - Mark pattern](/collections-model/en/target-model/current/descriptive-information#visual-item);
- `PC144_Joined_With` in the [Group Belonging](/collections-model/en/target-model/current/social-bonds#group-belonging) pattern.

## Data Provenance


### Provenance of the Dataset

One of the goals of this project is to aggregate data from Canadian heritage institutions and other relevant sources in a single knowledge graph. Because CHIN will not adjudicate the veracity or value of the information it aggregates (since providers should retain authority over their own data), the provenance of data (i.e. who the provider of the information is) will be crucial to the management of data and of factual agreement and/or disagreement about it. A challenge that arises is that, once the data has been aggregated and deposited into a triplestore—a database for the storage and retrieval of RDF triples—the provenance of said data is lost (i.e. what institution or person contributed it). Loading RDF data into a triplestore thus entails losing the ability to: 

* identify a subset of RDF triples (i.e. to identify their origin);
* determine whether a single triple is asserted once or multiple times (e.g. if a single triple is asserted by separate distinct sources as opposed to several times by a single source, thus asserting it more than once). 

CHIN considers the best way to establish provenance throughout the model is to use named graphs rather than a longer, more complex `E13_Attribute_Assignment` pattern (that would have to be repeatedly assigned to triples, each and every time, and would unnecessarily weigh down the model; for more information about this discarded `E13_Attribute_Assignment` pattern, see the [Appendix A: Data Provenance](/collections-model/en/target-model/current/appendix-a-data-provenance)). Named graphs, however, do not append to *every* triple the source of its information, which makes it impossible to express complex information pertaining to *specific* triples (e.g. indicating that a date attribution is uncertain).

| ![GitHub Mark](https://user-images.githubusercontent.com/48293227/104475587-49182180-558d-11eb-87fc-9f95190cb332.png) *Related Github Issue*<br/><br/>This topic is discussed in [Issue #14](https://github.com/chin-rcip/chin-rcip/issues/14) |

A named graph is a set of RDF triples that receives a fourth statement (the triples then become quadruples, or quads: `<subject> <predicate> <object> <graphname>`). This enables the treatment of the whole graph as a single entity which can receive attributes such as author, provenance, etc.; each triple within this named graph inherits the graph’s information. Named graphs also allow the use of specific subsets of the collected data based on graph identifiers [(Dodds and Davis 2019, 53)](/collections-model/en/target-model/current/bibliography#dodds-and-davis-2019). This is particularly useful because it enables SPARQL queries within specific subsets of a named graph. 

```
 💡  Example: 

// Example to come when we will have a first dataset \\

```

The granularity of the provenance information a dataset structure enables is partly associated with the level (dataset or record) at which named graphs are implemented. A provider’s dataset-based named graph might be better for data provenance documentation and information management, but a more granular record-based named graph can be preferable from a technical standpoint.  A survey on the implementation of named graphs in the CIDOC CRM community has been made in order to better inform CHIN's decision and provide a [technical report](/collections-model/en/technical-reports/current/named-graph-survey-report-1) on the matter to the CRM SIG. Based on its results and discussions with its Semantic Committee, CHIN has decided to implement named graphs at the dataset level for the following reasons:

* This is the most common practice, at least within the CIDOC CRM community;
* This entails a lower technological barrier than a record-based approach, as not all available software and processes might be able to support a more granular record-level structure;
* This prevents the issue of ‘border entities’ (i.e. the shared nodes of multiple entities such as the ‘Birth’ node that is shared between an actor and their parents) since, as all entities from a provider will be placed in a single and shared named graph, information will be uniformely applied;
* Even though there are concerns over the possibility of missing information that might not be included in a query, the entirety of the data provided will be mapped to CHIN's Target Model so that it will not be complicated to set a SPARQL query retrieving the data of a single entity (i.e. all triples pertaining to such entity, mainly an Actor or an Object).


| ![GitHub Mark](https://user-images.githubusercontent.com/48293227/104475587-49182180-558d-11eb-87fc-9f95190cb332.png) *Related Github Issue*<br/><br/>This topic is discussed in [Issue #45](https://github.com/chin-rcip/chin-rcip/issues/45) |


Only CIDOC CRM's entities are used to document the provenance data in the Target Model: the actors involved in the process are connected to the dataset creation event through a `PC14_Carried_Out_By` in order to associate them with their role(s) (`E55_Type`) in the process. From a modelling standpoint, such a collection of data would look like the following: 

<a name="014_Pattern_NamedGraph_p"></a>014_Pattern_NamedGraph_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=014_Pattern_NamedGraph_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1G2MBh4jcxAXv9YUJ-8MVDzLBaowem4EZ%26export%3Ddownload"></iframe>

The example below displays the two main actor roles that CHIN envisions in the context of named graph provenance data: 

* "Provider", used to type the `E39_Actor` responsible for the original dataset (and who has authority over its contents); 
* "Creator", used to type the `E39_Actor` who converts the provider's data into an RDF graph (most often CHIN). 

This pattern is scalable if future processes necessitate new types.

| 💡  Example 1:  <br/><br/>The National Gallery of Canada (NGC)'s data have been mapped to CHIN's Target Model on January 15th 2021. CHIN was in charge of the mapping and the NGC provided the input data. (fictive use case) |

<a name="014a_Example_NamedGraph_p"></a>014a_Example_NamedGraph_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?highlight=0000ff&edit=_blank&layers=1&nav=1&title=014a_Example_NamedGraph_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D185A9nr1WSQdzoCkY_Geiuiroghe1pVBZ%26export%3Ddownload"></iframe>

Such named graphs can be expressed in various syntaxes such as [NQuads](https://www.w3.org/2009/07/NamedGraph.html#syntax-1), [TRiG](https://www.w3.org/2009/07/NamedGraph.html#syntax-1), or [JSON-LD](https://www.w3.org/TR/json-ld11/#named-graphs). Though they cannot be expressed in RDF/XML, they are often represented in this context as additional instances to the usual triples (that thus become quads), although they can sometimes be represented at the beginning of an RDF file such as in the following example: 

```
 💡 Example:

{
  "@context": {
    "rdf": "http://www.w3.org/1999/02/22-rdf-syntax-ns#",
    "rdfs": "http://www.w3.org/2000/01/rdf-schema#",
    "xsd": "http://www.w3.org/2001/XMLSchema#",
    "crm": "http://www.cidoc-crm.org/cidoc-crm/",
    "crmdig": "http://www.ics.forth.gr/isl/CRMext/CRMdig.rdfs/",
    "frbroo": "http://iflastandards.info/ns/fr/frbr/frbroo/"
  },
  "@id": "http://mic.ca/uri/digital_object/001",
  "@type": "crmdig:D1_Digital_Object",
  "@graph": [
    {
      	"@id": "http://mic.ca/uri/actor/9999",
      	"@type": "crm:E21_Person",
      	"crm:P14i_performed": {
	      	"@type": "frbroo:F51_Pursuit",
	      	"crm:P2_has_type": {
			    "@id": "http://mic.ca/occupation/Printmaker",
			    "rdfs:label": "Printmaker",
			    "@type": "crm:E55_Type",
			    "crm:P2_has_type": {
			        "@id": "http://mic.ca/occupation_type/Occupation",
			        "rdfs:label": "Occupation",
			        "@type": "crm:E55_Type"
	      		}
	    	}
	  	}
    }
  	]
}

```

Therefore, when wanting to retrieve provenance data, users must include a graph clause in their SPARQL query. 

### Record Provenance with Aggregated Contributors

Despite its advantages, the dataset-level named graph approach is problematic when aggregating data that has *already* been aggregated. This is the case of datasets such as [Artists in Canada](https://app.pch.gc.ca/application/aac-aic/description-about.app?lang=en), a bilingual union list that identifies the location of documentation files on Canadian artists. Its data is submitted by specific institutions and its content is managed by the National Gallery of Canada whilst CHIN handles its technological maintenance [(National Gallery of Canada / Musée des beaux-arts du Canada 2019a)](/collections-model/en/target-model/current/bibliography#national-gallery-of-canada-musée-des-beaux-arts-du-canada-2019a); [(National Gallery of Canada / Musée des beaux-arts du Canada 2019b)](/collections-model/en/target-model/current/bibliography#national-gallery-of-canada-musée-des-beaux-arts-du-canada-2019b).

In the case of such aggregated provisions, it is mandatory to have a named graph for the provider as a whole in order for users to be able to query specific information from it (for example if someone wants to search only within Artists in Canada).

Thankfully, such aggregators also document the provenance of their data so that the primary provenance of each entry can be identified (e.g. the institution that contributed it to Artists in Canada in the first place and retains authority over its contents).

The easiest way to document such entries is to create an `E73_Information_Object` “record” instance linked to the individual `E39_Actor` it documents through the `P67_refers_to` property. This same `E73_Information_Object` is linked to its record contributor (a different `E39_Actor`) and dated through an `E65_Creation` event.

<a name="015a_Pattern_RecordContributor_Actor_p"></a>015a_Pattern_RecordContributor_Actor_p
<iframe frameborder="0" style="width:100%;height:500px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=015a_Pattern_RecordContributor_Actor_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1rsYOVLMwU_nSctm1Ys_6UA1eCuYcEiT9%26export%3Ddownload"></iframe>

The same pattern is applied to a record instance linked to an artefact (`E22_Human-Made_Object`).

<a name="015b_Pattern_RecordContributor_Artefact_p"></a>015b_Pattern_RecordContributor_Artefact_p
<iframe frameborder="0" style="width:100%;height:500px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=015b_Pattern_RecordContributor_Artefact_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1svxBqY5Heh3oqz0oQ8BFyWZ95jAJYQtv%26export%3Ddownload"></iframe>


| ![GitHub Mark](https://user-images.githubusercontent.com/48293227/104475587-49182180-558d-11eb-87fc-9f95190cb332.png) *Related Github Issue*<br/><br/>This topic is discussed in [Issue #34](https://github.com/chin-rcip/chin-rcip/issues/34) | 


| 💡  Example: <br/><br/>In Artist in Canada, the record of Jean Paul Riopelle indicates that the information comes from the National Gallery of Canada and was created on 1985.03.13 and last modified on 2017.06.05.<br/><br/>As CHIN has not yet determined how to document updates of information (something that will be developed later on), the creation date currently stands for the last modified version of the record. |

<a name="016_Example_ProvenanceNGCRiopelle_p"></a>016_Example_ProvenanceNGCRiopelle_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=016_Example_ProvenanceNGCRiopelle_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D139DPJgQlF_QXGeL7-4wKnjbYTfwyMJzT%26export%3Ddownload"></iframe>


## Challenges When Representing Indigenous Realities 

This project aims to document creators from Canadian institutions such that this Target Model must render most, if not all, of the distinctive characteristics of communities across Canada. This includes communities that are typically underserved by traditional models, most notably Indigenous creators. An overview of current models and vocabularies indicates that they typically adopt a western point of view that does not adequately represent the realities of Indigenous Peoples' lives and artefacts. CHIN, in line with Canadian society's reckoning and path towards reconciliation, considers that respect and deference should be observed when it comes to Indigenous practices and beliefs. Museums are increasingly documenting and exhibiting Indigenous artefacts and this will likely lead, in the years to come, to an increased need for structures that encompass Indigenous characteristics. Thus, special attention will be paid to Indigenous conceptions within the model, particularly when it comes to choosing proper terms to label fields and data. Hopefully, this undertaking will better answer the needs of both Indigenous communities and GLAMs.

For more details on this, please see [Appendix F: Discussions, Challenges When Representing Indigenous Realities](/collections-model/en/target-model/current/appendix-f-discussions#discussion-challenges-when-representing-indigenous-realities).


## Dates pattern

The dating pattern is the same throughout the model. In order to facilitate understanding and reading, it will not be reproduced in the rest of the diagrams of this document.

In CIDOC CRM, only `E2_Temporal_Entities` and its sub-classes (including `E5_Event`), can be situated temporally. This is done through a time-span, modeled with the property `P4_has_time-span` and the class `E52_Time-Span`.

This `E52_Time-Span` can be delimited (using the `xsd:dateTime` standard) with the use of 4 properties representing specific dates: 

* `P82a_begin_of_the_begin_` indicates that the time-span of the event may at the earliest have started on that date;
* `P81a_end_of_the_begin_`indicates that the time-span of the event has without doubt at the latest started on that date;
* `P81b_begin_of_the_end` indicates that the time-span of the event has without doubt lasted at least until this date;
* `P82b_end_of_the_end_`indicates that the time-span of the event may have lasted until that date.

The diagram below illustrates the differences between these 4 properties (see the [CIDOC CRM documentation](http://www.cidoc-crm.org/guidelines-for-using-p82a-p82b-p81a-p81b) for more information about this):

<a name="017_Pattern_E2TemporalEntities_p"></a>017_Pattern_E2TemporalEntities_p
<iframe frameborder="0" style="width:100%;height:400px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=017_Pattern_E2TemporalEntities_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D18Sra-NJR6bdhjLz5xUTFPDuz3Hdd7sNz%26export%3Ddownload"></iframe>

Because the `P82a_begin_of_the_begin` and `P82b_end_of_the_end` properties are the most encompassing delimiters of the event, it is wiser to use them systematically, and to use the properties `P81a_end_of_the_begin` and `P81b_begin_of_the_end` only when such precise information is available and specified as such.

It is also possible to add qualifiers to dates with the properties `P79_beginning_is_qualified_by` and `P80_end_is_qualified_by` in conjunction with an `rdfs:Literal`. Such qualifiers can include commentaries (e.g. presumed date) or typical qualifiers (e.g. circa, BC, etc.). 

The full date pattern is as follows: 

<a name="018_Pattern_FullDate_p"></a>018_Pattern_FullDate_p
<iframe frameborder="0" style="width:100%;height:500px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=018_Pattern_FullDate_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1wN6iq5Mdzg0UMX5N03HRacOlC_tqNLxf%26export%3Ddownload"></iframe>


| 💡  Example:<br/><br/>Pénelope Solette produced a painting that was presented to the public on the 10th of January 1997. Art historians consider she has started producing the work in October of 1996. |

<a name="019_Example_TimeSolette_p"></a>019_Example_TimeSolette_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=019_Example_TimeSolette_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1aW8wIzkXA2ZYrdi2Pru5LQzbX2AiBshk%26export%3Ddownload"></iframe>


> Previous: [Introduction](/collections-model/en/target-model/current/introduction)<br>Next: [Identification](/collections-model/en/target-model/current/identification)
