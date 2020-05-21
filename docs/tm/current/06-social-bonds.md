---
layout: page
title: Social Bonds
permalink: /target-model/current/social-bonds
---
[Back to the Table of Contents](/target-model/current/information#table-of-contents)

## Relationships

One of the most important facets of actor documentation is the associations between people and groups, whether it is family and friends or other consequential relationships. It is therefore crucial to model those relationships in a precise, meaningful, and flexible manner.

The CIDOC CRM ontology does not have classes or properties intended to manage the relationships between actors, mainly because it is oriented towards objects. Other ontologies have tried to deal with this issue, most notably Bio CRM [(Tuominen, Hyvönen, and Leskinen 2017)](https://www.zotero.org/google-docs/?4Zoaub) or AgRelOn [(Löhden 2019)](https://www.zotero.org/google-docs/?IQ1m1l), but their approaches are not satisfactory (see 

<p id="gdcalert50" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "Appendix D: Relationships"). Did you generate a TOC? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert51">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

[Appendix D: Relationships](#heading=h.csnacbarobb3) for a more detailed explanation). CIDOC CRM SIG has started to work on a new extension of CIDOC CRM to tackle social aspects, called CRM Soc [(CIDOC CRM Special Interest Group 2020)](https://www.zotero.org/google-docs/?lcJHHE). However promising, this project has not yet been completed and will probably be usable only later on. Meanwhile, this model has to handle relationships appropriately. 

The property of property module, developed by CIDOC CRM SIG, offers a series of classes based on properties (the Property Class) in order to add properties on properties that have been made into classes. For example, the new module makes it possible to add a `P14.1 in the role of` on the property `P14 carried out by` that is now the class `PC14 Carried out by`, thus typing the role of the actor when committing an act.

This is mostly useful to model the role of an actor in the production of an artefact (see the chapter 

<p id="gdcalert51" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "Artefact"). Did you generate a TOC? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert52">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

[Artefact](#heading=h.23ckvvd)), but it can also be used to type the role of an actor within a relationship.

In order to do so, relationships have to be considered as activities performed consciously or unconsciously by `E39 Actors`. Being unconscious of performing an activity could be seen as going against the scope note of `E7 Activity` because it has to be performed intentionally. However, since the `E5 Event`‘s properties does not allow the modeling of roles, we opted to go with an `E7 Activity` for the moment. As such, they are modeled using the class `E7 Activity` linked to the `E39 Actors` involved using the property class `PC14 Carried out by`. The latter is then assigned a type with the property `P14.1 in the role of` and an `E55 Type` specifying the roles of each party involved, as shown in the following diagram:



<p id="gdcalert52" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-128.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert53">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-128.png "image_tooltip")


The use of this pattern has a few advantages as it: 



*   Is compliant with CIDOC CRM, which ensures consistency within the model;
*   Does not require the creation of new classes, which is best for reusability;
*   Is a symmetric pattern so that it does not structurally induce an artificial hierarchy between the actors that would misrepresent their relationship;
*   Is bi-directional so that Actor A being linked to Actor B is as true as Actor B being linked to Actor A. 

<table>
  <tr>
   <td>
🔎 
   </td>
   <td><em>To Be Discussed</em>
<p>
CHIN is currently debating whether family relationships (including biological ties) should be modeled using the relationship pattern considering this would entail inconsistencies in the use of fields. 
<p>
This is discussed on <a href="https://github.com/chin-rcip/chin-rcip/issues/16">CHIN’s Github Issue #16</a> as well as mentioned above when examining 

<p id="gdcalert53" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "Birth/Death and Formation/Dissolution patterns"). Did you generate a TOC? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert54">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

<a href="#heading=h.dhrglii4cevr">Birth/Death and Formation/Dissolution patterns</a>. 
   </td>
  </tr>
</table>



```
💡  Example:
Jean Paul Riopelle met the group Les Surréalistes when living in Paris in 1947; he was greatly influenced by the group throughout his life.

```



```
💡  Example:
Jean Paul Riopelle married Françoise Lespérance, from then on Françoise Riopelle, in 1946.

```



### Group Belonging

CIDOC CRM has specific classes dedicated to rendering group belonging more adequately than with an accumulation of multiple relationships amongst individuals. The `P107 has current or former member` property establishes a direct link between an `E39 Actor` and an `E74 Group`, but it is not possible to date this membership. In order to do so, `E85 Joining` and `E86 Leaving` events must be added to the pattern. Finally, in order to qualify the type of membership, an `E55 Type` must be added with the `PC144 Joining with` property.

If the provider’s record documents an `E74 Group` and lists its members, then an `E85 Joining` (and an `E86 Leaving` if needed) will be created for each member (as discussed in the [issue #15](https://github.com/chin-rcip/chin-rcip/issues/15) on GitHub).



<p id="gdcalert54" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-129.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert55">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-129.png "image_tooltip")



```
💡  Example:
A. J. Casson, an artist, joined the Group of Seven in 1923 as a member and remained so until the group's dissolution in 1933.

```



<table>
  <tr>
   <td>🔎 
   </td>
   <td><em>To Be Discussed</em>
<p>
CHIN is currently debating whether attending school should be modeled as being a member of the school or university’s group.
<p>
Likewise, being a member of any company or institution (such as a professor in a University) should also be modeled according to this pattern.
<p>
This is discussed on <a href="https://github.com/chin-rcip/chin-rcip/issues/11">CHIN’s Github Issue #11</a>. 
   </td>
  </tr>
</table>



<table>
  <tr>
   <td>🔎 
   </td>
   <td><em>To Be Discussed</em>
<p>
Museums sometimes document groups by recording their members in a list. As such, they do not document which actors joined and left the group, and when. In such cases, a pattern such as <code>&lt;Group A> CHIN:hasMember &lt;Actor B></code> might be preferable in order to account for joining and leaving events of Actor B. 
<p>
This is discussed on <a href="https://github.com/chin-rcip/chin-rcip/issues/15">CHIN’s Github Issue #15</a>. 
   </td>
  </tr>
</table>