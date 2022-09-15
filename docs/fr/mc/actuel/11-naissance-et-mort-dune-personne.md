---
layout: page
language: fr
title: Naissance et mort d'une personne
permalink: /fr/modele-cible/actuel/naissance-et-mort-dune-personne
other_link: /en/target-model/current/birth-and-death-of-a-person
sidebar: mc22
date: 2022-06-30
description: La Spécification du modèle cible des actants modélise sémantiquement les actants dans un contexte patrimonial. Les patrons conceptuels les plus pertinents pour la vie des actants sont présentés avec des diagrammes et des exemples qui les illustrent, ainsi qu'un compte rendu et une explication des décisions pertinentes qui ont été prises lors de l'élaboration desdits patrons conceptuels. Il s'agit d'une documentation théorique qui n'a jamais été testée ou mise en application.
---

## Aperçu {#apercu}

Ce patron conceptuel peut être utilisé pour représenter les informations relatives à la durée de vie d'une personne (naissance et mort). Il comprend : 

* La date et le lieu de naissance d'une personne;
* Les parents biologiques d'une personne; 
* La date et le lieu de mort d'une personne; 
* Le lieu où les restes d'une personne sont situés (lieu de sépulture). 

Il concerne spécifiquement les informations vitales des personnes, et non leurs relations, les informations vitales des agents non humains (p. ex. les animaux ou les groupes) ou des humains non vivants (p. ex. les restes humains). En tant que tel, il ne comprend pas : 

* Les parents adoptifs d'une personne (le patron conceptuel [Relation](/collections-model/fr/modele-cible/actuel/relation) doit plutôt être utilisé); 
* La relation d'une personne avec ses parents (c.-à-d. ce patron conceptuel décrit la parenté biologique plutôt que le lien social entre la personne et ses parents) (le patron conceptuel [Relation](/collections-model/fr/modele-cible/actuel/relation) doit plutôt être utilisé);
* L'appartenance d'une personne à une famille (le patron conceptuel [Appartenance familiale](/collections-model/fr/modele-cible/actuel/appartenance-familiale) doit plutôt être utilisé);
* La cause de la mort d'une personne;
* La date et le lieu de naissance et de mort d'un agent non humain, tel qu'un animal ou une chose; 
* Le lieu où les restes d'un agent non humain, comme un animal ou une chose, sont situés (lieu de sépulture).

## Introduction et contexte

### Historique théorique {#historique-theorique}

L'enregistrement des statistiques d'état civil relatives à la naissance et à la mort des personnes remonte à l'Antiquité, lorsque ces informations étaient utilisées par les États pour déterminer les impôts et estimer les effectifs militaires (Brumberg et al. 2012, 407). Il s'agit d'une partie statistiquement et culturellement importante des données patrimoniales qui est souvent utilisée pour situer les actants dans des tendances sociétales et démographiques plus larges, et qui constitue un élément clé de la recherche en généalogie et en histoire des familles (Bibliothèque et Archives Canada 2020). 

Ces données sont utiles pour visualiser les tendances en matière de composition familiale, de lignée généalogique, de localisation d'actants dans l'espace et le temps, ou d'appartenance nationale (puisque les entités politiques peuvent changer au fil du temps, p. ex. Yousuf Karsh est né dans l'actuelle Turquie à l'époque de l'Empire ottoman (Éditeurs de la Encyclopædia Britannica n.d.)). Les lieux d'enterrement, en particulier, peuvent être révélateurs des mœurs et des pratiques sociales entourant la mort et sont de plus en plus enregistrés par des actants intéressés par la généalogie ou les données patrimoniales comme [Wikidata](https://www.wikidata.org/wiki/Property:P119) (Wikidata 2021) ou les instituts généalogiques, par exemple [Family Search](https://www.familysearch.org/wiki/en/Canada_Cemeteries) (FamilySearch 2020).

