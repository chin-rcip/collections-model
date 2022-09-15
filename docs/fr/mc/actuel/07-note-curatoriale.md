---
layout: page
language: fr
title: Note curatoriale
permalink: /fr/modele-cible/actuel/note-curatoriale
other_link: /en/target-model/current/curatorial-note
sidebar: mc22
date: 2022-06-30
description: La Spécification du modèle cible des actants modélise sémantiquement les actants dans un contexte patrimonial. Les patrons conceptuels les plus pertinents pour la vie des actants sont présentés avec des diagrammes et des exemples qui les illustrent, ainsi qu'un compte rendu et une explication des décisions pertinentes qui ont été prises lors de l'élaboration desdits patrons conceptuels. Il s'agit d'une documentation théorique qui n'a jamais été testée ou mise en application.
---

## Aperçu {#apercu}

Ce patron conceptuel peut être utilisé pour représenter les informations associées à un actant qui ne peuvent pas être enregistrées à travers des champs structurés, mais qui se rapportent à un autre nœud de données représenté ailleurs dans le modèle. Les informations peuvent être générales ou plus précises et visent principalement à offrir des connaissances supplémentaires. Elles comprennent les commentaires, les remarques ou les descriptions tels que les explications, les notes, les résultats, les évaluations, etc. Ce patron conceptuel comprend : 

* Le contenu d'une note curatoriale;
* L'auteur·e d'une note curatoriale;
* La langue dans laquelle une note curatoriale a été enregistrée.

Ce patron conceptuel ne doit pas être utilisé pour représenter :

