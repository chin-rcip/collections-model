---
layout: page
title: Appendix C - Identity 
permalink: /target-model/current/appendix-c-identity
---
[Back to the Table of Contents](/target-model/current/information#table-of-contents)

## Appendix C: Identity

As stated in the 

<p id="gdcalert70" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "Identity Patterns section"). Did you generate a TOC? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert71">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

[Identity Patterns section](#heading=h.ukfrff7gaar3), CHIN has decided to use a simple `E55 Type` pattern to identify gender and cultural affiliation whilst `E74 Group` will be used to identify nationality, nationhood and community. The `E55 Type` class will be used in conjunction with it to render what the type of the group is. The following patterns have been rejected for reasons explained below. 


### With `E5 Event`

Identity fields could be represented using an event in the following way: 



<p id="gdcalert71" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-141.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert72">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-141.png "image_tooltip")


However, both `E5 Event` and `E7 Activity` definitions establish that a _performance _has to occur on the part of the actor for them to apply. Neither gender nor community or nationality are _performed _so that handling these concepts as either `E5 Event` or `E7 Activity` would not be in semantic conformity to [CIDOC CRM](http://www.cidoc-crm.org/Entity/e7-activity/version-6.2.2)’s guidelines. This option has thus been dismissed.


### With Bio CRM

Bio CRM proposes another way to render genders and nationalities by linking a `bioc:Actor` with a `bioc:Actor_Role` that is neither an `E5 Event` nor an `E39 Actor`, but a subclass of `E1 CRM Entity`. However, this is not satisfactory as this new class cannot be dated without a `bioc:Event` that functions just as the CIDOC CRM `E5 Event`. This, for the same reasons as with the `E5 Event`, this pattern has been disqualified. 


### With `ore:Aggregation`

In their [discussions about gender and nationality](https://github.com/linked-art/linked.art/issues/152) the linked.art project has suggested to use the OAI-ORE Specifications ([http://www.openarchives.org/ore/1.0/datamodel](http://www.openarchives.org/ore/1.0/datamodel)), an approach that is similar to CIDOC CRM’s `E74 Group` but is composed of aggregated resources.

The ORE ontology is composed of four classes: `ore:Aggregation`, `ore:AggregatedResource`, `ore:ResourceMap` and `ore:Proxy`.



*   The `ore:Aggregation` class is a set of other resources. “They are more conceptual groupings, rather than physical ones” ([https://linked.art/model/collection/#aggregations](https://linked.art/model/collection/#aggregations)) 
*   The `ore:AggregatedResource` class is a resource that is a constituent of an aggregation
*   The `ore:ResourceMap` class is a resource with information consisting of assertions that describe a single aggregation, enumerate the constituent aggregated resources, and may include additional properties about the aggregation and aggregated resources. It must have a minimal number of metadata, at least `dcterms:creator` and `dcterms:modified`. The` ore:ResourceMap` seems mandatory, but neither linked.art ([https://linked.art/model/collection/](https://linked.art/model/collection/)) nor Europeana ([https://pro.europeana.eu/resources/apis/intro](https://pro.europeana.eu/resources/apis/intro)) use an `ore:ResourceMap` in their model.
*   The `ore:Proxy` is a class that links the `ore:AggregatedResource` and the `ore:Aggregation` to qualify the` ore:AggregatedResource` in the context of the aggregation. For example, `ore:Proxy` is used to express sequencing between `ore:AggregatedResource` in an `ore:Aggregation` since “without any sequencing information, the order of Aggregated Resources cannot be inferred — they form an unordered set. It would not be legitimate for the Resource Map to express this sequencing by asserting a triple of the sort `&lt;AR-1> &lt;hasNext> &lt;AR-2>`, since this fact is only true in the context of the specific Aggregation, and is not a "global" fact” ([http://www.openarchives.org/ore/1.0/datamodel#Proxy](http://www.openarchives.org/ore/1.0/datamodel#Proxy)).



<p id="gdcalert72" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-142.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert73">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-142.png "image_tooltip")


This ontology would therefore be appropriate to render the complexity of gender identification and nationalities, but would significantly complicate the Target Model. In addition it would rely on semantics that would be inconsistent with those of CIDOC CRM, rendering this part of the model problematic in the long term. Finally, it is not possible to express the period when the entity is part of the aggregation, so this would not be useful either. As a result, this approach has been dismissed. 


<table>
  <tr>
   <td>💬 <em>Discussion:</em>
   </td>
  </tr>
  <tr>
   <td>
    George Bruseker (18:11 16 Jul): This seems like a very technical solution that provides semantics that are inconsistent with the rest of CRM.
<p>

    George Bruseker (18:13 16 Jul): I would suggest that if you need to tackle this topic in the future that there is a strong argument for a new event class for ‘identification’ of some sort. There are of course a lot of potential debates in this area and some dangerous territory around nature or nurture. That being said there is an element of declarativeness about gender, regardless of its biological status. It is something that people state (otherwise we could not know). If this argument holds water then one could track statements of identification in order to see how gender/sexuality evolves for individuals over time.
   </td>
  </tr>
</table>