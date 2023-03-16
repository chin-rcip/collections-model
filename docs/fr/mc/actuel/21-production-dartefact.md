---
layout: page
language: fr
title: Production d'artefact
permalink: /fr/modele-cible/actuel/production-dartefact
other_link: /en/target-model/current/artefact-production
sidebar: mc22
date: 2022-06-30
description: La Spécification du modèle cible des actants modélise sémantiquement les actants dans un contexte patrimonial. Les patrons conceptuels les plus pertinents pour la vie des actants sont présentés avec des diagrammes et des exemples qui les illustrent, ainsi qu'un compte rendu et une explication des décisions pertinentes qui ont été prises lors de l'élaboration desdits patrons conceptuels. Il s'agit d'une documentation théorique qui n'a jamais été testée ou mise en application.
---

## Aperçu {#apercu}

Ce patron conceptuel peut être utilisé pour enregistrer de manière minimale les informations relatives à la production d'un artefact tangible. Il comprend : 

* Le ou les rôles du ou des actants dans la production d'un artefact; 
* Le moment lorsqu'un artefact a été créé; 
* Le lieu où un artefact a été créé;
* Le niveau de priorité de l'actant ayant contribué à sa production.

Il ne comprend pas : 

* Le titre de l'artefact (le patron conceptuel [Artefact](/collections-model/fr/modele-cible/actuel/artefact) doit plutôt être utilisé); 
* D'autres identifiants de l'artefact (le patron conceptuel [Artefact](/collections-model/fr/modele-cible/actuel/artefact) doit plutôt être utilisé). 

Les informations relatives aux artefacts eux-mêmes ainsi qu'à leur collecte, leur recherche, leur manipulation et leur conservation ne sont actuellement pas prises en compte dans ce patron conceptuel. Les informations minimales nécessaires pour identifier plutôt que décrire les artefacts ont été priorisées.

## Introduction et contexte

### Historique théorique {#historique-theorique}

Fondamentalement, la production, la recherche et la collecte patrimoniales sont des formes de relation être humain-objet qui sont de plus en plus comprises au-delà du statut de l'être humain comme producteur de sens et de l'objet comme production illustrative (Macdonald 2011, 93). Au contraire, les artefacts sont de plus en plus considérés comme des espaces de significations interreliées ayant une valeur (Bann 2003, 120). Ainsi, la notion d'artefact a beaucoup évolué au cours des vingt dernières années pour inclure le patrimoine culturel immatériel ainsi que les objets matériels. Parce que la relation entre l'être humain et les artefacts est significative pour le secteur du patrimoine, elle fait l'objet d'une multiplicité de recherches et de pratiques, en particulier dans le cas du patrimoine immatériel qui s'incarne souvent dans les modes humains et vivants (Đerić, Neyrinck, & Seghers 2020, 11).

### Énoncé des besoins {#enonce-des-besoins}

Dans le contexte du modèle DOPHEDA actuel, les artefacts sont compris comme englobant les objets matériels, qui constituent souvent l'unité centrale des enregistrements des bases de données patrimoniales. À cette fin, un certain nombre d'informations de base sont généralement utilisées à travers les disciplines. Une évaluation des champs pouvant leur être associés a été réalisée par le J. Paul Getty Trust lors de l'établissement d'un identifiant pour les objets (Object ID), une norme internationale pour les biens culturels destinée à prévenir le commerce illicite des artefacts dans le monde entier (ICOM 2021). Ces champs d'identification normés sont les suivants : 

* Type d'objet;
* Matériaux et techniques;
* Mesures;
* Inscriptions et marques;
* Caractéristiques particulières;
* Titre;
* Sujet;
* Date ou époque;
* Producteur·rice. 

Comme la seule fonction du patron conceptuel Production d'artefact est de prendre en compte les objets en tant qu'unité centrale d'enregistrement dans les collections patrimoniales, tous ces éléments ne sont pas abordés dans le modèle; seuls le rôle de la personne ayant produit l'artefact et la date ou la période de production sont pris en considération. Les titres et les identifiants sont traités dans le patron conceptuel [Artefact](/collections-model/fr/modele-cible/actuel/artefact).

## Description du patron conceptuel

Les informations relatives à l'identification et au rôle de l'actant ayant contribué à la production de l'artefact sont centrées sur une instance de `PC14_a_été_effectué_par` liée à une instance de `E12_Production` par la propriété `P01_a_pour_domaine`. Cette instance de `PC14_a_été_effectué_par` pointe vers une instance de `E39_Actant` identifiant l'actant par la propriété `P02_a_pour_portée`. 

