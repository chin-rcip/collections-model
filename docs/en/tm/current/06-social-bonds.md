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

The CIDOC CRM ontology does not have classes or properties intended to specifically manage the relationships between actors, mainly because it is oriented towards objects. Other ontologies have tried to deal with this issue, most notably Bio CRM [(Tuominen, Hyvönen, and Leskinen 2017)](/collections-model/en/target-model/current/bibliography#tuominen-hyvonen-and-leskinen-2017) or AgRelOn [(Löhden 2019)](/collections-model/en/target-model/current/bibliography#lohden-2019), but their approaches are not satisfactory (see [Appendix D: Relationships](/collections-model/en/target-model/current/appendix-d-relationships#) for a more detailed explanation). The issues pertaining to such social aspects of documentation are currently examined by the CIDOC Conceptual Reference Model Social Extension (CRMsoc) [(CIDOC CRM Special Interest Group 2020)](/collections-model/en/target-model/current/bibliography#cidoc-crm-special-interest-group-2020). 

Meanwhile, [property-classes](/collections-model/en/target-model/current/general-concepts#property-classes) (often called PC) have been developed by the CRM SIG in 2014 as part of an extension that enables the reification of specific properties (i.e. they have been transformed into classes) so that instances of these property-classes can become the subject of other triples without compromising the logics of the rest of the ontology. For example, a new class, called `PC14_Carried_Out_By` can be used instead of the property `P14_carried_out_by`. An instance of that `PC14_Carried_Out_By` can then be qualified with a role through the property `P14.1_carried_out_by`, which enables a more precise documentation of relationships between actors.  This extension makes it possible to use a `P14.1_in_the_role_of` property on the property-class `PC14_Carried_Out_By` (reification of `P14_carried_out_by`) thus qualifying the role an actor enacts in a specific context.

This is useful when modelling the role of an actor in the production of an artefact (see [Artefacts](/collections-model/en/target-model/current/artefacts#)), but it can also be used to type the role of an actor within a relationship.

In order to do so, relationships have to be considered as activities (performed consciously or unconsciously) by `E39_Actors`. Being unconscious of performing an activity could arguably be considered to go against the scope note of `E7_Activity` which dictates that the activity must be performed intentionally. However, the other option to model relationships would be to use an `E5_Event` whose properties do not enable the modelling of roles, thus compromising significantly on the granularity of the information that could be accomodated by such a pattern. As such, it seems preferable to use `E7_Activity` until CRMsoc develops a more suitable framework to the representation of relationships. The `E7_Activity` is linked to the `E39_Actor`s involved using the property class `PC14_Carried_Out_By` which is assigned a type with the property `P14.1_in_the_role_of` and an `E55_Type` specifying the role of each party involved, as shown in the following diagram:

<a name="056_Pattern_Relationships_p"></a>056_Pattern_Relationships_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=056_Pattern_Relationships_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1ubl5sPbPNStjDaQ3Io5y0I2p6S6flVg8%26export%3Ddownload"></iframe>


The use of this pattern has a few advantages as it: 

* Is compliant with CIDOC CRM, thus ensuring consistency within the model;
* Does not require the creation of new classes, which is best for reusability;
* Is an egalitarian pattern that does not structurally induce an artificial hierarchy between actors;
* Is bi-directional so that Actor A being linked to Actor B is as true as Actor B being linked to Actor A. 

| ![GitHub Mark](https://user-images.githubusercontent.com/48293227/104475587-49182180-558d-11eb-87fc-9f95190cb332.png) *Related Github Issue*<br/><br/>This topic is discussed in [Issue #16](https://github.com/chin-rcip/chin-rcip/issues/16) as well as mentioned when examining [Birth/Death and Formation/Dissolution patterns](/collections-model/en/target-model/current/life-events#birthdeath-of-people-and-formationdissolution-of-groups) |


| 💡  Example:<br/><br/>Jean Paul Riopelle met the group Les Surréalistes when living in Paris in 1947; he was greatly influenced by the group throughout his life. |

<a name="057_Example_RelationshipInfluenceRiopelle_p"></a>057_Example_RelationshipInfluenceRiopelle_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=057_Example_RelationshipInfluenceRiopelle_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1QSSMYclP3kQctxGyGYBRuenW0fVVMXJB%26export%3Ddownload"></iframe>

| 💡  Example:<br/><br/>Jean Paul Riopelle married Françoise Lespérance, from then on Françoise Riopelle, in 1946. |

<a name="058_Example_RelationshipMarriageRiopelle_p"></a>058_Example_RelationshipMarriageRiopelle_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=058_Example_RelationshipMarriageRiopelle_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1JQWN2UZGBLdBwCsTOSZV511iGGLIlfcQ%26export%3Ddownload"></iframe>

## Group Belonging

CIDOC CRM has specific classes dedicated to rendering group belonging more adequately than with an accumulation of multiple relationships amongst individuals. The `P107_has_current_or_former_member` property establishes a direct link between an `E39_Actor` and an `E74_Group`, but it is not possible to date this membership. In order to do so, `E85_Joining` and `E86_Leaving` events must be added to the pattern. Finally, in order to qualify the type of membership, an `E55_Type` must be added with the `PC144_Joining_With` property.

If the provider’s record documents an `E74_Group` and lists its members, then an `E85_Joining` (and an `E86_Leaving` if needed) will be created for each member (as discussed in the [issue #15](https://github.com/chin-rcip/chin-rcip/issues/15) on GitHub).

When it comes to schooling occupations, this pattern should be used when the information pertains to an individual being a *member* of a school rather than their schooling *activity*. If it is not the case and the *the input data is not referring to any institution in particular* but rather to the activity of being in school (e.g., this person was a student from 1952 to 1964), either the [Occupation](https://chin-rcip.github.io/collections-model/en/target-model/current/life-events#occupation) or [Social Status](https://chin-rcip.github.io/collections-model/en/target-model/current/life-events#social-status) patterns should be used, although there is no consensus yet on which one would be best.

<a name="059_Pattern_GroupBelonging_p"></a>059_Pattern_GroupBelonging_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=059_Pattern_GroupBelonging_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1RvtLjlTiHJkl_VU6dlx0SgRBBbteInqc%26export%3Ddownload"></iframe>

| 💡  Example:<br/><br/>A. J. Casson, an artist, joined the Group of Seven in 1923 as a member and remained so until the group's dissolution in 1933. |

<a name="060_Example_GroupBelongingGroup7_p"></a>060_Example_GroupBelongingGroup7_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=060_Example_GroupBelongingGroup7_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D17xazTJlfANMP0MeeYme_hDyyU5hNv_Cp%26export%3Ddownload"></iframe>

| ![GitHub Mark](https://user-images.githubusercontent.com/48293227/104475587-49182180-558d-11eb-87fc-9f95190cb332.png) *Related Github Issue*<br/><br/>This topic is discussed in [Issue #11](https://github.com/chin-rcip/chin-rcip/issues/11) and [Issue #15](https://github.com/chin-rcip/chin-rcip/issues/15) |

> Previous: [Life Events](/collections-model/en/target-model/current/life-events)<br>Next: [Descriptive Information](/collections-model/en/target-model/current/descriptive-information)
