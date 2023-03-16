---
layout: page
language: fr
title: Données désordonnées
permalink: /fr/modele-cible/actuel/donnees-desordonnees
other_link: /en/target-model/current/messy-data
sidebar: mc22
date: 2022-06-30
description: La Spécification du modèle cible des actants modélise sémantiquement les actants dans un contexte patrimonial. Les patrons conceptuels les plus pertinents pour la vie des actants sont présentés avec des diagrammes et des exemples qui les illustrent, ainsi qu'un compte rendu et une explication des décisions pertinentes qui ont été prises lors de l'élaboration desdits patrons conceptuels. Il s'agit d'une documentation théorique qui n'a jamais été testée ou mise en application.
---

## Aperçu {#apercu}

Ce patron conceptuel a été développé pour faciliter la mise en correspondance des données qui ne suivent pas les recommandations du modèle DOPHEDA. Il s'agit d'une solution technique pour accueillir, dans un graphe de connaissances, des données non structurées. Ce patron conceptuel couvre :

* Les données elles-mêmes, sous forme littérale;
* La langue dans laquelle les données sont enregistrées.

Il ne couvre pas :

* La provenance des données, qui est documentée à l'aide du patron conceptuel [Provenance du jeu de données](/collections-model/fr/modele-cible/actuel/provenance-du-jeu-de-donnees);
* La valorisation sémantique des données;
* Les notes ou commentaires contenant des informations textuelles sur une entité, qui sont documentées à l'aide du patron conceptuel [Note curatoriale](/collections-model/fr/modele-cible/actuel/note-curatoriale);
* Les champs de données qui ne correspondent à aucun patron conceptuel de la Spécification du modèle cible.

## Introduction et contexte

### Historique théorique {#historique-theorique}

Les données désordonnées sont un problème important pour les institutions patrimoniales. Un rapport du Heritage Data Research Workshop montre que l'une des principales préoccupations des spécialistes en données patrimoniales est de s'attaquer aux données complexes et désordonnées, soit en raison d'une multitude de formats ou d'un manque de normalisation (Harrison et al. 2017, 32). Bien qu'il soit difficile de quantifier la proportion de données désordonnées dans les collections numériques patrimoniales, une étude sur la base de données du Musée national d'histoire naturelle des Pays-Bas montre qu'elle contient environ 5 % d'erreurs d'orthographe et de mauvaises utilisations des colonnes, et environ 34 % d'erreurs de contenu (van den Bosch et al. 2009, 55-56). Cependant, le nettoyage continu de jeux de données entiers n'est pas pratique pour la plupart des institutions, car il s'agit d'un processus long et exigeant en ressources (CrowdFlower 2016, 6). Il est donc raisonnable de penser que d'autres institutions sont confrontées à des défis similaires et que les données désordonnées doivent être prises en compte et adaptées. 

### Énoncé des besoins {#enonce-des-besoins}

Même si la soumission de données doit suivre des règles strictes en matière de structure et de normalisation pour garantir la transformation transparente des jeux de données des soumissionnaires au format RDF, l'exercice de nettoyage des données, exigeant en ressources, que cela implique est souvent une attente irréaliste. Il en résulte des données non structurées, souvent appelées « données désordonnées », qui doivent être adaptées, même au détriment de la sémantique. Cela permet aux personnes d'accéder à l'ensemble des informations fournies par une institution, ainsi qu'aux futurs outils permettant d'analyser et de nettoyer les données désordonnées. Même si cela faciliterait le processus de mise en correspondance, le fait d'écarter les données désordonnées du graphe de connaissances DOPHEDA entraînerait une perte importante d'informations pertinentes, ce qui n'est pas souhaitable; c'est pourquoi ce patron conceptuel a été élaboré. 

## Description du patron conceptuel