Pour clarifier le rôle de cet actant, la même instance de `PC14_a_été_effectué_par` est liée à la valeur du [Rôle de l'actant dans la production](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#role-de-lactant-dans-la-production) (une instance de `E55_Type`) par la propriété `P14.1_dans_le_rôle_de`. Cette instance de `E55_Type` est qualifiée par une autre instance de `E55_Type` (un nœud doté d'un qualifiant spécifié) portant le libellé « Rôle de l'actant » par la propriété `P2_a_pour_type`. 

Pour préciser la priorité de l'actant dans la production de l'artefact, la même instance de `PC14_a_été_effectué_par` est également liée à la valeur de la [Priorité de l’actant dans la production](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#priorite-de-lactant-dans-la-production) (une instance de `E55_Type`) par la propriété `P14.1_dans_le_rôle_de`. Cette instance de `E55_Type` est qualifiée par une autre instance de `E55_Type` (un nœud doté d’un qualifiant spécifié) portant le libellé « Priorité de l'actant » par la propriété `P2_a_pour_type`. 

Le lieu et la date de production de l'artefact sont centrés sur une instance de `E12_Production` qui pointe vers l'objet produit (une instance de `E22_Objet_élaboré_par_l'humain`) par la propriété `P108_a_produit`.

La valeur du [Lieu de production](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#lieu-de-production) (une instance de `E53_Place`) est liée à cette instance de `E12_Production` par la propriété `P7_a_eu_lieu_dans`. 

Le moment durant lequel la production a eu lieu est indiqué à l'aide du patron conceptuel [Limites temporelles](/collections-model/fr/modele-cible/actuel/limites-temporelles) lié à l'instance de `E12_Production` par la propriété `P4_a_pour_intervalle_temporel` avec des valeurs extraites des nœuds de saisie [Date de début de la production](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-de-la-production), [Qualifiant de la date de début de la production](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-de-la-production), [Date de fin de la production](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-de-la-production) et [Qualifiant de la date de fin de la production](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-de-la-production). 

## Diagramme

<a name="070_PatronConceptuel_Production_p"></a>070_PatronConceptuel_Production_p

<div class="mxgraph" style="max-width:100%;border:1px solid #cccccc;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;target&quot;:&quot;blank&quot;,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom layers lightbox&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;xml&quot;:&quot;&lt;mxfile modified=\&quot;2023-03-15T17:12:55.237Z\&quot; host=\&quot;app.diagrams.net\&quot; agent=\&quot;5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) draw.io/20.3.0 Chrome/104.0.5112.114 Electron/20.1.3 Safari/537.36\&quot; etag=\&quot;QcwFInDpdwEnROOoZOBx\&quot; version=\&quot;20.3.0\&quot;&gt;&lt;diagram id=\&quot;tEP2vpm7clXapd7FymTL\&quot; name=\&quot;Page-1\&quot;&gt;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&lt;/diagram&gt;&lt;/mxfile&gt;&quot;}"></div>

## Exemples

### Exemple 1

L'œuvre *Canadissimo* (`P190_a_pour_contenu_symbolique`, Appellation de l’artefact) a été réalisée par le collectif artistique BGL (`P190_a_pour_contenu_symbolique`, Appellation de l'actant participant à la production) et présentée au Pavillon du Canada de la Biennale de Venise (`P7_a_eu_lieu_dans`, Lieu de production) en 2015 (`P82a_le_début_du_début`, Date de début de la production; `P79_a_son_début_qualifié_par`, Qualifiant de la date de début de la production « Ou avant »; `P82b_la_fin_de_la_fin`, Date de fin de la production; `P80_a_sa_fin_qualifiée_par`, Qualifiant de la date de fin de la production « Ou avant »). Le collectif BGL est composé de Jasmin Bilodeau (`P2_a_pour_type`, Rôle de l’actant dans la production « Créateur »; `P2_a_pour_type`, Priorité de l’actant dans la production « 1 »), Sébastien Giguère (`P2_a_pour_type`, Rôle de l’actant dans la production « Créateur »; `P2_a_pour_type`, Priorité de l’actant dans la production « 1 ») et Nicolas Laverdière (`P2_a_pour_type`, Rôle de l’actant dans la production « Créateur »; `P2_a_pour_type`, Priorité de l’actant dans la production « 1 ») (Wikipedia 2022).

<div id="0001_503_artefact-production" class="example"></div>

### Exemple 2

La photographie [*Self-Portrait*](https://upload.wikimedia.org/wikipedia/commons/3/3a/Yousuf-Karsh.jpg) (`P190_a_pour_contenu_symbolique`, Appellation de l'artefact) de Yousuf Karsh a été prise à Ottawa, CA-ON (`P7_a_eu_lieu_dans`, Lieu de production) en 1938 (`P82a_le_début_du_début`, Date de début de la production; `P82b_la_fin_de_la_fin`, Date de fin de la production) par Karsh (`P2_a_pour_type`, Rôle de l’actant dans la production « Créateur ») qui en était le seul créateur (`P2_a_pour_type`, Priorité de l'actant dans la production « 1 ») (Karsh 1938). 

<div id="0001_500_artefact-production" class="example"></div>

### Exemple 3

La sculpture [*Flightstop*](https://commons.wikimedia.org/wiki/File:Flight_stop.jpg) (`P190_a_pour_contenu_symbolique`, Appellation de l’artefact) de l'artiste Michael Snow (`P2_a_pour_type`, Rôle de l’actant dans la production « Créateur »; `P2_a_pour_type`, Priorité de l’actant dans la production « 1 ») est exposée au Centre Eaton de Toronto depuis 1979 (`P82a_le_début_du_début`, Date de début de la production; `P82b_la_fin_de_la_fin`, Date de fin de la production), date à laquelle elle a été fabriquée et installée. L'image disponible dans Wikimedia Commons a été prise par Simon Law (Law 2011; Snow 1979; Wikipedia 2021). 

<div id="0001_501_artefact-production" class="example"></div>

### Exemple 4

[*« I am half sick of shadows, said The Lady of Shalott » (Alfred, Lord Tennyson, The Lady of Shalott, Part II)*](https://en.wikipedia.org/wiki/File:John_William_Waterhouse_-_I_am_half-sick_of_shadows,_said_the_lady_of_shalott.JPG) (`P190_a_pour_contenu_symbolique`, Appellation de l’artefact) de John William Waterhouse est une œuvre peinte de 1915 (`P82a_le_début_du_début`, Date de début de la production; `P82b_la_fin_de_la_fin`, Date de fin de la production) réalisée uniquement par l'artiste (`P2_a_pour_type`, Rôle de l'actant dans la production « Créateur »; `P2_a_pour_type`, Priorité de l'actant dans la production « 1 ») (Waterhouse 1915; Wikipedia 2018).

<div id="0001_502_artefact-production" class="example"></div>

## Documentation connexe

### Modèles externes {#modeles-externes}

* Linked.art : [Object Names and Identifiers](https://linked.art/model/base/)
* SARI : [Artwork Reference Data Model – Existence](https://docs.swissartresearch.net/et/artwork/#existence)
* SARI : [Artwork Reference Data Model – Actor Relations](https://docs.swissartresearch.net/et/artwork/#actor-relations) 

### Nœuds de saisie {#noeuds-de-saisie}

* [Date de début de la production](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-de-la-production) \| Liste de vérification
* [Date de fin de la production](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-de-la-production) \| Liste de vérification
* [Lieu de production](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#lieu-de-production) \| Liste de vérification
* [Priorité de l'actant dans la production](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#priorite-de-lactant-dans-la-production) \| Liste de vérification
* [Qualifiant de la date de début de la production](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-de-la-production) \| Liste de vérification
* [Qualifiant de la date de fin de la production](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-de-la-production) \| Liste de vérification
* [Rôle de l'actant dans la production](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#role-de-lactant-dans-la-production) \| Liste de vérification

### Entités du CIDOC CRM {#entites-du-cidoc-crm}

* `E12_Production` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E12)]
* `E22_Objet_élaboré_par_l’humain` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E22)]
* `E39_Actant` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E39)]
* `E52_Intervalle_temporel` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E52)]
* `E53_Lieu` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E53)]
* `E55_Type` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E55)]
* `PC14_a_été_effectué_par`
* `P01_a_pour_domaine (est_le_domaine_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P01)]
* `P02_a_pour_portée (est_la_portée_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P02)]
* `P2_a_pour_type (est_le_type_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P2)]
* `P4_a_pour_intervalle_temporel (est_l’intervalle_temporel_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P4)]
* `P7_a_eu_lieu_dans (a_été_témoin_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P7)]
* `P14.1_dans_le_rôle_de` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P14.1)]
* `P79_a_son_début_qualifié_par` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P79)]
* `P80_a_sa_fin_qualifiée_par` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P80)]
* `P82a_le_début_du_début`
* `P82b_la_fin_de_la_fin`
* `P108_a_produit (a_été_produit_par)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P108)]

