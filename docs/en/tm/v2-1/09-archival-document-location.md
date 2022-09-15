---
layout: page
language: en
title: Archival Document Location
permalink: /en/target-model/version-2-1/archival-document-location
other_link: /fr/modele-cible/version-2-1/introduction
sidebar: tm21
date: 2021-03-12
description: The Actors Target Model is intended to model the Actors facet of CHIN’s DOPHEDA (that will cover collections data more broadly). Patterns most relevant to actors' lives are presented along with diagrams and examples illustrating them, as well as a record and explanation of relevant decisions that were made when developing said patterns. The current document is a work in progress and, as such, will be enhanced periodically. Elements currently under development or review are listed as issues.
---
<!-- [Back to the Table of Contents](/collections-model/en/target-model/version-2-1/information#table-of-contents)
 -->


Most museums as well as other heritage organisations hold archival records about the creators they document. For example, the [Artists in Canada](https://app.pch.gc.ca/application/aac-aic/description-about.app?lang=en) database documents this information as well as its primary sources. In CIDOC CRM, there is a distinction between information itself and the physical object this information is in (such as a book, a document, etc.). It is therefore necessary to create  an `E22_Human-Made_Object` in conjunction with an `E31_Document` in order to document (with the property `P70_documents`) the `E39_Actor` [institution](/collections-model/en/semantic-paths-specification/version-2-1/entry-nodes#archival-document-institution-appellation) which holds the document. This pattern enables the [localisation of the physical archival document](/collections-model/en/semantic-paths-specification/version-2-1/entry-nodes#archival-document-place) by linking this `E22_Human-Made_Object` to an `E53_Place` through a `P54_has_current_permanent_location` property. This also enables the recording of its [call number](/collections-model/en/semantic-paths-specification/version-2-1/entry-nodes#archival-document-call-number) as an `E42_Identifier` along with a `P1_is_identified_by` property. 

`E73_Information_Object` encompasses a large set of concepts that have an “objectively recognizable structure and are documented as single units” [(Le Boeuf et al. 2015, sec. E73 Information Object)](/collections-model/en/target-model/version-2-1/bibliography#le-boeuf-et-al-2015). However, it is also advised that “instances of `E73_Information_Object` of a documentary nature [...] be declared as instances of the `E31_Document` subclass", which is why the latter has been preferred to the former [(Le Boeuf et al. 2015, sec. E73 Information Object)](/collections-model/en/target-model/version-2-1/bibliography#le-boeuf-et-al-2015). 

Note that there is a distinction between the physical location of an institution (e.g. the city, address, or building where it is established—which is documented as an `E53_Place`) and the institution itself (i.e. an `E74_Group`). 

<a name="074_Pattern_DocumentLocation_p"></a>074_Pattern_DocumentLocation_p
<iframe frameborder="0" style="width:100%;height:500px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=074_Pattern_DocumentLocation_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1KHjjLjchjT6wIcKq8gZaY9FCjK6ItKr4%26export%3Ddownload"></iframe>


| 💡  Example:<br/><br/>Artists in Canada indicates that Artexte and the University of Calgary Library both have archival documents about Jean Paul Riopelle. The Artexte archival documents have the call number "410 - RIOPELLE, JEAN PAUL"; the University of Calgary call number is unknown. |

<a name="075_Example_DocumentLocationRiopelle_p"></a>075_Example_DocumentLocationRiopelle_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=075_Example_DocumentLocationRiopelle_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1xyt3QFP1G0blmWAjTEzOcI8NubU66AqG%26export%3Ddownload"></iframe>


> Previous: [Artefacts](/collections-model/en/target-model/version-2-1/artefacts)<br>Next: [Legal Aspects (Rights)](/collections-model/en/target-model/version-2-1/legal-aspects-rights)
