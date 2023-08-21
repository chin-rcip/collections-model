---
layout: page
language: fr
title: Mode d’emploi - CRITERIA
permalink: /fr/ressources/actuel/mode-demploi/criteria
other_link: /en/resources/current/how-to/criteria
sidebar: criteriafr
group: ressources
subgroup: mode d'emploi
date: 2022-11-17
description: Ce document présente un aperçu de ce que CRITERIA offre comme fonctionnalités ainsi que les instructions à suivre pour utiliser l’outil.
---

**Version** : 2.0

**Date de création** : 2021-04-19

**Dernière mise à jour** : 2022-11-17

**Pour information** : Si vous avez des questions ou des commentaires sur CRITERIA, veuillez consulter la section [Enjeux](https://github.com/chin-rcip/CRITERIA/issues) (et créer un nouvel Enjeu si c'est pertinent) ou nous contacter par courriel à l’adresse [pch.RCIP-CHIN.pch@canada.ca](mailto:pch.RCIP-CHIN.pch@canada.ca) avec « CRITERIA » comme objet.

## Utilisation principale

  - Convertir des documents RDF fondés sur [CIDOC CRM](http://www.cidoc-crm.org/) (en anglais seulement) en documents Markdown (syntaxe [Mermaid](https://mermaid-js.github.io/mermaid/#/) (en anglais seulement )).

## Contexte

**CRITERIA** (acronyme anglais de **C**idoc c**R**m **I**n **T**riples m**ER**maid d**I**agr**A**ms) est un outil créé en Python qui convertit des documents de tout format (.json-ld, .ttl, etc.) fondés sur le [CIDOC CRM](http://www.cidoc-crm.org/) (en anglais seulement) en documents Markdown (syntaxe [Mermaid](https://mermaid-js.github.io/mermaid/#/) (en anglais seulement), extension .mmd), qu’un script Javascript Mermaid peut ensuite convertir en organigramme.

## Vocabulaire de base et connaissances préalables {#vocabulaire-de-base-et-connaissances-prealables}

Avant de poursuivre, toute personne utilisant l'outil doit bien comprendre les termes et technologies suivants :

  - [Instance](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#instance-nom-feminin)

  - [Ontologie](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#ontologie-nom-feminin)

  - [Patron conceptuel](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#patron-conceptuel-nom-masculin)

  - [Modèle de données](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#modele-nom-masculin)

  - [Classe](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#classe-nom-feminin) et [Propriété](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#propriete-nom-feminin)

  - [RDF](https://www.w3.org/RDF/) (en anglais seulement) et ses divers formats, notamment [Turtle](https://www.w3.org/TR/turtle/) (en anglais seulement) et [JSON-LD](https://json-ld.org/) (en anglais seulement)

  - [URI](https://fr.wikipedia.org/wiki/Uniform_Resource_Identifier)

CRITERIA peut créer deux types de diagrammes à partir des mêmes données RDF, par exemple les données RDF relatives à la naissance et au décès de Marc-Aurèle Fortin :

```turtle
@prefix actor: <https://dopheda.info/crm_e39/> .
@prefix crm: <http://www.cidoc-crm.org/cidoc-crm/> .
@prefix geoname: <http://www.geonames.org/> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

actor:0001 a crm:E21_Person ;
  rdfs:label "Marc-Aurèle Fortin (1888-1970)"^^xsd:string ;
  crm:P98i_was_born <https://dopheda.info/crm_e2/0001> ;
  crm:P100i_died_in <https://dopheda.info/crm_e2/0002> .

<https://dopheda.info/crm_e2/0001> a crm:E67_Birth ;
  crm:P4_has_time-span <https://dopheda.info/crm_e52/0001> ;
  crm:P7_took_place_at geoname:6050610 ;
  crm:P96_by_mother actor:0002 ;
  crm:P97_from_father actor:0003 .

<https://dopheda.info/crm_e2/0002> a crm:E69_Death ;
  crm:P4_has_time-span <https://dopheda.info/crm_e52/0002> ;
  crm:P7_took_place_at geoname:6062563 .

<https://dopheda.info/crm_e52/0001> a crm:E52_Time-Span ;
  crm:P82a_begin_of_the_begin "1888-03-14T00:00:00"^^xsd:dateTime ;
  crm:P82b_end_of_the_end "1888-03-14T23:59:59"^^xsd:dateTime .

<https://dopheda.info/crm_e52/0002> a crm:E52_Time-Span ;
  crm:P82a_begin_of_the_begin "1970-03-02T00:00:00"^^xsd:dateTime ;
  crm:P82b_end_of_the_end "1970-03-02T23:59:59"^^xsd:dateTime .

geoname:6050610 a crm:E53_Place ;
  rdfs:label "Laval, Québec"@fr, "Laval, Quebec"@en .

geoname:6062563 a crm:E53_Place ;
  rdfs:label "Macamic, Québec"^^xsd:string .

actor:0002 a crm:E21_Person ;
  crm:P1_is_identified_by <https://dopheda.info/crm_e41/0002> .

actor:0003 a crm:E21_Person ;
  crm:P1_is_identified_by <https://dopheda.info/crm_e41/0003> .

<https://dopheda.info/crm_e41/0002> a crm:E41_Appellation, crm:E33_Linguistic_Object;
  crm:P190_has_symbolic_content "Amanda Fortier (1861-1953)"^^xsd:string .

<https://dopheda.info/crm_e41/0003> a crm:E41_Appellation, crm:E33_Linguistic_Object;
  crm:P190_has_symbolic_content "Thomas Fortin (1853-1933)"^^xsd:string .
```

  - **Instance** : type de diagramme qui comprend toutes les instances que renferme le document RDF, c’est-à-dire les URI et les valeurs littérales.

![](/collections-model/images/criteria_1.png)

  - **Ontologie** : type de diagramme qui ne comprend que les classes et leurs propriétés, c’est-à-dire le volet « ontologie » d’un patron conceptuel. Par « classe », on entend l’objet (du triplet) de la propriété `rdf:type`. Par conséquent, il est impossible de créer ce type de diagramme si une instance n’appartient à aucune classe.

![](/collections-model/images/criteria_2.png)

## Auditoires visés {#auditoires-vises}

CRITERIA est un outil de visualisation de données liées. Il se prête toutefois mal à la visualisation d'un ensemble de données ou d’un modèle de données complet se rapportant à une seule entité. Voici pourquoi :

1. Le format Mermaid dispose les nœuds de même niveau à l’horizontale ou à la verticale dans l’organigramme, ce qui rend rapidement ce dernier illisible;

2. Les niveaux sont présentés de haut en bas ou de gauche à droite; il est donc difficile de distinguer les liens entre des nœuds qui ne se suivent pas.

Par exemple, il ne faudrait pas utiliser CRITERIA pour visualiser toutes les données (nom, naissance, décès, nationalité, etc.) sur l’artiste canadienne Emily Carr sur un seul diagramme. En d’autres termes, cet outil sert à illustrer à l’aide de diagrammes des patrons conceptuels précis d’un modèle de données (patrons d’appellations, de naissances ou de décès, par exemple). Il intéresse donc divers groupes d’utilisateurs·rices.

  - *Ontologistes et modélisateurs·rices de données* : les personnes qui conçoivent ou créent des modèles de données peuvent se servir de CRITERIA pour visualiser leurs modèles afin de les valider.

  - *Utilisateurs·rices (incluant les néophytes) du CIDOC CRM* : les personnes qui désirent mieux comprendre les ontologies du CIDOC CRM peuvent visualiser une sérialisation RDF existante, puisque CRITERIA a été créé à partir de l'ontologie principale CIDOC CRM et de certaines de ses extensions. Le schème de couleurs du CIDOC CRM est le style appliqué par défaut.

  - *Développeurs·ses de logiciels ou de contenu* : les personnes chargées de produire la documentation sur un modèle de données ou de le tenir à jour sous forme numérique peuvent utiliser CRITERIA pour intégrer automatiquement dans leur environnement une visualisation des patrons conceptuels. Ces personnes seront particulièrement intéressées par l’utilisation en [ligne de commande](#interface-en-ligne-de-commande) de cet outil.

## Instructions

On peut utiliser CRITERIA de deux façons : par le biais d'un démonstrateur en ligne ou d'une ligne de commande.

> **Remarque** :** Le script traite les triplets en ordre aléatoire; par conséquent, l’utilisateur·rice n’a aucun contrôle sur l’ordre de présentation du fichier mermaid extrant. Cela signifie aussi qu’exécuter le script plusieurs fois à partir d’un même document RDF crée des documents Mermaid légèrement différents (l’ordre des énoncés y diffère), ce qui crée des diagrammes différents, car l’ordre des nœuds de même niveau sera différent. L’emplacement du nœud principal et la hiérarchie restent toutefois identiques.

### Démonstrateur en ligne {#demonstrateur-en-ligne}

Le [démonstrateur en ligne](http://chinrcip.pythonanywhere.com), en anglais seulement, intéressera surtout ceux et celles qui désirent créer rapidement des diagrammes.

Dans le cas des données JSON-LD, le démonstrateur en temps réel peut traiter les [contextes](https://w3c.github.io/json-ld-syntax/#the-context) (en anglais seulement) tant intégrés au document que ceux auxquels le document fait référence par URL (comme le [contexte Linked.art](https://linked.art/ns/v1/linked-art.json) (en anglais seulement)).

#### Navigateurs recommandés {#navigateurs-recommandes}

  - **MacOS** : Safari, Chrome ou Firefox

  - **Windows** : Firefox

#### Utilisation

Après avoir lancé le démonstrateur en ligne :

1. Cliquez sur le bouton `Example` (exemple) ou collez les données RDF dans le champ d’édition situé sous l'onglet `RDF input` (RDF d'entrée), qui peut mettre en évidence toute erreur de syntaxe.

2. Choisissez le format RDF dans la liste déroulante.

3. Choisissez le type de diagramme : `instance` ou `ontology` (ontologie).

4. Si `ontology` (ontologie) est sélectionné et qu'une annotation de nœud est nécessaire, cliquez sur l'onglet `SHACL` et ajoutez votre forme d'annotation SHACL en suivant la syntaxe décrite dans la section [Annotation de nœud](#annotation-de-noeud).

5. Pour ajouter votre propre configuration, cliquez sur l'onglet `Configuration` et modifiez ou écrasez la configuration JSON en suivant la structure décrite dans la section [Configuration](#configuration).

6. Cliquez sur le bouton `Convert` (convertir).

7. Pour agrandir ou réduire le diagramme, cliquez sur celui-ci.

8. Pour télécharger le diagramme en format PNG, SVG ou mermaid Markdown, cliquez sur le bouton correspondant.

![](/collections-model/images/criteria_3.png)

### Interface en ligne de commande

Cette méthode intéressera surtout les personnes voulant utiliser CRITERIA de façon automatisée, comme dans le traitement par lots ou la mise en application dans un système plus élaboré.

#### Installation

Pour installer l’outil, clonez [son répertoire](https://github.com/chin-rcip/CRITERIA) ou téléchargez celui-ci en fichier ZIP.

#### Dépendances {#dependances}

Pour exécuter l’outil, les versions du langage de programmation et les bibliothèques suivantes sont nécessaires :

  - [Python 3.7.0](https://www.python.org/downloads/release/python-370/) (en anglais seulement) ou une version plus récente

  - [rdflib 6.1.1](https://rdflib.readthedocs.io/en/6.1.1/) (en anglais seulement) ([license BSD 3](https://github.com/RDFLib/rdflib/blob/master/LICENSE) (en anglais seulement)) ou une version plus récente

#### Utilisation {#utilisation-1}

##### criteria.py

1. Ouvrez le répertoire `/CRITERIA` cloné ou téléchargé sur votre poste de travail.
    `$ cd /path/to/CRITERIA`

2. Exécutez : `$ python criteria.py Type rdf mmd [-sh SHACL] [-conf CONFIGFILE]`

    - `Type` (***requis***) : Le type de diagramme ne peut être que **instance** ou **ontology**.
    - `rdf` (***requis***) : `/chemin/vers/le/fichier/RDF/intrant`. Tel qu’installé ou téléchargé, CRITERIA comprend le sous-répertoire **rdf** où vous pouvez copier les fichiers RDF. Ensuite, précisez `./rdf/fichier_RDF_intrant.ttl`. Vous pouvez aussi indiquer le chemin d’accès absolu d’un fichier s’il ne se trouve pas dans ce sous-répertoire : `/chemin/du/répertoire/fichier_RDF_intrant.ttl`. L’outil peut traiter **plusieurs formats RDF**, comme Turtle, NTriples, RDF/XML, Trig ou JSON-LD.
    - `mmd` (***requis***) : `/chemin/du/répertoire/extrant`. Tel qu’installé ou téléchargé, CRITERIA comprend le sous-répertoire **mmd** où vous pouvez sauvegarder les fichiers mermaid (.mmd) extrants : `./mmd/fichier_MMD_extrant.mmd`. Vous pouvez aussi préciser le chemin d’accès absolu d’un répertoire où sauvegarder le fichier extrant : `/chemin/du/répertoire/fichier_MMD_extrant.mmd`.
    - `[-sh, --shacl SHACL]` (***optionnel***) : `/chemin/vers/le/fichier/de/forme/shacl/`. CRITERIA utilise la syntaxe SHACL pour annoter un nœud dans le diagramme ontologique, tel que le nom du nœud, la valeur d'exemple ou le lien vers la documentation du nœud. Voir la section [Annotation de nœud](#annotation-de-noeud) pour plus d'information sur la syntaxe requise.
    - `[-conf, --configFile CONFIGFILE]` (***optionnel***) : `/chemin/vers/le/fichier/de/configuration/JSON` : Cet argument vous permet de personnaliser votre style de diagramme (couleur) et de déclarer votre ou vos ontologies. CRITERIA comprend un fichier de configuration par défaut `config.json`, que vous pouvez utiliser si aucun fichier de configuration JSON n'est fourni. Voir la section [Configuration](#configuration) pour plus d'information sur la structure JSON requise.

3. Une fois le fichier mermaid extrant créé, le diagramme peut être généré en :

    - collant intégralement le contenu du fichier mermaid Markdown dans le champ de code de [l’éditeur Mermaid en ligne](https://mermaid-js.github.io/mermaid-live-editor) (en anglais seulement); cet utilitaire permet de télécharger le diagramme correspondant en format PNG ou SVG; ou en
    - intégrant le code Markdown dans le code source du site Web et en créant le diagramme à l’aide de [Mermaid.js](https://mermaid-js.github.io/mermaid/#/n00b-gettingStarted?id=_3-deploying-mermaid-on-the-browser) (en anglais seulement).

Exemple :

  - Voici la commande servant à générer un diagramme d’instances à partir du fichier RDF `BirthDeath_Fortin.ttl` dans le répertoire `./rdf` et à l’enregistrer dans le répertoire `./mmd` :
  ```shell
  $ python criteria.py instance ./rdf/BirthDeath_Fortin.ttl ./mmd/BirthDeath_Fortin.mmd
  ```

  - Voici la commande servant à générer un diagramme d’ontologie sans les nœuds annotés à partir du même fichier RDF et à l’enregistrer dans le même répertoire :
  ```shell
  $ python criteria.py ontology ./rdf/BirthDeath_Fortin.ttl ./mmd/BirthDeath_onto.mmd
  ```

  - Voici la commande servant à générer un diagramme d'ontologie avec les nœuds annotés à partir du même fichier RDF et à l'enregistrer dans le même répertoire : 
     ```shell
    $ python criteria.py ontology ./rdf/BirthDeath_Fortin.ttl ./mmd/BirthDeath_onto.mmd -sh ./rdf/demo_shape.shacl
    ```

#### Annotation de nœud {#annotation-de-noeud}

Le modèle SHACL pour ***chaque nœud annoté*** est le suivant :

```turtle
{forme-URI} a sh:NodeShape ; # Forme du nœud sujet du triplet dans lequel le nœud annoté est l'objet
        skos:example {URI-du-nœud-sujet-du-rdf-intrant} ;
  sh:property [
    sh:path {predicat-URI} ;
    sh:defaultValue {valeur-du-noeud-annote} ;
    sh:name "{libelle-du-noeud}" ;
    sh:description "{URL-de-la-documentation-du-noeud}" ;
  ] .
```
 
L'extrait RDF ci-dessous est utilisé pour la démonstration :
 
```turtle
<https://dopheda.info/crm_e2/0001> a crm:E67_Birth ;
  crm:P7_took_place_at geoname:6050610.
```
 
- Le nœud annoté est `Birth Place` (lieu de naissance), c.-à-d. `geoname:6050610`. Cependant, la `sh:NodeShape` (forme du nœud) définie est le nœud sujet du triplet dans lequel le nœud annoté est l'objet, l'URI de Naissance `<https://dopheda.info/crm_e2/0001>`.
- `skos:example` (**requis**) : Cette propriété est utilisée pour ajouter l'URI du nœud sujet, p. ex. `<https://dopheda.info/crm_e2/0001>`. Cette propriété n'interfèrera pas avec la validation SHACL réelle.
- Pour la [PropertyShape (forme de la propriété)](https://www.w3.org/TR/shacl/#property-shapes) (en anglais seulement), outre la propriété `sh:path` qui décrit le prédicat du triplet, les autres propriétés SHACL ne sont pas validantes, c.-à-d. qu'elles n'interfèrent pas avec la validation SHACL réelle. Bien que ces propriétés SHACL décrivent la forme de la propriété et non le nœud annoté en soi, elles sont valides pour l'utilisation de CRITERIA. Par exemple, le nom de `crm:P7_took_place_at` dans ce patron conceptuel particulier indique que son utilisation est pour `Birth Place` (lieu de naissance).
- `sh:path` (**requis**) : URI du prédicat, p. ex. `crm:P7_took_place_at`.
- `sh:name` : Libellé du nœud annoté, p. ex. `"Birth Place"`.
- `sh:describe` : URL de la documentation du nœud annoté. Cette valeur est intégrée au nœud annoté dans le diagramme en tant que lien.
- `sh:defaultValue` : Valeur spécifique du nœud annoté, qui peut être littérale ou un URI, p. ex. `geoname:6050610`. S'il s'agit d'un URI, cette valeur est intégrée au nœud de valeur dans le diagramme en tant que lien, le cas échéant.

**Remarque** : *Les nœuds annotés partageant le même nœud sujet peuvent être regroupés, voir l'exemple pour `Birth Date` dans la démonstration [demo_shape.shacl](https://github.com/chin-rcip/CRITERIA/rdf/demo_shape.shacl).*
 
Exemple SHACL :
 
```turtle
ex:BirthPlace a sh:NodeShape ;
  skos:example <https://dopheda.info/crm_e2/0001> ;
  sh:property [
    sh:path crm:P7_took_place_at ;
    sh:defaultValue geoname:6050610 ;
    sh:name "Birth Place" ;
    sh:description "https://chin-rcip.github.io/collections-model/en/semantic-paths-specification/current/entry-nodes#birth-place" ;
  ] .
```

#### Configuration

La configuration par défaut de CRITERIA comprend le schéma de couleurs du CIDOC CRM (tel que proposé par George Bruseker) ainsi que l'ontologie principale du CIDOC CRM et ses extensions disponibles en RDF en tant qu'ontologies source. 

Pour appliquer votre propre configuration, préparez un fichier JSON selon la structure ci-dessous :

```json
{
  "style": {},
  "onto": {},
  "prefix": {}
}
```

##### Schème de couleurs {#scheme-de-couleurs}

Actuellement, vous pouvez personnaliser la couleur de l'arrière-plan, de la bordure et de la police des nœuds de classe et des nœuds d'instance.

La **structure JSON** pour `"style"` est la suivante :

```json
"style": {
  "{type-de-classe}": {
    "classColor": "{couleur-de-larriere-plan-du-noeud-de-classe}",
    "classStroke": "{couleur-de-la-bordure-du-noeud-de-classe}",
    "classFontColor": "{couleur-de-la-police-du-noeud-de-classe}",
    "instanceColor": "{couleur-de-larriere-plan-du-noeud-dinstance}",
    "instanceStroke": "{couleur-de-la-bordure-du-noeud-dinstance}",
    "instanceFontColor": "{couleur-de-la-police-du-noeud-dinstance}",
    },
}
```
- `{type-de-classe}`: La classe, dont les nœuds sont stylisés en conséquence, y compris le préfixe, p. ex.`crm_E53_Place`, `schema_Thing`. Le style est également appliqué aux nœuds de ses sous-classes. REMARQUE :
    - Pour les nœuds de `rdf:Literal`, utilisez TOUJOURS la clé **`"Literal"`**.
    - Pour les nœuds de plusieurs classes, utilisez TOUJOURS la clé **`"Multi"`**.
    - Utilisez TOUJOURS le **trait de soulignement** comme séparateur entre le préfixe de l'ontologie et le nom de la classe.
- Utilisez **la valeur de couleur CSS**, p. ex. `#90EE09` ou `lightgreen`.

Exemple :

```json
{
  "style": {
    "Literal": {"classColor": "#ffffff", "classStroke": "#000000", "instanceColor": "#ffffff", "instanceStroke": "#000000"},
    "crm_E53_Place": {"classColor": "#94cc7d", "classStroke": "#000000", "classFontColor": "#000080", "instanceColor": "#e1f1da", "instanceStroke": "#000000", "instanceFontColor":"navy"}
  }
}
```

##### Source des ontologies

CRITERIA est installé avec plusieurs ontologies CIDOC CRM par défaut en format RDF. Elles se trouvent dans le répertoire `/src/ontologies/`.

  - [CIDOC CRM (v7.1.1)](http://www.cidoc-crm.org/Version/version-7.1.1) (en anglais seulement)

  - [FRBRoo (v2.4)](http://www.cidoc-crm.org/frbroo/ModelVersion/frbroo-v.-2.4) (en anglais seulement)

  - [CRMpc (v7.1.1)](https://cidoc-crm.org/rdfs/7.1.1/CIDOC_CRM_v7.1.1_PC.rdfs) (en anglais seulement)

  - CRMdig (v3.2.2) (téléchargée du site Web [3m du FORTH](https://isl.ics.forth.gr/3M/) (en anglais seulement))

  - [CRMarcheo (v1.4.1)](https://www.cidoc-crm.org/crmarchaeo/ModelVersion/version-1.4.1) (en anglais seulement)

  - [CRMsci (1.2.6)](https://cidoc-crm.org/crmsci/ModelVersion/version-1.2.6) (en anglais seulement)

Pour écraser les ontologies par défaut, préparez votre fichier de configuration JSON en suivant la structure des clés `"onto"` et `"prefix"` comme suit :

```json
  "onto": {
    "{ontologie-principale}": {
      "core": "{lien-ou-chemin-vers-lontologie-principale}",
      "extensions": {
        "{extension-de-lontologie-principale}": "{lien-ou-chemin-vers-lextension-de-lontologie-principale}"     }
    }
  },
  "prefix": {
    "{prefixe-de-lontologie}": "{url-de-base-de-lontologie}"
  }
```

- `{ontologie-principale}`, `{extension-de-lontologie-principale}` : Acronymes ou nom de l'ontologie principale et de ses extensions respectivement. La valeur peut être la même que le préfixe de l'ontologie.
- `{prefixe-de-lontologie}` : Préfixe de chaque ontologie, p. ex. `crm`, `frbroo`, `schema`. 
- `{lien-ou-chemin-vers-lontologie-principale}` : URL ou chemin complet au fichier RDF de l'ontologie principale.
- `"extensions"` : N'ajoutez ce groupe que si l'extension de l'ontologie principale est utilisée.
    - `{lien-ou-chemin-vers-lextension-de-lontologie-principale}`: URL ou chemin complet au fichier RDF de l'extension de l'ontologie principale.
- `{url-de-base-de-lontologie}` : URL de base de chaque ontologie.

Exemple :

```json
{
"onto": {
    "crm": {
      "core": "https://cidoc-crm.org/rdfs/7.1.1/CIDOC_CRM_v7.1.1.rdfs",
      "extensions": {
        "crmpc": "https://cidoc-crm.org/rdfs/7.1.1/CIDOC_CRM_v7.1.1_PC.rdfs"
      }
    },
    "schema": {
      "core": "https://schema.org/version/latest/schemaorg-current-https.jsonld"
    }

  },
  "prefix": {
    "crm": "http://www.cidoc-crm.org/cidoc-crm/",
    "crmpc": "http://www.ics.forth.gr/isl/CRMext/CRMdig.rdfs/",
    "schema":"https://schema.org/"
  }
}
```

## Aide-mémoire {#aide-memoire}

  - [Lien vers le démonstrateur en ligne](http://chinrcip.pythonanywhere.com) (en anglais seulement)

  - Syntaxe en ligne de commande : `$ python criteria.py Type rdf mmd [-sh SHACL] [-conf CONFIGFILE]`

## Pour en savoir plus

  - [Mermaid](https://mermaid-js.github.io/mermaid/#/) (en anglais seulement)

  - [RDFLib](http://rdflib.readthedocs.org) (en anglais seulement)

## Licence

CRITERIA est distribué en vertu de la [licence MIT](https://github.com/chin-rcip/CRITERIA/blob/master/LICENSE) (en anglais seulement). Pour satisfaire aux exigences relatives à son attribution, vous devez préciser comme suit le détenteur du droit d’auteur :

> Copyright (c) 2020-2022 Canadian Heritage Information Network, Canadian Heritage, Government of Canada – Réseau canadien d'information sur le patrimoine, Patrimoine canadien, Gouvernement du Canada

## Utilisateurs·rices dignes de mention {#utilisateurs-rices-dignes-de-mention}

Le RCIP veut remercier les responsables de projets et les institutions qui utilisent CRITERIA; nous ne pourrions pas améliorer cet outil sans leur contribution. Si vous utilisez CRITERIA mais que votre projet ne se trouve pas dans la liste ci-dessous, n’hésitez pas à [communiquer avec nous](mailto:pch.RCIP-CHIN.pch@canada.ca).

**Projet : [Reference Data Models](http://docs.swissartresearch.net/) (en anglais seulement)**

Organisme : [Swiss Art Research Infrastructure, University of Zurich](http://swissartresearch.net/) (en anglais seulement)

Description ([Source](https://docs.swissartresearch.net/) (en anglais seulement)) :

> Le projet des modèles de données sémantiques de référence a pour but de créer un ensemble de modèles de patrons conceptuels sémantiques réutilisables afin de simplifier l’intégration et la recherche des sources de données sur le patrimoine culturel. Chaque modèle consiste en une série de patrons conceptuels sémantiques fondés sur l’analyse de sources choisies jugées pertinentes à une entité. Pour assurer leur compatibilité avec l’ensemble du domaine patrimonial, ces patrons conceptuels sémantiques sont mis en correspondance avec l’ontologie CIDOC CRM et peuvent servir d’applications de référence aux institutions et aux responsables de projets peu familiers avec le CIDOC CRM. En effet, il est possible de les utiliser comme modèles pour développer des interfaces de saisie de données sémantiques créées nativement à partir du CRM. De plus, ces patrons conceptuels peuvent servir à transformer des sources existantes vers un modèle de référence conforme au CIDOC CRM, à l’aide d’un outil tel que 3M.

**Projet: [Census](http://census.de) - Semantic Census (en anglais seulement)**

Organismes :

- [Université Humboldt](https://www.hu-berlin.de/en) (en anglais seulement)
- [Institut Warburg](https://warburg.sas.ac.uk/) (en anglais seulement)
- [Bibliotheca Hertziana - Max-Planck-Institut für Kunstgeschichte](https://www.biblhertz.it/en/home) (en anglais seulement)
- [Université de Hambourg - Séminaire Kunstgeschichtliches](https://www.kulturwissenschaften.uni-hamburg.de/ks.html) (en allemand seulement)
- [Getty Research Institute](https://www.getty.edu/research/) (en anglais seulement)

Description :

> Le projet Semantic Census fait partie d'une stratégie à long terme plus large du projet Census visant à rendre cette riche ressource de recherche sur l'Antiquité et la Renaissance accessible à un public plus large. En créant une représentation sémantique de ce catalogue de connaissances, le projet Census vise à ouvrir le jeu de données à une réutilisation par les chercheurs·ses selon des manières non prévues à l'origine. De plus, en publiant une documentation complète et riche de son propre modèle sémantique, Semantic Census souhaite permettre aux chercheurs·ses de comprendre et d'interroger plus facilement la version sémantique des données du projet Census, ainsi que de potentiellement compléter et enrichir celles-ci en les croisant avec leurs propres recherches et autres jeux de données. L'outil CRITERIA a aidé le projet à générer automatiquement des graphiques de données cohérents et lisibles pour représenter et comprendre les structures du modèle. La documentation du modèle de données du projet Semantic Census est disponible à l'adresse [https://census-antiquity-renaissance.github.io/census-csdm/](https://census-antiquity-renaissance.github.io/census-csdm/) (en anglais seulement).

## Bibliographie

Beckett, David, Tim Berners-Lee, Eric Prud’hommeaux, et Gavin Carothers. s. d. « RDF 1.1 Turtle ». Consulté le 28 mai 2021. [https://www.w3.org/TR/turtle/](https://www.w3.org/TR/turtle/).

Réseau canadien d’information sur le patrimoine (RCIP). 2021a. « classe (nom féminin) ». *Glossaire*. Ottawa, Ont. : Gouvernement du Canada/Government of Canada. [https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#classe-nom-feminin](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#classe-nom-feminin).

———. 2021b. « instance (nom féminin) ». *Glossaire*. Ottawa, Ont. : Gouvernement du Canada/Government of Canada. [https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#instance-nom-feminin](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#instance-nom-feminin).

———. 2021c. « modèle (nom masculin) ». *Glossaire*. Ottawa, Ont. : Gouvernement du Canada/Government of Canada. [https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#modele-nom-masculin](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#modele-nom-masculin).

———. 2021d. « ontologie (nom féminin) ». *Glossaire*. Ottawa, Ont. : Gouvernement du Canada/Government of Canada. [https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#ontologie-nom-feminin](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#ontologie-nom-feminin).

———. 2021e. « patron conceptuel (nom masculin) ». *Glossaire*. Ottawa, Ont. : Gouvernement du Canada/Government of Canada. [https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#patron-conceptuel-nom-masculin](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#patron-conceptuel-nom-masculin).

———. 2021f. « propriété (nom féminin) ». *Glossaire*. Ottawa, Ont. : Gouvernement du Canada/Government of Canada. [https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#propriete-nom-feminin](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#propriete-nom-feminin).

JSON-LD Working Group. 2014. « JSON-LD - JSON for Linking Data ». JSON-LD. 16 janvier 2014. [https://json-ld.org/](https://json-ld.org/).

linked.art. 2020. « Linked Art ». Linked Art. 30 janvier 2020. [https://linked.art/](https://linked.art/).

RDF Working Group. 2014. « RDF - Semantic Web Standards ». W3C. 25 février 2014. [https://www.w3.org/RDF/](https://www.w3.org/RDF/).

RDFLib Team. s. d. « Rdflib 5.0.0 — Rdflib 5.0.0 Documentation ». Consulté le 28 mai 2021. [https://rdflib.readthedocs.io/en/stable/](https://rdflib.readthedocs.io/en/stable/).

Sveidqvist, Knut. s. d. « Mermaid - Markdownish Syntax for Generating Flowcharts, Sequence Diagrams, Class Diagrams, Gantt Charts and Git Graphs ». Consulté le 28 mai 2021. [https://mermaid-js.github.io/mermaid/#/](https://mermaid-js.github.io/mermaid/#/).

Swiss Art Research Infrastructure. s. d. « SARI Documentation ». Consulté le 28 mai 2021. [https://docs.swissartresearch.net/](https://docs.swissartresearch.net/).

Wikipédia. 2020. « Uniform Resource Identifier ». *Wikipédia*. San Francisco, CA : Wikipédia. [https://fr.wikipedia.org/wiki/Uniform_Resource_Identifier](https://fr.wikipedia.org/wiki/Uniform_Resource_Identifier).

