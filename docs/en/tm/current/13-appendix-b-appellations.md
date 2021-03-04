---
layout: page
language: en
title: Appendix B - Appellations
permalink: /en/target-model/current/appendix-b-appellations
other_link: /fr/modele-cible/actuel/introduction
sidebar: tm
---
<!-- [Back to the Table of Contents](/collections-model/en/target-model/current/information#table-of-contents)
 -->


The primary identifier of the actor is the URI, but there are other such as the identifier of the providing museum, or others applied by CHIN. The property `P1_is_identified_by` and the class `E42_Identifier` are used in conjunction to render this and a label could be applied to the latter as well. [Linked.art](https://linked.art/model/base/#identifiers) faced the same problems when trying to render the content of resources and proposed to use the property `P190_has_symbolic_content` to display the content of the identifiers.


## Language

CIDOC CRM suggests the use `E41_Appellation` for names but an `E41_Appellation` cannot have a `P72_has_language` tag linked to it, as opposed to the `E33_Linguistic_Object`. Usually, names do not need language tags (Stephen is still written Stephen in French and in English), but some of the most famous ones do (e.g. *Leonardo da Vinci* is *Léonard de Vinci* in French). Moreover, group appellations sometimes change in accordance with the language of their display (e.g. *Museum of Fine Art of Montreal* is *Musée des Beaux-Arts de Montréal* in French). It is possible to add a language label, but adding the language directly to the entity with the property `P72_has_language` would ease the SPARQL requests. It is thus necessary to tag languages to appellations.

Following in the footsteps of linked.art, CHIN could create a new `E33_E41_Linguistic_Appellation` class, a subclass of both `E33_Linguistic_Object` and `E41_Appellation`. This would make it possible to identify an `E39_Actor` with the `P1_is_identified_by` property whilst at the same time adding a language tag with the property `P72_has_language`. It would also be possible to attribute both classes to the `E41_Appellation`, but that would make the pattern unnecessarily complex and complicate the mapping process. 


## Preference

CHIN will not determine the preferred appellation of an actor, but most museums have preferred and alternative names for actors and both should be accounted for in this model. CIDOC CRM has the `P139_has_alternative_form` property and it could be linked to the `E41_Appellation`, but if an actor has many alternative appellations that differs amongst institutions, this pattern would become very complex. 


💡  Example: <br/>
As an example to show the problems with the P139 has alternative form solution, we could have the following case about the appellation of an Actor:  

| | Preferred Appellation | Alternative Appellation | Alternative Appellation | Alternative Appellation |
| --- | --- | --- | --- | --- | 
| Museum_A | Appellation 2 | Appellation 3 | Appellation 4 | Appellation 1 |
| Museum_B | Appellation 2 | Appellation 3 | Appellation 1 | — |
| Museum_C | Appellation 1 | Appellation 2 | Appellation 4 | — | 

The use of the `P139_has_alternative_form` property would entail the following model:

<a name="079_Example_Appellation-1_p"></a>079_Example_Appellation-1_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=079_Example_Appellation-1_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1rWEaZkslgKv8X2ItLoCKJxT5_7utcMwv%26export%3Ddownload"></iframe>

This is complex from a modeling standpoint as the preferred appellation relies on the existence of the alternative appellation. This would significantly complicate SPARQL requests as, when looking for the different appellations of an actor, the same appellation would be unnecessarily present multiple times. Moreover, when looking for a specific appellation, it would be difficult to differentiate between preferred and non-preferred appellations. In other words, the property, and not the vocabulary, would be the carrier of meaning.

Another solution would be to add an `E55_Type` to an `E33_E41_Linguistic_Appellation` to indicate preference based on an authority vocabulary (such as the AAT with the terms “preferred” and “non-preferred”). This would entail the following model: 

<a name="080_Example_Appellation-2_p"></a>080_Example_Appellation-2_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=080_Example_Appellation-2_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D15i1yXBJ2_5nmskHps5yfBCDbjbCKqW12%26export%3Ddownload"></iframe>

Such a pattern would make it easier to know which museum prefers which appellation whilst still displaying alternative names of an `E39_Actor`<sup id="a2">[2](#f2)</sup>.


## Partitioning

All this notwithstanding the fact that most appellations are a concatenation of different smaller appellations (e.g. a person’s name is composed of their first, middle and last names). It would be simpler not to distinguish between such parts, but museum name data is often partitioned so that not representing this could lead to a loss of information. In addition, the possibility to append affixes to the appellation (e.g. Sir or Doctor) might be useful to enable the querying of such information.

There are two options when trying to represent such partitioning: 

The first possibility is to directly distinguish between the different parts of the appellation of the `E39_Actor` by using `P1_is_identified_by`, `E33_E41_Linguistic_Appellation`, and `P2_has_type` and with an `E55_Type_`to specify which part of the name is represented. However, this would make it impossible to know which parts of the non-preferred appellation should be linked together to create a full appellation. 

| 💡  Example: <br/><br/>Considering an artist named Robert John Doe that is also known as Bob Doe and, in addition, uses the pseudonym Alfred, the aforementioned pattern would generate the following representation of information: |

<a name="081_Example_Partitioning-1_p"></a>081_Example_Partitioning-1_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=081_Example_Partitioning-1_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1XEU9ea13wzDUQAYDnOY4cGLumEe2PUp-%26export%3Ddownload"></iframe>

| In such a case, the preferred appellation would remain Robert John Doe, but it would be impossible for the model to generate a full non-preferred appellation as it could not determine whether to select Bob or Alfred as a first name. |


The second possibility, suggested by the [linked.art project](https://linked.art/model/actor/#parts-of-names), is to link the full name to the actor to subsequently partition it with the property `P106_is_composed_of`. 

| 💡  Example: <br/> <br/>Applying the same example to this pattern with amount to the following: |

<a name="082_Example_Partitioning-2_p"></a>082_Example_Partitioning-2_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=082_Example_Partitioning-2_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D11vOUKsQhZld3GyIThlFbY6UJmIpHqs33%26export%3Ddownload"></iframe>

This second option makes it easier to query names, but it has the following problem: just as with the first option it was impossible to reassemble different parts, here it is complicated to correctly divide full appellations; finding a standard way of doing so is problematic and will likely lead to many errors.

As mentioned [above](/collections-model/en/target-model/current/identification#identifiers-and-appellations), the best solution to represent the both the language and the preference whilst still rendering partitioning is to instantiate the `E39_Actor` with both an `E41_Appellation` and an `E33_Linguistic_Object`.

---
<b id="f2">2</b> On the interface, we could simply display the appellation that is used the most as the primary appellation.[↩](#a2)

> Previous: [Appendix A](/collections-model/en/target-model/current/appendix-a-data-provenance)<br>Next: [Appendix C](/collections-model/en/target-model/current/appendix-c-identity)
