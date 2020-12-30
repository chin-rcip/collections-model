---
layout: page
title: Descriptive Information
permalink: /target-model/current/descriptive-information
sidebar: tm
---
<!-- [Back to the Table of Contents](/collections-model/target-model/current/information#table-of-contents)
 -->
## On This Page

* [Biography](#biography)
* [Visual Item](#visual-item)
* [Curatorial Note](#curatorial-note)

## Biography

CIDOC CRM dictates that textual information should be rendered with the class `E33 Linguistic Object`. The biography of an actor written by a museum staff member would enter in that category. Linking the `E39 Actor` to his biography requires the use of the `P67 refers to` property, thus indicating that the biography refers to the actor. As seen [above](/collections-model/target-model/current/general-concepts#literal-content), the content of the biography is documented in a string of text linked to the `E33 Linguistic Object` through the property `P190 has symbolic content`.

The author of the biography, most often a museum staff worker, relies on other sources of information when researching the life of the actor; said information and its sources should thus also be documented. The simplest and most semantically correct way to render such a citation is to use the Dublin Core property `dct:source` to quote the bibliographic citation as a string of text.

For more details on this, please see [Appendix F: Discussions, Biography.](/collections-model/target-model/current/appendix-f-discussions#discussion-biography)

<a name="061_Pattern_Biography_p"></a>061_Pattern_Biography_p
<iframe frameborder="0" style="width:100%;height:400px;" src="https://viewer.diagrams.net/?highlight=0000ff&edit=_blank&layers=1&nav=1&title=061_Pattern_Biography_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1MW5F9Ybl02W4uyN20cxWln3J_rKuLb6x%26export%3Ddownload"></iframe>


| 💡  Example: <br/><br/>Jean Paul Riopelle's biography on Wikipedia (the contributor documented in the Named Graph) is the following: "Jean-Paul Riopelle, CC GOQ (7 October 1923–12 March 2002) was a painter and sculptor from Quebec, Canada. He became the first Canadian painter (since James Wilson Morrice) to attain widespread international recognition." <br/><br/>The source of this information is the following: "Tate, London, Artist Biography http://www.tate.org.uk/art/artists/jean-paul-riopelle-1847". |

<a name="062_Example_BiographyRiopelle_p"></a>062_Example_BiographyRiopelle_p
<iframe frameborder="0" style="width:100%;height:500px;" src="https://viewer.diagrams.net/?highlight=0000ff&edit=_blank&layers=1&nav=1&title=062_Example_BiographyRiopelle_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D122vVvCg7XgVwYN-q9JFHjjL-yVCJbM4e%26export%3Ddownload"></iframe>


## Visual Item

Actors are often depicted on images or photos and it is important to link those images to actors, not only to give a visual representation of them but also to identify people and groups represented on works of art.

CIDOC CRM distinguishes visual representations (`E36 Visual Item`) from physical objects carrying such representations (`E24 Physical Human-Made Thing`) and from digital representations of such images (`D1 Digital Object`). The links between those three images concepts is depicted in the following diagram.

<a name="063_Pattern_VisualItemDigitalObject_p"></a>063_Pattern_VisualItemDigitalObject_p
<iframe frameborder="0" style="width:100%;height:400px;" src="https://viewer.diagrams.net/?highlight=0000ff&edit=_blank&layers=1&nav=1&title=063_Pattern_VisualItemDigitalObject_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1Pk2bUZK8D12yLEmCSRBxQJz-tqWkR-4S%26export%3Ddownload"></iframe>


It is possible to link the physical `E24 Physical Human-Made Thing` image directly to the `E39 Actor` through the `P62 depicts` property, but this simpler pattern cannot link any *digital* image (`D1 Digital Object`) to the actor.  Considering how Actors will mostly manage digital images, a more complex pattern is necessary. 

Distinguishing the URI of the `D1 Digital Object` from the URL of the digital image is necessary to refer to both resources independently. The URL of a digital image can be seen as its contact point (or address) typed as a URL assigned to an  `E41 Appellation`; it would thus be a string of text.

<a name="064_Pattern_VisualItemImageUrl_p"></a>064_Pattern_VisualItemImageUrl_p
<iframe frameborder="0" style="width:100%;height:500px;" src="https://viewer.diagrams.net/?highlight=0000ff&edit=_blank&layers=1&nav=1&title=064_Pattern_VisualItemImageUrl_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1pENxJQXA721axvoY4jCV8vMY8-8XsQpR%26export%3Ddownload"></iframe>


| 💡  Example: <br/><br/> The digital scan of Louis the XIV of France by Hyacinthe Rigaud would be available on Wikimedia Commons at the following URL: [https://upload.wikimedia.org/wikipedia/commons/5/5f/Louis_XIV_of_France.jpg](https://upload.wikimedia.org/wikipedia/commons/5/5f/Louis_XIV_of_France.jpg) ![Digital scan of Louis the XIV of France](https://upload.wikimedia.org/wikipedia/commons/5/5f/Louis_XIV_of_France.jpg){:height="300px" width="200px"} |


<a name="065_Example_VisualItemLouisxiv_p"></a>065_Example_VisualItemLouisxiv_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?highlight=0000ff&edit=_blank&layers=1&nav=1&title=065_Example_VisualItemLouisxiv_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1j-mYcUS-y42HH3tfzsVF7CYu_dT6iEfe%26export%3Ddownload"></iframe>


Besides `E36 Visual Item`, other kinds of more symbolic visual items such as signatures, companies’ logos, etc. can be represented with the `E37 Mark` class connected to an `E39 Actor` following the same pattern as with the `E36 Visual Item`. However, this requires the use of the `PC138 represents` property class to add the `P138.1 mode of representation` property specifying that the `E37 Mark` represents the actor symbolically.

<a name="066_Pattern_Mark_p"></a>066_Pattern_Mark_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?highlight=0000ff&edit=_blank&layers=1&nav=1&title=066_Pattern_Mark_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1GzXllA_LfM1Y8RbrHkr7hkmS6_sQB3JC%26export%3Ddownload"></iframe>


| 💡  Example: <br/><br/> Wikimedia Commons has digital representation of the signature of Michel de Montaigne available at the following URL: [https://upload.wikimedia.org/wikipedia/commons/6/6d/Unterschrift_des_Michel_de_Montaigne.png](https://upload.wikimedia.org/wikipedia/commons/6/6d/Unterschrift_des_Michel_de_Montaigne.png) ![Digital representation of the signature of Michel de Montaigne](https://upload.wikimedia.org/wikipedia/commons/6/6d/Unterschrift_des_Michel_de_Montaigne.png){:height="96px" width="223px"} |

<a name="067_Example_MarkMontaigne_p"></a>067_Example_MarkMontaigne_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?highlight=0000ff&edit=_blank&layers=1&nav=1&title=067_Example_MarkMontaigne_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1ZKzgqArC_GtzobCoN2_opNVGETAr-N9Q%26export%3Ddownload"></iframe>

| 🔎  *To Be Discussed* <br/><br/>The best way to model images, URLs and other aspects of visual  representations is discussed on <a href="https://github.com/chin-rcip/chin-rcip/issues/17">CHIN’s Github Issue #17</a>. |


## Curatorial Note

Most museums have a “remark” field linked to the actors and objects  they document in order to account for non-formatted text that is distinct from descriptive texts intended to be published (such as captions for example, which will be modelised later on as part of the Collections model). In order to model this kind of information, the `E33 Linguistic Object` class must be used before typing the text as a “curatorial note” using the` E55 Type` class. This `E33 Linguistic Object` can then be linked to the actor it is commenting on with the property `P67 refers to`. The creator of the curatorial note is considered to be the institution or person providing the data as it will be in its named graph. If a curator or member of the museum staff was an explicit author/creator, it would be possible to add a creation event that could then be linked to the creator of that curatorial note.

<a name="068_Pattern_CuratorialNote_p"></a>068_Pattern_CuratorialNote_p
<iframe frameborder="0" style="width:100%;height:500px;" src="https://viewer.diagrams.net/?highlight=0000ff&edit=_blank&layers=1&nav=1&title=068_Pattern_CuratorialNote_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1ueJAi79FDWdpOIPc30mHcCcBvQfgCJiP%26export%3Ddownload"></iframe>


| 💡  Example: <br/><br/>If a fictional museum has the following curatorial note about Jean Paul Riopelle "Jean Paul Riopelle est l'un des plus grands peintres Québécois", then we would have the following structured data: |

<a name="069_Example_CuratorialNoteRiopelle_p"></a>069_Example_CuratorialNoteRiopelle_p
<iframe frameborder="0" style="width:100%;height:500px;" src="https://viewer.diagrams.net/?highlight=0000ff&edit=_blank&layers=1&nav=1&title=069_Example_CuratorialNoteRiopelle_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1h86daQriZxfUhn7dnddrCUD-JI3P6-pZ%26export%3Ddownload"></iframe>


> Previous: [Social Bonds](/collections-model/target-model/current/social-bonds)<br>Next: [Artefacts](/collections-model/target-model/current/artefacts)
