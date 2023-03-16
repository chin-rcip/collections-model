---
layout: page
language: en
title: Appendix C - Identity 
permalink: /en/target-model/version-2-1/appendix-c-identity
other_link: /fr/modele-cible/version-2-1/introduction
sidebar: tm21
date: 2021-03-12
description: The Actors Target Model is intended to model the Actors facet of CHIN’s DOPHEDA (that will cover collections data more broadly). Patterns most relevant to actors' lives are presented along with diagrams and examples illustrating them, as well as a record and explanation of relevant decisions that were made when developing said patterns. The current document is a work in progress and, as such, will be enhanced periodically. Elements currently under development or review are listed as issues.
---
<!-- [Back to the Table of Contents](/collections-model/en/target-model/version-2-1/information#table-of-contents)
 -->


As stated in the [Identity Patterns section](/collections-model/en/target-model/version-2-1/identification#identity-patterns), CHIN has decided to use a simple `E55_Type` pattern to identify gender and cultural affiliation whilst `E74_Group` will be used to identify nationality, nationhood and community. The `E55_Type` class will be used in conjunction with it to render what the type of the group is. The following patterns have been rejected for reasons explained below. 


## With `E5_Event`

Identity fields could be represented using an event in the following way: 

<a name="083_Pattern_IdentityWithEvent_p"></a>083_Pattern_IdentityWithEvent_p
<div class="mxgraph" style="max-width:100%;border:1px solid #cccccc;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;target&quot;:&quot;blank&quot;,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom layers lightbox&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;xml&quot;:&quot;&lt;mxfile modified=\&quot;2023-03-14T22:06:44.021Z\&quot; host=\&quot;app.diagrams.net\&quot; agent=\&quot;5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) draw.io/20.3.0 Chrome/104.0.5112.114 Electron/20.1.3 Safari/537.36\&quot; etag=\&quot;AuGspCOOE1jDOc6PE3EJ\&quot; version=\&quot;20.3.0\&quot;&gt;&lt;diagram id=\&quot;D4a299pbFKIJiZc3yz8S\&quot; name=\&quot;Page-1\&quot;&gt;7Vhdb9owFP01eWyVb8JjS2m7qp2QqNRuL5FxLoknEyPHFLJfP4c4JMG0Y0BHHiqVyvf6M+dcn2vbcAaz1R1H8+SJRUAN24xWhnNj2LZtFH9mlJemVZoxJ5HmGJPfoJym8i5IBFmroWCMCjJvOzFLU8Ci5UOcs2W72ZTR9qxzFIPmGGNEde8LiUSivJZp1hX3QOJETR14qmKGqsbKkSUoYsuGyxkazoAzJsrSbDUAWuBW4VL2u32ndrMwDqnYqwO3ft7dv8Tfnl7h8enB6XF7fKFGeUN0oT54aFvhCHjGUrVskVdYcLZIIyiGswznepkQAeM5wkXtUhIvfYmYUVU9JZQOGGV83deZTicRRvqaqwUAF7BquNQ33AGbgeC5bKJqnX5QdlHh5FkqvpYNeirMkwYzvvIhFRHxZugaNFlQuP0DhraG4chyQyyjj0AUsoUIJ7mGJUQyzJTJuEhYzFJEh7X3ukbblFbd5pGxucL4FwiRqz2DFoK1GZAY8/y16H/pVeYPNdzauFm1rFxZ75KUsQXH8AESrtqgiMcg/h51BQYfUs6BIkHe2lvx5Pw5On92mKAsFPkczkqc1aKtZvFsxHmdIs7VxasXXmE5MRH6jjtGvQIbO4A/Qb2c/rnVy9NB9LzweVfoH6X/aOL53gkQtDqHoK/rh8qf5pUuH5TKowsckD/Bh8kJ8OsF1lb+9C+9/RAMPgvB3lcGrTKjuacS+51S4uArhe7NnNWt009fp84tqSMzuMjmSL8HnHHnWR3gz+0Uf9W6GwQ+J1CAAHzK+AyluLDYVP6bAEnjYhHyN0Apisgudg/MUJEN/Wn/Iw4OT1JOcP4kZel35VEJcQ3qd0l4Eee7zp8HZ/4IehhOAKrX6yCoOy7PHZCfTKqAuCqej6QjZSlUvltSfJ8SnqhqgSnKMoJLp2qyVqoVEQ0Rk9bm9CDLtYQVRm409Oy/Kt/et3bn1MKnuo4YkWuuN7/bq+KyilQ/aA9SrlX1a755bQ3lu25rINfbWk0JjjbQOpY3X3REeOtvC4btU4nytTzL+3FReJCTlwpygwRU1XK6TYtNF155hp4dPhcbZLxrgxx10/UnGAenUfHty67dd/aTm0+7qln6k4FtWv1Dtfr0ic729oToAEWWZv3aXEZ4/VzvDP8A&lt;/diagram&gt;&lt;/mxfile&gt;&quot;}"></div>

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
<div class="mxgraph" style="max-width:100%;border:1px solid #cccccc;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;target&quot;:&quot;blank&quot;,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom layers lightbox&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;xml&quot;:&quot;&lt;mxfile modified=\&quot;2023-03-14T22:06:44.249Z\&quot; host=\&quot;app.diagrams.net\&quot; agent=\&quot;5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) draw.io/20.3.0 Chrome/104.0.5112.114 Electron/20.1.3 Safari/537.36\&quot; etag=\&quot;oxw554k1Lj_HgqWrIQ5q\&quot; version=\&quot;20.3.0\&quot;&gt;&lt;diagram id=\&quot;iNz_YC-lwkWBESp8Df5b\&quot; name=\&quot;Page-1\&quot;&gt;1VdNj5swEP01HHfFR8iSI5uk21a70qo5tNtL5eAJuDIMdZwA/fU1wQSQlWzabppUysHzZozt956HYHnTtHwQJE+ekAK3XJuWljezXNe16p9Nqya8CUaTBokFow3mdMCC/QQN2hrdMArrQaFE5JLlQzDCLINIDjAiBBbDshXy4ao5icEAFhHhJvqZUZlo1LHtLvEeWJzopQNfJ1LSFmtgnRCKRQ/y5pY3FYiyGaXlFHhNXctLM+/dgex+YwIyecqEWZROoPg6+vgjWRRYhs/w4fFGP2VL+EYfGIUahIrzSLClYr7Zu6xaQoAqfnSIQiYYY0b4vEPvBW4yCvWqtoq6mkfEXIGOAr+DlJUWm2wkKiiRKddZdSBRfdHzd8FLHdz6bTgr+8lZpSOTEX28NW5EBEdo0C6VRMQgj9SNmrqag94Cmu8HwBTUflSBAE4k2w49RLQV431dp5YaaMF+Qzz3gHifYN2c+Inkhn6dOjXVRcIkLHKyY6dQF3ioxEFGtyAklEc50Fkv8Jsp1f7qaBaL3n1qL0nSu0pj+0y8eQd4I3EsICby0q7vjP4y8Plbu350ouv9q3L96BX1GGYXN70/uTrT+wdoC1vTU8sdc7WL+6VQo7ge7RvJ9RHq+s6FCR0bhAq6UouEsspNwi7YQJyzNZDgv2wgd1crnGP9o/87pwo3uSrhAkO4MJKoupUdmrJxrj4R4PXmtGKcT5Grx9TzvNUKxrA8U9Pyxv6tf1rbCs7VtiYGiXPX+fYMYv23702DySWNyBv9iTSYvDuZyT94Aaiw+y7b5Xrftt78Fw==&lt;/diagram&gt;&lt;/mxfile&gt;&quot;}"></div>

This ontology would therefore be appropriate to render the complexity of gender identification and nationalities, but would significantly complicate the Target Model. In addition it would rely on semantics that would be inconsistent with those of CIDOC CRM, rendering this part of the model problematic in the long term. Finally, it is not possible to express the period when the entity is part of the aggregation, so this would not be useful either. As a result, this approach has been dismissed. 


| 💬 | *Discussion:* |
| --- | --- |
|| George Bruseker (18:11 16 Jul): This seems like a very technical solution that provides semantics that are inconsistent with the rest of CRM. <br/><br/> George Bruseker (18:13 16 Jul): I would suggest that if you need to tackle this topic in the future that there is a strong argument for a new event class for ‘identification’ of some sort. There are of course a lot of potential debates in this area and some dangerous territory around nature or nurture. That being said there is an element of declarativeness about gender, regardless of its biological status. It is something that people state (otherwise we could not know). If this argument holds water then one could track statements of identification in order to see how gender/sexuality evolves for individuals over time. |


> Previous: [Appendix B](/collections-model/en/target-model/version-2-1/appendix-b-appellations)<br>Next: [Appendix D](/collections-model/en/target-model/version-2-1/appendix-d-relationships)
