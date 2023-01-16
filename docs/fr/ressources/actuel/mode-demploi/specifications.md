---
layout: page
language: fr
title: Mode d'emploi - Spécifications du modèle cible et des chemins sémantiques
permalink: /fr/ressources/actuel/mode-demploi/specifications
other_link: /en/resources/current/how-to/specifications
sidebar: specs
group: ressources
subgroup: mode d'emploi
date: 2023-01-12
description: Ce document explique comment utiliser les spécifications du modèle cible et des chemins sémantiques individuellement ou conjointement de manière à élaborer un nouveau modèle de données ou de structurer des données de manière alignée avec la documentation DOPHEDA du RCIP, de réaliser un processus de mise en correspondance ou d'effectuer des requêtes SPARQL pertinentes.
---

**Version** : 1.0

**Auteurs** : Marie-Pier Blain, Karine Léonard Brouillet, Trang Dang, Stephen Hart, Philippe Michon

**Date de création** : 2022-09-20

**Dernière mise à jour** : 2023-01-12

**Résumé** : Ce document explique comment utiliser les spécifications du modèle cible et des chemins sémantiques individuellement ou conjointement de manière à élaborer un nouveau modèle de données ou de structurer des données de manière alignée avec la documentation DOPHEDA du RCIP, de réaliser un processus de mise en correspondance ou d'effectuer des requêtes SPARQL pertinentes.

**Pour information** : Pour toute question ou commentaire concernant le Mode d'emploi : Spécifications du modèle cible et des chemins sémantiques, veuillez consulter la section [Enjeux](https://github.com/chin-rcip/collections-model/issues) (et ouvrir un Enjeux si c’est pertinent) ou nous contacter par courriel à l'adresse [rcip-chin@pch.gc.ca](mailto:rcip-chin@pch.gc.ca) avec « Mode d'emploi : SMC et SCS » comme objet.


## Utilisations principales

Ce document a pour objectif de :

* Vulgariser les principaux termes utilisés dans les spécifications du modèle cible et des chemins sémantiques;
* Faciliter la lecture et la compréhension des spécifications du modèle cible et des chemins sémantiques;
* Expliquer comment utiliser les spécifications du modèle cible et des chemins sémantiques individuellement ou conjointement.

## Contexte

La Spécification du modèle cible (SMC) modélise sémantiquement les actants (personnes et groupes) dans un contexte patrimonial en documentant les patrons conceptuels les plus pertinents pour la vie des actants à travers des descriptions, des diagrammes, des exemples et des explications sur les décisions pertinentes qui ont été prises lors de leur élaboration.

La Spécification des chemins sémantiques (SCS) présente les liens sémantiques entre les entités du CIDOC CRM qui forment les patrons conceptuels présentés dans le modèle cible. 

Les deux spécifications sont destinées à être utilisées conjointement afin de répondre aux cas d'usage des projets en données ouvertes et liées (DOL) du domaine patrimonial.

## Vocabulaire de base et connaissances préalables {#vocabulaire-de-base-et-connaissances-prealables}

Dans les spécifications du modèle cible et des chemins sémantiques, divers termes techniques sont employés. L'utilisateur·rice devrait préalablement comprendre les concepts suivants :