## Discussion

### Justification

La plupart des bases de données patrimoniales centrent leur enregistrement sur un objet collecté plutôt que sur son ou sa producteur·rice. À des fins de mise en application fonctionnelle, il est donc nécessaire de créer un patron conceptuel qui permette l'identification de l'artefact. Le patron conceptuel Artefact a pour seul but de rendre compte des objets en tant qu'unité centrale de l'enregistrement dans les collections patrimoniales.

En outre, étant donné que la plupart des institutions se concentrent actuellement sur les objets tangibles plutôt que sur les artefacts intangibles comme unités centrales de leurs enregistrements, ce patron conceptuel n'offre que la possibilité de documenter des objets physiques. Ceci explique l'utilisation de la classe `E22_Objet_élaboré_par_l’humain`, qui est destinée à être utilisée pour les produits physiques plutôt que pour les pratiques vivantes.

### Limitations

De plus, dans le cas d'un artefact dont la production peut être décomposée en de multiples sous-évènements (p. ex. une sculpture produite grâce au procédé de cire perdue pourrait être déconstruite en de nombreux évènements), il n'est pas encore possible de lier plusieurs évènements à une instance unique de `E12_Production`. Par ailleurs, sur la base de la quantification de la propriété `P108_a_produit (a_été_produit_par)` dans le CIDOC CRM, il n'est pas permis de lier plusieurs instances de `E12_Production` au même artefact.

