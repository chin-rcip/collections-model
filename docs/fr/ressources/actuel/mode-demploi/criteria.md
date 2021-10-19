---
layout: page
language: fr
title: Mode d’emploi - CRITERIA
permalink: /fr/ressources/actuel/mode-demploi/criteria
other_link: /en/resources/current/how-to/criteria
sidebar: criteriafr
group: ressources
subgroup: mode d'emploi
date: 2021-06-14
description: Ce document présente un aperçu de ce que CRITERIA offre comme fonctionnalités ainsi que les instructions à suivre pour utiliser l’outil.
---


**Version** : 1.0

**Créé le** : 2021-04-19

**Mis à jour** : 2021-07-23

**Résumé** : Ce document présente un aperçu de ce que CRITERIA offre comme fonctionnalités ainsi que les instructions à suivre pour utiliser l’outil.

**Pour information** : Si vous avez des questions ou des commentaires sur CRITERIA, veuillez consulter la section [Issues](https://github.com/chin-rcip/CRITERIA/issues) (et créez une nouvelle problématique « Issue » si pertinent) ou communiquez avec nous par courriel, à l’adresse [rcip-chin@pch.gc.ca](mailto:rcip-chin@pch.gc.ca). Indiquez « CRITERIA » en objet.


## Utilisation principale

  - Convertir des documents RDF fondés sur [CIDOC CRM](http://www.cidoc-crm.org/) en documents Markdown (syntaxe [Mermaid](https://mermaid-js.github.io/mermaid/#/)).

## Contexte

**CRITERIA** (acronyme anglais de **C**idoc c**R**m **I**n **T**riples m**ER**maid d**I**agr**A**ms) est un outil créé en Python qui convertit des documents de tout format (json-ld, ttl, etc.) fondés sur le [CIDOC CRM](http://www.cidoc-crm.org/)) en documents Markdown (syntaxe [Mermaid](https://mermaid-js.github.io/mermaid/#/), extension .mmd), qu’un script Javascript Mermaid peut ensuite convertir en organigramme.

## Vocabulaire de base et connaissances préalables {#vocabulaire-de-base-et-connaissances-prealables}

Avant de poursuivre, tout utilisateur doit bien comprendre les termes et technologies suivants :

  - [Instance](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#instance-nom-feminin)

  - [Ontologie](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#ontologie-nom-feminin)

  - [Patron conceptuel](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#patron-conceptuel-nom-masculin)

  - [Modèle de données](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#modele-nom-masculin)

  - [Classe](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#classe-nom-feminin) et [Propriété](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#propriete-nom-feminin)

  - [RDF](https://www.w3.org/RDF/) et ses divers formats, notamment [Turtle](https://www.w3.org/TR/turtle/) et [JSON-LD](https://json-ld.org/)

  - [URI](https://fr.wikipedia.org/wiki/Uniform_Resource_Identifier)

CRITERIA peut créer deux types de diagrammes à partir des mêmes données RDF. Prenons par exemple les données RDF suivantes, sur la naissance et le décès de Marc-Aurèle Fortin :

```turtle
@prefix crm: <http://www.cidoc-crm.org/cidoc-crm/> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<https://www.chin-rcip.ca/e39/0001> a crm:E21_Person ;
  rdfs:label "Marc-Aurèle Fortin (1888-1970)"^^xsd:string ;
  crm:P98i_was_born <https://www.chin-rcip.ca/e2/0001> ;
  crm:P100i_died_in <https://www.chin-rcip.ca/e2/0002> .
<https://www.chin-rcip.ca/e2/0001> a crm:E67_Birth ;
  crm:P4_has_time-span <https://www.chin-rcip.ca/e52/0001> ;
  crm:P7_took_place_at <https://www.chin-rcip.ca/e53/0001> ;
  crm:P96_by_mother <https://www.chin-rcip.ca/e39/0002> ;
  crm:P97_from_father <https://www.chin-rcip.ca/e39/0003> .
<https://www.chin-rcip.ca/e2/0002> a crm:E69_Death ;
  crm:P4_has_time-span <https://www.chin-rcip.ca/e52/0002> ;
  crm:P7_took_place_at <https://www.chin-rcip.ca/e53/0002> .
<https://www.chin-rcip.ca/e52/0001> a crm:E52_Time-Span ;
  crm:P82a_begin_of_the_begin "1888-03-14T00:00:00"^^xsd:dateTime ;
  crm:P82b_end_of_the_end "1888-03-14T23:59:59"^^xsd:dateTime .
<https://www.chin-rcip.ca/e52/0002> a crm:E52_Time-Span ;
  crm:P82a_begin_of_the_begin "1970-03-02T00:00:00"^^xsd:dateTime ;
  crm:P82b_end_of_the_end "1970-03-02T23:59:59"^^xsd:dateTime .
<https://www.chin-rcip.ca/e53/0001> a crm:E53_Place ;
  rdfs:label "Laval, Québec"^^xsd:string .
<https://www.chin-rcip.ca/e53/0002> a crm:E53_Place ;
  rdfs:label "Macamic, Québec"^^xsd:string .
<https://www.chin-rcip.ca/e39/0002> a crm:E21_Person ;
  rdfs:label "Amanda Fortier (1861-1953)"^^xsd:string .
<https://www.chin-rcip.ca/e39/0003> a crm:E21_Person ;
  rdfs:label "Thomas Fortin (1853-1933)"^^xsd:string .
```

  - **Instance :** type de diagramme qui comprend toutes les instances que renferme le document RDF, c’est-à-dire les URIs et les valeurs littérales.

![](/collections-model/images/criteria_1.png)

  - **Ontologie :** type de diagramme qui ne comprend que les classes et leurs propriétés, c’est-à-dire le volet « ontologie » d’un patron conceptuel. Par « classe », on entend l’objet (du triplet) de la propriété `rdf:type`. Par conséquent, il est impossible de créer ce type de diagramme si une instance n’appartient à aucune classe.

![](/collections-model/images/criteria_2.png)

## Auditoires visés {#auditoires-vises}

CRITERIA est un outil de visualisation de données liées. Il se prête toutefois mal à la visualisation de tout un ensemble de données ou d’un modèle de données complet se rapportant à une seule entité. Voici pourquoi :

1. le format Mermaid dispose les nœuds de même niveau à l’horizontale ou à la verticale dans l’organigramme, ce qui rend rapidement ce dernier illisible;

2. les niveaux sont présentés de haut en bas ou de gauche à droite; il est donc difficile de distinguer les liens entre des nœuds qui ne se suivent pas.

Par exemple, il ne faudrait pas utiliser CRITERIA pour visualiser toutes les données (nom, naissance, décès, nationalité, etc.) sur l’artiste canadienne Emily Carr. En d’autres termes, cet outil sert à illustrer à l’aide de diagrammes des patrons conceptuels précis d’un modèle de données (patrons d’appellations, de naissances ou de décès, par exemple). Il intéresse donc divers groupes d’utilisateurs.

  - *Ontologistes et modélisateurs de données *: les personnes qui conçoivent ou créent des modèles de données peuvent se servir de CRITERIA pour visualiser leurs modèles afin de les valider.

  - *Utilisateurs (incluant les néophytes) du CIDOC CRM *: les personnes qui veulent mieux comprendre les ontologies du CIDOC CRM peuvent visualiser une sérialisation RDF existante, puisque CRITERIA a été créé à partir du CIDOC CRM de base et de certaines de ses extensions. Le schème de couleurs du CIDOC CRM est le style appliqué par défaut.

  - *Développeurs de logiciels ou de contenu *: les personnes chargées de produire la documentation sur un modèle de données ou de le tenir à jour sous forme numérique peuvent utiliser CRITERIA pour intégrer automatiquement dans leur environnement une visualisation des patrons conceptuels. Ces utilisateurs seront particulièrement intéressés par l’utilisation en [ligne de commande](https://docs.google.com/document/d/1BCWZAtljnQag212G7hsHwfjvvsDwplLfjOh7gfODPLQ/edit#heading=h.17dp8vu) de cet outil.

## Instructions

On peut utiliser CRITERIA de deux façons : par une démonstrateur en ligne ou par ligne de commande.

### Démonstrateur en ligne {#demonstrateur-en-ligne}

Le [démonstrateur en ligne](http://chinrcip.pythonanywhere.com), en anglais seulement, intéressera surtout ceux et celles qui désirent créer rapidement des diagrammes.

Dans le cas des données JSON-LD, le démonstrateur en temps réel peut traiter les [contextes](https://w3c.github.io/json-ld-syntax/#the-context) tant intégrés au document que ceux auxquels le document fait référence par URL (comme le [contexte Linked.art](https://linked.art/ns/v1/linked-art.json)).

#### Navigateurs recommandés {#navigateurs-recommandes}

  - **MacOS :** Safari, Chrome ou Firefox

  - **Windows :** Firefox

#### Utilisation

Après avoir lancé le démonstrateur en ligne :

1. Coller les données RDF dans le champ d’édition qui peut mettre en évidence toute erreur de syntaxe.

2. Choisir le format RDF dans la liste déroulante.

3. Choisir le type de diagramme : Instance ou Ontologie.

4. Cliquer sur « Convert » (convertir).

5. Pour agrandir ou réduire le diagramme, cliquer sur celui-ci.

6. Pour télécharger le diagramme en format PNG ou SVG, cliquer sur le bouton correspondant.

![](/collections-model/images/criteria_3.png)

### Interface en ligne de commande

Cette méthode intéressera surtout les utilisateurs voulant utiliser CRITERIA de façon automatisée, comme dans le traitement par lots ou la mise en œuvre dans un système plus élaboré.

#### Installation

Pour installer l’outil, cloner [son répertoire](https://github.com/chin-rcip/CRITERIA) ou télécharger celui-ci en fichier Zip.

#### Dépendances {#dependances}

Pour exécuter l’outil, les versions du langage de programmation et les bibliothèques suivantes sont nécessaires :

  - [Python 3.7.0](https://www.python.org/downloads/release/python-370/)

  - [rdflib 5.0.0](https://rdflib.readthedocs.io/en/stable/gettingstarted.html) ([license BSD 3](https://github.com/RDFLib/rdflib/blob/master/LICENSE))

  - [rdflib - 0.5.0](https://github.com/RDFLib/rdflib-jsonld) ([license BSD 3](https://github.com/RDFLib/rdflib-jsonld/blob/master/LICENSE.md))

#### Utilisation {#utilisation-1}

***criteria.py***

1. Ouvrir le répertoire `/CRITERIA` cloné ou téléchargé sur votre poste de travail.

    `$ cd /path/to/CRITERIA`

2. Exécuter : `$ python criteria.py [type] [rdf] [mmd]`

    - `[type]`: Le type de diagramme ne peut être que **instance** ou **ontology**.
    - `[rdf]`: `/chemin/vers/le/fichier/RDF/intrant`. Tel qu’installé ou téléchargé, CRITERIA comprend le sous-répertoire **rdf** où copier les fichiers RDF. Ensuite, préciser `./rdf/fichier_RDF_intrant.ttl`. On peut aussi indiquer le chemin d’accès complet d’un fichier s’il ne se trouve pas dans ce sous-répertoire : `/chemin/complet/du/répertoire/fichier_RDF_intrant.ttl`. L’outil peut traiter **plusieurs formats RDF**, comme Turtle, NTriples, RDF/XML, Trig ou JSON-LD.
    - `[mmd]`: `/chemin/du/répertoire/extrant`. Tel qu’installé ou téléchargé, CRITERIA comprend le sous-répertoire **mmd** où sauvegarder les fichiers mermaid (.mmd) extrants : `./mmd/fichier_MMD_extrant.ttl`. On peut aussi préciser le chemin d’accès complet d’un répertoire où sauvegarder le fichier extrant : `/chemin/complet/du/répertoire/fichier_MMD_extrant.ttl`.

    **Remarque :** Le script traite les triplets en ordre aléatoire; par conséquent, l’utilisateur n’a aucun contrôle sur l’ordre de présentation du fichier mermaid extrant. Cela signifie aussi qu’exécuter le script plusieurs fois à partir d’un même document RDF crée des documents Mermaid légèrement différents (l’ordre des énoncés y diffère), ce qui crée des diagrammes différents, car l’ordre des nœuds de même niveau sera différent. L’emplacement du nœud principal et la hiérarchie restent toutefois identiques.

3. Une fois le fichier mermaid extrant créé, générer le diagramme en procédant comme suit :

    - coller intégralement le contenu du fichier mermaid Markdown dans le champ de code de [l’éditeur Mermaid en ligne](https://mermaid-js.github.io/mermaid-live-editor); cet utilitaire permet de télécharger le diagramme correspondant en formats PNG ou SVG; ou
    - intégrer le code Markdown dans le code source du site Web et créer le diagramme à l’aide de [Mermaid.js](https://mermaid-js.github.io/mermaid/#/n00b-gettingStarted?id=_3-deploying-mermaid-on-the-browser).

    **Exemple :**
    - Voici la commande servant à générer un diagramme d’instances à partir du fichier RDF `BirthDeath_Fortin.ttl` dans le répertoire `./rdf` et l’enregistrer dans le répertoire `./mmd` :
    ```shell
    $ python criteria.py instance ./rdf/BirthDeath_Fortin.ttl ./mmd/BirthDeath_Fortin.mmd
    ```

    - Voici la commande servant à ne générer que l’ontologie à partir du même fichier et à l’enregistrer dans le même répertoire :
    ```shell
    $ python criteria.py ontology ./rdf/BirthDeath_Fortin.ttl ./mmd/BirthDeath_onto.mmd
    ```

***Schème de couleurs***

Comme l’a proposé George Bruseker, le style par défaut est fondé sur le schème de couleurs du CIDOC CRM. Les gabarits de styles, dans le répertoire `/src/templates/`, contiennent les classes Mermaid prédéfinies et les couleurs correspondantes.

  - `instance.mmd`: gabarit de styles pour les diagrammes d’instances.

  - `ontology.mmd`: gabarit de styles pour les diagrammes d’ontologies.

Pour modifier ce schème de couleurs, modifier les valeurs des paramètres **fill** et **stroke**.

Voici un exemple tiré du modèle des instances :

Fichier d’origine :

<div class="language-plaintext highlighter-rouge">
  <div class="highlight"><pre class="highlight">
    <code>
graph TD

classDef Literal fill:#f2f2f2,stroke:#000000;

classDef CRM_Entity fill:<strong>#FFFFFF</strong>,stroke:#000000;

classDef CRM_Entity_URI fill:<strong>#FFFFFF</strong>,stroke:#000000;
</code></pre></div></div>

Fichier modifié :

<div class="language-plaintext highlighter-rouge">
  <div class="highlight"><pre class="highlight">
    <code>
graph TD

classDef Literal fill:#f2f2f2,stroke:#000000;

classDef CRM_Entity fill:<strong>#ecb3ff</strong>,stroke:#000000;

classDef CRM_Entity_URI fill:<strong>#d24dff</strong>,stroke:#000000;
</code></pre></div></div>

<table>
<tbody>
<tr class="odd">
<td><p>🚩 <em>Avertissement</em></p>
<p><strong>NE JAMAIS</strong> <strong>modifier le nom, l’emplacement des fichiers gabarits</strong> ni le <strong>nom des classes Mermaid</strong>, à moins de vouloir modifier aussi le code source de criteria.py!</p></td>
</tr>
</tbody>
</table>

***Ontologies source (en anglais)***

CRITERIA est installé avec plusieurs ontologies CIDOC CRM par défaut en format RDF; elles se trouvent dans le répertoire `/src/ontologies/`.

  - [CIDOC CRM (v6.2.1)](http://www.cidoc-crm.org/Version/version-6.2.1)

  - [FRBRoo (v2.4)](http://www.cidoc-crm.org/frbroo/ModelVersion/frbroo-v.-2.4)

  - [CRMpc (v1.1)](http://www.cidoc-crm.org/Version/version-6.2)

  - CRMdig (v3.2.2) (téléchargée du site [3m du FORTH](https://isl.ics.forth.gr/3M/)).

<table>
<tbody>
<tr class="odd">
<td><p>🚩 <em>Avertissement</em></p>
<ul>
<li>
<p>La suppression ou l’ajout d’ontologies est actuellement IMPOSSIBLE. Par défaut, CRITERIA ne peut traiter que les ontologies incluses.</p>
</li>
<li>
<p>S’assurer donc que les classes des documents RDF intrants <strong>correspondent</strong> aux classes des ontologies (fichiers .rdfs).</p>
</li>
</ul>
<p>Si par exemple le fichier .ttl intrant désigne la classe « E24_Physical_Human-Made_Thing » mais que l’ontologie la nomme « E24_Physical_Man-Made_Thing », il faut modifier le fichier intrant ou l’ontologie, par souci d’uniformité.</p></td>
</tr>
</tbody>
</table>

## Aide-mémoire {#aide-memoire}

  - [Lien vers le démonstrateur en ligne](http://chinrcip.pythonanywhere.com)

  - Syntaxe en ligne de commande : `$ python criteria.py [type] [rdf] [mmd]`

## Pour en savoir plus

  - [Mermaid](https://mermaid-js.github.io/mermaid/#/)

  - [RDFLib](http://rdflib.readthedocs.org)

## Licence

CRITERIA est distribué en vertu de la [licence MIT](https://github.com/chin-rcip/CRITERIA/blob/master/LICENSE). Pour satisfaire aux exigences relatives à son attribution, vous devez préciser comme suit le détenteur du droit d’auteur :

> Copyright (c) 2020 Canadian Heritage Information Network, Canadian Heritage, Government of Canada – Réseau canadien d'information sur le patrimoine, Patrimoine canadien, Gouvernement du Canada

## Utilisateurs dignes de mention

Le RCIP veut remercier les responsables de projets et les institutions qui utilisent CRITERIA; nous ne pourrions pas améliorer cet outil sans leur contribution. Si vous utilisez CRITERIA mais que votre projet est absent de la liste ci-dessous, n’hésitez pas à [communiquer avec nous](#kix.xmzgkpdo17zb).

**Projet :** [Reference Data Models](http://docs.swissartresearch.net/) (en anglais seulement)

Organisme : [Swiss Art Research Infrastructure, University of Zurich](http://swissartresearch.net/)

Description ([Source](https://docs.swissartresearch.net/)) :

> Le projet des modèles de données sémantiques de référence a pour but de créer un ensemble de modèles de patrons conceptuels sémantiques réutilisables afin de simplifier l’intégration et la recherche des sources de données sur le patrimoine culturel. Chaque modèle consiste en une série de patrons conceptuels sémantiques fondés sur l’analyse de sources choisies jugées pertinentes à une entité. Aux fins de compatibilité avec l’ensemble du domaine patrimonial, ces patrons conceptuels sémantiques correspondent à l’ontologie CIDOC CRM et peuvent servir d’applications de référence aux institutions et responsables de projets peu familiers avec le CIDOC CRM. En effet, il est possible de les utiliser comme modèles pour développer des interfaces de saisie de données sémantiques créées nativement à partir du CRM. De plus, ces patrons conceptuels peuvent servir à transformer des sources existantes vers un modèle de référence conforme au CIDOC CRM, à l’aide d’un outil tel que 3M.

## Bibliographie

Beckett, David, Tim Berners-Lee, Eric Prud’hommeaux, et Gavin Carothers. sans date. “RDF 1.1 Turtle.” Consulté le 28 mai 2021. [https://www.w3.org/TR/turtle/](https://www.w3.org/TR/turtle/).

Réseau canadien d’information sur le patrimoine (RCIP). 2021a. « classe (nom féminin) ». Dans le *Glossaire*. Ottawa, Ont. : Gouvernement du Canada / Government of Canada. [https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#classe-nom-feminin](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#classe-nom-feminin)

———. 2021b. « instance (nom féminin) ». Dans le *Glossaire*. Ottawa, Ont. : Gouvernement du Canada / Government of Canada. [https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#instance-nom-feminin](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#instance-nom-feminin)

———. 2021c. « modèle (nom masculin) ». Dans le *Glossaire*. Ottawa, Ont. : Gouvernement du Canada / Government of Canada. [https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#modele-nom-masculin](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#modele-nom-masculin)

———. 2021d. « ontologie (nom féminin) ». Dans le *Glossaire*. Ottawa, Ont. : Gouvernement du Canada / Government of Canada. [https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#ontologie-nom-feminin](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#ontologie-nom-feminin)

———. 2021e. « patron conceptuel (nom masculin) ». Dans le *Glossaire*. Ottawa, Ont. : Gouvernement du Canada / Government of Canada. [https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#patron-conceptuel-nom-masculin](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#patron-conceptuel-nom-masculin)

———. 2021f. « propriété (nom féminin) ». Dans le *Glossaire*. Ottawa, Ont. : Gouvernement du Canada / Government of Canada. [https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#propriete-nom-feminin](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#propriete-nom-feminin)

JSON-LD Working Group. 2014. “JSON-LD - JSON for Linking Data.” LFQ 16 janvier 2014. https://json-ld.org/.

linked.art. 2020. “Linked Art.” Linked Art. 30 janvier 2020. https://linked.art/.

RDF Working Group. 2014. “RDF - Semantic Web Standards.” W3C. 25 février 2014. https://www.w3.org/RDF/.

RDFLib Team. sans date. “Rdflib 5.0.0 — Rdflib 5.0.0 Documentation.” Consulté le 28 mai 2021. https://rdflib.readthedocs.io/en/stable/.

Sveidqvist, Knut. sans date. “Mermaid - Markdownish Syntax for Generating Flowcharts, Sequence Diagrams, Class Diagrams, Gantt Charts and Git Graphs.” Consulté le 28 mai 2021. https://mermaid-js.github.io/mermaid/#/.

Swiss Art Research Infrastructure. sans date. “SARI Documentation.” Consulté le 28 mai 2021. https://docs.swissartresearch.net/.

Wikipédia 2020. “Uniform Resource Identifier.” Wikipédia. San Francisco (Californie) Wikipédia. https://fr.wikipedia.org/wiki/Uniform_Resource_Identifier.
