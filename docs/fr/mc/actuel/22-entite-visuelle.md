---
layout: page
language: fr
title: Entité visuelle
permalink: /fr/modele-cible/actuel/visual-item
other_link: /en/target-model/current/entite-visuelle
sidebar: mc22
date: 2022-06-30
description: La Spécification du modèle cible des actants modélise sémantiquement les actants dans un contexte patrimonial. Les patrons conceptuels les plus pertinents pour la vie des actants sont présentés avec des diagrammes et des exemples qui les illustrent, ainsi qu'un compte rendu et une explication des décisions pertinentes qui ont été prises lors de l'élaboration desdits patrons conceptuels. Il s'agit d'une documentation théorique qui n'a jamais été testée ou mise en application.
---

## Aperçu {#apercu}

Ce patron conceptuel peut être utilisé pour représenter les informations relatives à la représentation visuelle d'un actant sous une forme numérique ou sur un objet physique. Il comprend : 

* L'URL (Uniform Resource Locator ou localisateur uniforme de ressource) de l'image numérique d'un actant;
* La notice bibliographique de l'image;
* L'URL de l'identité visuelle (marque) d'un actant;
* Le type de la marque, par exemple une signature, un logo, un emblème, etc;
* La notice bibliographique de la marque.

Ce patron conceptuel ne doit pas être utilisé pour représenter :

* La description détaillée de la représentation numérique de l'entité visuelle; 
* Le support physique de l'entité visuelle. 

## Introduction et contexte

### Historique théorique {#historique-theorique}

Une entité visuelle est un concept multifacette qui implique une composante perceptible (ce qui est représenté) et la perception de la personne qui l'observe (comment elle est reçue). Par exemple, il est possible d'avoir des images mentales en lisant une histoire ou de détecter un évènement d'actualité dans une caricature. Cette relation entre l'image et l'observateur·rice permet de comprendre les signatures et les logos qui, sans contexte ni description, ne seraient que des formes aléatoires. La signification de ces formes provient nécessairement d'une lecture extrinsèque de l'image.

