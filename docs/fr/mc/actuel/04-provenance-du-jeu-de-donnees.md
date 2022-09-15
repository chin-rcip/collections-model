---
layout: page
language: fr
title: Provenance du jeu de données
permalink: /fr/modele-cible/actuel/provenance-du-jeu-de-donnees
other_link: /en/target-model/current/dataset-provenance
sidebar: mc22
date: 2022-06-30
description: La Spécification du modèle cible des actants modélise sémantiquement les actants dans un contexte patrimonial. Les patrons conceptuels les plus pertinents pour la vie des actants sont présentés avec des diagrammes et des exemples qui les illustrent, ainsi qu'un compte rendu et une explication des décisions pertinentes qui ont été prises lors de l'élaboration desdits patrons conceptuels. Il s'agit d'une documentation théorique qui n'a jamais été testée ou mise en application.
---

## Aperçu {#apercu}

Ce patron conceptuel peut être utilisé pour représenter les informations relatives à la soumission d'un jeu de données par une organisation ou une personne responsable de sa création, de sa soumission et/ou de sa mise à jour. Il comprend :

* L'appellation du soumissionnaire du jeu de données;
* La ou les dates de soumission du jeu de données (y compris les mises à jour).

Il concerne spécifiquement la soumission des jeux de données et non leur contenu ou les documents qu'ils contiennent. En tant que tel, ce patron conceptuel ne doit pas être utilisé pour enregistrer : 

* La provenance d'un artefact;
* L'emplacement où les données originales sont hébergées; 
* Ce qui constituait à l'origine l'enregistrement dans lequel se trouve une information; 
* D'où proviennent ces enregistrements. 

## Introduction et contexte

### Historique théorique {#historique-theorique}

Les graphes nommés, en tant qu'ensembles d’énoncés fédérés sous un seul URI, permettent la description d'un jeu de données. Ils peuvent être appliqués à différents niveaux d'un jeu de données pour le structurer et sont utiles pour documenter la provenance (Semantic Web Interest Group 2019). C'est particulièrement le cas dans un contexte d'agrégation tel que celui de DOPHEDA, dont le but est de soutenir l'agrégation, dans un seul graphe de connaissances, de données provenant d'institutions patrimoniales du Canada ainsi que d'autres sources pertinentes qui pourraient influencer ou éclairer ces jeux de données fondamentaux. 

### Énoncé des besoins {#enonce-des-besoins}

Cet objectif est directement touché par un ensemble d'éléments qui caractérisent le milieu patrimonial : 

* Le contexte dont les jeux de données émanent ou dans lequel ils sont présentés est crucial pour leur compréhension. Ce contexte est souvent significatif en soi pour les personnes qui s'intéressent à l'historicité des informations culturelles (c.-à-d. qui dit quoi, dans quelles circonstances ou dans quel environnement, et à quelle époque);
* Les informations sur un même artefact peuvent être détenues par plusieurs soumissionnaires qui peuvent ne pas l'interpréter de la même manière et fournir des informations complémentaires ou contradictoires à son sujet (le domaine du patrimoine valorise et encourage généralement une multiplicité de points de vue et de compréhensions de ses artefacts);
* Les soumissionnaires de données peuvent avoir différents profils, certains étant des « propriétaires » de données (p. ex. un musée soumettant le jeu de données sur ses collections) et d'autres étant des « collecteurs·rices » de données qui sélectionnent des données spécifiques auprès des propriétaires de données pour créer de nouveaux jeux de données axés sur des aspects ou des thèmes particuliers (p. ex. des chercheurs·euses, des agrégateurs);
* Les soumissionnaires de données souhaitent généralement conserver l'autorité sur leurs données et leur intégrité lorsqu'ils contribuent à des graphes de connaissances agrégés plus vastes; de même, l'évaluation de la véracité ou de la valeur des données de contenu ne fait pas partie des objectifs du projet DOPHEDA. 

Pour ces raisons, le fait d'intégrer seulement les dernières versions des jeux de données dans le graphe de connaissances DOPHEDA ne tiendrait pas compte de l'historicité et des caractéristiques contextuelles de ces jeux de données et, de ce fait, priverait les personnes de données pertinentes et d'accords et/ou de désaccords factuels à leur sujet lors de l'évaluation des informations qu'elles consultent. Il est donc nécessaire d'enregistrer qui a créé quoi et quand, à savoir la personne ou l'organisation qui a soumi ou mis à jour (qui) le jeu de données (quoi) et le moment lors duquel elle l'a fait (quand). C'est ce qu'on appelle la Provenance du jeu de données dans la Spécification du modèle cible.