### Énoncé des besoins {#enonce-des-besoins}

Il est important de garder à l'esprit que les informations vitales sont souvent enregistrées de manière incohérente ou problématique, et que les données du recensement sont fortement encadrées par la méthodologie du recensement, de sorte que toute utilisation d'informations vitales doit être fortement réfléchie (Hamilton 2008). Par exemple, les enregistrements coloniaux de l'ascendance autochtone sont notoirement imparfaits et n'ont souvent pas répertorié les actants autochtones, ou l'ont fait en utilisant des méthodes coloniales de collecte, d'enregistrement et d'archivage qui n'englobent pas les traditions et les concepts jugés pertinents pour leur ascendance par les peuples autochtones (Devlin & Cuggy 2017; Royal British Columbia Museum 2018). De telles utilisations des registres d'état civil doivent être faites de manière critique et prudente. 

Les dates et les lieux de naissance et de mort sont non seulement statistiquement significatifs, mais également cruciaux pour la désambiguïsation des actants (c.-à-d. que deux personnes différentes peuvent porter le même nom par hasard, ou une seule personne peut être associée à plusieurs noms ou orthographes d'un nom), car ils peuvent être utilisés pour confirmer l'identité d'une personne (OCLC 2019, 4). 

Comme ces informations sont couramment utilisées par les institutions patrimoniales et qu'elles servent à des fins de désambiguïsation, elles sont probablement parmi les plus documentées. Cela signifie que ces données seront, de manière prévisible, sujettes à l'échange et à la mobilisation par plusieurs soumissionnaires. L'interopérabilité avec d'autres modèles pertinents est donc importante pour le développement de ces patrons conceptuels.

Il est donc nécessaire d'identifier la personne qui est née, quand, où et de qui (père et mère biologiques), quand et où elle est morte, ainsi que l'endroit où se trouve sa dépouille. 

## Description du patron conceptuel

Ce patron conceptuel est basé sur une approche de modélisation dans laquelle un évènement incarne le « début » et la « fin » de l'entité (dans ce cas, une instance de `E21_Personne`). 

La naissance d'une personne est modélisée comme suit :

* Une instance de `E21_Personne` est liée à une instance de `E67_Naissance` par la propriété `P98_a_donné_vie_à`;
* L'instance de `E67_Naissance` est d'abord liée à une autre instance de `E21_Personne` représentant la mère biologique de la personne en utilisant la propriété `P96_de_mère`, qui est liée à une instance de `E41_Appellation` et de `E33_Objet_linguistique` par la propriété `P1_est_identifié_par`. À partir de cette instance, la valeur littérale de l'[Appellation de la mère](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-de-la-mere) est qualifiée par la propriété `P190_a_pour_contenu_symbolique`;
* De la même manière, la même instance de `E67_Naissance` est liée à une autre instance de `E21_Personnne` représentant le père biologique de la personne en utilisant la propriété `P97_de_père`, qui est liée à une instance de `E41_Appellation` et de `E33_Objet_linguistique` par la propriété `P1_est_identifié_par`. De cette instance, la valeur littérale de l'[Appellation du père](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-du-pere) est qualifiée par la propriété `P190_a_pour_contenu_symbolique`;
* Le lieu de naissance est indiqué en liant l'instance de `E67_Naissance` à la valeur du [Lieu de naissance](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#lieu-de-naissance) (une instance de `E53_Lieu`) par le biais de la propriété `P7_a_eu_lieu_dans`;
* Le moment lors duquel la naissance a eu lieu est indiqué à l'aide du patron conceptuel [Limites temporelles](/collections-model/fr/modele-cible/actuel/limites-temporelles) lié à l'instance de `E67_Naissance` par la propriété `P4_a_pour_intervalle_temporel` avec des valeurs extraites des nœuds de saisie [Date de début de la naissance](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-de-la-naissance), [Qualifiant de la date de début de la naissance](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-de-la-naissance), [Date de fin de la naissance](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-de-la-naissance) et [Qualifiant de la date de fin de la naissance](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-de-la-naissance). 

La mort d'une personne est modélisée comme suit : 

* Une instance de `E21_Personne` est liée à une instance de `E69_Mort` par la propriété `P100_a_été_la_mort_de`;
* Le lieu de mort est indiqué en liant l'instance de `E69_Mort` à la valeur du [Lieu de mort](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#lieu-de-mort) (une instance de `E53_Lieu`) par le biais de la propriété `P7_a_eu_lieu_dans`;
* Pour documenter le déplacement du corps du ou de la défunt·e de son dernier emplacement vers son lieu de disposition finale, une instance de `E9_Déplacement` est liée à l'instance de `E53_Lieu` représentant le lieu où la mort a eu lieu par la propriété `P27_a_déplacé_depuis`, en plus d'être liée par la propriété `P26_a_déplacé_vers` à la valeur du [Lieu de disposition finale](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#lieu-de-disposition-finale) qui est qualifiée par une instance de `E55_Type` (un nœud doté d’un qualifiant spécifié) portant le libellé « Lieu de sépulture » à l'aide de la propriété `P2_a_pour_type`;
* Pour indiquer que la mort de la personne a nécessairement eu lieu *avant* le déplacement de sa dépouille, l'instance de `E69_Mort` est également liée à l'instance de `E9_Déplacement` en utilisant la propriété CRMarcheo `AP28_se_produit_avant`;
* Le moment lors duquel la mort a eu lieu est indiqué à l'aide du patron conceptuel [Limites temporelles](/collections-model/fr/modele-cible/actuel/limites-temporelles) lié à l'instance de `E69_Mort` par la propriété `P4_a_pour_intervalle_temporel` avec des valeurs extraites des nœuds de saisie [Date de début de la mort](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-de-la-mort), [Qualifiant de la date de début de la mort](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-de-la-mort), [Date de fin de la mort](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-de-la-mort) et [Qualifiant de la date de fin de la mort](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-de-la-mort). 

## Diagramme

<a name="039_PatronConceptuel_NaissanceEtMort_p"></a>039_PatronConceptuel_NaissanceEtMort_p

<iframe frameborder="0" style="width:100%;height:500px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=039_PatronConceptuel_NaissanceEtMort_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1Uir3n4v090CQFzJQtzRWigUCYQh7p_8E%26export%3Ddownload"></iframe>

## Exemples

### Exemple 1

Yousuf Karsh (`P190_a_pour_contenu_symbolique`, Appellation de l'actant) est né le 23 décembre 1908 (`P82a_le_début_du_début`, Date de début de la naissance; `P82b_la_fin_de_la_fin`, Date de fin de la naissance) à Mardin (Empire ottoman) (`P7_a_eu_lieu_dans`, Lieu de naissance) de Bahiyah Nakash (`P190_a_pour_contenu_symbolique`, Appellation de la mère) et Massih Karsh (`P190_a_pour_contenu_symbolique`, Appellation du père). Il est décédé le 13 juillet 2002 (`P82a_le_début_du_début`, Date de début de la mort; `P82b_la_fin_de_la_fin`, Date de fin de la mort) à Boston (MA, États-Unis) (`P7_a_eu_lieu_dans`, Lieu de mort) et est enterré au cimetière Notre-Dame à Ottawa (ON, Canada) (`P26_a_déplacé_vers`, Lieu de disposition finale; `P2_a_pour_type`, « Lieu de sépulture ») (Éditeurs de la Encyclopædia Britannica n.d).

<div id="0001_100_birth-death" class="example"></div>

### Exemple 2

Emily Carr (`P190_a_pour_contenu_symbolique`, Appellation de l'actant) est née le 13 décembre 1871 (`P82a_le_début_du_début`, Date de début de la naissance; `P82b_la_fin_de_la_fin`, Date de fin de la naissance) à Victoria (C.-B., Canada) (`P7_a_eu_lieu_dans`, Lieu de naissance) d’Emily (Saunders) Carr (`P190_a_pour_contenu_symbolique`, Appellation de la mère) et Richard Carr (`P190_a_pour_contenu_symbolique`, Appellation du père). Elle est décédée le 2 mars 1945 (`P82a_le_début_du_début`, Date de début de la mort; `P82b_la_fin_de_la_fin`, Date de fin de la mort), également à Victoria (C.-B., Canada) (`P7_a_eu_lieu_dans`, Lieu de mort), et a été enterrée au Ross Bay Cemetery (C.-B., Canada) (`P26_a_déplacé_vers`, Lieu de disposition finale; `P2_a_pour_type`, « Lieu de sépulture ») (Baldissera 2015, 4).

<div id="0001_106_birth-death" class="example"></div>

### Exemple 3

David Altmejd (`P190_a_pour_contenu_symbolique`, Appellation de l'actant) est né en 1974 (`P82a_le_début_du_début`, Date de début de la naissance; `P82b_la_fin_de_la_fin`, Date de fin de la naissance) à Montréal (QC, Canada) (`P7_a_eu_lieu_dans`, Lieu de naissance) (Musée d'art contemporain de Montréal 2015). 

<div id="0001_109_birth" class="example"></div>

## Documentation connexe

### Modèles externes {#modeles-externes}

* Linked.art : [Birth and Death/Formation and Dissolution](https://linked.art/model/actor/#birth-and-death-formation-and-dissolution)
* SARI : [Person Reference Data Model – Person Existence](https://docs.swissartresearch.net/et/persons/#existence)

### Nœuds de saisie {#noeuds-de-saisie}

* [Appellation de la mère](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-de-la-mere) \| Liste de vérification
* [Appellation du père](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-du-pere) \| Liste de vérification
* [Date de début de la mort](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-de-la-mort) \| Liste de vérification
* [Date de début de la naissance](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-de-la-naissance) \| Liste de vérification
* [Date de fin de la mort](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-de-la-mort) \| Liste de vérification
* [Date de fin de la naissance](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-de-la-naissance) \| Liste de vérification
* [Lieu de disposition finale](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#lieu-de-disposition-finale) \| Liste de vérification
* [Lieu de mort](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#lieu-de-mort) \| Liste de vérification
* [Lieu de naissance](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#lieu-de-naissance) \| Liste de vérification
* [Qualifiant de la date de début de la mort](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-de-la-mort) \| Liste de vérification
* [Qualifiant de la date de début de la naissance](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-de-la-naissance) \| Liste de vérification
* [Qualifiant de la date de fin de la mort](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-de-la-mort) \| Liste de vérification
* [Qualifiant de la date de fin de la naissance](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-de-la-naissance) \| Liste de vérification

### Entités du CIDOC CRM {#entites-du-cidoc-crm}

* `AP28_se_produit_avant (se_produit_après)`
* `E9_Déplacement` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E9)]
* `E21_Personne` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E21)]
* `E33_Objet_linguistique` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E33)]
* `E41_Appellation` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E41)]
* `E52_Intervalle_temporel` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E52)]
* `E53_Lieu` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E53)]
* `E55_Type` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E55)]
* `E67_Naissance` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E67)]
* `E69_Mort` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E69)]
* `P1_est_identifié_par (identifie)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P1)]
* `P2_a_pour_type (est_le_type_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P2)]
* `P4_a_pour_intervalle_temporel (est_l’intervalle_temporel_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P4)]
* `P7_a_eu_lieu_dans (a_été_témoin_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P7)]
* `P25_a_déplacé (a_été_déplacé_par)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P25)]
* `P26_a_déplacé_vers (a_été_la_destination_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P26)]
* `P27_a_déplacé_depuis (a_été_le_point_de_départ_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P27)]
* `P79_a_son_début_qualifié_par` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P79)]
* `P80_a_sa_fin_qualifiée_par` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P80)]
* `P82a_le_début_du_début`
* `P82b_la_fin_de_la_fin`
* `P96_de_mère (a_donné_naissance_à)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P96)]
* `P97_de_père (a_été_le_père_pour)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P97)]
* `P98_a_donné_vie_à (est_né)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P98)]
* `P100_a_été_la_mort_de (est_mort_par)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P100)]
* `P190_a_pour_contenu_symbolique` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P190)]

## Discussion

### Justification

La filiation biologique (c.-à-d. le fait d'être biologiquement la mère et le père d'une personne) et la filiation parentale (c.-à-d. la relation sociale que la personne entretient avec ses parents et vice-versa) sont considérées comme distinctes dans le cadre du modèle DOPHEDA afin que chaque type de filiation puisse être enregistré de manière précise et exacte. L'enregistrement des interactions parentales et familiales est modélisé à l'aide du patron conceptuel [Relation](/collections-model/fr/modele-cible/actuel/relation). Ainsi, la modélisation du lignage biologique abordé dans ce patron conceptuel doit être employée lorsque l'objectif est de documenter des informations généalogiques. 

La modélisation du lieu de disposition finale, et notamment l'utilisation d'une instance de `E9_Déplacement`, est ontologiquement contestable. Représenter le déplacement post-mortem de la personne (`E21_Personne`) vers sa tombe par une instance de `E9_Déplacement` (évènement de déplacement) est la solution de modélisation la plus simple pour représenter le déplacement intentionnel de restes humains. Cependant, il s'agit d'une représentation conceptuellement problématique puisque les restes de la personne défunte ne peuvent techniquement pas être associés à une instance de `E21_Personne`. La logique du CIDOC CRM impose la création d'une instance de `E20_Objet_biologique` pour remplacer l'instance de `E21_Personne` par une instance de `E81_Transformation`. Sinon, le patron conceptuel (dans son état actuel) indiquerait que la personne a été déplacée et enterrée vivante. Cependant, cette modélisation plus longue et plus précise est très complexe et implique la création de nœuds qui alourdissent considérablement le modèle, complexifient sensiblement les requêtes et sollicitent inutilement les utilisateurs·rices. Étant donné qu'il existe très peu d'enregistrements de personnes enterrées vivantes (surtout en tant que telles) dans les collections patrimoniales, il semble préférable de faire un compromis sur la précision sémantique et d'adopter une solution plus simple, en supposant que les actants seront enterrés morts (voir l'[Enjeu no 72](https://github.com/chin-rcip/collections-model/issues/72)).

### Enjeux connexes sur GitHub

* [Enjeu n° 16 « Avons-nous besoin d'un patron conceptuel Relations familiales? Et que faire des parents? »](https://github.com/chin-rcip/collections-model/issues/16) (en anglais)
* [Enjeu n° 72 « Comment modéliser le Lieu de repos? »](https://github.com/chin-rcip/collections-model/issues/72) (en anglais)

### Cas limites

#### Exemple 1 {#cas-limites-exemple-1}

Le Soldat inconnu est mort en France en tant que soldat pendant la Première Guerre mondiale. Il est mort entre le 3 octobre 1914 (date à laquelle le premier contingent canadien a navigué vers l'Europe) et le 11 novembre 1918 (date à laquelle la participation directe des Canadiens au combat a pris fin), bien que la guerre se soit officiellement terminée avec le Traité de Versailles le 28 juin 1919. Il a été enterré au cimetière de guerre du Cabaret-Rouge près de Vimy (France) avant que ses restes ne soient déplacés dans un cercueil commémoratif à Ottawa (ON, Canada). Dans le modèle DOPHEDA, le déplacement de son lieu de mort vers sont lieu d'inhumation ne représenterait pas son passage à Cabaret-Rouge et n'indiquerait qu'un déplacement de la France (où il est mort entre 1914 et 1918) vers le Canada en 2000 (Foot 2018). 

#### Exemple 2 {#cas-limites-exemple-2}

Ramsès II est mort vers 1213 AEC selon la chronologie égyptienne (Hornung et al. 2006, 476-478). Son corps a été embaumé et déposé dans la tombe KV7 de la Vallée des Rois (Égypte actuelle), mais il a rapidement été déplacé et transféré dans d'autres tombes par des prêtres égyptiens pour le protéger des pillages. Le corps a finalement été découvert dans la tombe TT320 en 1881 (Wikipedia 2021).

Dans cet exemple, la momie transférée, ou du moins découverte par les archéologues, ne doit pas être considérée comme une personne (`E21_Personne`), mais plutôt comme un objet biologique (`E20_Objet_biologique`) qui peut être déplacé. Pour l'instant, ce type de transformation ne peut pas être documenté dans le cadre du patron conceptuel Naissance et mort d'une personne.

#### Exemple 3 {#cas-limites-exemple-3}

Maud Kathleen Lewis est née dans sa maison d'enfance de South Ohio, N.-É. (Lieu de naissance) de John Dowley (Appellation du père) et Agnes Dowley (Appellation de la mère) (Art Gallery of Nova Scotia n.d.). En plus de documenter la municipalité où elle est née, une institution pourrait vouloir enregistrer qu’« Elle est née dans sa maison d'enfance ». Cela pourrait être considéré comme une note curatoriale à propos de Maud Kathleen Lewis. Il en va de même pour la mort d'une personne qui est survenue dans la maison de son enfance.

## Bibliographie

Art Gallery of Nova Scotia. « Maud Lewis ». Art Gallery of Nova Scotia. n.d. [https://artgalleryofnovascotia.ca/maud-lewis](https://artgalleryofnovascotia.ca/maud-lewis).

Baldissera, Lisa. *Emily Carr: Life & Work*. Canadian Online Art Book Project. Toronto, CA-ON : Institut de l'art canadien, 2015. [https://www.aci-iac.ca/fr/livres-dart/emily-carr//](https://www.aci-iac.ca/fr/livres-dart/emily-carr//). 

Bibliothèque et Archives Canada. « Naissances, mariages et décès enregistrés au Canada ». *Bibliothèque et Archives Canada*. 9 septembre 2020. [https://www.bac-lac.gc.ca/fra/decouvrez/etat-civil-naissances-mariages-deces/naissances-mariages-deces-enregistres/Pages/naissances-mariages-deces.aspx](https://www.bac-lac.gc.ca/fra/decouvrez/etat-civil-naissances-mariages-deces/naissances-mariages-deces-enregistres/Pages/naissances-mariages-deces.aspx).

Brumberg, H. L., D. Dozor, et S. G. Golombek. « History of the Birth Certificate: From Inception to the Future of Electronic Data ». *Journal of Perinatology* 32, no 6 (Juin 2012) : 407-411. [https://doi.org/10.1038/jp.2012.3](https://doi.org/10.1038/jp.2012.3).

Devlin, Stacy, et Emily Cuggy. « Settler Records, Indigenous Histories: Challenges in Indigenous Genealogical Research ». *Active History* (blogue). 7 décembre 2017. [https://activehistory.ca/2017/12/settler-records-indigenous-histories-challenges-in-indigenous-genealogical-research/](https://activehistory.ca/2017/12/settler-records-indigenous-histories-challenges-in-indigenous-genealogical-research/).

Doerr, Martin, et Christian Emil Ore, éds. *Definition of the CIDOC Conceptual Reference Model*. Documentations du CIDOC CRM, 7.0.1. Paris, FR-IDF : Conseil international des musées (ICOM), 2020. [http://www.cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.0.1_%2018-10-2020.pdf](http://www.cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.0.1_%2018-10-2020.pdf).

Éditeurs de la Encyclopædia Britannica. « Yousuf Karsh ». *Encyclopædia Britannica*. Londres, UK-LDN : Encyclopædia Britannica, n.d. [https://www.britannica.com/biography/Yousuf-Karsh](https://www.britannica.com/biography/Yousuf-Karsh).

FamilySearch. « Canada Cemeteries ». *FamilySearch Wiki*. 7 avril 2020. [https://www.familysearch.org/wiki/en/Canada_Cemeteries](https://www.familysearch.org/wiki/en/Canada_Cemeteries).

Foot, Richard. « Le soldat inconnu du Canada ». *L'Encyclopédie canadienne*. Réimpression, Toronto, CA-ON : Historica Canada, 3 octobre 2018 [2014]. [https://www.thecanadianencyclopedia.ca/fr/article/le-soldat-inconnu](https://www.thecanadianencyclopedia.ca/fr/article/le-soldat-inconnu).

Hamilton, Michelle. « 'Anyone Not on the List Might as Well Be Dead': Aboriginal Peoples and the Censuses of Canada, 1851–1916 ». *Journal of the Canadian Historical Association/Revue de la Société historique du Canada* 18, no 1 (2007) : 57-79. [https://doi.org/10.7202/018254ar](https://doi.org/10.7202/018254ar).

Hornung, Erik, Rolf Krauss, et David A. Warburton, éds. *Ancient Egyptian Chronology*. Leiden, NL-ZH; Boston, US-MA : Brill, 2006.

Linked.art. *Linked Art Data Model*. Linked.art, 2021. [https://linked.art/model/index.html](https://linked.art/model/index.html).

Musée d'art contemporain de Montréal (MACM). *David Altmejd*. MACM, 2015. [http://staging.macm.org/expositions/david-altmejd/](http://staging.macm.org/expositions/david-altmejd/).

OCLC. *Virtual International Authority File Guidelines*. Réimpression, Dublin, US-OH : OCLC, 2019 [2015]. [https://www.oclc.org/content/dam/oclc/viaf/VIAF%20Guidelines.pdf](https://www.oclc.org/content/dam/oclc/viaf/VIAF%20Guidelines.pdf).

Royal British Columbia Museum. *Resources for First Nations Genealogical Research at the BC Archives*. Royal British Columbia Museum, Novembre 2018. [https://royalbcmuseum.bc.ca/sites/default/files/sites/default/files/images/resources_for_first_nations_genealogical_research_at_the_bcarchives_2018.pdf](https://royalbcmuseum.bc.ca/sites/default/files/sites/default/files/images/resources_for_first_nations_genealogical_research_at_the_bcarchives_2018.pdf).

Shadbolt, Doris. « Emily Carr ». *L'Encyclopédie canadienne*. Réimpression, Toronto, CA-ON : Historica Canada, 28 août 2015 [2013]. [https://www.thecanadianencyclopedia.ca/fr/article/emily-carr](https://www.thecanadianencyclopedia.ca/fr/article/emily-carr).

Skidmore, Colleen. « Yousuf Karsh ». *L'Encyclopédie canadienne*. Réimpression, Toronto, CA-ON : Historica Canada, 4 mars 2015 [2010]. [https://www.thecanadianencyclopedia.ca/fr/article/karsh-yousuf](https://www.thecanadianencyclopedia.ca/fr/article/karsh-yousuf).

Wikidata. « Place of Burial (P119) ». *Wikidata*. 9 avril 2021. [https://www.wikidata.org/wiki/Property:P119](https://www.wikidata.org/wiki/Property:P119).

Wikipedia. « Ramesses II ». *Wikipedia*. San Francisco, US-CA : Wikipedia, 2021. [https://en.wikipedia.org/wiki/Ramesses_II](https://en.wikipedia.org/wiki/Ramesses_II).

