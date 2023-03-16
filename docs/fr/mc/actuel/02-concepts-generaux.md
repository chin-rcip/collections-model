---
layout: page
language: fr
title: Concepts généraux
permalink: /fr/modele-cible/actuel/concepts-generaux
other_link: /en/target-model/current/general-concepts
sidebar: mc22
date: 2022-06-30
description: La Spécification du modèle cible des actants modélise sémantiquement les actants dans un contexte patrimonial. Les patrons conceptuels les plus pertinents pour la vie des actants sont présentés avec des diagrammes et des exemples qui les illustrent, ainsi qu'un compte rendu et une explication des décisions pertinentes qui ont été prises lors de l'élaboration desdits patrons conceptuels. Il s'agit d'une documentation théorique qui n'a jamais été testée ou mise en application.
---

## Priorisation de `E55_Type` et `P2_a_pour_type` sur les nouvelles classes et propriétés {#priorisation-de-e55_type-et-p2_a_pour_type-sur-les-nouvelles-classes-et-proprietes}

### Contexte {#priorisation-de-e55_type-et-p2_a_pour_type-sur-les-nouvelles-classes-et-proprietes-contexte}

Parce que le CIDOC CRM est une ontologie développée pour servir le secteur culturel dans son ensemble, ses entités sont intentionnellement de portée générale pour répondre adéquatement aux besoins et aux compréhensions des diverses disciplines patrimoniales (p. ex. archéologie, art, histoire, sociologie). Toutefois, cette généralité peut présenter une limite lors de la modélisation de concepts complexes (p. ex. relations, techniques, occupations) qui englobent eux-mêmes d'autres concepts et présentent de nombreuses caractéristiques. Cette complexité peut entraver les processus d'enregistrement et de requête qui seraient autrement simples d'un point de vue sémantique. Ainsi, il est conseillé de simplifier ces processus en qualifiant davantage les classes complexes afin d'améliorer leur précision sémantique (Bekiari et al. 2021, sect. About Types). Cela peut se faire de deux manières. 

Une option consiste à créer de nouvelles classes et propriétés. Toutefois, cette pratique n'est pas recommandée par le RCIP, car elle conduit à un modèle alambiqué (complexifiant ainsi le processus de mise en correspondance) et à un plus grand nombre d'entités à gérer (compliquant ainsi les requêtes des personnes impliquées). De plus, pour assurer l'efficacité d'un modèle, les ressources technologiques et humaines qu'il requiert doivent être réduites au minimum tout au long de son cycle de vie (phases de développement, de mise en application et de maintenance), un principe auquel la création de classes et de propriétés contrevient. Il est donc recommandé de :

* Limiter les champs d'expertise qu'un modèle accueille et représente (Bruseker 2017, 25);
* Éviter l'inclusion de patrons conceptuels qui répondent à des impératifs *technologiques* plutôt qu'*informationnels* (Gruber 1995, 910); 
* Privilégier l'utilisation de classes et de propriétés préexistantes plutôt que la création, la documentation et la maintenance de nouvelles classes et propriétés. 

Une pratique courante pour relever ce défi consiste à utiliser des vocabulaires externes pour catégoriser les entités génériques. Cette approche présente plusieurs avantages : 

* Elle nécessite moins de ressources que la maintenance et la gestion internes d'entités spécialisées (Doerr et al. 2020, xxxviii); 
* Elle facilite l'interopérabilité entre les modèles, car la réconciliation d'entités spécialisées entre différents modèles est plus compliquée que celle de termes entre des vocabulaires communs; 
* Elle permet aux organisations de s'appuyer sur un ensemble de compétences que leurs professionnels·les possèdent déjà (c.-à-d. la gestion du vocabulaire). 

Pour ces raisons, le RCIP a décidé de s'appuyer fortement sur l'utilisation de vocabulaires externes plutôt que sur la création de nouvelles entités.

### Description {#priorisation-de-e55_type-et-p2_a_pour_type-sur-les-nouvelles-classes-et-proprietes-description}

Ainsi, la classe `E55_Type` et la propriété `P2_a_pour_type` sont utilisées pour spécifier des entités plutôt que de créer de nouvelles sous-classes et sous-propriétés. 

