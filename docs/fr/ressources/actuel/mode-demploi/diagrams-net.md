---
layout: page
language: fr
title: Mode d’emploi - Bibliothèques logicielles diagrams.net
permalink: /fr/ressources/actuel/mode-demploi/bibliotheques-logicielles-diagrams-net
other_link: /en/resources/current/how-to/diagrams-net-libraries
sidebar: diagramsfr
group: ressources
subgroup: mode d'emploi
date: 2021-06-14
description: Ce document présente un aperçu des bibliothèques logicielles diagrams.net et explique comment les utiliser.
---

**Version** : 1.0

**Créé le** : 2021-04-22

**Mis à jour le** : 2021-06-14

**Résumé** : Ce document présente un aperçu des bibliothèques logicielles diagrams.net et explique comment les utiliser.

**Des questions?** : Veuillez adresser vos questions et commentaires par courriel à l’adresse [pch.RCIP-CHIN.pch@canada.ca](mailto:pch.RCIP-CHIN.pch@canada.ca). Précisez « Bibliothèques diagrams.net » dans l’objet.

## Utilisation principale

  - Simplifier la visualisation de modèles de données fondés sur [CIDOC CRM](http://www.cidoc-crm.org/) et [ses extensions](http://www.cidoc-crm.org/collaborations) lorsque ceux-ci sont réalisés par l’intermédiaire de l’outil [diagrams.net](https://www.diagrams.net/).

## Contexte

Les bibliothèques [diagrams.net](https://www.diagrams.net/) constituent un ensemble de fichiers XML d’ontologies qui sert à représenter des patrons conceptuels à l’aide du logiciel [diagrams.net](https://www.diagrams.net/). Tenu à jour par le Réseau canadien d’information sur le patrimoine (RCIP), ces bibliothèques logicielles permettent de créer des diagrammes dans le cadre de projets de données ouvertes et liées. Le RCIP a jusqu’à maintenant créé sept bibliothèques destinées aux ontologies du Modèle conceptuel de référence du Comité international pour la Documentation (CIDOC CRM); celles-ci sont diffusées officiellement en format RDFS et répertoriées ci-dessous. Elles seront utiles aux utilisateurs qui créent des diagrammes de modèles de données fondés sur le CIDOC CRM.

  - CIDOC CRM base (version 6.2.1)

  - FRBRoo (version 2.4)

  - PRESSoo (version 1.0)

  - CRMdig (version 3.2.2)

  - CRMpc (version 1.1.1)

  - CRMarchaeo (version 1.4.1)

  - CRMgeo (version 1.2)

*Ces travaux ont été inspirés par le [travail de Nicola Carboni](https://github.com/ncarboni/Shapes_CIDOC-CRM).*

## Vocabulaire de base et connaissances préalables {#vocabulaire-de-base-et-connaissances-prealables}

Une bibliothèque consiste en un ensemble de formes qu’on peut simplement glisser et déposer dans un diagramme pour en faciliter la création. Elle se trouve habituellement dans le volet gauche du logiciel diagrams.net.

Chaque bibliothèque contient les formes de toutes les [classes](https://chin-rcip.github.io/collections-model/en/resources/current/glossary#class-noun) et les connecteurs correspondant aux [propriétés](https://chin-rcip.github.io/collections-model/en/resources/current/glossary#property-noun) de chaque ontologie. La palette de couleurs choisie (voir ci-dessous) est fondée sur une proposition de George Bruseker pour le [CIDOC CRM](http://www.cidoc-crm.org/) .

<table>
<tbody>
<tr><td style="background-color: #FFFFFF">`E1_CRM_Entity` et toute sous-classe ne faisant pas partie des classes ci-dessous (#FFFFFF)</td></tr>
<tr><td style="background-color: #82C3EC">`E2_Temporal_Entity` et ses sous-classes (#82C3EC)</td></tr>
<tr><td style="background-color: #FAB565">`E55_Type` et ses sous-classes (#FAB565)</td></tr>
<tr><td style="background-color: #86BCC8">`E52_Time-Span` et ses sous-classes (#86BCC8)</td></tr>
<tr><td style="background-color: #FEF3BA">`E41_Appellation` et ses sous-classes (#FEF3BA)</td></tr>
<tr><td style="background-color: #94CC7D">`E53_Place` et ses sous-classes (#94CC7D)</td></tr>
<tr><td style="background-color: #FDDC34">`E28_Conceptual_Object` et ses sous-classes (#FDDC34)</td></tr>
<tr><td style="background-color: #E1BA9C">`E18_Physical_Thing` et ses sous-classes (#E1BA9C)</td></tr>
<tr><td style="background-color: #FFBDCA">`E41_Actor` et ses sous-classes (#FFBDCA)</td></tr>
<tr><td style="background-color: #CC80FF">Toutes les PC_Classes (#CC80FF)</td></tr>
</tbody>
</table>

## Auditoire visé et description des sections {#auditoire-vise-et-description-des-sections}

Quiconque voulant visualiser des modèles de données fondés sur le CIDOC CRM et ses extensions peut utiliser cet outil. Selon la version de diagrams.net utilisée, deux versions permettent de charger les bibliothèques :

  - [version bureau (version locale)](#ouverture-dune-bibliothèque)

  - [version en ligne](#chargement-dune-bibliothèque-par-son-url)

Vous trouverez à la rubrique [Utilisation des bibliothèques](#utilisation-des-bibliothèques) une description plus approfondie des bibliothèques et des conseils sur leur utilisation.

## Instructions

### Chargement des bibliothèques {#chargement-des-bibliotheques}

Vous pouvez accéder à l’une ou l’autre des bibliothèques de deux façons :

  - vous ouvrez une bibliothèque XML directement dans le logiciel;

  - vous chargez la bibliothèque voulue par son URL.

#### Ouverture d’une bibliothèque {#ouverture-dune-bibliotheque}

*Cette option est la plus appropriée à l’usage local du logiciel diagrams.net.*

Lancez le logiciel diagrams.net, cliquez dans l’ordre sur **Fichier** puis **Ouvrir une librairie depuis**, et :

1.  si le répertoire Github ou les fichiers XML sont déjà téléchargés :
    
    1.  choisissez le service ou l’appareil où se trouvent les
        fichiers;
    
    2.  localisez le fichier voulu et sélectionnez-le (l’extension est
        .xml), puis cliquez sur **Ouvrir**.

OU

2.  entrez directement l’URL Github de chaque bibliothèque, dans le répertoire **/cidoc-crm** :
    
    1.  CIDOC CRM base
        [(https://raw.githubusercontent.com/chin-rcip/diagrams.net_libraries/main/cidoc-crm/crm_library.xml](about:blank))
    
    2.  FRBRoo
        ([https://raw.githubusercontent.com/chin-rcip/diagrams.net_libraries/main/cidoc-crm/frbroo_library.xml](https://raw.githubusercontent.com/chin-rcip/diagrams.net_libraries/main/cidoc-crm/frbroo_library.xml))
    
    3.  PRESSoo
        ([https://raw.githubusercontent.com/chin-rcip/diagrams.net_libraries/main/cidoc-crm/pressoo_library.xml](https://raw.githubusercontent.com/chin-rcip/diagrams.net_libraries/main/cidoc-crm/pressoo_library.xml))
    
    4.  CRMdig
        ([https://raw.githubusercontent.com/chin-rcip/diagrams.net_libraries/main/cidoc-crm/crmdig_library.xml](https://raw.githubusercontent.com/chin-rcip/diagrams.net_libraries/main/cidoc-crm/crmdig_library.xml))
    
    5.  CRMpc
        ([https://raw.githubusercontent.com/chin-rcip/diagrams.net_libraries/main/cidoc-crm/crmpc_library.xml](https://raw.githubusercontent.com/chin-rcip/diagrams.net_libraries/main/cidoc-crm/crmpc_library.xml))
    
    6.  CRMarchaeo
        (([https://raw.githubusercontent.com/chin-rcip/diagrams.net_libraries/main/cidoc-crm/crmarchaeo_library.xml](https://raw.githubusercontent.com/chin-rcip/diagrams.net_libraries/main/cidoc-crm/crmpc_library.xml))
    
    7.  CRMgeo
        (([https://raw.githubusercontent.com/chin-rcip/diagrams.net_libraries/main/cidoc-crm/crmgeo_library.xml](https://raw.githubusercontent.com/chin-rcip/diagrams.net_libraries/main/cidoc-crm/crmpc_library.xml))

![](/collections-model/images/diagrams_net_fr_1.png)

#### Chargement d’une bibliothèque par son URL {#chargement-dune-bibliothèque-par-son-URL}

*Cette option est la plus appropriée à l’usage en ligne du logiciel diagrams.net.*

Cliquez sur l’une des adresses suivantes pour ouvrir diagrams.net et y charger la bibliothèque voulue :

  - [Bibliothèque CRM base](https://app.diagrams.net/?splash=0&clibs=Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrm_library.xml)

  - [Bibliothèque FRBRoo](https://app.diagrams.net/?splash=0&clibs=Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Ffrbroo_library.xml)

  - [Bibliothèque PRESSoo](https://app.diagrams.net/?splash=0&clibs=Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fpressoo_library.xml)

  - [Bibliothèque CRMdig](https://app.diagrams.net/?splash=0&clibs=Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrmdig_library.xml)

  - [Bibliothèque CRMpc](https://app.diagrams.net/?splash=0&clibs=Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrmpc_library.xml)

  - [Bibliothèque CRMarchaeo](https://app.diagrams.net/?splash=0&clibs=Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrmarchaeo_library.xml)

  - [Bibliothèque CRMgeo](https://app.diagrams.net/?splash=0&clibs=Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrmgeo_library.xml)

  - [Toutes les bibliothèques](https://app.diagrams.net/?splash=0&clibs=Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrm_library.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Ffrbroo_library.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrmdig_library.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrmpc_library.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fpressoo_library.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrmarchaeo_library.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrmgeo_library.xml)

Une fois chargée, la bibliothèque est habituellement gardée dans la mémoire cache du navigateur Web; il est donc inutile de la charger de nouveau à moins d’avoir vidé la mémoire cache.

### Utilisation des bibliothèques {#utilisation-des-bibliotheques}

Les bibliothèques contiennent deux types de formes :

  - des rectangles arrondis colorés selon la palette de couleurs décrite ci-dessus et qui représentent les classes;

  - des flèches noires qui représentent les propriétés.

Chaque forme est étiquetée selon la nomenclature du CIDOC CRM, c’est-à-dire un caractère de soulignement après le code de l’entité et entre chaque mot, par exemple, « `E2_Temporal_Entity` ». Pour simplifier les recherches à l’aide du champ **Chercher des formes** dans la partie supérieure du volet de gauche, ces caractères de soulignement sont remplacés par des espaces dans le titre  : « E2 Temporal Entity ».

![](/collections-model/images/diagrams_net_fr_2.png)

Pour trouver une forme en particulier (classes ou propriétés), entrez son code CIDOC CRM ou son titre dans le champ de recherche.

![](/collections-model/images/diagrams_net_fr_3.png)

## Aide-mémoire {#aide-memoire}

  - Cliquez [ici](https://app.diagrams.net/?splash=0&clibs=Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrm_library.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Ffrbroo_library.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrmdig_library.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrmpc_library.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fpressoo_library.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrmarchaeo_library.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrmgeo_library.xml) pour charger toutes les bibliothèques dans la version en ligne de diagrams.net.

  - Interrogez l’outil de recherche pour trouver une entité par son code ou son titre.

## Pour plus d'informations

Pour en savoir plus sur la création, l’échange et le chargement des bibliothèques de formes dans diagrams.net, consultez les ressources documentaires suivantes (en anglais seulement) :

  - [https://desk.draw.io/support/solutions/articles/16000067790](https://desk.draw.io/support/solutions/articles/16000067790)

  - [http://jgraph.github.io/drawio-libs/](http://jgraph.github.io/drawio-libs/)

## Licence

Les fichiers de ce répertoire sont distribués en vertu de la licence MIT. Pour satisfaire aux exigences relatives à son attribution, vous devez préciser comme suit le détenteur du droit d’auteur :

> Copyright (c) 2021 Canadian Heritage Information Network, Canadian Heritage, Government of Canada - Réseau canadien d'information sur le patrimoine, Patrimoine canadien, Gouvernement du Canada

## Bibliographie

Benson, David. 2020. « *Work with Custom Shape Libraries* ». Legacy desk – do not use. 15 septembre 2020. [https://drawio.freshdesk.com/support/solutions/articles/16000067790-work-with-custom-shape-libraries](https://drawio.freshdesk.com/support/solutions/articles/16000067790-work-with-custom-shape-libraries). (En anglais seulement)

Carboni, Nicola. (2020) 2021. Shapes_CIDOC-CRM. [https://github.com/ncarboni/Shapes_CIDOC-CRM](https://github.com/ncarboni/Shapes_CIDOC-CRM) (en anglais seulement)

jgraph. n.d. « Diagrams.Net Libraries ». Drawio-Libs. Consulté le 13 mai 2021. [http://jgraph.github.io/drawio-libs/](http://jgraph.github.io/drawio-libs/) (en anglais seulement)

Réseau canadien d’information sur le patrimoine (RCIP). 2021a. « classe (nom féminin) ». Dans le *Glossaire*. Ottawa, ON : Government of Canada / Gouvernement du Canada. [https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#classe-nom-feminin](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#classe-nom-feminin)

Réseau canadien d’information sur le patrimoine (RCIP). 2021a. « propriété (nom féminin) ». Dans le *Glossaire*. Ottawa, ON : Government of Canada / Gouvernement du Canada. [https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#propriete-nom-feminin](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#propriete-nom-feminin)
