---
layout: page
language: fr
title: Artefact
permalink: /fr/modele-cible/actuel/artefact
other_link: /en/target-model/current/artefact
sidebar: mc22
date: 2022-06-30
description: La Spécification du modèle cible des actants modélise sémantiquement les actants dans un contexte patrimonial. Les patrons conceptuels les plus pertinents pour la vie des actants sont présentés avec des diagrammes et des exemples qui les illustrent, ainsi qu'un compte rendu et une explication des décisions pertinentes qui ont été prises lors de l'élaboration desdits patrons conceptuels. Il s'agit d'une documentation théorique qui n'a jamais été testée ou mise en application.
---

## Aperçu {#apercu}

Ce patron conceptuel peut être utilisé pour identifier de façon minimale un artefact tangible. Il comprend : 

* Les principaux numéros d'identification d'un artefact (p. ex. le numéro d'acquisition, le numéro spécifique de la base de données, etc.);
* L'appellation d'un artefact.

Même si ce patron conceptuel peut être lié au patron conceptuel [Production d'artefact](/collections-model/fr/modele-cible/actuel/production-dartefact) afin de prendre en compte d'autres informations impliquant des actants, il ne comprend pas : 

* Les artefacts immatériels;
* La ou les personnes ayant produit un artefact (le patron conceptuel [Production d'artefact](/collections-model/fr/modele-cible/actuel/production-dartefact) doit plutôt être utilisé); 
* Les dates et lieux de création ou de production (le patron conceptuel [Production d'artefact](/collections-model/fr/modele-cible/actuel/production-dartefact) doit plutôt être utilisé). 

Les informations relatives aux artefacts eux-mêmes, ainsi qu'à leur collecte, leur recherche, leur manipulation et leur conservation, ne sont actuellement pas prises en compte dans ce patron conceptuel. Les informations minimales nécessaires pour identifier plutôt que pour décrire les artefacts ont été priorisées. De même, seuls les artefacts tangibles sont modélisés dans ce patron conceptuel. 

En outre, il est important de souligner que le patron conceptuel [Entité visuelle](/collections-model/fr/modele-cible/actuel/entite-visuelle) ne peut pas être utilisé pour référer aux artefacts ou à leurs reproductions, car celui-ci prend exclusivement en compte les représentations des actants pour le moment. 

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

Comme la seule fonction du patron conceptuel Artefact est de prendre en compte les objets en tant qu'unité centrale d'enregistrement dans les collections patrimoniales, tous ces éléments ne sont pas abordés dans le modèle; seuls les titres et les identifiants sont pris en considération. Le rôle de la personne ayant produit l'artefact et la date ou la période de production sont traités dans le patron conceptuel [Production d'artefact](/collections-model/fr/modele-cible/actuel/production-dartefact).

## Description du patron conceptuel

Ce patron conceptuel comporte deux ensembles principaux : les identifiants de l'artefact et son titre. Les deux se rapportent directement à une instance de `E22_Objet_élaboré_par_l’humain`, qui est l'unité centrale de ce patron conceptuel et encapsule l'artefact. 

Les informations relatives aux identifiants sont concentrées autour d'une instance de `E42_Identifiant` qui est liée à l'instance de `E22_Objet_élaboré_par_l’humain` par la propriété `P1_est_identifié_par`. Cette instance de `E42_Identifiant` est liée à la valeur littérale de l'[Identifiant de l'artefact](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#identifiant-de-lartefact) par la propriété `P190_a_pour_contenu_symbolique` ainsi qu'à la valeur du [Type d'identifiant de l'artefact](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#type-didentifiant-de-lartefact) par la propriété `P2_a_pour_type`.

Les informations relatives à l'appellation de l'artefact sont rendues avec la même logique que le patron conceptuel [Identifiants et appellations de l'actant](/collections-model/fr/modele-cible/actuel/identifiants-et-appellations-de-lactant). Une instance de `E41_Appellation` et de `E33_Objet_linguistique` est liée à :

* La valeur littérale de l'[Appellation de l'artefact](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-de-lartefact) par la propriété `P190_a_pour_contenu_symbolique`;
* La valeur de la [Langue de l’appellation de l’artefact](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#langue-de-lappellation-de-lartefact) (une instance de `E56_Langue`) par la propriété `P72_a_pour_langue`;
* La valeur du [Type d’appellation de l’artefact](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#type-dappellation-de-lartefact) (une instance de `E55_Type`) par la propriété `P2_a_pour_type`, qui est qualifiée par une instance de `E55_Type` (un nœud doté d’un qualifiant spécifié) portant le libellé « Type d'appellation » par la propriété `P2_a_pour_type`;

 * La valeur de la [Primauté de l'appellation de l'artefact](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#primaute-de-lappellation-de-lartefact) (une instance de `E55_Type`) par la propriété `P2_a_pour_type`, qui est qualifiée par une instance de `E55_Type` (un nœud doté d’un qualifiant spécifié) portant le libellé « Primauté » par la propriété `P2_a_pour_type`.

L'instance de `E41_Appellation` et de `E33_Objet_linguistique` est aussi liée à l'instance de `E22_Objet_élaboré_par_l’humain` par la propriété `P1_est_identifié_par`. 

## Diagramme

<a name="072_PatronConceptuel_Artefact_p"></a>072_PatronConceptuel_Artefact_p

<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=072_PatronConceptuel_Artefact_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1PneNUPJ5mSgs4EMn392WEXTcsgk5CUIy%26export%3Ddownload"></iframe>

## Exemples

### Exemple 1

[*Self-Portrait*](https://upload.wikimedia.org/wikipedia/commons/3/3a/Yousuf-Karsh.jpg) (`P190_a_pour_contenu_symbolique`, Appellation de l’artefact) de Yousuf Karsh est intitulé (`P2_a_pour_type`, Type d’appellation de l’artefact « Titre ») en anglais (`P72_a_pour_langue`, Langue de l’appellation de l’artefact) et il s'agit du titre principal utilisé pour faire référence à l'artefact (`P2_a_pour_type`, Primauté de l'appellation de l'artefact « Préférée »). Il est aussi parfois intitulé *Self Portret* (`P190_a_pour_contenu_symbolique`, Appellation de l’artefact; `P2_a_pour_type`, Type d’appellation de l’artefact « Titre »), mais cette appellation n'est pas préférée (`P2_a_pour_type`, Primauté de l'appellation de l'artefact « Non préférée »). Le numéro d'identification de la reproduction de Bibliothèque et Archives Canada (`P2_a_pour_type`, Type d'identifiant de l'artefact « Numéro d'identification ») est PA-212511 (`P190_a_pour_contenu_symbolique`, Identifiant de l'artefact « PA-212511 ») (Karsh 1938). 

<div id="0001_500_artefact" class="example"></div>

### Exemple 2

[*Flightstop*](https://commons.wikimedia.org/wiki/File:Flight_stop.jpg) (`P190_a_pour_contenu_symbolique`, Appellation de l'artefact; `P72_a_pour_langue`, Langue de l’appellation de l'artefact  « Anglais »; `P2_a_pour_type`, Type d'appellation de l'artefact « Titre »; `P2_a_pour_type`, Primauté de l'appellation de l'artefact « Préférée ») est une sculpture de l'artiste Michael Snow, parfois intitulée *Flight Stop* (`P190_a_pour_contenu_symbolique`, Appellation de l’artefact; `P72_a_pour_langue`, Langue de l’appellation de l’artefact « Anglais »; `P2_a_pour_type`, Type d’appellation de l’artefact « Titre »; `P2_a_pour_type`, Primauté de l'appellation de l'artefact « Non préférée ») (Law 2011; Snow 1979; Wikipedia 2021).

<div id="0001_501_artefact" class="example"></div>

### Exemple 3

[*« I am half sick of shadows, said The Lady of Shalott » (Alfred, Lord Tennyson, The Lady of Shalott, Partie II)*](https://en.wikipedia.org/wiki/File:John_William_Waterhouse_-_I_am_half-sick_of_shadows,_said_the_lady_of_shalott.JPG) (`P190_a_pour_contenu_symbolique`, Appellation de l'artefact) est une œuvre peinte de John William Waterhouse de 1915 conservée par le Musée des beaux-arts de l'Ontario. Elle est identifiée par le numéro d'objet 71/18 (`P190_a_pour_contenu_symbolique`, Identifiant de l'artefact), qui a été attribué par la personne responsable du catalogage (`P2_a_pour_type`, Type d'identifiant de l’artefact « AGO_ID ») (Waterhouse 1915; Wikipedia 2018). 

<div id="0001_502_artefact" class="example"></div>

## Documentation connexe

### Modèles externes {#modeles-externes}

* Linked.art : [Object Names and Identifiers](https://linked.art/model/base/)
* SARI : [Artwork Reference Data Model – Names and Classifications](https://docs.swissartresearch.net/et/artwork/#names-and-classifications)

### Nœuds de saisie {#noeuds-de-saisie}

* [Appellation de l'artefact](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-de-lartefact) \| Liste de vérification
* [Identifiant de l'artefact](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#identifiant-de-lartefact) \| Liste de vérification
* [Langue de l'appellation de l’artefact](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#langue-de-lappellation-de-lartefact) \| Liste de vérification
* [Primauté de l'appellation de l’artefact](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#primaute-de-lappellation-de-lartefact) \| Liste de vérification
* [Type d'appellation de l'artefact](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#type-dappellation-de-lartefact) \| Liste de vérification
* [Type d'identifiant de l'artefact](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#type-didentifiant-de-lartefact) \| Liste de vérification

### Entités du CIDOC CRM {#entites-du-cidoc-crm}

* `E22_Objet_élaboré_par_l’humain` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E22)]
* `E33_Objet_linguistique` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E33)]
* `E41_Appellation` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E41)]
* `E42_Identifiant` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E42)]
* `E55_Type` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E55)]
* `E56_Langue` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E56)]
* `P1_est_identifié_par (identifie)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P1)]
* `P2_a_pour_type (est_le_type_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P2)]
* `P72_a_pour_langue (est_la_langue_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P72)]
* `P190_a_pour_contenu_symbolique` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P190)]

## Discussion

### Justification

La plupart des bases de données patrimoniales centrent leur enregistrement sur un objet collecté plutôt que sur son ou sa producteur·rice. À des fins de mise en application fonctionnelle, il est donc nécessaire de créer un patron conceptuel qui permette l'identification de l'artefact. Le patron conceptuel Artefact a pour seul but de rendre compte des objets en tant qu'unité centrale de l'enregistrement dans les collections patrimoniales.

En outre, étant donné que la plupart des institutions se concentrent actuellement sur les objets tangibles plutôt que sur les artefacts intangibles comme unités centrales de leurs enregistrements, ce patron conceptuel n'offre que la possibilité de documenter des objets physiques. Ceci explique l'utilisation de la classe `E22_Objet_élaboré_par_l’humain`, qui est destinée à être utilisée pour les produits physiques plutôt que pour les pratiques vivantes. 

### Limitations

Ceci est uniquement destiné à identifier au minimum les artefacts sans les décrire;  tout ce qui a trait à l'objet lui-même est donc manquant (voir l'[Enjeu no 71](https://github.com/chin-rcip/collections-model/issues/71)). 

### Enjeux connexes sur GitHub

* [Enjeu no 69 « Enregistrements pour la facette Objet »](https://github.com/chin-rcip/collections-model/issues/69) (en anglais)
* [Enjeu no 71 « Champs et concepts à modéliser pour la facette Objet »](https://github.com/chin-rcip/collections-model/issues/71) (en anglais)

### Cas limites

#### Exemple 1 {#cas-limites-exemple-1}

Le *Portrait de Madeleine* de Marie-Guillemine Benoist a auparavant été intitulé en utilisant une description raciale. De récentes études ont établi que le nom de la personne assise représentée était « Madeleine », mais son nom de famille demeure inconnu. Une annotation ou une note curatoriale pourrait être placée sur les Appellations de l'artefact  :

* « Portrait de Madeleine » est l'appellation préférée (Primauté de l'appellation de l'artefact) et « Ancien titre affichant un langage racial insensible » est la note curatoriale;
* « Portrait d'une femme noire » est l'appellation non préférée (Primauté de l'appellation de l'artefact) et « Maintenant intitulé Portrait de Madeleine » est la note curatoriale;
* « Portrait d'une femme noire » est l'appellation non préférée (Primauté de l'appellation de l'artefact) et « Ancien titre affichant un langage racial insensible » est l'annotation.

Une note curatoriale pourrait également être utilisée pour l'actant « Madeleine » qui est représenté (« Personne assise dans le *Portrait de Madeleine*, ancien titre comportant un langage racial insensible avec la personne assise identifiée comme étant "Madeleine" par Viktoria Schmidt-Linsenhoff »). Il existe un certain nombre d'œuvres dans les collections canadiennes qui ont des titres offensants ou autrement insensibles, imprégnés de terminologie raciste et/ou colonialiste (Schmidt-Linsenhoff 2013; Waller 2018). 

#### Exemple 2 {#cas-limites-exemple-2}

Les institutions catégorisent les objets différemment. Par exemple, d'une part, la Tom Thomson Memorial Art Gallery enregistre l'œuvre *Triptych* de Don Phillips comme trois objets dans [Artefacts Canada](https://app.pch.gc.ca/application/artefacts_hum/indice_index.app?lang=fr) :

* Appellation de l'artefact : *Triptych (1978) (left panel)*
  * Identifiant de l'artefact : 994.039.1
  * Type d’identifiant de l'artefact : TTMAG_ID
* Appellation de l'artefact : *[Triptych (1978) (centre panel)*
  * Identifiant de l'artefact : 994.039.2
  * Type d’identifiant de l'artefact : TTMAG_ID
* Appellation de l'artefact : *Triptych (1978) (right panel)*
  * Identifiant de l'artefact : 994.039.3
  * Type d’identifiant de l'artefact : TTMAG_ID

D'autre part, la Vancouver Art Gallery enregistre l'œuvre *Mariner’s Triptych: For Night Navigation* de B.C. Binning en tant qu'œuvre unique dans Artefacts Canada :

* Appellation de l'artefact : *Mariner’s Triptych: For Night Navigation*
  * Identifiant de l'artefact : 65.11
  * Type d’identifiant de l'artefact : VAG_ID

Ces cas montrent à quel point l'enregistrement d'artefacts constitués de plusieurs parties peut être problématique, à la fois en termes d'identifiants, mais aussi dans le cas d'autres champs tels que les appellations. Pour l'instant, l'identifiant devient le porteur de la fédération des objets (Artefacts Canada 2006). 

## Bibliographie

Artefacts Canada. 2006. [https://app.pch.gc.ca/application/artefacts_hum/indice_index.app?lang=fr](https://app.pch.gc.ca/application/artefacts_hum/indice_index.app?lang=fr).

Bann, Stephen. « The Return to Curiosity: Shifting Paradigms in Contemporary Museum Display ». *Art and Its Publics: Museum Studies at the Millennium*, édité par Andrew McClellan. New Interventions in Art History 2. Malden, US-MA : Blackwell Pub. Co., 2003 : 117-132.

Conseil international des musées. *Object ID*. ICOM. 19 juillet 2021. [https://icom.museum/en/resources/standards-guidelines/objectid/](https://icom.museum/en/resources/standards-guidelines/objectid/).

Đerić, Tamara Nikolić, Jorjin Neyrinck, et Evelyne Seghers. *Museums and Intangible Cultural Heritage: Towards a Third Space in the Heritage Sector, A Companion to Discover Transformative Heritage Practices for the 21st Century*. Projet sur le patrimoine culturel immatériel et les musées. Anderlecht, BE-BRU : Werkplaats immaterieel erfgoed, 2020. [https://www.ichandmuseums.eu/en/toolbox/book-museums-and-intangible-cultural-heritage/success#details](https://www.ichandmuseums.eu/en/toolbox/book-museums-and-intangible-cultural-heritage/success#details).

Doerr, Martin, et Christian Emil Ore, éds. *Definition of the CIDOC Conceptual Reference Model*. Documentations du CIDOC CRM, 7.0.1. Paris, FR-IDF : Conseil international des musées (ICOM), 2020. [http://www.cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.0.1_%2018-10-2020.pdf](http://www.cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.0.1_%2018-10-2020.pdf).

Karsh, Yousuf. *Self Portret*. Photographie. 1938. Cette image est disponible à Bibliothèque et Archives Canada sous le numéro de référence de reproduction PA-212511 et sous l'identifiant MIKAN 3198631. Cette étiquette n'indique pas le statut du droit d'auteur de l'œuvre jointe. Une étiquette normale de droit d’auteur est encore requise. Voir *Commons: Licensing* pour plus d'informations. Bibliothèque et Archives Canada ne permet pas l'utilisation libre de ses œuvres protégées par le droit d'auteur. Voir *Category: Images from Library and Archives Canada*. [https://commons.wikimedia.org/wiki/File:Yousuf-Karsh.jpg](https://commons.wikimedia.org/wiki/File:Yousuf-Karsh.jpg).

Law, Simon. *Toronto Eaton Centre, Toronto, Canada*. Photographie. Flickr. 2006. [https://commons.wikimedia.org/wiki/File:Flight_stop.jpg](https://commons.wikimedia.org/wiki/File:Flight_stop.jpg).

MacDonald, Sharon, éd. « Collecting Practices ». *A Companion to Museum Studies*. Blackwell Companions in Cultural Studies. Malden, US-MA : John Wiley & Sons, 2011 : 81-97.

Schmidt-Linsenhoff, Viktoria. « Who Is the Subject? Marie-Guillemine Benoist’s Portrait d’une Négresse ». *Slave Portraiture in the Atlantic World*, édité par Agnes Lugo-Ortiz et Angela Rosenthal. Livre de poche. Cambridge, UK-CAM : Cambridge University Press, 2013 : 315-345.

Snow, Michael. *Flight Stop*. Sculpture. Flickr. 1979. [https://commons.wikimedia.org/wiki/File:Flight_stop.jpg](https://commons.wikimedia.org/wiki/File:Flight_stop.jpg).

Waller, Susan. « Marie-Guillemine Benoist, Portrait of Madeleine ». *Smarthistory* (blogue). 26 septembre 2018. [https://smarthistory.org/benoist-portrait/](https://smarthistory.org/benoist-portrait/).

Waterhouse, John William. *« 'I Am Half Sick of Shadows', Said The Lady of Shalott » (Alfred, Lord Tennyson, The Lady of Shalott, Part II)*. Peinture. 1915. [https://en.wikipedia.org/w/index.php?title=File:John_William_Waterhouse_-\_I_am_half-sick_of_shadows,\_said_the_lady_of_shalott.JPG&oldid=838315116](https://en.wikipedia.org/w/index.php?title=File:John_William_Waterhouse_-_I_am_half-sick_of_shadows,_said_the_lady_of_shalott.JPG&oldid=838315116).

Wikipedia. « Flight Stop ». *Wikipedia*. San Francisco, US-CA : Wikipedia, 2021. [https://en.wikipedia.org/w/index.php?title=Flight_Stop&oldid=1021679066](https://en.wikipedia.org/w/index.php?title=Flight_Stop&oldid=1021679066).

Wikipedia. « John William Waterhouse - I Am Half-Sick of Shadows, Said the Lady of Shalott.JPG ». *Wikipedia*. San Francisco, US-CA : Wikipedia, 2018. [https://en.wikipedia.org/w/index.php?title=File:John_William_Waterhouse_-\_I_am_half-sick_of_shadows,\_said_the_lady_of_shalott.JPG&oldid=838315116](https://en.wikipedia.org/w/index.php?title=File:John_William_Waterhouse_-_I_am_half-sick_of_shadows,_said_the_lady_of_shalott.JPG&oldid=838315116).