Par exemple, dans le patron conceptuel [Identifiants et appellations de l'actant](/collections-model/fr/modele-cible/actuel/identifiants-et-appellations-de-lactant), l'appellation d'un actant est qualifiée par la propriété `P2_a_pour_type` et un vocabulaire contrôlé est utilisé pour désigner le type de cette appellation, qui est une instance de `E55_Type`.

<a name="095_Convention_E55_Type_FRA_p"></a>095_Convention_E55_Type_FRA_p

<div class="mxgraph" style="max-width:100%;border:1px solid #cccccc;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;target&quot;:&quot;blank&quot;,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom layers lightbox&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;xml&quot;:&quot;&lt;mxfile host=\&quot;app.diagrams.net\&quot; modified=\&quot;2023-03-15T17:12:55.923Z\&quot; agent=\&quot;5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) draw.io/20.3.0 Chrome/104.0.5112.114 Electron/20.1.3 Safari/537.36\&quot; etag=\&quot;EkBscyGfEb--MlbQexda\&quot; version=\&quot;20.3.0\&quot;&gt;&lt;diagram id=\&quot;f60aMePYo0SVpJyMsOzK\&quot; name=\&quot;Page-1\&quot;&gt;rVXfb5swEP5roj4R8SNkyWObJtmkTa2WVuuekIMv4M5gZkwC++t3BhNArFkrJS/xfb7znb/vfEy8VVJuJcnib4ICn7g2LSfe/cR1rcVsgX8aqRrEacxIMjoCduwPGNA2aMEo5ANHJQRXLBuCoUhTCNUAI1KK09DtIPgwa0YiGAG7kPAx+oNRFTfowrc7/DOwKG4zO7bZSUjrbIA8JlScepC3nngrKYRqVkm5Aq6pa3lp4jZv7J4Lk5Cq9wR83y6T5weHvvrJ4+r2i5Us+dZyzDFHwgtz40c3IEEmChmoKgNTu6paQoAiP8YUUsUiEinh6w69k6JIKeisNlqdz1chMgQdBF9BqcqITQolEIpVws0ulEy99NY/9VFT31j3pTm5NqrWSJWsXvpGL0qbXVhttXFjFg0jOTIQwiXqXNOOREagLjnOGkfNXC+FUWkLIgGsCB0kcKLYcdh5xDRwdPbrNMaFkfkjkrsjydeeFzzsUZSAsxRfXK7Yb9xz5xzvdbeXuIr0aj1zgtsswyRYp0hHvdEpr6U7xUzBLiM1iyccDkOVD4zzleBC1rFeWP/elOMIUkF5kT6zu/hkHlw7b5bGPnXv1/EMFvfe7tz+MOPPOUhNHA4e1+ZkD7wJPVPXMvdUPyWb3pA+fTbVIL8hoSJ4XxOEOc5x/9DA94On88NEvX41KWOl9Ei81aW6mzBmqSVDlk0jpuJiP2VCo4JzrBVz51bSDOrNAU/e5BmE7MDCui4LB64VxpAwdMshwdJ0O+Toh4UWdVQqoKA5elo5YTnDajw9LSzau5/e5e3V3P+25aynqunjK7XWgez9uX+F1nIc9x295V6nt9DstVcLdd+L2r33zfXWfwE=&lt;/diagram&gt;&lt;/mxfile&gt;&quot;}"></div>

**Exemple** : Yousuf Karsh est le nom complet (`E55_Type`) de ce photographe arméno-canadien.

<div id="0001_100_appellation-full-name" class="example"></div>

En plus de cette considération, lorsque plusieurs instances de `E55_Type` accueillant différents types d'informations sont attachées aux mêmes entités, un autre niveau de `E55_Type` désigne le premier `E55_Type` avec un second métatype de `E55_Type`, qui est utilisé pour récupérer facilement des informations comparables au stade de requête.

Par exemple, dans le patron conceptuel [Identifiants et appellations de l'actant](/collections-model/fr/modele-cible/actuel/identifiants-et-appellations-de-lactant), l'appellation d'un actant est qualifiée à la fois par une valeur du type d'appellation sélectionnée dans un vocabulaire associé (p. ex. Nom complet, Pseudonyme) et par une valeur du type de primauté également sélectionnée dans un vocabulaire associé (p. ex. Préférée, Non préférée). Chacune de ces valeurs sélectionnées, instances de `E55_Type`, est encore qualifiée à l'aide de la propriété `P2_a_pour_type` et des libellés de vocabulaire décrivant leurs catégories plus larges respectives, « Primauté » et « Type d'appellation », qui sont également des instances de `E55_Type` (afin que le type d'information trouvé dans chaque `E55_Type` puisse être facilement identifié par la personne utilisant le modèle).

<a name="096_Convention_E55_Metatype_FRA_p"></a>096_Convention_E55_Metatype_FRA_p.drawio

<div class="mxgraph" style="max-width:100%;border:1px solid #cccccc;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;target&quot;:&quot;blank&quot;,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom layers lightbox&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;xml&quot;:&quot;&lt;mxfile host=\&quot;app.diagrams.net\&quot; modified=\&quot;2023-03-15T17:12:56.147Z\&quot; agent=\&quot;5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) draw.io/20.3.0 Chrome/104.0.5112.114 Electron/20.1.3 Safari/537.36\&quot; etag=\&quot;mHLQ4hLJ4MkeJrVccXD_\&quot; version=\&quot;20.3.0\&quot;&gt;&lt;diagram id=\&quot;f60aMePYo0SVpJyMsOzK\&quot; name=\&quot;Page-1\&quot;&gt;1VjbctowEP0aT5/M+IK5PAIB+pBMmSadJk+MsGVbjWy5srj167uyZWxjQoEhacgwGevsri6756wFmj2KNlOOkvCBeZhqluFtNPtOsyxLkx/D2+ZDMx8GnHgN4JH8wQo0FLokHk5rjoIxKkhSB10Wx9gVNQxxztZ1N5/R+qoJCnADeHQRbaI/iSfCHO05Rol/xSQIi5VNQ1kiVDgrIA2Rx9YVyB5r9ogzJvKnaDPCVOatyEseN3nDutsYx7E4JeD+AQ2/T38/+a9BfzYl+mCzsnVVmxWiS3XgmTVH84Qt+VxsE6y2LrZFPrAH6VFDxkXIAhYjOi7RIWfL2MNyUQNGpc89YwmAJoC/sBBbVWu0FAygUERUWeE8fPus4rPBixy0nGJ4t6ka77bFaEPEc+kJo5eKpQySgyKmmUSV1xQy4OIjmWsrMiIeYHHEryCyTFxlBVWjKWYRhkOAA8cUCbKq8w4p+gY7v13ojBHYs2UolbX77VbP6ZptK//fzydQorPbvVbF2Ot06/Pnx1BTliSCh8oeSyij1hk0sz8jzQ7SxTxKl0up+f4061ybZTUKnFvvdqPeY9uef1tAReaUxNDUU0F+g83qUDjVcMHhKZBP47Y5HyQJrAHbZHGDGGXZZaXWIRH4MUFZCtfw8qmX2CeUjhhlPIu13ezvzVqsMBd4czR7yup0jZq6rKLpr8tXhGkrLKy8HjrGOyXc+YQCu5z0nVN7q/VBrP+RYi7Z68qGS9EC0zx0x9+Cvk9ZrnMQ5tjhB4juOPOnXWVAFK/5lKEQ8mozkFuxJm5IYp27JGkFRITLRYswiTJKYS+gj1SP8tvWxIeZJ2mCXeITN9OODhcn3Q1xRMAtxRGKM82l4IdcscyiYoaXXgqeeopISmA3tqSL7qFSg9JKIQKpd8NxJnYqFVDMvZJ8fbRwOs4V5Nu19+TbN1tOU8DWdQQMwwp9ztB0v6HpgkUeWRU0ymReYVzFdMC70g8OR9zObe/y7lLcyP7dXswT24vilW60VEO69C5XuDDfT/GZN7GTe9SMkwjqoI1sbdCXX8ywDPhSUXwFVLK/6Y6W5AfGeSO7tLGZhnZznc00D1xM/ndfK2RVvR3uqLNPKm1kaQMgm7HPWmkYNjvWpyhD3/m4MpyY8+YX/RNynpsNb6833FLqrf67KqD8+SZv0OXvX/b4Lw==&lt;/diagram&gt;&lt;/mxfile&gt;&quot;}"></div>

### Exemples {#priorisation-de-e55_type-et-p2_a_pour_type-sur-les-nouvelles-classes-et-proprietes-exemples}

Yousuf Karsh est le nom complet (`E55_Type`, Type d'appellation de l'actant) préféré (`E55_Type`, Primauté de l'appellation de l'actant) de ce photographe arméno-canadien.

<div id="0001_100_appellation-precedence" class="example"></div>

### Enjeux connexes sur GitHub {#priorisation-de-e55_type-et-p2_a_pour_type-sur-les-nouvelles-classes-et-proprietes-enjeux-connexes-sur-github}

* [Enjeu n° 37 « Utilité de `E55_Type` »](https://github.com/chin-rcip/collections-model/issues/37) (en anglais)

## Différences entre `E39_Actant`, `E21_Personne` et `E74_Groupe` {#differences-entre-e39_actant-e21_personne-et-e74_groupe}

La plupart des données patrimoniales relatives aux personnes ou aux groupes sont centrées sur les *créateurs·rices* d'artefacts et, à ce titre, les patrons conceptuels des actants de la Spécification du modèle cible sont centrés sur la classe `E39_Actant` qui « comprend les personnes, soit individuellement ou en groupes, qui ont le potentiel d'effectuer des actions intentionnelles pour lesquelles quelqu'un peut être tenu responsable » (Le Bœuf et al. 2015, sect. E39 Actor; notre traduction).

Il existe deux sous-classes de `E39_Actant` : 

* `E21_Personne`, qui comprend les personnes réelles;
* `E74_Groupe`, qui représente tout type de rassemblement ou d'organisation d'instances de `E39_Actant` agissant collectivement. Comme indiqué dans le CIDOC CRM, « un rassemblement de personnes devient un `E74_Groupe` lorsqu'il présente des caractéristiques organisationnelles généralement caractérisées par un ensemble d'idées ou de croyances communes, ou d'actions réalisées ensemble » (Le Bœuf et al. 2015, sect. E74 Group; notre traduction).

En termes de mise en correspondance, lorsqu'il est possible de distinguer une personne d'un groupe dans un jeu de données d'origine, l'utilisation des sous-classes plus précises `E21_Personne` et `E74_Groupe` doit être privilégiée par rapport à celle de la classe `E39_Actant` pour les raisons suivantes :

* La maintenance du processus de mise en correspondance est plus efficace, car la modélisation d'une instance de `E21_Personne` n'est pas complètement identique à la modélisation d'une instance de `E74_Groupe`;
* Le nettoyage des données est facilité par une réconciliation plus précise et plus efficace à long terme.

Cependant, dans certains cas, il est acceptable d'utiliser la classe `E39_Actant` (`E77_Entité_persistante`) plutôt que l'une de ses sous-classes :

* Lorsqu'il est incertain si l'actant est une personne, une organisation ou un groupe (Linked.art 2019);
* Lorsqu'un jeu de données peut contenir des données relatives à la fois aux actants et aux groupes dans un seul champ.

Si un jeu de données d'origine initialement mis en correspondance à l'aide de la classe `E39_Actant` est mis à jour pour distinguer les personnes et les groupes, sa mise en correspondance doit être mise à jour pour utiliser les sous-classes de la classe `E39_Actant` (`E21_Personne` et `E74_Groupe`). Cela peut être fait avec une requête de mise à jour SPARQL.

Bien que la Spécification du modèle cible offre techniquement la possibilité d'utiliser soit `E39_Actant`, `E21_Personne` ou `E74_Groupe`, la Spécification des chemins sémantiques n'offre pas cette latitude.

## Différences sémantiques entre les libellés, les annotations ou les commentaires, et les contenus littéraux {#differences-semantiques-entre-les-libelles-les-annotations-ou-les-commentaires-et-les-contenus-litteraux}

Les données patrimoniales littérales (p. ex. le contenu d'un texte) peuvent généralement être classées en trois types de chaînes de caractères : 

* Libellés;
* Annotations ou commentaires;
* Contenu littéral.

Il existe plusieurs façons de lier ces données, chacune d'entre elles étant destinée à tenir compte d'un type précis d'énoncé lisible par l'humain. Le choix de la propriété à attribuer à une ressource indique de quel type d'énoncé il s'agit et comment les données sont gérées. 

### Libellés {#libelles}

#### Contexte {#libelles-contexte}

Les libellés sont utilisés pour fournir une version lisible à l'humain de l'identification d'une ressource en plus de son identifiant de ressource uniforme ou *uniform resource identifier* (URI). Une ressource peut avoir plus d'un libellé, notamment en raison des langues utilisées pour s'y référer (p. ex. un libellé en français, un second en anglais). 

#### Description {#libelles-description}

Les libellés sont rendus avec la propriété `rdfs:label`.

<a name="007_PatronConceptuel_Libelles_p"></a>007_PatronConceptuel_Libelles_p

<div class="mxgraph" style="max-width:100%;border:1px solid #cccccc;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;target&quot;:&quot;blank&quot;,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom layers lightbox&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;xml&quot;:&quot;&lt;mxfile host=\&quot;app.diagrams.net\&quot; modified=\&quot;2023-03-15T17:12:50.067Z\&quot; agent=\&quot;5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) draw.io/20.3.0 Chrome/104.0.5112.114 Electron/20.1.3 Safari/537.36\&quot; etag=\&quot;DH171ALYKYld9rnUZLkw\&quot; version=\&quot;20.3.0\&quot;&gt;&lt;diagram id=\&quot;1uye8jos9k4TIMqE3fPV\&quot; name=\&quot;Page-1\&quot;&gt;xVRNb5wwEP01HFPxkWyS45alG7WJqmQPbXJZOXgCrgyDhmGB/vqaxSwglFV7aCtx8HvzjO33PHaCMGu2JIr0ASVox3dl4wQbx/d9p/tc2fbQ62FCSi6InfoJlnQtWykJ5UzIiJpVMSdjzHOIecYJIqznsjfU81ULkcCC2MVCL9lvSnLaszf+9cjfgUrSYWVvddtXMjGI7UnKVEisJ1QQOUFIiNyPsiYE3fk2+NLP+/RO9bQxgpx/Z0JMj/vtZfw18Tjfr14+H+6+0IX9y0Hoyh6Y5JuxbK3FaxficePcDm6ANOZYiMQpJpgLHY3sR8Iql9At6Ro0au4RC0N6hvwBzK1NWlSMhko507ZqTkPtdzv/CJ478OFqgJtmWty0Fi3tsGcrsaIYznhg7ycLSoDP6IJe13kwWcCavQXMwOzHCAi0YHWYXyBh72Fy0o1RmYFN6w+S8xfJRd4+ylmxEwbO+nYfPj0s8hvT6ayuU8WwK8TRndq07jyJdx09ADE0Zz0YWt+1l9/2/qkZ6rGXvIFLJ320cv+SbcHCtqY0+nXJpPLkvxt2efXvDDNwfH2OtcnzHUS/AA==&lt;/diagram&gt;&lt;/mxfile&gt;&quot;}"></div>

#### Exemples {#libelles-exemples}

Par exemple, si l'occupation d'un photographe est documentée à l'aide d'un [URI du Art & Architecture Thesaurus (AAT)](http://vocab.getty.edu/aat/300025687), le libellé « Photographes » doit être ajouté à cet URI afin que les humains puissent comprendre quelle est cette occupation sans avoir à se référer au site Web du Getty. 

<div id="aat_300025687_label" class="example"></div>

Un autre exemple est celui des évènements de naissance où les mécanismes de concaténation (au stade de la mise en correspondance) peuvent fournir des libellés descriptifs utiles tels que « Naissance de Yousuf Karsh » pour une instance de `E67_Naissance` représentant la naissance de Yousuf Karsh; de cette façon, la fonction du nœud est facilement compréhensible pour les humains.

### Annotations ou commentaires

#### Contexte {#annotations-ou-commentaires-contexte}

Les données patrimoniales étant issues de recherches intensives, les annotations et les commentaires font partie intégrante de la qualification d'un enregistrement ou même d'une donnée précise. On les distingue en deux types :

* Annotations qui apparaissent au cours du processus de mise en correspondance et qui concernent, par exemple, des enjeux de qualité des données, de modélisation et/ou de mise en correspondance, ou de l'information que le soumissionnaire de données souhaite soumettre à l'environnement DOPHEDA en même temps que le jeu de données;
* Annotations qui font partie du jeu de données original, telles que des notes curatoriales ou de recherche.

Le premier type est décrit dans cette section, tandis que le patron conceptuel [Note curatoriale](/collections-model/fr/modele-cible/actuel/note-curatoriale) doit être utilisé pour le second.

#### Description {#annotations-ou-commentaires-description}

En fonction de ce qui fait l'objet d'un commentaire, les annotations sur une ressource sont rendues soit par :

* La propriété du CIDOC CRM `P3_a_pour_note`, qui est utilisée pour les [annotations](collections-model/fr/specification-des-chemins-semantiques/actuel/noeud-de-saisie#annotation) concernant des valeurs de données précises (p. ex. « l'URL de l'image n'est pas valide/ne fonctionne pas »); ou
* La propriété RDFS [`rdfs:comment`](https://www.w3.org/TR/rdf-schema/#ch_comment), qui est utilisée pour les commentaires relatifs aux classes et aux propriétés d'un modèle de données (p. ex. « Cette propriété identifie l'instance E24 Chose matérielle élaborée par l’humain qui a été diminuée par une instance de E80 Retrait d’élément »).

Les propriétés `P3_a_pour_note` et `rdfs:comment` font des énoncés sur le contenu de la ressource, mais ne comprennent pas son contenu. Par exemple, la propriété `P3_a_pour_note` appliquée à une instance de `E33_Objet_linguistique` permet d'annoter le texte, mais ne l'inclut pas (pour de plus amples informations sur le contenu, voir la section [Contenu littéral](collections-model/fr/modele-cible/actuel/concepts-generaux#contenu-litteral).

#### Diagramme {#annotations-ou-commentaires-diagramme}

<a name="008_PatronConceptuel_AnnotationsCommentaires_p"></a>008_PatronConceptuel_AnnotationsCommentaires_p

<div class="mxgraph" style="max-width:100%;border:1px solid #cccccc;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;target&quot;:&quot;blank&quot;,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom layers lightbox&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;xml&quot;:&quot;&lt;mxfile host=\&quot;app.diagrams.net\&quot; modified=\&quot;2023-03-15T17:12:50.291Z\&quot; agent=\&quot;5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) draw.io/20.3.0 Chrome/104.0.5112.114 Electron/20.1.3 Safari/537.36\&quot; etag=\&quot;UFEU1w6mXvsdZKbOEubj\&quot; version=\&quot;20.3.0\&quot;&gt;&lt;diagram id=\&quot;GJdnDhDloI1vw7WJk8cn\&quot; name=\&quot;Page-1\&quot;&gt;1VZtb5swEP41fKTiJUnXjykJnbRVm5ZVbfclMnABd8ZmxuSlv37nYAIINUsmde0kPvieO9vn57k7YflBvr2RpMhuRQLM8pxka/kzy/M8S39OsqtNtzZTSZMBsKDPYEDHoBVNoOwFKiGYokUfjAXnEKseRqQUm37YSrD+rQVJYQAsYsKG6D1NVFajH7zLFv8INM2am93JVe3JSRNsXlJmJBGbDuTPLT+QQqh6lW8DYJq3hpd6X/iC95CYBK5O2ZCyuzB+uA+eP/2IxhH/vkp5ZU/qU9aEVebBX/0lWRaikksuFJjU1a7hAxKkx5hCqkykghM2b9FrKSqegL7UQauN+SxEgaCL4BMotTNak0oJhDKVM+PF98jdg9m/Nx61cTFuzNm265ztjDUkxHBU4mtiOMJCU1hEpqCOxJlK1hx0LjB034DIAfPBAAmMKLrulxAxlZge4lqxcGH0OkM7d6Dd3F3OuaLKCnxrerUMvt0O9GvV0VRvMqpgUZA9Oxts3r4SLzK6Bqlge5SDpvkdU/6m+w/tsGm7yW2wrNNJE+ds2u5KkF+iJz0GPIeRCFi91fImDE+9jnCR6sWUY22jQoI3Ljzp4D2EywbZlkjYtFSS8rTOilH+sz48U0qPoqlOygvjjHJbxrS4SKnKquiCCo0KxjArvK+083o6his8PSwLiOmKxvtcbBx0dpxBTjGshJyglL8qHH5eSGJV7XdxAVVSYqRdElpS7E+fdB7j/almvI5YpsbesDhG439XHGh26uOMNrsctJlMVlrxWOS5fvsbjMi/H3WjE0fd+F2NutH/OOr8V6zm02gbD2gbTrJ31P6vSRia7a/W3tf5V/XnvwE=&lt;/diagram&gt;&lt;/mxfile&gt;&quot;}"></div>

#### Exemples {#annotations-ou-commentaires-exemples}

L'[URI du AAT](http://vocab.getty.edu/aat/300025687) est utilisé comme instance de l'occupation « Photographes », mais seul un libellé en anglais est disponible, sans équivalent en français déjà établi. Cette information peut être mentionnée dans le cadre d'une annotation à l'URI du AAT (`E33_Objet_linguistique`, `P3_a_pour_note`).

<div id="aat_300025687_label-note" class="example"></div>

#### Discussion {#annotations-ou-commentaires-discussion}

Le nœud de saisie [Annotation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#annotation), qui repose sur la propriété `P3_a_pour_note`, doit être utilisé dans les cas limites où un élément est trop complexe et subtil pour être correctement pris en compte par les patrons conceptuels actuels, et trop précis pour justifier la création d'un nouveau patron conceptuel. Il doit être utilisé par les soumissionnaires de données pour clarifier l'information sur une valeur de données, tandis que la propriété `rdfs:comment` doit être utilisée par la personne créant un modèle pour ajouter directement de l'information sur celui-ci. 

#### Nœuds de saisie {#annotations-ou-commentaires-noeuds-de-saisie}

*Il n'y a pas de nœuds de saisie pour les commentaires, car ils ne se rapportent pas aux valeurs des données elles-mêmes (ils ne proviennent donc pas du soumissionnaire de données et/ou du processus de mise en correspondance des données)*. 

* [Annotation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#annotation) \| Liste de vérification

#### Enjeux connexes sur GitHub {#annotations-ou-commentaires-enjeux-connexes-sur-github}

* [Enjeu no 32 « Devrions-nous utiliser `P3 a pour note` ou `rdfs:comment`? »](https://github.com/chin-rcip/collections-model/issues/32) (en anglais)

### Contenu littéral {#contenu-litteral}

#### Contexte {#contenu-litteral-contexte}

Les jeux de données patrimoniales contiennent souvent, sinon toujours, des contenus décrivant des ressources telles que des appellations, des biographies ou des descriptions trop complexes ou détaillées pour être entièrement sémantisées et dont la forme textuelle ou « libre » doit donc être conservée. En outre, les données non structurées qui ne peuvent pas être correctement « nettoyées » avec la technologie et les ressources actuelles sont également traitées comme des contenus textuels littéraux (pour plus de détails, voir le patron conceptuel [Données désordonnées](/collections-model/fr/modele-cible/actuel/donnees-desordonnees)). Ces valeurs littérales décrivent une ressource et, en tant que telles, doivent être correctement captées par le modèle et distinguées d'autres types de chaînes de caractères, tels que les libellés, les annotations ou les commentaires.

#### Description {#contenu-litteral-description}

Ces contenus littéraux sont des valeurs provenant de nœuds de saisie liés à leur instance de classe correspondante par la propriété `P190_a_pour_contenu_symbolique`.

#### Exemples {#contenu-litteral-exemples}

La biographie de Yousuf Karsh peut comporter :

* Un libellé « Biographie de Yousuf Karsh »;
* Une note du soumissionnaire de données évaluant la biographie, indiquant qu'elle doit être révisée;
* Le contenu de la biographie.

<div id="0001_100_literal-content-bio" class="example"></div>

#### Discussion {#contenu-litteral-discussion}

Les propriétés `rdfs:comment` et `rdfs:label` ne sont pas adaptées pour capter des contenus littéraux.

Même si le CIDOC CRM recommandait précédemment l'utilisation de la propriété `P3_a_pour_note` pour les contenus patrimoniaux (Le Bœuf et al. 2015, sect. E33 Linguistic Object), ce n'est plus le cas, car la propriété `P3_a_pour_note` « est un contenant pour toutes les descriptions informelles sur un objet qui n'ont pas été exprimées en termes de constructions CRM. Elle saisit notamment la caractérisation de l'entité elle-même, ses structures internes, son apparence, etc. » (Le Bœuf et al. 2015, sect. P3 Has Note; notre traduction). Pour y remédier, le CIDOC CRM a développé la propriété `P190_a_pour_contenu_symbolique` pour associer une instance de `E90_Objet_symbolique` à une représentation de son contenu entier sous la forme d'une chaîne de texte (Bekiari et al. 2021, sect. P190 Has Symbolic Content).

La meilleure façon de représenter sémantiquement le contenu d'une ressource est d'utiliser la propriété `P190_a_pour_contenu_symbolique` pour rendre le contenu littéral plutôt que de s'appuyer sur une propriété personnalisée qui ne serait utilisée que localement. Comme c'est souvent le cas avec les données ouvertes et liées, il est préférable d'utiliser des classes et des propriétés reconnues et approuvées plutôt que d'en créer de nouvelles à usage unique.

## Propriétés-classes {#proprietes-classes}

### Contexte {#proprietes-classes-contexte}

Dans le CIDOC CRM, certaines propriétés peuvent être qualifiées par un énoncé afin de décrire plus précisément la nature du lien entre deux entités. Par exemple, une personne peut souhaiter préciser le rôle dans lequel une personne a effectué une activité en pointant un terme de vocabulaire définissant ce rôle. Pour ce faire, il serait possible d'utiliser la propriété `P14.1_dans_le_rôle_de`, mais cela poserait le problème suivant : si le rôle de l'actant réalisant une activité devait être qualifié par la propriété `P14.1_dans_le_rôle_de` appliquée directement à la propriété `P14_a_été_effectué_par`, l'URI de cette propriété serait toujours qualifié (quel que soit le contexte de son utilisation). Par exemple, si le rôle A est utilisé pour spécifier la propriété `P14_a_été_effectué_par` qui lie l'actant B à l'activité C, les autres occurrences de la propriété `P14_a_été_effectué_par` seront également liées au rôle A, même si cela est inexact. En d'autres termes, le CIDOC CRM a tendance à être mis en application en RDF, où les propriétés ne peuvent pas être qualifiées, laissant un écart entre l'expressivité idéale de l'ontologie et son expression dans une implémentation réelle. En 2014, afin de résoudre ce problème, le CRM SIG a élaboré des propriétés-classes (souvent appelées PC dans le contexte du CIDOC CRM) qui font partie d'une [extension](http://www.cidoc-crm.org/sites/default/files/CRMpc_v1.0.rdfs). Cette dernière permet la réification de propriétés spécifiques, de sorte que les instances des propriétés-classes peuvent devenir le sujet d'autres triplets sans compromettre la logique du reste de l'ontologie.

### Description {#proprietes-classes-description}

Pour revenir à l'exemple ci-dessus, la propriété-classe `PC14_a_été_effectué_par` peut être utilisée au lieu de la propriété `P14_a_été_effectué_par`. Une instance de la propriété-classe `PC14_a_été_effectué_par` peut être qualifiée par un rôle (`E55_Type`, Rôle de l'actant dans la relation) à travers la propriété `P14.1_a_été_effectué_par`. Puisque c'est l'instance de la propriété-classe qui est utilisée comme sujet du triplet, le rôle ne s'applique qu'à cette instance spécifique.

Afin de lier le domaine et la portée de la propriété `P14_a_été_effectué_par` précédemment utilisée, deux nouvelles propriétés (`P01_a_pour_domaine` et `P02_a_pour_portée`) ont été créées pour connecter la propriété-classe `PC14_a_été_effectué_par` à son domaine (`E7_Activité`) et à sa portée (`E39_Actant`) correspondants.

`E7_Activité → P14_a_été_effectué_par → E39_Actant`

a été remplacé par :

`E7_Activité ← P01_a_pour_domaine ← PC14_a_été_effectué_par → P02_a_pour_portée → E39_Actant`

### Exemples {#proprietes-classes-exemples}

Sans l'utilisation des propriétés-classes, le rôle des actants impliqués dans une relation serait directement lié à la propriété `P14_a_été_effectué_par`. Yousuf Karsh serait un participant d'un évènement de relation avec Solange Gauthier, tous deux dans le rôle d'« Époux·se », comme le montre le diagramme ci-dessous :

<a name="097a_PC_Exemple_1_p"></a>097a_PC_Exemple_1_p

<div class="mxgraph" style="max-width:100%;border:1px solid #cccccc;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;target&quot;:&quot;blank&quot;,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom layers lightbox&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;xml&quot;:&quot;&lt;mxfile host=\&quot;app.diagrams.net\&quot; modified=\&quot;2023-03-15T17:12:56.388Z\&quot; agent=\&quot;5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) draw.io/20.3.0 Chrome/104.0.5112.114 Electron/20.1.3 Safari/537.36\&quot; etag=\&quot;6H6Noz8w_tfKUjkCLPVr\&quot; version=\&quot;20.3.0\&quot;&gt;&lt;diagram id=\&quot;oBNQi6Dc_Pm5MJZH-vkU\&quot; name=\&quot;Page-1\&quot;&gt;7VrdcqM2FH4aLpNBEj/m0nZwtrPtTDrZmTa9YWQQhhYjRpYTu09fEUvGWNhmE4zptnuRRQeQpe87/8JA0+XmkeEi+YVGJDOgGW0M9GBAOIKe+FsKtjsB2A0XLI00wXP6N5FCU0rXaURWtQc5pRlPi7owpHlOQl6TYcboW/2xmGb1Xy3wgmiC5xBnuvS3NOKJ2pRbyb+QdJGoXwaO3O4Sq4flTlYJjujbgQj5BpoySvnuarmZkqxETuGye2924u5+YYzkvM0Lf2230Yv5zcM/2fOvf2wneEF/vZOzvOJsLTfsQxA8EbYq8ZQL51uFBqPrPCLlhMBAk7ck5eS5wGF5902QL2QJX2bydpxm2ZRmlL2/i+J4HoVYX7VaAmGcbA5EchePhC4JZ1vxiLxrSYSlPu1V5a3iByjQkwNuHCnDUiUW+5kr1MSFBO47QIQ6iG4wDnn6mnJjioyx1ymQIxgiEnYAJHLdGpLAuzWS6F+ojq5p1vUR3hpFT0ORRbGBxnxb6BiSSPg7OaSMJ3RBc5z5lXRSoWyKUfXMz5QWEts/Cedb6bzxmtM68mST8t/L1+9dWw5f5Gzl9cPmcLCVg5PMrOiaheTM9h0ZJjBbEH7Z95UAnOWZkQwLW64HhO5V325iTfzKOMPzMqLekjfYnreY5vzAzMz3f73wiaxBEepofCacl1nLuJwXziJaJCTC92keUzEM2TIgSJjuTOAFAqC8ykfdHWahJNY2de83m/mOPzlHS3sHeOfWHSBCugOEyOvRAaqMYDgeMBfb2pmSrYYvh/cqW3offd4Jui2NBg7KZoCeSj0BK8DBLo2S2VRA4ljk+ms5EvDcgtPrc+MMixs9OfsPczPqmhv56hNNxZL3vtU5Si7Rsc/cbUi+dcTwfhkfJ93VODegkwlgJqsC5+J6wd+RvxTYXBXXEHDUDEJ0OMk1w90D9L2Z1024Q9C6HO6g02e406v4oST835E4ftxmR20TxEH501FHpnWQM4LRDWyry1TSNWGLVBL0aVt6Gj8U26oV0+BKtgWslsYF7EFZF2psggyxnD7P3KnKoaoVmiuH7svw1pqAOs+NPmfBlqYJdaf6SkM8vycbvCwyolyrCVRD5kpe88F3p343XhPY9STRshu8ptlnBxLozSzftoNvTT7zU01cPLcduwMIoV1vhdvurZu4QE+9Rbl1D4II56sgIwErS6yJJa6iQfU0Lnmmk2xdDjGdN/iai67jEybktiu69InQkWEeT7Tb8tWqN6gXBsPSoY/rgtV54+pEAa5c2Wd14XiivZPuSReQHgaNKTTGggPzha5X61hcfMVslYj/yzuTbquGDpz0nXN00tZw8uv12WdGjcXBTZPMU3lfz2dwrUtytx8zHh2fUYB++2iooZGmrO+ZZjgX24fmo+AzSQkbrAWOVF/rzFl3vxbY0EVRuJaxbeQVdL0ZLJ7AqqtlU9rZK57W4E7O+m13qLTicv4xrGai1dgC/r/d0YcmDOuzA7XuH7fdYYN6ELp9u8Nq+G5t0O0OB6KLcaffdod1pjzZB/IVGWwkt03nIqIdRXIxrL4a3iWo1YfXyP8H&lt;/diagram&gt;&lt;/mxfile&gt;&quot;}"></div>

Cependant, une telle représentation impliquerait que toute autre occurrence de la propriété `P14_a_été_effectué_par` serait également liée au rôle « Époux·se ». Cela permettrait d'affirmer que, par exemple, Charles Lutwidge Dodgson, plus connu sous le nom de Lewis Carroll, a créé le livre *Les aventures d'Alice au pays des merveilles* avec le rôle « Époux », comme le montre le diagramme ci-dessous :

<a name="097b_PC_Exemple_2_p"></a>097b_PC_Exemple_2_p

<div class="mxgraph" style="max-width:100%;border:1px solid #cccccc;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;target&quot;:&quot;blank&quot;,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom layers lightbox&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;xml&quot;:&quot;&lt;mxfile host=\&quot;app.diagrams.net\&quot; modified=\&quot;2023-03-15T17:12:56.621Z\&quot; agent=\&quot;5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) draw.io/20.3.0 Chrome/104.0.5112.114 Electron/20.1.3 Safari/537.36\&quot; etag=\&quot;86njisBJAfHEep9IbZMH\&quot; version=\&quot;20.3.0\&quot;&gt;&lt;diagram id=\&quot;USYlgpdLoFhz4zm1ofy6\&quot; name=\&quot;Page-1\&quot;&gt;zVpdb6M4FP01aJ+2AhtIeMwHzEo7o6nUWc30CTnYCcw6OHVMPvbXrwETIE6atKUJVdVyL2DwOfdeX5/EgJPl7gtHq/gbw4QawMQ7A04NAICR/5p4X5pWaS54gjXHU/IfUU5TebMEk3XrQsEYFcmq7YxYmpJItHyIc7ZtXzZntP3UFVoQzfEUIap7fyZYxKV3CAa1/y+SLOLqyZbrlWeWqLpYzWQdI8y2DRf0DTjhjInyaLmbEJrjVuFS3hecOXt4MU5Scc0N083+++h5thug3y+zf//+9U8yjP9Uo2wQzdSEfWCFj4SvczzVi4t9hQZnWYpJPqBlwPE2TgR5WqEoP7uV1EtfLJZUnZ4nlE4YZby4F87nMxwh/a2rVyBckF3DpWbxhbAlEXwvL1FnHagQVQEFh8re1gRZFepxgxxX+ZCKicVh6Bo2eaCQewOKQEfRdcIJNybQGHlIJCztFMohiCCJOoByaA96BiXUoOR4bsCR2K/0cCRY5qoyGRcxW7AUUb/2jmuUTWnV13xlbKWw/U2E2KvCgzLB2siTXSJ+5bc/DBxlPqvR8uPprmnslXGWmTXLeERemb6jShziCyIu520OwKs8c0Jl+G3axaxz0uxTpMmHjCia5UvBPWkD19M2Z6loZJlZ/NyGTqdXfDoan7EQ+YI7yscFAWarmGD0kKRzJs2IL0MC5boXSLys0DLBx6od4pEi1jH14hcEvuuPX6Pl+vpnm+2lxDH1+gegd8P65/at/qVyVmUmOZX53DxXp1JhfbwEelfmDOhVygw03h4tO0Rh2QKI8l9I5nPZpGbKkujcg9LPp6Zf1WyoU+Pl1ESqP1N/75pczdRqZNqZ5Op+obo66cxeUetp1BrApXIC4/UKyZ7bXYgC8UuLl+tUi5dpO9UQ0tUc5TPXtCnwvcDrZk0bePblNQ24N1zTqr18fxa10019darrpt4C17aBsFfZZenqQE/7+teZO9fDmDcvs9dHgtuvSNAVjnZR3bAIzR7IDi1XlFSl1bSg85lVM5j6g4nfTdV0QXsncLCbVdO8pRJi6VKI7zjhj1M180O6HJo5rtPFwgPaYtLAvreYZOnChOzKH6wQo3QdUhIWHeDYlke4V7urS5XpLFuXC0vn2yZ16yNL5LvUwWB57S7EPiK5rJXqrqZsfTzQ0RbdPR6onLI2UBEwh/l8IIZ0McSYAGMkOTAnMeKUrOXR10zIKJeQAnPK8GKdC75mft24276xgzQ91jxOar7mLTUPSxc9ZNP9krGi7ZYZOvRWLNs1fD2D1LXakJ6qfN5NEdXliEPQjmgSkT/yoB3hjZxzxosITvKI/ckkjJyiFPc2fC0wcC/G723B1gWGvmxv3iB+v1fo675JrlqEy2JEvz4FsXQ1oj/bpTd8enVHRqu61RNGgS5cvE9fKl6k0JeG9RA31JeCIBj5bkcF2LLbBfj+AhPQhQofwvD7TGZHSJN0kSVrkbxkHW+cMI6g/Z6EeQvYV33ZoRuwpVl/HaXsn+vv80D/fw==&lt;/diagram&gt;&lt;/mxfile&gt;&quot;}"></div>

Avec l'utilisation des propriétés-classes, la propriété `P14_a_été_effectué_par` deviendrait une instance de `PC14_a_été_effectué_par`, ce qui signifie que le rôle d'« Époux » de Yousuf Karsh ne serait applicable qu'à cette instance particulière de `PC14_a_été_effectué_par` qui relie Yousuf Karsh à l'évènement de sa relation avec Solange Gauthier, comme le montre le diagramme ci-dessous :

<a name="097c_PC_Exemple_3_p"></a>097c_PC_Exemple_3_p

<div class="mxgraph" style="max-width:100%;border:1px solid #cccccc;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;target&quot;:&quot;blank&quot;,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom layers lightbox&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;xml&quot;:&quot;&lt;mxfile host=\&quot;app.diagrams.net\&quot; modified=\&quot;2023-03-15T17:12:56.868Z\&quot; agent=\&quot;5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) draw.io/20.3.0 Chrome/104.0.5112.114 Electron/20.1.3 Safari/537.36\&quot; etag=\&quot;OpZ4BrJTMhncxvQkfe1B\&quot; version=\&quot;20.3.0\&quot;&gt;&lt;diagram id=\&quot;iP3Ln60_yB398n3yy0CB\&quot; name=\&quot;Page-1\&quot;&gt;7Vtdc6s2EP01PCaDJD7Mo01w7kzbmcykndv0hZFBGO5gi8pybN9fXxGEMZbtkJgASW8eHLSAjHb37J5dYQ25i+09w1n8Bw1JqkE93GroToNwBB3xmQt2hQAUwzlLQkXwmPwkUqhL6ToJyap2Iac05UlWFwZ0uSQBr8kwY3RTvyyiaf1bMzwniuAxwKkq/Z6EPC4XZVfybySZx+U3A0sud4HLi+VKVjEO6eZAhDwNuYxSXhwtti5Jc82Veinum545u38wRpa80Q1z+o/17/N0bvz46U+//+VuvNmNnOUZp2u5YA8C/4GwVa5P+eB8V2qD0fUyJPmEQEOTTZxw8pjhID+7EcYXspgvUnk6StLUpSllL/eiKJqFAVafunwEwjjZHojkKu4JXRDOduISefYGGvIe6VF7Z9lUFgKl2uMD61hShqVTzPdzV3oTB1J1b1AjVNVo++OAJ88J11ykjZ1WVTmCASJBC6pEtl3TJHD61iT6hA4JdF2vOyTsW42GokYWRhoa812mKpGEIuTJIWU8pnO6xKlXSSeVmnUxqq75ndJMKvcH4Xwn4zdec1pXPdkm/O/89lvblMMnOVt+fLc9HOzk4KxpVnTNAnJh+ZbMFJjNCb9wnZwvV8BFQzOSYgHmek5o3WjmKaOJLxmneJbn1D7NBpubLaJLfgAz/eWvG3M6g7Knpdgz5jznLeN8XjgNaRaTEN8my4iKYcAWPkFiCVOhL+CDMqi8N9xhFkjDmroa/aZTz/Iml8zyhoyMrHoAREgNgBA5HQZAe2gBcClWVUDJLIdPh+cqLL2Mro+BJSl6FTVwUKApH/vAchq0UrGAySrDS3E85y+qfQ1JdgkkBKxyBiE6nOQj8XUHPWfqtIMvBI3X4QWtDuEF1MJhKATjDZnqCnDBhuBCwwKXWqi8D1wHaQqMekBXm9lLJFrYIHuBLuGllkFDgVeNv4OPgpfZlPFZw8LXybpriBT+suXOsZWKn5xmK+1T/8aeAAdGY9Rirh5Vn2mAZ7dkixdZSsrYqgNkfmjYvPNs17sybMooadgnoqTeZZMDqAWWZ5r+n6di5FWNIjwzLbOVTFNvt5m9t9uAWic9AOMW+CFervyU+CxvX04McRQOqm56LRK9P+KgpnVTCfH2Io689YEm4qH3XuM4dXbiHDlDsSJ5U+UPyjyjeo1uHM9TLFiZ58Wv9qu5wtVGA3e1K1zGaJqkOnIZ227JZ44n2gf9rpzGUZxGc6E2FsbSn+h6tY7EwW+YrWLxPz8zabfsaCHo3yDzaHfgxHaV02VvDKotlr5Z6jni2PG+QeOyvpzxo4EMgH3UWQXNkNwWAKHa6NkD8JGmeCnWD/V7YdE4IWywIASgbI9d2KLrFoQnWjGlYvNEOHIyut4OVqH7Pu0FKtutPv/nLRPYuFAeVssE/mqZtNwyae4J9rA84eu2TORZa1Tfx+m/hQI/WwvFdurvfvXfQoFqC0VN5Csy2Exu2carGu02k6s1X7+Z/P2huHEvCcG2Q/GZeuL4TTWz23oeqfHmQQc+9gVGWLmPOGPlFqIf0gVOTrz39zWsXnLogSRgdKIZrMPzxsmEVou3W/ttDe8HT3X61V9reFgUG6n9nnft+mdBvr9ZbPtD1Me2vzdx3em0rQoW1UJh/y/VlEngEH8uMAQAC5TtXyXXfRJFJODrQuALPbTK1oJgpEdRCzo26tlmAK+XD61LcEUwarrpgLradBjVAdU5t1B54xfkFk2tPjBuYag5aMjcogsDtU75r4uMah/uapJg2+iTkwTrePulf5Kgdsk+OUmwYT1vfCRLEMPqF5dF4ql+tIq8/wA=&lt;/diagram&gt;&lt;/mxfile&gt;&quot;}"></div>

### Limitations {#proprietes-classes-limitations}

La hiérarchie de l'extension des propriétés-classes impose que chaque nouvelle propriété-classe soit une sous-classe d'une classe mère appelée `PC0_Propriété_CRM_typée`. Cette hiérarchie minimaliste ne respecte toutefois pas les conventions hiérarchiques de l'extension CRMbase selon lesquelles certaines propriétés Pxx.1 hériteraient des caractéristiques de leurs super-propriétés. Par exemple, la propriété `P67.1_a_pour_type` (domaine `PC67_renvoie_à`) ne peut pas être utilisée avec la propriété-classe `PC138_représente` même si elle est une sous-propriété de `P67_renvoie_à` dans  le CRMbase. 

En outre, la propriété-classe `PC0_Propriété_CRM_typée` n'est pas une sous-classe de `E1_Entité_CRM` ou de toute autre entité du CRMbase, ce qui implique que les propriétés-classes ne sont techniquement pas liées sémantiquement au CIDOC CRM (bien que leur utilisation reste relativement répandue). 

### Documentation interne connexe {#proprietes-classes-documentation-interne-connexe}

Les propriétés-classes utilisées dans la Spécification du modèle cible sont les suivantes :

* `PC14_a_été_effectué_par` dans les patrons conceptuels [Relation](/collections-model/fr/modele-cible/actuel/relation) et [Production d’artefact](/collections-model/fr/modele-cible/actuel/production-dartefact);
* `PC138_représente` dans le patron conceptuel [Entité visuelle](/collections-model/fr/modele-cible/actuel/entite-visuelle);
* `PC144_a_fait_adhérer_à` dans le patron conceptuel [Appartenance à un groupe](/collections-model/fr/modele-cible/actuel/appartenance-a-un-groupe).

## Défis de la représentation des réalités des communautés mal desservies {#defis-de-la-representation-des-realites-des-communautes-mal-desservies}

Le projet DOPHEDA vise à documenter les actants des institutions culturelles situées au Canada. À ce titre, la Spécification du modèle cible doit rendre la plupart, sinon la totalité, des caractéristiques distinctives des communautés de tout le Canada, y compris celles qui sont généralement mal desservies par les modèles traditionnels, notamment les communautés autochtones et LGBTQIA+.

Un aperçu général des données actuellement détenues par les organisations patrimoniales révèle un besoin de documenter plusieurs aspects des traits identitaires des actants, tels que leur appartenance culturelle, leur genre et leur appartenance nationale ou communautaire. Ces traits identitaires sont de plus en plus pertinents pour la contextualisation du travail des actants ainsi que des pratiques de collecte et de documentation, surtout lorsqu'il s'agit d'évaluer la (mauvaise) représentation des communautés marginalisées dans les collections patrimoniales. 

Cependant, ces informations présentent également un risque élevé d'être problématiques, que ce soit au niveau de l'enregistrement (c.-à-d. dans les bases de données des soumissionnaires), de la structuration (c.-à-d. dans le modèle DOPHEDA) ou de la mise en correspondance (c.-à-d. lors de l'affectation des valeurs provenant des bases de données des soumissionnaires au modèle). Les traits d'identité d'un actant sont beaucoup plus fluides et flexibles qu'il n'y paraît à première vue et l'élaboration de patrons conceptuels qui seraient trop simplistes pour rendre compte de cette fluidité pourrait conduire à une représentation encore plus erronée de communautés déjà marginalisées.

### Patrons conceptuels concernés {#defis-de-la-representation-des-realites-des-communautes-mal-desservies-patrons-conceptuels-concernes}

Un examen des modèles et des vocabulaires actuels indique qu'ils adoptent généralement un point de vue qui ne représente pas de manière adéquate les réalités de la vie des personnes et des artefacts en matière d'identité. Les patrons conceptuels qui en résultent risquent donc d'être problématiques et le RCIP a décidé de retirer les patrons conceptuels et les nœuds suivants de la version 2.2 de la Spécification du modèle cible et de la Spécification des chemins sémantiques, afin d'évaluer pleinement les implications de leur développement, de leur mise en application et de leur déploiement : 

* **Genre** : Ce nœud documente le genre culturel (par opposition au genre biologique) auquel une personne s'identifie. En tant que concept socio-culturel, il s'agit d'un état ou d'une condition associé à une série de caractéristiques liées au comportement, aux manières, aux intérêts et à l'apparence d'une personne, ainsi qu'à la manière dont elles sont associées aux catégories de genre dans un contexte culturel particulier.
* **Nationalité** : Ce nœud indique le statut d'appartenance (par origine, naissance ou naturalisation) à une entité politiquement autonome dotée d'une indépendance nationale. Contrairement à l'affiliation culturelle, qui repose sur l'auto-association à une culture, la nationalité réfère au statut juridique de citoyen ou de sujet d'un État reconnu. Il est possible d'avoir plusieurs affiliations à la fois. 
* **Type d'affiliation culturelle** : Ce nœud indique une appartenance culturelle, plutôt que juridique, à un groupe qui se caractérise par des coutumes, des mœurs et des pratiques partagées autour d'éléments communs tels que le lieu, l'histoire, la langue, les croyances, les pratiques culinaires, etc. L'affiliation s'articule autour de valeurs et d'identités collectives et, à ce titre, il est possible d'avoir plusieurs affiliations à la fois. Cette appartenance n'est pas officielle dans le sens où l'assentiment du groupe concerné n'est pas formalisé ou explicite. Elle est distincte et plus large que la nationalité, qui est un concept strictement juridique indépendant de l'identification explicite ou implicite d'un actant à une culture. Par exemple, un artiste né en France et doté de la nationalité française pourrait vivre au Canada pendant la majeure partie de sa vie et revendiquer une affiliation culturelle canadienne, bien qu'il n'ait pas la citoyenneté canadienne.
* **Appartenance nationale** : Ce nœud indique le statut d'appartenance à une entité politique autonome dotée de structures officielles ou d'une hiérarchie institutionnalisée (formalisée ou non) ainsi que de coutumes, mœurs et pratiques partagées autour d'éléments communs tels que le lieu, l'histoire, la langue, les croyances, les pratiques culinaires, etc. Contrairement à l'affiliation culturelle, qui repose sur l'(auto-)identification, ou la nationalité, qui fait référence au statut juridique de citoyen ou de sujet d'un État reconnu, l'appartenance à une nation décrit l'appartenance officielle avec l'assentiment implicite ou explicite du groupe (représenté par ses membres officiels ou influents). Elle réfère à la nation à laquelle l'actant s'identifie/est identifié, indépendamment de sa nationalité ou de sa culture. Ce nœud permet de prendre en compte différents types d'appartenance à une nation, notamment ethnique, civique, tribale et multiculturelle. Elle s'articule souvent autour de pratiques et de traditions communes transmises d'une génération à l'autre, bien que ce ne soit pas exclusivement le cas. Le RCIP ne recommande pas l'utilisation de ce nœud pour enregistrer l'association à un ordre religieux, qui devrait être enregistrée à l'aide du nœud Communauté, car il s'agit de la conviction et de la foi individuelles dans la véracité de croyances précises, plus que de l'appartenance au groupe lui-même. Les structures officielles des entités politiques peuvent prendre la forme de différentes unités politiques telles que des organismes gouvernementaux civils ou locaux, des assemblées tribales, des conseils de bande, etc. Bien que les entités politiques aient souvent le contrôle d'une zone géographique ou de ressources, ce n'est pas toujours le cas.
* **Communauté** : Ce nœud indique le statut d'appartenance à un groupe ou à une unité sociale ayant des normes, des valeurs, des coutumes, des pratiques et des identités communes, ainsi que des croyances, des préférences, des besoins et des risques partagés. Cette appartenance n'a pas à être formalisée par un organisme gouvernemental; elle tourne autour de la participation et du sentiment d'appartenance, même si une appartenance officielle peut se produire, comme dans le cas des communautés religieuses. Quatre éléments majeurs peuvent être utilisés pour évaluer l'appartenance à une communauté : l'adhésion (l'actant partage un sentiment d'appartenance personnelle), l'influence (l'actant compte pour le groupe et le groupe compte pour l'actant), le renforcement (le groupe contribue à l'intégration de l'actant et à la satisfaction de ses besoins) et la connexion émotionnelle.
* **Type de groupe** : Ce nœud caractérise conceptuellement les organisations afin de les catégoriser en ensembles sur la base de leur mission ou de leur fonction formellement ou informellement déclarée. Il réfère à deux grandes catégories de groupes, chacune ayant des formes plus précises : les groupes sociaux (troupe, gang, équipe, etc.) et les groupes organisationnels (musée, université, entreprise, gouvernement, etc.).

## Bibliographie

Bekiari, Chryssoula, George Bruseker, Martin Doerr, Christian-Emil Ore, Stephen Stead, et Athanasios Velios, éds. *Definition of the CIDOC Conceptual Reference Model*. Documentations du CIDOC CRM, 7.1. Paris, FR-IDF : CIDOC CRM Special Interest Group, 2021. [http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf](http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf).

–––. « P190 Has Symbolic Content ». *Definition of the CIDOC Conceptual Reference Model*. Documentations du CIDOC CRM, 7.1. Paris, FR-IDF : CIDOC CRM Special Interest Group, 2021. [http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf](http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf).

–––. « About Types ». *Definition of the CIDOC Conceptual Reference Model*. Documentations du CIDOC CRM, 7.1.1. Paris, FR-IDF : Conseil international des musées (ICOM), 2021. [http://www.cidoc-crm.org/sites/default/files/cidoc_crm_v.7.1.1.pdf)](http://www.cidoc-crm.org/sites/default/files/cidoc_crm_v.7.1.1.pdf).

Brickley, Dan, et R. V. Guha. « rdfs:comment ». *RDF Schema 1.1.*. Recommandation du W3C, 25 février 2014. [https://www.w3.org/TR/rdf-schema/#ch_comment](https://www.w3.org/TR/rdf-schema/#ch_comment).

–––. « rdfs:label ». *RDF Schema 1.1.*. Recommandation du W3C, 25 février 2014. [https://www.w3.org/TR/rdf-schema/#ch_label](https://www.w3.org/TR/rdf-schema/#ch_label).

Bruseker, George. « Principles for Modelling Ontologies: A Short Reference Guide ». *Projet Parthenos* 17 (2017) : 72.

Doerr, Martin, et Christian Emil Ore, éds. *Definition of the CIDOC Conceptual Reference Model*. Documentations du CIDOC CRM, 7.0.1. Paris, FR-IDF : Conseil international des musées (ICOM), 2020. [http://www.cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.0.1_%2018-10-2020.pdf](http://www.cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.0.1_%2018-10-2020.pdf).

FORTH-ICS. *CRMpc 1.0*. 2014. [http://www.cidoc-crm.org/sites/default/files/CRMpc_v1.0.rdfs](http://www.cidoc-crm.org/sites/default/files/CRMpc_v1.0.rdfs).

Gruber, Thomas R. « Toward Principles for the Design of Ontologies Used for Knowledge Sharing? ». *International Journal of Human-Computer Studies* 43, no 5 (1995) : 907-28. [https://doi.org/10.1006/ijhc.1995.1081](https://doi.org/10.1006/ijhc.1995.1081).

Le Bœuf, Patrick, Martin Doerr, Christian Emil Ore, et Stephen Stead, éds. « E33 Linguistic Object ». *Definition of the CIDOC Conceptual Reference Model*. Documentations du CIDOC CRM, 6.2.1. Paris, FR-IDF : Conseil international des musées (ICOM), 2015. [http://www.cidoc-crm.org/sites/default/files/cidoc\_crm\_version\_6.2.1.pdf](http://www.cidoc-crm.org/sites/default/files/cidoc_crm_version_6.2.1.pdf).

–––. « E39 Actor ». *Definition of the CIDOC Conceptual Reference Model*. Documentations du CIDOC CRM, 6.2.1. Paris, FR-IDF : Conseil international des musées (ICOM), 2015. [http://www.cidoc-crm.org/sites/default/files/cidoc\_crm\_version\_6.2.1.pdf](http://www.cidoc-crm.org/sites/default/files/cidoc_crm_version_6.2.1.pdf).

–––. « E74 Group ». *Definition of the CIDOC Conceptual Reference Model*. Documentations du CIDOC CRM, 6.2.1. Paris, FR-IDF : Conseil international des musées (ICOM), 2015. [http://www.cidoc-crm.org/sites/default/files/cidoc\_crm\_version\_6.2.1.pdf](http://www.cidoc-crm.org/sites/default/files/cidoc_crm_version_6.2.1.pdf).

–––. « P3 Has Note ». *Definition of the CIDOC Conceptual Reference Model*. Documentations du CIDOC CRM, 6.2.1. Paris, FR-IDF : Conseil international des musées (ICOM), 2015. [http://www.cidoc-crm.org/sites/default/files/cidoc\_crm\_version\_6.2.1.pdf](http://www.cidoc-crm.org/sites/default/files/cidoc_crm_version_6.2.1.pdf).

Linked.art. « Actors: People and Organizations ». *Linked.art*. 11 décembre 2019. [https://linked.art/model/actor/#types](https://linked.art/model/actor/#types).

The Getty Research Institute. « Photographes ». *The Getty Vocabularies*. The Getty Research Institute, 10 avril 2018. [http://vocab.getty.edu/aat/300025687](http://vocab.getty.edu/aat/300025687).

