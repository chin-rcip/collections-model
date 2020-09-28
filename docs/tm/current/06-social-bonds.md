---
layout: page
title: Social Bonds
permalink: /target-model/current/social-bonds
---
[Back to the Table of Contents](/target-model/current/information#table-of-contents)

## On This Page

* [Relationships](#relationships)
* [Group Belonging](#group-belonging)


## Relationships

One of the most important facets of actor documentation is the associations between people and groups, whether it is family and friends or other consequential relationships. It is therefore crucial to model those relationships in a precise, meaningful, and flexible manner.

The CIDOC CRM ontology does not have classes or properties intended to manage the relationships between actors, mainly because it is oriented towards objects. Other ontologies have tried to deal with this issue, most notably Bio CRM [(Tuominen, Hyvönen, and Leskinen 2017)](/target-model/current/bibliography#tuominen-hyvonen-and-leskinen-2017) or AgRelOn [(Löhden 2019)](/target-model/current/bibliography#lohden-2019), but their approaches are not satisfactory (see [Appendix D: Relationships](/target-model/current/appendix-d-relationships/target-model/current/appendix-d-relationships#) for a more detailed explanation). CIDOC CRM SIG has started to work on a new extension of CIDOC CRM to tackle social aspects, called CRM Soc [(CIDOC CRM Special Interest Group 2020)](/target-model/current/bibliography#cidoc-crm-special-interest-group-2020). However promising, this project has not yet been completed and will probably be usable only later on. Meanwhile, this model has to handle relationships appropriately. 

The property of property module, developed by CIDOC CRM SIG, offers a series of classes based on properties (the Property Class) in order to add properties on properties that have been made into classes. For example, the new module makes it possible to add a `P14.1 in the role of` on the property `P14 carried out by` that is now the class `PC14 Carried out by`, thus typing the role of the actor when committing an act.

This is mostly useful to model the role of an actor in the production of an artefact (see the chapter [Artefacts](/target-model/current/artefacts#)), but it can also be used to type the role of an actor within a relationship.

In order to do so, relationships have to be considered as activities performed consciously or unconsciously by `E39 Actors`. Being unconscious of performing an activity could be seen as going against the scope note of `E7 Activity` because it has to be performed intentionally. However, since the `E5 Event`‘s properties does not allow the modeling of roles, we opted to go with an `E7 Activity` for the moment. As such, they are modeled using the class `E7 Activity` linked to the `E39 Actors` involved using the property class `PC14 Carried out by`. The latter is then assigned a type with the property `P14.1 in the role of` and an `E55 Type` specifying the roles of each party involved, as shown in the following diagram:

<a name="056_Pattern_Relationships_p"></a>056_Pattern_Relationships_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?highlight=0000ff&edit=_blank&layers=1&nav=1&title=056_Pattern_Relationships_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1ubl5sPbPNStjDaQ3Io5y0I2p6S6flVg8%26export%3Ddownload"></iframe>


The use of this pattern has a few advantages as it: 

* Is compliant with CIDOC CRM, which ensures consistency within the model;
* Does not require the creation of new classes, which is best for reusability;
* Is a symmetric pattern so that it does not structurally induce an artificial hierarchy between the actors that would misrepresent their relationship;
* Is bi-directional so that Actor A being linked to Actor B is as true as Actor B being linked to Actor A. 

| 🔎  *To Be Discussed* <br/><br/>CHIN is currently debating whether family relationships (including biological ties) should be modeled using the relationship pattern considering this would entail inconsistencies in the use of fields. <br/><br/>This is discussed on <a href="https://github.com/chin-rcip/chin-rcip/issues/16">CHIN’s Github Issue #16</a> as well as mentioned above when examining [Birth/Death and Formation/Dissolution patterns](/target-model/current/life-events#birthdeath-of-people-and-formationdissolution-of-groups) | 


| 💡  Example:<br/><br/>Jean Paul Riopelle met the group Les Surréalistes when living in Paris in 1947; he was greatly influenced by the group throughout his life. |

<a name="057_Example_RelationshipInfluenceRiopelle_p"></a>057_Example_RelationshipInfluenceRiopelle_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?highlight=0000ff&edit=_blank&layers=1&nav=1&title=057_Example_RelationshipInfluenceRiopelle_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1QSSMYclP3kQctxGyGYBRuenW0fVVMXJB%26export%3Ddownload"></iframe>

| 💡  Example:<br/><br/>Jean Paul Riopelle married Françoise Lespérance, from then on Françoise Riopelle, in 1946. |

<a name="058_Example_RelationshipMarriageRiopelle_p"></a>058_Example_RelationshipMarriageRiopelle_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?highlight=0000ff&edit=_blank&layers=1&nav=1&title=058_Example_RelationshipMarriageRiopelle_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1JQWN2UZGBLdBwCsTOSZV511iGGLIlfcQ%26export%3Ddownload"></iframe>

## Group Belonging

CIDOC CRM has specific classes dedicated to rendering group belonging more adequately than with an accumulation of multiple relationships amongst individuals. The `P107 has current or former member` property establishes a direct link between an `E39 Actor` and an `E74 Group`, but it is not possible to date this membership. In order to do so, `E85 Joining` and `E86 Leaving` events must be added to the pattern. Finally, in order to qualify the type of membership, an `E55 Type` must be added with the `PC144 Joining with` property.

If the provider’s record documents an `E74 Group` and lists its members, then an `E85 Joining` (and an `E86 Leaving` if needed) will be created for each member (as discussed in the [issue #15](https://github.com/chin-rcip/chin-rcip/issues/15) on GitHub).

<a name="059_Pattern_GroupBelonging_p"></a>059_Pattern_GroupBelonging_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?highlight=0000ff&edit=_blank&layers=1&nav=1&title=059_Pattern_GroupBelonging_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1RvtLjlTiHJkl_VU6dlx0SgRBBbteInqc%26export%3Ddownload"></iframe>

| 💡  Example:<br/><br/>A. J. Casson, an artist, joined the Group of Seven in 1923 as a member and remained so until the group's dissolution in 1933. |

<a name="060_Example_GroupBelongingGroup7_p"></a>060_Example_GroupBelongingGroup7_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?highlight=0000ff&edit=_blank&layers=1&nav=1&title=060_Example_GroupBelongingGroup7_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D17xazTJlfANMP0MeeYme_hDyyU5hNv_Cp%26export%3Ddownload"></iframe>

| 🔎  *To Be Discussed* <br/><br/>CHIN is currently debating whether attending school should be modeled as being a member of the school or university’s group.<br/><br/>Likewise, being a member of any company or institution (such as a professor in a University) should also be modeled according to this pattern.<br/><br/>This is discussed on <a href="https://github.com/chin-rcip/chin-rcip/issues/11">CHIN’s Github Issue #11</a>. |


| 🔎  *To Be Discussed* <br/><br/>Museums sometimes document groups by recording their members in a list. As such, they do not document which actors joined and left the group, and when. In such cases, a pattern such as <code>&lt;Group A> CHIN:hasMember &lt;Actor B></code> might be preferable in order to account for joining and leaving events of Actor B. <br/><br/>This is discussed on <a href="https://github.com/chin-rcip/chin-rcip/issues/15">CHIN’s Github Issue #15</a>. |

