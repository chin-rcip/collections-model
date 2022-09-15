---
layout: page
language: fr
title: Spécification du modèle cible
permalink: /fr/modele-cible/actuel/introduction
other_link: /en/target-model/current/introduction
sidebar: mc22
group: spécifications
date: 2022-06-30
description: La Spécification du modèle cible des actants modélise sémantiquement les actants dans un contexte patrimonial. Les patrons conceptuels les plus pertinents pour la vie des actants sont présentés avec des diagrammes et des exemples qui les illustrent, ainsi qu'un compte rendu et une explication des décisions pertinentes qui ont été prises lors de l'élaboration desdits patrons conceptuels. Il s'agit d'une documentation théorique qui n'a jamais été testée ou mise en application.
---

Version 2.2 ([Versions précédentes](/collections-model/fr/versions))

> <span class="disclaimer">AVERTISSEMENT :</span> Cette documentation est une collection de documents théoriques élaborés dans le contexte d'un projet pilote où les tests et la mise en application n'ont jamais eu lieu. En tant que telle, bien qu'elle soit diffusée publiquement en français et en anglais, elle ne constitue pas une publication officielle.

## Dates

Date de création : 2019-05-13

Dernière mise à jour : 2022-06-30

## Résumé {#resume}

La Spécification du modèle cible modélise sémantiquement les actants (personnes et groupes) dans un contexte patrimonial. Les patrons conceptuels les plus pertinents pour la vie des actants sont présentés avec des diagrammes et des exemples qui les illustrent, ainsi qu'un compte rendu et une explication des décisions pertinentes qui ont été prises lors de l'élaboration desdits patrons conceptuels. Il s'agit d'une documentation théorique qui n'a jamais été testée ou mise en application. Les éléments en cours de développement ou de révision sont répertoriés comme [Enjeux](https://github.com/chin-rcip/collections-model/issues).  

## Fonction du modèle cible {#fonction-du-modele-cible}

