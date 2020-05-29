---
layout: page
title: General Concepts
permalink: /target-model/current/general-concepts
---
[Back to the Table of Contents](/target-model/current/information#table-of-contents)

## The differences between `E39 Actor`, `E21 Person` and `E74 Group`

As Actors is centered on the creators of artefacts, the central class of the target model is `E39 Actor`. As CIDOC CRM indicates, “this class comprises people, either individually or in groups, who have the potential to perform intentional actions of kinds for which someone may be held responsible” [(Doerr and Ore 2019b, 22)](https://www.zotero.org/google-docs/?kFv0ft). There are two subclasses to `E39 Actor:` `E21 Person`, which comprises real persons; and `E74 Group`, which accounts for any type of gathering or organisation of `E39 Actor` acting collectively. As stated in CIDOC CRM, “a gathering of people becomes an `E74 Group` when it exhibits organisational characteristics usually typified by a set of ideas or beliefs held in common, or actions performed together [(CIDOC CRM 2019, 34–35)](https://www.zotero.org/google-docs/?95nfKK). As the project linked.art pointed out, the class `E39 Actor` “might be used when it is not certain whether the actor is a Person or an Organisation or Group” [(linked.art 2019b)](https://www.zotero.org/google-docs/?qUBVws).

Some datasets might contain data pertaining to both actors and groups in a single field; in this case, it would be possible to use the `E39 Actor` superclass without any of its subclasses, although cleaning the data would be preferable. Such a practice should be avoided in order to maintain an efficient mapping process, but it would be interesting to flag such data (using comments or named graphs) as being in need of revision, and invite the public to clean it as this is an ideal crowdsourcing task.

For more details on this, please refer to the 

<p id="gdcalert7" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "Appendix F: Discussions, The Differences Between E39 Actor, E21 Person, and E74 Group"). Did you generate a TOC? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert8">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

[Appendix F: Discussions, The Differences Between E39 Actor, E21 Person, and E74 Group](#heading=h.o7jvmfy3kcw0). 


### Semantic Differences Between Contents, Labels, Notes and Comments, and Descriptive Texts

There are various ways to link a literal to an entity using different properties, each of which is intended to represent a specific type of human-readable statement. Therefore, it is important to assign the adequate properties to resources.

Heritage data can generally be classified into three kinds of strings explained below: 



*   Labels
*   Annotations and comments
*   Literal content


#### Labels

Labels are used to provide a human-readable version of a resource’s content in addition to its URI as well as to handle data in several languages (i.e. labeling a piece of information as being in French or in English for example). They are rendered with the property `rdfs:label`.



<p id="gdcalert8" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-16.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert9">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-16.png "image_tooltip")


For example, if the occupation of an artist is documented using the AAT and has the URI <code>&lt;[http://vocab.getty.edu/page/aat/300411314](http://vocab.getty.edu/page/aat/300411314)></code>, it would be useful to add the label “artist painters” to that occupation so that humans can understand what that occupation is without going to the Getty website. Another example would be in the case of Birth events where it would be relevant to use a concatenation mechanism (at the mapping stage) to provide useful descriptive labels such as “Birth of Jean Paul Riopelle" so that anyone arriving directly at the birth event node has a good idea of what its function is.


<table>
  <tr>
   <td>🚩 
   </td>
   <td><em>Important Information</em>
<p>
Labels can be attached to any resource across the target model and, since they can be so easily added, they will not be displayed in the schemas below to facilitate readability.
   </td>
  </tr>
</table>



#### Annotations and Comments

Annotations to specific pieces of data—rendered by the CIDOC CRM `P3 has note` property or by the <code>[rdfs:comment](https://www.w3.org/TR/rdf-schema/#ch_comment)</code> property in RDF—are used to describe or comment on a specific resource. 



<p id="gdcalert9" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-17.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert10">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-17.png "image_tooltip")


Both `P3 has note` and `rdfs:comments` make statements _about_ the resource’s content and _do not_ comprise its content. For example, a `P3 has note` applied to an `E33 Linguistic Object` annotates the latter’s text, but does not include it (i.e. it does not contain the expression of the `E33 Linguistic Object` resource). 


```
💡 Example:
If a manufacturer is named "Woodwork Construction Ltd.", and we wish to express that its current name is based on the owner's previous company, an annotation can be used.

```


For more details on this, please see 

<p id="gdcalert10" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "Appendix F: Discussions, Semantic Differences Between Contents, Labels, Notes and Comments, and Descriptive Texts"). Did you generate a TOC? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert11">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

[Appendix F: Discussions, Semantic Differences Between Contents, Labels, Notes and Comments, and Descriptive Texts](#heading=h.kpg34jcd89h7).

Annotations should be used in edge cases when something is too complex and subtle to be adequately expressed by creating a new pattern in the model. They should not be dismissed entirely, but they should be used with caution. In the Woodwork example mentioned above, it would also be possible to use `P130 shows features of`. However, in the rare cases when something is really extraneous to the model but not to understanding, `P3 has note` and `rdfs:comment` are valid choices. If this is the case, `rdfs:comment` should be used when the annotation pertains to classes or properties (ontological content) whereas `P3 has note` should be used when the annotation pertains to museum data (cultural content).


<table>
  <tr>
   <td>🚩 
   </td>
   <td><em>Important Information</em>
<p>
Unless the creator of the annotation is impacting the model itself by their work, <code>rdfs:comment</code> should not be used and <code>P3 has note</code> should be preferred.
   </td>
  </tr>
</table>


 


#### Literal Content

To represent the linguistic content of a resource—appellations, biographies or descriptions for example—`rdfs:comment` or `rdfs:label` are not suitable. Even though CIDOC CRM previously recommended the use of `P3 has note` to represent content [(Doerr and Ore 2019b, 20)](https://www.zotero.org/google-docs/?24yMfw), it is no longer the case as `P3 has note` “is a container for all informal descriptions about an object that have not been expressed in terms of CRM constructs. In particular it captures the characterisation of the item itself, its internal structures, appearance, etc”[(Doerr and Ore 2019d, 48)](https://www.zotero.org/google-docs/?2klVaf). To remedy this, CIDOC CRM has developed the `P190 has symbolic content` property to associate an instance of `E90 Symbolic Object` with a representation of its entire content in the form of a string of text [(Doerr and Ore 2019e, 114)](https://www.zotero.org/google-docs/?mVJQ1m).


```
💡 Example:
For example, the biography of Jean Paul Riopelle could have:
a label "Biography of Jean Paul Riopelle";
a note from the museum assessing the biography, stating that it has to be revised for example; 
the content of the biography.
From a modeling standpoint, this would look like the following: 


```


The best way to represent the content of a resource is to follow CIDOC CRM’s approach rather than to rely on a homemade property that would only be used by CHIN. As is often the case in the LOD context, it is preferable to employ recognised and approved classes and properties rather than create new, “single use” ones.


<table>
  <tr>
   <td>🔎 
   </td>
   <td><em>To Be Discussed</em>
<p>
Whether it would be preferable to use local CHIN classes in this case is discussed on <a href="https://github.com/chin-rcip/chin-rcip/issues/37">CHIN’s Github Issue #37</a>. 
   </td>
  </tr>
</table>



### Mapping problems and E33 Linguistic Object

If the data of the contributing institution is clean—in other words, if it is not mixing data types and/or contents within single fields—, CHIN’s [Pipeline](https://drive.google.com/open?id=1W_vsT_Br86BRR92SWEqFX90861Nu3mUTmx_fAyuOE5A) along with the [Reference Documentation](https://drive.google.com/open?id=1-9B8plo0LZg-5H643mgJumzy6XEF3PYlAwGTFuHaxKA) and Target Model will successfully translate it from a relational to a semantic framework.  However, if the input data is poor—for example if it mixes different kinds of information within fields or if it contains heterogeneous natural language expressions—, it will not be possible to map it to semantic standards.

In such a case, a standard semantic mapping solution is to create an instance of `E33 Linguistic Object` that is typed using `E55 Type` in order to: 



*   indicate the general kind of information held by the `E33 Linguistic Object`; 
*   distinguish it from other `E33 Linguistic Objects` such as biographies. 

The language of the content must also be indicated and the data must be instantiated into an `rdfs:Literal` and connected to the `E33 Linguistic Object` instance through the `P190 has symbolic content` property. The instance of `E33 Linguistic Object` itself should be linked back to the node that it describes using the `P67 refers to` property. 



<p id="gdcalert11" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-18.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert12">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-18.png "image_tooltip")



```
💡Example:
For example, a museum could have recorded the birth of Jean Paul Riopelle with the following value:  "le septième jour du mois d'octobre 1923". Such a value could not be mapped as it is not compliant with XSD:Date format requirements. In order to nonetheless retain this information, an E33 Linguistic Object linked to an E52 Time-span can be created, as shown below:

Had the value been "07.10.1923", the dates could have been encoded properly using the XSD:DateTime format, as shown below:


```



### Data Provenance


#### Provenance of the Dataset

One of the goals of Actors is to aggregate museum data from Canadian institutions and other sources in a single [knowledge graph](https://en.wikipedia.org/wiki/Knowledge_Graph). To properly differentiate these data and manage questions of factual agreement and disagreement, it is crucial to track data provenance. But, once the data has been aggregated and deposited into a [triplestore](https://en.wikipedia.org/wiki/Triplestore)—a database for the storage and retrieval of RDF triples—the provenance of said data is lost (i.e. what institution or person contributed it). Loading RDF data into such a collection thus entails losing the ability to: 



*   identify a subset of RDF triples (i.e. to identify their origin);
*   determine whether a single triple is asserted once or multiple times (e.g. if a single triple is asserted by separate distinct sources as opposed to several times by a single source, thus asserting it more than once). 

CHIN considersthe best way to establish provenance throughout the model is to use Named Graphs rather than the longer, more complex `E13 Attribute Assignment` pattern (that would have to be repeatedly assigned to triples, each and every time, and would unnecessarily weigh down the model). For more information about this `E13 Attribute Assignment` pattern, see the 

<p id="gdcalert12" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "Appendix A: Data Provenance"). Did you generate a TOC? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert13">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

[Appendix A: Data Provenance](#heading=h.fgypzyshl1ox).

A [Named Graph](https://en.wikipedia.org/wiki/Named_graph) is a set of RDF triples that receives a fourth statement (the triples then become quadruples, or quads: `&lt;subject> &lt;predicate> &lt;object> &lt;graphname>`). This enables the treatment of the whole graph as a single entity which can receive attributes such as author, provenance, etc. Each triple within this Named Graph will inherit the graph’s information. Named Graphs also allow the use of specific subsets of the collected data based on graph identifiers [(Dodds and Davis 2019, 53)](https://www.zotero.org/google-docs/?a5qAir). One of their most useful characteristics is that they enable SPARQL queries within specific subsets of Named Graphs. 

// EXAMPLE TO COME

From a modeling standpoint, such a collection of data would look like the following: 



<p id="gdcalert13" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-19.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert14">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-19.png "image_tooltip")


Such Named Graphs can be expressed in various syntaxes such as [NQuads](https://www.w3.org/2009/07/NamedGraph.html#syntax-1), [TRiG](https://www.w3.org/2009/07/NamedGraph.html#syntax-1), or [JSON-LD](https://www.w3.org/TR/json-ld11/#named-graphs), although they cannot be represented in RDF/XML. They are often represented as additional instances to the usual triples (that thus become quads), but can also be represented at the beginning of an RDF file such as in the following example. 


```
💡Example:
{
  "@context": {
    "rdf": "http://www.w3.org/1999/02/22-rdf-syntax-ns#",
    "rdfs": "http://www.w3.org/2000/01/rdf-schema#",
    "xsd": "http://www.w3.org/2001/XMLSchema#",
    "prov": "http://www.w3.org/ns/prov#",
    "crm": "http://www.cidoc-crm.org/cidoc-crm/"
  },
  "@id": "http://mic.ca/graph/wikidata0001",
  "@type": "prov:Entity",
  "@type": "crm:E73_Information_Object
  "prov:wasAttributedTo": {
        "@id": "http://mic.ca/actor/9999"
      },
  "@graph": [
    {
      "@id": "http://mic.ca/actor/9999",
      "@type": "crm:E74_Group",
      "@type": "prov:Agent"
    },
    {
      "@id": "http://mic.ca/occupation/Printmaker",
      "@type": "crm:E55_Type",
      "crm:P2_has_type": {
        "@id": "http://mic.ca/occupation_type/Occupation"
      },
      "rdfs:label": "Printmaker"
    }
  ]
}

```



#### Record Provenance with Aggregated Contributors

However, the Named Graph approach is problematic when aggregating data that has already been aggregated. This is the case of [Artists in Canada](https://app.pch.gc.ca/application/aac-aic/description-about.app?lang=en), a bilingual union list that identifies the location of documentation files on Canadian artists. Its data is submitted by specific institutions and its content is managed by the National Gallery of Canada whilst CHIN handles its technological maintenance [(National Gallery of Canada / Musée des beaux-arts du Canada 2019a; 2019b)](https://www.zotero.org/google-docs/?BzAdkM).

In the case of such aggregated contributors, it is mandatory to have a named graph for the whole contributor in order for users to be able to query specific information from it (for example if someone wants to search only within Artists in Canada).

As those aggregated contributors also document the provenance of their data, it will be necessary to also identify the primary provenance of each entry (i.e. the institution that contributed it to Artists in Canada in the first place). For the purposes of this model an entry corresponds to the institutional record.

The easiest way to document such entries is to create an `E73 Information Object` “record” instance linked to the individual `E39 Actor` it documents through the `P67 refers to` property. This same `E73 Information Object` is linked to its record contributor (a different `E39 Actor`) and dated through an `E65 Creation` event.



<p id="gdcalert14" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-110.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert15">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-110.png "image_tooltip")



<table>
  <tr>
   <td>🔎 
   </td>
   <td><em>To Be Discussed</em>
<p>
Whether it would be useful to use the same pattern to document non-aggregating contributors, such as a cataloguer responsible for the documentation of a record in an institution, is under discussion and your input on this matter would be useful. CHIN wants to explore the legal and ethical concerns of displaying personal information of individuals and will examine those with relevant experts. In the meantime, such information will not be recorded. 
<p>
For more details on this, see <a href="https://github.com/chin-rcip/chin-rcip/issues/34">CHIN’s GitHub Issue #34</a>. 
   </td>
  </tr>
</table>



```
💡 Example:
In Artist in Canada, the record of Jean Paul Riopelle indicates that the information comes from the National Gallery of Canada and was created on 1985.03.13 and last modified on 2017.06.05.
As CHIN has not yet determined how to document updates of information (something that will be developed later on), the creation date currently stands for the last modified version of the record. 


```



<table>
  <tr>
   <td>🔎 
   </td>
   <td><em>To Be Discussed</em>
<p>
The best way to manage updates to named graphs is still unclear to CHIN and is discussed on <a href="https://github.com/chin-rcip/chin-rcip/issues/14">CHIN’s Github Issue #14</a>.
   </td>
  </tr>
</table>



#### Limits of and Issues with the Named Graph and “Record” approach

The Named Graphs combined with a “record” approach lacks some of the precision and granularity of the `E13 Attribute Assignment` pattern (for more information about the `E13 Attribute Assignment pattern`, see the 

<p id="gdcalert15" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "annexes"). Did you generate a TOC? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert16">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

[annexes](#heading=h.tv714o5e4vr4)). As the source is not specified on every triple, it is not possible to express complex information pertaining to specific triples. For example, it is not possible to indicate that a date attribution is uncertain.

Also, this approach records the provenance of the data, but not the documents used by the contributing institutions themselves when documenting their records. 


<table>
  <tr>
   <td>🔎 
   </td>
   <td><em>To Be Discussed</em>
<p>
How to best identify who the creators of a record are is discussed on <a href="https://github.com/chin-rcip/chin-rcip/issues/10">CHIN’s Github Issue #10</a>.
   </td>
  </tr>
</table>



<table>
  <tr>
   <td>🔎 
   </td>
   <td><em>To Be Discussed</em>
<p>
How to best manage updates is discussed on <a href="https://github.com/chin-rcip/chin-rcip/issues/14">CHIN’s Github Issue #14</a>.
   </td>
  </tr>
</table>



<table>
  <tr>
   <td>🔎 
   </td>
   <td><em>To Be Discussed</em>
<p>
How to best manage uncertainty is discussed on <a href="https://github.com/chin-rcip/collections-model/issues/47">CHIN’s Github Issue #47</a>.
   </td>
  </tr>
</table>



### Challenges When Representing Indigenous Realities 

Actors aims to document creators from Canadian museums. As such, its model must render most, if not all, of the distinctive characteristics of communities across Canada. This includes communities that are typically underserved by traditional models, most notably Indigenous creators. An overview of current models and vocabularies indicates that they typically adopt a western point of view that does not adequately represent the realities of Indigenous Peoples' lives and artefacts. CHIN, in line with Canadian society's reckoning and path towards reconciliation, considers that respect and deference should be observed when it comes to Indigenous practices and beliefs. Museums are increasingly documenting and exhibiting Indigenous artefacts and this will likely lead, in the years to come, to an increased need for structures that encompass Indigenous characteristics. Thus, special attention will be paid to Indigenous conceptions within the model, particularly when it comes to choosing proper terms to label fields and data. Hopefully, this undertaking will better answer the needs of both Indigenous communities and GLAMs.

For more details on this, please see 

<p id="gdcalert16" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "Appendix F: Discussions, Challenges When Representing Indigenous Realities"). Did you generate a TOC? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert17">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

[Appendix F: Discussions, Challenges When Representing Indigenous Realities](#heading=h.4k6wwh518q3m).


### Dates pattern

The dating pattern is the same throughout the model. In order to facilitate understanding and reading, it will not be reproduced in the rest of the diagrams of this document. .

In CIDOC CRM, only `E2 Temporal Entities` and its subclasses (comprising events), can be situated temporally. This is done through a time-span, modeled with the property `P4 has time-span` and the class `E52 Time-Span`.

This `E52 Time-Span` can then be delimited (using the XSD Date standards) with the use of 4 properties representing specific dates: 



*   `P82a begin of the begin ` indicates that the time-span of the event may at the earliest have started on that date.
*   `P81a end of the begin `indicates that the time-span of the event has without doubt at the latest started on that date.
*   `P81b begin of the end` indicates that the time-span of the event has without doubt lasted at least until this date.
*   `P82b end of the end `indicates that the time-span of the event may have lasted until that date.

The diagram below illustrates the differences between these 4 properties (see the [CIDOC CRM documentation](http://www.cidoc-crm.org/guidelines-for-using-p82a-p82b-p81a-p81b) for more information about this):



<p id="gdcalert17" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-111.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert18">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-111.png "image_tooltip")


Because the `P82a begin of the begin` and `P82b end of the end` properties are the most encompassing delimiters of the event, it is wiser to use them systematically and to use the properties `P81a end of the begin` and `P81b begin of the end` only when we have such precise information that is specified as such.

It is also possible to add qualifiers to dates with the properties `P79 beginning is qualified by` and `P80 end is qualified by` in conjunction with an `rdfs:Literal`. Such qualifiers can include commentaries (e.g. presumed date) or typical qualifiers (e.g. circa, BC, etc.). 

The full date pattern is as follows: 



<p id="gdcalert18" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-112.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert19">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-112.png "image_tooltip")



```
💡  Example:
Pénelope Solette produced a painting that was presented to the public on the 10th of January 1997. Art historians consider she has started producing the work in October of 1996.

```