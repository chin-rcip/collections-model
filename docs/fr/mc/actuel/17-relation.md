---
layout: page
language: fr
title: Relation
permalink: /fr/modele-cible/actuel/relation
other_link: /en/target-model/current/relationship
sidebar: mc22
date: 2022-06-30
description: La Spécification du modèle cible des actants modélise sémantiquement les actants dans un contexte patrimonial. Les patrons conceptuels les plus pertinents pour la vie des actants sont présentés avec des diagrammes et des exemples qui les illustrent, ainsi qu'un compte rendu et une explication des décisions pertinentes qui ont été prises lors de l'élaboration desdits patrons conceptuels. Il s'agit d'une documentation théorique qui n'a jamais été testée ou mise en application.
---

## Aperçu {#apercu}

Ce patron conceptuel peut être utilisé pour représenter les informations relatives à la relation entre deux actants (par association ou connaissance). Il comprend : 

* Le type de relation;
* Les appellations des actants liés;
* Le temps durant lequel les actants se sont associés l'un à l'autre;
* Les rôles que chaque actant a assumés au sein de la relation.

Ce patron conceptuel ne doit pas être utilisé pour représenter :

* La participation/l’adhésion d'un actant à un groupe (le patron conceptuel [Appartenance à un groupe](/collections-model/fr/modele-cible/actuel/appartenance-a-un-groupe) doit plutôt être utilisé);
* L'appartenance d'une personne à une famille (le patron conceptuel [Appartenance familiale](/collections-model/fr/modele-cible/actuel/appartenance-familiale) doit plutôt être utilisé);
* La relation parents-enfants dans une perspective biologique (le patron conceptuel [Naissance et mort d'une personne](/collections-model/fr/modele-cible/actuel/naissance-et-mort-dune-personne) doit plutôt être utilisé).

## Introduction et contexte

### Historique théorique {#historique-theorique}

Depuis la naissance, l'expérience de vie d'une personne est principalement façonnée par ses relations interpersonnelles, c'est-à-dire ses associations, ses liens et ses interactions avec les autres. Une relation est caractérisée par plusieurs dimensions, telles que le degré d'intimité, la durée, la réciprocité, la répartition du pouvoir, la fréquence, la spatialité et la régulation (Rashid et Blanco 2017). 

En outre, les relations interpersonnelles sont considérées comme des « systèmes dynamiques qui peuvent changer continuellement tout au long de leur existence » (Wikipedia 2019; notre traduction). Elles ont une durée de vie avec un début et une fin. Tout au long de sa vie, chaque actant d'une relation assume un rôle qui peut être modifié en fonction de l'évolution des dimensions de la relation, à l'exception des rôles dans les relations familiales. Par exemple, si en raison de divers facteurs et circonstances, deux actants qui étaient amis sont devenus ennemis, la nature de leur relation ainsi que leurs rôles ont changé.

### Énoncé des besoins {#enonce-des-besoins}

L'un des aspects les plus importants de la vie d'un actant est son association avec d'autres personnes et groupes, qu'il s'agisse de sa famille, de ses amis ou d'autres relations conséquentes. Lier les actants entre eux permet de construire un réseau virtuel qui permet des découvertes et des recherches fortuites dans différents domaines, tels que la généalogie, la sociologie, etc. Il est donc essentiel de modéliser ces relations de manière précise, significative et flexible.

Deux éléments d'une relation doivent être saisis : son type et les rôles joués par chaque actant, car un actant peut avoir plusieurs relations avec différents actants ainsi qu'avec un seul actant, et tenir un rôle spécifique dans chaque relation. Par exemple, pour Yousuf Karsh, George Nakash était un oncle dans le contexte de leur relation familiale, mais il était aussi son employeur dans le contexte de leur relation professionnelle. 

En outre, une relation a une date de début et une date de fin, qui sont souvent déterminées par des facteurs externes, et cette temporalité est souvent nécessaire à la désambiguïsation et à la collecte de données sur les actants.

## Description du patron conceptuel

Pour chaque relation, une instance de `E39_Actant` est d'abord liée à une instance de `PC14_a_été_effectué_par` (représentant l'actant dans un rôle) par la propriété `P02_a_pour_portée`. L'instance de `PC14_a_été_effectué_par` est alors liée à une instance de `E7_Activité` par la propriété `P01_a_pour_domaine`. 

À partir de la première instance de `PC14_a_été_effectué_par`, la valeur du [Rôle de l'actant dans la relation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#role-de-lactant-dans-la-relation) (une instance de `E55_Type`) est rendue par la propriété `P14.1_dans_le_rôle_de`.

De même, la valeur du [Rôle de l’actant lié](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#role-de-lactant-lie) (une instance de `E55_Type`) est rendue à partir de la deuxième instance de `PC14_a_été_effectué_par` par la propriété `P14.1_dans_le_rôle_de`. L'instance de `E39_Actant` identifiant l'actant lié est liée à une instance de `E41_Appellation` et de `E33_Objet_linguistique` par la propriété `P1_est_identifié_par`. De cette instance, la valeur littérale de l'[Appellation de l'actant lié](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-de-lactant-lie) est rendue par la propriété `P190_a_pour_contenu_symbolique`.

La durée de l'activité de relation est indiquée à l'aide du patron conceptuel [Limites temporelles](/collections-model/fr/modele-cible/actuel/limites-temporelles) lié à l'instance de `E7_Activité` par la propriété `P4_a_pour_intervalle_temporel` avec des valeurs extraites des nœuds de saisie [Date de début de la relation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-de-la-relation), [Qualifiant de la date de début de la relation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-de-la-relation), [Date de fin de la relation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-de-la-relation) et [Qualifiant de la date de fin de la relation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-de-la-relation). 

En outre, l'activité est qualifiée par la valeur du [Type de relation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#type-de-relation) (une instance de `E55_Type`) par le biais de la propriété `P2_a_pour_type`. Cette instance de `E55_Type` est en outre qualifiée par une instance de `E55_Type` (un nœud doté d’un qualifiant spécifié) portant le libellé « Relation » par le biais de la propriété `P2_a_pour_type`.

## Diagramme

<a name="056_PatronConceptuel_Relation_p"></a>056_PatronConceptuel_Relation_p

<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=056_PatronConceptuel_Relation_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D148zmKkFOLUmcrXdRRdotd7mQ92aPyDZq%26export%3Ddownload"></iframe>

## Exemples

Le photographe canadien d'origine arménienne Yousuf Karsh a été marié (`P2_a_pour_type`, Type de relation « Mariage ») à Solange Gauthier (`P190_a_pour_contenu_symbolique`, Appellation de l'actant lié) de 1939 (`P82a_le_début_du_début`, Date de début de la relation) à 1961 (`P82b_la_fin_de_la_fin`, Date de fin de la relation). Tous deux avaient le rôle « Époux »/« Épouse » dans la relation (`P14.1_dans_le_rôle_de`, Rôle de l'actant dans la relation) (Wikipedia 2021).

<div id="0001_100_relationship" class="example"></div>

## Documentation connexe

### Modèles externes {#modeles-externes}

* CRMbio : [Relationship Classes and Properties](http://ldf.fi/schema/bioc/)
* SARI : [Person Reference Data Model – Social Relations](https://docs.swissartresearch.net/et/persons/#social-relations)
* AgRelOn : [Relationship Classes and Properties](https://d-nb.info/standards/elementset/agrelon)
* ULAN : [Relationship Properties](http://vocab.getty.edu/ontology)
* Wikidata : [« significant person  » (P3342)](https://www.wikidata.org/wiki/Property:P3342) et la majorité de ses [sous-propriétés](https://w.wiki/3nYP); [Properties for Human Relationships](https://w.wiki/3nYf); [« object has role » (P3831)](https://www.wikidata.org/wiki/Property:P3831) et ses [sous-propriétés](https://w.wiki/3nYh).

### Nœuds de saisie {#noeuds-de-saisie}

* [Appellation de l'actant lié](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-de-lactant-lie) \| Liste de vérification
* [Date de début de la relation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-de-la-relation) \| Liste de vérification
* [Date de fin de la relation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-de-la-relation) \| Liste de vérification
* [Qualifiant de la date de début de la relation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-de-la-relation) \| Liste de vérification
* [Qualifiant de la date de fin de la relation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-de-la-relation) \| Liste de vérification
* [Rôle de l'actant dans la relation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#role-de-lactant-dans-la-relation) \| Liste de vérification
* [Rôle de l'actant lié](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#role-de-lactant-lie) \| Liste de vérification
* [Type de relation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#type-de-relation) \| Liste de vérification

### Entités du CIDOC CRM {#entites-du-cidoc-crm}

* `E7_Activité` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E7)]
* `E33_Objet_linguistique` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E33)]
* `E39_Actant` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E39)]
* `E41_Appellation` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E41)]
* `E52_Intervalle_temporel` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E52)]
* `E55_Type` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E55)]
* `PC14_a_été_effectué_par`
* `P01_a_pour_domaine (est_le_domaine_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P01)]
* `P02_a_pour_portée (est_la_portée_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P02)]
* `P1_est_identifié_par (identifie)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P1)]
* `P2_a_pour_type (est_le_type_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P2)]
* `P4_a_pour_intervalle_temporel (est_l’intervalle_temporel_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P4)]
* `P14_a_été_effectué_par (a_effectué)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P14)]
* `P14.1_dans_le_rôle_de` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P14.1)]
* `P79_a_son_début_qualifié_par` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P79)]
* `P80_a_sa_fin_qualifiée_par` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P80)]
* `P82a_le_début_du_début`
* `P82b_la_fin_de_la_fin`
* `P190_a_pour_contenu_symbolique` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P190)]

