---
layout: page
language: fr
title: Spécification des chemins sémantiques
permalink: /fr/specification-des-chemins-semantiques/actuel/introduction
other_link: /en/semantic-paths-specification/current/introduction
sidebar: scs22
group: spécifications
date: 2022-01-27
description: La Spécification des chemins sémantiques présente les liens sémantiques entre les entités du CIDOC CRM qui forment les patrons conceptuels présentés dans la Spécification du modèle cible et destinés à répondre aux cas d'usage pertinents pour le projet.
---

Version 2.2 ([Versions précédentes](/collections-model/fr/versions))

> AVERTISSEMENT : La documentation accessible par la présente est une collection de documents de travail. En tant que telle, bien qu'elle soit diffusée publiquement, elle ne constitue pas une publication officielle et des modifications sont apportées de façon continue. En raison de ces modifications régulières, <span class="disclaimer">la majorité de ce contenu est présenté en **anglais** et ne sera traduit que lorsqu'une publication stable et officielle sera disponible.</span>

## Dates

Date de création : 2021-10-15

Dernière mise à jour : 2022-01-27

## Résumé {#resume}

La Spécification des chemins sémantiques présente les liens sémantiques entre les entités du CRM CIDOC qui forment les patrons conceptuels présentés dans la [Spécification du modèle cible](/collections-model/fr/modele-cible/actuel/introduction) et destinés à répondre aux cas d'usage pertinents pour le projet.

## Avant-propos