C'est ce que propose Helmholtz en identifiant la compréhension spontanée comme une des facultés de la représentation (Leroux 1998, 149). Par exemple, une image est instantanément comprise par un·e observateur·rice si il ou elle dispose inconsciemment de toutes les clés pour en percevoir le sens. Si cet·te observateur·rice a déjà vu une photographie d'une personne, il ou elle sera très probablement capable de reconnaître cette personne dans une autre position. Ainsi, une image et sa copie, même si elles peuvent différer par la couleur, la texture ou le format, peuvent être considérées comme partageant un élément visuel qui demeure inchangé (c.-à-d. l'entité visuelle). 

### Énoncé des besoins {#enonce-des-besoins}

Les actants sont souvent représentés dans des éléments visuels (œuvres peintes, photographies, etc.) et il est important d'établir les liens connus entre les images et les actants pour documenter la manière dont les actants ont été représentés (p. ex. de manière figurative ou abstraite), mais aussi pour déterminer ce que les images illustrent. 

De multiples éléments visuels peuvent se rapporter à la vie et à la production d'un actant, tels que des signatures, des logos d'entreprises, etc. Ces types de marques sont considérés comme « représentant » les actants. Souvent, ces éléments visuels sont stockés sous forme numérique dans des systèmes de gestion des collections, distribués et disponibles sur le Web à des URL désignés. En outre, l'utilisation de ces éléments visuels nécessite généralement une citation ou une attribution de source appropriée.

L'enregistrement des images et des métadonnées de qualité qui leur sont associées est encore plus important lors de la mise en application d'une stratégie de libre accès, puisqu'elle vise à garantir l'utilisation légale et pertinente des images. Cette ouverture des données d'images devrait augmenter à mesure que les institutions constatent une meilleure visibilité de leurs collections en ligne grâce à leur présence multiplateforme ainsi que l'augmentation du trafic sur leur site Web (Kelly 2013, 24).

Les entités visuelles, spécialement les images, jouent un rôle majeur dans la visibilité des collections en ligne (Réseau canadien d'information sur le patrimoine 2020, 1). Elles offrent un support visuel permettant l’identification rapide de l'objet décrit dans un enregistrement, ainsi que le sujet qui y est représenté, augmentant ainsi la probabilité que l'enregistrement soit consulté. 

## Description du patron conceptuel

Pour chaque image qui représente un actant, une instance de `E39_Actant` est d'abord liée par une instance de `PC138_représente` à une instance de `E36_Entité_visuelle`, qui est ensuite liée à :

 * Une autre instance de `E36_Entité_visuelle` par la propriété `P165_inclut`;

* La valeur littérale de la [Mention bibliographique de l'image](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#mention-bibliographique-de-limage) par la propriété `dct:source`;
* Une instance de `E24_Chose_matérielle_élaborée_par_l’humain` par la propriété `P65_représente_l’entité_visuelle`;
* Une instance de `D1_Objet_numérique` par la propriété `P165_inclut`.

L'objet numérique est lié par la propriété `P1_est_identifié_par` à une instance de `E42_Identifiant` qui est liée à la valeur littérale de l'[URL de l'image](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#url-de-limage) par la propriété `P190_a_pour_contenu_symbolique`. Cette instance de `E42_Identifiant` est également qualifiée par une instance de `E55_Type` (un nœud doté d’un qualifiant spécifié) portant le libellé « URL » par la propriété `P2_a_pour_type`.

Pour chaque marque qui représente un actant, une instance de `E39_Actant` est d'abord liée par la propriété `P02_a_pour_portée` à une instance de `PC138_représente`, qui est ensuite liée à une instance de `E37_Marque` par la propriété `P01_a_pour_domaine`. L'instance de `PC138_représente` est qualifiée par une instance de `E55_Type` (un nœud doté d’un qualifiant spécifié) portant le libellé « Symbolique » par la propriété `P138.1_mode_de_représentation`.

L'instance de `E37_Marque` est alors liée à :

* La valeur du [Type de marque](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#type-de-marque) (une instance de `E55_Type`) par la propriété `P2_a_pour_type`;
* La valeur littérale de la [Mention bibliographique de la marque](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#mention-bibliographique-de-la-marque) par la propriété `dct:source`;
* Une instance de `E24_Chose_matérielle_élaborée_par_l’humain` par la propriété `P65_représente_l’entité_visuelle`;
* Une instance de `D1_Objet_numérique` par la propriété `P165_inclut`.

L'objet numérique est lié par la propriété `P1_est_identifié_par` à une instance de `E42_Identifiant` qui est liée à la valeur littérale de l’[URL de la marque](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#url-de-la-marque) par la propriété `P190_a_pour_contenu_symbolique`. L’instance de `E42_Identifiant` est également qualifiée par une instance de `E55_Type` (un nœud doté d’un qualifiant spécifié) portant le libellé « URL » par la propriété `P2_a_pour_type`.

## Diagramme

<a name="064_PatronConceptuel_EntiteVisuelleImage_p"></a>064_PatronConceptuel_EntiteVisuelleImage_p

<div class="mxgraph" style="max-width:100%;border:1px solid #cccccc;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;target&quot;:&quot;blank&quot;,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom layers lightbox&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;xml&quot;:&quot;&lt;mxfile modified=\&quot;2023-03-15T17:12:54.528Z\&quot; host=\&quot;app.diagrams.net\&quot; agent=\&quot;5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) draw.io/20.3.0 Chrome/104.0.5112.114 Electron/20.1.3 Safari/537.36\&quot; etag=\&quot;NaiPxWX4wWb9rnDLZSo3\&quot; version=\&quot;20.3.0\&quot;&gt;&lt;diagram id=\&quot;--a-xpLdCh8Zg1l4UYJX\&quot; name=\&quot;Page-1\&quot;&gt;1VlbU9s4FP41Hp7C+BI7+DGEUNjClJZld3nyyLISi8qWkeQm6a9fCcmJYxsIbW6dYZico4ul75zvO7JseaNs/omBIr2lCSKWaydzy7uwXNe11J+dLLTpaHPKcNJy3OOfyDht4y1xgvhaR0EpEbhYd0Ka5wiKNR9gjM7Wu00oWX9qAaao5biHgLS9/+JEpMbr2Paq4QrhaWoefeabhgxUnY2DpyChs5rLG1veiFEq9K9sPkJE4VbhosddvtK6XBhDudhkQPh50Xse34Rn5bfx0/WgvH3i1z0zyw9ASrPhsRdGQyiAnFQvWywqLBgt8wSp6RzLO5+lWKD7AkDVOpOBl75UZMQ0TzAhI0ooexnrTSZxAkF7zdUCEBNoXnOZPXxCNEOCLWQX09ofGDxNOvWNOatFp4I8rQUmMD5gEmK6nHmFmfxhYPsIhGctDO8c7yxiqGDWyLOGIZe7RS00USITzZiUiZROaQ7IeOU9X+FtS2vV54bSwqD8hIRYGNaAUtD1GMjnssV/avypX5mP9baLuZlcWwtjvRomTksG0RtgBIaigE2ReD/vFAZvBp0hAgT+sU7GrYcw6GBBEI1zgYWOYPQD81JO1I7ib3EiSaDX3wEnnPDQpOjiROBHOIekbAvLfqng7okLVQl7lwzBUZEh7AhdhLiIZCGWjJhgQwkJyUED6dSjWBO4w8XR8Y8qkNW6a5G8cKIvscQ3ystMh5Hh5/JYVc1eVzXv8KW+fVy6k6rWqPSR5QZELuU8lgQJpuoXOUGbFJP96uBgXzro/pE6WC27fipw+9EopRxF8nRf8UdHshnxSDcTEFOTG0grZqsjOUnLDOB8qyRETgxC+FbYNueh72/AQ2+vPPTaPHQjEBUyFSOxKA7NrH0Ry9+0MB0Zs/odR4zQrgIoX+UFysuIL7KYks76dMBw2kcQzsFxhdNvC2Xfja7NcXHrNwlo4sXbuElw+kd3vuh4EfX96O8XRWsWDmvkWkOZbvbDtxv5X5nn59tFGsR+4O8AabcS8B0g/cARU2dcKLPOluUXET10CWCFn4YtQarbCc7UPaDpImdc9mrjPucSzSEXDOdTvTqC8+/6IakQ6l5yqBbnXsIU5z0GcXE6xSIt41NMlZfKAwMUmOa8l+mr0suJnP2SFwhKvkCg2noJ4j2YogzLbhxlkkVKCbnsB6AoX0blFJUJlz17HGCO5fq9khFlE7Mf992MG9QCZ1L0V7NnB4nSDwY7SxRp1nKlm6WjL1fPs8UDPIN/XZWPV97t14J23JkmaoKhEfiD1qqPvROjORbLV2n5uzZKWqtBytjJ3WAnvu62q5sZekexKkVVrgVOQ5TcRg7pDZlRjTRaLuO3JOhWVUgqT/52jGOC6VR9PtEHnk5hqol/h1QdtTBlequ9xkZfE6vXE+NotCoI93fpuolW3X9OQvh46z595344evwn/8rtDq06nnvYD70lVVJlH0qqOuHdk1Q17/c9fzOpak3kNzWvmYt6x7+geZulY8eVyh/1ocVtct7eKedXH4d1AFZf173x/w==&lt;/diagram&gt;&lt;/mxfile&gt;&quot;}"></div>


<a name="066_PatronConceptuel_EntiteVisuelleMarque_p"></a>066_PatronConceptuel_EntiteVisuelleMarque_p

<div class="mxgraph" style="max-width:100%;border:1px solid #cccccc;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;target&quot;:&quot;blank&quot;,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom layers lightbox&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;xml&quot;:&quot;&lt;mxfile host=\&quot;app.diagrams.net\&quot; modified=\&quot;2023-03-15T17:12:54.764Z\&quot; agent=\&quot;5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) draw.io/20.3.0 Chrome/104.0.5112.114 Electron/20.1.3 Safari/537.36\&quot; etag=\&quot;2BA21Tpe7u-mV8Q86_ql\&quot; version=\&quot;20.3.0\&quot;&gt;&lt;diagram id=\&quot;2y-6vv1WeGx6k1ehrlox\&quot; name=\&quot;Page-1\&quot;&gt;5Vpbd5s4EP41nH1yDiCD7UfbSdo9TbbZxt1NnjgCBKgrECtEbPfXV7KEjQ3OZeMLOfvSotHF0jcz38xIMcA0XXxiME9uaYiIYZvhwgCXhm1b1sAS/0nJUktUM2Y4bAju8U+khaaWljhExdZATinhON8WBjTLUMC3ZJAxOt8eFlGy/as5jFFDcB9A0pT+jUOeVKdyR5uOzwjHif7poT1QHSmsBuuTFAkM6bwmAlcGmDJKufpKF1NEJHQVLmre9Z7e9cYYyvhrJnx7eoDgy8/4azR/tCZlPPtyk/f0Kk+QlPrAV2DkjQMOxaJq23xZYcFomYVILmcZYDJPMEf3OQxk71zoXsgSnhLdHWFCppRQtpoLosgPA9jcc7UBxDha1ET6DJ8QTRFnSzFE94IKT21OQ92c17RTDUlqinG1DGqDiNcrbzATHxq2N0AIGhDembYHvZyWTPzDuDEFxniEGnCiUFiabophCY1pBsnVRjrZAG6K1mbMDaW5hvkH4nyp3QaWnG4rQcDMlg9y/oVTNR/rfZcLvbhqLXVrr54KcagAPYOGrX0Ushjxlw1PYvCs1hkikOOnbW88uA6dFh1alQ5DmkKcnUV/x9dDv1N6GDT1YIHhheWlIqx4hu0ScZaJz8RXLL+EkKGcKQ8rBEhijzQ7r6fV/azmdmfzNLdTGrabGp4KFe+osels74k9QTA0o+gIsWcd288WfPot8Xvg3UL2b3lYDKMwDED/CBgC99wYuk0MHcebLXPUJBxjahtj4bTm/TL1KcErmE0pnUwOizf0Hdc5AN6u2TWbtZpJ553lOh7OAlI2s87Tpkn2ifKk4YeMz1ZLsmt5qOCeqNIyjiOsONwTkJxVkdapovBr9WjZnVLksKHHS8v76gt0vaxMlRIZ7mwQsfvbpOZYZyc1s+kZgtN20hqP/CbdRJeE3hMuSrH2uUvDwYk4b/QhOW/UTA/svjdNaIG8FPLKV5Qed/MFT3UT6FNtB0hyo7CDpJRV5UHdC1k+HAXPqej1HtY3X+Fh4KQe1lKkr+9Z+Cpb+z9csFSB5OWI0y03stpq+5FZKTCggh6z0itqeXV31Gl2QJ3dquOrfddpsW97v+s08ODXxygC/iGuj9eBujuZQ0sN/3L9+f3bTccLz12kwRAcDenvBWIyew2E1Zki2CKipq4BrPBTsIVoNcyQrzTqpkQNE6uuRzaxXxQC0XHBGc5itUOCs3/UDyWcywepsdygfR0kOOuxAOcXMeZJ6V9gKqVUpAiBvKAseql6JruOxOrXRY4C4TPB6vKyF6KiFyQoxWJYgVLhSZINCzEOBrxczcooKsNCjOwVEBdY7B+UjMg2gb20dvnzvOG5Nf1pS/2vRnQEe3HB4Gj2Ipo1k9njrH+GPx4RmHHvFt3ln53pEMxa3stCucBY8/xZQ9bbSl60wHxdKYvv2izR2kySjfeHuX5LlGvD9+BVsp56R7GMSOvsduBsc9Nox4bUgfSsHTNab+NdTHQrA6V8qzB97BNMY/l6ru8T9/FTLQ60MFan+SlVx+3tHPY5ztprH52hLGfXjI54l/0aynIerv9K0ylE/I9ZYdNokI/bnvg/btlUkZZ5LtJqRfhEpGXvBMi+fXLSUkmp4qe3pE6bhLZjtCQdQAraCGi/rg9DQMdKvC1n58VndLzEu4WVhGjzR03K9jZ/GAaufgE=&lt;/diagram&gt;&lt;/mxfile&gt;&quot;}"></div>

## Exemples

### Exemple 1

Un autoportrait photographique de Yousuf Karsh est disponible sur Wikimedia Commons à l'adresse « https://upload.wikimedia.org/wikipedia/commons/3/3a/Yousuf-Karsh.jpg » (`P190_a_pour_contenu_symbolique`, URL de l'image) avec la citation de source « Cette image est disponible par l'entremise de Bibliothèque et Archives Canada sous le numéro de référence de la reproduction PA-212511 et sous le numéro MIKAN 3198631 » (`dct:source`, Mention bibliographique de l’image) (Wikipedia 2021).

<div id="0001_100_visual-item-image" class="example"></div>

### Exemple 2

Wikimedia Commons détient une représentation numérique de la signature (`P2_a_pour_type`, Type de marque) de Yousuf Karsh disponible à l'URL suivante : « https://upload.wikimedia.org/wikipedia/commons/4/46/Signature_of_Yousuf_Karsh.png » (`P190_a_pour_contenu_symbolique`, URL de la marque), avec la citation de source « Cette image a été trouvée sur Wikimedia Commons (Signature de Yousuf Karsh,  Domaine public), et originellement disponible sur https://karsh.org/wordpress/wp-content/themes/bigflannel-karsh/img/karsh-signature.jpg » (`dct:source`, Mention bibliographique de la marque) (Wikipedia 2021).

<div id="0001_100_visual-item-mark" class="example"></div>

## Documentation connexe

### Modèles externes {#modeles-externes}

* Linked.art : [Actors: People and Organizations – Descriptive Information](https://linked.art/model/actor/#descriptive-information)
* Linked.art : [Actors: People and Organizations – Digital Integration](https://linked.art/model/actor/#digital-integration)
* SARI : [Person Reference Data Model – Documention](https://docs.swissartresearch.net/et/persons/#documentation) 

### Nœuds de saisie {#noeuds-de-saisie}

* [Mention bibliographique de la marque](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#mention-bibliographique-de-la-marque) \| Liste de vérification
* [Mention bibliographique de l'image](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#mention-bibliographique-de-limage) \| Liste de vérification
* [Type de marque](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#type-de-marque) \| Liste de vérification
* [URL de la marque](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#URL-de-la-marque) \| Liste de vérification
* [URL de l'image](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#URL-de-limage) \| Liste de vérification

### Entités du CIDOC CRM {#entites-du-cidoc-crm}

* `dct:source`
* `D1_Objet_numérique`
* `E24_Chose_matérielle_élaborée_par_l’humain` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E24)]
* `E36_Entité_visuelle` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E36)]
* `E37_Marque` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E37)]
* `E39_Actant` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E39)]
* `E42_Identifiant` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E42)]
* `E55_Type` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E55)]
* `PC138_représente`
* `P01_a_pour_domaine (est_le_domaine_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P01)]
* `P02_a_pour_portée (est_la_portée_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P02)]
* `P1_est_identifié_par (identifie)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P1)]
* `P2_a_pour_type (est_le_type_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P2)]
* `P65_représente_l’entité_visuelle (est_représenté_par)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P65)]
* `P138_représente (est_représenté_par)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P138)]
* P138.1_mode_de_représentation` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P138.1)]
* `P165_inclut (est_inclus_dans)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P165)]
* `P190_a_pour_contenu_symbolique` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P190)]

