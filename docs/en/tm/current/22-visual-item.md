---
layout: page
language: en
title: Visual Item
permalink: /en/target-model/current/visual-item
other_link: /fr/modele-cible/actuel/entite-visuelle
sidebar: tm22
date: 2022-03-31
description: The Actors Target Model Specification semantically models actors in a heritage context. Patterns most relevant to actors' lives are presented along with diagrams and examples illustrating them, as well as a record and explanation of relevant decisions that were made when developing said patterns. This is a theoretical documentation that has never been tested or implemented.
--- 

Version 2.2 ([Previous versions](/collections-model/en/versions))

## At Glance

This pattern can be used to represent the information pertaining to the visual representation of an actor in a digital form or depicted on a physical object. It includes: 

* The Uniform Resource Locator (URL) of the digital image of an actor;
* The bibliographical statement of the image;
* The URL of the visual identity (mark) of an actor;
* The type of the mark, for example signature, logo, emblem, etc.;
* The bibliographical statement of the mark.

This pattern should not be used to represent:

* The detailed description of the digital representation of the visual item; 
* The physical carrier of the visual item. 

## Introduction and Context

### Theoretical Background

A visual item is a multi-faceted concept that involves a perceivable component (what is represented) and the observer’s perception (how it is received). For example, it is possible to have mental images when reading a story or detect a news event in a caricature. This relationship between the image and its observer is what enables the understanding of signatures and logos which without a context or a description would only amount to random shapes. The meaning of these forms necessarily comes from an extrinsic reading of the image.

This is what Helmholtz proposes identifying spontaneous understanding as one of the faculties of representation (Leroux 1998, 149). For example, an image is instantly understood by an observer if they unconsciously have all the keys to perceive its meaning. If they have ever seen a photograph of a person, they will most likely be able to recognize that person in another position. As such, an image and its copy, even if they may differ in colour, texture, or format, can be considered to share a visual element that remains unchanged (i.e. the visual item). 

### Statement of Need

Actors are often depicted in visual elements (painting, photographs, etc.) and it is important to establish the known links between images and actors in order to document how the actors have been represented (e.g. figuratively or abstractly), but also to determine what the images illustrate. 

Multiple visual elements can be relevant to an actor's life and production, such as signatures, companies’ logos, etc. These types of marks are considered to "represent" actors. Often, these visual elements are stored in digital form in collections management systems, distributed, and available on the web at designated URLs. In addition, the use of such visual elements usually requires proper citation or source attribution.

The recording of images and of quality metadata associated with them is even more important when implementing an open access strategy in order to ensure the legal and relevant use of images. This opening of image data is anticipated to increase as institutions are noticing a better visibility of their online collections as a result of their cross-platform presence as well as greater website traffic (Kelly 2013, 24).

Visual items, especially images, play a major role in the visibility of online collections (Canadian Heritage Information Network 2020, 1). They offer a visual support that enables the quick identification of the object described in a record, as well as its depicted subject, thus increasing the likelihood that the record will be consulted. 

## Description of the Pattern

For each image that represents an actor, an instance of `E39_Actor` is first linked by an instance of `PC138_represents` to an instance of `E36_Visual_Item`, which is then connected to:

 * Another instance of `E36_Visual_Item` by the property `P165_incorporates`;