Conformément à son mandat qui consiste à « appu[yer] les musées canadiens dans leur travail de documentation et de gestion de leurs collections, ainsi que dans la diffusion de l’information sur leurs collections », le Réseau canadien d'information sur le patrimoine (RCIP) a mis sur pied un projet pilote pour déterminer s'il a la capacité de rendre les ressources qu'il crée et les données qu'il agrège disponibles en données ouvertes et liées (DOL) (Réseau canadien d'information sur le patrimoine (RCIP) 2019). L'objectif était de consolider, dans des enregistrements uniques, les informations relatives aux actants. Dans le cadre de ce projet, un actant représente tout individu ou groupe qui a participé à la création ou qui est lié aux artefacts culturels documentés par un soumissionnaire de données. Cela comprend les créateurs·rices (artistes, artisans·es, fabricants·es, groupes d'artistes, etc.) ainsi que d'autres actants importants comme les propriétaires, les mécènes, les personnes représentées, etc., qui ont participé à la création des artefacts ou qui sont liés aux artefacts recueillis par les institutions patrimoniales du Canada.

Ce projet a pour but d'évaluer et, éventuellement, de soutenir le développement d'un futur modèle plus vaste et d'un environnement de sémantisation qui engloberait les enregistrements patrimoniaux de toutes sortes (matériels et immatériels, collections, évènements, etc.). L'accent a d'abord été mis sur la collecte, la normalisation et l'agrégation des données des actants, qui sont variées en termes de structures, de formats, de langues et d'origines. Pour atteindre cet objectif, la réconciliation et la conversion en un [graphe de connaissances](https://fr.wikipedia.org/wiki/Knowledge_Graph) utilisant le [CIDOC CRM](http://www.cidoc-crm.org/) et ses [extensions](https://cidoc-crm.org/collaborations) ont été envisagées. Les étapes importantes prévues étaient :

* La modélisation des informations relatives aux personnes et aux groupes (actants);

* La documentation du modèle et du pipeline de données qui en résulte; 

* La période de tests; 

* La mise en place d'une interface de soumission et d'une interface d'interrogation avec un point terminal SPARQL. 

Bien que la modélisation et la documentation aient eu lieu et soient présentées ici, les procédures subséquentes nécessaires aux tests, à la mise en application et à la réalisation n'ont pas été accomplies. Il est donc particulièrement important de prendre en considération que cette documentation est purement théorique et que le modèle qu'elle décrit n'a été ni testé ni mis en application. Les personnes souhaitant le réutiliser doivent donc s'assurer de son applicabilité par une sélection approfondie de vocabulaires contrôlés (pour chaque nœud contenant des instances de `E55_Type`), de tests de modèles et de phases de mise en application. 

Pour le moment, il n'est pas prévu de gérer les données ou de les utiliser ultérieurement sur la base de la Spécification du modèle cible. Cela s'explique en partie par le fait que la Spécification du modèle cible est destinée à être un profil d'application potentiel élaboré et révisé sur une base évolutive et continue, sans que le déploiement ou la fin de la phase de théorisation ne soient prévus. Actuellement, l'accent est plutôt mis sur le développement de contenus supplémentaires basés en fonction de l'examen des patrons conceptuels existants d'autres projets, afin de les améliorer pour la documentation de la Spécification du modèle cible.

En outre, il est important de considérer qu'il n'y a pas de système intégré dans la conception des patrons conceptuels de la Spécification du modèle cible qui évalue la véracité ou la valeur des données de contenu. L'autorité sur les données est plutôt celle du propriétaire et doit être documentée à l'aide du patron conceptuel [Provenance du jeu de données](/collections-model/fr/modele-cible/actuel/provenance-du-jeu-de-donnees). 

## Choix d'une ontologie

Comme il s’agit d’un projet pilote, le choix d'un sous-ensemble limité de données à modéliser s'est imposé afin d'évaluer la faisabilité d'un environnement de sémantisation à plus grande échelle. Le RCIP a choisi de travailler d'abord avec les patrons conceptuels des actants, sachant qu'il existe peu de jeux de données patrimoniales axés sur les personnes et les groupes (par opposition aux artefacts). En effet, les informations sur les actants constituent un ensemble autonome et significatif (c.-à-d. que les informations sur les personnes et les groupes sont compréhensibles et significatives même si les objets auxquels ceux-ci sont liés ne sont pas modélisés de manière exhaustive). Ainsi, toutes les informations sur les actants ne peuvent pas être représentées à l'aide de ce modèle, et des institutions spécifiques peuvent documenter des aspects ciblés ou de niche de la vie ou de l'objet d'un actant, des aspects qui ne concernent qu'eux (p. ex. un musée consacré aux pompiers pourrait documenter le niveau de formation en premiers soins qu'un actant a reçu). Ces informations précises n'ont pas été modélisées ici afin d'éviter toute complexité inutile (car de nombreuses institutions de collectionnement ont des besoins individuels qui ne sont pas partagés par leurs homologues; pour une discussion détaillée sur ce sujet, voir l'[Enjeu no 19](https://github.com/chin-rcip/collections-model/issues/19)). 

L'ontologie sur laquelle reposent ces patrons conceptuels a été sélectionnée sur la base de critères plus larges touchant l'entièreté d'un modèle potentiel qui engloberait les données patrimoniales en général. Trois critères principaux ont été pris en compte : 

* L'adoption par la communauté sémantique patrimoniale afin de favoriser l'interopérabilité;

* La richesse et la durabilité de l'ontologie;

* La représentation adéquate des données institutionnelles qui sont largement axées sur les objets plutôt que sur les personnes.

Dans ce contexte, le RCIP a choisi de travailler avec l'ontologie du [CIDOC CRM](http://www.cidoc-crm.org/versions-of-the-cidoc-crm). Parce qu'elle a été développée par le [Conseil international des musées](https://icom.museum/fr/) (ICOM) pour les institutions du patrimoine en tenant compte de leurs besoins, elle est de loin la plus utilisée dans ce domaine. Pour cette raison et parce qu'elle est sous la responsabilité de l'ICOM par l’entremise de son Groupe d'intérêt spécial ou Special Interest Group (CRM SIG) qui lui est consacré ([CIDOC Conceptual Reference Model Special Interest Group](http://network.icom.museum/cidoc/working-groups/crm-special-interest-group/)), l'ontologie du CIDOC CRM semble être un choix durable. Elle est régulièrement mise à jour et adaptée aux besoins de la communauté patrimoniale, offrant ainsi un cadre de travail riche et précis. Enfin, en tant qu'ontologie basée sur les évènements, elle est adaptée à la représentation des informations relatives aux actants et aux objets, car elle peut relier des instances de ces deux types d'information par le biais d'instances d'évènements qui peuvent être situés dans le temps et l'espace.

L'inconvénient de ce choix est que le CIDOC CRM est fortement axé sur l'histoire enregistrée des objets. Les relations sociales sont parmi les éléments les plus difficiles à représenter en raison de leur complexité et des multiples compréhensions d'un même évènement qu'elles véhiculent. 

## Conventions de diagramme

Les patrons conceptuels sont des descriptions conceptuelles des connaissances de base relatives à un élément précis du patrimoine (p. ex. comment représenter le fait qu'une personne a utilisé une technique précise pour créer un objet). Afin de comprendre plus facilement les patrons conceptuels, des diagrammes sont souvent utilisés. Dans la Spécification du modèle cible, deux types de diagrammes sont présentés : 

* Les diagrammes ontologiques sont des représentations du modèle de données supportant le graphe de connaissances; 

* Les diagrammes des instances illustrent des exemples comme moyen de représenter un graphe de connaissances (données modélisées selon le modèle de données).

Si le modèle devait être mis en application, des libellés pourraient être liés à toute instance du graphe de connaissances, mais ils ne seraient pas affichés dans les diagrammes pour en faciliter la lecture. De plus, pour simplifier la compréhension, les deux types de diagrammes partagent des conventions de couleur et de style typiquement utilisées par le CIDOC CRM et suggérées par George Bruseker, chef de la direction de Takin.Solutions. L'utilisation de ces conventions par le modèle DOPHEDA est décrite ci-dessous. 

### Diagrammes ontologiques

Par souci de clarté et de visibilité, les instances ont été omises dans les diagrammes ontologiques pour que l'accent soit mis sur la représentation des relations entre les classes, même si, dans le graphe de connaissances, ce sont les instances qui sont liées entre elles par des propriétés et non les classes elles-mêmes (ce que les diagrammes ontologiques pourraient suggérer). 

Les classes sont représentées par des boîtes dans lesquelles est inscrit le nom de la classe, tandis que les propriétés sont représentées par des flèches allant du domaine à la portée, avec leur nom écrit sur la flèche, comme le montre le schéma ci-dessous :

<a name="001_Convention_ClassesEtProprietes_p"></a>001_Convention_ClassesEtProprietes_p

<iframe frameborder="0" style="width:100%;height:200px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=001_Convention_ClassesEtProprietes_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1-Yew3eSFoNIOyUh-u6lj-bDJ2asAKzka%26export%3Ddownload"></iframe>

Par exemple, le diagramme ci-dessous montre que toute instance de la classe `E21_Personne` peut être liée à une instance de la classe `E55_Type` par la propriété `P2_a_pour_type` :

<a name="002_Convention_ClassesEtProprietesExemple_p"></a>002_Convention_ClassesEtProprietesExemple_p

<iframe frameborder="0" style="width:100%;height:200px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=002_Convention_ClassesEtProprietesExemple_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1zQBsBLAjNoUkgLNLfKmksvs6-V7q7OjI%26export%3Ddownload"></iframe>

Dans certains cas, une même instance peut être définie par deux classes (p. ex. les noms d'actants qui sont des instances à la fois de `E33_Objet_linguistique` et de `E41_Appellation`); il s'agit d'une double instanciation. Ceci est illustré de manière schématique avec deux classes différentes indiquées dans une seule boîte (p. ex. `E33_Objet_linguistique` et `E41_Appellation` sont indiquées dans la case).

Pour faciliter la compréhension et transmettre visuellement la manière dont les entités du CIDOC CRM sont utilisées pour modéliser différents types d'informations, les conventions de couleurs ci-dessous ont été adoptées pour représenter les classes de premier niveau ainsi que leurs sous-classes. Les instances attendues de `rdfs:Literal` sont également représentées dans les diagrammes ontologiques sous la forme d'une boîte blanche contenant le type de données attendu (c.-à-d. `xsd:string` ou `xsd:dateTime`). 

<a name="003_Convention_Couleurs_p"></a>003_Convention_Couleurs_p

<iframe frameborder="0" style="width:100%;height:300px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=003_Convention_Couleurs_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1qIZVkbD99a8uuNiUM-iNT1E-9xhfTVry%26export%3Ddownload"></iframe>

Toutes les données fournies doivent être soumises sous forme de valeurs par le biais de [nœuds de saisie](/collections-model/fr/specification-des-chemins-semantiques/actuel/introduction#noeuds-de-saisie) définis dans la [Spécification des chemins sémantiques](/collections-model/fr/specification-des-chemins-semantiques/actuel/introduction). Le nom du nœud de saisie est indiqué en gras au-dessus du nom de la classe ou du type de données qui lui est associé, comme illustré ci-dessous :

<a name="004_Convention_Champ_p"></a>004_Convention_Champ_p

<iframe frameborder="0" style="width:100%;height:400px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=004_Convention_Champ_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1U_RDlk_O5NhjVcG_gnyE5sCPfr40Hh1Q%26export%3Ddownload"></iframe>

Dans le diagramme ci-dessus, le style en gras indique les nœuds de saisie [Lieu de naissance](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#lieu-de-naissance), [Date de début de la naissance](collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-de-la-naissance) et [Date de fin de la naisssance](collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-de-la-naissance). En plus de faciliter la compréhension, cela illustre comment la sémantisation des données d'entrée génère plusieurs nouveaux éléments tels que `E67_Naissance` et `E52_Intervalle_temporel`.

Parfois, un `E55_Type` dans un patron conceptuel précis n'est destiné qu'à accueillir une instance fixe. Ces nœuds dotés d’un qualifiant spécifié sont nommés entre guillemets sous le nom de la classe, comme dans l'exemple suivant :

<a name="005_Convention_Metatype_FRA_p"></a>005_Convention_Metatype_FRA_p

<iframe frameborder="0" style="width:100%;height:200px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=005_Convention_Metatype_FRA_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1q76DXcB4ueXsZ3E_hGTy320oHp3t4u41%26export%3Ddownload"></iframe>

Le diagramme ci-dessus représente le patron conceptuel Technique utilisée : l'élément du milieu correspond au nœud de saisie [Type de technique utilisée](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#type-de-technique-utilisee) (en gras), qui enregistre la technique utilisée par l'actant (p. ex. aquarelle, travail du bois, etc.). Cette information est ensuite désignée comme se rapportant à des techniques par un autre `E55_Type` qui a toujours la valeur « Technique utilisée ». Par exemple, il est indiqué que Yousuf Karsh a utilisé la technique « Épreuve argentique à la gélatine » et cette information est désignée comme étant du type « Technique utilisée ».

### Diagrammes d'instance

Chaque exemple est illustré par une description textuelle du cas d'usage suivie d'un diagramme d'instance (généré à l'aide de l'outil [CRITERIA](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/mode-demploi/criteria) du RCIP), ainsi que d'expressions JSON-LD et Turtle. 

Les diagrammes d'instance sont des représentations visuelles du graphe de connaissances : les instances, en plus des classes et des propriétés, y sont illustrées. Les classes et les propriétés suivent les mêmes conventions que pour les diagrammes ontologiques. Les instances sont documentées dans une forme oblongue en utilisant la couleur de leur classe associée à une saturation faible (c.-à-d. plus pâle). Les exemples de données des instances sont illustrés dans une forme oblongue avec un URI ou des valeurs littérales entre guillemets, comme indiqué ci-dessous :

<div id="0001_100_technique-used-inst-diagram" class="example"></div>

Dans ce diagramme, les instances (Yousuf Karsh, Épreuve argentique à la gélatine, Technique utilisée) sont liées entre elles par des propriétés conformément à la structure du patron conceptuel Technique utilisée correspondant qui se trouve dans la Spécification du modèle cible.

## Diagramme A-Z

Un aperçu ontologique de l'entièreté des patrons conceptuels développés est également disponible. 

* Chaque patron conceptuel est entouré d'une bulle à points bleus, dont le titre mène à la section correspondante dans la Spécification du modèle cible à l'aide d'un clic;

* Chaque classe recevant le nœud de saisie (avec le nom du nœud de saisie en gras dans sa boîte) mène au nœud correspondant dans la [Spécification des chemins sémantiques](/collections-model/fr/specification-des-chemins-semantiques/actuel/introduction) à l'aide d'un clic. 

<a name="000_Patrons_Conceptuels_2.2_p"></a>000_Patrons_Conceptuels_2.2_p

<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=000_Patrons_Conceptuels_2.2_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1UzXw9jJZxG1Evf-PO9qNx_JtszfXrW2X%26export%3Ddownload"></iframe>

## Bibliographie

Réseau canadien d'information sur le patrimoine (RCIP). 2019. « Réseau canadien d'information sur le patrimoine ». Governmental. Government of Canada Website. 23 octobre 2019.. [https://www.canada.ca/fr/reseau-information-patrimoine.html](https://www.canada.ca/fr/reseau-information-patrimoine.html).

