---
layout: page
language: en
title: Social Bonds
permalink: /en/target-model/current/social-bonds
other_link: /fr/modele-cible/actuel/introduction
sidebar: tm
---
<!-- [Back to the Table of Contents](/collections-model/en/target-model/current/information#table-of-contents)
 -->


## Relationships

One of the most important facets of actor documentation is the associations between people and groups, whether it is family and friends or other consequential relationships. It is therefore crucial to model those relationships in a precise, meaningful, and flexible manner.

The CIDOC CRM ontology does not have classes or properties intended to manage the relationships between actors, mainly because it is oriented towards objects. Other ontologies have tried to deal with this issue, most notably Bio CRM [(Tuominen, Hyvönen, and Leskinen 2017)](/collections-model/en/target-model/current/bibliography#tuominen-hyvonen-and-leskinen-2017) or AgRelOn [(Löhden 2019)](/collections-model/en/target-model/current/bibliography#lohden-2019), but their approaches are not satisfactory (see [Appendix D: Relationships](/collections-model/en/target-model/current/appendix-d-relationships#) for a more detailed explanation). CIDOC CRM SIG has started to work on a new extension of CIDOC CRM to tackle social aspects, called CRM Soc [(CIDOC CRM Special Interest Group 2020)](/collections-model/en/target-model/current/bibliography#cidoc-crm-special-interest-group-2020). However promising, this project has not yet been completed and will probably be usable only later on. Meanwhile, this model has to handle relationships appropriately. 

The property of property module, developed by CIDOC CRM SIG, offers a series of classes based on properties (the Property Class) in order to add properties on properties that have been made into classes. For example, the new module makes it possible to add a `P14.1_in_the_role_of` on the property `P14_carried_out_by` that is now the class `PC14_Carried_out_by`, thus typing the role of the actor when committing an act.

This is mostly useful to model the role of an actor in the production of an artefact (see the chapter [Artefacts](/collections-model/en/target-model/current/artefacts#)), but it can also be used to type the role of an actor within a relationship.

In order to do so, relationships have to be considered as activities performed consciously or unconsciously by `E39_Actors`. Being unconscious of performing an activity could be seen as going against the scope note of `E7_Activity` because it has to be performed intentionally. However, since the `E5_Event`‘s properties does not allow the modeling of roles, we opted to go with an `E7_Activity` for the moment. As such, they are modeled using the class `E7_Activity` linked to the `E39_Actors` involved using the property class `PC14_Carried_out_by`. The latter is then assigned a type with the property `P14.1_in_the_role_of` and an `E55_Type` specifying the roles of each party involved, as shown in the following diagram:

<a name="056_Pattern_Relationships_p"></a>056_Pattern_Relationships_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=056_Pattern_Relationships_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1ubl5sPbPNStjDaQ3Io5y0I2p6S6flVg8%26export%3Ddownload"></iframe>


The use of this pattern has a few advantages as it: 

* Is compliant with CIDOC CRM, which ensures consistency within the model;
* Does not require the creation of new classes, which is best for reusability;
* Is a symmetric pattern so that it does not structurally induce an artificial hierarchy between the actors that would misrepresent their relationship;
* Is bi-directional so that Actor A being linked to Actor B is as true as Actor B being linked to Actor A. 

| ![GitHub Mark](https://user-images.githubusercontent.com/48293227/104475587-49182180-558d-11eb-87fc-9f95190cb332.png) *Related Github Issue*<br/><br/>This topic is discussed in [Issue #16](https://github.com/chin-rcip/chin-rcip/issues/16) as well as mentioned when examining [Birth/Death and Formation/Dissolution patterns](/collections-model/en/target-model/current/life-events#birthdeath-of-people-and-formationdissolution-of-groups) |


| 💡  Example:<br/><br/>Jean Paul Riopelle met the group Les Surréalistes when living in Paris in 1947; he was greatly influenced by the group throughout his life. |

<a name="057_Example_RelationshipInfluenceRiopelle_p"></a>057_Example_RelationshipInfluenceRiopelle_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=057_Example_RelationshipInfluenceRiopelle_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1QSSMYclP3kQctxGyGYBRuenW0fVVMXJB%26export%3Ddownload"></iframe>

| 💡  Example:<br/><br/>Jean Paul Riopelle married Françoise Lespérance, from then on Françoise Riopelle, in 1946. |

<a name="058_Example_RelationshipMarriageRiopelle_p"></a>058_Example_RelationshipMarriageRiopelle_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=058_Example_RelationshipMarriageRiopelle_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1JQWN2UZGBLdBwCsTOSZV511iGGLIlfcQ%26export%3Ddownload"></iframe>

## Group Belonging

CIDOC CRM has specific classes dedicated to rendering group belonging more adequately than with an accumulation of multiple relationships amongst individuals. The `P107_has_current_or_former_member` property establishes a direct link between an `E39_Actor` and an `E74_Group`, but it is not possible to date this membership. In order to do so, `E85_Joining` and `E86_Leaving` events must be added to the pattern. Finally, in order to qualify the type of membership, an `E55_Type` must be added with the `PC144_Joining_with` property.

If the provider’s record documents an `E74_Group` and lists its members, then an `E85_Joining` (and an `E86_Leaving` if needed) will be created for each member (as discussed in the [issue #15](https://github.com/chin-rcip/chin-rcip/issues/15) on GitHub).

When it comes to schooling activities, the current pattern is certainly the most common option as museums describe essentially the fact of being a member of a school rather than the schooling activity itself. However, the [Occupation](https://chin-rcip.github.io/collections-model/en/target-model/current/life-events#occupation) or the [Social Status](https://chin-rcip.github.io/collections-model/en/target-model/current/life-events#social-status) patterns could be used if the input data is not referring to any institution in particular (e.g., this person was a student from 1952 to 1964). To describe the latter, we do not have a consensus on which of these two patterns is the most appropriate one.

<a name="059_Pattern_GroupBelonging_p"></a>059_Pattern_GroupBelonging_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=059_Pattern_GroupBelonging_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1RvtLjlTiHJkl_VU6dlx0SgRBBbteInqc%26export%3Ddownload"></iframe>

| 💡  Example:<br/><br/>A. J. Casson, an artist, joined the Group of Seven in 1923 as a member and remained so until the group's dissolution in 1933. |

<a name="060_Example_GroupBelongingGroup7_p"></a>060_Example_GroupBelongingGroup7_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=060_Example_GroupBelongingGroup7_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D17xazTJlfANMP0MeeYme_hDyyU5hNv_Cp%26export%3Ddownload"></iframe>

| ![GitHub Mark](https://user-images.githubusercontent.com/48293227/104475587-49182180-558d-11eb-87fc-9f95190cb332.png) *Related Github Issue*<br/><br/>This topic is discussed in [Issue #11](https://github.com/chin-rcip/chin-rcip/issues/11) and [Issue #15](https://github.com/chin-rcip/chin-rcip/issues/15) |

> Previous: [Life Events](/collections-model/en/target-model/current/life-events)<br>Next: [Descriptive Information](/collections-model/en/target-model/current/descriptive-information)