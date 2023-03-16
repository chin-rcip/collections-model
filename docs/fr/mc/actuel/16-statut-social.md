---
layout: page
language: fr
title: Statut social
permalink: /fr/modele-cible/actuel/statut-social
other_link: /en/target-model/current/social-status
sidebar: mc22
date: 2022-06-30
description: La Spécification du modèle cible des actants modélise sémantiquement les actants dans un contexte patrimonial. Les patrons conceptuels les plus pertinents pour la vie des actants sont présentés avec des diagrammes et des exemples qui les illustrent, ainsi qu'un compte rendu et une explication des décisions pertinentes qui ont été prises lors de l'élaboration desdits patrons conceptuels. Il s'agit d'une documentation théorique qui n'a jamais été testée ou mise en application.
---

## Aperçu {#apercu}

Ce patron conceptuel peut être utilisé pour représenter les informations relatives à un ou plusieurs statuts sociaux d'une personne ou d'un groupe de personnes. Il comprend : 

* Le type de statut social (p. ex. aîné, membre élu d'un ordre, etc.), qui inclut le rang relatif et l'honneur ou le prestige possible qu'un actant détient par rapport à la façon dont il est perçu comme correspondant aux objectifs et aux idéaux de la société, ainsi que sa position hiérarchique dans la stratification sociale du groupe;
* Le moment durant lequel un actant a assumé le statut;
* Le lieu où un actant a assumé le statut;
* L'appellation d'un actant qui a attribué le statut à son titulaire.

Ce patron conceptuel ne doit pas être utilisé pour représenter :

* Les activités, entreprises, professions et autres rôles liés au travail d'un actant (le patron conceptuel [Occupation](/collections-model/fr/modele-cible/actuel/occupation) doit plutôt être utilisé);
* Les activités d'un actant en tant qu'individu faisant partie d'un groupe (le patron conceptuel [Appartenance à un groupe](/collections-model/fr/modele-cible/actuel/appartenance-a-un-groupe) doit plutôt être utilisé). 

## Introduction et contexte

### Historique théorique {#historique-theorique}

Le statut social est un rang social relatif qu'un individu occupe au sein d'une stratification sociale basée sur l'honneur ou le prestige. Le statut reflète un ensemble de comportements, d'activités, de fonctions, de droits, d'obligations, de devoirs, de croyances, de modes de vie et de normes connectés. Le statut peut être attribué ou obtenu. Le statut attribué est assigné aux personnes à la naissance et est généralement involontaire (p. ex. être le fils aîné d'une famille, naître prince). En revanche, le statut obtenu est acquis par les personnes grâce à leurs efforts et leurs actions, nécessitant généralement des qualités particulières et se basant sur l'éducation, l'occupation, les relations, les réalisations, etc. (Éditeurs de la Encyclopædia Britannica 2019). Par exemple, le photographe Yousuf Karsh a acquis le statut de Compagnon de l'Ordre du Canada pour ses contributions à la nation. 

Ainsi, l'occupation d’une personne, qu'il s'agisse d'une activité rémunérée ou non, d'une entreprise, d'une profession ou de tout autre rôle lié au travail, peut être une variable permettant de juger de son statut social. De même, l'acte de joindre un groupe dans un certain rôle peut également établir le statut d'une personne. Par exemple, Helen Keller, photographiée par Yousuf Karsh, a fondé et a été membre de plusieurs groupes militants (p. ex. Helen Keller International) tout au long de sa carrière, ce qui lui a permis d'obtenir le statut social de « militante politique » aux yeux de certains de ses contemporains.

### Énoncé des besoins {#enonce-des-besoins}

Si les actants ont des occupations professionnelles ou artistiques, ils détiennent également un ou plusieurs statuts sociaux, comme celui de leader, d'aîné ou de chevalier. Le statut peut être acquis à la naissance ou attribué à la suite de certaines activités et/ou évènements, tels que la contribution à la société, les accomplissements de vie, les œuvres importantes, etc. En tant que telle, l'information sur le statut social peut être considérée comme une qualité distinctive d'un actant. 

En outre, le statut est acquis par le biais d'une reconnaissance et d'une attribution officielles par un ou plusieurs autres actants qui représentent la communauté qui le confère. Par conséquent, il est important d'identifier le cédant du statut social afin de documenter le contexte social du statut.

