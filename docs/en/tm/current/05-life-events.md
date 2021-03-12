---
layout: page
language: en
title: Life Events
permalink: /en/target-model/current/life-events
other_link: /fr/modele-cible/actuel/introduction
sidebar: tm
---
<!-- [Back to the Table of Contents](/collections-model/en/target-model/current/information#table-of-contents)
 -->


## Technique Used

The modelisation of the production of artefacts ([see section below](/collections-model/en/target-model/current/artefacts#artefact-creation-and-the-role-of-the-actor-in-the-creation)) documents some information pertaining to the role of the actor as well as the technique used to produce the object.

Because museums often document the techniques used by an actor by linking this information to said actor instead of linking it to the production of (an) artefact(s), an `E55_Type` has to be created in order to specify the technique and link it directly to the actor with the property `P2_has_type`.

There is a difference between a technique used by an actor, and the activity or occupation this actor could have in his life. For example, an actor A could be a painter, and use the technique watercolor but also have used once the technique sculpture, without being a sculptor. For the occupation, [see below](#occupation).

<a name="031_Pattern_TechniqueUsed_p"></a>031_Pattern_TechniqueUsed_p
<iframe frameborder="0" style="width:100%;height:400px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=031_Pattern_TechniqueUsed_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1ZJr-_XW99UqZvNS86dt0-jTtnE9U4sEj%26export%3Ddownload"></iframe>


| 🔎  *To Be Discussed* <br/> <br/> CHIN is aware that this pattern is not ideal as it implies that an <code>E39_Actor</code> is a Technique. When this pattern was developed, there was no other way of representing the use of a technique by a creator in CIDOC CRM. However, two alternatives are currently being developed and could be leveraged at a later date: <a href="https://github.com/linked-art/linked.art/issues/237#issuecomment-611035443">Linked.Art’s  E13_Attribute_Assignment relationship strategy</a> or <a href="http://www.cidoc-crm.org/crmsoc/sites/default/files/CRMsoc_20190326.pdf">CRMsoc’s Phase class</a>. |

| 💡  Example: <br/><br/> In the case of Jean Paul Riopelle, the artist used the technique "drawing" and "painting". |

<a name="032_Example_TechniqueRiopelle_p"></a>032_Example_TechniqueRiopelle_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=032_Example_TechniqueRiopelle_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1J6xdsEQbGPeXh6Ba10CGEWGj1oGnfBd4%26export%3Ddownload"></iframe>

## Occupation

As we have seen in the Technique Used section ([see above](#technique-used)), some information pertaining to the role of an actor can be documented when modeling the production of (an) artefact(s) ([see section below](/collections-model/en/target-model/current/artefacts#artefact-creation-and-the-role-of-the-actor-in-the-creation)).

But an actor could also have an occupation that is not linked to any production event and there is a difference between the role of an actor during a production event and an occupation in life (a person could be the writer during the production of a book, but their main occupation could be painter).

There is also a difference between an occupation, like being a musician (even without being employed) and employment as an individual part of an `E74_Group` (for example a musician in an orchestra). Such employment is modeled following the group belonging pattern explained [below](/collections-model/en/target-model/current/social-bonds#group-belonging).

In order to account for these intricacies, the occupation is modeled with the class `F51_Pursuit` (from the CIDOC CRM extension of [FRBR](https://en.wikipedia.org/wiki/Functional_Requirements_for_Bibliographic_Records), [FRBRoo](http://www.cidoc-crm.org/frbroo/)) which is an event that is `P14_carried_out_by` the `E39_Actor`. This `F51_Pursuit` occupation is then typed to specify which kind of occupation it is (paintor, sculptor, artist, etc.).

When it comes to schooling activities, the [Group Belonging](https://chin-rcip.github.io/collections-model/en/target-model/current/social-bonds#group-belonging) pattern is certainly the most common option as museums describe essentially the fact of being a member of a school rather than the schooling activity itself. However, the current pattern could be used if the input data is not referring to any institution in particular (e.g., this person was a student from 1952 to 1964). To describe the latter, we do not have a consensus whether this pattern or the [Social Status](https://chin-rcip.github.io/collections-model/en/target-model/current/life-events#social-status) one should be used.


| ![GitHub Mark](https://user-images.githubusercontent.com/48293227/104475587-49182180-558d-11eb-87fc-9f95190cb332.png) *Related Github Issue*<br/><br/>This topic is discussed in [Issue #27](https://github.com/chin-rcip/chin-rcip/issues/27), [Issue #28](https://github.com/chin-rcip/chin-rcip/issues/28), and [Issue #29](https://github.com/chin-rcip/chin-rcip/issues/29) |

<a name="033_Pattern_Occupation_p"></a>033_Pattern_Occupation_p
<iframe frameborder="0" style="width:100%;height:400px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=033_Pattern_Occupation_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1JdZ7dhPt4eJBHDCstGVxmGL-Gnoa-jpa%26export%3Ddownload"></iframe>

| 💡  Example: <br/><br/>In the case of Jean Paul Riopelle, the creator is documented as holding the Painter profession in Montreal and in Paris, from 1940 until his death. |

<a name="034_Example_OccupationRiopelle_p"></a>034_Example_OccupationRiopelle_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=034_Example_OccupationRiopelle_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1S9omimGEnTJfBxKD1Dz8oM88f0F5oayJ%26export%3Ddownload"></iframe>	

## Social Status

Whilst actors have professional or artistic occupations, people also hold social status(es), like being a leader, an Indigenous Community elder, or a knight. These cannot be modeled as occupations because they are not *pursued* per se and do not fit the scope of `F51_Pursuit`.

[CIDOC CRM-Soc](http://www.cidoc-crm.org/crmsoc/) will have a class called “Phase” that may document such statuses, but it is still in development. In the meantime, the best way to model social statuses is to use an `E7_Activity` class carried out by the `E39_Actor` holding said status. 

When it comes to schooling activities, the [Group Belonging](https://chin-rcip.github.io/collections-model/en/target-model/current/social-bonds#group-belonging) pattern is certainly the most common option as museums describe essentially the fact of being a member of a school rather than the schooling activity itself. However, the current pattern could be used if the input data is not referring to any institution in particular (e.g., this person was a student from 1952 to 1964). To describe the latter, we do not have a consensus whether this pattern or the [Occupation](https://chin-rcip.github.io/collections-model/en/target-model/current/life-events#occupation) one should be used.

<a name="035_Pattern_SocialStatus_p"></a>035_Pattern_SocialStatus_p
<iframe frameborder="0" style="width:100%;height:400px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=035_Pattern_SocialStatus_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1lKwj0Jw_ggXprABA7UFszDHHtMW7RALq%26export%3Ddownload"></iframe>


| 💡  Example: <br/><br/> Jean Paul Riopelle became, in 1969, officer of the Order of Canada and, in 1975, companion of the Order of Canada. |

<a name="036_Example_SocialStatusRiopelle_p"></a>036_Example_SocialStatusRiopelle_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=036_Example_SocialStatusRiopelle_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1AOUj5hq0L2QjthOcexP02kcRzzKsB146%26export%3Ddownload"></iframe>

| ![GitHub Mark](https://user-images.githubusercontent.com/48293227/104475587-49182180-558d-11eb-87fc-9f95190cb332.png) *Related Github Issue*<br/><br/>This topic is discussed in [Issue #27](https://github.com/chin-rcip/chin-rcip/issues/27) |


## Flourishing dates

The flourishing dates of an artist or maker are often an important piece of information for museums. In terms of modeling, the flourishing period is not an `E7_Activity` as the `E39_Actor` is not actively carrying his flourishing; it is rather an arbitrary event decided by other people (usually historians) so that it has been represented as an `E5_Event`. 

The `E39_Actor` is a participant (modeled with the property `P11_has_participant`) of this `E5_Event` and this same event is typed as a flourishing event. This event can of course be situated chronologically and geographically.

<a name="037_Pattern_Flourishing_p"></a>037_Pattern_Flourishing_p
<iframe frameborder="0" style="width:100%;height:400px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=037_Pattern_Flourishing_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1ip83XvCu8RkvZO6FIWrilHE1kREJbl6r%26export%3Ddownload"></iframe>

| 💡  Example: <br/><br/> Cyril Henry Barraud, an English painter who participated in World War I as a war artist of the Canadian army is considered by Artists in Canada to have flourished between 1913 and 1915. |

<a name="038_Example_FlourishingBarraud_p"></a>038_Example_FlourishingBarraud_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=038_Example_FlourishingBarraud_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D18obAQnuK0LsfdYZEHTKND5nE4sJ2exgs%26export%3Ddownload"></iframe>

## Specific traits

Most of the museums have unique fields to document specific collections or objects. How to deal with such types of information has not yet been determined. 


| ![GitHub Mark](https://user-images.githubusercontent.com/48293227/104475587-49182180-558d-11eb-87fc-9f95190cb332.png) *Related Github Issue*<br/><br/>This topic is discussed in [Issue #19](https://github.com/chin-rcip/chin-rcip/issues/19)<br/><br/>And... <br/><br/>This topic is discussed in [Issue #29](https://github.com/chin-rcip/chin-rcip/issues/29) |


## Artistic Movements

At the moment CHIN is unsure whether it should or needs to model artistic movements


| ![GitHub Mark](https://user-images.githubusercontent.com/48293227/104475587-49182180-558d-11eb-87fc-9f95190cb332.png) *Related Github Issue*<br/><br/>This topic is discussed in [Issue #21](https://github.com/chin-rcip/chin-rcip/issues/21) |


## Birth/Death of People and Formation/Dissolution of Groups

The Birth/Death and Formation/Dissolution patterns are modeled following the same pattern based on the logic of CIDOC CRM where there are events for the creation and ending of an `E39_Actor`. With this pattern, it is possible to date and place each of these events.

The use of an `E67_Birth` event also enables linking to the biological mother of the `E39_Actor` with the property `P96_by_mother`, and to their biological father with the property `P97_from_father`. These two `E21_Person` only represent *biological* parents and any other type of parenthood (adoptive parents, etc.) should be rendered through relationships.

For more details on this, please see [Appendix F: Discussions, Birth/Death of People and Formation/Dissolution of Groups](/collections-model/en/target-model/current/appendix-f-discussions#discussion-birthdeath-of-people-and-formationdissolution-of-groups).


| ![GitHub Mark](https://user-images.githubusercontent.com/48293227/104475587-49182180-558d-11eb-87fc-9f95190cb332.png) *Related Github Issue*<br/><br/>This topic is discussed in [Issue #16](https://github.com/chin-rcip/chin-rcip/issues/16) |


Any `E39_Actor` can carry out `E66_Formation` and `E67_Dissolution` events so that an `E74_Group` can be responsible for the creation of another `E74_Group`. 

The main challenge when it comes to the death of a person is accounting for the location of the remains of the deceased. Such locations as graves are sometimes recorded, most notably in WikiData, so that it appears best to model them despite the fact that CIDOC CRM does not easily render such data. 

There are two ways to model such information: 


*   with an `E24_Physical_Human-Made_Thing` representing the grave; 
*   through a move of the `E21_Person` to his grave place after his death.

The main challenge with creating an `E24_Physical_Human-Made_Thing` to represent the grave is to link this `E24_Physical_Human-Made_Thing` with the `E21_Person` as there is no simple way to do so.

Representing the post-death move of the `E21_Person` to their grave through an `E9_Move` event is easier to model, but it is conceptually problematic as a dead person is no longer an `E21_Person` capable of carrying out activities such as moving. The logic of CIDOC CRM dictates the creation of a new `E20_Biological_Object` to replace the `E21_Person`, but that considerably and unnecessarily complicates the model. 

In the absence of a simple solution, the `E9_Move` event has been chosen to represent the location of the grave, without creating a new `E20_Biological_Object` in place of the `E21_Person`. Technically, it would be necessary to create an `E5_Event` to represent the transformation of the `E21_Person` into an `E18_Physical_Thing` through an `E81_transformation` so that it is not induced that the person was buried alive. Because of the complexity and heaviness such a pattern would entail, CHIN has decided to compromise on semantic preciseness and to adopt a simpler model, assuming actors will be buried whilst dead.

The [project linked.art](https://linked.art/model/actor/#birth-and-death-formation-and-dissolution) came to the same conclusion and stated that:

| “After death, people are still instances of Person which is a subclass of Actor, even though they can no longer carry out activities. People in comas or otherwise completely incapacitated also cannot carry out activities, but are not temporarily non-Actors. The modeling that death is a transformation from an instance of Person to an instance of Thing adds complexity for the sake of purity, but does not add any actual value. Thus a burial activity ([aat:300263485](http://vocab.getty.edu/aat/300263485)) buries a Person, not a Thing-that-used-to-be-a-Person. However if the skeleton is then dug up and exhibited, it is exhibited as a Thing. There is, therefore, a transition at some undetermined point.” |

Modeling the Birth and Death of an `E21_Person` looks like the following: 

<a name="039_Pattern_BirthDeath_p"></a>039_Pattern_BirthDeath_p
<iframe frameborder="0" style="width:100%;height:800px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=039_Pattern_BirthDeath_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D107d_h_4kMQ-nrshmNQv2YpY3ZFIMXs-j%26export%3Ddownload"></iframe>


| 💡  Example: <br/><br/>Jean Paul Riopelle was born on the 7th of October 1923 in Montreal to Anna Riopel and Léon-Léopold Riopelle. |

<a name="040_Example_BirthRiopelle_p"></a>040_Example_BirthRiopelle_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=040_Example_BirthRiopelle_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1M0Q5jD-SWHU_iKtFPHxwsEFMMzlzBHI5%26export%3Ddownload"></iframe>

| He died on the 12th of March 2002 at Saint-Antoine-de-l'Isle-aux-Grues and is buried in Montreal. |

<a name="041_Example_DeathRiopelle_p"></a>041_Example_DeathRiopelle_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=041_Example_DeathRiopelle_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1a2ZBTCGa0jLIp0H4oEzajA_DiQcILXGL%26export%3Ddownload"></iframe>

Modeling the Formation and Dissolution of an `E74_Group` looks like the following: 

<a name="042_Pattern_GroupFormationDissolution_p"></a>042_Pattern_GroupFormationDissolution_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=042_Pattern_GroupFormationDissolution_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1P7hRu-rR8y22b1OOxripnPIqsD4pP2BW%26export%3Ddownload"></iframe>


| 💡  Example: <br/><br/>The Group of Seven was founded by Lawren Harris on the 7th of May 1920 in Toronto. |

<a name="043_Example_GroupFormationGroup7_p"></a>043_Example_GroupFormationGroup7_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=043_Example_GroupFormationGroup7_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1Vd_pEQrS7u3GNzAuoFUxFJWaMCwL2YWN%26export%3Ddownload"></iframe>

| The Group was dissolved at an unknown date in 1936. |

<a name="044_Example_GroupDissolutionGroup7_p"></a>044_Example_GroupDissolutionGroup7_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=044_Example_GroupDissolutionGroup7_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1dkBdOT-qsRlOExyyhH059njZD6kXc5jS%26export%3Ddownload"></iframe>

## Moving events

Throughout their lives or activities, `E39_Actors` may travel, live or be present in various locations that are relevant to document. 

In CIDOC CRM, there is a distinction between the physical `E21_Person` that is located in space and can be subjected to `E9_Move` events, and the more abstract `E39_Actor` and `E74_Group` that do not move through space and time.

In order to record the locations of persons and groups, additional patterns are required:

1. An `E8_Acquisition` event to record properties acquired by groups
2. And `E7_Activity` pattern to model the stays of `E21_Person` and `E74_Group` in different locations.

For more on this, please see [Appendix E: Moving Events](/collections-model/en/target-model/current/appendix-e-moving-events#) and [Github Issue #31](https://github.com/chin-rcip/collections-model/issues/31).

### Legal Headquarter Attribution

*This pattern will be reviewed*

Companies’ legal and official headquarters must also be documented. This is something that could be done using the `E13_attribute_assignment` class with the following pattern, although it is still under consideration and might change:

<!-- <a name="045_Pattern_HQAssignment_p"></a>045_Pattern_HQAssignment_p -->
<!-- <iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=045_Pattern_HQAssignment_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D14PlQX6U990zXPxPxtp8tvf44vqeQm3TR%26export%3Ddownload"></iframe> -->

### `E7_Activity` Stay for `E21_Person` and `E74_Group`

*Internal note: VR begins*

In most cases, our stakeholders record the fact of being somewhere instead of the moving event. Therefore, the way of modeling the locations where an `E39_Actor` went is to have an `E7_Activity`. In this instance, stays encompass any location where an `E39_Actor` has stayed, including their customary residence, and are not limited to vacations or travels.

In order to do so, the `E7_Activity` event is used and a “Stay” type is attributed to it. This same `E7_Activity` is then situated geographically and temporally.

*Internal note: VR ends*

<a name="052_Pattern_Stay_p"></a>052_Pattern_Stay_p
<iframe frameborder="0" style="width:100%;height:400px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=052_Pattern_Stay_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D14N5th3YJ8tDZgVLeoW3kGLba2y5Mpm84%26export%3Ddownload"></iframe>

| 💡  Example:<br/><br/>Jean Paul Riopelle moved to Paris in 1947 before coming back to Montreal in 1948 and going once again to Paris in December 1948: |

<a name="053_Example_StayRiopelle_p"></a>053_Example_StayRiopelle_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=053_Example_StayRiopelle_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1dYngkqVWXFgBsBXpRzl64Dg6if24g60B%26export%3Ddownload"></iframe>

| 💡  Example:<br/><br/>The Group of Seven met at the Studio Building in Toronto—a building where several artist studios were situated. As we do not know of other places where these artists met on a regular basis, this is the only location associated with the group during its activity years, from 1920 to 1933. |

<a name="054_Example_StayGroup7_p"></a>054_Example_StayGroup7_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=054_Example_StayGroup7_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1NQIujp5uqqjfTH59NpusPjNKwDoX4n-s%26export%3Ddownload"></iframe>

## Influences

A creator might have been influenced by many things in their creative lives. These include people as well as other entities such as events or objects. However, CIDOC CRM traditionally represents influence through a relationship pattern articulated around associations between `E39_Actors`. To account for the richness of influences when it comes to creative endeavours, a different approach must be adopted as entities other than `E39_Actors` might influence a creator (events, styles, etc.). 

The `P15_was_influenced_by` property has an `E7_Activity` as a domain and any `E1_CRM_Entity` as a range. It is meant to render things that have an influence on any activity, but not on people so that using it in conjunction with `E39_Actor` goes against its scope.

At the moment (version 2.1 of the TM), we do not have a pattern to render influences of non-actors on actors.

<!-- <a name="055_Pattern_Influences_p"></a>055_Pattern_Influences_p -->
<!-- <iframe frameborder="0" style="width:100%;height:400px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=055_Pattern_Influences_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1KNO27qQ2axy07E1sO5H3AV45y1QLnFPx%26export%3Ddownload"></iframe> -->

| ![GitHub Mark](https://user-images.githubusercontent.com/48293227/104475587-49182180-558d-11eb-87fc-9f95190cb332.png) *Related Github Issue* <br/><br/>This topic is discussed in [Issue #33](https://github.com/chin-rcip/chin-rcip/issues/33) |

> Previous: [Identification](/collections-model/en/target-model/current/identification)<br>Next: [Social Bonds](/collections-model/en/target-model/current/social-bonds)