## Discussion

### Justification

L'ontologie CIDOC CRM ne dispose pas de classes ou de propriétés destinées à gérer spécifiquement les relations entre des actants, principalement parce qu'elle est orientée vers les objets. D'autres ontologies ont tenté de traiter cette question, notamment la [Agent Relationship Ontology](https://d-nb.info/standards/elementset/agrelon) (AgRelOn) (Löhden 2019) et CRMbio (Tuominen et Hyvönen 2020), mais leurs approches ne sont pas satisfaisantes.

La AgRelOn développée par la Deutsche National Bibliothek est conçue pour décrire et représenter des relations complexes entre des personnes et des groupes en utilisant diverses propriétés et classes. Cependant, l'utilisation d'une ontologie basée sur les propriétés implique la modification de la Spécification du modèle cible en ajoutant une nouvelle propriété chaque fois qu'un nouveau type de relation doit être représenté. Un modèle comportant trop de propriétés peut rapidement devenir excessivement compliqué et difficile à gérer.

CRMbio, une extension non officielle du CIDOC CRM, permet la représentation de relations complexes, mais pose toujours problème au niveau des requêtes et complique le modèle pour peu d'avantages sémantiques. Dans CRMbio, la classe `bioc:Actant` (une sous-classe de `E39_Actant`) n'est pas directement liée à une relation `bioc:Évènement` (une sous-classe de `E5_Évènement`). Ces entités sont plutôt liées par l'entité intermédiaire `bioc:Rôle_de_l'actant` (une sous-classe directe de `E1_Entité_CRM`) qui spécifie le rôle de l'actant (`bioc:Actant`) dans la relation en conjonction avec la classe `E55_Type`. En utilisant la classe `E55_Type` avec un vocabulaire contrôlé, il est possible de représenter plusieurs types de relations sans ajouter de nouvelles entités au modèle. Cependant, la classe `bioc:Rôle_de_l'actant` n'est pas une sous-classe de `bioc:Actant` ni de `E39_Actant`. Par conséquent, elle ne peut pas être sémantiquement liée à la classe `E5_Évènement` par la propriété `P11_a_eu_pour_actant_participant`. En outre, ce patron conceptuel repose sur un rôle pour participer aux évènements, ce qui est problématique en soi, car une personne peut être impliquée sans avoir un rôle précis documenté. 