* Les annotations qui se rapportent au modèle lui-même et qui apparaissent au cours du processus de cartographie (p. ex. les évaluations de la qualité des données, les enjeux de modélisation et/ou de cartographie, la documentation, les informations que le soumissionnaire souhaite soumettre avec le jeu de données) (le patron conceptuel [Concepts généraux – Annotations ou commentaires](/collections-model/fr/modele-cible/actuel/concepts-generaux#annotations-ou-commentaires) doit plutôt être utilisé);
* Le contenu (p. ex. textuel) non structuré d'un champ de données (le patron conceptuel [Données désordonnées](/collections-model/fr/modele-cible/actuel/donnees-desordonnees) doit plutôt être utilisé);
* Le ou les descriptions biographiques d'un actant (le patron conceptuel [Biographie](/collections-model/fr/modele-cible/actuel/biographie) doit plutôt être utilisé);
* Les données qui ne sont pas couvertes par la Spécification du modèle cible, auquel cas les propositions de nouveaux patrons conceptuels sémantiques peuvent être soumises au RCIP par le biais de la section [GitHub Issues](https://github.com/chin-rcip/collections-model/issues).

## Introduction et contexte

### Historique théorique {#historique-theorique}

La plupart des musées disposent d'un champ de remarques ou de notes contenant des informations qui peuvent être complémentaires soit aux actants et aux objets en général, soit à un champ de données spécifique. Par exemple, une note pourrait préciser que la date de naissance d'un artiste est estimée à au moins 15 ans avant la production de son œuvre connue comme étant la plus ancienne. Ces notes sont souvent des éléments textuels distincts des textes descriptifs destinés à être publiés (p. ex. les légendes). Le contenu de ces notes curatoriales peut aider à mettre en contexte les données qu'elles documentent et constitue, à ce titre, un élément nécessaire des modèles de données patrimoniales.

Afin de répondre adéquatement aux besoins de divers utilisateurs·rices – le plus souvent déterminés par les domaines d'activité et les communautés cibles qui circonscrivent généralement le développement de modèles (Bruseker 2017), un modèle d'agrégation doit prendre en compte le plus large éventail possible d'informations provenant d'un domaine d'activité et tenir compte de la variabilité de la nature, du format et de la compréhension des données. Par conséquent, il est d'usage d'avoir une combinaison de patrons conceptuels précis pour assurer une représentation minutieuse des informations structurées, ainsi que des patrons conceptuels plus larges pour prendre en compte les informations imprévues qui ne peuvent pas être intégrées dans les champs de métadonnées existants (Allemang, Hendler et Gandon 2020, 26-34). 

### Énoncé des besoins {#enonce-des-besoins}

Les notes curatoriales sont des informations imprévues dont il faut tenir compte et qui peuvent être utiles pour déterminer les ajouts ou les améliorations possibles à un modèle (p. ex. de nouveaux patrons conceptuels ou la révision de patrons conceptuels plus précis). 

Par défaut, l'actant qui crée une note curatoriale est considéré comme l'institution ou la personne qui soumet les données (voir le patron conceptuel [Provenance du jeu de données](/collections-model/fr/modele-cible/actuel/provenance-du-jeu-de-donnees)). Toutefois, si un·e conservateur·rice ou un·e expert·e a été explicitement enregistré·e comme l'auteur·e ou le ou la créateur·rice de la note, cette information doit également être modélisée selon ce patron conceptuel.

En outre, en raison de leur forme textuelle, il est essentiel de documenter la langue dans laquelle les notes curatoriales sont rédigées afin de faciliter l'extraction et l'analyse potentielles ultérieures de l'information. 

## Description du patron conceptuel

Pour chaque note curatoriale, une instance de `E39_Actant` ou d'une de ses sous-classes est d'abord liée par la propriété `P67i_fait_l’objet_d’un_renvoi_par` à une instance de `E33_Objet_linguistique`, qui est ensuite liée à :

* Une instance de `E55_Type` (un nœud doté d’un qualifiant spécifié) portant le libellé « Note curatoriale » par la propriété `P2_a_pour_type`;
* La valeur littérale du [Contenu de la note curatoriale](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#contenu-de-la-note-curatoriale) par la propriété `P190_a_pour_contenu_symbolique`;
* La valeur de la [Langue de la note curatoriale](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#langue-de-la-note-curatoriale) (une instance de `E56_Langue`) par la propriété `P72_a_pour_langue`;
* Une instance de `E65_Création` par la propriété `P94i_a_été_créé_par` qui est liée à une instance de `E39_Actant` qui représente l'actant ayant rédigé la note curatoriale par la propriété `P14_a_été_effectué_par`. Cette instance de `E39_Actant` est également liée par la propriété `P1_est_identifié_par` à une instance de `E33_Objet_linguistique` et de `E41_Appellation` qui est qualifiée par la valeur littérale de l'[Appellation de l'actant rédigeant la note curatoriale](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-de-lactant-redigeant-la-note-curatoriale) par la propriété `P190_a_pour_contenu_symbolique`.

## Diagramme

<a name="068_PatronConceptuel_NoteCuratoriale_p"></a>068_PatronConceptuel_NoteCuratoriale_p

<iframe frameborder="0" style="width:100%;height:500px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=068_PatronConceptuel_NoteCuratoriale_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1la8J2GhxniDYXFgdd3V4R9qh1iOpUiwW%26export%3Ddownload"></iframe>

## Exemples

### Exemple 1

L'enregistrement de Yousuf Karsh dans Artistes au Canada comprend un champ *Remarques* dont la valeur est « Immigré au Canada en 1924 » (`P190_a_pour_contenu_symbolique`, Contenu de la note curatoriale) (Patrimoine canadien, Gouvernement du Canada 2011).

<div id="0001_100_curatorial-note" class="example"></div>

### Exemple 2

Greg A. Hill (`P190_a_pour_contenu_symbolique`, Appellation de l'actant rédigeant la note curatoriale), en tant que conservateur principal Audain de l'art autochtone au Musée des beaux-arts du Canada, pourrait vouloir commenter un actant.

<div id="0001_126_curatorial-note" class="example"></div>

### Exemple 3

La note « Rebecca Belmore was the first Indigenous woman to present at the Canadian pavilion of the Venice Biennale in 2005 » (`P190_a_pour_contenu_symbolique`, Contenu de la note curatoriale) est rédigée en anglais (`P72_a_pour_langue`, Langue de la note curatoriale) (Berlin et Baird 2014).

<div id="0001_127_curatorial-note" class="example"></div>

## Documentation connexe

### Modèles externes {#modeles-externes}

* Linked.art : [Baseline Patterns ​​– Statements about a Resource](https://linked.art/model/base/#statements-about-a-resource) 
* SARI : [Person Reference Data Model – Description](https://docs.swissartresearch.net/et/persons/#description)

### Nœuds de saisie {#noeuds-de-saisie}

* [Appellation de l'actant rédigeant la note curatoriale](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-de-lactant-redigeant-la-note-curatoriale) \| Liste de vérification
* [Contenu de la note curatoriale](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#contenu-de-la-note-curatoriale) \| Liste de vérification
* [Langue de la note curatoriale](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#langue-de-la-note-curatoriale) \| Liste de vérification

### Entités du CIDOC CRM {#entites-du-cidoc-crm}

* `E33_Objet_linguistique` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E33)]
* `E39_Actant` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E39)]
* `E41_Appellation` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E41)]
* `E55_Type` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E55)]
* `E56_Langue` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E56)]
* `E65_Création` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E65)]
* `P1_est_identifié_par (identifie)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P1)]
* `P2_a_pour_type (est_le_type_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P2)]
* `P14_a_été_effectué_par (a_effectué)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P14)]
* `P72_a_pour_langue (est_la_langue_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P72)]
* `P94_a_créé (a_été_créé_par)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P94)]
* `P190_a_pour_contenu_symbolique` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P190)]

## Discussion

### Justification

Dans la plupart des cas, les valeurs des notes curatoriales seront du texte non structuré, c'est pourquoi la classe `E33_Objet_linguistique` est utilisée en conjonction avec la propriété `P190_a_pour_contenu_symbolique`. Cependant, comme cette classe est également employée dans d'autres patrons conceptuels, elle doit être établie comme appartenant à une note curatoriale en l'identifiant comme une instance de `E55_Type` avec le libellé « Note curatoriale ». Cela clarifie la nature de l'information et facilite les requêtes.

Parce que la note est considérée comme le produit d'une action effectuée par son auteur·e, elle peut être considérée comme étant « créée » (`E65_Création`); c'est pourquoi la classe `E65_Création` doit être utilisée plutôt que sa super-classe `E7_Activité`, plus largement définie.

### Limitations

Il est possible d'extraire des données significatives des notes curatoriales, mais cela demande beaucoup de travail et/ou nécessite des ressources technologiques et une expertise dont la plupart des institutions patrimoniales ne disposent pas (p. ex. le traitement des langues naturelles). C'est le cas dans l'environnement actuel de DOPHEDA; pour l'instant, ces contenus ne peuvent pas être structurés davantage.





De plus, il n'y a aucun moyen d'identifier ou de catégoriser les notes curatoriales par sujet. Si une personne s'intéresse à un sujet particulier, elle ne peut pas filtrer les notes curatoriales afin de restreindre sa recherche (voir l'[Enjeu no 63](https://github.com/chin-rcip/collections-model/issues/63)). 

### Enjeux connexes sur GitHub

* [Enjeu n° 20 « Que faire du champ "Remarques" dans certains musées? »](https://github.com/chin-rcip/collections-model/issues/20) (en anglais)
* [Enjeu n° 63 « Sujet de la note curatoriale »](https://github.com/chin-rcip/collections-model/issues/63) (en anglais)

### Cas limites

#### Exemple 1 {#cas-limites-exemple-1}

En utilisant le même exemple ci-dessus concernant les remarques dans l'enregistrement de Yousuf Karsh dans Artistes au Canada, la valeur « Immigré au Canada en 1924 » peut être considérée comme une note d'une activité de séjour au Canada qui a débuté en 1924.

#### Exemple 2 {#cas-limites-exemple-2}

Le *Portrait de Madeleine* de Marie-Guillemine Benoist a auparavant été intitulé en utilisant une description raciale. De récentes études ont établi que le nom de la personne assise représentée était « Madeleine », mais son nom de famille demeure inconnu. Une annotation pourrait être placée sur les Appellations de l'artefact (avec « Portrait de Madeleine » comme appellation préférée (Primauté de l'appellation de l'artefact) et l'annotation « Ancien titre affichant un langage racial insensible »; « Portrait d'une femme noire » comme appellation non préférée (Primauté de l'appellation de l'artefact) et l'annotation « Maintenant intitulé Portrait de Madeleine »; avec « Portrait d'une femme noire » comme appellation non préférée (Primauté de l'appellation de l'artefact) et l'annotation « Ancien titre comportant un langage racial insensible »), mais une note curatoriale pourrait également être utilisée pour l'actant « Madeleine » qui est représenté (« Personne assise dans le *Portrait de Madeleine*, ancien titre comportant un langage racial insensible avec la personne assise identifiée comme étant "Madeleine" par Viktoria Schmidt-Linsenhoff »). Le même Contenu de la note curatoriale pourrait également être appliqué à Marie-Guillemine Benoist. Le fait que le Contenu de la note curatoriale concerne l'artiste, la personne représentée, ou les deux, dépend de la formulation du soumissionnaire (Schmidt-Linsenhoff 2013; Waller 2018).

## Bibliographie

Allemang, Dean, James A. Hendler, et Fabien Gandon. *Semantic Web for the Working Ontologist: Effective Modeling for Linked Data, RDFS, and OWL*. Troisième édition. ACM Books 33. New York, US-NY : ACM Books, 2020.

Bekiari, Chryssoula, George Bruseker, Martin Doerr, Christian-Emil Ore, Stephen Stead, et Athanasios Velios, éds. *Definition of the CIDOC Conceptual Reference Model*. Documentations du CIDOC CRM, 7.1. Paris, FR-IDF : CIDOC CRM Special Interest Group, 2021. [http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf](http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf.).

Berlin, Mira, et Daniel Baird. « Rebecca Belmore ». *L'Encyclopédie canadienne*. Toronto, CA-ON : Historica Canada, 2016 [2014]. [https://www.thecanadianencyclopedia.ca/en/article/rebecca-belmore](https://www.thecanadianencyclopedia.ca/en/article/rebecca-belmore).

Bruseker, George. « Principles for Modelling Ontologies: A Short Reference Guide ». *Projet Parthenos*. 17 (2017) : 72.

Patrimoine canadien, Gouvernement du Canada. « Karsh, Yousuf ». *Artistes au Canada*. Ottawa, CA-ON : Gouvernement du Canada, 2011. [https://app.pch.gc.ca/application/aac-aic/artiste_detailler_bas-artist_detail_bas.app?lang=en&rID=8494](https://app.pch.gc.ca/application/aac-aic/artiste_detailler_bas-artist_detail_bas.app?lang=en&rID=8494).

Schmidt-Linsenhoff, Viktoria. « Who Is the Subject? Marie-Guillemine Benoist’s Portrait d’une Négresse ». *Slave Portraiture in the Atlantic World*, édité par Agnes Lugo-Ortiz et Angela Rosenthal. Livre de poche. Cambridge, UK-CAM : Cambridge University Press, 2013 : 315-345.

Waller, Susan. « Marie-Guillemine Benoist, Portrait of Madeleine ». *Smarthistory* (blogue). 26 septembre 2018. [https://smarthistory.org/benoist-portrait/](https://smarthistory.org/benoist-portrait/).









