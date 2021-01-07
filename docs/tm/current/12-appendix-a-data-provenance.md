---
layout: page
title: Appendix A - Data Provenance
permalink: /target-model/current/appendix-a-data-provenance
sidebar: tm
---
<!-- [Back to the Table of Contents](/collections-model/target-model/current/information#table-of-contents)
 -->
<div class="hidden-content">
## On This Page

* [Data Provenance](#)
</div>

As stated in the [Provenance of the Dataset](/collections-model/target-model/current/general-concepts#data-provenance) section, one way of establishing data provenance would be to use the `E13_Attribute_Assignment` event pattern described below and assign it to each triple so that their provenance can be documented. However, this would make the model in general much heavier as each triple would be assigned this pattern. From a processing standpoint this would become increasingly burdensome as the amount of data grows, which is why the Named Graph approach described in the Provenance of the Dataset section has been adopted. 

The `E13_Attribute_Assignment` class represents the action of making assertions about the properties or relations between two items or concepts, as stated in the [CIDOC CRM Scope note](http://www.cidoc-crm.org/Entity/e13-attribute-assignment/version-6.2.2).

This `E13_Attribute_Assignment` event can link together an `E1_CRM_Entity` to another `E1_CRM_Entity`, which correspond to said items or concepts. The performer of this `E13_Attribute_Assignment`—in other words the actor who stated this relationship between the two `E1_CRM_Entity`—is the museum providing the data. As the  `E13_Attribute_Assignment` is an event, it can be dated though an `E52_Time-Span`<sup id="a1">[1](#f1)</sup>, thus providing a way to represent both the provider of the data and the moment of provision. 

In early 2019, the [CIDOC CRM team](http://www.cidoc-crm.org/Issue/ID-367-e13-attribute-assignment) discussed the fact that the `E13_Attribute_Assignment` needs a property to denote which kind of property the attribute assignment is about. Their conclusion was to create a yet to be implemented new property `PXXX assigned property type` with a sub property of `P2_has_type`. When it is made available, it would have been preferable to use `PXXX assigned property type.` Until then, the use of `P2_has_type` in conjunction with `E55_Type` to specify the property the `E13_attribute_assignment` is about would have been best. This pattern would be used for each triple, so that its provenance is documented: 

<a name="076_Pattern_AttributeAssignment_p"></a>076_Pattern_AttributeAssignment_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=076_Pattern_AttributeAssignment_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D193Ej0Z_p8OsMopEOqx9XDN6MApKSi2FT%26export%3Ddownload"></iframe>


| 💡  Example: <br/><br/>In 2018, WikiData assessed with certainty that the Birth of Emily Carr took place in Victoria, BC. |

<a name="077_Example_DataProvenanceCertainCarr_p"></a>077_Example_DataProvenanceCertainCarr_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=077_Example_DataProvenanceCertainCarr_np.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1wqaynDfWdj6v3DkBF_n5DKVJ03GpEYE3%26export%3Ddownload"></iframe>

If multiple and contradictory statements are made about a resource, various and distinct `E13_Attribute_Assignment` would be created and linked to their respective statement. For example, if Museum A attributes the date 1920 to the birth of an artist, and museum B attributes 1922, then we should have two `E13_Attribute_Assignment` (one for each Museum) linked to the `E67_Birth`  event and linked to two different `E52_Time-Span`, 1920 and 1922, as shown in the example below:


| 💡  Example: <br/><br/>In this example, the actor "Bob" was born in 1920 for Museum A and in 1922 for Museum B. |

<a name="078_Example_DataProvenanceUncertainBob_p"></a>078_Example_DataProvenanceUncertainBob_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=078_Example_DataProvenanceUncertainBob_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1_teNI079JcU5vcgWbgJbby4bdcLrGMTb%26export%3Ddownload"></iframe>


| 💬  Discussion: <br/><br/>George Bruseker (17:40 16 Jul): modeling wise this is very nice and correct. From integration management perspective though, I don't think it will scale. You cannot know in advance what facts the partners will not agree on. On the other hand you cannot make every attribute the function of an attribute assignment (your graph will be painfully bloated). It seems the solution is to have the whole imported dataset in a named graph so it I find two facts disagreeing about the birthdate in the integrated knowledge based, I can follow the property back to the dataset it belongs to and form there understand who uttered/documented/believed fact x.<br/><br/>Philippe Michon (09.56 17 Jul): We already suspected that this pattern was complicated as we were repeating the same data on each triple. That said, I still have a bunch of questions:<br/>1. Should we remove completely the e13 pattern in favor of Named Graphs?<br/>2. Should/Could we still use e13 to express the provenance of our Named Graphs?<br/>3. If not, which ontology should we use to monitor the provenance?<br/>4. How the reconciliation process is going to work if we use Named Graphs. I guess we will have to compare all the graphs but I don't clearly vizualise the process?<br/>5. What will happen if, on our UI, someone confirm that this date is true? This will generate a new graph for this user with just this date statement?<br/>6. As I'm not familiar with Named Graphs, all of them will be placed in our future triple store and we could query them all together and just specific ones if needed?<br/><br/>George Bruseker (07:31 22 Jul): It's a long set of questions for a side comment, but I will add my ideas as coherently as possible. <br/>1. In the scenario where you are loading a whole dataset, the whole dataset should be in a single named graph that would have the provenance information attached. E13 can be used within a graph to indicate 'someone said something of something'. It can also in principle be used as the model to document, as a single instance, the provenance of your whole named graph. Ie. You make on named graph statement about who is responsible for the dataset and how and you attach it to the named graph that is the statement (ie the whole dataset contributed).<br/>2. It seems one good model to follow. The other plan might be to use CRMdig which is for digital provenance. If what you want to trace is rather the steps and methods of contribution. Warning there though, that it would probably need to be developed some to support this (does not already have events like 'aggregation').<br/>3. Prov-o is a major competitor and is a possibility.<br/>4. It kind of depends on when in the process you do reconciliation... longer conversation to my mind.<br/>5. Depends on the scenario, but as researchspace implements, for example, I believe this is the strategy. You would not want to mix up the institutional belief (what is delivered by the contributing museum) with the individual user belief.<br/>6. It becomes an additional attribute that you can add to the sparql query, so you can bring back data from one or more namedgraphs depending on what you specify.<br/><br/>Philippe Michon (09:36 22 Jul): +george.bruseker@gmail.com I agree that we should take some time to review this topic at some point.<br/>1-2: We should probably keep the pattern in the model but describe it very clearly. Especially if we use it for the provenance of the whole graph and for specific statements.<br/>I will let Stephen look at CRMdig. I'm not sure to understand the modeling if we decide to use e13 for the provenance of the whole graph, would it be something like:<br/>Museum A (e74) -> p14i -> [1] (e13)<br/>[1] (e13) ->p140 -> Museum A's graph <br/>Is it mandatory to use p141? If so, how do I use it?<br/> |

---
<b id="f1">1</b> Note that the scope of the date of the assignment date does not refer to the time this assertion was thought to be true, but to the time it was made.[↩](#a1)


> Previous: [Bibliography](/collections-model/target-model/current/bibliography)<br>Next: [Appendix B](/collections-model/target-model/current/appendix-b-appellations)