De même, les informations géographiques et temporelles relatives à l'attribution d'un statut social doivent être saisies, car elles permettent d'enrichir les données et offrent davantage d'informations sur le contexte du statut. En termes de temps, un statut social peut avoir une date de fin, car certains statuts cessent d'être reconnus à la mort de la personne détenant le statut ou sont transférés à son successeur. Dans d'autres cas, il peut être révoqué par un autre actant, qui est généralement le même actant qui a attribué le statut, ou le détenteur du statut le délaisse volontairement. 

Les statuts sociaux étant un aspect important de la vie humaine, ces informations peuvent faire l'objet de nombreuses études, telles que la documentation de la reconnaissance officielle des artistes issus·es des minorités, l'évolution de certains statuts à travers le temps ou l'espace, etc.

## Description du patron conceptuel

Pour chaque statut social, une instance de `E39_Actant` est d'abord liée par la propriété `P11_a_eu_pour_actant_participant` à une instance de `E5_Évènement` qui est qualifiée par la valeur du [Type de statut social](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#type-de-statut-social) (une instance de `E55_Type`) en utilisant la propriété `P2_a_pour_type`. Cette instance de `E55_Type` est davantage qualifiée par une instance de `E55_Type` (un nœud doté d’un qualifiant spécifié) portant le libellé « Statut social » par le biais de la propriété `P2_a_pour_type`.

La durée de l'évènement est indiquée à l'aide du patron conceptuel [Limites temporelles](collections-model/fr/modele-cible/actuel/limites-temporelles) lié à l'instance de `E5_Évènement` par la propriété `P4_a_pour_intervalle_temporel` avec des valeurs extraites des nœuds de saisie [Date de début du statut social](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-du-statut-social), [Qualifiant de la date de début du statut social](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-du-statut-social), [Date de fin du statut social](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-du-statut-social) et [Qualifiant de la date de fin du statut social](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-du-statut-social). 

En outre, l'évènement est lié à la valeur du [Lieu du statut social](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#lieu-du-statut-social) (une instance de `E53_Lieu`) par la propriété `P7_a_eu_lieu_dans`.

L'instance de `E5_Évènement` qui représente le statut social est déclenchée par (propriété CRMsci `O13i_est_déclenché_par`) un évènement d'attribution de statut social (une instance de `E13_Assignation_d'attribut`). Grâce à la propriété `P14_a_été_effectué_par`, cette activité d'attribution est liée à une instance de `E39_Actant` qui représente l'actant ayant attribué le statut social. Cette instance de `E39_Actant` est ensuite liée à une instance de `E41_Appellation` et de `E33_Objet_linguistique` par la propriété `P1_est_identifié_par`. De cette instance, la valeur littérale de l'[Appellation de l'actant attribuant le statut social](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-de-lactant-attribuant-le-statut-social) est rendue par la propriété `P190_a_pour_contenu_symbolique`.

L'instance de `E13_Assignation_d'attribut` est également liée à la même instance de `E5_Évènement` par la propriété `P141_a_attribué` ainsi que liée à la première instance de `E39_Actant` (qui a reçu le statut) par la propriété `P140_a_assigné_l'attribut_à`.

## Diagramme

<a name="035_PatronConceptuel_StatutSocial_p"></a>035_PatronConceptuel_StatutSocial_p

<div class="mxgraph" style="max-width:100%;border:1px solid #cccccc;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;target&quot;:&quot;blank&quot;,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom layers lightbox&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;xml&quot;:&quot;&lt;mxfile modified=\&quot;2023-03-15T17:12:52.626Z\&quot; host=\&quot;app.diagrams.net\&quot; agent=\&quot;5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) draw.io/20.3.0 Chrome/104.0.5112.114 Electron/20.1.3 Safari/537.36\&quot; etag=\&quot;a2770JM8O5hDWAq-KnOW\&quot; version=\&quot;20.3.0\&quot;&gt;&lt;diagram id=\&quot;Vnz9Qq2Wo0vU6o8shjVE\&quot; name=\&quot;Page-1\&quot;&gt;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&lt;/diagram&gt;&lt;/mxfile&gt;&quot;}"></div>

## Exemples

### Exemple 1

En 1990 (`P82a_le_début_du_début`, Date de début du statut social), Yousuf Karsh a été nommé Compagnon de l'Ordre du Canada (`P2_a_pour_type`, Type du statut social) par la reine Elizabeth II (`P190_a_pour_contenu_symbolique`, Appellation de l'actant attribuant le statut social) à Ottawa, CA-ON (`P7_a_eu_lieu_dans`, Lieu du statut social). Ce statut social a été maintenu même après la mort de Yousuf Karsh en 2002 (Hillmer 2018; Skidmore 2015). 