La relation a été modélisée comme un seul évènement plutôt que deux pour les raisons suivantes :

* Le fait de ne pas lier le début et la fin de la relation peut entraîner des problèmes de requête. Bien que cette proposition respecte la note d'application de la classe `E5_Évènement`, il est difficile de cibler une instance claire représentant le lien entre deux évènements;
* Pour lier deux évènements, on pourrait utiliser la classe `E70_Chose` qui serait créée au début de la relation comme un remplacement pour la relation elle-même. Cependant, cela compliquerait considérablement le modèle en créant, pour une seule relation, deux instances de `E5_Évènement`, en plus d’une autre instance de `E70_Chose` sans que cette dernière n'ajoute aucune information qui ne soit déjà rendue par d'autres entités. 

Pendant ce temps, les [propriétés-classes](/collections-model/fr/modele-cible/actuel/concepts-generaux#proprietes-classes) ont été développées par le CRM SIG en 2014 dans le cadre d'une extension qui permet la réification de propriétés spécifiques (c.-à-d. qu'elles ont été transformées en classes) afin que les instances de ces propriétés-classes puissent devenir le sujet d'autres triplets sans compromettre les logiques du reste de l'ontologie. Ceci est utile pour modéliser le rôle d'un actant dans la production d'un artefact (voir le patron conceptuel [Artefact](/collections-model/fr/modele-cible/actuel/artefact), mais il peut également être utilisé pour indiquer le rôle d'un actant dans une relation.

Pour ce faire, les relations doivent être considérées comme des activités réalisées consciemment ou inconsciemment par les actants. Une instance de `E7_Activité` est liée à une instance de `E39_Actant` représentant l'actant impliqué en utilisant la propriété-classe `PC14_a_été_effectué_par` à laquelle est attribué un type par la propriété `P14.1_dans_le_rôle_de` et une instance de `E55_Type` spécifiant le rôle de chaque partie impliquée. 

L'utilisation de ce patron conceptuel présente quelques avantages : 

* Est conforme au CIDOC CRM, ce qui garantit la cohérence du modèle;
* Ne nécessite pas la création de nouvelles classes, ce qui est préférable pour la réutilisation;
* Est égalitaire et n'induit pas structurellement une hiérarchie artificielle entre les actants;
* Est bidirectionnelle, de sorte que le chemin « l'actant A est lié à l'actant B » est aussi vrai que « l'actant B est lié à l'actant A ». 

Plus d'information sur la justification de ce patron conceptuel est disponible dans les [Actes de la conférence CIDOC de 2020](https://cidoc.mini.icom.museum/cidoc-2020-conference-papers-published/). 

### Limitations

Le fait d'être inconscient d'exécuter une activité pourrait être considéré comme allant à l'encontre de la note d'application de la classe `E7_Activité`, qui stipule que l'activité doit être exécutée intentionnellement. Pour modéliser les relations, l'autre option serait d'utiliser la classe `E5_Évènement` dont les propriétés ne permettent pas la modélisation des rôles, ce qui compromet considérablement la granularité des informations qui pourraient être prises en compte par un tel patron conceptuel. Ainsi, il semble préférable d'utiliser la classe `E7_Activité` jusqu'à ce que le groupe de travail CRMsoc (une extension du CIDOC CRM pour l'intégration de données sur les phénomènes sociaux) développe un cadre plus approprié pour la représentation des relations.