## Description du patron conceptuel

Un graphe nommé est appliqué au niveau du jeu de données, ce qui permet de traiter ledit jeu de données comme une instance unique de `D1_Objet_numérique` afin que les informations relatives à la soumission de l'objet numérique (p. ex. l'auteur·e, la date) puissent y être ajoutées. Ce graphe nommé est une instance de `D1_Objet_numérique` liée à une instance de `E65_Création` par la propriété `P94_a_créé`. Cette même instance de `E65_Création` est liée au soumissionnaire (une instance de `E39_Actant`) par une instance de `PC14_a_été_effectué_par` dont le domaine est indiqué par le biais de la propriété `P01_a_pour_domaine` liée à l'instance de `E65_Création`, et dont la portée est indiquée par le biais de la propriété `P02_a_pour_portée` liée à l'instance de `E39_Actant`. 

Cette instance de `E39_Actant` est également liée par la propriété `P1_est_identifié_par` à une instance de `E41_Appellation` et de `E33_Objet_linguistique` qui, à son tour, est liée à la valeur littérale de l’[Appellation de l'actant participant à la création du jeu de données](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-de-lactant-participant-a-la-creation-du-jeu-de-donnees) par la propriété `P190_a_pour_contenu_symbolique`. Le rôle du soumissionnaire est indiqué en liant l'instance de `PC14_a_été_effectué_par` à la valeur du [Rôle de l'actant participant à la création du jeu de données](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#role-de-lactant-participant-a-la-creation-du-jeu-de-donnees) (une instance de `E55_Type`) par le biais de la propriété `P14.1_dans_le_rôle_de`.

Le moment lors duquel la soumission a été effectuée est indiqué à l'aide du patron conceptuel [Limites temporelles](/collections-model/fr/modele-cible/actuel/limites-temporelles) lié à l'instance de `E65_Création` par le biais de la propriété `P4_a_pour_intervalle_temporel` avec des valeurs extraites des nœuds de saisie [Date de début de la création du jeu de données](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-de-la-creation-du-jeu-de-donnees) et [Date de fin de la création du jeu de données](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-de-la-creation-du-jeu-de-donnees).

## Diagramme

<a name="014_PatronConceptuel_ProvenanceDuJeuDeDonnees_p"></a>014_PatronConceptuel_ProvenanceDuJeuDeDonnees_p

<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=014_PatronConceptuel_ProvenanceDuJeuDeDonnees_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1XxVuQd2Xdyosk2ikoM7czfWaKzf2m8Uu%26export%3Ddownload"></iframe>

## Exemples

Le Musée des beaux-arts du Canada (`P190_a_pour_contenu_symbolique`, Appellation de l'actant participant à la création du jeu de données) aurait pu soumettre un jeu de données (`P14.1_dans_le_rôle_de`, Rôle de l'actant participant à la création du jeu de données « Soumissionnaire ») qui aurait été cartographié avec la Spécification du modèle cible de DOPHEDA (`P14.1_dans_le_rôle_de`, Rôle de l'actant participant à la création du jeu de données « Créateur ») par le RCIP (`P190_a_pour_contenu_symbolique`, Appellation de l'actant participant à la création du jeu de données) le 15 janvier 2021 (`P82a_le_début_du_début`, Date de début de la création du jeu de données; `P82b_la_fin_de_la_fin`, Date de fin de la création du jeu de données). Ceci serait illustré comme suit : le MBAC est le soumissionnaire de données (c.-à-d. qu'il a autorité sur le contenu et la propriété du jeu de données) et le RCIP est le créateur (c.-à-d. qu'il est chargé de cartographier le jeu de données d'entrée avec le modèle) :

<div id="0001_3_dataset-prov" class="example"></div>

Ces graphes nommés peuvent être exprimés sous la forme de diverses syntaxes, telles que [NQuads](https://www.w3.org/2009/07/NamedGraph.html#syntax-1), [TRiG](https://www.w3.org/2009/07/NamedGraph.html#syntax-1) ou [JSON-LD](https://www.w3.org/TR/json-ld11/#named-graphs). Voici un exemple au format JSON-LD : 

```

{

  "@context": {

    "rdf": "http://www.w3.org/1999/02/22-rdf-syntax-ns#",

    "rdfs" : "http://www.w3.org/2000/01/rdf-schema#",

    "xsd" : "http://www.w3.org/2001/XMLSchema#",

    "crm" : "http://www.cidoc-crm.org/cidoc-crm/",

    "crmdig" : "http://www.ics.forth.gr/isl/CRMext/CRMdig.rdfs/",

    "frbroo" : "http://iflastandards.info/ns/fr/frbr/frbroo/"

  },

  "@id" : "https://www.dopheda.info/d1/001_1234",

  "@type" : "crmdig:D1_Digital_Object",

  "crm:P94i_was_created_by" : {

            "@id" : "https://www.dopheda.info/e65/001_5678",

            "@type" : "crm:E65_Creation",

            "crm:P4_has_time-span": {

                      "@id" : "https://www.dopheda.info/e52/001_9101",

                      "@type" : "crm:E52_Time-Span",

                       "crm:P82a_begin_of_the_begin" : {

                                "@value" : "1665-04-24T00:00:00",

                                "@type" : "xsd:dateTime"

                      },

                      "crm:P82b_end_of_the_end" : {

                              "@value" : "1665-04-24T23:59:59",

                              "@type" : "xsd:dateTime"

                    }

            }

  },

  "@graph" : [

    {

              "@id" : "https://www.dopheda.info/e39/001_9999",

              "@type" : "crm:E21_Person" }

          ]

}





```

Pour récupérer les données de provenance, une clause `GRAPH` doit être incluse dans la requête SPARQL (SPARQL Working Group 2013).

## Documentation connexe

### Modèles externes {#modeles-externes}

* Nomisma.org : [VoID RDF](http://nomisma.org/documentation/contribute)

### Nœuds de saisie {#noeuds-de-saisie}

* [Appellation de l'actant participant à la création du jeu de données](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-de-lactant-participant-a-la-creation-du-jeu-de-donnees) \| Liste de vérification
* [Date de début de la création du jeu de données](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-de-la-creation-du-jeu-de-donnees) \| Liste de vérification
* [Date de fin de la création du jeu de données](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-de-la-creation-du-jeu-de-donnees) \| Liste de vérification
* [Rôle de l'actant participant à la création du jeu de données](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#role-de-lactant-participant-a-la-creation-du-jeu-de-donnees) \| Liste de vérification

### Entités du CIDOC CRM {#entites-du-cidoc-crm}

* `D1_Objet_numérique`
* `E33_Objet_linguistique` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E33)]
* `E39_Actant` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E39)]
* `E41_Appellation` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E41)]
* `E52_Intervalle_temporel` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E52)]
* `E55_Type` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E55)]
* `E65_Création` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E65)]
* `PC14_a_été_effectué_par`
* `P01_a_pour_domaine (est_le_domaine_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P01)]
* `P02_a_pour_portée (est_la_portée_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P02)]
* `P1_est_identifié_par (identifie)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P1)]
* `P4_a_pour_intervalle_temporel (est_l’intervalle_temporel_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P4)]
* `P14.1_dans_le_rôle_de` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P14.1)]
* `P82a_le_début_du_début`
* `P82b_la_fin_de_la_fin`
* `P94_a_créé (a_été_créé_par)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P94)]
* `P190_a_pour_contenu_symbolique` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P190)]

## Discussion

### Justification

Il existe deux approches principales pour documenter les informations de provenance : 

* Ajouter un patron conceptuel de provenance centré sur l'utilisation d'une instance de `E13_Assignation_d'attribut` à chaque triplet; 
* Utiliser un graphe nommé appliqué soit sur l'enregistrement du soumissionnaire, soit sur son jeu de données. 