La Spécification des chemins sémantiques (SCS) fournit une vue granulaire du [modèle DOPHEDA](/collections-model/) et est destinée aux personnes qui veulent élaborer un processus de mise en correspondance ou effectuer des requêtes SPARQL. Elle est destinée à être utilisée conjointement avec la [Spécification du modèle cible](/collections-model/fr/modele-cible/actuel/introduction) (SMC), qui décrit les relations entre les [nœuds](#nœud) par le biais d'un ensemble de patrons conceptuels, bien qu'à l'heure actuelle, seuls les [nœuds de saisie](#noeud-de-saisie) soient documentés.

Chaque nœud est défini par une [note d'application](#portee) précise détaillant les valeurs de données qu'il peut accueillir, ainsi que par son ou ses [liens générés](#liens-generes), son [évaluation sémantique](#evaluation-sémantique) et sa [liste contrôlée de termes ou terme unique](#liste-controleeterme). Le contexte de chaque nœud peut être exploré à travers ses [dépendances](#dependances), ses [nœuds dotés d’un qualifiant spécifié liés](#ndqs-lies), son [chemin complet](#chemin-complet), sa position visualisée dans la ou les [vue·s de la Spécification du modèle cible](#vues-du-modele-cible) et son ou ses [origines de valeur](#origines-de-valeur). Outre les [commentaires](#commentaires) pertinents et les [erreurs potentielles](#erreurs-potentielles), la SCS énumère également les [cas typiques](#cas-typiques) et les [cas limites](#cas-limites) qui illustrent la manière dont les soumissionnaires peuvent documenter les informations dans d'autres domaines. Les [références](#réferences) pour chaque nœud sont également incluses.

## Glossaire

### Nœud de saisie {#noeud-de-saisie}

[Nœud](#noeud) où une valeur (chaîne de caractères, nombre entier, date ou dans certains cas URI) doit être extraite du champ correspondant dans le jeu de données du soumissionnaire. Toutes les données (c.-à-d. toutes les valeurs de données explicites dérivées de la structure de données d'origine (liste de vérification)) qui se trouvent dans le réseau de données sémantiques généré seront stockées dans ces nœuds. Dans ce document, l'instance de la classe et son libellé sont, dans la plupart des cas, présentés comme un seul [nœud](#noeud). Cependant, les URI deviennent directement des instances de leur classe connexe, tandis que les littéraux sont attachés par une propriété à une instance générée de cette classe connexe. De plus amples informations sur cette distinction sont documentées dans le champ [évaluation sémantique](#evaluation-semantique).

### Nœud généré {#noeud-genere}

Nœud généré automatiquement qui représente des parties de la relation sémantique complète entre les [nœuds de saisie](#noeud-de-saisie). Les nœuds générés sont automatiquement associés à des URI (instances et classes) ainsi qu'à des libellés générés par des scripts et déduits (mais non présents dans) des ensembles de données d'origine. Du point de vue d'un soumissionnaire de données, ces [nœuds](#noeud) sont utiles pour comprendre l'objectif des entités qui seront automatiquement générées par le processus de mise en correspondance du CIDOC CRM. La plupart des nœuds générés sont définis dans la spécification du [CIDOC CRM](http://www.cidoc-crm.org/versions-of-the-cidoc-crm) et ne sont donc pas abordés ici. Une exception à cette règle est la documentation de [nœuds](#noeud) utilisés pour catégoriser d'autres nœuds générés en les désignant comme étant « X ». De tels [nœuds](#noeud) sont, ci-après, définis comme des [nœuds dotés d’un qualifiant spécifié](#noeud-dote-dun-qualifiant-specifie-ndqs).

### Nœud doté d’un qualifiant spécifié (NDQS) {#noeud-dote-dun-qualifiant-specifie-ndqs}

[Nœud généré](#noeud-genere) qui contient des termes de vocabulaire spécifiques; sa fonction est de catégoriser une autre [nœud](#noeud) d'instance en utilisant un seul URI. Cette fonction est fréquente dans le modèle, puisqu'elle permet de normaliser les données et de les récupérer en désignant ce à quoi le contenu de l'instance catégorisée se rapporte conceptuellement. Si cette instance catégorisée est également un type, le nœud doté d’un qualifiant spécifié est appelé un métatype. L'utilisation de nœuds dotés d’un qualifiant spécifié est récurrente dans le modèle comme moyen de mieux classifier les informations, facilitant ainsi les requêtes en fédérant les entités sous des types communs.

Outre les objectifs de catégorisation, les nœuds dotés d’un qualifiant spécifié sont parfois utilisés de manière descriptive pour identifier la propriété impliquée dans un patron conceptuel d'assignation d'attribut ou pour représenter les informations sémantiques relatives aux instances de [CRMpc](http://www.cidoc-crm.org/sites/default/files/CRMpc_v1.1_0.rdfs).

L'URI unique utilisé pour la catégorisation sera sélectionné dans un vocabulaire contrôlé ou un thésaurus particulier au projet DOPHEDA.

#### Nœud {#noeud}

Un nœud est un point d'interaction significatif dans le réseau sémantique du modèle. Il contient des informations et se connecte de manière non hiérarchique à d'autres nœuds afin de contextualiser et de lier ces informations. Les nœuds (dans le contexte de ce projet) peuvent être des [nœuds de saisie](#noeud-de-saisie) ou des [nœuds générés](#noeud-genere).

La réutilisation du CIDOC CRM ou de l'un des éléments de ses extensions est indiquée par la mention de leur code correspondant (p. ex. E21, P1, F52, R64, etc.). Parmi ceux-ci, seuls les éléments mobilisés par la Spécification du modèle cible du RCIP sont présentés ici; de plus amples informations sur le CIDOC CRM sont disponibles à l'adresse suivante : [http://www.cidoc-crm.org/](http://www.cidoc-crm.org/).

L'absence de code indique que le nœud a été créé par le RCIP (c'est surtout le cas pour les [nœuds de saisie](#noeud-de-saisie), qui contiennent des valeurs présentées par les soumissionnaires et converties en normes sémantiques à l'aide du modèle).

## Structure de la documentation

|---|---|
|**<a name="portee"></a>Portée**|Description des valeurs de données prises en compte par le [nœud](#noeud); cela inclut à la fois le type de données formel attendu et la signification sémantique du [nœud](#noeud) dans un graphe de connaissances (indiqué formellement par le chemin sémantique complet).|
|**<a name="liens-generes"></a>Lien·s généré·s**|Connexion du [nœud](#noeud) à la classe correspondante; cette connexion est automatiquement provoquée par l'association respective des liens à une entité de liaison commune.|
|**<a name="dependances"></a>Dépendance·s**|Liste de [nœuds](#noeud) qui doivent être remplis si le soumissionnaire utilise le [nœud](#noeud) actuel afin d'exécuter la mise en correspondance correctement. Plus d'un [nœud](#noeud) peut être requis et des [nœuds générés](#noeud-genere) peuvent être indiqués. Tous les [nœuds](#noeud) doivent être utilisés tels qu'ils sont présentés dans la Spécification des chemins sémantiques, à l'exception de la classe `E39_Actant`, où l'une de ses sous-classes, soit `E21_Personne` ou `E74_Groupe`, doit être utilisée.<br><br>Ce champ n'affiche que les [nœuds](#noeud) qui doivent être complétés si le [nœud](#noeud) actuel est documenté; il n'inclut pas tous les [nœuds](#noeud) qui pourraient apporter plus de sens au nœud actuel. Pour ce faire, la personne utilisant le modèle doit explorer les [vues de la Spécification du modèle cible](#vues-du-modele-cible) associées.|
|**<a name="ndqs-relies"></a>NDQS relié·s**|Ce champ indique le [nœud doté d’un qualifiant spécifié](#noeud-dote-dun-qualifiant-specifie-ndqs) (NDQS) lié qui est essentiel pour récupérer le nœud actuel. Le chemin menant au NDQS est inclus dans le chemin complet du nœud actuel et est mis entre parenthèses.|
|**<a name="chemin-complet"></a>Chemin complet**|Ce champ indique les classes et les propriétés qui seront générées lorsqu'une valeur se trouve dans le [nœud](#noeud) décrit. La convention suivante est utilisée : Classe -\> Propriété -\> Classe (-\> Propriété -\> [Nœud doté d’un qualifiant spécifié](#noeud-dote-dun-qualifiant-specifie-ndqs)) -\> Propriété -\> [**Nœud de saisie**](#noeud-de-saisie) (-\> Propriété -\> Nœud doté d’un qualifiant spécifié). Pour des raisons de lisibilité, les propriétés `rdfs:label` ne sont pas représentées. Toutes les classes doivent être utilisées telles qu'elles sont présentées dans la Spécification des chemins sémantiques, à l'exception de la classe `crm:E39_Actant`, qui indique que sa sous-classe, `crm:E21_Personne` ou `crm:E74_Groupe`, doit être utilisée lors de l'exécution d'une requête. Le point de départ du chemin complet est toujours la classe cible de la facette de la Spécification du modèle cible (c.-à-d. les actants ou les objets).|
|**<a name="vues-du-modele-cible"></a>Vue·s de la Spécification du modèle cible**|Ce champ recense les diagrammes de la [Spécification du modèle cible](/collections-model/fr/modele-cible/actuel/introduction) dans lesquels le [nœud](#noeud) est utilisé; ces diagrammes documentent les patrons conceptuels qui peuvent être utilisés pour modéliser des situations ciblées habituellement documentées par les soumissionnaires de données patrimoniales.|
|**<a name="evaluation-semantique"></a>Évaluation sémantique**|Indicateurs de la réutilisabilité interconnectée des valeurs fournies pour le [nœud](#noeud) selon les niveaux suivants :<br><br>*Faible* : données non standardisées qui doivent être traitées à l'aide du patron conceptuel [Données désordonnées](/collections-model/fr/modele-cible/actuel/donnees-desordonnees); elles ne seront donc sémantiquement pas expressives (c.-à-d. aucune nouvelle connaissance n'en sera déduite à travers le modèle), mais resteront néanmoins accessibles.<br><br>*Moyenne* : données normalisées qui nécessitent une normalisation supplémentaire afin de permettre l'expressivité sémantique. Après ce nettoyage, de nouvelles connaissances peuvent être déduites des données à travers le modèle, mais l'automatisation du processus de nettoyage induit un degré d'incertitude dans les déductions.<br><br>*Élevée* : données normalisées et nettoyées qui seront sémantiquement expressives une fois converties et qui généreront logiquement de nouvelles informations selon le modèle (créant ainsi un jeu de données facilement améliorable).<br><br>Chaque [nœud](#noeud) aura différents seuils de niveau qui seront documentés selon la convention suivante : « Niveaux : Éléments de qualification ».<br><br>Les données qui ne sont pas conformes au niveau d'évaluation sémantique le plus faible ne seront pas prises en compte par le modèle du RCIP. Le ou les Types de valeur acceptée seront indiqués pour chaque niveau, sauf le premier. Les types de valeur acceptée sont mentionnés dans les niveaux Moyenne et Élevée pour indiquer quel type de valeur doit être utilisé. Le niveau Faible n'a pas de champ Type·s de valeur acceptée, puisque tout y est acceptable.|
|**<a name="cas-typiques"></a>Cas typique·s**|Exemple·ss contextualisé·s de valeurs qui seraient considérées comme conformes à la [note d'application](#portee) du [nœud](#noeud).|
|**<a name="cas-limites"></a>Cas limite·s**|Exemple·s contextualisé·s de valeurs qui seraient considérées comme étant aux limites des paramètres de la [note d'application](#portee).|
|**<a name="origines-de-valeur"></a>Origine·s de valeur**|Source·s technique·s de la valeur dans le pipeline; cette provenance sera indiquée en utilisant la convention suivante : « Outil : Libellé du champ spécifique : Données du soumissionnaire » (p. ex. « Liste de vérification des actants : Identifiant de l'actant : Données du soumissionnaire »).|
|**<a name="liste-controleeterme"></a>Liste contrôlée/Terme**|Lien vers la liste contrôlée de termes (pour les nœuds de saisie qui s'appuient sur des vocabulaires externes) ou le terme unique (pour les [nœuds dotés d’un qualifiant spécifié](#noeud-dote-dun-qualifiant-specifie-ndqs)) avec lequel la valeur enregistrée doit être réconciliée (le RCIP sera chargé de ce processus de réconciliation). Si le vocabulaire mentionné est obligatoire, il sera indiqué en utilisant la convention suivante « Vocabulaire : Recommandation ».|
|**<a name="erreurs-potentielles"></a>Erreur·s potentielle·s**|La liste des erreurs potentielles qui pourraient découler de l'utilisation fonctionnelle du [nœud](#noeud) lorsqu'il est mis en application dans le pipeline.|
|**<a name="commentaires"></a>Commentaire·s**|Notes, explications et annotations pertinentes concernant le [nœud](#noeud).|
|**<a name="references"></a>Référence·s**|Citations bibliographiques pertinentes pour le [nœud](#noeud) et/ou utilisées pour définir sa [portée](#portee) ou d'autres champs descriptifs. Les références complètes (selon le style Chicago) sont fournies dans la bibliographie.|
