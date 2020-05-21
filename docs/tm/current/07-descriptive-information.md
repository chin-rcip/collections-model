---
layout: page
title: Descriptive Information
permalink: /target-model/current/descriptive-information
---
[Back to the Table of Contents](/target-model/current/information#table-of-contents)

## Biography

CIDOC CRM dictates that textual information should be rendered with the class `E33 Linguistic Object`. The biography of an actor written by a museum staff member would enter in that category. Linking the `E39 Actor` to his biography requires the use of the `P67 refers to` property, thus indicating that the biography refers to the actor. As seen 

<p id="gdcalert55" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "above"). Did you generate a TOC? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert56">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

[above](#heading=h.1izxmvmgozxe), the content of the biography is documented in a string of text linked to the `E33 Linguistic Object` through the property `P190 has symbolic content`.

The author of the biography, most often a museum staff worker, relies on other sources of information when researching the life of the actor; said information and its sources should thus also be documented. The simplest and most semantically correct way to render such a citation is to use the Dublin Core property `dct:source` to quote the bibliographic citation as a string of text.

For more details on this, please see 

<p id="gdcalert56" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "Appendix F: Discussions, Biography."). Did you generate a TOC? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert57">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

[Appendix F: Discussions, Biography.](#heading=h.jjoy3wf22bws)



<p id="gdcalert57" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-130.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert58">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-130.png "image_tooltip")



```
💡  Example:
Jean Paul Riopelle's biography on Wikipedia (the contributor documented in the Named Graph) is the following: "Jean-Paul Riopelle, CC GOQ (7 October 1923–12 March 2002) was a painter and sculptor from Quebec, Canada. He became the first Canadian painter (since James Wilson Morrice) to attain widespread international recognition."
The source of this information is the following: "Tate, London, Artist Biography http://www.tate.org.uk/art/artists/jean-paul-riopelle-1847".

```



### Visual Item

Actors are often depicted on images or photos and it is important to link those images to actors, not only to give a visual representation of them but also to identify people and groups represented on works of art.

CIDOC CRM distinguishes visual representations (`E36 Visual Item`) from physical objects carrying such representations (`E24 Physical Man-Made Thing`) and from digital representations of such images (`D1 Digital Object`). The links between those three images concepts is depicted in the following diagram.



<p id="gdcalert58" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-131.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert59">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-131.png "image_tooltip")


It is possible to link the physical `E24 Physical Man-Made Thing` image directly to the `E39 Actor` through the `P62 depicts` property, but this simpler pattern cannot link any _digital _image (`D1 Digital Object`) to the actor.  Considering how Actors will mostly manage digital images, a more complex pattern is necessary. 

Distinguishing the URI of the `D1 Digital Object` from the URL of the digital image is necessary to refer to both resources independently. The URL of a digital image can be seen as its contact point (or address) typed as a URL assigned to an  `E41 Appellation`; it would thus be a string of text.



<p id="gdcalert59" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-132.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert60">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-132.png "image_tooltip")



```
💡  Example:
The digital scan of Louis the XIV of France by Hyacinthe Rigaud would be available on Wikimedia Commons at the following URL: 
https://upload.wikimedia.org/wikipedia/commons/5/5f/Louis_XIV_of_France.jpg



```


Besides `E36 Visual Item`, other kinds of more symbolic visual items such as signatures, companies’ logos, etc. can be represented with the `E37 Mark` class connected to an `E39 Actor` following the same pattern as with the `E36 Visual Item`. However, this requires the use of the `PC138 represents` property class to add the `P138.1 mode of representation` property specifying that the `E37 Mark` represents the actor symbolically.



<p id="gdcalert60" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-133.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert61">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-133.png "image_tooltip")



```
💡  Example:
Wikimedia Commons has digital representation of the signature of Michel de Montaigne available at the following URL:
https://upload.wikimedia.org/wikipedia/commons/6/6d/Unterschrift_des_Michel_de_Montaigne.png


```



<table>
  <tr>
   <td>🔎 
   </td>
   <td><em>To Be Discussed</em>
<p>
The best way to model images, URLs and other aspects of visual  representations is discussed on <a href="https://github.com/chin-rcip/chin-rcip/issues/17">CHIN’s Github Issue #17</a>. 
   </td>
  </tr>
</table>



### Curatorial Note

Most museums have a “remark” field linked to the actors and objects  they document in order to account for non-formatted text that is distinct from descriptive texts intended to be published (such as captions for example, which will be modelised later on as part of the Collections model). In order to model this kind of information, the `E33 Linguistic Object` class must be used before typing the text as a “curatorial note” using the` E55 Type` class. This `E33 Linguistic Object` can then be linked to the actor it is commenting on with the property `P67 refers to`. The creator of the curatorial note is considered to be the institution or person providing the data as it will be in its named graph. If a curator or member of the museum staff was an explicit author/creator, it would be possible to add a creation event that could then be linked to the creator of that curatorial note.



<p id="gdcalert61" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-134.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert62">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-134.png "image_tooltip")



```
💡  Example:
If a fictional museum has the following curatorial note about Jean Paul Riopelle "Jean Paul Riopelle est l'un des plus grands peintres Québécois", then we would have the following structured data:

```