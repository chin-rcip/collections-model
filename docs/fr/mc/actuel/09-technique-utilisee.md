---
layout: page
language: fr
title: Technique utilisée
permalink: /fr/modele-cible/actuel/technique-utilisee
other_link: /en/target-model/current/technique-used
sidebar: mc22
date: 2022-06-30
description: La Spécification du modèle cible des actants modélise sémantiquement les actants dans un contexte patrimonial. Les patrons conceptuels les plus pertinents pour la vie des actants sont présentés avec des diagrammes et des exemples qui les illustrent, ainsi qu'un compte rendu et une explication des décisions pertinentes qui ont été prises lors de l'élaboration desdits patrons conceptuels. Il s'agit d'une documentation théorique qui n'a jamais été testée ou mise en application.
---

## Aperçu {#apercu}

Ce patron conceptuel peut être utilisé pour représenter les informations sur la ou les techniques employées par un actant qui ne sont pas enregistrées dans le cadre de la production d'un objet précis. Il est particulièrement utile lorsqu'un soumissionnaire de données ne dispose d'aucun objet produit par l'actant d'intérêt ou qu'il dispose d'un champ dédié pour décrire l'actant par le ou les techniques qu'il a utilisées ou pour lesquelles il était connu. 

Ce patron conceptuel ne doit pas être utilisé pour représenter :

