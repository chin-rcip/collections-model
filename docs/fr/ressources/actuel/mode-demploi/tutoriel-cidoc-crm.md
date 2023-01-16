---
layout: page
language: fr
title: Tutoriel CIDOC CRM
permalink: /fr/ressources/actuel/mode-demploi/tutoriel-cidoc-crm
other_link: /en/resources/current/how-to/cidoc-crm-tutorial
sidebar: tutcidocfr
group: ressources
subgroup: mode d'emploi
date: 2022-03-08
description: Ce document explique comment utiliser la documentation de CIDOC CRM afin de déterminer les entités susceptibles de répondre à un besoin particulier. Afin d’y parvenir, certains concepts associés aux données ouvertes et liées sont sommairement définis.
---

**Version:** 2.0

**Auteurs:** Marie-Pier Blain, Karine Léonard Brouillet, Philippe Michon

**Date de création:** 2021-02-01

**Date de mise à jour:** 2022-03-08

**Résumé:** Ce document explique comment utiliser la spécification du CIDOC CRM afin de déterminer les entités susceptibles de répondre à un besoin ciblé. Afin d’y parvenir, certains concepts associés aux ontologies mobilisant les données ouvertes et liées sont sommairement définis.

**Pour information:** Pour toute question ou commentaire concernant le Tutoriel CIDOC CRM, veuillez consulter la section [Enjeux](https://github.com/chin-rcip/collections-model/issues) (et ouvrir un Enjeux si c’est pertinent) ou nous contacter par courriel à l'adresse [rcip-chin@pch.gc.ca](mailto:rcip-chin@pch.gc.ca) avec « Tutoriel CIDOC CRM » comme objet.

## Utilisations principales

* Se familiariser avec les principaux termes employés dans le CIDOC CRM;
* Comprendre et utiliser la spécification du CIDOC CRM;
* Identifier les entités pouvant répondre à un besoin précis.

## Contexte

Le *Conceptual Reference Model* du Comité international pour la documentation (CIDOC CRM) est une ontologie formelle ayant pour objectif de faciliter l’intégration, la médiation et l’échange d’informations patrimoniales hétérogènes. Plus spécifiquement, ce modèle définit la sémantique qui sous-tend les schèmes de base de données et les structures des documents utilisés par les institutions muséales et patrimoniales. En outre, il permet d’expliquer la logique de ce que ces institutions documentent afin de favoriser l’interopérabilité sémantique.

## Vocabulaire de base et connaissances préalables {#vocabulaire-de-base-et-connaissances-prealables}

Avant de poursuivre, toute personne utilisant le CIDOC CRM, que ce soit à des fins de modélisation ou non, doit bien comprendre les termes suivants :

* [Classe](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#classe-nom-feminin)
* [Entité](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#entite-nom-feminin)
* [Instance](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#instance-nom-feminin)
* [Propriété](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#propriete-nom-feminin)

## Auditoire visé et description des sections {#auditoire-vise-et-description-des-sections}

### Auditoire

Ce tutoriel s’adresse aux personnes ayant des connaissances techniques et informatiques préalables qui désirent se familiariser avec le CIDOC CRM.

### Sections

* Mode d’emploi : les versions et les extensions du CIDOC CRM, la structuration des entités et la nomenclature utilisée, le cadre conceptuel du modèle ainsi que la méthode d’identification des entités appropriées y sont définis;
* Aide-mémoire : les éléments clés et les pistes d’action à retenir y sont détaillés;
* Pour plus d’informations : des suggestions de lectures complémentaires y sont proposées;
* Bibliographie : les sources bibliographiques ayant contribué à la rédaction de ce tutoriel y sont documentées. 

## Mode d’emploi 

### Versions et extensions

Le CIDOC CRM, dont la version originale est en anglais, est mis à jour sur une base régulière. Lorsque le CIDOC CRM est utilisé à des fins de recherche, il s’avère judicieux de se référer à la dernière version publiée. Toutefois, lorsque le CIDOC CRM est utilisé à des fins d'implémentation d’un modèle, il est préférable de se référer à la dernière version encodée en RDF. En date du 31 octobre 2021, il s’agit de la version 7.1.1.

La liste de toutes les versions est accessible [ici](http://www.cidoc-crm.org/versions-of-the-cidoc-crm).

Le CIDOC CRM sert aussi de fondement à d’autres modèles auxiliaires, dont certains ont été approuvés par le CRM SIG, appelés extensions. Ces extensions, compatibles avec le CIDOC CRM, se trouvent [ici](http://www.cidoc-crm.org/collaborations). Une fois qu’un modèle est sélectionné, il est possible de consulter l’ensemble de ses versions en cliquant sur « Resources » dans le coin supérieur droit. Par exemple, le modèle [CRMgeo](http://www.cidoc-crm.org/crmgeo/) permet de gérer des données géospatiales.

### Structuration des entités du CIDOC CRM {#structuration-des-entites-du-cidoc-crm}

Le CIDOC CRM n’est pas conçu pour être lu du début à la fin. Pour naviguer efficacement dans ce document de référence, une compréhension des concepts suivants est nécessaire.

#### Nomenclature du CIDOC CRM

La partie principale du document est divisée en deux grandes sections : « CIDOC CRM Class Declarations » et « CIDOC CRM Property Declarations ». Dans le CIDOC CRM, les classes sont toujours précédées d’un identifiant débutant par la lettre « E » suivie d’un nombre. Par exemple, la classe « Lieu » est précédée de son identifiant « E53 » : `E53_Lieu`. Il en va de même pour les propriétés, dont l’identifiant commence toujours par la lettre « P » suivie d’un nombre (il y a plus de propriétés que de classes dans le CIDOC CRM). Par exemple, la propriété « a eu lieu dans » est précédée de son identifiant « P7 » : `P7_a_eu_lieu_dans`.

À noter qu’il existe aussi une autre distinction de style entre ces deux catégories d’entités; en français, le premier mot contenu dans le nom d’une classe débute toujours par une majuscule (p. ex. `E10_Transfert_de_la_garde`), alors que les propriétés sont toujours écrites en minuscules dans leur intégralité (p. ex. `P28_a_mis_fin_à_la_garde_par`). Cependant, en anglais (la version originale), la première lettre des mots contenus dans le nom d’une classe (à l’exception de « of » et « or ») est en majuscule (p. ex. `E10_Transfer_of_Custody`). Les propriétés sont pour leur part rédigées intégralement en minuscules (p. ex. `P28_custody_surrendered_by`).

#### Classes

Les classes sont des entités qui permettent de catégoriser un ensemble d’instances en fonction d’une définition commune. Par exemple, la valeur « Montréal » pourrait être considérée comme une instance de la classe `E53_Lieu`. En plus de partager une définition commune, les instances d’une même classe peuvent être liées à d’autres instances via le même ensemble de propriétés.

#### Propriétés {#proprietes}

Les propriétés servent à lier deux instances entre elles. Ces liaisons mettent notamment en lumière la sémantique associée aux données. Par exemple, il est possible d’utiliser la propriété `P122_est_limitrophe_de` entre les valeurs « Montréal » et « Fleuve Saint-Laurent » pour indiquer que ces instances de la classe `E53_Lieu` partagent une frontière géographique commune.

#### Domaine et Portée {#domaine-et-portee}

Les propriétés ne s’appliquent pas automatiquement à toutes les instances. Deux concepts fondamentaux permettent de déterminer quelles propriétés peuvent s’appliquer à quelles instances : le domaine (en anglais *domain*) et la portée (en anglais *range*).

Le domaine indique la classe de l’instance avec laquelle il est possible d’utiliser une propriété. Similairement, la portée indique la classe de l’instance qui sert de point d’arrivée à cette même propriété. Par exemple, la propriété `P122_est_limitrophe_de` a à la fois pour domaine et pour portée la classe `E53_Lieu`, ce qui valide l’exemple précédent puisque les valeurs « Montréal » et le « Fleuve Saint-Laurent » sont toutes les deux des instances associées à `P122_est_limitrophe_de`.

À noter qu’il est possible, et même fréquent, que le domaine et la portée diffèrent. C’est notamment le cas de `P7_a_eu_lieu_dans`, qui a pour domaine `E4_Période` et pour portée `E53_Lieu`.

#### Super-classe/Sous-classe et Super-propriété/Sous-propriété {#super-classesous-classe-et-super-proprietesous-propriete}

Un autre concept important du CIDOC CRM est la hiérarchisation des entités (classes et propriétés). En effet, il est possible d’indiquer qu’une classe est la sous-classe d’une autre classe (cette dernière est alors nommée super-classe). Cette hiérarchisation est très importante, car une sous-classe hérite des propriétés de toutes ses super-classes. Par exemple, il est possible d’appliquer la propriété `P7_a_eu_lieu_dans` à la classe `E12_Production` même si son domaine est la classe `E4_Période`, car la chaîne de sous-classes suivante existe : `E4_Période`, `E5_Évènement`, `E7_Activité`, `E11_Modification` et `E12_Production` (chaque classe listée dans cette énumération est la super-classe de la suivante).

Cette hiérarchisation permet aussi à une personne utilisant le modèle d’identifier le niveau de précision qu’elle devrait préconiser. En choisissant la classe la plus précise possible, une grande variété de propriétés peut être utilisée, ce qui facilite les recherches plus spécifiques au sein d’un corpus.

Les propriétés peuvent aussi être hiérarchisées, ce qui permet d’effectuer des requêtes plus générales en utilisant des super-propriétés plutôt que leurs sous-propriétés, qui ont des notes d’application plus contraignantes. Ceci s’avère utile pour obtenir, grâce à l’usage de la propriété adéquate, le niveau de précision approprié au besoin.

### Cadre conceptuel du CIDOC CRM

Il est possible d’explorer la hiérarchie des classes et des sous-classes en s’appuyant sur les domaines et les portées ainsi que sur les propriétés qui leur sont associées sans pour autant devoir lire l’intégralité du document. Il est néanmoins utile de connaître les principes conceptuels du CIDOC CRM afin d’identifier plus rapidement les entités pertinentes à un travail sans toujours se référer à la classe `E1_Entité_CRM`, qui est très générique.

#### Entités temporelles {#entites-temporelles}

Le CIDOC CRM est structuré autour de la notion d’entité temporelle (`E2_Entité_temporelle`). Ainsi, la modélisation d’une information issue d’un jeu de données nécessite fréquemment l’utilisation d’une sous-classe de `E2_Entité_temporelle`. Par exemple, pour indiquer la date de production d’un objet, il est nécessaire d’associer une date à l'évènement de sa production, et non pas à l’objet produit. C’est pourquoi il est utile de connaître les principales sous-classes de `E2_Entité_temporelle`.

Ces entités temporelles sont dites « perdurantes », car elles évoluent dans le temps, de sorte qu’il est impossible de réduire l’entièreté d’une entité temporelle à un instant *t* (contrairement à une entité « endurante », qui contient toutes ses caractéristiques à un instant *t*). Le CIDOC CRM utilise la classe `E77_Entité_persistante` pour définir les entités endurantes, qui sont principalement des personnes ou des groupes (sous-classes de `E39_Actant`) et des choses (notamment des objets physiques et des concepts).

Certaines entités ne font partie d’aucune de ces deux catégories; c’est notamment le cas des intervalles de temps (p. ex. `E52_Intervalle_temporel`) et des lieux (p. ex. `E53_Lieu`).

#### Classes principales du CIDOC CRM

Afin de faciliter la recherche dans la spécification du CIDOC CRM, certaines classes peuvent être utilisées comme point de départ pour identifier l’entité la plus appropriée à un besoin. Le diagramme suivant met en lumière les classes principales du CIDOC CRM :

Diagramme des classes principales du CIDOC CRM

<iframe frameborder="0" style="width:100%;height:363px;" src="https://viewer.diagrams.net/?tags=%7B%7D&target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=CRM_ClassesPrincipales_2021-11-04.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1u6bnEUFB4WMzagTiurfA-PZgnjmPmrlT%26export%3Ddownload"></iframe>

La classe `E2_Entité_temporelle` et ses sous-classes permettent de lier les personnes ou groupes qui ont participé à un évènement aux objets physiques ou conceptuels utilisés ou créés lors de celui-ci. La durée de cet évènement peut être indiquée en utilisant la classe `E52_Intervalle_temporel` et les lieux où se déroule l’action peuvent être identifiés grâce à la classe `E53_Lieu`.

De manière générale, deux classes essentielles traversent l’entièreté du modèle et sont utiles pour nommer une instance (`E41_Appellation`) ou en préciser la nature (`E55_Type` associée à des vocabulaires externes). 

#### Gestion de la temporalité dans le CIDOC CRM {#gestion-de-la-temporalite-dans-le-cidoc-crm}

La gestion de la temporalité au sein du CIDOC CRM est souvent difficile à comprendre lors d’une première utilisation du modèle. Tout d’abord, il faut savoir que le CIDOC CRM utilise uniquement des *intervalles* pour documenter le passage du temps. Ce principe clé permet de rendre adéquatement compte du flou qui entoure la temporalité d’un évènement. En effet, les données patrimoniales ne représentent qu’une approximation (aussi précise soit-elle) du moment exact où un évènement s’est produit dans le monde qu’elles décrivent. Même en connaissant le moment exact (à la seconde près) où un évènement a débuté, il est presque impossible de déterminer le dixième de seconde où il a eu lieu, et ainsi de suite pour des intervalles toujours plus courts. La période durant laquelle un évènement s’est produit peut également être connue, mais sans plus de précision.

Trois propriétés (illustrées ci-dessous) permettent de documenter l’intervalle de temps durant lequel un évènement s’est produit.

Diagramme de l’intervalle de temps

<iframe frameborder="0" style="width:100%;height:302px;" src="https://viewer.diagrams.net/?tags=%7B%7D&target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=CRM_Temporalite_2021-11-04.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1pALuxT_l-7QJpzfr7XSeJlKGAG22Zoux%26export%3Ddownload"></iframe>

Premièrement, la propriété `P191_a_eu_pour_durée` permet d’indiquer pendant combien de temps l’évènement s’est déroulé : par exemple, l'évènement a duré trois jours.

Deuxièmement, la propriété `P81_a_couvert` — ou ses équivalents fonctionnels et plus précis `P81a_la_fin_du_début` et `P81b_le_début_de_la_fin` — permet d’indiquer le moment lors duquel l’évènement a eu lieu : par exemple, l’évènement a eu lieu le 2 février 2020 (il est possible qu’il ait commencé avant ou qu’il se soit terminé après, mais il est établi que le 2 février 2020, cet évènement était en cours).

Troisièmement, les propriétés `P82a_le_début_du_début` et `P82b_la_fin_de_la_fin` permettent d’indiquer les limites temporelles de la période durant laquelle l’entièreté de l’évènement s’est déroulée. L’utilisation de ces propriétés plus précises substitue celle de `P82_a_eu_lieu_durant` et permet d’indiquer les périodes où il est établi que l’évènement n’avait *pas* lieu. Cette troisième option est la plus courante dans le secteur patrimonial.

À noter que les spécialisations des propriétés `P81_a_couvert` et `P82_a_eu_lieu_durant` (`P81a_la_fin_du_début` et `P81b_le_début_de_la_fin` ainsi que `P82a_le_début_du_début` et `P82b_la_fin_de_la_fin`) ne sont pas recensées dans la spécification actuelle du CIDOC CRM, bien qu’elles soient fréquemment utilisées et recensées dans sa dernière version en RDF.

### Identifier la bonne entité {#identifier-la-bonne-entite}

Il existe plusieurs interfaces de consultation de la spécification du CIDOC CRM. Certaines versions (comme la [version 7.1.1](http://www.cidoc-crm.org/Version/version-7.1.1)) ont été générées en HTML afin que chaque entité puisse être consultée sur une page Web dédiée. On y trouve notamment l’ensemble des propriétés qu’une classe peut mobiliser, y compris celles qui sont associées à ses super-classes. Ceci permet d’identifier aisément les propriétés qui peuvent être utilisées avec une classe donnée.

Cependant, les versions les plus récentes sont disponibles uniquement en format .docx ou .pdf sous la forme de documents de travail (c’est le cas pour la [version 7.2](http://www.cidoc-crm.org/Version/version-7.2)).

Chaque entité est décrite à l’aide d’une série de champs, dont en voici les principaux :

**Pour les classes**

* « Sous-classe de » et « Super-classe de » identifient les classes hiérarchiquement au-dessus ou au-dessous de la classe consultée. Il est possible d’avoir accès à une vue de l’ensemble de la hiérarchie en consultant les pages 48 à 54 du document ([version 7.1.1](http://www.cidoc-crm.org/Version/version-7.1.1)).
* « Note d’application » définit la classe et les instances qui en font partie.
* « Exemples » illustre des instances possibles de la classe.
* « Propriétés » identifie les propriétés immédiatement associées à la classe consultée (c.-à-d. que cette classe en est le domaine). Les propriétés associées aux super-classes d’une classe peuvent aussi être mobilisées par cette dernière même si elles ne sont pas listées dans ce champ. Il en va de même pour les propriétés inverses. Pour avoir un aperçu de l’ensemble des propriétés, de leurs domaines et de leurs portées, il est pertinent de se référer à la [hiérarchie générale](http://www.cidoc-crm.org/Version/version-7.1.1). 

**Pour les propriétés**

* « Domaine » et « Portée » identifient rapidement le domaine et la portée de la propriété consultée.
* « Sous-propriété de » et « Super-propriété de » permettent de naviguer dans la hiérarchie des propriétés.
* « Note d’application » définit la nature du lien entre deux instances.
* « Exemples » illustre des liens possibles entre deux instances.

## Aide-mémoire {#aide-memoire}

* Il n’est pas nécessaire de lire le document dans son intégralité. Jongler avec les sous-classes, les super-classes, les sous-propriétés, les super-propriétés, les domaines et les portées s’avère le moyen le plus efficace de trouver les entités du CIDOC CRM susceptibles de répondre à des besoins d’implémentation précis. 
* La hiérarchie complète des classes et des propriétés peut être consultée dans l’introduction de la spécification du CIDOC CRM. Elle donne un bon aperçu des entités utilisables pour mobiliser ce standard.
* Les propriétés associées à une classe spécifique ne constituent pas nécessairement l’entièreté des propriétés utilisables avec cette classe, de sorte qu’il est nécessaire d’analyser les propriétés de ses super-classes ainsi que les propriétés inverses qui peuvent y être associées.
* Les entités temporelles sont au cœur du CIDOC CRM; il est pertinent de s’y référer fréquemment pour identifier les entités répondant à des besoins d’implémentation précis.
* Finalement, il est possible que le CIDOC CRM ne réponde pas à tous les besoins; l’analyse des extensions existantes ou la création d’une extension locale sont de bonnes manières de répondre à des besoins particuliers.

## Pour plus d’informations

* [Jeu d’apprentissage du CIDOC CRM](http://www.cidoc-crm-game.org/) (en anglais seulement)
* [Tutoriels sur des aspects précis du CIDOC CRM](http://www.cidoc-crm.org/tutorialPageRes) (la plupart en anglais)
* [Site du Groupe de travail canadien pour la traduction du CIDOC CRM](https://chin-rcip.github.io/cidoc_crm_fr-ca/)
* [Vidéo de présentation du CIDOC CRM](http://www.cidoc-crm.org/cidoc-crm-tutorial) (en anglais seulement)

## Bibliographie

Bekiari, Chryssoula, George Bruseker, Martin Doerr, Christian-Emil Ore, Stephen Stead, et Athanasios Velios, éd. *Definition of the CIDOC Conceptual Reference Model*. CIDOC CRM Documentations, 7.1. Paris, FR-IDF: CIDOC CRM Special Interest Group, 2021. [http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf](http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf).

CIDOC CRM. « CRMgeo ». 2021. [http://www.cidoc-crm.org/crmgeo/home-5](http://www.cidoc-crm.org/crmgeo/home-5).

CIDOC CRM Special Interest Group. « Tutorials ». CIDOC CRM. Octobre 2021. [http://www.cidoc-crm.org/tutorialPageRes](http://www.cidoc-crm.org/tutorialPageRes).

FORTH. *CRMgeo: A Spatiotemporal Model: An Extension of CIDOC CRM to Link the CIDOC CRM to GeoSPARQL through a Spatiotemporal Refinement*. GR. 2015. [http://www.cidoc-crm.org/crmgeo/sites/default/files/CRMgeo1_2.pdf](http://www.cidoc-crm.org/crmgeo/sites/default/files/CRMgeo1_2.pdf).

Groupe de travail canadien pour la traduction du CIDOC CRM. « Traduction en français du CIDOC CRM ». Traduction en français du CIDOC CRM. 3 juin 2021. [https://chin-rcip.github.io/cidoc_crm_fr-ca/](https://chin-rcip.github.io/cidoc_crm_fr-ca/).

Guillem, Anaïs, et George Bruseker. « CIDOC CRM Game ». CIDOC CRM Game. 2021 [2017]. [http://www.cidoc-crm-game.org/](http://www.cidoc-crm-game.org/).

Stead, Stephen. « CIDOC CRM Tutorial ». CIDOC CRM. Novembre 2008. [http://www.cidoc-crm.org/cidoc-crm-tutorial](http://www.cidoc-crm.org/cidoc-crm-tutorial).