<div id="0001_100_social-status" class="example"></div>

### Exemple 2

Aung San Suu Kyi a reçu la citoyenneté canadienne honoraire (`P2_a_pour_type`, Type de statut social) en 2007 (`P82a_le_début_du_début`, Date de début du statut social) CE (`P79_a_son_début_qualifié_par`, Qualifiant de la date de début du statut social) par le Parlement du Canada (`P190_a_pour_contenu_symbolique`, Appellation de l'actant attribuant le statut social). L'honneur a été révoqué par la Chambre des communes le 27 septembre 2018 et par le Sénat (`P7_a_eu_lieu_dans`, Lieu du statut social « Canada ») le 2 octobre 2018 (`P82b_la_fin_de_la_fin`, Date de fin du statut social (discutable); `P80_a_sa_fin_qualifiée_par`, Qualifiant de la date de fin du statut social « Avant » (discutable)) en raison de préoccupations relatives aux droits de l'homme concernant son traitement des Rohingyas (Wikipedia 2022a).

<div id="0001_129_social-status" class="example"></div>

## Documentation connexe

### Modèles externes {#modeles-externes}

Liens vers les modèles externes

### Nœuds de saisie {#noeuds-de-saisie}

* [Appellation de l'actant attribuant le statut social](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-de-lactant-attribuant-le-statut-social) \| Liste de vérification
* [Date de début du statut social](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-du-statut-social) \| Liste de vérification
* [Date de fin du statut social](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-du-statut-social) \| Liste de vérification
* [Lieu du statut social](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#lieu-du-statut-social) \| Liste de vérification
* [Qualifiant de la date de début du statut social](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-du-statut-social) \| Liste de vérification
* [Qualifiant de la date de fin du statut social](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-du-statut-social) \| Liste de vérification
* [Type de statut social](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#type-de-statut-social) \| Liste de vérification

### Entités du CIDOC CRM {#entites-du-cidoc-crm}

* `E5_Évènement` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E5)]
* `E13_Assignation_d'attribut` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E13)]
* `E33_Objet_linguistique` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E33)]
* `E39_Actant` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E39)]
* `E41_Appellation` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E41)]
* `E52_Intervalle_temporel` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E52)]
* `E53_Lieu` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E53)]
* `E55_Type` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E55)]
* `O13_déclenche (est_déclenché_par)`
* `P1_est_identifié_par (identifie)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P1)]
* `P2_a_pour_type (est_le_type_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P2)]
* `P4_a_pour_intervalle_temporel (est_l'intervalle_temporel_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P4)]
* `P7_a_eu_lieu_dans (a_été_témoin_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P7)]
* `P11_a_eu_pour_actant_participant (a_participé_à)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P11)]
* `P14_a_été_effectué_par (a_effectué)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P14)]
* `P79_a_son_début_qualifié_par` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P79)]
* `P80_a_sa_fin_qualifiée_par` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P80)]
* `P82a_le_début_du_début`
* `P82b_la_fin_de_la_fin`
* `P140_a_assigné_l'attribut_à (a_reçu_l'attribut_par)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P140)]
* `P141_a_assigné (a_été_assigné_par)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P141)]
* `P190_a_pour_contenu_symbolique` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P190)]

## Discussion

### Justification

La classe `E5_Évènement` est utilisée pour représenter le statut social pour les raisons suivantes :

* Contrairement à l'occupation, le statut social est une position sociale qu'un actant peut ne pas avoir activement et intentionnellement recherchée lui-même; il est donc au-delà de la portée de la classe `F51_Pratique`. Néanmoins, il existe plusieurs occupations qui peuvent également être considérées comme des statuts sociaux et donc documentées dans les deux patrons conceptuels (p. ex. premier ministre);
* Souvent, le statut social n'est pas « effectué intentionnellement par » (Le Bœuf et al. 2015, sect. E7 Activity; notre traduction) l'actant décrit. Il s'agit plutôt d'un « changement d'état dans des systèmes culturels, sociaux ou physiques » (Le Bœuf et al. 2015, sect. E5 Event; notre traduction) auquel l'actant décrit a participé.

