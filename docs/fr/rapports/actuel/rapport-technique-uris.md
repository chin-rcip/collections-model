---
layout: page
language: fr
title: Rapport technique sur les URI
permalink: /fr/rapports-techniques/actuel/rapport-technique-sur-les-uri
other_link: /en/technical-reports/current/uris-technical-report
sidebar: urireportfr
group: rapports techniques
date: 2022-03-22
description: Ce rapport technique détaille (1) les principes d’organisation qui dictent (2) le modèle recommandé de spécification des URI du RCIP et (3) la gestion de ces URI (actuellement en cours de développement et dont la publication est prévue ici dans une version ultérieure). En tant que tel, ce rapport met l’accent sur les éléments pertinents pour le RCIP en tant qu’organisation et s’adresse aux décideurs·euses auxquels·les il rend compte. Ceci étant dit, le présent document peut être utilisé par d’autres organisations patrimoniales ou gouvernementales pour établir des directives internes pour la publication d'URI.
---

 **Version** : 2.1

**Date de création** : 2020-04-24

**Dernière mise à jour** : 2022-03-22

## Résumé {#resume}

Ce rapport technique détaille (1) les principes d’organisation qui dictent (2) le modèle recommandé de spécification des URI du RCIP et (3) la gestion de ces URI (actuellement en cours de développement et dont la publication est prévue ici dans une version ultérieure). En tant que tel, ce rapport met l’accent sur les éléments pertinents pour le RCIP en tant qu’organisation et s’adresse aux décideurs·euses auxquels·les il rend compte. Ceci étant dit, le présent document peut être utilisé par d’autres organisations patrimoniales ou gouvernementales pour établir des directives internes pour la publication d'URI.

## Contexte

### Travail sur les données ouvertes et liées au RCIP {#travail-sur-les-donnees-ouvertes-et-liees-au-rcip}

Le RCIP, conformément à son mandat qui consiste à appuyer les musées canadiens dans la documentation, la gestion et le partage de leurs collections, élabore actuellement des ressources permettant aux données canadiennes d’entrer dans l’écosystème des données ouvertes et liées (DOL), qui est de plus en plus utilisé par les personnes œuvrant dans le domaine du patrimoine du monde entier pour documenter les artefacts culturels. Les objectifs des projets du RCIP sont les suivants :

