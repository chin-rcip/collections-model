---
layout: page
language: fr
title: Tutoriel CIDOC CRM
permalink: /fr/ressources/actuel/tutoriel-cidoc-crm
other_link: /en/resources/current/cidoc-crm-tutorial
sidebar: tutcidocfr
group: ressources
date: 2021-03-12
description: Ce document explique comment utiliser la documentation de CIDOC CRM afin de déterminer les entités susceptibles de répondre à un besoin particulier. Afin d’y parvenir, certains concepts associés aux données ouvertes et liées sont sommairement définis.
---

**Version:** 1.0

**Auteurs:** Karine Léonard Brouillet, Philippe Michon

**Date de création:** 2021-02-01

**Date de mise à jour:** 2021-03-12

## Résumé {#resume}

Ce document explique comment utiliser la documentation de CIDOC CRM afin de déterminer les entités susceptibles de répondre à un besoin particulier. Afin d’y parvenir, certains concepts associés aux données ouvertes et liées sont sommairement définis.


## Vocabulaire essentiel

### Classe

Une classe fédère des [instances](#instance) qui partagent des caractéristiques communes sur la base desquelles ces instances sont mobilisées similairement puisque des instances d’une même classe ont la possibilité d’utiliser les mêmes [propriétés](#propriete).

### Entité {#entite}

Une entité est un terme générique désignant les [classes](#classe) et [propriétés](#propriete) d’un modèle sémantique.

### Instance

Une instance est une occurrence spécifique d’une [classe](#classe).

### Propriété {#propriete}

Une propriété décrit le lien qui existe entre deux [instances](#instance).

## Versions et extensions

Le *Conceptual Reference Model* du *Comité International pour la Documentation* du *Conseil International des Musées* (CIDOC CRM) est une ontologie formelle dont la version originale anglophone est mise à jour sur une base régulière. Lorsque CIDOC CRM est utilisé à des fins de recherche, il s’avère la plupart du temps judicieux de se référer à la dernière version publiée. En date du 12 mars 2021, il s’agit de la version 7.1. Lorsque CIDOC CRM est utilisé à des fins d'implémentation d’un modèle, il est préférable de se référer à la version de laquelle découle le dernier fichier RDF disponible. Actuellement, il s’agit de la version 6.2.1.

La liste de toutes les versions est accessible [ici](http://www.cidoc-crm.org/versions-of-the-cidoc-crm).

CIDOC CRM sert aussi de fondement à d’autres modèles dont certains ont été approuvés par le CRM Special Interest Group (CRM SIG), comité qui maintient CIDOC CRM à jour. Ces extensions officielles se trouvent [ici](http://www.cidoc-crm.org/collaborations) et une fois que l’une d’elles a été sélectionnée, il est possible de consulter l’ensemble de ses versions en cliquant sur “Resources” dans le coin supérieur droit. Il existe par exemple une extension qui permet de gérer des données géospatiales qui s’intitule [CRMgeo.](http://www.cidoc-crm.org/crmgeo/)

## Structuration des entités de CIDOC CRM {#structuration-des-entites-de-cidoc-crm}

CIDOC CRM n’est pas une documentation conçue pour être lue du début à la fin. Il s’agit plutôt d’un document de référence qui nécessite une compréhension de certains concepts de base afin de naviguer efficacement.

### Nomenclature de CIDOC CRM

La partie principale du document se divise en deux grandes sections: *CIDOC CRM Class Declarations* et *CIDOC CRM Property Declarations*. Les classes dans CIDOC CRM sont toujours précédées d’un identifiant commençant par la lettre “E” suivie d’un ou deux chiffres. Par exemple, la classe “Place” est précédée de son identifiant qui est “E53” : `E53_Place`. Il en va de même pour les propriétés qui commencent toujours par la lettre “P” suivie d’un, deux ou trois chiffres (il y a plus de propriétés que de classes dans CIDOC CRM). Par exemple, la propriété “took place at” est précédée de son code “P7” : `P7_took_place_at`. À noter qu’il existe aussi une autre distinction de style entre les deux catégories: les mots contenus dans le nom d’une classe débutent toujours avec une majuscule (la seule exception étant le mot “of” qui est toujours en minuscule) alors que les propriétés sont toujours écrites en minuscules.

### Classes

Les classes sont des entités qui permettent de catégoriser un ensemble d’instances selon une définition commune. Par exemple, la valeur “Montréal” pourrait être considérée comme étant une instance de la classe `E53_Place`. En plus de partager une définition commune, les instances d’une même classe peuvent être liées à d’autres instances via le même ensemble de propriétés.

### Propriétés {#proprietes}

De leur côté, les propriétés servent à lier deux instances entre elles. C’est notamment ces liaisons qui mettent en lumière la sémantique associée aux données. Par exemple, il serait possible d’utiliser `P122_borders_with` entre “Montréal” et “Fleuve Saint-Laurent” afin d’indiquer que les deux instances partagent une frontière commune.

### Domaine et Portée {#domaine-et-portee}

Les propriétés ne s’appliquent pas automatiquement à toutes les instances. Deux concepts fondamentaux permettent de déterminer quelles propriétés peuvent s’appliquer à quelles instances: le domaine (en anglais: domain) et la portée (en anglais: range). Le domaine permet d’indiquer la classe de l’instance avec laquelle il est possible d’utiliser une propriété. Similairement, la portée indique la classe de l’instance qui sert de point d’arrivée à cette même propriété. Par exemple, `P122_borders_with` a à la fois pour domaine et pour portée `E53_Place`, ce qui valide l’exemple précédent puisque “Montréal” et le “Fleuve Saint-Laurent” sont tous les deux des instances de `E53_Place`. À noter qu’il est tout à fait possible, et même fréquent, que le domaine et la portée diffèrent. C’est notamment le cas de `P7_took_place_at` qui a pour domaine `E4_Period` et pour portée `E53_Place`.

### Super-classe/Sous-classe et Super-propriété/Sous-propriété {#super-classesous-classe-et-super-proprietesous-propriete}

Un autre concept important de CIDOC CRM est la hiérarchisation des entités (classes et propriétés). En effet, il est possible d’indiquer qu’une classe est la sous-classe d’une autre classe (cette dernière est alors nommée super-classe). Cette hiérarchisation est très importante, car une sous-classe hérite les propriétés de toutes ses super-classes. Par exemple, il est possible d’appliquer la propriété `P7_took_place_at` sur `E12_Production` même si le domaine de `P7_took_place_at` est `E4_Period`, car la chaîne de sous-classes suivante existe: `E4_Period`, `E5_Event`, `E7_Activity`, `E11_Modification` et `E12_Production`.

Cette hiérarchisation permet aussi d’identifier le niveau de précision que l’utilisateur devrait utiliser. Il est en effet préférable de choisir la classe la plus précise possible afin de pouvoir profiter d’une grande variété de propriétés et d’ainsi favoriser des recherches plus spécifiques au sein d’un corpus. Cette hiérarchisation existe aussi au niveau des propriétés et s’avère utile pour impartir le niveau de précision souhaité par le modélisateur grâce à des liens spécifiques.

## Cadre conceptuel de CIDOC CRM

Le modélisateur peut explorer la hiérarchie des sous-classes en utilisant les domaines et les portées afin d’explorer les propriétés qui sont associées à ces (sous-)classes sans pour autant devoir lire l’intégralité du document. Il est néanmoins utile de connaître les principes conceptuels de CIDOC CRM afin d’identifier plus rapidement les entités pertinentes à un travail sans toujours commencer par examiner `E1_CRM_Entity` qui est une classe très générique.

### Entités temporelles {#entites-temporelles}

CIDOC CRM est structuré autour de la notion d’entité temporelle (`E2_Temporal_Entity`). Ainsi, dans la majorité des cas, la modélisation d’une information issue d’un jeu de données nécessite l’utilisation d’une sous-classe de `E2_Temporal_Entity`. Par exemple, pour indiquer la date de production d’un objet, il est nécessaire d’associer une date non pas à l’objet produit, mais bien à l'évènement de sa production (ce pourquoi il est utile de connaître les principales sous-classes de `E2_Temporal_Entity`).

Ces entités temporelles sont dites “perdurantes” car elles évoluent dans le temps de sorte qu’il est impossible de réduire l’entièreté d’une entité temporelle à un instant *t* (le contraire d’une entité “endurante” qui elle contient toutes ses caractéristiques à un instant *t*). CIDOC CRM utilise la classe `E77_Persistent_Item` pour définir ces entités endurantes qui sont essentiellement des acteurs (personnes ou groupes) et des choses (notamment des objets physiques et des concepts).

Certaines entités ne font partie d’aucune de ces deux catégories; c’est notamment le cas des intervalles de temps (p. ex. `E52_Time-Span`) et des lieux (p. ex. `E53_Place`).

### Classes principales de CIDOC CRM

Afin de faciliter la recherche dans la documentation de CIDOC CRM, certaines classes peuvent être utilisées comme point de départ afin d’identifier l’entité centrale la plus appropriée à un besoin. Le diagramme suivant met en lumière les classes principales de CIDOC CRM:

![](/collections-model/images/cidoc_tut_1.png)

`E2_Temporal_Entity` et ses sous-classes permettent de lier les acteurs qui ont participé à un évènement avec les objets physiques ou conceptuels utilisés ou créés lors de ce même évènement. La durée de ce dernier peut être indiquée par l’usage de la classe `E52_Time-Span`, ainsi que les lieux où se déroule l’action grâce à l’usage de la classe `E53_Place`.

De manière générale, deux classes essentielles traversent l’entièreté du modèle et sont utiles lorsque vient le temps de nommer une instance (`E41_Appellation`) ou d’en préciser la nature (`E55_Type` associé à des vocabulaires externes).

### Gestion de la temporalité dans CIDOC CRM {#gestion-de-la-temporalite-dans-cidoc-crm}

La gestion de la temporalité au sein de CIDOC CRM est souvent un élément difficile à comprendre lors d’une première utilisation du modèle. Il faut tout d’abord savoir que CIDOC CRM utilise uniquement des *intervalles* afin de documenter le passage du temps. Ce principe est important, car il permet de rendre compte adéquatement du flou qui entoure la temporalité d’un évènement : en effet, les données patrimoniales ne représentent qu’une approximation (aussi précise soit-elle) du moment exact où un évènement s’est produit dans le monde qu’elle décrivent. Même en connaissant le moment exact (à la seconde près) où un évènement a débuté, un flou demeure quant au dixième de seconde où il a eu lieu, et ainsi de suite vers des intervalles toujours plus petits. C’est sans compter le flou attesté qui entoure souvent un évènement alors que la période durant laquelle il s’est produit est connue, mais sans plus.

Trois propriétés (illustrées ci-dessous) permettent de documenter l’intervalle de temps durant lequel s’est produit un évènement :

![](/collections-model/images/cidoc_tut_2.png)

Premièrement, la durée permet d’indiquer pendant combien de temps l’événement s’est déroulé (`P191_had_duration`): l'événement a duré trois jours. Deuxièmement, il y a le moment durant lequel il est établi que l’évènement avait cours (`P81_ongoing_throughout`) : l’évènement avait lieu le 2 février 2020 (il est possible qu’il ait commencé avant ou qu’il se soit terminé après, mais il est établi que le 2 février 2020 cet évènement était en cours). Troisièmement, il y a la période durant laquelle l’entièreté de l’évènement s’est déroulée, période qui est définie par les limites temporelles (`P82_begin_of_the_begin` et `P92b_end_of_the_end`, qui ne sont pas recensées dans la spécification actuelle de CIDOC CRM) où il est établi que l'événement n’avait *pas* cours (`P82_at_some_time_within`). Cette dernière option est la plus souvent utilisée.

## Identifier la bonne entité {#identifier-la-bonne-entite}

Il existe plusieurs interfaces de consultation de la spécification de CIDOC CRM. Certaines versions (comme la [version 6.2](http://www.cidoc-crm.org/Version/version-6.2)) ont été générées en HTML afin que chaque entité puisse être consultée sur une page web dédiée. On y trouve notamment l’ensemble des propriétés qu’une classe peut mobiliser, y compris celles qui sont associées à ses superclasses. Ceci permet d’identifier aisément les propriétés qu’il peuvent être utilisées avec une classe donnée.

Cependant, les versions les plus récentes, qui sont toujours en cours sous la forme de documents de travail (comme la [version 7.0](http://www.cidoc-crm.org/Version/version-7.0)), ne sont disponibles qu’en format .docx ou .pdf.

Chaque entité est décrite à l’aide d’une série de champs dont certains sont essentiels pour assurer une recherche efficace:

  - Pour les classes:
    
      - “Subclass of” et “Superclass of” identifie les classes à un niveau de distance de la classe consultée dans la hiérarchie. L’utilisateur peut aussi avoir une vue de l’ensemble de la hiérarchie en consultant les pages xxxiv à xxxvi de la spécification de CIDOC CRM ([version 7.1](http://www.cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf)).
    
      - “Scope Note” définit les instances qui font partie d’une classe.
    
      - “Examples” illustre la nature des instances mentionnées dans le “scope note”.
    
      - “Properties” identifie les propriétés dont la classe consultée est le domaine (et, du même coup, quelle est la portée de cette même propriété). Cependant, ceci ne recense que les propriétés qui ont la classe pour domaine et non pas l’ensemble des propriétés qui peuvent y être associées (lesquelles incluent les propriétés associées aux superclasses de la classe consultée). Les propriétés inverses ne sont pas non plus documentées dans la spécification de CIDOC CRM. Ainsi, les propriétés inverses n’apparaissent pas dans le champ “Properties” des classes et il est nécessaire de se référer à la hiérarchie générale pour avoir un aperçu de l’ensemble des propriétés, de leurs domaines et de leurs portées.

  - Pour les propriétés:
    
      - “Domain” et “Range” identifient rapidement le domaine et la portée de la propriété consultée.
    
      - “Subproperty of” et “Superproperty of” permettent de naviguer dans la hiérarchie des propriétés.
    
      - “Scope Note” définit la nature du lien entre deux instances.
    
      - “Examples” illustrent la nature du lien entre deux instances.

## Aide-mémoire {#aide-memoire}

  - Il n’est pas nécessaire de lire le document dans son intégralité. Jongler avec les sous-classes, les superclasses, les sous-propriétés, les super-propriétés, les domaines et les portées s’avère le moyen le plus efficace de trouver les entités CIDOC CRM susceptibles de répondre aux besoins d’implémentation de l’utilisateur.

  - La hiérarchie complète des classes et des propriétés se trouve dans l’introduction de la spécification CIDOC CRM et donne un bon aperçu des entités utilisables pour mobiliser ce standard.

  - Les propriétés associées à une classe spécifique ne constituent pas nécessairement l’entièreté des propriétés utilisables de concert avec cette classe de sorte qu’il est nécessaire d’analyser les propriétés de ses superclasses ainsi que les propriétés inverses qui peuvent y être associées.

  - Les entités temporelles sont au cœur de CIDOC CRM et il est pertinent d’y revenir souvent afin d’identifier les entités répondant aux besoins d’implémentation du modélisateur.

  - Finalement, il est possible que CIDOC CRM ne réponde pas à tous les besoins; l’analyse des extensions existantes ou la création d’une extension locale sont de bonnes manières de répondre à des besoins particuliers