En outre, le statut social d'un actant est généralement attribué ou assigné par un autre actant qui est socialement habilité à le faire. Dans le CIDOC CRM, la classe `E13_Assignation_d'attribut` est considérée comme la plus appropriée pour représenter cette action, car elle « comprend les actions consistant à faire des affirmations sur les propriétés d'un objet ou sur toute relation entre deux éléments ou concepts. Cette classe permet de documenter la manière dont l'affectation respective a eu lieu et par qui elle a été réalisée » (Le Bœuf et al. 2015, sect. E13 Attribute Assignment; notre traduction). Cependant, cela repose sur une utilisation plus spécifique de la classe `E13_Assignation_d'attribut`, car elle ne décrit que l'évènement d'attribution socialement habilité, et pas seulement l'acte d'enregistrement du statut.

Bien sûr, l’obtention d'un statut social et son attribution ne sont pas deux évènements isolés. En fait, le second précède le premier. Pour documenter ce lien séquentiel, la propriété `O13_déclenche` de l'extension CRMsci est utilisée pour indiquer la relation de causalité entre ces deux évènements (Doerr et al. 2015, sect. O13 triggers (is triggered by)).

De plus, pour différencier ce type d'activité des autres types, notamment lors de l'exécution de requêtes, un nœud doté d’un qualifiant spécifié est nécessaire. Dans la version 1.5 du modèle cible, le statut social était davantage qualifié par deux niveaux supplémentaires de la classe `E55_Type`, par exemple `E55_Type` (« Compagnon de l'Ordre du Canada ») -> `P2_a_pour_type` -> `E55_Type` (« Titre honorifique ») -> `P2_a_pour_type` -> `E55_Type` (« Statut social »). Cependant, trois niveaux de `E55_Type` peuvent rapidement gonfler le modèle de données et compliquer sa maintenance et sa gestion pour un simple besoin de qualification du statut social. Par conséquent, deux niveaux de la classe `E55_Type` (le nœud de saisie pour le Type de statut social et le nœud doté d'un qualifiant spécifié portant le libellé « Statut social ») sont jugés suffisants. Si une hiérarchisation plus développée du statut social est nécessaire (p. ex. en distinguant différents types de statut social), elle doit être traitée en utilisant le vocabulaire de ce statut. 

### Limitations

Bien qu'il soit possible de documenter la personne qui a assigné le statut social et la fin de ce statut dans cette version du modèle DOPHEDA, il n'y a aucun moyen de documenter l'actant qui a supprimé ou invalidé le statut.

Il faut noter que le patron conceptuel décrit ci-dessus n'est qu'une solution temporaire pour documenter les informations sur le statut social d'un actant, en attendant une version officielle de la [CIDOC CRM Social Extension](http://www.cidoc-crm.org/crmsoc/). L'extension, qui est encore en cours de développement, aura probablement une classe semblable à une « Phase » qui pourrait documenter les statuts.

### Enjeux connexes sur GitHub