### Enjeux connexes sur GitHub

* [Enjeu no 7 « E39 Identification des créateurs »](https://github.com/chin-rcip/collections-model/issues/7) (en anglais)
* [Enjeu no 12 « Comment modéliser la priorité d'un actant dans la production d'un artefact? »](https://github.com/chin-rcip/collections-model/issues/12) (en anglais)
* [Enjeu n° 66 « Proposition de création de PC11_avait_pour_participant et P11.1_dans_le_rôle_de »](https://github.com/chin-rcip/collections-model/issues/66) (en anglais)
* [Enjeu no 69 « Enregistrements pour la facette Objet »](https://github.com/chin-rcip/collections-model/issues/69) (en anglais)
* [Enjeu no 71 « Champs et concepts à modéliser pour la facette Objet »](https://github.com/chin-rcip/collections-model/issues/71) (en anglais)

### Cas limites

#### Exemple 1 {#cas-limites-exemple-1}

Même si ce patron conceptuel permet d'enregistrer une certaine forme de rôle dans la production d'un artefact, la manière d'enregistrer cette information de façon cohérente et significative n'est pas claire. D'ailleurs, la manière de déterminer le rôle et la priorité dépendra possiblement de chaque nœud en relation avec un autre. Par exemple, Jeff Koons pourrait se voir attribuer la Priorité de l'actant participant à la production la plus élevée pour n'importe laquelle de ses œuvres, bien qu'il ne participe généralement pas physiquement à leur réalisation. Les concepteurs·rices, les ingénieurs·es, etc. qu'il emploie auraient une Priorité de l'actant participant à la production inférieure.

De même, il n'est pas clair si la production d'une œuvre débute par son idéation ou sa *création* physique. Qu'en est-il des performances ou des productions immatérielles? L'utilisation d'un qualifiant conceptuel attribué aux dates pourrait éventuellement être évaluée.

#### Exemple 2 {#cas-limites-exemple-2}

Une valeur manquante/inconnue pour le Rôle de l'actant dans la production pour un actant participant à une production collective peut limiter considérablement la portée sémantique de la hiérarchisation de tous les actants impliqués. Si, dans une production réalisée par trois actants, seuls deux d'entre eux sont priorisés, il devient impossible de savoir où se situe l'actant non priorisé par rapport aux autres.

#### Exemple 3 {#cas-limites-exemple-3}

Lorsqu'un évènement se déroule en ligne ou dans un univers virtuel, il peut devenir difficile de déterminer son emplacement physique. Par exemple, un artiste peut produire une œuvre uniquement en ligne à partir d'un ordinateur situé à Winnipeg (CA-MA), tout en utilisant une plateforme de rassemblement accessible sur un serveur Web qui pourrait également être considérée comme le lieu de production.

#### Exemple 4 {#cas-limites-exemple-4}

L'œuvre *Canadissimo* a été réalisée par le collectif artistique BGL et présentée au pavillon du Canada de la Biennale de Venise en 2015. On pourrait dire que la Biennale de Venise est le lieu d'exposition plutôt que le lieu de production, ou les deux étant donné qu'il s'agit d'une installation.

## Bibliographie

Bann, Stephen. « The Return to Curiosity: Shifting Paradigms in Contemporary Museum Display ». *Art and Its Publics: Museum Studies at the Millennium*, édité par Andrew McClellan. New Interventions in Art History 2. Malden, US-MA : Blackwell Pub. Co, 2003 : 117-132.

Conseil international des musées. *Object ID*. ICOM. 19 juillet 2021. [https://icom.museum/en/resources/standards-guidelines/objectid/](https://icom.museum/en/resources/standards-guidelines/objectid/).

Đerić, Tamara Nikolić, Jorjin Neyrinck, et Evelyne Seghers. *Museums and Intangible Cultural Heritage: Towards a Third Space in the Heritage Sector, A Companion to Discover Transformative Heritage Practices for the 21st Century*. Projet sur le patrimoine culturel immatériel et les musées. Anderlecht, BE-BRU : Werkplaats immaterieel erfgoed, 2020. [https://www.ichandmuseums.eu/en/toolbox/book-museums-and-intangible-cultural-heritage/success#details](https://www.ichandmuseums.eu/en/toolbox/book-museums-and-intangible-cultural-heritage/success#details).

Doerr, Martin, et Christian Emil Ore, éds. *Definition of the CIDOC Conceptual Reference Model*. Documentations du CIDOC CRM, 7.0.1. Paris, FR-IDF : Conseil international des musées (ICOM), 2020. [http://www.cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.0.1_%2018-10-2020.pdf](http://www.cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.0.1_%2018-10-2020.pdf).

Karsh, Yousuf. *Self Portret*. Photographie. 1938. Cette image est disponible à Bibliothèque et Archives Canada sous le numéro de référence de reproduction PA-212511 et sous l'identifiant MIKAN 3198631. Cette étiquette n'indique pas le statut du droit d'auteur de l'œuvre jointe. Une étiquette normale de droit d’auteur est encore requise. Voir *Commons: Licensing* pour plus d'informations. Bibliothèque et Archives Canada ne permet pas l'utilisation libre de ses œuvres protégées par le droit d'auteur. Voir *Category: Images from Library and Archives Canada*. [https://commons.wikimedia.org/wiki/File:Yousuf-Karsh.jpg](https://commons.wikimedia.org/wiki/File:Yousuf-Karsh.jpg).

Law, Simon. *Toronto Eaton Centre, Toronto, Canada*. Photographie. Flickr. 2006. [https://commons.wikimedia.org/wiki/File:Flight_stop.jpg](https://commons.wikimedia.org/wiki/File:Flight_stop.jpg).

MacDonald, Sharon, éd. « Collecting Practices ». *A Companion to Museum Studies*. Blackwell Companions in Cultural Studies. Malden, US-MA : John Wiley & Sons, 2011 : 81-97.

Snow, Michael. *Flight Stop*. Sculpture. Flickr. 1979. [https://commons.wikimedia.org/wiki/File:Flight_stop.jpg](https://commons.wikimedia.org/wiki/File:Flight_stop.jpg).

Waterhouse, John William. *« 'I Am Half Sick of Shadows', Said The Lady of Shalott » (Alfred, Lord Tennyson, The Lady of Shalott, Part II)*. Peinture. 1915. [https://en.wikipedia.org/w/index.php?title=File:John_William_Waterhouse_-\_I_am_half-sick_of_shadows,\_said_the_lady_of_shalott.JPG&oldid=838315116](https://en.wikipedia.org/w/index.php?title=File:John_William_Waterhouse_-_I_am_half-sick_of_shadows,_said_the_lady_of_shalott.JPG&oldid=838315116).

Wikipedia. « John William Waterhouse - I Am Half-Sick of Shadows, Said the Lady of Shalott.JPG ». *Wikipedia*. San Francisco, US-CA : Wikipedia, 2018. [https://en.wikipedia.org/w/index.php?title=File:John_William_Waterhouse_-\_I_am_half-sick_of_shadows,\_said_the_lady_of_shalott.JPG&oldid=838315116](https://en.wikipedia.org/w/index.php?title=File:John_William_Waterhouse_-_I_am_half-sick_of_shadows,_said_the_lady_of_shalott.JPG&oldid=838315116).

\_\_\_. « Flight Stop ». *Wikipedia*. San Francisco, US-CA : Wikipedia, 2021. [https://en.wikipedia.org/w/index.php?title=Flight_Stop&oldid=1021679066](https://en.wikipedia.org/w/index.php?title=Flight_Stop&oldid=1021679066).

\_\_\_. « BGL (artists) ». *Wikipedia*. San Francisco, US-CA : Wikipedia, 2022a. [https://en.wikipedia.org/wiki/BGL_(artists)](https://en.wikipedia.org/wiki/BGL_(artists)).

