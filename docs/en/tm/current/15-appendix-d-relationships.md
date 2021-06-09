---
layout: page
language: en
title: Appendix D - Relationships 
permalink: /en/target-model/current/appendix-d-relationships
other_link: /fr/modele-cible/actuel/introduction
sidebar: tm
date: 2021-03-12
description: The Actors Target Model is intended to model the Actors facet of CHIN’s DOPHEDA (that will cover collections data more broadly). Patterns most relevant to actors' lives are presented along with diagrams and examples illustrating them, as well as a record and explanation of relevant decisions that were made when developing said patterns. The current document is a work in progress and, as such, will be enhanced periodically. Elements currently under development or review are listed as issues.
---
<!-- [Back to the Table of Contents](/collections-model/en/target-model/current/information#table-of-contents)
 -->


Few ontologies have tackled the modeling of actors relationships, understood to be an association between different `E39_Actors`, thus creating a network of makers. The CIDOC CRM ontology does not render those ties well, although other options have attempted to do so: 


*   The Agent Relationship Ontology.
*   Bio CRM.

Both are worthy ontologies that have been seriously considered but ultimately discarded for reasons explained below. 


## The Agent Relationship Ontology

The [Agent Relationship Ontology](https://d-nb.info/standards/elementset/agrelon) (AgRelOn), developed by the *Deutsche National Bibliothek*, is designed to describe complex relations amongst people and groups. It uses various properties and classes to render them and could answer the needs of Creators in Canada. Such a model would look like the following: 

<a name="085_Pattern_AgentRelationshipOntology_p"></a>085_Pattern_AgentRelationshipOntology_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=085_Pattern_AgentRelationshipOntology_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1_cpf_EfjysKnsQj-uraIPrNTnBLIKxWu%26export%3Ddownload"></iframe>

However, a property-based ontology entails the modification of the Target Model and the creation of a corresponding property everytime a new type of relationship has to be represented. In addition, a model with so many properties will quickly become overly complicated and hard to manage


## Bio CRM

Two unofficial extensions of CIDOC CRM can handle the relationships between `E39_Actors`: bio CRM and a separate module of CIDOC CRM devoted to properties of properties.

These extensions enable the representation of complex relationships such as that to biological parents in the birth event (see [Birth](/collections-model/en/target-model/current/life-events#birthdeath-of-people-and-formationdissolution-of-groups)), that to a group (see [Group Belonging](/collections-model/en/target-model/current/life-events#group-belonging)) and other relationships described below.

Bio CRM links `bioc:Actor` (a subclass of `E39_Actor`) to a relationship `bioc:Event` (a subclass of `E39_Event`) and specifies the role of the `bioc:Actor` in the relationship through `bioc:Actor_Role` (a direct subclass of `E1_CRM_Entity`) in conjunction with `E55_Type`. By using `E55_Type` with a controlled vocabulary it is possible to represent multiple relationship types without changing the model.

There should therefore be two events representing the beginning of the relationship and its ending: 

<a name="086_Pattern_BioCrm_p"></a>086_Pattern_BioCrm_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=086_Pattern_BioCrm_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1tBQbi30ISiIagVLVcIfO43UJGiYc8MX9%26export%3Ddownload"></iframe>

However, this model may induce querying problems considering two events pertaining to the same relationship are not linked together. As a result, when querying for a list of the different relationships of a Person 1, the same relationship could appear twice:

<a name="087_Pattern_BioCrmPossibleResult_p"></a>087_Pattern_BioCrmPossibleResult_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=087_Pattern_BioCrmPossibleResult_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1pHDrL5_kWi-czv_TBJ8_V74cOsN_-3Qw%26export%3Ddownload"></iframe>

| Actor | Relationship | Actor related |
| --- | --- | --- |
| Person 1 | Event of the beginning of the relationship A | Person 2 |
| Person 1 | Event of the Ending of the relationship A | Person 2 |
| Person 1 | Event of the beginning of the relationship B | Person 2 |
| Person 1 | Event of the Ending of the relationship B | Person 2 |


To connect the two `E5_Events` an remedy this problem, an `E70_Thing` has to be created at the beginning of the relationship as a stand-in for the relationship itself:

<a name="088_Pattern_BioCrmE70Thing_p"></a>088_Pattern_BioCrmE70Thing_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=088_Pattern_BioCrmE70Thing_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1yw5-EP6YmCRsv0BIZOBVNppOxPYf0_bx%26export%3Ddownload"></iframe>

<a name="089_Pattern_BioCrmE70ThingResult_p"></a>089_Pattern_BioCrmE70ThingResult_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=089_Pattern_BioCrmE70ThingResult_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D14Q2srj9E4GAqLi2YbrEu2lriS4wNoxOK%26export%3Ddownload"></iframe>

This would significantly complicate the model by creating for a single relationship both an `E5_Event` and an `E70_Thing` without the latter adding any information that is not already rendered by other entities. In addition, this pattern relies on a role to participate in events, which is problematic in and of itself. 

The property of properties module of CIDOC CRM follows the same logic as bio CRM, but complies with CIDOC CRM semantics and structure:

<a name="090_Pattern_RelationshipCrmBio_p"></a>090_Pattern_RelationshipCrmBio_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=090_Pattern_RelationshipCrmBio_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D19Soi3HhpiGsmM5PM-BYk2ERrafOfW-KK%26export%3Ddownload"></iframe>

<a name="091_Pattern_RelationshipPc14_p"></a>091_Pattern_RelationshipPc14_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=091_Pattern_RelationshipPc14_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1X32X1W_q8AzrAk0yes9Gh7XL87CNo4NH%26export%3Ddownload"></iframe>

CHIN has thus elected to use the Property of property module as it is consistent with the rest of the model, adequately represent every relationship in compliant patterns (parenthood, group membership, etc.), and is more sustainable considering it is widely used by the community and well documented.

> Previous:[Appendix C](/collections-model/en/target-model/current/appendix-c-identity)<br>Next: [Appendix E](/collections-model/en/target-model/current/appendix-e-moving-events)