## Discussion

### Justification

Le CIDOC CRM distingue les représentations visuelles (`E36_Entité_visuelle`) des objets physiques qui portent ces représentations (`E24_Chose_matérielle_élaborée_par_l’humain`) et de leurs représentations numériques (`D1_Objet_numérique`).

Alors que le support physique d'une représentation visuelle (`E24_Chose_matérielle_élaborée_par_l’humain`) peut être directement lié à une instance de `E39_Actant` par la propriété `P62_illustre`, sa forme *numérique* (`D1_Objet_numérique`) ne peut pas être liée à cette instance. Étant donné que les images numériques sont devenues un actif commun dans le secteur du patrimoine, un patron conceptuel plus précis tenant compte du fait qu'il peut y avoir plusieurs supports d'une seule `E36_Entité_visuelle` est nécessaire. 

Les entités visuelles sont, comme le précise la note d'application de la classe du CIDOC CRM, « les aspects intellectuels ou conceptuels des marques et des images reconnaissables » (Le Bœuf et al. 2015, sect. E36 Visual Item; notre traduction). Elles sont indépendantes de l'orientation, de la taille, de la couleur ou de toute autre caractéristique qui n'affecte pas leur identification. Par exemple, une copie en noir et blanc de la *Mona Lisa* serait toujours considérée comme portant l'entité visuelle de la *Mona Lisa*. Un cas plus complexe, cependant, concerne l'altération d'une image qui demeure reconnaissable, mais qui pourrait être considérée comme une nouvelle entité (p. ex. le *Marilyn Diptych* d'Andy Warhol, qui utilise une photographie de Marilyn Monroe et la « recolore », peut être considéré comme une nouvelle œuvre d'art, et donc comme une nouvelle entité visuelle). Dans certains cas, une entité visuelle peut être sous-divisée en plusieurs entités, spécialement si une image contient d'autres entités visuelles, comme c'est le cas pour [*Modern Rome* de Giovanni Paolo Panini](https://commons.wikimedia.org/wiki/File:Panini,_Modern_Rome.jpg). Dans tous les cas, il est possible de lier plusieurs instances de `E36_Entité_visuelle` avec la propriété `P165_inclut`. Ce patron conceptuel permet l'enregistrement de l'incorporation d'une entité visuelle dans une autre (p. ex. l'œuvre peinte *Marilyn Diptych* de Warhol incorpore une photographie originale de Marilyn Monroe; *Modern Rome* de Panini incorpore des représentations de plusieurs œuvres d'art célèbres, telles que *Moses* de Michel-Ange et *Constantin*, *David* et *Apollo and Daphne* de Gian Lorenzo Bernini).

De plus, il est nécessaire de distinguer le rendu numérique d'une entité visuelle sous la forme d'une image de son URL, qui doit être mentionnée indépendamment de l'URI de l'objet numérique. L'URL de l'image numérique se voit ainsi attribuer un identifiant (`E42_Identifiant`).

Dans le cas des marques, la classe `E37_Marque` est utilisée pour modéliser la marque d'un actant, car sa portée est sémantiquement plus précise que la classe `E36_Entité_visuelle`. Elle est connectée à une instance de `E39_Actant` suivant le même patron conceptuel que celui de `E36_Entité_visuelle`. Cependant, cela nécessite l'utilisation de la propriété-classe `PC138_représente` pour spécifier (avec la propriété `P138.1_mode_de_représentation`) que la marque représente l'actant de manière symbolique.

### Limitations

Ce patron conceptuel comporte trois limites qui font toujours l’objet de recherches :

* Sa portée est uniquement limitée à la modélisation de la présence d'un actant dans une entité visuelle, et ne comprend pas la description de l'entité visuelle elle-même;
* Il ne contient pas d'informations sur les droits ou les licences; 
* La citation des entités visuelles est modélisée comme du texte brut non structuré, même si, de préférence, elle devrait être plus structurée pour être plus sémantiquement expressive.

Une autre limite est l'absence d'une propriété permettant de lier les instances de l'objet physique avec l'URL de son image numérique. Actuellement, le seul moyen de le faire est d’utiliser la classe `E36_Entité_visuelle`. Si deux objets physiques ou plus affichent la même image et que l'image numérique de chacun d'eux a sa propre URL, il devient difficile de déterminer quelle URL peut être utilisée pour rendre l'image de quel objet (voir l'[Enjeu no 65](https://github.com/chin-rcip/collections-model/issues/65)). La seule façon de contourner cette limitation est d'associer une instance de `E24_Chose_matérielle_élaborée_par_l’humain` et une instance de `D1_Objet_numérique` à une instance de `E36_Entité_visuelle`. Cette solution temporaire n'est pas optimale, car elle conduit à la création de plusieurs instances de `E36_Entité_visuelle` qui devraient normalement être sous le même URI si sa note d'application était respectée.

### Enjeux connexes sur GitHub

* [Enjeu no 17 « Comment modéliser les images et comment intégrer les URL des images? »](https://github.com/chin-rcip/chin-rcip/issues/17) (en anglais)
* [Enjeu no 65 « Description de l'entité visuelle »](https://github.com/chin-rcip/chin-rcip/issues/65) (en anglais)

### Cas limites

#### Exemple 1 {#cas-limites-exemple-1}

Le pape Jean XXIII a été photographié par Yousuf Karsh en 1959 ([Karsh n.d.](https://karsh.org/photographs/pope-john-xxiii/)). Pendant la séance, une autre photo a été prise, qui montre Yousuf Karsh discutant avec le pape ([Karsh n.d.](https://karsh.org/yousuf-karsh-and-pope-john-xxiii-1959/)). Comme le pape se trouve sur deux photos prises lors du même évènement, c'est à la personne responsable du catalogage de décider si l'entité visuelle de la deuxième photo contient l'entité visuelle de la première. La note d'application de la classe `E36_Entité_visuelle`, qui utilise des concepts comme « reconnaissable » ou « identifiable de manière unique » (Bekiari et al. 2021, sect. E36 Visual Item), fonctionne relativement bien pour les objets immuables, mais son application devient plus complexe pour les actants. Selon la personne responsable du catalogage, plusieurs critères peuvent être pris en compte ou non, tels que la date et le lieu de la prise de vue, la position de l'actant, l'action en cours, les vêtements portés, etc. Si l'entité visuelle de la première photographie est définie comme « Pape Jean XXIII », cette même entité visuelle se retrouve également dans la deuxième photographie. Toutefois, si l'entité visuelle de la première photographie est définie comme « Le pape Jean XXIII photographié avec la main en l'air », cette même entité visuelle ne fait pas partie de la deuxième photographie.

#### Exemple 2 {#cas-limites-exemple-2}

*Mawu-che-hitoowin: A Gathering of People for any Purpose* est une installation réalisée en 1992 par Rebecca Belmore. Il est discutable si la mention des droits d'une telle image (« © Rebecca Belmore 1992 ») peut être considérée comme bibliographique.

## Bibliographie

Bekiari, Chryssoula, George Bruseker, Martin Doerr, Christian-Emil Ore, Stephen Stead, et Athanasios Velios, éds. *Definition of the CIDOC Conceptual Reference Model*. Documentations du CIDOC CRM, 7.1. Paris, FR-IDF : CIDOC CRM Special Interest Group, 2021. [http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf](http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf).

Doerr, Martin, Stephen Stead, et Maria Theodoridou. *Definition of the CRMdig: An Extension of CIDOC-CRM to Support Provenance Metadata*. CRMdig, 3.2.1. Heraklion, GR : CIDOC CRM, 2016. [http://www.cidoc-crm.org/crmdig/ModelVersion/version-3.2.1](http://www.cidoc-crm.org/crmdig/ModelVersion/version-3.2.1).

​​DCMI Usage Board. « DCMI Metadata Terms ». *Dublin Core Metadata Initiative*. 20 janvier 2020. [http://dublincore.org/specifications/dublin-core/dcmi-terms](http://dublincore.org/specifications/dublin-core/dcmi-terms).

FORTH-ICS. *CRMpc 1.0*. 2014. [http://www.cidoc-crm.org/sites/default/files/CRMpc_v1.0.rdfs](http://www.cidoc-crm.org/sites/default/files/CRMpc_v1.0.rdfs).

Karsh, Yousuf. « Pope John XXIII ». *Yousuf Karsh* (blog). n.d. [https://karsh.org/photographs/pope-john-xxiii/](https://karsh.org/photographs/pope-john-xxiii/).

Karsh, Yousuf. « With Pope John XXIII, 1959 ». *Yousuf Karsh* (blog). n.d. [https://karsh.org/yousuf-karsh-and-pope-john-xxiii-1959/](https://karsh.org/yousuf-karsh-and-pope-john-xxiii-1959/).

Kelly, Kristin. *Images of Works of Art in Museum Collections: The Experience of Open Access, A Study of 11 Museums*. CLIR Publication 157. Washington, USA-DC : Council on Library and Information Resources (CLIR), 2013. [https://www.clir.org/wp-content/uploads/sites/6/pub157.pdf](https://www.clir.org/wp-content/uploads/sites/6/pub157.pdf).

Le Bœuf, Patrick, Martin Doerr, Christian Emil Ore, et Stephen Stead, éds. « E36 Visual Item ». *Definition of the CIDOC Conceptual Reference Model*. Documentations du CIDOC CRM, 6.2.1. Paris, FR-IDF : Conseil international des musées (ICOM), 2015. [http://www.cidoc-crm.org/sites/default/files/cidoc_crm_version_6.2.1.pdf](http://www.cidoc-crm.org/sites/default/files/cidoc_crm_version_6.2.1.pdf).

Leroux, Jean. « Les 'Théories de L'image' De Helmholtz et de Hertz et Les Motifs de Carnap Dans L'aufbau ». *The Paideia Archive: Twentieth World Congress of Philosophy* 37, (1998) : 148-154. [https://doi.org/10.5840/wcp20-paideia199837665](https://doi.org/10.5840/wcp20-paideia199837665).

Réseau canadien d'information sur le patrimoine. Critique de *Numérisez vos collections : Guide à l'intention des gestionnaires chargés de la planification et de la mise en œuvre de projets de numérisation*, par Ern Bieman. Gouvernement du Canada. 2020. [https://publications.gc.ca/collections/collection_2020/pch/CH57-4-10-2020-fra.pdf](https://publications.gc.ca/collections/collection_2020/pch/CH57-4-10-2020-fra.pdf).

Wikipedia. « Yousuf Karsh. » *Wikipedia*. San Francisco, US-CA : Wikipedia, 2021. [https://fr.wikipedia.org/wiki/Yousuf_Karsh](https://fr.wikipedia.org/wiki/Yousuf_Karsh).

