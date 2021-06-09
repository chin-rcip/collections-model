---
layout: page
language: en
title: Appendix C - Identity 
permalink: /en/target-model/current/appendix-c-identity
other_link: /fr/modele-cible/actuel/introduction
sidebar: tm
date: 2021-03-12
description: The Actors Target Model is intended to model the Actors facet of CHIN’s DOPHEDA (that will cover collections data more broadly). Patterns most relevant to actors' lives are presented along with diagrams and examples illustrating them, as well as a record and explanation of relevant decisions that were made when developing said patterns. The current document is a work in progress and, as such, will be enhanced periodically. Elements currently under development or review are listed as issues.
---
<!-- [Back to the Table of Contents](/collections-model/en/target-model/current/information#table-of-contents)
 -->


As stated in the [Identity Patterns section](/collections-model/en/target-model/current/identification#identity-patterns), CHIN has decided to use a simple `E55_Type` pattern to identify gender and cultural affiliation whilst `E74_Group` will be used to identify nationality, nationhood and community. The `E55_Type` class will be used in conjunction with it to render what the type of the group is. The following patterns have been rejected for reasons explained below. 


## With `E5_Event`

Identity fields could be represented using an event in the following way: 

<a name="083_Pattern_IdentityWithEvent_p"></a>083_Pattern_IdentityWithEvent_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=083_Pattern_IdentityWithEvent_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1R18JnHXoI0G35ttgQvtt0annpSKRAm4V%26export%3Ddownload"></iframe>

However, both `E5_Event` and `E7_Activity` definitions establish that a *performance* has to occur on the part of the actor for them to apply. Neither gender nor community or nationality are *performed* so that handling these concepts as either `E5_Event` or `E7_Activity` would not be in semantic conformity to [CIDOC CRM](http://www.cidoc-crm.org/Entity/e7-activity/version-6.2.2)’s guidelines. This option has thus been dismissed.


## With Bio CRM

Bio CRM proposes another way to render genders and nationalities by linking a `bioc:Actor` with a `bioc:Actor_Role` that is neither an `E5_Event` nor an `E39_Actor`, but a subclass of `E1_CRM_Entity`. However, this is not satisfactory as this new class cannot be dated without a `bioc:Event` that functions just as the CIDOC CRM `E5_Event`. This, for the same reasons as with the `E5_Event`, this pattern has been disqualified. 


## With `ore:Aggregation`

In their [discussions about gender and nationality](https://github.com/linked-art/linked.art/issues/152) the linked.art project has suggested to use the OAI-ORE Specifications ([http://www.openarchives.org/ore/1.0/datamodel](http://www.openarchives.org/ore/1.0/datamodel)), an approach that is similar to CIDOC CRM’s `E74_Group` but is composed of aggregated resources.

The ORE ontology is composed of four classes: `ore:Aggregation`, `ore:AggregatedResource`, `ore:ResourceMap` and `ore:Proxy`.

*   The `ore:Aggregation` class is a set of other resources. “They are more conceptual groupings, rather than physical ones” ([https://linked.art/model/collection/#aggregations](https://linked.art/model/collection/#aggregations)) 
*   The `ore:AggregatedResource` class is a resource that is a constituent of an aggregation
*   The `ore:ResourceMap` class is a resource with information consisting of assertions that describe a single aggregation, enumerate the constituent aggregated resources, and may include additional properties about the aggregation and aggregated resources. It must have a minimal number of metadata, at least `dcterms:creator` and `dcterms:modified`. The` ore:ResourceMap` seems mandatory, but neither linked.art ([https://linked.art/model/collection/](https://linked.art/model/collection/)) nor Europeana ([https://pro.europeana.eu/resources/apis/intro](https://pro.europeana.eu/resources/apis/intro)) use an `ore:ResourceMap` in their model.
*   The `ore:Proxy` is a class that links the `ore:AggregatedResource` and the `ore:Aggregation` to qualify the` ore:AggregatedResource` in the context of the aggregation. For example, `ore:Proxy` is used to express sequencing between `ore:AggregatedResource` in an `ore:Aggregation` since “without any sequencing information, the order of Aggregated Resources cannot be inferred — they form an unordered set. It would not be legitimate for the Resource Map to express this sequencing by asserting a triple of the sort `&lt;AR-1> &lt;hasNext> &lt;AR-2>`, since this fact is only true in the context of the specific Aggregation, and is not a "global" fact” ([http://www.openarchives.org/ore/1.0/datamodel#Proxy](http://www.openarchives.org/ore/1.0/datamodel#Proxy)).

<a name="084_Pattern_IdentityWithOreAggregation_p"></a>084_Pattern_IdentityWithOreAggregation_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=084_Pattern_IdentityWithOreAggregation_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1HSk1qe1t9UEI5sy1fCq2BPvZUHuOJUa4%26export%3Ddownload"></iframe>

This ontology would therefore be appropriate to render the complexity of gender identification and nationalities, but would significantly complicate the Target Model. In addition it would rely on semantics that would be inconsistent with those of CIDOC CRM, rendering this part of the model problematic in the long term. Finally, it is not possible to express the period when the entity is part of the aggregation, so this would not be useful either. As a result, this approach has been dismissed. 


| 💬 | *Discussion:* |
| --- | --- |
|| George Bruseker (18:11 16 Jul): This seems like a very technical solution that provides semantics that are inconsistent with the rest of CRM. <br/><br/> George Bruseker (18:13 16 Jul): I would suggest that if you need to tackle this topic in the future that there is a strong argument for a new event class for ‘identification’ of some sort. There are of course a lot of potential debates in this area and some dangerous territory around nature or nurture. That being said there is an element of declarativeness about gender, regardless of its biological status. It is something that people state (otherwise we could not know). If this argument holds water then one could track statements of identification in order to see how gender/sexuality evolves for individuals over time. |


> Previous: [Appendix B](/collections-model/en/target-model/current/appendix-b-appellations)<br>Next: [Appendix D](/collections-model/en/target-model/current/appendix-d-relationships)
