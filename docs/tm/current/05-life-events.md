---
layout: page
title: Life Events
permalink: /target-model/current/life-events
---
[Back to the Table of Contents](/target-model/current/information#table-of-contents)

## Technique Used

The modelisation of the production of artefacts (

<p id="gdcalert31" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "see section below"). Did you generate a TOC? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert32">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

[see section below](#heading=h.ihv636)) documents some information pertaining to the role of the actor as well as the technique used to produce the object.

Because museums often document the techniques used by an actor by linking this information to said actor instead of linking it to the production of (an) artefact(s), an `E55 Type` has to be created in order to specify the technique and link it directly to the actor with the property `P2 has type`.

There is a difference between a technique used by an actor, and the activity or occupation this actor could have in his life. For example, an actor A could be a painter, and use the technique watercolor but also have used once the technique sculpture, without being a sculptor. For the occupation, 

<p id="gdcalert32" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "see below"). Did you generate a TOC? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert33">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

[see below](#heading=h.lyvgqltutk5t).



<p id="gdcalert33" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-117.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert34">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-117.png "image_tooltip")



<table>
  <tr>
   <td>🔎 
   </td>
   <td><em>To Be Discussed</em>
<p>
CHIN’s is aware that this pattern is not ideal as it implies that an <code>E39_Actor</code> is a Technique. When this pattern was developed, there was no other way of representing the use of a technique by a creator in CIDOC CRM. However, two alternatives are currently being developed and could be leveraged at a later date: <a href="https://github.com/linked-art/linked.art/issues/237#issuecomment-611035443">Linked.Art’s  E13_Attribute_Assignment relationship strategy</a> or <a href="http://www.cidoc-crm.org/crmsoc/sites/default/files/CRMsoc_20190326.pdf">CRMsoc’s Phase class</a>.
   </td>
  </tr>
</table>



```
💡Example:
In the case of Jean Paul Riopelle, the artist used the technique "drawing" and "painting".
	
```



### Occupation

As we have seen in the Technique section (

<p id="gdcalert34" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "see above"). Did you generate a TOC? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert35">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

[see above](#heading=h.1y810tw)), some information pertaining to the role of an actor can be documented when modeling the production of (an) artefact(s) (

<p id="gdcalert35" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "see section below"). Did you generate a TOC? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert36">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

[see section below](#heading=h.ihv636)).

But an actor could also have an occupation that is not linked to any production event and there is a difference between the role of an actor during a production event and an occupation in life (a person could be the writer during the production of a book, but their main occupation could be painter).

There is also a difference between an occupation, like being a musician (even without being employed) and employment as an individual part of an `E74 group` (for example a musician in an orchestra). Such employment is modeled following the group belonging pattern explained 

<p id="gdcalert36" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "below"). Did you generate a TOC? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert37">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

[below](#heading=h.cnjof86v1w0s).

In order to account for these intricacies, the occupation is modeled with the class `F51 Pursuit` (from the CIDOC CRM extension of [FRBR](https://en.wikipedia.org/wiki/Functional_Requirements_for_Bibliographic_Records), [FRBRoo](http://www.cidoc-crm.org/frbroo/)) which is an event that is `P14 carried out by` the `E39 Actor`. This `F51 Pursuit` occupation is then typed to specify which kind of occupation it is (paintor, sculptor, artist, etc.).


<table>
  <tr>
   <td>🔎 
   </td>
   <td><em>To Be Discussed</em>
<p>
CHIN is currently examining whether an additional <code>E55 Type</code> is needed to specify if the occupation is a profession, leisure, etc. This issue is discussed on <a href=" https://github.com/chin-rcip/chin-rcip/issues/29">CHIN’s Github Issue #29</a>. 
<p>
We are also wondering whether the occupation pattern could be used to assign a type to the industry of a group and to describe the occupation of a group of artists? This issue is discussed on <a href="https://github.com/chin-rcip/chin-rcip/issues/28">CHIN’s Github Issue #28</a>.
   </td>
  </tr>
</table>




<p id="gdcalert37" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-118.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert38">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-118.png "image_tooltip")



```
💡Example:
In the case of Jean Paul Riopelle, the creator is documented as holding the Painter profession in Montreal and in Paris, from 1940 until his death.
	
```



### Social Status

Whilst actors have professional or artistic occupations, people also hold social status(es), like being a leader, an Indigenous Community elder, or a knight. These cannot be modeled as occupations because they are not _pursued_ per se and do not fit the scope of `F51 Pursuit`.

[CIDOC CRM-Soc](http://www.cidoc-crm.org/crmsoc/) will have a class called “Phase” that may document such statuses, but it is still in development. In the meantime, the best way to model social statuses is to use an `E7 Activity` class carried out by the `E39 Actor` holding said status. 



<p id="gdcalert38" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-119.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert39">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-119.png "image_tooltip")



```
💡Example:
Jean Paul Riopelle became, in 1969, officer of the Order of Canada and, in 1975, compagnon of the Order of Canada.
	
```



<table>
  <tr>
   <td>🔎 
   </td>
   <td><em>To Be Discussed</em>
<p>
The question of the necessity of this Social Status pattern is discussed on <a href="https://github.com/chin-rcip/chin-rcip/issues/27">CHIN’s Github Issue #27</a>. 
<p>
There is also the question of modeling this kind of information under the Social Status pattern or with the Membership Group pattern. In the case of being an Officer of the Order of Canada, it could be modeled as being a member of the order, rather than performing the activity of Officer. CHIN will have to determine how information should be attributed to these patterns, according to which criteria, etc. 
<p>
<code>E13_Attribute_Assignment</code> would be a way to avoid using <code>E7_Activity</code> as a “Phase”.
   </td>
  </tr>
</table>



### Flourishing dates

The flourishing dates of an artist or maker are often an important piece of information for museums. In terms of modeling, the flourishing period is not an `E7 Activity` as the `E39 Actor` is not actively carrying his flourishing; it is rather an arbitrary event decided by other people (usually historians) so that it has been represented as an `E5 Event`. 

The `E39 Actor` is a participant (modeled with the property `P11 has participant`) of this `E5 Event` and this same event is typed as a flourishing event. This event can of course be situated chronologically and geographically.



<p id="gdcalert39" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-120.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert40">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-120.png "image_tooltip")



```
💡Example:
Cyril Henry Barraud, an English painter who participated in World War I as a war artist of the Canadian army is considered by Artists in Canada to have flourished between 1913 and 1915.

	
```



### Specific traits

Most of the museums have unique fields to document specific collections or objects. How to deal with such types of information has not yet been determined. 


<table>
  <tr>
   <td>🔎 
   </td>
   <td><em>To Be Discussed</em>
<p>
For the moment, CHIN is not considering such niche fields. However, a museum could submit a proposal for the addition of a field that it deems necessary and useful. CHIN could then assess whether it is relevant to model it. At the moment, CHIN is wondering whether this would be a suitable option, and if a “miscellaneous” field should be created as well to accommodate such data. 
<p>
This issue is discussed in <a href="https://github.com/chin-rcip/chin-rcip/issues/19">CHIN’s Github Issue #19</a>. 
<p>
How to treat Business Output is a similar concern CHIN has. One possibility would be to use the property <code>R59 had typical subject</code> on the <code>F51 Pursuit</code> activity of the group, as discussed in the <a href="https://github.com/chin-rcip/chin-rcip/issues/29">issue #29</a>.
   </td>
  </tr>
</table>



### Artistic Movements

At the moment CHIN is unsure whether it should or needs to model artistic movements


<table>
  <tr>
   <td>🔎 
   </td>
   <td><em>To Be Discussed</em>
<p>
At the moment, movements are modeled by linking actors to groups, but this way of proceeding does not allow a datation of belonging to the movement, or even of the movement itself. In order to do so, an E5 Event would have to be used. 
<p>
CHIN is currently debating whether such a pattern should be adopted in order to allow datation, which is often important to art history and museums. This issue is discussed on <a href="https://github.com/chin-rcip/chin-rcip/issues/21">CHIN’s Github Issue #21</a>. 
   </td>
  </tr>
</table>



### Birth/Death of People and Formation/Dissolution of Groups

The Birth/Death and Formation/Dissolution patterns are modeled following the same pattern based on the logic of CIDOC CRM where there are events for the creation and ending of an `E39 Actor`. With this pattern, it is possible to date and place each of these events.

The use of an `E67 Birth` event also enables linking to the biological mother of the `E39 Actor` with the property `P96 by mother`, and to their biological father with the property `P97 from father`. These two `E21 Person` only represent _biological _parents and any other type of parenthood (adoptive parents, etc.) should be rendered through relationships.

For more details on this, please see 

<p id="gdcalert40" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "Appendix F: Discussions, Birth/Death of People and Formation/Dissolution of Groups"). Did you generate a TOC? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert41">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

[Appendix F: Discussions, Birth/Death of People and Formation/Dissolution of Groups](#heading=h.p8bb8jkhzluz).


<table>
  <tr>
   <td>🔎 
   </td>
   <td><em>To Be Discussed</em>
<p>
CHIN is currently debating whether family relationships (including biological ties) should be modeled using the relationship pattern considering this would entail inconsistencies in the use of fields. 
<p>
This is discussed on <a href="https://github.com/chin-rcip/chin-rcip/issues/16">CHIN’s Github Issue #16</a>  as well as mentioned below when examining 

<p id="gdcalert41" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "Relationship patterns"). Did you generate a TOC? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert42">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

<a href="#heading=h.2bn6wsx">Relationship patterns</a>. .
   </td>
  </tr>
</table>


Any `E39 Actor` can carry out `E66 Formation` and `E67 Dissolution` events so that an `E74 Group` can be responsible for the creation of another `E74 Group`. 

The main challenge when it comes to the death of a person is accounting for the location of the remains of the deceased. Such locations as graves are sometimes recorded, most notably in WikiData, so that it appears best to model them despite the fact that CIDOC CRM does not easily render such data. 

There are two ways to model such information: 



*   with an `E24 Physical Man-Made Thing` representing the grave; 
*   through a move of the `E21 Person` to his grave place after his death.

The main challenge with creating an `E24 Physical Man-Made Thing` to represent the grave is to link this `E24 Physical Man-Made Thing` with the `E21 Person` as there is no simple way to do so.

Representing the post-death move of the `E21 Person` to their grave through an `E9 Move` event is easier to model, but it is conceptually problematic as a dead person is no longer an `E21 Person` capable of carrying out activities such as moving. The logic of CIDOC CRM dictates the creation of a new `E20 Biological Object` to replace the `E21 Person`, but that considerably and unnecessarily complicates the model. 

In the absence of a simple solution, the `E9 Move` event has been chosen to represent the location of the grave, without creating a new `E20 Biological Object` in place of the `E21 Person`. Technically, it would be necessary to create an `E5 Event` to represent the transformation of the `E21 Person` into an `E18 Physical Thing` through an `E81 transformation` so that it is not induced that the person was buried alive. Because of the complexity and heaviness such a pattern would entail, CHIN has decided to compromise on semantic preciseness and to adopt a simpler model, assuming actors will be buried whilst dead.

The [project linked.art](https://linked.art/model/actor/#birth-and-death-formation-and-dissolution) came to the same conclusion and stated that:


    “After death, people are still instances of Person which is a subclass of Actor, even though they can no longer carry out activities. People in comas or otherwise completely incapacitated also cannot carry out activities, but are not temporarily non-Actors. The modeling that death is a transformation from an instance of Person to an instance of Thing adds complexity for the sake of purity, but does not add any actual value. Thus a burial activity ([aat:300263485](http://vocab.getty.edu/aat/300263485)) buries a Person, not a Thing-that-used-to-be-a-Person. However if the skeleton is then dug up and exhibited, it is exhibited as a Thing. There is, therefore, a transition at some undetermined point.”

Modeling the Birth and Death of an `E21 Person` looks like the following: 



<p id="gdcalert42" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-121.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert43">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-121.png "image_tooltip")



```
💡  Example:
Jean Paul Riopelle was born on the 7th of October 1923 in Montreal to Anna Riopel and Léon-Léopold Riopelle.

He died on the 12th of March 2002 at Saint-Antoine-de-l'Isle-aux-Grues and is buried in Montreal.

```


Modeling the Formation and Dissolution of an `E74 Group` looks like the following: 



<p id="gdcalert43" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-122.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert44">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-122.png "image_tooltip")



```
💡  Example:
The Group of Seven was founded by Lawren Harris on the 7th of May 1920 in Toronto.

The Group was dissolved at an unknown date in 1936. 

```



### Moving events

Throughout their lives or activities, `E39 Actors` may travel, live or be present in various locations that are relevant to document. 

In CIDOC CRM, there is a distinction between the physical `E21 Person` that is located in space and can be subjected to `E9 Move` events, and the more abstract `E39 Actor` and `E74 Group` that do not move through space and time.

In order to record the locations of persons and groups, additional patterns are required: :



1. A CIDOC CRM `E9 Move` pattern must be established for the `E21 Person`
2. Along with an `E8 Acquisition` event to record properties acquired by groups
3. And `E7 Activity` patterns to model the sojourns of `E21 Person` and `E74 Group` in different locations.

For more on this, please see 

<p id="gdcalert44" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "Appendix E: Moving Events"). Did you generate a TOC? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert45">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

[Appendix E: Moving Events](#heading=h.aynjpld0l6iz).


<table>
  <tr>
   <td>🔎 
   </td>
   <td><em>To Be Discussed</em>
<p>
The best way to render different group locations throughout time is still debated amongst CHIN. This issue is discussed in <a href=" https://github.com/chin-rcip/chin-rcip/issues/18">CHIN’s Github Issue #18</a>. 
<p>
How to model the geographical presence of actors in general has not been determined either and is discussed in<a href="https://github.com/chin-rcip/chin-rcip/issues/31"> CHIN’s Github Issue #31</a>. 
   </td>
  </tr>
</table>



#### Legal Headquarter Attribution

Companies’ legal and official headquarters must also be documented. This is something that could be done using the `E13 attribute assignment` class with the following pattern, although it is still under consideration and might change:



<p id="gdcalert45" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-123.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert46">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-123.png "image_tooltip")



#### Pattern 1:  `E9 Move` Event for `E21 Person`

As written above, the `E9 move` event is recommended in CIDOC CRM to document the change of location of `E19 Physical Objects` (including the `E21 Persons`). However, it does not document the location of that person, but rather the event of moving from one place to another.

This pattern can document long travels as it relies on moving events with beginning and end dates. However, it does not comply with museum databases’ logic where actor _locations _are recorded rather than their _moving_. This means that if a museum has recorded that Jean Paul Riopelle lived in Montreal, then in Paris, then once again in Montreal, there would be  2 moving events rather than 3 living locations.

The `E9 Move` pattern documents the original location with the property `P27 moved from`, and the arrival location with the property `P26 moved to`. As the `E9 Move` class is an event, it can be located in time and the `E21 Person` it pertains to can be specified using a  `P25 moved` property. 



<p id="gdcalert46" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-124.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert47">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-124.png "image_tooltip")



```
💡  Example:
Jean Paul Riopelle was born and lived in Montreal at the beginning of his life, but moved to Paris in 1947 before coming back to Montreal in 1948 and returning to Paris once again in December 1948:

```



```
💡  Example:
Jacques Cartier left France on the 20th of April 1534 and arrived in what is now Newfoundland on the 10th of May 1534. The time he spent travelling can be modeled with CIDOC CRM: 

```



#### Pattern 2: `E8 Acquisition` Event for `E74 Group`

Whilst `E21 Persons` are physical objects that can move through space and time, `E74 Groups` are _conceptual _gatherings of either `E21 Persons` or other `E74 Groups`, which means that `E74 Groups` are not located in space and time.

Because of that, `E74 Groups` cannot be participating in an `E9 Move` event. However, `E74 Groups` can be present geographically by owning a place. For example, a company may have a store in Montreal, a factory in Ottawa, and headquarters in Montreal as well. If headquarters are transferred from Montreal to Ottawa, the `E74 Group` will not `E9 Move`: rather, the initial location of the headquarters will close and a new location will be selected and occupied by the company.

Such an `E8 Acquisition` pattern can therefore be used to document the location of an `E74 Group` and its growth through time.

In this pattern, the location where the `E74 Group` is established is considered to be real estate and, as such, is an `E22 Man-made Thing`. This real estate object is acquired by the `E74 Group` through an `E8 Acquisition` event (and the two properties `P22 transferred title to` and `P24 transferred title of`). 

This same `E22 Man-made Thing` real estate object is then located geographically with the property `P54 has current permanent location` and the class `E53 Place`. This property does not document when this real estate has been constructed and is an information that is beyond the scope of what CHIN will modelise as part of its Actors or Collections models.


<table>
  <tr>
   <td>🔎 
   </td>
   <td><em>To Be Discussed</em>
<p>
Three properties in CIDOC CRM can be used to indicate the location of an <code>E22 Man Made Object</code> in an <code>E53 Place</code>:
<ol>

<li><code>P53 has former or current location</code>

<li><code>P54 has current permanent location</code>

<li><code>P55 has current location</code>

<p>
Which property is best to use is unclear considering <code>P54 has current permanent location</code> would be best for mobile objects, but CIDOC CRM rather uses <code>P53 has former or current location</code>.
</li>
</ol>
   </td>
  </tr>
</table>




<p id="gdcalert47" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-125.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert48">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-125.png "image_tooltip")



<table>
  <tr>
   <td>🔎 
   </td>
   <td><em>To Be Discussed</em>
<p>
The main downside of such a pattern is that we need to add a pattern for the loss of title of the real estate, which has not yet been modeled.
   </td>
  </tr>
</table>



```
💡  Example:
The company Example Inc. could have been established in 1881 with a single shopping location in Montreal.

```



```
🔀 Alternative (Proposed by George Bruseker)
George Bruseker proposed in one of the comments to create a new class, a CHIN:Establishing that would be the subclass of E7 Activity and E13 Attribute Assignment. A new property should also be created, CHIN:established, that would link the CHIN:Establishing event with the E53 Place.

```



<table>
  <tr>
   <td>🔎 
   </td>
   <td><em>To Be Discussed</em>
<p>
The pros and cons of each approach are discussed and examined in <a href="https://github.com/chin-rcip/chin-rcip/issues/31">CHIN’s Github Issue #31</a>. 
   </td>
  </tr>
</table>



#### Pattern 3: `E7 Activity` Sojourn for `E21 Person` and `E74 Group`

Another way of modeling the locations where an `E39 Actor` went is to have a “sojourn” pattern representing where someone stayed rather than their movements across places. In this instance, “sojourns” encompass any location where an `E39 Actor` has stayed, including their customary residence, and are not limited to vacations or travels.

In order to do so, an `E7 Activity` event is used and a “sojourn” type is assigned to it. This same  `E7 Activity` is then situated geographically and temporally.



<p id="gdcalert48" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-126.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert49">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-126.png "image_tooltip")



```
💡  Example:
Jean Paul Riopelle moved to Paris in 1947 before coming back to Montreal in 1948 and going once again to Paris in December 1948:

```



```
💡  Example:
The Group of Seven met at the Studio Building in Toronto—a building where several artist studios were situated. As we do not know of other places where these artists met on a regular basis, this is the only location associated with the group during its activity years, from 1920 to 1933.

```



### Influences

A creator might have been influenced by many things in their creative lives. These include people as well as other entities such as events or objects. However, CIDOC CRM traditionally represents influence through a relationship pattern articulated around associations between `E39 Actors`. To account for the richness of influences when it comes to creative endeavours, a different approach must be adopted as entities other than `E39 Actors` might influence a creator (events, styles, etc.). 

The `P15 was influenced by` property has an `E7 Activity` as a domain and any `E1 CRM Entity` as a range. It is meant to render things that have an influence on any activity, but not on people so that using it in conjunction with `E39 Actor` goes against its scope.

At the moment (version 2.1 of the TM), we do not have a pattern to render influences of non-actors on actors.


<table>
  <tr>
   <td>🔎 
   </td>
   <td><em>To Be Discussed</em>
<p>
In the version 1.5 of the Target Model, there was a pattern close to the relationship pattern where a <code>P15 was influenced by</code> property was used in conjunction with an <code>E7 Activity</code> to which an “influence” type was assigned. This <code>E7 Activity</code> was then linked to the <code>E39 Actor</code> with the class <code>PC14 Carried out by</code> in the role of “was influenced by”, as shown below:
<p>


<p id="gdcalert49" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-127.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert50">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


<img src="images/TM-Documentation-2-127.png" width="" alt="alt_text" title="image_tooltip">

<p>
The problem with this pattern is that it cannot render anything other than the fact that someone is <em>influenced by</em> something. If we want to model that someone <em>influenced something</em> for example, another pattern would have to be developed.
<p>
The necessity and relevance of using such a pattern is discussed on <a href="https://github.com/chin-rcip/chin-rcip/issues/33">CHIN’s Github Issue #33</a>. 
   </td>
  </tr>
</table>