L'utilisation de la classe `E13_Assignation_d'attribut` dans le graphe de connaissances a l'avantage d'augmenter la précision lors de l'établissement des informations de provenance. Cependant, cela alourdit considérablement le modèle en général, car chaque triplet doit être affecté à ce patron conceptuel. Cela n'empêche pas que lorsque des énoncés multiples et contradictoires sont faits sur une ressource, des instances diverses et distinctes de `E13_Assignation_d'attribut` doivent être créées et liées à leur énoncé respectif. Du point de vue du traitement, cela deviendrait de plus en plus lourd, car la quantité de données augmenterait de façon exponentielle. C'est pourquoi cette approche n'est pas adoptée par le RCIP dans l'environnement DOPHEDA. 

Considérant que chaque triplet du graphe nommé hérite des informations du graphe, le choix de l'ensemble auquel l'appliquer (enregistrement ou jeu de données) est débattable. Ce point est particulièrement important, car il a un impact direct sur la granularité des informations de provenance qu'une structure de jeu de données permet. Le graphe nommé d'un soumissionnaire basé sur un jeu de données peut être préférable pour la documentation des données de provenance et la gestion des informations, mais un graphe nommé plus granulaire basé sur un enregistrement pourrait être préférable d'un point de vue technique.

Pour déterminer quelle approche est préférable, un sondage sur la mise en application des graphes nommés auprès de la communauté du CIDOC CRM et un [rapport technique](https://chin-rcip.github.io/collections-model/fr/rapports-techniques/actuel/rapport-denquete-des-graphes-nommes-1) sur le sujet ont été réalisés. Sur la base des résultats et des discussions avec le comité sémantique du RCIP, la décision de mettre en application des graphes nommés au niveau du jeu de données a été prise. Les éléments suivants ont fortement influencé cette décision :

* Il s'agit de la pratique la plus courante, du moins au sein de la communauté du CIDOC CRM;
* Elle comporte une barrière technologique moins importante qu'une approche fondée sur les enregistrements, car tous les logiciels et processus disponibles ne sont pas en mesure de prendre en charge une structure plus granulaire au niveau des enregistrements;
* Cette décision permet d'éviter le problème des entités limitrophes (c.-à-d. les nœuds de saisie partagés par plusieurs entités, comme les nœuds de saisie liés à la [naissance](/collections-model/fr/modele-cible/actuel/naissance-et-mort-dune-personne) qui sont partagés par un actant et ses parents) car, comme toutes les entités d'un soumissionnaire sont placées dans un graphe nommé unique et partagé, les informations sont appliquées uniformément;
* Bien qu'il y ait des préoccupations quant à la possibilité d'informations manquantes qui pourraient ne pas être incluses dans une requête, l'intégralité des données soumises est cartographiée avec le modèle cible, de sorte qu'il n'est pas compliqué de définir une requête SPARQL récupérant les données d'une seule entité (c.-à-d. tous les triplets relatifs à cette entité, principalement un actant ou un objet).

Le graphe nommé est modélisé comme une instance de `D1_Objet_numérique` car, en tant que sous-classe de `E73_Objet_informationnel`, c'est l'entité la plus précise qui puisse être utilisée. De plus, parce qu'elle fait partie de l'extension [CIDOC CRM Model for the Provenance of Metadata](http://www.cidoc-crm.org/crmdig/) (CRMdig) dédiée à la représentation des contenus numériques, `D1_Objet_numérique` est destinée à être utilisée avec plusieurs propriétés dédiées. Cependant, elles ne peuvent pas être utilisées conjointement avec la classe `E73_Objet_informationnel`, qui est moins expressive. Même s'il n'est pas nécessaire d'utiliser ces propriétés dédiées pour le moment, il est probable que le besoin se fera ressentir dans le futur et, à ce titre, l'utilisation de `D1_Objet_numérique` est la plus durable.  

### Limitations

Chaque triplet au sein d'un graphe nommé hérite des informations ajoutées à ce graphe. Des sous-ensembles (p. ex. des triplets ciblés) peuvent faire l'objet d'une requête en utilisant des identifiants de graphes (Dodds et Davis 2019, 53). Comme la provenance est gérée au niveau du jeu de données, la même information de provenance est appliquée à chaque triplet du graphe. Pour exprimer de l'information complexe relative à une entité précise (p. ex. indiquer que l'attribution d'une date est incertaine), il faut utiliser un autre patron conceptuel, soit :

* Le patron conceptuel [Provenance de l’enregistrement](/collections-model/fr/modele-cible/actuel/provenance-de-lenregistrement) permet d'indiquer la provenance d'un enregistrement prédéterminé; 
* Le patron conceptuel [Note curatoriale](/collections-model/fr/modele-cible/actuel/note-curatoriale) permet d'indiquer la provenance d'un triplet précis, ce qui constitue une utilisation inhabituelle, mais acceptable du champ.

Cependant, ces options s'appliquent à une entité spécifique et jamais à un groupe d'entités ou de triplets. Cela implique que la provenance de tout énoncé complexe modélisé avec des triplets multiples ne puisse pas être documentée.

### Enjeux connexes sur GitHub

* [Enjeu n° 14 « Nous devons gérer les mises à jour des enregistrements (et des graphes nommés?) »](https://github.com/chin-rcip/collections-model/issues/14) (en anglais)
* [Enjeu n° 34 « Les catalogueurs doivent-ils être documentés dans le patron conceptuel Enregistrement? »](https://github.com/chin-rcip/collections-model/issues/34) (en anglais)
* [Enjeu n° 45 « Graphes nommés : Enregistrement vs Jeu de données »](https://github.com/chin-rcip/collections-model/issues/45) (en anglais)

### Cas limites

Dans le cas où un soumissionnaire unique envoie plusieurs fichiers distincts de son jeu de données (p. ex. un pour les groupes et un pour les personnes), il est possible de créer un graphe nommé pour chaque fichier ou de les réunir en un seul graphe nommé. La première option fournit une description plus granulaire des données du soumissionnaire, surtout si les fichiers contiennent des informations de provenance différentes (telles que les dates de création et/ou de mise à jour). La deuxième option permet de simplifier la gestion des graphes nommés en réduisant le nombre de graphes nommés.

Par conséquent, le choix entre documenter la soumission de nouvelles données sur une entité spécifique en tant que nouveau graphe nommé ou en tant qu'information supplémentaire sur la provenance de l'enregistrement peut devenir difficile à faire en fonction de la gouvernance de l'écosystème en place. Comme autre exemple, dans un contexte où un musée offre une plateforme de sociofinancement pour enrichir ses contenus et où un·e expert·e indépendant·e contribue à un enregistrement, le soumissionnaire de données pourrait inclure la provenance de cette information dans le patron conceptuel Provenance de l’enregistrement, mais pourrait aussi préférer que les données externes soient gérées dans un graphe nommé différent. Ainsi, il pourrait y avoir un graphe nommé qui ne représente que les informations soumises par l'expert·e externe.

## Bibliographie

Bruseker, George, et Nicola Carboni. « Digital Object Reference Data Model (SARI Documentation) ». *Swiss Art Research Infrastructure*. 8 décembre 2020. [https://docs.swissartresearch.net/et/do/#existence](https://docs.swissartresearch.net/et/do/#existence).

Bruseker, George, Trang Dang, Philippe Michon et Stephen Hart. *Rapport d'enquête sur l'utilisation des graphes nommés du patrimoine culturel (partie 1)*. Rapports techniques DOPHEDA. Ottawa, CA-ON : Réseau canadien d'information sur le patrimoine (RCIP), 2020. [https://chin-rcip.github.io/collections-model/fr/rapports-techniques/actuel/rapport-denquete-des-graphes-nommes-1](https://chin-rcip.github.io/collections-model/fr/rapports-techniques/actuel/rapport-denquete-des-graphes-nommes-1).

Dodds, Leigh, et Ian Davis, éds. « Named Graph ». *Linked Data Patterns: A Pattern Catalogue for Modelling, Publishing, and Consuming Linked Data*. 2019 : 53-54. [https://patterns.dataincubator.org/book/named-graphs.html](https://patterns.dataincubator.org/book/named-graphs.html).

Doerr, Martin. « A Digital Provenance Ontology ». Didacticiel présenté à la *International Conference on Theory and Practice of Digital Libraries*. Berlin, DE-BE, 25 septembre 2011. [http://www.cidoc-crm.org/Resources/a-digital-provenance-ontology-0](http://www.cidoc-crm.org/Resources/a-digital-provenance-ontology-0).

Doerr, Martin, et Christian Emil Ore, éds. *Definition of the CIDOC Conceptual Reference Model*. Documentations du CIDOC CRM, 7.0.1. Paris, FR-IDF : Conseil international des musées (ICOM), 2020. [http://www.cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.0.1_%2018-10-2020.pdf](http://www.cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.0.1_%2018-10-2020.pdf).

Doerr, Martin, Stephen Stead, et Maria Theodoridou. *Definition of the CRMdig: An Extension of CIDOC-CRM to Support Provenance Metadata*. CRMdig, 3.2.1. Heraklion, GR-CR : CIDOC CRM, 2016. [http://www.cidoc-crm.org/crmdig/ModelVersion/version-3.2.1](http://www.cidoc-crm.org/crmdig/ModelVersion/version-3.2.1).

Semantic Web Interest Group. « Named Graphs ». *W3*. 27 septembre 2019. [https://www.w3.org/2004/03/trix/](https://www.w3.org/2004/03/trix/).

SPARQL Working Group. « SPARQL 1.1 Query Language ». Recommandation du W3C. 21 mars 2013. [https://www.w3.org/TR/sparql11-query/](https://www.w3.org/TR/sparql11-query/).

