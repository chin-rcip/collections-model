---
layout: page
title: Artefacts
permalink: /target-model/current/artefacts
---
[Back to the Table of Contents](/target-model/current/information#table-of-contents)

## Artefact Creation and the Role of the Actor in the Creation

The [CRM extension module “property of properties”](http://www.cidoc-crm.org/sites/default/files/CRMpc_v1.1_0.rdfs) can render the roles of `E39 Actors` during the `E12 Production` event of an `E22 Man-made Object`. The property `P14 carried out by` is replaced by the class `PC14 Carried out by` and an `E55 Type` is assigned to the latter to represent the nature of the actor’s participation to the production of the artefact, whether in terms or their role (e.g. painter) or priority (minor or major). 

A single `E12 Production` event can be attached to an `E22 Man-made Object`, which entails that multiple `E39 Actors` participating to the creation of a single artefact should all be attached to this one `E12 Production` event. If an `E39 Actor` endorses multiple roles in the creation, multiple `E55 Type` should be linked to the single `PC14 Carried out by` class. In addition, the production role of the actor must be linked to them directly so that it can be displayed as their occupation when querying the data. 


<table>
  <tr>
   <td>🔎 
   </td>
   <td><em>To Be Discussed</em>
<p>
CHIN is still debating whether a field should be added to document creations made “in the style of” to account for visual influence with a pattern such as <code>"in the style of" > affiliation</code>. 
   </td>
  </tr>
</table>


.



<p id="gdcalert62" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-135.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert63">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-135.png "image_tooltip")



```
💡  Example:
Jean Paul Riopelle produced the painting "Rue DeLorimier" at some point between 1938 and 1943. As the only maker of the work, he is the sole artist in terms of priority and occupies a "painter" role. 

```


## Artefact (Before the Development of the Objects Facet)

The Objects Facet semantic model will be developed later on.  In the meantime, some core information about artefacts must be modelled as part of Creators in Canada in order for this model to be functional and usable: 



*   Object IDs (the one assigned by CHIN and the ones assigned by museums);
*   Object Appellations; 
*   Object Medium (painting, sculpture, etc.);
*   Object Visuals (when copyrights free); 
*   Production Date;
*   Production Place.

The first three elements, namely appellations and identifiers, follow the same pattern as `E39 Actor` except that there is no need to partition appellations (as was the case for the names of individuals). 

The type of artefact, however, has to be specified using `E55 Type` with the use of a vocabulary like [Nomenclature ](https://www.nomenclature.info/apropos-about.app?lang=en)or the [AAT](https://www.getty.edu/research/tools/vocabularies/aat/).

Finally, the date of fabrication and the place of production are documented using `E12 Production` events.



<p id="gdcalert63" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-136.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert64">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-136.png "image_tooltip")



```
💡  Example:
"Rue DeLorimier" was painted by Jean Paul Riopelle and is in the Montreal Museum of Fine Arts' collection. The identification number assigned by the MMFA is 2004.139 and the one assigned by CHIN is CHIN_001. Its medium is "Painting".

```