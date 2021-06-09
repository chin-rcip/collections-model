---
layout: page
language: en
title: Artefacts
permalink: /en/target-model/current/artefacts
other_link: /fr/modele-cible/actuel/introduction
sidebar: tm
date: 2021-03-12
description: The Actors Target Model is intended to model the Actors facet of CHIN’s DOPHEDA (that will cover collections data more broadly). Patterns most relevant to actors' lives are presented along with diagrams and examples illustrating them, as well as a record and explanation of relevant decisions that were made when developing said patterns. The current document is a work in progress and, as such, will be enhanced periodically. Elements currently under development or review are listed as issues.
---
<!-- [Back to the Table of Contents](/collections-model/en/target-model/current/information#table-of-contents)
 -->


## Artefact Creation and the Role of the Actor in the Creation

The [CRM extension module “property of properties”](http://www.cidoc-crm.org/sites/default/files/CRMpc_v1.1_0.rdfs) can render the roles of `E39_Actor` instances during the `E12_Production` event of an `E22_Human-made_Object`. The property `P14_carried_out_by` is replaced by the class `PC14_Carried_Out_By` and an `E55_Type` is assigned to the latter to represent the nature of the actor’s participation in the production of the artefact, whether in terms or their role (e.g. painter) or priority (minor or major). 

A single `E12_Production` event can be attached to an `E22_Human-made_Object`, which entails that several `E39_Actor` (all participating to the creation of a single artefact) should be attached to this one `E12_Production` event. If an `E39_Actor` endorses multiple roles in the creation, multiple `E55_Type` should be linked to the single `PC14_Carried_Out_By`. In addition, the production role of the actor must be linked to them directly so that it can be displayed as their occupation when querying the data. 


| 🔎  *To Be Discussed*<br/><br/>CHIN is still debating whether a field should be added to document creations made “in the style of” to account for visual influence with a pattern such as <code>"in the style of" > affiliation</code>. |

<a name="070_Pattern_Production_p"></a>070_Pattern_Production_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=070_Pattern_Production_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1CBIaxjeW5CySxVQIx-1d7uZ52nA0Bj9O%26export%3Ddownload"></iframe>

| 💡  Example:<br/><br/>Jean Paul Riopelle produced the painting "Rue DeLorimier" at some point between 1938 and 1943. As the only maker of the work, he is the sole artist in terms of priority and occupies a "painter" role. |

<a name="071_Example_ProductionRueDelorimier_p"></a>071_Example_ProductionRueDelorimier_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=071_Example_ProductionRueDelorimier_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1sJga3epp53BIis47FFLwGTQMw16RYivt%26export%3Ddownload"></iframe>

## Artefact (Before the Development of the Objects Facet)

Until the Objects facet of this model is developed, core information about artefacts must be modelled, notably: 

* [Object IDs](/collections-model/en/semantic-paths-specification/current/entry-nodes#object-id) (the ID assigned by CHIN as well as others assigned by providers);
* [Object appellations](/collections-model/en/semantic-paths-specification/current/entry-nodes#object-appellation); 
* [Object medium](/collections-model/en/semantic-paths-specification/current/entry-nodes#object-medium) (painting, sculpture, etc.);
* [Object image](/collections-model/en/semantic-paths-specification/current/entry-nodes#object-image-url)(when available and copyrights free); 
* [Production date](/collections-model/en/semantic-paths-specification/current/entry-nodes#production-date-begin);
* [Production place](/collections-model/en/semantic-paths-specification/current/entry-nodes#production-place).

The first two elements, namely identifiers and appellations, follow the same identifying patterns as `E39_Actor` except that there is no need to partition appellations (as was the case for the name of individuals). 

The type of artefact, however, has to be specified using an `E55_Type` along with a vocabulary such as [Nomenclature](https://www.nomenclature.info/apropos-about.app?lang=en)or the [AAT](https://www.getty.edu/research/tools/vocabularies/aat/).

Finally, the production date and place are documented using `E12_Production` events.


<a name="072_Pattern_Artefact_p"></a>072_Pattern_Artefact_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=072_Pattern_Artefact_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1HOzruVJyvSI96F3Ilt0mbNz7bX9obV1K%26export%3Ddownload"></iframe>

| 💡  Example:<br/><br/>"Rue DeLorimier" was painted by Jean Paul Riopelle and is in the Montreal Museum of Fine Arts' collection. The identification number assigned by the MMFA is 2004.139 and the one assigned by CHIN is CHIN_001. Its medium is "Painting". |

<a name="073_Example_ArtefactRueDelorimier_p"></a>073_Example_ArtefactRueDelorimier_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=073_Example_ArtefactRueDelorimier_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1V0V1_hxMdS8hVhseVFdmEldhp5sb-Fvv%26export%3Ddownload"></iframe>


> Previous: [Descriptive Information](/collections-model/en/target-model/current/descriptive-information)<br>Next: [Archival Document Location](/collections-model/en/target-model/current/archival-document-location)