* Le médium d'un artefact, c'est-à-dire la substance ou le matériau;
* Les techniques employées dans la production d'un artefact;
* Le domaine de discipline dans lequel un actant a été impliqué;
* L'occupation d'un actant (voir le patron conceptuel [Occupation](/collections-model/fr/modele-cible/actuel/occupation).

## Introduction et contexte

### Historique théorique {#historique-theorique}

Une technique est « la manière dont les détails techniques sont traités (comme par un écrivain) ou les mouvements physiques de base sont utilisés (comme par un danseur) – également : la capacité à traiter de tels détails ou à utiliser de tels mouvements (bonne technique pianistique) » (Merriam-Webster 2021a; notre traduction), tandis que l'adjectif *technique* indique « marqué par ou caractéristique de la spécialisation » (Merriam-Webster 2021b; notre traduction). Cette définition semble être adoptée par plusieurs institutions culturelles telles que le Getty Research Institute (Art & Architecture Thesaurus 2021), le Museum of Modern Art (MoMA 2019), la Société des musées du Québec (SMQ 2020) et le Réseau canadien d'information sur le patrimoine (RCIP 1999).

De plus, selon la façon dont la technique est définie, l'utilisation de différents matériaux pourrait nécessiter des compétences différentes. Par exemple, dans un vocabulaire, le concept de « gravure sur bois » pourrait être défini avec des processus et des compétences différents de ceux de la « gravure sur cuivre », alors qu'un autre vocabulaire pourrait les définir comme une seule et même technique (c.-à-d. gravure) utilisée avec différents matériaux. La définition du terme *technique* dans le Art & Architecture Thesaurus confirme cette inclusion du matériel : « La hiérarchie des procédés et des techniques contient des termes pour les actions et les méthodes effectuées physiquement sur ou avec des matériaux et des objets [...] » (Art & Architecture Thesaurus 2019; notre traduction). 

### Énoncé des besoins {#enonce-des-besoins}

Dans le secteur du patrimoine, il existe des cas où un actant est connu pour avoir utilisé certaines techniques qui sont enregistrées sous forme de métadonnées directement associées à l'actant (p. ex. dans une biographie) plutôt qu'à un artefact spécifique (p. ex. les techniques utilisées dans une production). Par exemple, dans Artistes au Canada, *Technique* est l'un des éléments descriptifs relatifs à un actant (« Photographie » est la technique de Yousuf Karsh) (Patrimoine canadien, Gouvernement du Canada 2011). 

Une institution peut percevoir les données sur les techniques utilisées comme une forme de catégorisation des actants. En outre, une institution peut ne pas avoir d'objets représentant les techniques employées par l'actant; l'absence de ce champ résulterait donc à un manque d'information. Par exemple, un musée qui ne possède que des peintures d'un artiste dans ses collections peut enregistrer la technique de la peinture à travers tous ses objets; cependant, cet artiste peut aussi avoir été connu pour ses sculptures. Ainsi, un champ dédié permettrait au musée d'enregistrer la technique de la sculpture même s'il ne recueille aucun exemple de la production de l'artiste. Ces métadonnées ne doivent pas être rejetées ou fusionnées avec la production d'artefacts, car elles seraient sémantiquement inexactes et pourraient être difficiles à documenter si l'institution ne dispose d'aucun objet produit par l'actant décrit. Ainsi, ce patron conceptuel a été développé par le RCIP afin de recueillir de manière indépendante les techniques d'un actant dans le modèle DOPHEDA. 

## Description du patron conceptuel

La valeur du [Type de technique utilisée](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#type-de-technique-utilisee) est mise en correspondance comme une instance de `E55_Type` liée à une instance de `E39_Actant` par la propriété `P2_a_pour_type`. Cette instance de `E55_Type` est qualifiée par une instance de `E55_Type` (un nœud doté d’un qualifiant spécifié) portant le libellé « Technique utilisée » par la propriété `P2_a_pour_type`.

## Diagramme

<a name="031_PatronConceptuel_TechniqueUtilisee_p"></a>031_PatronConceptuel_TechniqueUtilisee_p

<div class="mxgraph" style="max-width:100%;border:1px solid #cccccc;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;target&quot;:&quot;blank&quot;,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom layers lightbox&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;xml&quot;:&quot;&lt;mxfile host=\&quot;app.diagrams.net\&quot; modified=\&quot;2023-03-15T17:12:52.160Z\&quot; agent=\&quot;5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) draw.io/20.3.0 Chrome/104.0.5112.114 Electron/20.1.3 Safari/537.36\&quot; etag=\&quot;nSJs1CDQllciGA6u2nKh\&quot; version=\&quot;20.3.0\&quot;&gt;&lt;diagram id=\&quot;9k90kyf8VMb0ZACqADbf\&quot; name=\&quot;Page-1\&quot;&gt;5Vbfb9owEP5r8hiUHwqjj5BCu63TJkHVdi/I2Efs1olTxwGyv342cRJSWrRqZS+TEPJ9vrPP33c+xwnjdHclUU6/CQLcCTyyc8JLJwgCx/w8UtWmX5uJZOQImLNfYEHPoiUjUPQclRBcsbwPYpFlgFUPQ1KKbd9tLXh/1xwlcATMMeLH6B0jitboKPI6/BpYQpudfc/OpKhxtkBBERHbAyicOmEshVD1KN3FwA1vDS913OyN2TYxCZn6k4DnTyPXvcm/up9v79AiqZ7YjLphvcoG8dIe+EewRMtclHKpqhxs6qpq+ACi6bGmkIqKRGSITzt0IkWZETCbetrqfG6EyDXoa/ARlKqs1qhUQkNUpdzO6vPI6t7ED6LGfLDL7Y3LXc+qrHVMiOWo0KfBcIKFprCQTECd8LOVbDg42MDSfQUiBZ2PdpDAkWKbfgkhW4lJ69eJpQdWr3do5x9pNw0vlmOskD7/S906VQzFW8oUzHO0Z2WrL21fgTXjPBZcyH1suF6vCEZv0rsBqWB3kpCmE4zsXbCtoL0b2+5q+Q1GD67V0Pt7Djfz+IHcs5/3UTauHv3r8aX80ij6n9d/cFz/r7Ll/6P6vy1Afl89mn4eeBytgNehTjDkOr/JSg8SM1jsJfKI+VOAacaeSzMuFeOscOLQGV9AE6U3aQPblWSDTKNouWgV5yx7qvekSpmnZmxyDWaYssyVmOWDhClargZMGFRwrpNlIivctH79Zmu98qzIAbM1w8jMufohczGFlGm3AlJ9TU26hfZDWJX7qExASQrt6RaIFUxnE5oyNEB7Prc+HdhUT/aI4EAgex8+qimgVTSMztAUwuH5moI2D2rrHX3ilV7b1svLSnLiwBnrCvMWb1ekZ5wmk49t0+dSJPLOqkj3CbSfO/iGDKe/AQ==&lt;/diagram&gt;&lt;/mxfile&gt;&quot;}"></div>

## Exemples

Dans Artistes au Canada, la principale technique associée à Yousuf Karsh est la photographie (`P2_a_pour_type`, Type de technique utilisée « Photographie ») (Patrimoine canadien, Gouvernement du Canada 2011).

<div id="0001_100_technique-used" class="example"></div>

## Documentation connexe

### Modèle externe

* SARI : [Person Reference Data Model – Knowledge](https://docs.swissartresearch.net/et/persons/#knowledge)

### Nœuds de saisie {#noeuds-de-saisie}

* [Type de technique utilisée](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#type-de-technique-utilisee) \| Liste de vérification

### Entités du CIDOC CRM {#entites-du-cidoc-crm}

* `E39_Actant` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E39)]
* `E55_Type` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E55)]
* `P2_a_pour_type (est_le_type_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P2)]

## Discussion

### Justification

Pour recueillir les données des techniques directement liées à un actant, trois options ont été envisagées par le RCIP :

* La première consiste à traiter les techniques comme les compétences qu'un actant a utilisées dans l'exercice d'une occupation. Chaque technique est modélisée comme une instance de `E55_Type` qui est liée à la même instance de `F51_Pratique` par la propriété `P32_a_mobilisé_comme_technique_générale`, et cette instance de `F51_Pratique` est effectuée par l'actant. Toutefois, ce chemin sémantique affirme que l'actant a exercé une occupation qui n'avait pas été initialement attribuée par le soumissionnaire. En plus d'informations inexactes, l'ajout de ces nœuds inutiles entraînerait des requêtes plus compliquées et plus lourdes.
* La deuxième option consiste à modéliser chaque technique comme une instance de `E55_Type` qui est directement liée à une instance de `E39_Actant` par une nouvelle propriété qui pourrait porter le libellé « Composé de connaissances » ou « A pour compétence ». Cependant, cela implique la création d'une nouvelle propriété, un processus qui devrait être évité pour les raisons détaillées dans la section [Priorisation de `E55_Type` et `P2_a_pour_type` sur les nouvelles classes et propriétés](/collections-model/fr/modele-cible/actuel/concepts-generaux#priorisation-de-e55_type-et-p2_a_pour_type-sur-les-nouvelles-classes-et-proprietes). 
* La dernière option, similaire à la seconde ci-dessus, est de modéliser chaque technique comme une instance de `E55_Type` qui est directement liée à une instance de `E39_Actant` en utilisant la propriété `P2_a_pour_type` plutôt que de créer une nouvelle propriété. La propriété `P2_a_pour_type` semble sémantiquement inexacte, car elle implique qu'un actant est d'un type, par exemple « Peinture à l'huile ». Toutefois, le CRM SIG considère cette pratique comme acceptable lorsqu'il s'agit de langues parlées par les actants (voir l'[Enjeu no 429 du CRM SIG](http://www.cidoc-crm.org/Issue/ID-429-p72-has-language). De plus, la catégorisation d'un actant semble utile, car elle fournit des informations sur la manière dont l'actant est perçu par différentes institutions.

### Limitations

Comme mentionné dans la Justification, ce patron conceptuel n'est pas idéal sur le plan sémantique. Deux alternatives sont actuellement en cours d'élaboration et pourraient éventuellement être exploitées : <a href="https://github.com/linked-art/linked.art/issues/237#issuecomment-611035443">Stratégie relationnelle de Linked.art pour E13_Assignation_d'attribut</a> ou <a href="http://www.cidoc-crm.org/crmsoc/sites/default/files/CRMsoc_20190326.pdf">CRMsoc’s Phase class</a>. 

En outre, comme le nœud de saisie Type de technique utilisée est lié directement à l'actant, la question du vocabulaire approprié persiste (voir l'[Enjeu no 76](https://github.com/chin-rcip/collections-model/issues/76)).

### Enjeux connexes sur GitHub

* [Enjeu no 1 « Techniques versus Occupations »](https://github.com/chin-rcip/collections-model/issues/1) (en anglais)
* [Enjeu no 74 « Est-il nécessaire d'ajouter une `E13_Attribution` dans le patron conceptuel Technique utilisée? »](https://github.com/chin-rcip/collections-model/issues/74) (en anglais)
* [Enjeu n° 76 « Quels termes de vocabulaire devraient être utilisés pour distinguer les différentes techniques et  occupations documentées? »](https://github.com/chin-rcip/collections-model/issues/76) (en anglais)

### Cas limites

Yousuf Karsh était particulièrement connu pour ses portraits. Comme l’indique l'Historique théorique, selon la classification choisie, un vocabulaire pourrait définir la photographie de portrait comme une technique, comme le AAT avec le « Portrait commercial » (AAT 2019), ou s'arrêter simplement à « Photographie » sans aucun terme connexe. Ce dernier point implique que la production d'un portrait ne requiert pas de compétences différentes de celles nécessaires à la production de tout type de photographie. Dans ce cas, les techniques peuvent être précisées grâce à la description des artefacts, et les informations concernant le portrait peuvent être gérées par le biais des sujets de la photographie réalisée par Yousuf Karsh ou la description de sa composition.

## Bibliographie

Art & Architecture Thesaurus. « Processes and Techniques ». *Art & Architecture Thesaurus Online Full Record Display*. 25 septembre 2019. [http://www.getty.edu/vow/AATFullDisplay?find=technique&logic=AND&note=&page=1&subjectid=300053001](http://www.getty.edu/vow/AATFullDisplay?find=technique&logic=AND&note=&page=1&subjectid=300053001).

Art & Architecture Thesaurus. « Technique (Concept) ». *Art & Architecture Thesaurus Online Full Record Display*. 13 septembre 2021. http://www.getty.edu/vow/AATFullDisplay?find="technique"&logic=AND&note=&english=N&prev_page=1&subjectid=300055843.

Bekiari, Chryssoula, George Bruseker, Martin Doerr, Christian-Emil Ore, Stephen Stead, et Athanasios Velios, éds. *Definition of the CIDOC Conceptual Reference Model*. Documentations du CIDOC CRM, 7.1. Paris, FR-IDF : CIDOC CRM Special Interest Group, 2021. [http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf](http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf).

CIDOC CRM Special Interest Group. « Issue 429: P72 Has Language ». *CIDOC CRM*. 2019. [http://www.cidoc-crm.org/Issue/ID-429-p72-has-language](http://www.cidoc-crm.org/Issue/ID-429-p72-has-language).

Merriam-Webster. « Technical ». *Dictionnaire Merriam-Webster.com*. Springfield, US-MA : Merriam-Webster, 2021a. [https://www.merriam-webster.com/dictionary/technical](https://www.merriam-webster.com/dictionary/technical).

Merriam-Webster. « Technique. » *Merriam-Webster.com Dictionary*. Springfield, US-MA : Merriam-Webster, 2021b. [https://www.merriam-webster.com/dictionary/technique](https://www.merriam-webster.com/dictionary/technique).

Museum of Modern Art. « Technique ». *Museum of Modern Art Glossary of Art Terms*. 25 septembre 2019. [https://www.moma.org/learn/moma_learning/glossary/#t](https://www.moma.org/learn/moma_learning/glossary/#t).

Patrimoine canadien, Gouvernement du Canada. « Karsh, Yousuf ». *Artistes au Canada*. Ottawa, CA-ON : Gouvernement du Canada, 2011. [https://app.pch.gc.ca/application/aac-aic/artiste_detailler_bas-artist_detail_bas.app?lang=fr&qlang=en&rID=8494&pID=1&fID=1&ps=50&sort=AM_ASC](https://app.pch.gc.ca/application/aac-aic/artiste_detailler_bas-artist_detail_bas.app?lang=fr&qlang=en&rID=8494&pID=1&fID=1&ps=50&sort=AM_ASC).

Réseau canadien d'information sur le patrimoine (RCIP). « Dictionnaires de données du RCIP ». *Dictionnaire de données du RCIP*. 9 février 1999. [https://app.pch.gc.ca/application/ddrcip-chindd/field_detailler_rechercher-search_field_detail.app?lang=fr&qlang=en&rID=1032&dd=sh-hs&sub=technique&mne=&pID=1&ac=false&rac=false](https://app.pch.gc.ca/application/ddrcip-chindd/field_detailler_rechercher-search_field_detail.app?lang=fr&qlang=en&rID=1032&dd=sh-hs&sub=technique&mne=&pID=1&ac=false&rac=false).

Société des musées du Québec. « Technique de Fabrication (Description Physique) ». *Guide de documentation du Réseau Info-Muse*. 9 décembre 2020. [https://www.musees.qc.ca/fr/professionnel/guidesel/doccoll/fr/ethno-art-techno/tf.htm](https://www.musees.qc.ca/fr/professionnel/guidesel/doccoll/fr/ethno-art-techno/tf.htm).

