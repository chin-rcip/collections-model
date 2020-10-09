---
layout: page
title: Archival Document Location
permalink: /target-model/current/archival-document-location
---
[Back to the Table of Contents](/target-model/current/information#table-of-contents)

## On This Page

* [Archival Document Location](#)

Most museums as well as other heritage organisations hold archival records about the creators they document. For example, the [Artists in Canada](https://app.pch.gc.ca/application/aac-aic/description-about.app?lang=en) database documents this information as well as its primary sources. In CIDOC CRM, there is a distinction between information itself and the physical object this information is in (such as a book, a document, etc.). It is therefore necessary to create  an `E22 Man-Made Object` in conjunction with an `E31 Document` in order to document (with the property `P70 documents`) the `E39 Actor`. This pattern enables the localisation of the physical archival document by linking this `E22 Man-Made Object` to an `E53 Place` through a `P54 has current permanent location` property. This also enables the recording of its call number as an `E42 Identifier` along with a `P1 is identified by` property. 

`E73 Information Object` encompasses a large set of concepts that have an “objectively recognizable structure and are documented as single units” [(Doerr and Ore 2019a, 34)](/target-model/current/bibliography#doerr-and-ore-2019a). However, it is also advised that “instances of `E73 Information Object` of a documentary nature [...] be declared as instances of the `E31 Document` subclass", which is why the latter has been preferred to the former [(Doerr and Ore 2019a, 34)](/target-model/current/bibliography#doerr-and-ore-2019a). 

Note that there is a distinction between the physical location of an institution (e.g. the city, address, or building where it is established—which is documented as an `E53 Place`) and the institution itself (i.e. an `E74 Group`). 

<a name="083_Pattern_IdentityWithEvent_p"></a>083_Pattern_IdentityWithEvent_p
<iframe frameborder="0" style="width:100%;height:500px;" src="https://viewer.diagrams.net/?highlight=0000ff&edit=_blank&layers=1&nav=1&title=074_Pattern_DocumentLocation_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1KHjjLjchjT6wIcKq8gZaY9FCjK6ItKr4%26export%3Ddownload"></iframe>


| 💡  Example:<br/><br/>Artists in Canada indicates that Artexte and the University of Calgary Library both have archival documents about Jean Paul Riopelle. The Artexte archival documents have the call number "410 - RIOPELLE, JEAN PAUL"; the University of Calgary call number is unknown. |

<a name="084_Pattern_IdentityWithOreAggregation_p"></a>084_Pattern_IdentityWithOreAggregation_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?highlight=0000ff&edit=_blank&layers=1&nav=1&title=075_Example_DocumentLocationRiopelle_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1xyt3QFP1G0blmWAjTEzOcI8NubU66AqG%26export%3Ddownload"></iframe>
