---
layout: page
language: en
title: Artefacts
permalink: /en/target-model/current/artefacts
sidebar: tm
---
<!-- [Back to the Table of Contents](/collections-model/en/target-model/current/information#table-of-contents)
 -->
<div class="hidden-content">
## On This Page

* [Artefact Creation and the Role of the Actor in the Creation](#artefact-creation-and-the-role-of-the-actor-in-the-creation)
* [Artefact (Before the Development of the Objects Facet)](#artefact-before-the-development-of-the-objects-facet)
</div>

## Artefact Creation and the Role of the Actor in the Creation

The [CRM extension module “property of properties”](http://www.cidoc-crm.org/sites/default/files/CRMpc_v1.1_0.rdfs) can render the roles of `E39_Actors` during the `E12_Production` event of an `E22_Human-made_Object`. The property `P14_carried_out_by` is replaced by the class `PC14_Carried_out_by` and an `E55_Type` is assigned to the latter to represent the nature of the actor’s participation to the production of the artefact, whether in terms or their role (e.g. painter) or priority (minor or major). 

A single `E12_Production` event can be attached to an `E22_Human-made_Object`, which entails that multiple `E39_Actors` participating to the creation of a single artefact should all be attached to this one `E12_Production` event. If an `E39_Actor` endorses multiple roles in the creation, multiple `E55_Type` should be linked to the single `PC14_Carried_out_by` class. In addition, the production role of the actor must be linked to them directly so that it can be displayed as their occupation when querying the data. 


| 🔎  *To Be Discussed*<br/><br/>CHIN is still debating whether a field should be added to document creations made “in the style of” to account for visual influence with a pattern such as <code>"in the style of" > affiliation</code>. |

<a name="070_Pattern_Production_p"></a>070_Pattern_Production_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=070_Pattern_Production_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1CBIaxjeW5CySxVQIx-1d7uZ52nA0Bj9O%26export%3Ddownload"></iframe>

| 💡  Example:<br/><br/>Jean Paul Riopelle produced the painting "Rue DeLorimier" at some point between 1938 and 1943. As the only maker of the work, he is the sole artist in terms of priority and occupies a "painter" role. |

<a name="071_Example_ProductionRueDelorimier_p"></a>071_Example_ProductionRueDelorimier_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=071_Example_ProductionRueDelorimier_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1sJga3epp53BIis47FFLwGTQMw16RYivt%26export%3Ddownload"></iframe>

## Artefact (Before the Development of the Objects Facet)

The Objects Facet semantic model will be developed later on.  In the meantime, some core information about artefacts must be modelled as part of Creators in Canada in order for this model to be functional and usable: 

* Object IDs (the one assigned by CHIN and the ones assigned by museums);
* Object Appellations; 
* Object Medium (painting, sculpture, etc.);
* Object Visuals (when copyrights free); 
* Production Date;
* Production Place.

The first three elements, namely appellations and identifiers, follow the same pattern as `E39_Actor` except that there is no need to partition appellations (as was the case for the names of individuals). 

The type of artefact, however, has to be specified using `E55_Type` with the use of a vocabulary like [Nomenclature ](https://www.nomenclature.info/apropos-about.app?lang=en)or the [AAT](https://www.getty.edu/research/tools/vocabularies/aat/).

Finally, the date of fabrication and the place of production are documented using `E12_Production` events.


<a name="072_Pattern_Artefact_p"></a>072_Pattern_Artefact_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=072_Pattern_Artefact_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1HOzruVJyvSI96F3Ilt0mbNz7bX9obV1K%26export%3Ddownload"></iframe>

| 💡  Example:<br/><br/>"Rue DeLorimier" was painted by Jean Paul Riopelle and is in the Montreal Museum of Fine Arts' collection. The identification number assigned by the MMFA is 2004.139 and the one assigned by CHIN is CHIN_001. Its medium is "Painting". |

<a name="073_Example_ArtefactRueDelorimier_p"></a>073_Example_ArtefactRueDelorimier_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=073_Example_ArtefactRueDelorimier_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1V0V1_hxMdS8hVhseVFdmEldhp5sb-Fvv%26export%3Ddownload"></iframe>


> Previous: [Descriptive Information](/collections-model/en/target-model/current/descriptive-information)<br>Next: [Archival Document Location](/collections-model/en/target-model/current/archival-document-location)