### Enjeux connexes sur GitHub

* [Enjeu n° 16 « Avons-nous besoin d'un patron conceptuel Relations familiales? Et que faire des parents? »](https://github.com/chin-rcip/chin-rcip/issues/16) (en anglais)

### Cas limites

#### Exemple 1 {#cas-limites-exemple-1}

La mise en correspondance peut devenir délicate lorsque l'un des actants de la relation est un groupe et que l'on peut utiliser à la fois les patrons conceptuels Relation et Appartenance à un groupe.

Par exemple, le Musée du portrait du Canada et son Groupe consultatif peuvent être considérés comme étant :

* Dans une relation de « Consultation » (Type de relation), le Musée du portrait du Canada (Appellation de l'actant lié) étant l'« Actant conseillé » (Rôle de l'actant lié) et le Groupe consultatif (Appellation de l'actant) étant le « Consultant » (Rôle de l'actant dans la relation);
* Dans une dynamique d'appartenance à un groupe, le Groupe consultatif (Appellation de l'actant) ayant joint le Musée du portrait du Canada (Appellation du groupe) en tant que « Consultant » (Rôle du membre du groupe).

#### Exemple 2 {#cas-limites-exemple-2}

Un jeu de données qui documenterait une personne comme étant la figure paternelle ou maternelle d'une famille serait difficile à enregistrer, car la famille peut contenir plusieurs membres et le rôle parental peut ne pas s'appliquer à tous. Dans ce cas, il serait possible de documenter le fait que la personne appartienne à la famille par le biais du patron conceptuel Appartenance familiale, ou d'établir sa relation avec chaque membre de ladite famille par le biais du patron conceptuel de Relation. Cependant, il est impossible de documenter le rôle de la personne dans le premier scénario, et dans le second, il est fort probable que le soumissionnaire de données ne connaisse pas tous les membres de la famille, de sorte qu'il ne peut établir avec certitude leur relation.

## Bibliographie

Bekiari, Chryssoula, George Bruseker, Martin Doerr, Christian-Emil Ore, Stephen Stead, et Athanasios Velios, éds. *Definition of the CIDOC Conceptual Reference Model*. Documentations du CIDOC CRM, 7.1. Paris, FR-IDF : CIDOC CRM Special Interest Group, 2021. [http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf](http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf).

Deutsche National Bibliothek. « AgRelOn ». *AgRelOn, an Agent Relationship Ontology*. 2 octobre 2019. [https://d-nb.info/standards/elementset/agrelon](https://d-nb.info/standards/elementset/agrelon).

Löhden, Aenne. *AgRelOn: An Agent Relationship Ontology*. Frankfurt, DE-BB; Leipzig, DE-SN : Deutsche Nationalbibliothek, 2019. [https://d-nb.info/standards/elementset/agrelon_20190618](https://d-nb.info/standards/elementset/agrelon_20190618).

Rashid, Farzana, et Eduardo Blanco. « Dimensions of Interpersonal Relationships: Corpus and Experiments ». *Proceedings of the 2017 Conference on Empirical Methods in Natural Language Processing*. Copenhague, DEN : Association for Computational Linguistics, 2017. [https://doi.org/10.18653/v1/D17-1244](https://doi.org/10.18653/v1/D17-1244).

Tuominen, Jouni, et Eero Hyvönen. *Bio CRM: A Data Model for Representing Biographical Information for Prosopography*. Aalto University, Semantic Computing Research Group (SeCo). 2020. [https://seco.cs.aalto.fi/projects/biographies/biocrm-2020-05-28.pdf](https://seco.cs.aalto.fi/projects/biographies/biocrm-2020-05-28.pdf).

Wikipedia. « Interpersonal Relationship ». *Wikipedia*. San Francisco, US-CA : Wikipedia, 2019. [https://en.wikipedia.org/w/index.php?title=Interpersonal_relationship&oldid=918983104](https://en.wikipedia.org/w/index.php?title=Interpersonal_relationship&oldid=918983104).

Wikipedia. « Yousuf Karsh. » *Wikipedia*. San Francisco, US-CA : Wikipedia, 2021. [https://fr.wikipedia.org/wiki/Yousuf_Karsh](https://fr.wikipedia.org/wiki/Yousuf_Karsh).