* The literal value of the [Image Bibliographical Mention](/collections-model/en/semantic-paths-specification/current/entry-nodes#image-bibliographical-mention) by the property `dct:source`;
* An instance of `E24_Physical_Human-Made_Thing` by the property `P65_shows_visual_item`;
* An instance of `D1_Digital_Object` by the property `P165_incorporates`.

The digital object is linked by the property `P1_is_identified_by` to an instance of `E42_Identifier` which is linked to the literal value of the [Image URL](/collections-model/en/semantic-paths-specification/current/entry-nodes#image-url) value through the property `P190_has_symbolic_content`. This instance of `E42_Identifier` is also qualified by an instance of `E55_Type` (a specified qualifier node) labelled "URL" by the property `P2_has_type`.

For each mark that represents an actor, an instance of `E39_Actor` is first linked by the property `P02_has_range` to an instance of `PC138_represents`, which is then connected to an instance of `E37_Mark` by the property `P01_has_domain`. The instance of `PC138_represents` is qualified by an instance of `E55_Type` (a specified qualifier node) labelled "Symbolic" by the property `P138.1_mode_of_representation`.

The instance of `E37_Mark` is then linked to:

* The [Mark Type](/collections-model/en/semantic-paths-specification/current/entry-nodes#mark-type) value (an instance of `E55_Type`) by the property `P2_has_type`;
* The literal value of the [Mark Bibliographical Mention](/collections-model/en/semantic-paths-specification/current/entry-nodes#mark-bibliographical-mention) by the property `dct:source`;
* An instance of `E24_Physical_Human-Made_Thing` by the property `P65_shows_visual_item`;
* An instance of `D1_Digital_Object` by the property `P165_incorporates`.

The digital object is linked by the property `P1_is_identified_by` to an instance of `E42_Identifier` which is linked to the literal value of the [Mark URL](/collections-model/en/semantic-paths-specification/current/entry-nodes#mark-url) through the property `P190_has_symbolic_content`. The instance of `E42_Identifier` is also qualified by an instance of `E55_Type` (a specified qualifier node) labelled "URL" by the property `P2_has_type`.

## Diagram

<a name="064_Pattern_VisualItemImageUrl_p"></a>064_Pattern_VisualItemImageUrl_p

<div class="mxgraph" style="max-width:100%;border:1px solid #cccccc;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;target&quot;:&quot;blank&quot;,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom layers lightbox&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;xml&quot;:&quot;&lt;mxfile modified=\&quot;2023-03-15T17:12:30.629Z\&quot; host=\&quot;app.diagrams.net\&quot; agent=\&quot;5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) draw.io/20.3.0 Chrome/104.0.5112.114 Electron/20.1.3 Safari/537.36\&quot; etag=\&quot;v-grHL1VA4i1Nt7xLq9n\&quot; version=\&quot;20.3.0\&quot;&gt;&lt;diagram id=\&quot;--a-xpLdCh8Zg1l4UYJX\&quot; name=\&quot;Page-1\&quot;&gt;1Vnbcps6FP0aP5LhYrB5jB2n9mk8TZum5+SJESCDXIGIJGLTrz9SEDY2NHE6vtCZjIO2Lkhr77W2JHrWOFl/oiCL5ySEuGfq4bpn3fRM0+zJPz0syqJRFiOKwobhAf2Cyqgra45CyHYackIwR9muMSBpCgO+YwOUktVuswXBu2/NQAQbhocA4Kb1XxTyWFkNXd9WTCGKYvXqoa0qElA1VgYWg5CsaiZr0rPGlBBePiXrMcQStwqXst/tb2o3E6Mw5Yd0cD8X2vPkzh3m3ybL2SCfL9lMU6O8AJyrBU8s17sOOKFq1ryooKAkT0MoRzN61mgVIw4fMhDI2pXwu7DFPMGqeoEwHhMshpF9rcXCDwPQnHL1fkg5XNdMagmfIEkgp4Voomr7AwWniqa+Kq5qzqkQj2t+cZQNqHiINiNvIRMPCrWPIDhsQHhvWEOPwoxCJhbKGkDCUISYKhLKYxKRFODJ1jraQq2L0rbNHSGZAngJOS8UX0DOyS784r20+E/2v7Kr4lO97matBi9LhSr91kOM5DSAb+DgKHICGkH+fsRJDN70N4UYcPSyS8Oje89piX/H+4FYDrA34zA5LgvCMLD6J2CB4V6aBm0scGwPpQGhGaGAw0vzwDwTEarM9S4TnE4xwW1xoIeYJ9JvytECwdDzi4u60Kj7r6Zrl/OgYXfKhdW8az68MbwbFCEu1OyLv5QbpG7qmb6rZ9bl03pzZ3Qv9IzFYkfp9UwHiwmMfLFJciL59FJmDNSWMc4rc4NzyZz5V8pcNe16xjf73n1cMCR2/d40T0CqzUEIve8xSqOj8gUaPnCDt2A/nDK2fQBlrLNSxmpSxvRiwDxeZPDCtDgXK+xDU0fHaNFvSf+u/uo9ViQ+wSjwxBmbS0Q65Em9A54cdMuTdlPg+qY3q7ZxRz7Xw4XlH+Ncb/Q7twNoORvatvf9Vcv287/4/5zLm5zR47e7beG4WAPfduwTYG1Wyn0CrB8ZpNXOU8fAh7jsuoGwQnCWyJs4Uy/xwyV6t34N4D3I10zAeM043WRpjNKf5egx5/J+8FrOyrwNRCLXaICyK7ETjnP/ChFpJRiLaSGSMi0pryxvYSp+GBRbAI4CLQM8ZhrLYCCIEwDZVPbL6Sv2srVYu5YSeUFpWkguQMspLifzdmwNag5SwfinUXKCgOg7g5MFhCjWYqKdj+Mv0+dV8RgMg3+m+dPUmn/NSMtVZSgHuFZKftGk9LGTKVwjvjnQiudaL1HadpKFk1zMteJrHjuNqa73BEm2VLHmGHviY+7FULkg1WsvjDbTOIrUjJCPEYnkNwu59xeWuUySkuUt+t6QpG4KkL+7KC2plmS+RzCzU5rkuOe74jxEkx4+h27wNDeXP5ntjp9+pF+Z3qJJXbv1/NC5pxIm/VLC1ArymYRp/07dsg8TpsZA9r7C7UdkueI/ULjDgrLlhuNv+KZh7hNePynhtx9eS9y3X66tyf8=&lt;/diagram&gt;&lt;/mxfile&gt;&quot;}"></div>


<a name="066_Pattern_Mark_p"></a>066_Pattern_Mark_p

<div class="mxgraph" style="max-width:100%;border:1px solid #cccccc;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;target&quot;:&quot;blank&quot;,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom layers lightbox&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;xml&quot;:&quot;&lt;mxfile host=\&quot;app.diagrams.net\&quot; modified=\&quot;2023-03-15T17:12:30.867Z\&quot; agent=\&quot;5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) draw.io/20.3.0 Chrome/104.0.5112.114 Electron/20.1.3 Safari/537.36\&quot; etag=\&quot;OdSIaDwGRK-EOvFBL-nz\&quot; version=\&quot;20.3.0\&quot;&gt;&lt;diagram id=\&quot;2y-6vv1WeGx6k1ehrlox\&quot; name=\&quot;Page-1\&quot;&gt;5Vpdd6I4GP41XtoDRFAvq63TOdPudKfObnvFCRAgnUDYEKrOr9+kBEGh1tlBoWdvlLz5MHme95M4APNo/YnBJLyjHiIDQ/PWA3A1MAxdH+viS0o2SpI3A4a9muAB/0RKqClphj2U7gzklBKOk12hS+MYuXxHBhmjq91hPiW7v5rAANUEDy4kdenf2ONhcSprWnbcIByE6qcnxjjviGAxWJ0kDaFHVxURuB6AOaOU50/Reo6IhK7AJZ+3eKN3uzGGYn7MhG8vjxB8+Rl89VdP+iwLll9uk6Fa5QWSTB34GkztS5dTpnbNNwUUjGaxh+Rq+gDMViHm6CGBruxdCeqFLOQRUd0+JmROiVhGzgW+73gurG+5+H3EOFpXROoInxCNEGcbMUT1ggJOpU0T1VxVyCmGhBVeLCWDSh+C7colZOJBofYLCIIagveaYYcwtRmMhW7to4g8oV+qSRkPaUBjSK5L6azEWROtcswtpYlC9xlxvlHGAjNOd7EX6LLNo5x/YRbNp2rf1Votnrc2qvUmPSnNmIsOgGAoy4QsQPx9dZMYHCSbIQI5ftm1wdapMxuo01+p82gEcdwFd6fnYNQrDsZ1DnQwudDtSAQSe2BYRJxl5ghvZAXyifo2QwlDqcBHbI92QlJpYFXzqlhbZwZm9Ypco07uXLBbMpi2GmRcd6L5/gmCzDaGdxZlRg1xemzfQfaj3TDteS4YnQBBYHWNoFVH0DTt5SZBdScjvv/JZF42e9hEDiXYLSXt4g0d0zJbwNvS+qaxej21vNct08axS1lCGeSobv3nTY6MM2VHkw8ZmfWGzFa3cWqLgizm2MfIs51NpxTq5wq/xzKoG72icFJj8Eq3r3CAOST2V+dZFsy9DB/GaNedmXrn7kyrW4PwZmlIV2lDmvqC00xgLMCLOnZy4zM5uemHdHLTelZgjOz7cJNiV/B3k0UwHt5BUYosQxwHrVoL0h04dQ+BfrzBjLQjDAac1WAaquv8vQh/zbn+D69FinDwftzol1XoTVX5VHtlL1UZse3SmEtEesSk1gMm+1WBF/uuOriRYX8uUjjWbvxHPnDaeMu7Dbf9if8NFfgR9eP3b7d9Lx33sQYTcDKsv6eIFXmnRqCDSD51C2GBYP5mQ8vhIzl4C6eC7x7i61SgeJlytg3SBMc/8sVDzuVl0aXclLFwRRwfMhcnFyINDjPnAlMppYSIXWEap8Mov8JaoFh8pEhkABy7wwTyMB2mCXKF3bjq1ePCzdgr9HK0OPowpvK2ygCR2P8wYyTfy2HNsir0KFX8rzpyAnWwwPhk6iCaFY14wxr/9J6fEFhy+w7dJzfmfAKWDddWnlzgUvnxTkPSr9WkaI35tpQVz5VZolVOko3fD2OjhijWhG/rZayaek+xNJZt1jo2d13PdE+H8gOpWXtqtN1GC45m353MsEMwDeSFtqwDxBp3MmBKk2/w9TX/1Etv5OyeaRgVJzLeszajVw7K3FeaE75aPsZBmY+Lv6JoDhH/Y5ka1B8nl0336h+0+Cn8k9aVf2qE90z+ydiLhSOjI/+kVfPMw5lQmZX2xO+UGn/QYlp0MqfKlHVz75JlerpMucHzCFH5b6Fcxcp/XIHrfwE=&lt;/diagram&gt;&lt;/mxfile&gt;&quot;}"></div>

## Examples

### Example 1

A self-portrait photograph of Yousuf Karsh is available on Wikimedia Commons at "https://upload.wikimedia.org/wikipedia/commons/3/3a/Yousuf-Karsh.jpg" (`P190_has_symbolic_content`, Image URL) with the cited source "This image was found on Wikimedia Commons (Yousuf Karsh, Public domain), and originally available from Library and Archives Canada under the reproduction reference number PA-212511 and under the MIKAN ID number 3198631" (`dct:source`, Image Bibliographical Mention) (Wikipedia 2021).

<div id="0001_100_visual-item-image" class="example"></div>

### Example 2

Wikimedia Commons has a digital representation of the signature (`P2_has_type`, Mark Type) of Yousuf Karsh available at the following URL: "https://upload.wikimedia.org/wikipedia/commons/4/46/Signature_of_Yousuf_Karsh.png" (`P190_has_symbolic_content`, Mark URL), with the cited source "This image was found on Wikimedia Commons (Signature of Yousuf Karsh, Public domain), and originally available from https://karsh.org/wordpress/wp-content/themes/bigflannel-karsh/img/karsh-signature.jpg" (`dct:source`, Mark Bibliographical Mention) (Wikipedia 2021).

<div id="0001_100_visual-item-mark" class="example"></div>

## Related Documentation

### External Models

* Linked.art: [Actors: People and Organizations – Descriptive Information](https://linked.art/model/actor/#descriptive-information)
* Linked.art: [Actors: People and Organizations – Digital Integration](https://linked.art/model/actor/#digital-integration)
* SARI: [Person Reference Data Model – Documention](https://docs.swissartresearch.net/et/persons/#documentation) 

### Entry Nodes

* [Image Bibliographical Mention](/collections-model/en/semantic-paths-specification/current/entry-nodes#image-bibliographical-mention) \| Checklist
* [Image URL](/collections-model/en/semantic-paths-specification/current/entry-nodes#image-url) \| Checklist
* [Mark Bibliographical Mention](/collections-model/en/semantic-paths-specification/current/entry-nodes#mark-bibliographical-mention) \| Checklist
* [Mark Type](/collections-model/en/semantic-paths-specification/current/entry-nodes#mark-type) \| Checklist
* [Mark URL](/collections-model/en/semantic-paths-specification/current/entry-nodes#mark-url) \| Checklist

### CIDOC CRM Entities

* `dct:source`
* `D1_Digital_Object`
* `E24_Physical_Human-Made_Thing` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E24)]
* `E36_Visual_Item` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E36)]
* `E37_Mark` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E37)]
* `E39_Actor` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E39)]
* `E42_Identifier` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E42)]
* `E55_Type` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E55)]
* `PC138_represents`
* `P01_has_domain (is_domain_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P01)]
* `P02_has_range (is_range_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P02)]
* `P1_is_identified_by (identifies)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P1)]
* `P2_has_type (is_type_of)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P2)]
* `P65_shows_visual_item (is_shown_by)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P65)]
* `P138_represents (has representation)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P138)]
* `P138.1_mode_of_representation` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P138.1)]
* `P165_incorporates (is_incorporated_by)` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P165)]
* `P190_has_symbolic_content` [[Scope Note](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P190)]

