---
layout: page
title: Archival Document Location
permalink: /target-model/current/archival-document-location
---
[Back to the Table of Contents](/target-model/current/information#table-of-contents)

## Archival Document Location

Most museums as well as other heritage organisations hold archival records about the creators they document. For example, the [Artists in Canada](https://app.pch.gc.ca/application/aac-aic/description-about.app?lang=en) database documents this information as well as its primary sources. In CIDOC CRM, there is a distinction between information itself and the physical object this information is in (such as a book, a document, etc.). It is therefore necessary to create  an `E22 Man-Made Object` in conjunction with an `E31 Document` in order to document (with the property `P70 documents`) the `E39 Actor`. This pattern enables the localisation of the physical archival document by linking this `E22 Man-Made Object` to an `E53 Place` through a `P54 has current permanent location` property. This also enables the recording of its call number as an `E42 Identifier` along with a `P1 is identified by` property. 

`E73 Information Object` encompasses a large set of concepts that have an “objectively recognizable structure and are documented as single units” [(Doerr and Ore 2019a, 34)](https://www.zotero.org/google-docs/?6DnvdO). However, it is also advised that “instances of `E73 Information Object` of a documentary nature [...] be declared as instances of the `E31 Document` subclass", which is why the latter has been preferred to the former [(Doerr and Ore 2019a, 34)](https://www.zotero.org/google-docs/?jagEsB). 

Note that there is a distinction between the physical location of an institution (e.g. the city, address, or building where it is established—which is documented as an `E53 Place`) and the institution itself (i.e. an `E74 Group`). 



<p id="gdcalert64" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-137.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert65">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-137.png "image_tooltip")



```
💡  Example:
Artists in Canada indicates that Artexte and the University of Calgary Library both have archival documents about Jean Paul Riopelle. The Artexte archival documents have the call number "410 - RIOPELLE, JEAN PAUL"; the University of Calgary call number is unknown. 

```