Une solution courante pour traiter les données désordonnées dans les graphes de connaissances est de considérer ces données comme des chaînes de caractères, ce qui revient à créer une instance de `E33_Objet_linguistique`. La valeur du [Type d’énoncé de données désordonnées](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#type-denonce-de-donnees-desordonnees) (une instance de `E55_Type`) est liée à cette instance de `E33_Objet_linguistique` par la propriété `P2_a_pour_type` afin d'indiquer le type général d'information détenu par l'instance de `E33_Objet_linguistique` en fonction du nœud de saisie qui aurait accueilli les données si sa valeur sémantique avait été plus élevée, ainsi que pour la distinguer d'autres instances de `E33_Objet_linguistique`, telles que les biographies. L'instance de `E55_Type` est ensuite qualifiée par une autre instance de `E55_Type` (un nœud doté d’un qualifiant spécifié) portant le libellé « Énoncé de données désordonnées » à travers la propriété `P2_a_pour_type`.

La valeur de la [Langue de l’énoncé de données désordonnées](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#langue-de-lenonce-de-donnees-desordonnees) (une instance de `E56_Langue`) est liée à l'instance de `E33_Objet_linguistique` par la propriété `P72_a_pour_langue`, et la valeur littérale du [Contenu de l'énoncé de données désordonnées](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#contenu-de-lenonce-de-donnees-desordonnees) est liée à cette même instance de `E33_Objet_linguistique` par la propriété `P190_a_pour_contenu_symbolique`. L'instance de `E33_Objet_linguistique` représentant les données littérales est finalement liée par la propriété `P67_renvoie_à` à l'instance concernée de `E39_Actant`.

## Diagramme

<a name="011_PatronConceptuel_DonneesDesordonnees_p"></a>011_PatronConceptuel_DonneesDesordonnees_p

<div class="mxgraph" style="max-width:100%;border:1px solid #cccccc;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;target&quot;:&quot;blank&quot;,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom layers lightbox&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;xml&quot;:&quot;&lt;mxfile modified=\&quot;2023-03-15T17:12:50.517Z\&quot; host=\&quot;app.diagrams.net\&quot; agent=\&quot;5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) draw.io/20.3.0 Chrome/104.0.5112.114 Electron/20.1.3 Safari/537.36\&quot; etag=\&quot;3MzZLQ6NPppY82oQ4EmB\&quot; version=\&quot;20.3.0\&quot;&gt;&lt;diagram id=\&quot;c6s0q2QLkiWBAHBR0o4x\&quot; name=\&quot;Page-1\&quot;&gt;3ZhZk5s4EIB/DbVPdmEwPh5tx04yO6mdiieVzL5QMghQIhAjhI/99dsCcRkyO+MwR7bKD+pW6+r+3Gqkmavw+J6jOPjEXEw1Q3ePmvlOMwxDkz/dPeXiKBd9TtyWYkv+wUqpK21KXJw0DAVjVJC4qXRYFGFHNHSIc3ZomnmMNleNkY9biq2DaFv7lbgiUFpD16uOD5j4gVp6NlYdISqMlSIJkMsONZW51swVZ0zkrfC4wlT6rfBLPm7zk95yYxxH4jED/Kv70dfPt9SwB/tx/DmOPt1tBmY+yx7RVB34ZjK1Yco9I9jWVqa2KLYvToVPsAsuUiLjImA+ixBdV9olZ2nkYrmwDlJlc81YDMoRKL9jIU4q3igVDFSBCKnqhTPx07e6cCcnG1qF+O6oJs+lk5LaTlF+SljKHfyAJxSlAnEfq6Hpzbdb78+tS8xjfH9YfhxZP/yBmk/6oLaAcvl7zEIM+wEDjikSZN/ECCka/dKuHHrDCGzZ0Is/zUz5Xf1rzKnenCLfqBpVhR0atW1UqgyGJ4BhtcEYzXUb2TE40oZ/m8BRqhkTCr5a7ji0fNmyk1O4Y5Tcw6jXxEZ/RWw67caPxEaFXx+qiS/FqDBhnpfgZyFk1iZkahSAUBT5vxcC+EhENmw4tZR4V0wJ7WqUFF6Om0nf6aaBwVNjPm/HvAy5OMX/h4Drrxzw6ZsKuNEK+No07b92EBKbEviPk0R0JvsqrDJGh4AIvI1R5qEDFInNEHqE0hWjjGdjTc91HXP8U1fvMRf4+JgsOh6fXaKFfKiVcqbSBbUqbqI/2Z9fEsylXxyZfSnaYZoPLe/I4opcFXen7mJp+kdWZc0jFjl5q+hxoaTNNVAAg5i3E8abHedXcKGB/ZVrHhOIxCIRHEKWnwyC9yPfYCCErKUX8mDGxglINOAOiYc+EUG6GxImtYxSOBlhUTII8/J+48GKmyTGDvGIg2TfACr1gRPgkIBZgkMUZWzAHjfIEWk2KmI4dROwHCSIJATOaapiQuoolm7AsikPibG0VCfGciLjv4Ad14BQgF9KZQ8ATo0zAM0OAI0OAM+rvUcACGKNwacxea2u616RrAPYxnRtTexsWfkB9taQzMuXfoic9Efkc+XJc0zHXXmyC9ML8mQHpq2r6O779toU1serv0dfRsnu/nD1Iey4in7f2uPyMmLaLiM6vdX7Z+qvXnu3WYggZawNDb5t5/MXyTGWfVui8Ybyi+QVFL+aWqbPl1rQzppYz5BajLeYWopT1arckpxWebUytAWwpksUZ5fzq8uJlst+C+e+ojafvVzUWiF66Nmt8SEytxeOQOr9qzcfejvXQT34sHzCfujjoz/yq4fk/IGneok31/8C&lt;/diagram&gt;&lt;/mxfile&gt;&quot;}"></div>

## Exemples

L'information détaillant le début de l'occupation de Yousuf Karsh en tant que photographe de studio établi pourrait prendre la forme suivante : « De retour au Canada en 1931, Karsh établit rapidement un studio avec l'aide financière de son oncle (Éditeurs de la Encyclopædia Britannica n.d.) » (`P190_a_pour_contenu_symbolique`, Contenu de l’énoncé de données désordonnées). Si les données avaient été normalisées, elles auraient pu être soumises à l'aide du nœud de saisie Date de début de l'occupation, mais comme elles ne sont pas normalisées, le nœud de saisie Contenu de l'énoncé de données désordonnées doit être utilisé à la place, avec un libellé indiquant qu'il s'agit d'un « Énoncé de la date de début de l'occupation » (`P2_a_pour_type`, Type d’énoncé de données désordonnées) rédigé en anglais (`P72_a_pour_langue`, Langue de l’énoncé de données désordonnées).

<div id="0001_100_messy-data" class="example"></div>

## Documentation connexe

### Modèles externes {#modeles-externes}

* Linked.art : [Statements about a Resource](https://linked.art/model/base/#statements-about-a-resource)

### Nœuds de saisie

* [Contenu de l'énoncé de données désordonnées](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#contenu-de-lenonce-de-donnees-desordonnees) \| Liste de vérification
* [Langue de l'énoncé de données désordonnées](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#langue-de-lenonce-de-donnees-desordonnees) \| Liste de vérification
* [Type d'énoncé de données désordonnées](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#type-denonce-de-donnees-desordonnees) \| Liste de vérification

### Entités du CIDOC CRM {#entites-du-cidoc-crm}

* `E33_Objet_linguistique` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E33)]
* `E39_Actant` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E39)]
* `E55_Type` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E55)]
* `E56_Langue` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E56)]
* `P2_a_pour_type (est_le_type_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P2)]
* `P67_renvoie_à (fait_l’objet_d’un_renvoi_par)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P67)]
* `P72_a_pour_langue (est_la_langue_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P72)]
* `P190_a_pour_contenu_symbolique` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P190)]

## Discussion

### Justification

Ce patron conceptuel n'est pas conçu pour documenter un type d'information précis, contrairement à la plupart des patrons de la Spécification du modèle cible. Il s'agit plutôt d'une solution technique au problème des données non structurées et non standard. La plupart des projets en DOL mettent l'accent sur le développement d'un modèle de données plutôt que sur sa mise en application; c'est pourquoi ce patron conceptuel se trouve rarement dans d'autres projets. Pourtant, il est essentiel pour un environnement comme DOPHEDA qui vise à agréger et à mettre en correspondance les données de nombreux soumissionnaires. De façon réaliste, tous les soumissionnaires n'auront pas les ressources nécessaires pour nettoyer leurs données avant de contribuer à l'environnement DOPHEDA et le RCIP doit tenir compte des besoins de ses diverses parties prenantes. 

Ce patron conceptuel est structurellement similaire au patron conceptuel [Note curatoriale](/collections-model/fr/modele-cible/actuel/note-curatoriale). Tous deux ont comme nœud central une instance de `E33_Objet_linguistique` qui est liée au nœud qu'elle documente par la propriété `P67_renvoie_à`. Les données désordonnées et les notes curatoriales peuvent néanmoins être différenciées les unes des autres par l'utilisation d'un type désigné approprié. Les deux nœuds `E55_Type`, appelés [nœuds dotés d’un qualifiant spécifié](/collections-model/fr/specification-des-chemins-semantiques/actuel/introduction#noeud-dotes-dun-qualifiant-specifie-ndqs), reposent sur l'utilisation de vocabulaires spécifiques qui n'ont pas encore été déterminés. 

### Limitations

Comme indiqué ci-dessus, en raison de leur nature, les données désordonnées hébergées dans le graphe de connaissances DOPHEDA restent sémantiquement pauvres. Même si des données désordonnées sont disponibles dans l'environnement DOPHEDA, il est difficile d'en extraire de l'information par le biais de requêtes. Seuls les humains qui lisent le contenu des nœuds textuels peuvent déterminer la signification de telles données. Ce processus peut être long en raison de leur quantité. Tant que les outils ne pourront pas nettoyer les données désordonnées, elles demeureront difficiles à accéder et à exploiter.

Pour pouvoir utiliser la mise en correspondance de l'information, le patron conceptuel Données désordonnées doit être lié à l'entité principale décrite (l'instance de `E39_Actant` ou de `E22_Objet_élaboré_par_l’humain`). Cependant, il se peut que l'énoncé de données désordonnées ne réfère pas directement à l'actant, mais à un autre nœud de saisie, tel que la Date de début de l'entrée dans la famille. Cela pourrait créer de la confusion pour les personnes utilisant ce patron conceptuel, soit parce qu'elles ne savent pas à quel nœud l'énoncé de données désordonnées fait référence, soit parce qu'elles pensent que seules les informations relatives à l'actant principal peuvent être modélisées avec le patron conceptuel Données désordonnées.

### Enjeux connexes sur GitHub

* [Enjeu no 20 « Que faire du champ "Remarques" dans certains musées? »](https://github.com/chin-rcip/collections-model/issues/20) (en anglais)
* [Enjeu no 32 « Devrions-nous utiliser `P3 a pour note` ou `rdfs:comment`? »](https://github.com/chin-rcip/collections-model/issues/32) (en anglais)
* [Enjeu no 63 « Sujet de la note curatoriale »](https://github.com/chin-rcip/collections-model/issues/63) (en anglais)

### Cas limites

#### Exemple 1 {#cas-limites-exemple-1}

Yousuf Karsh a utilisé la technique de la « Photographie » tout au long de sa carrière. Une institution qui documente cette technique à l'aide d'un vocabulaire contrôlé sera en mesure de rendre compte de cette information avec le patron conceptuel Technique utilisée. Cependant, malgré le fait que l'information transmise soit structurée, le soumissionnaire pourrait être réticent à catégoriser une personne en fonction des techniques qu'elle a utilisées. Dans un tel cas, le patron conceptuel Données désordonnées peut être utilisé pour tenir compte du point de vue du soumissionnaire. 

#### Exemple 2 {#cas-limites-exemple-2}

Un seul contenu de l’énoncé de données désordonnées pourrait inclure plus d'une seule langue. Dans un tel cas, un soumissionnaire pourrait choisir de répertorier les langues dans une seule entrée, ou de créer une entrée par langue et de toutes les associer au contenu.

## Bibliographie

CrowdFlower. *Data Science Report*. CrowdFlower, 2016. [https://visit.figure-eight.com/rs/416-ZBE-142/images/CrowdFlower_DataScienceReport_2016.pdf](https://visit.figure-eight.com/rs/416-ZBE-142/images/CrowdFlower_DataScienceReport_2016.pdf).

Éditeurs de la Encyclopaedia Britannica. « Yousuf Karsh ». *Encyclopædia Britannica*. Londres, UK-LDN : Encyclopædia Britannica, n.d. [https://www.britannica.com/biography/Yousuf-Karsh](https://www.britannica.com/biography/Yousuf-Karsh).

Harrison, Rodney, Hana Morel, Maja Mericevic, et Sefryn Penrose. *Heritage and Data: Challenges and Opportunities for the Heritage Sector*. Heritage Data Research Workshop. Londres, UK-LDN : Arts and Humanities Research Council, 2017. [https://heritage-research.org/app/uploads/2017/11/Heritage-Data-Challenges-Opportunities-Report.pdf](https://heritage-research.org/app/uploads/2017/11/Heritage-Data-Challenges-Opportunities-Report.pdf).

Van den Bosch, Antal, Marieke van Erp, et Caroline Sporleder. « Making a Clean Sweep of Cultural Heritage ». *Intelligent Systems, IEEE* 24, no 2 (2009) : 54-63.