## Discussion

### Rationale

CIDOC CRM distinguishes visual representations (`E36_Visual_Item`) from the physical objects carrying such representations (`E24_Physical_Human-Made_Thing`) and their digital representations (`D1_Digital_Object`).

While the physical carrier of a visual representation (`E24_Physical_Human-Made_Thing`) can be directly linked to an instance of `E39_Actor` through the property `P62_depicts`, its *digital* form (`D1_Digital_Object`) cannot be linked to this instance. Considering how digital images have become a common asset in the heritage sector, a more precise pattern accounting for the fact that there might be several supports of a single `E36_Visual_Item` is necessary. 

Visual items are, as the scope note of the CIDOC CRM class states, "intellectual or conceptual aspects of recognisable marks and images" (Le Bœuf et al. 2015, sect. E36 Visual Item). They are independent of the orientation, size, colour, or any other characteristics that do not affect their identification. For example, a black and white copy of the *Mona Lisa* would still be considered to carry the visual item of the *Mona Lisa*. A more challenging case, however, pertains to the alteration of an image that remains recognizable, but could be considered as a new item (e.g. Andy Warhol's *Marilyn Diptych*, which uses a photograph of Marilyn Monroe and "recolours" it, can be considered as a new artwork, and therefore as a new visual item). In some cases, a visual item could be sub·divided into multiple ones, especially if an image contains other visual items, as in the case of [Giovanni Paolo Panini’s *Modern Rome*](https://commons.wikimedia.org/wiki/File:Panini,_Modern_Rome.jpg). In any case, it is possible to link multiple instances of `E36_Visual_Item` together with the property `P165_incorporates`. This pattern enables the record of the incorporation of one visual item in another one (e.g. Warhol’s *Marilyn Diptych* painting incorporates an original Marilyn Monroe photography; Panini’s *Modern Rome* incorporates depictions of several famous artworks such as Michelangelo's *Moses* and Gian Lorenzo Bernini's *Constantine*, *David*, and *Apollo and Daphne*).

Additionally, it is necessary to distinguish a visual item’s digital rendering in the form of an image from its URL which must be referred to independently from the digital object's URI. The URL of the digital image is thus assigned an identifier (`E42_Identifier`).

In the case of marks, the class `E37_Mark` is used to model the mark of an actor as its scope is semantically more precise than the class `E36_Visual_Item`. It is connected to an instance of `E39_Actor` following the same pattern as that of the `E36_Visual_Item`. However, this requires the use of the property-class `PC138_represents` to specify (with the property `P138.1_mode_of_representation`) that the mark represents the actor symbolically.

### Limitations

This pattern contains three limitations whose research is still underway:

* Its scope is only limited to modelling the presence of an actor within a visual item, and does not include the description of the visual item itself;
* It does not contain any information on rights or licences; 
* The citation of the visual elements is modelled as unstructured plain text, though, preferably, it should be more structured to be more semantically expressive.

Another limitation is the lack of a property allowing to connect the instances of the physical object with the URL of its digital image. Currently, the only way to do this is through the class `E36_Visual_Item`. In the case of two or more physical objects showing the same image and the digital image of each having its own URL, it becomes difficult to ascertain which URL can be used to render the image of which object (see [Issue #65](https://github.com/chin-rcip/collections-model/issues/65)). The only way to get around this limitation is to associate an instance of `E24_Physical_Human-Made_Thing` and an instance of `D1_Digital_Object` with an instance of `E36_Visual_Item`. This temporary solution is not optimal since it leads to the creation of several instances of `E36_Visual_Item` which normally should be under the same URI if its scope note was respected.

### Related GitHub Issues

* [Issue #17 "How to model images and how to integrate images URLs?"](https://github.com/chin-rcip/chin-rcip/issues/17)
* [Issue #65 "Visual Item Description"](https://github.com/chin-rcip/chin-rcip/issues/65)

### Edge Cases

#### Example 1 {#edge-cases-example-1}

Pope John XXIII was photographed by Yousuf Karsh in 1959 ([Karsh n.d.](https://karsh.org/photographs/pope-john-xxiii/)). During the shoot, another photograph was taken which shows Yousuf Karsh discussing with the Pope ([Karsh n.d.](https://karsh.org/yousuf-karsh-and-pope-john-xxiii-1959/)). Since the Pope is in two shots taken from the same event, it is up to the cataloguer to decide whether the visual item in the second photograph contains the visual item in the first one. The scope note of the class `E36_Visual_Item` which uses concepts like "recognizable" or "uniquely identifiable" (Bekiari et al. 2021, sect. E36 Visual Item) works relatively well for immutable objects, but its application becomes more complex for actors. Depending on the cataloguer, several criteria may or may not be taken into consideration such as the date and location of the image taken, the actor's position, the action in progress, the clothing worn, etc. If the visual item of the first photograph is defined as "Pope John XXIII", this same visual item is also found in the second photograph. However, if the visual item in the first photograph is defined as "Pope John XXIII photographed with his hand in the air", this same visual item is not part of the second photograph.

#### Example 2 {#edge-cases-example-2}

*Mawu-che-hitoowin: A Gathering of People for any Purpose* is a 1992 installation by Rebecca Belmore. Whether the rights mention of such an image ("© Rebecca Belmore 1992") could be considered to be bibliographical is debatable.

## Bibliography

Bekiari, Chryssoula, George Bruseker, Martin Doerr, Christian-Emil Ore, Stephen Stead, and Athanasios Velios, eds. *Definition of the CIDOC Conceptual Reference Model*. CIDOC CRM Documentations, 7.1. Paris, FR-IDF: CIDOC CRM  Special Interest Group, 2021. [http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf](http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf).

Canadian Heritage Information Network (CHIN). Review of *Capture Your Collections: A Guide for Managers Who Are Planning and Implementing Digitization Projects*, by Ern Bieman. Government of Canada. 2020. [https://publications.gc.ca/collections/collection_2020/pch/CH57-4-10-2020-eng.pdf](https://publications.gc.ca/collections/collection_2020/pch/CH57-4-10-2020-eng.pdf).

Doerr, Martin, Stephen Stead, and Maria Theodoridou. *Definition of the CRMdig: An Extension of CIDOC-CRM to Support Provenance Metadata*. CRMdig, 3.2.1. Heraklion, GR: CIDOC CRM, 2016. [http://www.cidoc-crm.org/crmdig/ModelVersion/version-3.2.1](http://www.cidoc-crm.org/crmdig/ModelVersion/version-3.2.1).

​​DCMI Usage Board. "DCMI Metadata Terms." *Dublin Core Metadata Initiative*. January 20, 2020. [http://dublincore.org/specifications/dublin-core/dcmi-terms](http://dublincore.org/specifications/dublin-core/dcmi-terms).

FORTH-ICS. *CRMpc 1.0*. 2014. [http://www.cidoc-crm.org/sites/default/files/CRMpc_v1.0.rdfs](http://www.cidoc-crm.org/sites/default/files/CRMpc_v1.0.rdfs).

Karsh, Yousuf. "Pope John XXIII." *Yousuf Karsh* (blog). n.d. [https://karsh.org/photographs/pope-john-xxiii/](https://karsh.org/photographs/pope-john-xxiii/).

Karsh, Yousuf. "With Pope John XXIII, 1959." *Yousuf Karsh* (blog). n.d. [https://karsh.org/yousuf-karsh-and-pope-john-xxiii-1959/](https://karsh.org/yousuf-karsh-and-pope-john-xxiii-1959/).

Kelly, Kristin. *Images of Works of Art in Museum Collections: The Experience of Open Access, A Study of 11 Museums*. CLIR Publication 157. Washington, USA-DC: Council on Library and Information Resources (CLIR), 2013. [https://www.clir.org/wp-content/uploads/sites/6/pub157.pdf](https://www.clir.org/wp-content/uploads/sites/6/pub157.pdf).

Le Bœuf, Patrick, Martin Doerr, Christian Emil Ore, and Stephen Stead, eds. "E36 Visual Item." *Definition of the CIDOC Conceptual Reference Model*. CIDOC CRM Documentations, 6.2.1. Paris, FR-IDF: International Council of Museums (ICOM), 2015. [http://www.cidoc-crm.org/sites/default/files/cidoc_crm_version_6.2.1.pdf](http://www.cidoc-crm.org/sites/default/files/cidoc_crm_version_6.2.1.pdf).

Leroux, Jean. "Les 'Théories de L’image' De Helmholtz et de Hertz et Les Motifs de Carnap Dans L’aufbau." *The Paideia Archive: Twentieth World Congress of Philosophy* 37, (1998): 148–154. [https://doi.org/10.5840/wcp20-paideia199837665](https://doi.org/10.5840/wcp20-paideia199837665).

Wikipedia. "Yousuf Karsh." *Wikipedia*. San Francisco, US-CA: Wikipedia, 2021. [https://fr.wikipedia.org/wiki/Yousuf_Karsh](https://fr.wikipedia.org/wiki/Yousuf_Karsh).