* [Enjeu n° 27 « Comment devrions-nous modéliser le ou les patrons conceptuels du statut social? »](https://github.com/chin-rcip/collections-model/issues/27) (en anglais)
* [Enjeu n° 29 « Avons-nous besoin de trois niveaux de types dans le patron conceptuel Occupation? »](https://github.com/chin-rcip/collections-model/issues/29) (en anglais)
* [Enjeu n° 37 « Utilité de `E55_Type` »](https://github.com/chin-rcip/collections-model/issues/37) (en anglais)

### Cas limites

#### Exemple 1 {#cas-limites-exemple-1}

Le statut social de Yousuf Karsh en tant que Compagnon de l'Ordre du Canada peut également être considéré comme une appartenance à un groupe, qui peut être modélisée en utilisant le patron conceptuel Appartenance à un groupe.

#### Exemple 2 {#cas-limites-exemple-2}

L'exemple d'Helen Keller mentionné plus haut est également un cas limite, puisqu'il est possible de considérer son activisme comme une occupation et non comme un statut social. Dans un tel cas, un statut social peut être attribué par une compréhension générale, et non pendant un évènement spécifique par un actant spécifique. Il devient toutefois difficile de savoir qui est l'actant chargé d'attribuer le statut social.

#### Exemple 3 {#cas-limites-exemple-3}

Alice Ann Munro est une nouvelliste canadienne et lauréate du prix Nobel de littérature (Type de statut social « Lauréate du prix Nobel »), qui lui a été décerné à Stockholm (Lieu du statut social) en 2013 (Date de début du statut social). Munro est décédée en 2013 peu de temps après avoir reçu le prix (Date de fin du statut social; Qualifiant de la date de fin du statut social « Après ») (Wikipedia 2022b). Il est débattable s'il existe une fin naturelle à un statut (c.-à-d. lorsque l'actant meurt) ou si la seule façon de mettre fin à un statut est la révocation officielle de ce statut (c.-à-d. que ceux qui ont conféré le statut en dépouillent le bénéficiaire).

## Bibliographie

Bekiari, Chryssoula, George Bruseker, Martin Doerr, Christian-Emil Ore, Stephen Stead, et Athanasios Velios, éds. *Definition of the CIDOC Conceptual Reference Model*. Documentations du CIDOC CRM, 7.1. Paris, FR-IDF : CIDOC CRM Special Interest Group, 2021. [http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf](http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf).

Doerr, Martin, Athina Kritsotaki, Yannis Rousakis, Gerald Hiebel et Maria Theodoridou. « O13 triggers (is triggered by) ». *Definition of the CRMsci: An Extension of CIDOC-CRM to Support Scientific Observation. 1.2.8*. Heraklion, GR : CIDOC CRM, 2020. [https://cidoc-crm.org/crmsci/sites/default/files/CRMsci%20v.1.2.8.pdf](https://cidoc-crm.org/crmsci/sites/default/files/CRMsci%20v.1.2.8.pdf).

Éditeurs de la Encyclopædia Britannica. « Social Status ». *Encyclopædia Britannica*. Londres, UK-LDN : Encyclopædia Britannica, 2019. [https://www.britannica.com/topic/social-status](https://www.britannica.com/topic/social-status).

Hillmer, Norman. « Roland Michener ». *L'Encyclopédie canadienne*. Toronto, CA-ON : Historica Canada, 2018 [2008]. [https://www.thecanadianencyclopedia.ca/fr/article/michener-daniel-roland](https://www.thecanadianencyclopedia.ca/fr/article/michener-daniel-roland).

Le Bœuf, Patrick, Martin Doerr, Christian Emil Ore, et Stephen Stead, éds. « E5 Event ». *Definition of the CIDOC Conceptual Reference Model*. Documentations du CIDOC CRM, 6.2.1. Paris, FR-IDF : Conseil international des musées (ICOM), 2015. [http://www.cidoc-crm.org/sites/default/files/cidoc_crm_version_6.2.1.pdf](http://www.cidoc-crm.org/sites/default/files/cidoc_crm_version_6.2.1.pdf).

–––. « E7 Activity ». *Definition of the CIDOC Conceptual Reference Model*. Documentations du CIDOC CRM, 6.2.1. Paris, FR-IDF : Conseil international des musées (ICOM), 2015. [http://www.cidoc-crm.org/sites/default/files/cidoc_crm_version_6.2.1.pdf](http://www.cidoc-crm.org/sites/default/files/cidoc_crm_version_6.2.1.pdf).

–––. « E13 Attribute Assignment ». *Definition of the CIDOC Conceptual Reference Model*. Documentations du CIDOC CRM, 6.2.1. Paris, FR-IDF : Conseil international des musées (ICOM), 2015. [http://www.cidoc-crm.org/sites/default/files/cidoc_crm_version_6.2.1.pdf](http://www.cidoc-crm.org/sites/default/files/cidoc_crm_version_6.2.1.pdf).

Skidmore, Colleen. « Yousuf Karsh ». *L'Encyclopédie canadienne*. Toronto, CA-ON : Historica Canada, 4 mars 2015 [2010]. [https://www.thecanadianencyclopedia.ca/en/article/yousuf-karsh](https://www.thecanadianencyclopedia.ca/en/article/yousuf-karsh).

Wikipedia. « Aung San Suu Kyi ». *Wikipedia*. San Francisco, US-CA : Wikipedia, 2022a. [https://fr.wikipedia.org/wiki/Aung_San_Suu_Kyi](https://fr.wikipedia.org/wiki/Aung_San_Suu_Kyi).

Wikipedia. « Alice Munro ». *Wikipedia*. San Francisco, US-CA : Wikipedia, 2022b. [https://fr.wikipedia.org/wiki/Alice_Munro](https://fr.wikipedia.org/wiki/Alice_Munro).