* Identification des entités patrimoniales (actants<sup>[1](#note-1)</sup>, objets) à travers l’utilisation d’identificateurs de ressources uniformes ou *unique resource identifiers* (URI);

*  Représentation des relations entre les actants et/ou les objets;

* Amélioration de l'information facilement disponible sur la culture matérielle en rapprochant les données provenant de différentes sources.

Les personnes ciblées sont les chercheurs·ses et les professionnels·les des secteurs du patrimoine, universitaire et de la sémantique, les galeries, les bibliothèques, les centres d'archives et les musées, ainsi que les outils logiciels adaptés à l’interprétation et à la mobilisation de ces données. L’industrie du patrimoine bénéficiera également de ce nouvel écosystème de données adapté grâce à l’accès à des données ouvertes et réutilisables lors du développement d’interfaces d’applications qui pourront à leur tour servir le grand public.

Le principal avantage des DOL est leur potentiel de répartir la charge de travail du RCIP et des parties prenantes en matière de données :

* En facilitant la recherche par les personnes qui les utilisent;

* En encourageant la documentation ouverte et sa consommation;

* En facilitant la mise en relation des informations par les chercheurs·ses, les publics et les membres de communautés spécifiques ou marginalisées dans une approche co-documentaire où toute personne est invitée à réutiliser les modèles et donc à rendre ses données accessibles et ouvertes;

* En rendant explicite la signification et la structure des bases de données ouvertes et liées par des relations significatives entre les jeux de données, plutôt que de s’appuyer uniquement sur la compréhension locale et implicite des données par les responsables du catalogage.

### Déclaration d’intention {#declaration-dintention}

Ce rapport technique est une incursion dans les considérations et les principes qui sous-tendent la gestion des URI au RCIP. En tant que tel, ce rapport met l’accent sur les éléments qui sont pertinents pour le RCIP en tant qu’organisation et s’adresse aux décisionnaires auxquels l’organisme rend compte. Cela dit, le présent document peut être utilisé par d’autres organisations patrimoniales ou gouvernementales pour établir des directives internes pour la publication d'URI.

Même si les meilleures pratiques et le consensus sur la meilleure façon de gérer les URI évolueront certainement avec le temps, étant donné que les URI sont destinés à être réutilisés par des parties prenantes externes dans le cadre de la communauté du Web sémantique, il est crucial que les URI publiés (et donc potentiellement réutilisés) restent inchangés afin de garantir la facilité d’utilisation, la pertinence ainsi que la fonctionnalité tant pour le RCIP que pour les parties prenantes qui réutilisent (ou réutiliseront) ses URI.

L’objectif principal de ce rapport est donc de déterminer comment nommer et gérer au mieux les URI. Il est divisé en trois sections principales :

* Principes d’organisation – une explication des concepts de base et des meilleures pratiques en matière de dénomination et de gestion des URI, basée sur une analyse documentaire des pratiques actuelles et des recommandations des principales organisations;

* Spécification du RCIP – un examen de la façon dont le RCIP nomme et traite les URI;

* Gestion – une présentation des questions relatives à la création, à la publication et à la maintenance des URI (en cours de développement; publication à venir dans une version ultérieure).

## Principes d’organisation

Un identificateur de ressource uniforme ou *unique resource identifier* (URI) est composé de quatre parties principales :

* Schéma : la partie de l’URI qui précède le `:` et précise le type d’application à utiliser (les schémas les plus courants sont http et https); les schémas d’URI doivent être enregistrés auprès de l’[Internet Assigned Numbers Authority (IANA)](https://www.iana.org/);

* Domaine : la partie de l’URI qui suit généralement le schéma et indique la propriété ou le contrôle d’une ressource (le format le plus courant est `nom-de-domaine.quelque-chose`); le format du nom de domaine doit être conforme au système de noms de domaine ainsi qu’aux politiques de l’organisation qui stocke et gère les URI (et qui possède le nom de domaine);

* Segment·s : les chaînes de caractères qui suivent le nom de domaine et sont liées par `/`; les segments précisent la catégorisation d’une ressource au sein d’un système et sont de préférence lisibles par les professionnels·les afin de faciliter leur compréhension (habituellement, les segments facilitent la navigation en identifiant les éléments d’un système auxquels une ressource appartient);

* Identifiant pour adresse URL : ce segment final est propre à la ressource et est le plus souvent opaque; il est parfois appelé le « segment final ».

La syntaxe d’un URI est donc la suivante :

``` 
schema://nom-de-domaine.dol/segment1/segment2/identifiant-pour-adresse-URL
```

Il existe plusieurs façons de structurer les URI afin qu’ils soient cohérents avec le système ou l’organisation dans lequel ou laquelle ils s’insèrent. Un examen des directives et spécifications internes doit être effectué afin de garantir la conformité avec les meilleures pratiques de l’organisation en matière de données.

Outre ces recommandations, les URI doivent être conformes aux trois principes suivants ([Berners-Lee 1998](#berners-lee-1998); [Sauermann et Cyganiak 2008](#sauermann-cyganiak-2008)) :

* *Stabilité* : Comme le but de l’URI est d’identifier une ressource de manière cohérente, il devrait rester inchangé afin de pouvoir être facilement récupéré. Il est donc recommandé de ne pas inclure dans les URI des unités propres à la mise en œuvre, comme `.php` ou `.asp`, afin qu’ils ne soient pas affectées par les changements opérationnels ou technologiques;

* *Simplicité* : Les URI étant utilisés par de multiples personnes dans un écosystème de DOL, et parfois au-delà d’une organisation, il est préférable d’utiliser des segments courts et mnémoniques afin de faciliter leur partage, leur utilisation et leur maintenance;

* *Gérabilité* : Les URI doivent être émis d’une manière compatible avec les besoins de l’organisation en matière de maintenance et de gestion (p. ex. en stockant les 303 URI dans un sous-domaine dédié afin de faciliter la migration du sous-système de gestion des URI par la suite).

En outre, il n’est pas toujours nécessaire de créer de nouveaux URI, notamment dans le cas de concepts communs (p. ex. les lieux, les rôles, les matériaux, etc.) qui font déjà partie de vocabulaires contrôlés dédiés et maintenus par des organisations réputées ([Archer, Goedertier et Loutas 2013, 41](#archer-et-al-2013)). Dans ce cas, il est conseillé de réutiliser les URI établis afin de minimiser les responsabilités de maintenance de l’organisation et de favoriser l’interopérabilité.

Enfin, pour les organisations qui souhaitent uniquement générer des URI pour leur contenu sans gérer la manière dont celui-ci sera présenté, il est possible d’utiliser des outils de base de génération et de gestion d’identifiants persistants tels que [ARK](http://n2t.net/e/ark_ids.html), [Handle](https://www.handle.net) ou [DOI](http://www.doi.org/) ([Koster 2020](#koster-2020)).

Cependant, pour les organisations qui souhaitent gérer la représentation d’une ressource qui sera fournie en fonction du contexte (c.-à-d. la négociation du contenu), de tels outils sont insuffisants et un système de génération d’URI dédié est conseillé (c’est le cas du RCIP).

## Spécification recommandée par le RCIP {#specification-recommandee-par-le-rcip}

Bien qu’il n’existe pas de politique particulière concernant les URI, le gouvernement canadien recommande de se fonder sur le document du Royaume-Uni [« Designing URI Sets for the UK Public Sector: A Report from the Public Sector Information Domain of the CTO Council’s cross-Government Enterprise Architecture »](https://assets.publishing.service.gov.uk/government/uploads/system/uploads/attachment_data/file/60975/designing-URI-sets-uk-public-sector.pdf). Ce dernier indique, entre autres, que :

* La longévité attendue et le potentiel de réutilisation des URI devraient être publiés, et les ensembles d’URI dont la réutilisation est encouragée devraient être conçus pour durer au moins 10 ans ([Chief Technology Officer Council 2009, 3](#chief-technology-officer-council-2009)).

* Le ministère ou l'agence chargé·e de définir et de nommer les instances doit en être responsable, mais son nom ne doit pas apparaître dans l’URI ([Chief Technology Officer Council 2009, 4](#chief-technology-officer-council-2009)). Cela dit, la personne chargée de l'édition doit avoir le contrôle du contenu du sous-domaine vers lequel l’ensemble d’URI se résout, et le domaine doit avoir des niveaux de service et une évolutivité, tout en sachant que le domaine sera maintenu à perpétuité; en d’autres termes, le « domaine lui-même devrait donner une assurance de qualité et de longévité » ([Chief Technology Officer Council 2009, 5](#chief-technology-officer-council-2009); notre traduction).

* Au moins une représentation sémantique doit permettre la construction d’un graphe RDF, bien qu’il soit recommandé de proposer des formats supplémentaires ([Chief Technology Officer Council 2009, 10](#chief-technology-officer-council-2009)).

En outre, les directives générales du gouvernement du Canada relatives à la publication d’autres contenus stipulent que le bilinguisme doit être intégré autant que possible dans les conventions de dénomination, bien que cela ne semble pas être obligatoire dans le cas des URI.

Pour ces raisons, le RCIP recommande une convention de dénomination basée sur les projets pour ses URI, tandis que les acronymes, abréviations et codes bilingues seront privilégiés par rapport aux codes monolingues (tant qu’ils facilitent la compréhension plutôt que de l’entraver).

Cette approche est applicable aux URI attribués à différents types de données qu’une organisation gère ([Henderson, Earley, et Sebastian-Coleman 2017, 422](#henderson-et-al-2017)), à savoir :

* *Descriptives* : données qui décrivent une ressource et permettent son identification et sa récupération (p. ex. définitions et descriptions de jeux de données, modèles et normes de données, notes et problèmes d’utilisation, etc.);

* *Structurelles* : données qui décrivent les relations au sein des ressources et entre celles-ci et leurs composants (noms de tableaux et de colonnes, autorisations d’accès, définitions de schémas de formats de fichiers, documentation de la mise en correspondance des données, calendriers de mise à jour et dépendances, règles de récupération et de sauvegarde, etc.);

* *Opérationnelles* : données utilisées pour gérer les ressources tout au long de leur cycle de vie (journaux d’exécution des tâches des programmes par lots, anomalies dans l'exécution de tâches planifiées, journaux d’erreurs, patrons volumétriques et d’utilisation, etc.).

Pour tous ces éléments, la négociation du contenu sera mise en place.

### Négociation de contenu – adresses URL dérivées d’URI {#negociation-de-contenu-adresses-url-derivees-duri}

Le concept fondamental de la négociation de contenu est la distinction entre l’URI d’une entité et ses manifestations, qui prennent généralement la forme de localisateurs de ressources uniformes ou *uniform resource locators* (URL, dont les formes ne sont pas régies par les mêmes principes que ceux des URI). Cela permet d’obtenir de nombreux rendus d'information en fonction des besoins de la personne qui les interroge.

Par exemple, le rendu sémantique d’un ensemble sera une réplique du graphe RDF où chaque instance aura une page HTML affichant l’intégralité des déclarations comportant l’instance. En revanche, une interface publique n’affiche que les informations jugées pertinentes par la requête (p. ex. il n’est pas nécessaire d’afficher l’URI de l’événement d’une naissance en plus de celle de la naissance elle-même).

Afin de différencier les diverses représentations des informations associées à un URI, ces représentations devraient utiliser le chemin d’accès le plus court à l’URI et y ajouter des informations pertinentes pour l’URL. Il existe deux types de représentations qui devraient être rendues accessibles au public : les représentations propres au format de données et les interfaces lisibles par l'humain.

#### Représentations propres au format de données {#representations-propres-au-format-de-donnees}

Les représentations d’entités propres au format de données permettent à une personne de consommer des informations dans le format de données qui répond le mieux à ses besoins, ce qui peut être précisé en ajoutant l’extension du format de fichier à la fin de l’URI selon le modèle suivant :

```
schema://nom-de-domaine.dol/segment/identifiant-pour-adresse-URL.extension-du-fichier

https://nom-du-projet.dol/code-de-lontologie_code-de-la-classe/ID-du-soumissionnaire_numero-aleatoire.extension-du-fichier
```

Pour un URI, cela se ferait comme suit :

```
schema://nom-de-domaine.dol/segment/identifiant-pour-adresse-URL

https://nom-du-projet.dol/code-de-lontologie_code-de-la-classe/ID-du-soumissionnaire_numero-aleatoire
```

Les représentations possibles seraient les suivantes :

```
schema://nom-de-domaine.dol/segment/identifiant-pour-adresse-URL

https://nom-du-projet.dol/code-de-lontologie_code-de-la-classe/ID-du-soumissionnaire_numero-aleatoire.html
```

```
schema://nom-de-domaine.dol/segment/identifiant-pour-adresse-URL.jsonld

https://nom-du-projet.dol/code-de-lontologie_code-de-la-classe/ID-du-soumissionnaire_numero-aleatoire.jsonld
```

```
schema://nom-de-domaine.dol/segment/identifiant-pour-adresse-URL

https://nom-du-projet.dol/code-de-lontologie_code-de-la-classe/ID-du-soumissionnaire_numero-aleatoire.rdf
```

```
schema://nom-de-domaine.dol/segment/identifiant-pour-adresse-URL

https://nom-du-projet.dol/code-de-lontologie_code-de-la-classe/ID-du-soumissionnaire_numero-aleatoire.ttl
```

De telles représentations n’afficheraient que les liens directs d’une entité ciblée. Par exemple, lors de l’affichage de données relatives à la naissance d’une personne, la représentation ne comprendrait que l’énoncé liant la personne à l’*événement* de sa naissance; pour connaître la *date* de cet événement, la personne interrogeant les données devrait suivre le chemin de l'URI menant à cette information.

#### Interfaces lisibles par l'humain

Les interfaces lisibles par l'humain des entités et des graphes de connaissances permettent une consommation conviviale de l'information par les personnes et peuvent être précisées en insérant un segment supplémentaire dans l’URI juste après le nom de domaine :

```
schema://nom-de-domaine.dol/segment/identifiant-pour-adresse-URL

https://nom-du-projet.dol/page-web/code-de-lontologie_code-de-la-classe/ID-du-soumissionnaire_numero-aleatoire
```

Des liens vers les représentations RDF susmentionnées peuvent être affichés sur la page Web lisible par l'humain d’une entité, en plus des autres représentations RDF. Il pourrait s’agir de représentations qui intégreraient dans un seul fichier toutes les déclarations et entités sémantiques nécessaires pour recueillir les informations affichées sur une page Web (pour offrir le chemin sémantique complet de la personne à sa date de naissance, par exemple).

Il est conseillé d’avoir une interface principale qui n’est pas propre à une entité pour que les personnes l'utilisant puissent y revenir si elles le souhaitent :

```
schema://nom-de-domaine.dol/page-web

https://nom-du-projet.dol/page-web
```

### Modèle d’URI {#modele-duri}

Un seul modèle d’URI peut être utilisé pour accueillir plusieurs types de données (descriptives, structurelles, opérationnelles). Cela dit, différents types d’URI peuvent nécessiter un modèle ciblé à des fins de mise en application. Dans le contexte des informations sur le patrimoine, les trois types d’URI les plus susceptibles d’être rencontrés sont les suivants :

* URI de contenu : utilisés pour stocker les données descriptives (données de base soumises et leurs métadonnées) dans un jeu de données;

* URI de vocabulaire : utilisés pour identifier les termes d’un vocabulaire ou d’un thésaurus correspondant;

* URI ontologiques : utilisés pour identifier les classes et les propriétés d’une ontologie. Parce qu’ils créent la couche de liaison fondamentale du modèle, les URI ontologiques utilisent souvent un modèle différent des autres URI commerciaux (contenu et vocabulaire) (p. ex. ils sont généralement créés à l’aide de signes \# plutôt que de signes /).

Tous ces éléments peuvent être générés à l’aide du modèle suivant<sup>[2](#note-2)</sup> :

```
https://nom-du-projet.dol/code-de-lontologie_code-de-la-classe/ID-du-soumissionnaire_numero-aleatoire
```

#### Schéma – Protocole sécurisé {#schema-protocole-securise}

Afin de garantir la sécurité sur le réseau et de se conformer aux meilleures pratiques actuelles, les URI seront accessibles sous le protocole de transfert hypertexte sécurisé ou Hypertext Transfer Protocol Secure (https).

#### Domaine – Axé sur les projets {#domaine-axe-sur-les-projets}

Le RCIP recommande d’utiliser le nom de l’organisation ou du projet principal qui supervise la gestion des URI comme nom de domaine pour plusieurs raisons :

* L’organisation qui gère les URI est clairement indiquée dans l’URI lui-même, ce qui facilite le travail des personnes qui auraient besoin de l’identifier ou de communiquer avec elle;

* L’accès à la page du projet à partir des URI est donc plus facile, car la personne l'utilisant peut simplement se référer à l’URL principale;

* Le nom de domaine d’un projet est généralement stable et ne changera pas au fil du temps, ce qui garantit la stabilité des URI.

Puisque le RCIP est situé sous le domaine canada.ca et qu’il n’a pas de nom de domaine indépendant et dédié, il n’est pas conseillé d’utiliser la position actuelle du RCIP dans le site Web canada.ca comme point de départ. Il est déconseillé d’utiliser le nom des ministères ou des agences comme domaine ou URI, car ils sont sujets à changement, autant au niveau de leur nom officiel que de leur position au sein du site Web gouvernemental et de l’organigramme.

Le RCIP a donc choisi d’utiliser une version abrégée du nom de son projet consacré à la gestion des données des collections comme nom de domaine, DOnnées Patrimoniales HEritage DAta (DOPHEDA) : `dopheda.info`. Ce dernier a été choisi parce qu’il est bilingue/alingue, court, facilement récupérable par les moteurs de recherche et indépendant de l’infrastructure de canada.ca (c.-à-d. hébergé sur un domaine dédié).

#### Segments – Significatifs pour l’organisation {#segments-significatifs-pour-lorganisation}

Les segments sont les éléments du chemin de l’URI où, typiquement, une négociation se produit entre la signification (qui confère la lisibilité) et l’opacité (qui confère la durabilité en isolant l’élément de sa compréhension conceptuelle, qui peut changer avec le temps).

Un URI est considéré comme significatif lorsqu’il contient des données lisibles décrivant la ressource qu’il détermine (p. ex. un URI significatif pour la ville d’Ottawa pourrait contenir « ottawa » ou un code postal), de sorte qu’il soit facilement lisible et compréhensible par les personnes s'y référant. Cependant, le fait de se baser uniquement sur des éléments significatifs pour les segments à venir induit un risque d’ambiguïté (p. ex. confondre la ville d’Ottawa, située au Canada, et celle du même nom située dans l’Illinois, aux États-Unis). Ce problème se pose également pour toute donnée susceptible de changer, car le nom de la ville peut changer au fil du temps (p. ex. ce qui était autrefois la ville de Vanier fait maintenant partie de la ville d’Ottawa).

Un URI est considéré comme opaque lorsque ses segments sont complètement déconnectés du contenu identifié par la ressource (p. ex. une chaîne de chiffres aléatoire), de sorte qu’elle est pérenne et alingue en englobant facilement plusieurs appellations d’une même entité (p. ex. un chiffre aléatoire peut être utilisé pour désigner Istanbul, Constantinople et Byzance à la fois). Cependant, les URI totalement opaques sont difficiles à lire, à comprendre et à gérer pour les personnes, surtout dans les contextes où elles doivent mobiliser les technologies de DOL sans en avoir une connaissance experte.

Le RCIP recommande donc l’utilisation d’une combinaison de segments significatifs et opaques pour assurer à la fois la lisibilité et la durabilité technique. La meilleure façon de mettre ceci en application consiste à choisir un système de classification complémentaire à l’écosystème de données de l’organisation et à en utiliser une version concise pour spécifier les segments de contenu, la dernière partie de l’URI (la plus spécifique à la ressource) étant un numéro opaque.

Dans le cas du RCIP, les URI de contenu utiliseront des abréviations d’ontologie et des codes de classe afin de clarifier la façon dont la ressource est classée dans l’écosystème DOPHEDA (en utilisant la syntaxe `abreviation-de-lontologie_code-de-la-classe`). De cette façon, les entités d’une classe spécifique partageront le même chemin, ce qui est cohérent avec le modèle axé sur les événements du CIDOC CRM (qui est la base de DOPHEDA).

Dans la plupart des cas, il s’agira de réutiliser les codes de classe CIDOC CRM (en utilisant la syntaxe `crm_exx`). Dans les cas où d’autres ontologies qui n’ont pas de codes officiels sont utilisées, un répertoire sera maintenu par le RCIP en utilisant la syntaxe `abreviation-de-lontologie_numero-de-la-classe`. Cela facilitera l’utilisation en même temps que cela répondra aux préoccupations sur le bilinguisme et résoudra les problèmes qui pourraient survenir si l’ontologie changeait le nom de la classe. Pour les mêmes raisons, il est conseillé de prioriser l’utilisation de codes de super-classes significatifs dans les URI plutôt qu’à des classes de niveau supérieur (qui englobent tellement de concepts qu’elles n’apportent aucune compréhension substantielle) ou à des sous-classes plus précises (qui sont plus susceptibles de changer). Des exemples de tels segments seraient :

```
/crm_e39/

/prov_1/

/skos_1/
```

Les classes principales les plus susceptibles d’être utilisées sont les suivantes :

* `E4_Période` (`/crm_e4/`)

* `E5_Évènement` (`/crm_e5/`)

* `E18_Chose_matérielle` (`/crm_e18/`)

* `E28_Objet_conceptuel` (`/crm_e28/`)

* `E39_Actant` (`/crm_e39/`)

* `E41_Appellation` (`/crm_e41/`)

* `E52_Intervalle_temporel` (`/crm_e52/`)

* `E53_Lieu` (`/crm_e53/`)

* `E55_Type` (`/crm_e55/`)

* `E63_Début_d'existence` (`/crm_e63/`)

* `E64_Fin_d'existence` (`/crm_e64/`)

Dans les cas où plusieurs classes sont utilisées pour identifier une entité unique, un seul URI doit être créé selon les règles établies par l’organisation. Dans le cas du RCIP, étant donné que cette double instanciation est rare et ne se produira probablement pas souvent, cela sera déterminé au cas par cas<sup>[3](#note-3)</sup>.

#### Identifiant pour adresse URL – Semi-Opaque {#identifiant-pour-adresse-url-semi-opaque}

Les mêmes considérations qui s’appliquent aux segments s’appliquent aux identifiants pour adresse URL. Dans le cas des URI descriptifs du RCIP, deux besoins principaux doivent être pris en compte dans les identifiants pour adresse URL : la possibilité d’identifier le soumissionnaire des données associées à l’URI et la nécessité d’identifier la ressource de façon unique. Les identifiants pour adresse URL auront donc le format `providerIDSoumissionnaire_numeroAleatoirerandomNumber`, alors que le RCIP maintiendra un répertoire des numéros d’identification des soumissionnaires de données (attribués sur une base incrémentielle) et des numéros aléatoires seront attribués à la dernière partie de l'identifiant pour adresse URL pour établir l’unicité (plusieurs outils, tels que [NOID](https://n2t.net/e/noid.html) ou [UUID](https://www.uuidgenerator.net/), peuvent être utilisés pour générer ces numéros aléatoires). Cela permettra de :

* S’assurer de la non-duplicité des identifiants créés;

* Rationaliser les requêtes relatives à la provenance des données;

* Faciliter les protocoles de maintenance et de mise à jour des jeux de données.

Il est recommandé d’utiliser un numéro unique (attribué de manière aléatoire ou incrémentielle) comme identifiant pour adresse URL complet ou partiel. Si une partie lisible est ajoutée à l'identifiant pour adresse URL, elle doit être significative pour l’organisme gestionnaire et répondre à un besoin clair de sa part.

## Gestion

Cette question est actuellement examinée par le RCIP et sera ajoutée dès que sa rédaction sera terminée. Elle abordera ce qui suit :

* Quels URI seront sous la garde du RCIP et lesquels ne seront mobilisés que par lui;

* Comment les URI seront exploités dans l’écosystème de DOL du RCIP;

* Quels seront les principes de création et de maintenance;

* Quels sont les principes et/ou protocoles pertinents envisagés en matière d’intégrité et de sécurité.

Pour tout commentaire ou demande d'information, n’hésitez pas à nous contacter à l’adresse <rcip-chin@pch.gc.ca> en indiquant comme objet « Rapport technique sur les URI ».

---

#### Notes

<a name="note-1"></a><sup>1</sup> Par actants, on entend ici les personnes, les entreprises, les groupes, les institutions et tout autre agent actif.

<a name="note-2"></a><sup>2</sup> C’est l’approche que le RCIP adoptera pour le moment, bien que d’autres recherches sur les URI d’ontologie seront menées dans les mois à venir, et qu’un modèle dédié pourrait être conçu à la suite de ces recherches.

<a name="note-3"></a><sup>3</sup> Une fois que le modèle aura été étendu et que d’autres cas d’utilisation émergeront, une hiérarchie de classes pourrait être établie à cet effet.

--- 

## Bibliographie

<a name="archer-et-al-2013"></a>Archer, Phil, Stijn Goedertier et Nikolaos Loutas. « Study on Persistent URIs, with Identification of the Best Practices and Recommendations on the Topic for the MSs and the EC ». *D7.1.3. ISA - Interoperability Solutions for European Public Administrations*. Bruxelles, BE : Commission européenne, 2013. [https://joinup.ec.europa.eu/sites/default/files/document/2013-02/D7.1.3%20-%20Study%20on%20persistent%20URIs.pdf](https://joinup.ec.europa.eu/sites/default/files/document/2013-02/D7.1.3%20-%20Study%20on%20persistent%20URIs.pdf).

<a name="berners-lee-1998"></a>Berners-Lee, Tim. « Cool URIs Don’t Change ». Style W3C. 1998. [https://www.w3.org/Provider/Style/URI](https://www.w3.org/Provider/Style/URI).

<a name="ca-digital-library-2020a"></a>California Digital Library. « Archival Resource Key (ARK) Identifiers ». *N2T* (Name to Thing). 2020a. [http://n2t.net/e/ark\_ids.html](http://n2t.net/e/ark_ids.html).

<a name="ca-digital-library-2020b"></a>---« Nice Opaque Identifiers (NOID) ». N2T (Name to Thing). 2020b. [https://n2t.net/e/noid.html](https://n2t.net/e/noid.html).

<a name="chief-technology-officer-council-2009"></a>Chief Technology Officer Council. *Designing URI Sets for the UK Public Sector: A Report from the Public Sector Information Domain of the CTO Council’s Cross-Government Enterprise Architecture*. United Kingdom Chief Technology Officer Council, 2009. [https://assets.publishing.service.gov.uk/government/uploads/system/uploads/attachment\_data/file/60975/designing-URI-sets-uk-public-sector.pdf](https://assets.publishing.service.gov.uk/government/uploads/system/uploads/attachment_data/file/60975/designing-URI-sets-uk-public-sector.pdf).

<a name="corp-national-research-initiatives-2020"></a>Corporation for National Research Initiatives. « Handle Registry ». *Handle*. 2020. [https://www.handle.net/](https://www.handle.net/).

<a name="henderson-et-al-2017"></a>Henderson, Deborah, Susan Earley, et Laura Sebastian-Coleman, eds. *DAMA-DMBOK: Data Management Body of Knowledge*. 2e éd. Basking Ridge, NJ : Technics Publications, 2017.

<a name="doi-2020"></a>International DOI Foundation. « DOI ». DOI. 2020. [https://www.doi.org/](https://www.doi.org/).

<a name="icann-2020"></a>Internet Corporation for Assigned Names and Numbers (ICANN). « Internet Assigned Numbers Authority (IANA) ». IANA. 2020. [https://www.iana.org/](https://www.iana.org/).

<a name="koster-2020"></a>Koster, Lukas. « Persistent Identifiers for Heritage Objects ». *The Code4Lib Journal*, no. 47 (février 2020). [https://journal.code4lib.org/articles/14978](https://journal.code4lib.org/articles/14978).

<a name="uuid-generator-2020"></a> « Online UUID Generator Tool ». UUID Generator. 2020. [https://www.uuidgenerator.net/api](https://www.uuidgenerator.net/api).

<a name="sauermann-cyganiak-2008"></a>Sauermann, Leo, et Richard Cyganiak. « Cool URIs for the Semantic Web ». W3C Interest Group Note. 2008. [https://www.w3.org/TR/cooluris/](https://www.w3.org/TR/cooluris/).

<a name="w3c-2014"></a>W3C. « URI Design and Management for Persistence ». Data on the Web Best Practices. 2014. [https://www.w3.org/2013/dwbp/wiki/URI\_Design\_and\_Management\_for\_Persistence](https://www.w3.org/2013/dwbp/wiki/URI_Design_and_Management_for_Persistence).

