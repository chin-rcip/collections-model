---
layout: page
language: en
title: Descriptive Information
permalink: /en/target-model/current/descriptive-information
other_link: /fr/modele-cible/actuel/introduction
sidebar: tm
---
<!-- [Back to the Table of Contents](/collections-model/en/target-model/current/information#table-of-contents)
 -->


## Biography

CIDOC CRM dictates that textual information should be rendered with the class `E33_Linguistic_Object`. The biography of an actor written by a museum staff member would enter in that category. Linking the `E39_Actor` to his biography requires the use of the `P67_refers_to` property, thus indicating that the biography refers to the actor. As seen [above](/collections-model/en/target-model/current/general-concepts#literal-content), the content of the biography is documented in a string of text linked to the `E33_Linguistic_Object` through the property `P190_has_symbolic_content`.

The author of the biography, most often a museum staff worker, relies on other sources of information when researching the life of the actor; said information and its sources should thus also be documented. The simplest and most semantically correct way to render such a citation is to use the Dublin Core property `dct:source` to quote the bibliographic citation as a string of text.

For more details on this, please see [Appendix F: Discussions, Biography.](/collections-model/en/target-model/current/appendix-f-discussions#discussion-biography)

<a name="061_Pattern_Biography_p"></a>061_Pattern_Biography_p
<iframe frameborder="0" style="width:100%;height:400px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=061_Pattern_Biography_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1MW5F9Ybl02W4uyN20cxWln3J_rKuLb6x%26export%3Ddownload"></iframe>


| 💡  Example: <br/><br/>Jean Paul Riopelle's biography on Wikipedia (the contributor documented in the Named Graph) is the following: "Jean-Paul Riopelle, CC GOQ (7 October 1923–12 March 2002) was a painter and sculptor from Quebec, Canada. He became the first Canadian painter (since James Wilson Morrice) to attain widespread international recognition." <br/><br/>The source of this information is the following: "Tate, London, Artist Biography http://www.tate.org.uk/art/artists/jean-paul-riopelle-1847". |

<a name="062_Example_BiographyRiopelle_p"></a>062_Example_BiographyRiopelle_p
<iframe frameborder="0" style="width:100%;height:500px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=062_Example_BiographyRiopelle_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D122vVvCg7XgVwYN-q9JFHjjL-yVCJbM4e%26export%3Ddownload"></iframe>


## Visual Item

Actors are often depicted on images or photos and it is important to link those images to actors, not only to give a visual representation of them but also to identify people and groups represented on works of art.

CIDOC CRM distinguishes visual representations (`E36_Visual_Item`) from physical objects carrying such representations (`E24_Physical_Human-Made_Thing`) and from digital representations of such images (`D1_Digital_Object`). The links between those three images concepts is depicted in the following diagram.

<a name="063_Pattern_VisualItemDigitalObject_p"></a>063_Pattern_VisualItemDigitalObject_p
<iframe frameborder="0" style="width:100%;height:400px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=063_Pattern_VisualItemDigitalObject_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1Pk2bUZK8D12yLEmCSRBxQJz-tqWkR-4S%26export%3Ddownload"></iframe>


It is possible to link the physical `E24_Physical_Human-Made_Thing` image directly to the `E39_Actor` through the `P62_depicts` property, but this simpler pattern cannot link any *digital* image (`D1_Digital_Object`) to the actor.  Considering how Actors will mostly manage digital images, a more complex pattern is necessary. 

Distinguishing the URI of the `D1_Digital_Object` from the URL of the digital image is necessary to refer to both resources independently. The URL of a digital image can be seen as its contact point (or address) typed as a URL assigned to an  `E42_Identifier`; it would thus be a string of text.

Moreover, visual items are, as the scope note of the CIDOC CRM class states, "intellectual or conceptual aspects of recognisable marks and images" [(Le Boeuf et al. 2015, sec. E36 Visual Item)](/collections-model/en/target-model/current/bibliography#le-boeuf-et-al-2015), no matter the orientation, size, color or other characteristics that does not affect the identification of a visual item. For example, a black and white copy of the Mona Lisa would still carry the Visual Item of the Mona Lisa. A more complex case is when the alteration of an image, although still recognizable, is considered as a new artwork. For example, the work of Andy Warhol, transforming a photo of Marilyn Monroe by simply adding new colors, can be considered as a new artwork, and therefore a new Visual Item. In some other cases, a Visual Item can be subdivided in multiple ones, especially if an image contains other artwork, like the famous Giovanni Paolo Panini’s *Modern Rome*.

In both cases, it is possible to link multiple instances of `E36_Visual_Item` together with the property `P165_incorporates`. This pattern, it can be possible to document that one visual item incorporates another one (in the case of Andy Warhol’s *Marilyn Monroe*, it incorporates the original photography, while in the case of Panini’s *Modern Rome*, it incorporates all the artworks visible).

<a name="064_Pattern_VisualItemImageUrl_p"></a>064_Pattern_VisualItemImageUrl_p
<iframe frameborder="0" style="width:100%;height:500px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=064_Pattern_VisualItemImageUrl_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1pENxJQXA721axvoY4jCV8vMY8-8XsQpR%26export%3Ddownload"></iframe>


| 💡  Example: <br/><br/> The digital scan of Louis the XIV of France by Hyacinthe Rigaud would be available on Wikimedia Commons at the following URL: [https://upload.wikimedia.org/wikipedia/commons/5/5f/Louis_XIV_of_France.jpg](https://upload.wikimedia.org/wikipedia/commons/5/5f/Louis_XIV_of_France.jpg) ![Digital scan of Louis the XIV of France](https://upload.wikimedia.org/wikipedia/commons/5/5f/Louis_XIV_of_France.jpg){:height="300px" width="200px"} |


<a name="065_Example_VisualItemLouisxiv_p"></a>065_Example_VisualItemLouisxiv_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=065_Example_VisualItemLouisxiv_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1j-mYcUS-y42HH3tfzsVF7CYu_dT6iEfe%26export%3Ddownload"></iframe>


Besides `E36_Visual_Item`, other kinds of more symbolic visual items such as signatures, companies’ logos, etc. can be represented with the `E37_Mark` class connected to an `E39_Actor` following the same pattern as with the `E36_Visual_Item`. However, this requires the use of the `PC138_represents` property class to add the `P138.1_mode_of_representation` property specifying that the `E37_Mark` represents the actor symbolically.

<a name="066_Pattern_Mark_p"></a>066_Pattern_Mark_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=066_Pattern_Mark_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1GzXllA_LfM1Y8RbrHkr7hkmS6_sQB3JC%26export%3Ddownload"></iframe>


| 💡  Example: <br/><br/> Wikimedia Commons has digital representation of the signature of Michel de Montaigne available at the following URL: [https://upload.wikimedia.org/wikipedia/commons/6/6d/Unterschrift_des_Michel_de_Montaigne.png](https://upload.wikimedia.org/wikipedia/commons/6/6d/Unterschrift_des_Michel_de_Montaigne.png) ![Digital representation of the signature of Michel de Montaigne](https://upload.wikimedia.org/wikipedia/commons/6/6d/Unterschrift_des_Michel_de_Montaigne.png){:height="96px" width="223px"} |

<a name="067_Example_MarkMontaigne_p"></a>067_Example_MarkMontaigne_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=067_Example_MarkMontaigne_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1ZKzgqArC_GtzobCoN2_opNVGETAr-N9Q%26export%3Ddownload"></iframe>

| ![GitHub Mark](https://user-images.githubusercontent.com/48293227/104475587-49182180-558d-11eb-87fc-9f95190cb332.png) *Related Github Issue*<br/><br/>This topic is discussed in [Issue #17](https://github.com/chin-rcip/chin-rcip/issues/17) |


## Curatorial Note

Most museums have a “remark” field linked to the actors and objects  they document in order to account for non-formatted text that is distinct from descriptive texts intended to be published (such as captions for example, which will be modelised later on as part of the Collections model). In order to model this kind of information, the `E33_Linguistic_Object` class must be used before typing the text as a “curatorial note” using the `E55_Type` class. This `E33_Linguistic_Object` can then be linked to the actor it is commenting on with the property `P67_refers_to`. The creator of the curatorial note is considered to be the institution or person providing the data as it will be in its named graph. If a curator or member of the museum staff was an explicit author/creator, it would be possible to add a creation event that could then be linked to the creator of that curatorial note.

<a name="068_Pattern_CuratorialNote_p"></a>068_Pattern_CuratorialNote_p
<iframe frameborder="0" style="width:100%;height:500px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=068_Pattern_CuratorialNote_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1ueJAi79FDWdpOIPc30mHcCcBvQfgCJiP%26export%3Ddownload"></iframe>


| 💡  Example: <br/><br/>If a fictional museum has the following curatorial note about Jean Paul Riopelle "Jean Paul Riopelle est l'un des plus grands peintres Québécois", then we would have the following structured data: |

<a name="069_Example_CuratorialNoteRiopelle_p"></a>069_Example_CuratorialNoteRiopelle_p
<iframe frameborder="0" style="width:100%;height:500px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=069_Example_CuratorialNoteRiopelle_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1h86daQriZxfUhn7dnddrCUD-JI3P6-pZ%26export%3Ddownload"></iframe>


> Previous: [Social Bonds](/collections-model/en/target-model/current/social-bonds)<br>Next: [Artefacts](/collections-model/en/target-model/current/artefacts)
