---
layout: page
title: Appendix D - Relationships 
permalink: /target-model/current/appendix-d-relationships
---
[Back to the Table of Contents](/target-model/current/information#table-of-contents)

Few ontologies have tackled the modeling of actors relationships, understood to be an association between different `E39 Actors`, thus creating a network of makers. The CIDOC CRM ontology does not render those ties well, although other options have attempted to do so: 



*   The Agent Relationship Ontology.
*   Bio CRM.

Both are worthy ontologies that have been seriously considered but ultimately discarded for reasons explained below. 


## The Agent Relationship Ontology

The [Agent Relationship Ontology](https://d-nb.info/standards/elementset/agrelon) (AgRelOn), developed by the _Deutsche National Bibliothek_, is designed to describe complex relations amongst people and groups. It uses various properties and classes to render them and could answer the needs of Creators in Canada. Such a model would look like the following: 



<p id="gdcalert73" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-143.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert74">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-143.png "image_tooltip")


However, a property-based ontology entails the modification of the Target Model and the creation of a corresponding property everytime a new type of relationship has to be represented. In addition, a model with so many properties will quickly become overly complicated and hard to manage


## Bio CRM

Two unofficial extensions of CIDOC CRM can handle the relationships between `E39 Actors`: bio CRM and a separate module of CIDOC CRM devoted to properties of properties.

These extensions enable the representation of complex relationships such as that to biological parents in the birth event (see 

<p id="gdcalert74" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "Birth"). Did you generate a TOC? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert75">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

[Birth](#heading=h.dhrglii4cevr)), that to a group (see 

<p id="gdcalert75" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "Group Belonging"). Did you generate a TOC? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert76">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

[Group Belonging](#heading=h.cnjof86v1w0s)) and other relationships described below.

Bio CRM links `bioc:Actor` (a subclass of `E39 Actor`) to a relationship `bioc:Event` (a subclass of `E39 Event`) and specifies the role of the `bioc:Actor` in the relationship through `bioc:Actor_Role` (a direct subclass of `E1 CRM Entity`) in conjunction with `E55 Type`. By using `E55 Type` with a controlled vocabulary it is possible to represent multiple relationship types without changing the model.

There should therefore be two events representing the beginning of the relationship and its ending: 



<p id="gdcalert76" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-144.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert77">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-144.png "image_tooltip")


However, this model may induce querying problems considering two events pertaining to the same relationship are not linked together. As a result, when querying for a list of the different relationships of a Person 1, the same relationship could appear twice:



<p id="gdcalert77" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-145.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert78">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-145.png "image_tooltip")



<table>
  <tr>
   <td>Actor
   </td>
   <td>Relationship
   </td>
   <td>Actor related
   </td>
  </tr>
  <tr>
   <td rowspan="4" >Person 1
   </td>
   <td>Event of the beginning of the relationship A
   </td>
   <td>Person 2
   </td>
  </tr>
  <tr>
   <td>Event of the Ending of the relationship A
   </td>
   <td>Person 2
   </td>
  </tr>
  <tr>
   <td>Event of the beginning of the relationship B
   </td>
   <td>Person 2
   </td>
  </tr>
  <tr>
   <td>Event of the Ending of the relationship B
   </td>
   <td>Person 2
   </td>
  </tr>
</table>


To connect the two `E5 Events` an remedy this problem, an `E70 Thing` has to be created at the beginning of the relationship as a stand-in for the relationship itself:



<p id="gdcalert78" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-146.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert79">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-146.png "image_tooltip")




<p id="gdcalert79" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-147.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert80">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-147.png "image_tooltip")


This would significantly complicate the model by creating for a single relationship both an `E5 Event` and an `E70 Thing` without the latter adding any information that is not already rendered by other entities. In addition, this pattern relies on a role to participate in events, which is problematic in and of itself. 

The property of properties module of CIDOC CRM follows the same logic as bio CRM, but complies with CIDOC CRM semantics and structure:



<p id="gdcalert80" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-148.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert81">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-148.png "image_tooltip")




<p id="gdcalert81" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-149.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert82">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-149.png "image_tooltip")


CHIN has thus elected to use the Property of property module as it is consistent with the rest of the model, adequately represent every relationship in compliant patterns (parenthood, group membership, etc.), and is more sustainable considering it is widely used by the community and well documented.