* [Classe](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#classe-nom-feminin)
* [Instance](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#instance-nom-feminin)
* [Graphe de connaissances](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#connaissance-nom-feminin)
* [Modèle](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#modele-nom-masculin)
* [Graphe nommé](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#graphe-nomme-nom-masculin)
* [Nœud](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#noeud-nom-masculin)
* [Patron conceptuel](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#patron-conceptuel-nom-masculin)
* [Propriété](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#propriete-nom-feminin)
* [Propriété-classe](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#propriete-nom-feminin)
* [Spécification](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#specification-nom-feminin)

Le terme « modèle cible » est utilisé comme raccourci pour désigner le modèle en DOL du RCIP, auquel les jeux de données des utilisateurs·rices peuvent être mis en correspondance (d'où le terme « cible »).

De plus, toute personne utilisant les spécifications du modèle cible et des chemins sémantiques, que ce soit à des fins de modélisation ou non, doit être familière avec les notions de base des DOL; autrement, il est recommandé de consulter les ressources suivantes :

* [101 - Choix d’un modèle de DOL](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/mode-demploi/choix-modele-dol)
* [Modèle RDF](https://www.w3.org/RDF/) (en anglais)
* [Langage Turtle](https://www.w3.org/TR/turtle/) (en anglais)
* [Format JSON-LD](https://json-ld.org) (en anglais)

Il est également recommandé de lire le [glossaire ciblé](https://chin-rcip.github.io/collections-model/fr/specification-des-chemins-semantiques/actuel/introduction#glossaire) de la SCS pour mieux saisir la différence entre les nombreux concepts associés à la notion de « nœud » dans le contexte du modèle de données du RCIP.

Finalement, étant donné que le modèle du RCIP repose sur l'ontologie CIDOC CRM, l'utilisateur·rice doit en avoir une compréhension de base. Des ressources utiles peuvent être trouvées ici :

* [Site Web du CIDOC CRM](https://www.cidoc-crm.org/) (en anglais)
* [Tutoriel CIDOC CRM](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/tutoriel-cidoc-crm)

## Auditoires visés et description des sections {#auditoires-vises-et-description-des-sections}

Les utilisateurs·rices des spécifications du modèle cible et des chemins sémantiques doivent avoir une connaissance de base des technologies et techniques de l'information (p. ex. les catalogueurs·ses de musée, les programmeurs·ses, les experts·es en modélisation/ontologies).

Ce mode d'emploi est divisé en quatre sections :

1. **Mode d'emploi** : l'utilité et la structure de la SMC et de la SCS y sont présentées, ainsi que différentes manières de naviguer dans les documents et de les utiliser ensemble (trois personas sont mis en lumière à titre d'exemples);
2. **Aide-mémoire** : les éléments clés et les actions importantes y sont détaillés;
3. **Pour plus d'information** : des liens externes pertinents y sont fournis;
4. **Bibliographie** : les sources bibliographiques utilisées dans la préparation de ce mode d'emploi y sont documentées. 

## Mode d'emploi

### Spécification du modèle cible {#specification-du-modele-cible}

#### Utilité {#smc-utilite}

La spécification du modèle cible (SMC) explique la structure du modèle de données qui représente l'épine dorsale de la documentation DOPHEDA. L'objectif est d'aider les utilisateurs·rices à identifier, documenter, décrire et consolider, dans des enregistrements uniques, les informations relatives aux personnes et aux groupes (c.-à-d. les actants) liés aux objets des collections patrimoniales, les principaux évènements qui ponctuent généralement leur vie, ainsi que leurs relations aux autres.

Une autre intention derrière la SMC est d'encourager et d'aider les utilisateurs·rices à développer leur infrastructure en DOL, et éventuellement, leur propre modèle cible.

Ces spécifications ne sont pas nécessairement destinées à être lues dans leur intégralité et doivent plutôt être utilisées comme documents de référence. Les personnes intéressées par la **création d'un modèle de données** sont encouragées à consulter l'[introduction de la SMC](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/introduction).

#### Structure {#smc-structure}

##### Division des chapitres {#smc-division-des-chapitres}

La spécification du modèle cible est divisée en 23 chapitres. La structure du document a été conçue pour faciliter la recherche et la structuration de l'information dans un contexte de DOL, en plus de l'exploration du contexte d'un sujet spécifique.

1. [Introduction](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/introduction) : cette section présente les informations générales relatives à la version actuelle du modèle cible, la méthodologie employée pour son développement, ainsi que la description des conventions stylistiques et ontologiques utilisées dans les diagrammes à travers le modèle.
2. [Concepts généraux](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/concepts-generaux) : ce chapitre regroupe les notions, concepts et entités pertinents utilisés dans la SMC et présents dans la plupart des patrons conceptuels. Par exemple, l'utilité de réifier des propriétés spécifiques afin que les instances des propriétés-classes puissent devenir le sujet d'autres triplets est expliquée dans la section [propriétés-classes](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/concepts-generaux#proprietes-classes).

Chacun des chapitres suivants fait référence à un patron conceptuel particulier.

3. [Données désordonnées](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/donnees-desordonnees) : ce patron conceptuel a été développé pour faciliter la mise en correspondance des données non structurées, à savoir les données qui ne suivent pas les recommandations de DOPHEDA. Par exemple, le Yukon Arts Centre pourrait utiliser ce patron conceptuel pour documenter que l'artiste Ted Harrison est d'ascendance anglaise et qu'après s'être établi à Carcross, au Yukon, en 1968, il a obtenu la citoyenneté canadienne en 1973. Puisqu'aucun autre modèle ne permet de documenter ce type de données, il est recommandé d'utiliser le patron conceptuel Données désordonnées.
4. [Provenance du jeu de données](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/provenance-du-jeu-de-donnees) : ce patron conceptuel a été conceptualisé pour représenter l'information relative à la soumission d'un jeu de données par une organisation ou une personne responsable de sa création, de sa soumission et/ou de sa mise à jour. Par exemple, le Musée canadien de l'histoire pourrait utiliser ce patron conceptuel pour documenter que Sophie Piedmont (fictive) était la catalogueuse du jeu de données du musée lorsqu'il a été soumis à un graphe de connaissances le 31 octobre 2020.
5. [Provenance de l'enregistrement](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/provenance-de-lenregistrement) : ce patron conceptuel est destiné à représenter l'information relative à la documentation d'un enregistrement par un organisme ou une personne responsable soit de sa création, soit de sa dernière mise à jour. Par exemple, le Musée canadien de l'histoire pourrait utiliser ce patron conceptuel pour documenter que le catalogueur Maximilian Dunham (fictif) a créé l'enregistrement de Medalta Potteries Ltd. dans la base de données du musée le 15 juillet 1996.
6. [Limites temporelles](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/limites-temporelles) : ce patron conceptuel a été créé pour faciliter l'enregistrement des dates des évènements significatifs décrits dans la SMC. Tous les patrons conceptuels du modèle cible qui permettent la documentation des dates de début et de fin utilisent la même structure de base présentée dans ce patron conceptuel.
7. [Note curatoriale](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/note-curatoriale) : ce patron conceptuel concerne les informations associées à un actant qui ne peuvent pas être enregistrées à l'aide de champs structurés, mais qui se rapportent à un autre nœud de données représenté ailleurs dans le modèle. Il est particulièrement utile pour les utilisateurs·rices qui souhaitent modéliser des informations sous forme de commentaires, de remarques ou de descriptions, telles que des explications, des notes, des résultats ou des évaluations. Par exemple, la Winnipeg Art Gallery pourrait utiliser ce patron conceptuel pour documenter une note rédigée en anglais par Martin Jutt, le conservateur adjoint des arts décoratifs (fictif), qui évalue la valeur monétaire et l'état de conservation de l'œuvre *Buttermere Bridge* de W.T. Copeland & Sons.
8. [Identifiants et appellations de l'actant](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/identifiants-et-appellations-de-lactant) : ce patron conceptuel est l'un des plus importants de la SMC puisqu'il fait référence à des informations d'identification de base sur les actants que la majorité, sinon la totalité, des institutions patrimoniales documentent, telles que les identifiants ou les appellations. Par exemple, le Musée royal de l'Ontario pourrait utiliser ce patron conceptuel pour documenter les différentes appellations de l'artiste Michelangelo (p. ex. Michelangelo, Michel-Ange, Michelangelo di Lodovico Buonarroti Simoni, etc.), ainsi que préciser leur type (p. ex. prénom, nom usuel, nom complet, etc.), leur contexte, leur langue (p. ex. anglais, français, italien, etc.) et leur primauté.
9. [Technique utilisée](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/technique-utilisee) : ce patron conceptuel permet la représentation de l'information sur les techniques employées par un actant dans un acte de production, ou qu'on sait qu'il a employées de manière générale. Par exemple, le Orillia Museum of Art & History pourrait utiliser ce patron conceptuel pour documenter que Sylvia Tesori, l'artiste de l'œuvre *Cockpit*, a réalisé quelques sculptures au cours de sa carrière, même si elle est surtout connue pour ses œuvres peintes.
10. [Appartenance familiale](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/appartenance-familiale) : ce patron conceptuel peut être utilisé pour documenter l'appartenance d'une personne à une famille. Par exemple, le Musée des beaux-arts du Canada pourrait utiliser ce patron conceptuel pour indiquer que le peintre et graveur Jan Brueghel l'Ancien, qui a peint *Vue du Pont Rotto, Rome* en 1593-1596, appartient à la famille Brueghel, qui a aussi comme membres Pieter Bruegel l'Ancien et Pieter Brueghel le Jeune, tous deux célèbres peintres de la Renaissance hollandaise et flamande.
11. [Naissance et mort d'une personne](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/naissance-et-mort-dune-personne) : ce patron conceptuel est utile pour délimiter la durée de vie d'un actant (c.-à-d. sa naissance et sa mort). Par exemple, la Beaverbrook Art Gallery pourrait utiliser ce patron conceptuel pour documenter que l'artiste Clarence Gagnon est né le 8 novembre 1881 à Montréal, CA-QC, est décédé le 5 janvier 1942 à Montréal, CA-QC, et a été inhumé au Cimetière Notre-Dame-des-Neiges. 
12. [Formation et dissolution d'un groupe](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/formation-et-dissolution-dun-groupe) : ce patron conceptuel a été conçu pour documenter le début et la fin d'un groupe (c.-à-d. sa formation et sa dissolution) ainsi que les actants responsables. Par exemple, la Art Gallery of Hamilton pourrait utiliser ce patron conceptuel pour documenter la création de la Société d'art contemporain par John Lyman, son fondateur et premier président, à Montréal, CA-QC, en 1939.
13. [Floruit](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/floruit) : ce patron conceptuel a été développé pour faciliter la mise en correspondance des informations relatives à la période de productivité et d’excellence ou d’influence la plus élevée d’un actant dans un domaine au cours de sa vie. Par exemple, le Museum of Anthropology at UBC pourrait utiliser ce patron conceptuel pour documenter que l'artiste populaire portugais Domingos Gonçalves Lima, également connu sous le nom de Mistério, était particulièrement actif entre 1950 et 1990 à Barcelos.
14. [Appartenance à un groupe](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/appartenance-a-un-groupe) : ce patron conceptuel peut être utilisé pour documenter l'association officielle d'un actant à un groupe. Par exemple, la Art Gallery of Hamilton pourrait utiliser ce patron conceptuel pour documenter que Fritz Brandtner a rejoint la Société d'art contemporain en 1939 en tant que membre.
15. [Occupation](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/occupation) : ce patron conceptuel concerne les informations sur les occupations d'un actant – qui peuvent être une entreprise, une profession, ou toute autre activité liée au travail, qu'elle soit rémunérée ou non – en tant qu'activités principales dans sa vie. Par exemple, le Musée McCord Stewart pourrait utiliser ce patron conceptuel pour documenter qu'en plus de travailler comme orfèvre, Pierre Huguet dit Latour était également marchand et perruquier.
16. [Statut social](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/statut-social) : ce patron conceptuel permet la représentation des informations relatives aux statuts sociaux d'un actant, qui incluent le rang relatif et l'honneur ou le prestige possible qu'un actant détient par rapport à la façon dont il est perçu. Par exemple, le Musée national des beaux-arts du Québec pourrait utiliser ce patron conceptuel pour documenter que le sculpteur québécois Louis Archambault a été nommé Officier de l'Ordre du Canada par la reine Elizabeth II à Ottawa, CA-ON, en 1974.
17. [Relation](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/relation) : ce patron conceptuel est particulièrement utile pour la documentation des informations relatives à la relation d'association ou de connaissance entre deux actants. Par exemple, la Dalhousie Art Gallery pourrait utiliser ce patron conceptuel pour documenter la relation entre l'artiste Marcel Barbeau et son professeur, l'artiste Paul-Émile Borduas, lorsque ce premier a étudié à l'École du meuble de Montréal entre 1942 et 1946.
18. [Évènement de séjour](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/evenement-de-sejour) : ce patron conceptuel peut être utilisé pour représenter les informations relatives à la présence physique d'un actant quelque part pour une durée prolongée ou temporaire, y compris à leur résidence/emplacement géographique habituel. Par exemple, la Vancouver Art Gallery pourrait utiliser ce patron conceptuel pour documenter que le peintre Lawren Harris a séjourné à Berlin entre 1904 et 1908 pour étudier l'art, la philosophie et la théosophie.
19. [Biographie](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/biographie) : ce patron conceptuel détaille comment représenter les informations textuelles relatives à la biographie d'un actant. Par exemple, la Art Gallery of Nova Scotia pourrait utiliser ce patron conceptuel pour documenter la biographie en anglais de l'artiste Maud Lewis, « Maud Lewis (1901-1970) was born to John and Agnes Dowley [... and the house she painted] is on permanent display in Halifax at the Art Gallery of Nova Scotia », accessible sur son site Web à l'adresse [https://artgalleryofnovascotia.ca/maud-lewis](https://artgalleryofnovascotia.ca/maud-lewis).
20. [Artefact](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/artefact) : ce patron conceptuel est l'un des plus importants de la SMC puisqu'il fait référence aux informations d'identification de base sur les objets que la majorité, sinon la totalité, des institutions patrimoniales documentent, telles que leurs numéros d'accession et leurs appellations. Par exemple, le Musée des beaux-arts de Montréal pourrait utiliser ce patron conceptuel pour documenter que *Soleil de minuit (Quatuor en blanc)* est le titre en français d'une œuvre de l'artiste Jean Paul Riopelle qui est conservée sous le numéro d'accession 2001.161.1- 4.
21. [Production d'artefact](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/production-dartefact) : ce patron conceptuel peut être utilisé pour enregistrer minimalement les informations relatives à la production d'un artefact tangible, telles que le rôle des producteurs·rices dans sa création et leur niveau de priorité, ainsi que le moment lors duquel et l'endroit où il a été créé. Par exemple, Power Corporation du Canada pourrait utiliser ce patron conceptuel pour documenter que Jean Paul Riopelle est le seul artiste de la peinture *Iceberg no. 5* et que cette œuvre a été peinte en 1977 dans l'atelier de l'artiste situé à Estérel, CA-QC.
22. [Entité visuelle](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/entite-visuelle) : ce patron conceptuel peut être utilisé pour représenter les informations relatives à la représentation visuelle d'un actant sous forme numérique ou représenté sur un objet physique, qu'il s'agisse d'une image (p. ex. Albrecht Dürer dans l'un de ses nombreux autoportraits) ou d'une marque (p. ex. le poinçon de l'orfèvre Carl Poul Petersen sous le pied d'une aiguière), ainsi que leur type et leur mention bibliographique.
23. [Emplacement du document de référence](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/emplacement-du-document-de-reference) : ce patron conceptuel concerne les documents de référence liés à un actant ainsi que les informations indiquant où se trouvent ces documents. Par exemple, le Musée national des beaux-arts du Québec pourrait utiliser ce modèle pour documenter que le catalogue de l'exposition « Jean Paul Lemieux au Musée du Québec », dans lequel un artefact spécifique de sa collection est représenté, est conservé sous le numéro de référence 700 L554m 2001-3 et peut être consulté à la bibliothèque du musée.

#### Gabarit des patrons conceptuels

Chaque patron conceptuel modélisé et décrit dans la SMC suit le même gabarit de description pour faciliter l'identification des informations utiles liées à un besoin spécifique. Le gabarit est le suivant :

* **Aperçu** : cette section décrit l'utilité du patron conceptuel, le type d'information qu'il peut représenter ainsi que ses limites; 
* **Introduction et contexte** : cette section définit les concepts sur lesquels le patron conceptuel repose et présente le contexte justifiant son développement par le RCIP;
* **Description du patron conceptuel** : cette section fournit une description détaillée des liens sémantiques entre les nœuds de saisie, les classes et les propriétés composant le patron conceptuel;
* **Diagramme** : cette section offre une représentation visuelle du patron conceptuel, dans laquelle les [conventions stylistiques et ontologiques](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/introduction#conventions-de-diagramme) d'autres projets importants en données ouvertes et liées dans le domaine patrimonial, tels que SARI et Linked.art, ont été utilisées. Le RCIP a développé des bibliothèques logicielles [diagrams.net](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/outils) pour les musées souhaitant développer leur propre modèle basé sur CIDOC CRM;
* **Exemples** : cette section présente des diagrammes d'instances (générés par [CRITERIA](https://github.com/chin-rcip/CRITERIA)) qui aident à illustrer l'utilisation du patron conceptuel avec un ou plusieurs cas d'usage concrets (c.-à-d. comment des données spécifiques sont modélisées en fonction du modèle de données) afin que le ou la développeur·se puisse tester rapidement le patron conceptuel dans son modèle de données grâce aux représentations en Turtle et en JSON-LD;
* **Documentation connexe** : cette section fait référence aux modèles externes qui ont été utiles pour la conceptualisation et le développement du patron conceptuel, en plus de lister les nœuds de saisie du patron conceptuel ainsi que les entités du CIDOC CRM que le patron conceptuel mobilise;
* **Discussion** : cette section explique pourquoi le patron conceptuel a été modélisé d'une certaine manière (c.-à-d. les avantages et les inconvénients), explore ses enjeux et ses limites, et présente des cas limites actuels permettant à l'utilisateur·rice de documenter des circonstances moins courantes dans la vie des actants (p. ex. lorsqu'un artiste connaît plus d'un floruit, que ce soit dans les mêmes domaines/médiums/périodes ou non) ou des données difficiles à enregistrer (p. ex. le père d'une famille n'est pas nécessairement le père de tous les membres de cette famille);
* **Bibliographie** : cette section documente en ordre alphabétique toutes les sources bibliographiques ayant permis la conceptualisation et le développement du patron conceptuel.

### Spécification des chemins sémantiques {#specification-des-chemins-semantiques}

#### Utilité {#scs-utilite}

La spécification des chemins sémantiques (SCS) fournit une description sémantique de chaque nœud de saisie composant les patrons conceptuels de la SMC. Cette description spécifie les informations (c.-à-d. les données) qui doivent être documentées dans le nœud, les chemins sémantiques qui permettent d'effectuer une requête, ainsi que les niveaux d'évaluation de la qualité attendue des données enregistrées.

La SCS peut servir de document de référence pour tout processus de mise en correspondance. Par exemple, un musée qui souhaite transformer des données existantes enregistrées dans sa base de données institutionnelle en une autre structure de données répondant mieux aux exigences du Web sémantique peut s'appuyer sur le modèle DOPHEDA pour développer son propre modèle.

Un·e utilisateur·rice ne disposant pas de données préliminaires peut construire sa propre base de données et/ou son propre modèle de données directement à partir de la SCS.

#### Structure {#scs-structure}

##### Division des chapitres {#scs-division-des-chapitres}

La spécification des chemins sémantiques est divisée en trois chapitres :

1. [Introduction](https://chin-rcip.github.io/collections-model/fr/specification-des-chemins-semantiques/actuel/introduction) : cette section documente les informations pertinentes sur l'utilisation de la spécification, un glossaire clarifiant les différents termes liés à la notion de « nœud » ainsi qu'une description de la structure adoptée pour la présentation de tous les nœuds de saisie du modèle.
2. [Nœuds de saisie](https://chin-rcip.github.io/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie) : cette section est le corps de la documentation; elle contient des tableaux décrivant chacun des nœuds de saisie de la SCS, classés par ordre alphabétique pour faciliter leur repérage sur la barre latérale (côté gauche de l'interface).
3. [Bibliographie](https://chin-rcip.github.io/collections-model/fr/specification-des-chemins-semantiques/actuel/bibliographie) : cette section documente en ordre alphabétique les sources bibliographiques qui ont permis la conceptualisation et le développement des nœuds de saisie.

#### Gabarit des nœuds de saisie {#gabarit-des-noeuds-de-saisie}

Chaque nœud de saisie est défini par un ensemble de caractéristiques descriptives rassemblées dans un tableau.

Chaque nœud de saisie est décrit par une note d'application précise (c.-à-d. sa portée) détaillant les valeurs de données qu'il peut accueillir ainsi que par ses liens générés, son évaluation sémantique et sa liste contrôlée de termes. Le contexte de chaque nœud peut être exploré à travers ses dépendances, ses nœuds dotés d'un qualifiant spécifié reliés, son chemin complet, ses vues de la spécification du modèle cible et ses origines de valeur. En plus des commentaires pertinents et des erreurs potentielles, la SCS énumère des cas typiques et limites qui illustrent comment les institutions patrimoniales pourraient documenter l'information pouvant être associée à d'autres domaines. Des références sont également incluses pour chaque nœud.

Une description détaillée de chaque caractéristique descriptive se trouve dans la section [Structure de la documentation](https://chin-rcip.github.io/collections-model/fr/specification-des-chemins-semantiques/actuel/introduction#structure-de-la-documentation) de la SCS.

### Utiliser conjointement la SMC et la SCS

#### Spécifications complémentaires {#specifications-complementaires}

Les spécifications du modèle cible et des chemins sémantiques ont été pensées, conceptualisées et développées dans une logique de complémentarité et doivent donc être utilisées l'une avec l'autre. Alors que la SMC présente le modèle de données, le contexte de chaque nœud de saisie et les relations entre tous les nœuds de saisie via un ensemble de patrons conceptuels, la SCS décrit chaque nœud de saisie en détail, les informations qu'ils doivent contenir et les chemins permettant de les interroger.

En d'autres mots, l'information présentée dans la SMC est plus théorique et particulièrement utile pour comprendre la sémantique sous-jacente au modèle, les raisons justifiant la conception des patrons conceptuels, ainsi que les interactions entre les entités du CIDOC CRM au sein d'un même patron conceptuel. La SMC est également utile pour valider les interprétations des utilisateurs·rices ou déterminer ce qui peut être fait avec un jeu de données existant. De plus, l'introduction de la SMC est un point de départ essentiel pour quiconque n'est pas familier avec la documentation DOPHEDA; le RCIP recommande de la lire avant de se rendre à la SCS.

En revanche, l'information incluse dans la SCS est présentée de manière appliquée pour faciliter la mise en application. Elle permet aux utilisateurs·rices, une fois engagés·es dans un processus de mise en correspondance ou de mise en application d'un modèle de données, d'évaluer le potentiel sémantique de leurs données en fonction de leur capacité et de développer un processus fonctionnel de mise en correspondance en conséquence (p. ex. s'assurer que les nœuds sont connectés aux entités pertinentes).

#### Navigation

Il existe plusieurs façons de d'effectuer des recherches et de naviguer dans les spécifications du modèle cible et des chemins sémantiques. Puisqu'elles n'ont pas à être lues linéairement (du début à la fin), leur capacité de recherche est une caractéristique importante. Il existe trois façons d'effectuer une recherche dans la SMC et la SCS : à partir de l'organisation des chapitres qui est visible sur la barre latérale, de l'outil de recherche ou du diagramme A-Z.

##### Barre latérale {#barre-laterale}

La structure des chapitres de la SMC et de la SCS est visible sur la barre latérale de la documentation de la plateforme (côté gauche de l'interface). En y naviguant, il est possible d'accéder à des chapitres spécifiques de la documentation et de trouver les informations nécessaires.

L'utilisation de la barre latérale est le meilleur moyen d'obtenir un aperçu général de la hiérarchie des spécifications et d'avoir un extrait des différents sujets couverts par le modèle et de la structure de chaque patron conceptuel (SMC) et nœud de saisie (SCS).

##### Outil de recherche

Un outil de recherche est également disponible dans le menu supérieur du site Web de DOPHEDA (l'icône en forme de loupe). Grâce à cet outil de recherche, il est possible de récupérer des mots spécifiques présents sur l'ensemble du site Web. Une fois les mots-clés saisis dans l'outil de recherche, quelques exemples de requêtes sont affichés afin d'aider les utilisateurs·rices à sélectionner les résultats de recherche les plus adaptés à leurs besoins.

Cet outil est particulièrement utile aux utilisateurs·rices qui connaissent déjà ce qu'ils recherchent, qui veulent trouver des termes significatifs dans des sections qu'ils auraient pu manquer autrement, qui ont besoin de rassembler toutes les informations relatives à un sujet particulier, ou qui souhaitent confirmer que tous les patrons conceptuels pertinents à un besoin de modélisation ont été examinés.

##### Diagramme A-Z

Pour les utilisateurs·rices plus avancés·es, le diagramme A-Z situé dans l'introduction de la SMC est un outil essentiel pour accéder à des patrons conceptuels spécifiques (en cliquant sur leur titre) et effectuer une recherche rapide puisqu'il ne nécessite pas de naviguer dans la hiérarchie de la SMC.

De plus, chaque nœud présent dans la SCS dont les caractères sont en gras sur le diagramme A-Z est accessible en cliquant dessus. Ces liens sont le meilleur moyen pour les utilisateurs·rices de naviguer entre la SMC et la SCS.

#### Personas

Pour illustrer différentes manières de consulter les spécifications et de les utiliser à diverses fins, les exemples suivants ont été élaborés. Ils sont purement *fictifs* et servent à démontrer **trois** manières parmi **plusieurs** d'utiliser conjointement la SMC et la SCS.

Le fil conducteur unissant ces trois personas est le développement d'un graphe de connaissances par l'Association canadienne pour l'avancement des sciences humaines ouvertes (ACASHO) (fictive) pour rassembler les données ouvertes et liées de nombreux musées et institutions patrimoniales situés à travers le pays.

##### Catalogueur·se de musée {#catalogueurse-de-musee}

Abigail est catalogueuse au Musée d'art Eureka (MAE), qui a récemment été fondé grâce au mécénat de la famille Eureka et au don de son exceptionnelle collection privée à la Ville d'Ottawa. Le musée souhaite verser les données sur sa collection dans l'écosystème mis en place par l'ACASHO, qui s'appuie principalement sur le modèle sémantique DOPHEDA. D'une part, Abigail s'est vue confier le mandat de veiller à ce que le sens des données de l'institution soit préservé lors de leur intégration dans le graphe de connaissances de l'ACASHO. D'autre part, elle doit respecter les règles sémantiques proposées par le modèle DOPHEDA afin d'assurer l'interopérabilité des données de l'établissement avec l'ensemble des données collectées par l'ACASHO.

À cette fin, Abigail doit préparer un gabarit de mise en correspondance (tableau) comprenant tous les nœuds de saisie avec les champs suivants tout en consultant les informations de ces caractéristiques dans la SCS, par exemple :

|Patron conceptuel|Nœud de saisie|Définition|Format de données|Exemple|Nom du champ de données du musée|Notes|
|---|---|---|---|---|---|
|[Identifiants et appellations de l'actant](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/identifiants-et-appellations-de-lactant)|[Appellation de l'actant](https://chin-rcip.github.io/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-de-lactant)|le·s mot·s, chiffre·s, symbole·s ou code·s complets d’identification par lesquels un actant (personne ou groupe) se distingue des autres, comme le nom, le titre ou la désignation tels qu’ils ont été attribués par une institution|chaîne de caractères|« Emily Carr »|||
|[Identifiants et appellations de l'actant](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/identifiants-et-appellations-de-lactant)|[Langue de l'appellation de l'actant](https://chin-rcip.github.io/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#langue-de-lappellation-de-lactant)|la langue naturelle dans laquelle l’appellation de l’actant est écrite|URI ou valeur pouvant être réconciliée avec une URI du vocabulaire lexvo|« Français », « fra », « fr », « http://www.lexvo.org/page/iso639-3/fra »|||

Sur la base de ce gabarit, Abigail peut créer un profil de mise en correspondance pour le MAE en identifiant quel champ de données de son jeu de données correspond à quel nœud de saisie. Étant donné qu'Abigail connaît la base de données du MAE et la description de chaque champ qu'elle contient, elle peut utiliser ses connaissances pour déterminer quel champ de données correspond à quel nœud de saisie. Par exemple, la description des métadonnées du champ décrivant l'appellation des artistes dans la base de données du MAE est la suivante :

|nom_du_champ|définition|format|
|---|---|---|
|nom_de_l'artiste_fr|Nom complet de l'artiste en français|nom de famille, prénom|

Bien que le gabarit de mise en correspondance inclut de brèves descriptions des nœuds de saisie, Abigail peut consulter leurs descriptions complètes dans la SCS, en particulier les sections Évaluation sémantique, Cas typiques et Commentaires, en plus de la section Exemples dans la SMC, pour s'assurer de l'exactitude de la mise en correspondance et déterminer si une manipulation supplémentaire des données est nécessaire. Dans cet exemple, Abigail décide que :

- les données dans `nom_de_l'artiste_fr` doivent être reformatées en `prénom nom de famille` et être saisies comme « nom complet »;
- les données doivent être scindées en deux Parties de l'appellation de l'actant de types « prénom » et « nom de famille »;
- la Langue de l'Appellation de l'actant et des Parties de l'appellation de l'actant doivent être enregistrées comme « Français ». 
Lors de son analyse du champ de données du MAE `nom_de_l'artiste_fr`, s'il y avait une anomalie et/ou une incohérence dans les données, Abigail aurait pu consulter les sections Cas limites de la SMC et de la SCS pour déterminer si elles auraient pu être mises en correspondance. Voici une partie du profil de mise en correspondance du MAE après l'analyse :

|Patron conceptuel|Nœud de saisie|Définition|Format de données|Exemple|Nom du champ de données du musée|Notes|
|---|---|---|---|---|---|
|[Identifiants et appellations de l'actant](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/identifiants-et-appellations-de-lactant)|[Appellation de l'actant](https://chin-rcip.github.io/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-de-lactant)|le·s mot·s, chiffre·s, symbole·s ou code·s complets d’identification par lesquels un actant (personne ou groupe) se distingue des autres, comme le nom, le titre ou la désignation tels qu’ils ont été attribués par une institution|chaîne de caractères|« Emily Carr »|nom_de_l'artiste_fr|à reformater de « nom de famille, prénom » à « prénom nom de famille »|
|[Identifiants et appellations de l'actant](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/identifiants-et-appellations-de-lactant)|[Langue de l'appellation de l'actant](https://chin-rcip.github.io/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#langue-de-lappellation-de-lactant)|la langue naturelle dans laquelle l’appellation de l’actant est écrite|URI ou valeur pouvant être réconciliée avec une URI du vocabulaire lexvo|« Français », « fra », « fr », « http://www.lexvo.org/page/iso639-3/fra »||« Français » comme valeur fixée|
|[Identifiants et appellations de l'actant](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/identifiants-et-appellations-de-lactant)|[Partie de l'appellation de l'actant 1](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/partie-de-lappellation-de-lactant)|l’une des unités composant l’Appellation de l’actant|chaîne de caractères|« Carr »|nom_de_l'artiste_fr[« nom de famille »]|première partie de la donnée du musée<br>virgule de séparation|
|[Identifiants et appellations de l'actant](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/identifiants-et-appellations-de-lactant)|[Partie de l'appellation de l'actant 2](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/partie-de-lappellation-de-lactant)|l’une des unités composant l’Appellation de l’actant|chaîne de caractères|« Emily »|nom_de_l'artiste_fr[« prénom »]|deuxième partie de la donnée du musée<br>virgule de séparation|

Une fois le profil de mise en correspondance terminé, Abigail peut l'envoyer à l'ACASHO avec le jeu de données exporté du EAM.

##### Développeur {#developpeur}

Ronaldo est un développeur qui a été embauché par l'ACASHO pour concevoir un graphe de connaissances qui puisse être utilisé par les musées et les institutions patrimoniales pour partager et diffuser les données sur leurs collections. Son rôle consiste également à transformer les données des institutions partenaires tout en respectant leur profil de mise en correspondance. L'ACASHO souhaite que le graphe de connaissances se base sur le modèle cible du RCIP. Ainsi, l'une des principales tâches de Ronaldo est de préparer la transformation des jeux de données soumis par les institutions partenaires (p. ex. en CSV) en DOL en suivant le modèle cible.

Dans son plan de travail, la première étape consiste à se familiariser avec les patrons conceptuels de la SMC en consultant le diagramme A-Z se trouvant en introduction. Ensuite, Ronaldo décide de débuter par le patron conceptuel le plus important, à savoir Identifiants et appellations de l'actant. À partir du diagramme A-Z, il clique sur le titre du patron conceptuel et est redirigé vers le chapitre approprié, où il prête attention aux sections Aperçu, Description du patron conceptuel, Diagramme, Exemples et Nœuds de saisie.

- La section Aperçu lui donne une compréhension générale du patron conceptuel, ainsi que ce qu'il représente et ne représente pas. Cette présentation l'aide à découvrir que ce patron conceptuel couvre les identifiants des actants, mais pas les informations d'identification des artefacts.
- Les sections Description du patron conceptuel et Diagramme permettent à Ronaldo de comprendre la structure sémantique sous-jacente du patron conceptuel. Elles contiennent toutes les deux des liens cliquables vers la description de chaque nœud de saisie dans la SCS ainsi que plusieurs caractéristiques descriptives qui aident à solidifier la transformation des jeux de données. D'une part, les Liens générés, les Dépendances, le Chemin complet et les NDQS reliés l'aident à valider la transformation conforme de chaque nœud. D'autre part, l'Évaluation sémantique l'informe de la valeur requise des données pour leur transformation suivant la structure sémantique du patron conceptuel; sinon, Ronaldo doit ajouter le patron conceptuel Données désordonnées dans la transformation.
- La section Exemples fournit les résultats exemplaires en DOL de la transformation, qui peuvent être téléchargés dans le propre écosystème de Ronaldo à des fins de test.
Une fois les scripts de transformation prêts, les jeux de données soumis peuvent être semi-automatiquement convertis en DOL et ingérés dans le graphe de connaissances. Ronaldo doit ensuite discuter avec les personnes responsables du catalogage dans les institutions partenaires, y compris Abigail (voir le premier persona), pour s'assurer que son processus de transformation générera les données souhaitées par les institutions.

##### Chercheur·se

Gabriele effectue des recherches et souhaite identifier tous les artistes représentés dans les collections permanentes du Musée des humanités et du Musée d'art Eureka qui ont utilisé la sculpture comme technique principale. Gabriele possède quelques connaissances en DOL et souhaite trouver facilement les informations dont iel a besoin sans avoir à comprendre l'ensemble du modèle de données mobilisé par le graphe de connaissances de l'ACASHO. 

Pour déterminer comment bâtir efficacement sa requête, Gabriele utilise l'outil de recherche du site Web de DOPHEDA et saisit des mots-clés relatifs à la sculpture, à savoir « technique », « médium » et « matériau ». Des exemples de résultats lui permettent de repérer les patrons conceptuels [Technique utilisée](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/technique-utilisee), [Occupation](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/occupation) et [Production d'artefact](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/production-dartefact) dans la SMC.

Pour s'assurer qu'iel s'appuie sur les bons patrons conceptuels et les utilise de manière efficace, Gabriele lit les sections Aperçu, Historique théorique et Énoncé des besoins. Cette première familiarisation avec les patrons conceptuels lui permet d'éliminer le patron conceptuel Production d'artefact, que les musées peuvent utiliser uniquement pour documenter les informations relatives aux rôles des producteurs·rices dans la création d'un artefact, le lieu lors duquel et le moment où l'artefact a été créé, ainsi que le niveau de priorité de ses producteurs·rices.

Au contraire, le patron conceptuel Technique utilisée peut être utilisé par les musées pour représenter les informations sur les techniques employées par un actant qui ne sont pas enregistrées dans le cadre de la production d'un objet spécifique, plus précisément en utilisant le nœud de saisie [Type de technique utilisée](https://chin-rcip.github.io/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#type-de-technique-utilisee) (p. ex. le Type de technique utilisée « Sculpture » permettrait à Gabriele de trouver tous les artistes associés à cette technique). De même, le patron conceptuel Occupation peut être utilisé par les musées pour représenter les informations sur les activités, les entreprises, les professions et autres rôles liés au travail d'un actant, plus précisément en utilisant le nœud de saisie [Type d'occupation](https://chin-rcip.github.io/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#type-doccupation) (p. ex. le Type d'occupation « Sculpteur ou Sculpteuse » permettraient à Gabriele de trouver tous les artistes associés à cette occupation).

Puisque Gabriele s'intéresse aux données de deux jeux de données spécifiques, iel vérifie également s'il existe un patron conceptuel de provenance. Iel découvre que le patron conceptuel [Provenance du jeu de données](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/provenance-du-jeu-de-donnees) lui permettrait de cibler adéquatement des jeux de données institutionnels spécifiques. Le patron conceptuel [Provenance de l'enregistrement](https://chin-rcip.github.io/collections-model/fr/modele-cible/actuel/provenance-de-lenregistrement) ne s'appliquerait pas dans cet exemple, car il permet uniquement de cibler la provenance d'un enregistrement particulier dans une base de données. Ici, Gabriele a besoin de connaître uniquement la provenance du jeu de données et non de chacun de ses enregistrements.

Une fois ces trois patrons conceptuels identifiés et leur utilité validée, Gabriele lit leurs Descriptions du patron conceptuel (SMC), vérifie leurs Diagrammes (SMC), explore leurs Exemples (SMC) et analyse leurs Chemins complets (SCS) afin d'identifier tous les construits sémantiques pertinents à prendre en considération lors de l'élaboration de sa requête. Les exemples lui sont particulièrement utiles, car iel peut jeter un œil aux sérialisations du graphe de connaissances en Turtle et en JSON-LD.

Avec toutes ces informations en main, Gabriele est maintenant en mesure de créer la requête SPARQL suivante, qui l'aidera à trouver toutes les personnes ayant « Sculpteur ou Sculpteuse » comme occupation et « Sculpture » comme technique utilisée dans les deux jeux de données spécifiques :



```sparql
prefix crm: <http://www.cidoc-crm.org/cidoc-crm/> .

prefix crmdig: <http://www.ics.forth.gr/isl/CRMext/CRMdig.rdfs/> .

prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .



SELECT ?actant ?technique ?occupation ?soumissionnaireNom

WHERE{

        ?g a crmdig:D1_Digital_Object ;
                crm:P94i_was_created_by/crm:P01i_is_domain_of/crm:P02_has_range/crm:P1_is_identified_by/crm:P190_has_symbolic_content ?soumissionnaireNom .
        FILTER (CONTAINS(lcase(?soumissionnaireNom),"musée des humanités") || CONTAINS(lcase(?soumissionnaireNom),"musée d'art eureka"))
        GRAPH ?g {
                optional{
                        ?actant crm:P2_has_type ?techniqueURI.
                        ?techniqueURI crm:P2_has_type/rdfs:label "Technique utilisée"@fr.
                        ?techniqueURI rdfs:label ?technique.
                        FILTER(lang(?technique)="fr")
                        FILTER REGEX(?technique,"sculpt","i")
                }
                optional{
                        ?actant crm:P14i_performed/crm:P2_has_type ?occupationURI.
                        ?occupationURI crm:P2_has_type/rdfs:label "Occupation"@fr.
                        ?occupationURI rdfs:label ?occupation.
                        FILTER(lang(?occupation)="fr")
                        FILTER REGEX(?occupation,"sculpt","i")
                }
        }
}
```


Notez que la requête développée par Gabriele pourrait être améliorée pour être davantage efficace, mais cela ne fait pas partie des objectifs de ce document.

## Aide-mémoire {#aide-memoire}

La recherche dans la SCS peut être complexe si l'utilisateur·rice n'est pas familier·ère avec la structure adoptée. Pour cette raison, le RCIP a répertorié des recherches courantes.

* Comment trouver le nœud approprié? Vous pouvez :
   	* effectuer une recherche par mots-clés en utilisant l'outil de recherche;
	* consulter ses dépendances;
	* regarder les nœuds associés;
	* parcourir les patrons conceptuels de la SMC.
* Comment comprendre le chemin sémantique d'un nœud? Vous pouvez consulter :
	* son chemin complet. Certains nœuds ont des chemins plus longs, car ils mobilisent un ou plusieurs nœuds dotés d'un qualifiant spécifié;
	* la SMC via les vues de la spécification du modèle cible pour cerner le contexte du nœud dans un patron conceptuel;
	* son évaluation sémantique pour comprendre quel type de données est attendu, en particulier lors de la rédaction de requêtes pouvant s'appuyer sur des algorithmes logiques ou sur certains vocabulaires contrôlés;
	* ses commentaires.
* Comment déterminer le contenu attendu d'un nœud? Vous pouvez lire :
	* sa portée pour mieux comprendre de quoi il s'agit;
	* son évaluation sémantique pour savoir quel type de données devrait être documenté;
	* ses cas typiques pour avoir des exemples de données documentées;
	* ses cas limites pour comprendre les limites du nœud.
* Comment établir le contexte d'un nœud? Vous pouvez regarder ses :
	* dépendances;
	* NDQS reliés;
	* vues de la spécification du modèle cible;
	* origines de valeur dans la liste de vérification (indisponible pour le moment).
* Comment évaluer la qualité de vos données? Vous pouvez vous référer à l'évaluation sémantique de chaque nœud de saisie.

## Pour plus d'information

Liens externes pertinents :

* [101 - Choix d’un modèle de DOL](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/mode-demploi/choix-modele-dol)
* [Modèle RDF](https://www.w3.org/RDF/) (en anglais)
* [Langage Turtle](https://www.w3.org/TR/turtle/) (en anglais)
* [Format JSON-LD](https://json-ld.org) (en anglais)
* [Site Web du CIDOC CRM](https://www.cidoc-crm.org/) (en anglais)
* [Tutoriel CIDOC CRM](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/tutoriel-cidoc-crm)

## Bibliographie

Art Gallery of Nova Scotia. « Maud Lewis ». Art Gallery of Nova Scotia – Collection. 2022. [https://artgalleryofnovascotia.ca/maud-lewis](https://artgalleryofnovascotia.ca/maud-lewis).

Derome, Robert et Norma Morgan. « HUGUET, Latour, PIERRE ». Dictionnaire biographique du Canada. 1983. [http://www.biographi.ca/fr/bio/huguet_pierre_5F.html](http://www.biographi.ca/fr/bio/huguet_pierre_5F.html).

Gagnon, François-Marc. « Jean Paul Riopelle : Sa vie et son œuvre par François-Marc Gagnon ». Institut de l'art canadien. 2019. [https://www.aci-iac.ca/fr/livres-dart/jean-paul-riopelle/oeuvres-phares/iceberg-no-1/](https://www.aci-iac.ca/fr/livres-dart/jean-paul-riopelle/oeuvres-phares/iceberg-no-1/).

La Bibliothèque nationale du Canada. « Ted Harrison, 1926- ». Collections Canada. 12 mars 1997. [https://www.collectionscanada.gc.ca/eppp-archive/100/200/301/nlc-bnc/art_illustrations-ef/magic/fharris2.htm](https://www.collectionscanada.gc.ca/eppp-archive/100/200/301/nlc-bnc/art_illustrations-ef/magic/fharris2.htm).

La gouverneure générale du Canada. « M. Louis Archambault ». La gouverneure générale du Canada. 2022. [https://www.gg.ca/fr/distinctions/recipiendaires/146-99](https://www.gg.ca/fr/distinctions/recipiendaires/146-99).

Ministère de l'Emploi et de la Solidarité sociale. « Jean Paul Lemieux au Musée du Québec / Michèle Grandbois. – ». Catalogue CUBIQ. 2022. [https://www.cubiq.ribg.gouv.qc.ca/notice?id=p%3A%3Ausmarcdef_0000639862](https://www.cubiq.ribg.gouv.qc.ca/notice?id=p%3A%3Ausmarcdef_0000639862).

Musée des beaux-arts de Montréal. « Jean Paul Riopelle ». Musée des beaux-arts de Montréal – Les collections du Musée des beaux-arts de Montréal. 2022. [https://www.mbam.qc.ca/fr/oeuvres/35801/](https://www.mbam.qc.ca/fr/oeuvres/35801/).

Musée des beaux-arts du Canada. « Jan (le vieux) Brughel ». Musée des beaux-arts du Canada – Recherche dans la collection. 2022. [https://www.beaux-arts.ca/collection/artiste/jan-le-vieux-brueghel?\_gl=1\*12lxdi1\*\_ga\*NjY0MDYxMzA0LjE2NzA3MTQyNzc.\*\_ga_83BW334MD2\*MTY3MDcxNDI3Ni4xLjEuMTY3MDcxNDU0NS4wLjAuMA..](https://www.beaux-arts.ca/collection/artiste/jan-le-vieux-brueghel?_gl=1*12lxdi1*_ga*NjY0MDYxMzA0LjE2NzA3MTQyNzc.*_ga_83BW334MD2*MTY3MDcxNDI3Ni4xLjEuMTY3MDcxNDU0NS4wLjAuMA..).

Museum of Anthropology at UBC. « Lima, Domingos Goncalves (1921 - 1995) ». Museum of Anthropology at UBC – Collection Online. 2022. [http://collection-online.moa.ubc.ca/search/person?person=5504&tab=biography](http://collection-online.moa.ubc.ca/search/person?person=5504&tab=biography).

Orillia Museum of Art & History. « The Man Who Could Fly; The Girl Who Flies in her Dreams by Sylvia Tesori ». Orillia Museum of Art & History – Current Exhibitions. 2022. [https://www.orilliamuseum.org/project/the-man-who-could-fly-and-the-girl-who-flies-in-her-dreams-by-sylvia-tesori/](https://www.orilliamuseum.org/project/the-man-who-could-fly-and-the-girl-who-flies-in-her-dreams-by-sylvia-tesori/).

Wikipédia. « Clarence Gagnon ». Wikipédia. 23 juin 2022. [https://fr.wikipedia.org/wiki/Clarence_Gagnon](https://fr.wikipedia.org/wiki/Clarence_Gagnon).

Wikipédia. « John Lyman ». Wikipédia. 7 juin 2021. [https://fr.wikipedia.org/wiki/John_Lyman](https://fr.wikipedia.org/wiki/John_Lyman).

Wikipédia. « Lawren Harris ». Wikipédia. 30 décembre 2021. [https://fr.wikipedia.org/wiki/Lawren_Harris](https://fr.wikipedia.org/wiki/Lawren_Harris).

Wikipédia. « Marcel Barbeau ». Wikipédia. 9 novembre 2022. [https://fr.wikipedia.org/wiki/Marcel_Barbeau](https://fr.wikipedia.org/wiki/Marcel_Barbeau).

Wikipédia. « Michel-Ange ». Wikipédia. 1er décembre 2022. [https://fr.wikipedia.org/wiki/Michel-Ange](https://fr.wikipedia.org/wiki/Michel-Ange).

Winnipeg Art Gallery. « W.T. Copeland & Sons ». Winnipeg Art Gallery – Search the Collections. 2022. [https://www.wag.ca/art/collection/item/34378/?from=art-search](https://www.wag.ca/art/collection/item/34378/?from=art-search).