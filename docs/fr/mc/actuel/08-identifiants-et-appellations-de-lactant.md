---
layout: page
language: fr
title: Identifiants et appellations de l'actant
permalink: /fr/modele-cible/actuel/identifiants-et-appellations-de-lactant
other_link: /en/target-model/current/actor-identifiers-and-appellations
sidebar: mc22
date: 2022-06-30
description: La Spécification du modèle cible des actants modélise sémantiquement les actants dans un contexte patrimonial. Les patrons conceptuels les plus pertinents pour la vie des actants sont présentés avec des diagrammes et des exemples qui les illustrent, ainsi qu'un compte rendu et une explication des décisions pertinentes qui ont été prises lors de l'élaboration desdits patrons conceptuels. Il s'agit d'une documentation théorique qui n'a jamais été testée ou mise en application.
---

## Aperçu {#apercu}

Ce patron conceptuel peut être utilisé pour représenter les informations relatives à l'identité d'une personne ou d'un groupe au moyen de marqueurs tels que des noms, des chiffres, etc. Il comprend : 

* Les identifiants uniques attribués à un actant dans un système d'information et leurs types associés;
* Les appellations attribuées à un actant, y compris les titres honorifiques et autres titres ainsi que leurs types associés;
* La langue utilisée pour les appellations;
* La primauté d'une appellation sur les autres, telle qu'elle est déterminée par le soumissionnaire du jeu de données;
* Le contexte et l'époque dans lesquels une appellation est utilisée;
* Les parties qui composent une appellation et leurs types associés.

Ce patron conceptuel ne couvre pas les identifiants et les appellations des objets ou des artefacts (voir plutôt le patron conceptuel [Artefact](/collections-model/fr/modele-cible/actuel/artefact)). 

## Introduction et contexte

### Historique théorique {#historique-theorique}

Les appellations sont un élément essentiel de l'identification et de l'extraction de l'information ainsi que de la communication. C'est particulièrement le cas pour les noms propres et les identifiants alphanumériques qui sont plus difficiles à établir en utilisant des vocabulaires hiérarchiques externes reposant sur des libellés pour documenter les noms communs. 

Les appellations et les identifiants jouent un double rôle :

* La dénotation, qui permet d'identifier un élément donné en fonction d'un contexte donné; 
* Le sens, qui permet de communiquer quelque chose que le terme véhicule ou auquel il est associé (Granger 1982). 

Nommer ou attribuer un identifiant à une personne est un acte social qui s'accompagne d'un contexte et d'une signification. Par exemple, l'attribution d'un numéro à un·e prisonnier·ère n'est pas seulement un processus administratif, c'est aussi une forme de déshumanisation des interactions avec l'individu de la part de ceux qui « numérotent » le·la prisonnier·ère. De même, nommer quelqu'un a une signification sociale dans la mesure où une appellation peut être porteuse d'attentes en matière de masculinité ou de féminité qui dépendent du contexte et de la société. Ainsi, l'acte de nommer imprègne l'identification de la personne d'une composante identitaire qui va au-delà du simple besoin de dénotation (Granger 1982).

D'un point de vue historique, la perception qu'une société a d'une appellation ou le sens qu'elle lui attribue (Lecolle, Paveau et Reboul-Touré 2009) peut évoluer de manière suffisamment importante pour qu'elle soit fortement dépendante de son contexte spatio-temporel. Par exemple, le nom d'un groupe est parfois choisi pour évoquer quelque chose dans l'esprit des parties prenantes potentielles (p. ex. Greenpeace évoque l'environnementalisme par l'association des mots « vert » avec la nature, et « paix » avec la communion), comme c'est le cas des prénoms étymologiquement évocateurs (p. ex. Victoria évoque la victoire) (Lecolle, Paveau et Reboul-Touré 2009). Parce que les noms sont porteurs d'une signification propre à leur contexte social, ils ne peuvent pas être considérés comme uniques à une entité qu'ils désignent, ce qui indique que plusieurs entités peuvent être associées à la même appellation. Au fur et à mesure que le contexte s'élargit, une appellation seule n'est souvent pas suffisante pour identifier précisément un actant. Par exemple, dans le contexte de la vie familiale, le prénom d'un enfant peut suffire à l'identifier sans ambiguïté, mais ce n'est pas forcément le cas dans le contexte d'une classe d'école, où un camarade de classe peut également porter le même prénom. Dans ce dernier contexte, une combinaison de divers autres éléments tels que les dates de naissance, l'appartenance à un club, etc. est nécessaire (Granger 1982).

Cette question de l'unicité des appellations et des identifiants est encore plus importante lorsque leur contexte social ne peut pas être détecté intuitivement par une machine (Green et Bide 1997). Dans ce cas, les URI constituent le mécanisme le plus prometteur pour garantir que la machine puisse traiter les informations sans ambiguïté. Un ensemble de principes, qui garantissent le développement d'identifiants uniques et durables, a été élaboré par le RCIP. Un aperçu de ces principes est présenté dans le [Rapport technique sur les URI](/collections-model/fr/rapports-techniques/actuel/rapport-technique-sur-les-uri).

### Énoncé des besoins {#enonce-des-besoins}

L'identifiant primaire d'un actant dans le contexte d'un graphe de connaissances est son URI. Toutefois, avant l'attribution de cet URI dans le contexte de la soumission de données, la plupart des soumissionnaires de données ont eux-mêmes attribué des identifiants dédiés destinés à identifier l'actant de manière unique dans leur système d'information (p. ex. une base de données relationnelle, une feuille de calcul Excel, etc.). Ainsi, un même actant peut avoir plusieurs identifiants dont la finalité est déterminée par l'organisation, la division ou la personne à laquelle ils sont destinés. Pour préserver l'intégrité des données originales soumises, les identifiants doivent être soigneusement enregistrés, conservés et suivis. 

Outre ces identifiants, une personne ou un groupe est généralement identifié par ses appellations, dont l'orthographe et l'écriture peuvent varier en fonction de la langue utilisée. Par exemple, *Leonardo da Vinci* (en anglais) désigne la même personne que *Léonard de Vinci* (en français) et *Montreal Museum of Fine Arts* (en anglais) désigne la même institution que *Musée des beaux-arts de Montréal* (en français). Il est donc nécessaire d'indiquer la langue dans laquelle une appellation a été documentée.

En outre, tout au long de sa vie, un actant sera désigné par plus d'une seule appellation. Par exemple, lors de l'adoption du nom de famille de son époux ou de son épouse au moment du mariage, lors de l'acquisition d'un nouveau titre grâce à des réalisations reconnues comme l'obtention d'un doctorat, lors de l'utilisation de pseudonymes dans le contexte d'occupations spécifiques comme l'écriture sous un nom de plume, ou lors de l'adoption d'un nouveau nom ou d'autres changements d'apparence publique pour mieux représenter l'identité personnelle ou collective. Pour qualifier davantage l'identification d'un actant, il est nécessaire d'enregistrer le type d'une appellation ainsi que le contexte et l'époque dans lesquels elle a été utilisée. 

Bien que le RCIP soit un agrégateur, il ne se prononce pas sur la primauté des appellations. La plupart des soumissionnaires utilisent des noms préférés et alternatifs dans leur système d'information, ce dont ce modèle doit tenir compte afin de préserver l'intégrité des données originales.

De plus, une appellation est souvent composée de nombreuses parties qui sont significatives dans le contexte de leur catégorie respective (p. ex. une personne peut avoir un prénom, un second prénom et un nom de famille, et n'importe lequel de ces noms peut être Jean), de sorte que les partitions d'une appellation et les types associés sont nécessaires pour éviter la perte d'informations ou l'inexactitude, en plus de conserver la richesse d'un jeu de données. 

Un autre élément lié à l'appellation d'un actant est la localisation géographique de sa présence physique et le lieu où l'appellation a été utilisée, notamment pour les groupes (voir le patron conceptuel [Évènement de séjour](/collections-model/fr/modele-cible/actuel/evenement-de-sejour)). Par exemple, une entreprise pourrait avoir utilisé deux noms enregistrés différents associés à deux adresses différentes. 

La documentation des appellations est également essentielle pour les recherches onomastiques et généalogiques. Non seulement elle aide généralement à identifier les actants et les groupes d'actants, mais elle fournit aussi des informations importantes sur les tendances en matière de noms et, dans certains cas, contribue à l'identification des origines des noms et des antécédents familiaux (p. ex. en retraçant les flux migratoires).

## Description du patron conceptuel

L'identifiant unique d'un actant est rendu en liant une instance de `E39_Actant` par la propriété `P1_est_identifié_par` à une instance de `E42_Identifiant` qui est qualifiée par la valeur du [Type d’identifiant de l’actant](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#type-didentifiant-de-lactant) (une instance de `E55_Type`) par la propriété `P2_a_pour_type`. Cette même instance de `E42_Identifiant` est également liée à la valeur littérale de l'[Identifiant de l’actant](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#identifiant-de-lactant) par la propriété `P190_a_pour_contenu_symbolique`. 

Pour chaque appellation, l'instance de `E39_Actant` est liée par la propriété `P1_est_identifié_par` à une instance de `E41_Appellation` et de `E33_Objet_linguistique` qui est aussi liée à :

* La valeur littérale de l'[Appellation de l'actant](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-de-lactant) par la propriété `P190_a_pour_contenu_symbolique`;
* La valeur de la [Langue de l'appellation de l'actant](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#langue-de-lappellation-de-lactant) (une instance de `E56_Langue`) par la propriété `P72_a_pour_langue`;
* La valeur du [Type d’appellation de l’actant](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#type-dappellation-de-lactant) (une instance de `E55_Type`) par la propriété `P2_a_pour_type`. De plus, cette instance est qualifiée par une instance de `E55_Type` (un nœud doté d’un qualifiant spécifié) portant le libellé « Type d'appellation » par le biais de la propriété `P2_a_pour_type`;
* La valeur de la [Primauté de l’appellation de l’actant](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#primaute-de-lappellation-de-lactant) (une instance de `E55_Type`) par la propriété `P2_a_pour_type`. De plus, cette instance est qualifiée par une instance de `E55_Type` (un nœud doté d’un qualifiant spécifié) portant le libellé « Primauté » par le biais de la propriété `P2_a_pour_type`;
* Une instance de `E41_Appellation` et de `E33_Objet_linguistique` par la propriété `P106_est_composé_de` pour chaque partie qui compose l'appellation. À partir de cette instance, les propriétés `P190_a_pour_contenu_symbolique` et `P2_a_pour_type` sont utilisées pour rendre respectivement la valeur littérale de la [Partie de l'appellation de l’actant](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#partie-de-lappellation-de-lactant) et du [Type de partie de l'appellation de l’actant](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#type-de-partie-de-lappellation-de-lactant) (une instance de `E55_Type`) qui est encore qualifiée par une autre instance de `E55_Type` (un nœud doté d’un qualifiant spécifié) portant le libellé « Type de partie de l'appellation » par la propriété `P2_a_pour_type`;
* Une instance de `F52_Activité_d'utilisation_du_nom` par la propriété `R64i_a_été_le_nom_mobilisé_par`. De cette instance, la valeur du [Contexte d’utilisation de l’appellation de l'actant](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#contexte-dutilisation-de-lappellation-de-lactant) (une instance de `E55_Type`) est rendue par la propriété `R61_s'est_produit_dans_le_type_de_contexte` et l'intervalle temporel lors duquel le contexte a été utilisé est indiqué à l'aide du patron conceptuel [Limites temporelles](/collections-model/fr/modele-cible/actuel/limites-temporelles) par la propriété `P4_a_pour_intervalle_temporel` avec des valeurs extraites des nœuds de saisie [Date de début d’utilisation de l'appellation de l'actant](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-dutilisation-de-lappellation-de-lactant), [Qualifiant de la date de début d'utilisation de l'appellation de l'actant](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-dutilisation-de-lappellation-de-lactant), [Date de fin d'utilisation de l'appellation de l'actant](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-dutilisation-de-lappellation-de-lactant) et [Qualifiant de la date de fin d'utilisation de l'appellation de l'actant](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-dutilisation-de-lappellation-de-lactant).

## Diagramme

<a name="020_PatronConceptuel_IdentifiantsEtAppellations_p"></a>020_PatronConceptuel_IdentifiantsEtAppellations_p

<iframe frameborder="0" style="width:100%;height:500px;" src="https://viewer.diagrams.net/?highlight=0000ff&edit=_blank&layers=1&nav=1&title=020_PatronConceptuel_IdentifiantsEtAppellations_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1zD6FYZAeAYRfb0HVzE2mr-RCftsImGGX%26export%3Ddownload"></iframe>

## Exemples

### Identifiants

Dans Artistes au Canada, l'identifiant (`P2_a_pour_type`, Type d'identifiant de l'actant « Identifiant d'Artistes au Canada ») de Yousuf Karsh (`P190_a_pour_contenu_symbolique`, Appellation de l'actant) est 8494 (`P190_a_pour_contenu_symbolique`, Identifiant de l'actant) (Patrimoine canadien, Gouvernement du Canada 2011).

<div id="0001_100_identifier" class="example"></div>

### Appellations

Yousuf Karsh (`P190_a_pour_contenu_symbolique`, Appellation de l'actant) est l'orthographe anglaise (`P72_a_pour_langue`, Langue de l’appellation de l’actant) du nom complet du photographe arméno-canadien (`P2_a_pour_type`, Type d'appellation de l’actant), tandis que Յուսուֆ Քարշ (`P190_a_pour_contenu_symbolique`, Appellation de l'actant) est l'orthographe arménienne (`P72_a_pour_langue`, Langue de l'appellation de l'actant). Yousuf Karsh est le nom préféré (`P2_a_pour_type`, Primauté de l'appellation de l'actant) par le Musée des beaux-arts du Canada (le contributeur de l'enregistrement de Yousuf Karsh dans Artistes au Canada). Yousuf (`P190_a_pour_contenu_symbolique`, Partie de l'appellation de l’actant) est son prénom (`P2_a_pour_type`, Type de partie de l’appellation de l’actant) et Karsh (`P190_a_pour_contenu_symbolique`, Partie de l’appellation de l’actant) est son nom de famille (`P2_a_pour_type`, Type de partie de l’appellation de l’actant) (Patrimoine canadien, Gouvernement du Canada 2011).

<div id="0001_100_appellations" class="example"></div>

### Utilisation du nom

Charles Lutwidge Dodgson a utilisé le nom de plume (`P2_a_pour_type` Type d’appellation de l’actant) Lewis Carroll (`P190_a_pour_contenu_symbolique`, Appellation de l’actant) de 1856 (`P82a_le_début_du_début`, Date de début d’utilisation de l’appellation de l'actant) à sa mort en 1898 (`P82b_la_fin_de_la_fin`, Date de fin d’utilisation de l’appellation de l'actant) en publiant des livres pour enfants (`R61_s'est_produit_dans_le_type_de_contexte`, Contexte d'utilisation de l'appellation de l'actant « Écriture de livres pour enfants ») alors que son travail de mathématicien (`R61_s'est_produit_dans_le_type_de_contexte`, Contexte d'utilisation de l'appellation de l'actant « Auteur de traités de mathématiques ») était publié sous son nom de naissance (`P2_a_pour_type`, Type d'appellation de l'actant) Charles Lutwidge Dodgson (`P190_a_pour_contenu_symbolique`, Appellation de l'actant) (Wikipedia 2022a).

<div id="0001_102_name-use" class="example"></div>

## Documentation connexe

### Modèles externes {#modeles-externes}

* Linked.art : [Names and Identifiers for a Resource](https://linked.art/model/base/#names-and-identifiers-for-a-resource)
* SARI : [Person Reference Data Model – Names and Classifications](https://docs.swissartresearch.net/et/persons/#names-and-classifications)

### Nœuds de saisie {#noeuds-de-saisie}

* [Appellation de l'actant](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-de-lactant) \| Liste de vérification
* [Contexte d'utilisation de l’appellation de l’actant](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#contexte-dutilisation-de-lappellation-de-lactant) \| Liste de vérification
* [Date de début d'utilisation de l'appellation de l'actant](//collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-dutilisation-de-lappellation-de-lactant) \| Liste de vérification
* [Date de fin d'utilisation de l'appellation de l'actant](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-dutilisation-de-lappellation-de-lactant) \| Liste de vérification
* [Identifiant de l'actant](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#identifiant-de-lactant) \| Liste de vérification
* [Langue de l'appellation de l’actant](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#langue-de-lappellation-de-lactant) \| Liste de vérification
* [Partie de l'appellation de l'actant](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#partie-de-lappellation-de-lactant) \| Liste de vérification
* [Primauté de l'appellation de l'actant](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#primaute-de-lappellation-de-lactant) \| Liste de vérification
* [Qualifiant de la date de début d'utilisation de l'appellation de l'actant](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-dutilisation-de-lappellation-de-lactant) \| Liste de vérification
* [Qualifiant de la date de fin d'utilisation de l'appellation de l'actant](//collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-dutilisation-de-lappellation-de-lactant) \| Liste de vérification
* [Type d'appellation de l'actant](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#type-dappellation-de-lactant) \| Liste de vérification
* [Type de partie de l’appellation de l’actant](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#type-de-partie-de-lappellation-de-lactant) \| Liste de vérification
* [Type d'identifiant de l'actant](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#type-didentifiant-de-lactant) \| Liste de vérification

De plus, toutes les appellations et les identifiants des actants liés à l'actant documenté utilisent les nœuds de saisie présentés ci-dessus. En d'autres termes, les nœuds suivants peuvent également être décrits comme un [Identifiant de l'actant](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#identifiant-de-lactant), une [Appellation de l'actant](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-de-lactant) ou une [Partie de l'appellation de l'actant](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#partie-de-lappellation-de-lactant) selon le contenu enregistré. Il s'agit notamment des nœuds suivants :

* [Appellation de l'actant attribuant le statut social](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-de-lactant-attribuant-le-statut-social) \| Liste de vérification
* [Appellation de l'actant effectuant la dissolution](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-de-lactant-effectuant-la-dissolution) \| Liste de vérification
* [Appellation de l'actant fondateur](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-de-lactant-fondateur) \| Liste de vérification
* [Appellation de l'actant lié](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-de-lactant-lie) \| Liste de vérification
* [Appellation de l'actant participant à la création du jeu de données](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-de-lactant-participant-a-la-creation-du-jeu-de-donnees) \| Liste de vérification
* [Appellation de l'actant rédigeant la note curatoriale](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-de-lactant-redigeant-la-note-curatoriale) \| Liste de vérification
* [Appellation de la famille](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-de-la-famille) \| Liste de vérification
* [Appellation de la mère](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-de-la-mere) \| Liste de vérification
* [Appellation du contributeur de l’enregistrement](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-du-contributeur-de-lenregistrement) \| Liste de vérification
* [Appellation du groupe](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-du-groupe) \| Liste de vérification
* [Appellation du père](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-du-pere) \| Liste de vérification

### Entités du CIDOC CRM {#entites-du-cidoc-crm}

* `E7_Activité` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E7)]
* `E33_Objet_linguistique` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E33)]
* `E39_Actant` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E39)]
* `E41_Appellation` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E41)]
* `E42_Identifiant` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E42)]
* `E52_Intervalle_temporel` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E52)]
* `E55_Type` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E55)]
* `E56_Langue` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E56)]
* `F52_Activité_d'utilisation_du_nom`
* `P1_est_identifié_par (identifie)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P1)]
* `P2_a_pour_type (est_le_type_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P2)]
* `P4_a_pour_intervalle_temporel (est_l’intervalle_temporel_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P4)]
* `P16_a_mobilisé_l’objet_spécifique (a_été_mobilisé_pour)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P16)]
* `P72_a_pour_langue (est_la_langue_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P72)]
* `P79_a_son_début_qualifié_par` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P79)]
* `P80_a_sa_fin_qualifiée_par` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P80)]
* `P82a_le_début_du_début`
* `P82b_la_fin_de_la_fin`
* `P106_est_composé_de (fait_partie_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P106)]
* `P190_a_pour_contenu_symbolique` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P190)]
* `R61_s'est_produit_dans_le_type_de_contexte (était_le_type_de_contexte_pour)`
* `R64_a_mobilisé_le_nom (a_été_le_nom_mobilisé_par)`

## Discussion

### Justification

Le CIDOC CRM suggère l'utilisation de la classe `E41_Appellation` en conjonction avec la propriété `P1_est_identifié_par` pour représenter les noms qui n'ont généralement pas besoin que la langue utilisée soit précisée, car le plus souvent une seule orthographe est employée pour toutes les langues. Cependant, le nom d'un actant peut avoir été traduit ou adapté, par exemple *Leonardo da Vinci* est *Léonard de Vinci* en français. Toutes les variations sont nécessaires pour la recherche et l'analyse des données ainsi que pour la réconciliation, de sorte qu'elles doivent être prises en compte conjointement avec leur langue respective. Pour ce faire, il est possible d'étiqueter une valeur littérale avec une étiquette de langue (p. ex. @en, @fr), mais ajouter la langue directement au patron conceptuel des appellations à travers la propriété `P72_a_pour_langue` augmente la vitesse des requêtes SPARQL et semble donc être une meilleure pratique. Cependant, une instance de `E41_Appellation` seule ne peut pas être liée à une valeur de langue par la propriété `P72_a_pour_langue`. C'est pourquoi une instance de `E41_Appellation` et de `E33_Objet_linguistique` est plus appropriée. 

Dans le modèle DOPHEDA, chaque appellation est traitée comme unique à son porteur plutôt que partagée entre différents actants, même si l'approche de « l'appellation partagée » est théoriquement plus compatible avec les principes des données liées; chaque appellation doit être représentée comme un URI unique qui est lié à plusieurs actants portant le même nom. Comme expliqué dans l'Historique théorique, une appellation est porteuse d'une signification infléchie par son contexte social. Toutefois, cette approche peut être difficile à mettre en application. Par exemple, la réconciliation avec l'URI d'une même appellation doit être faite pour chaque processus de cartographie. De plus, le RCIP n'a pas encore identifié une utilisation immédiate et prévisible de l’« approche de l'appellation partagée » (voir l'[Enjeu no 25](https://github.com/chin-rcip/collections-model/issues/25)).

En termes de primauté, la propriété `P139_a_pour_forme_alternative` peut être utilisée, mais elle rendra l'appellation préférée dépendante de l'existence d'une appellation alternative, ce qui complexifie significativement le patron conceptuel et la gestion des données qu'il accueille. Cette approche complique considérablement les requêtes SPARQL puisque, lors de la recherche des différentes appellations d'un même actant, la même appellation revient plusieurs fois. De plus, lors de la recherche d'une appellation spécifique, il est difficile de différencier les appellations préférées des appellations non préférées. 

Cela dit, le chemin sémantique `P2_a_pour_type` et `E55_Type` offre une solution simple pour indiquer l'appellation préférée d'une organisation tout en affichant les autres noms d'un actant (`E39_Actant`). La primauté d'une appellation doit être distinguée en s'appuyant sur un vocabulaire contrôlé plutôt que sur un booléen, car les nœuds de primauté sont plus significatifs que « oui » ou « non » (p. ex. cela permet de rechercher toutes les appellations préférées parmi les actants).

Pour les partitions d'appellations, deux options ont été envisagées. La première possibilité était d'ajouter directement les différentes parties des appellations (`E33_Objet_linguistique` et `E41_Appellation`) de l'actant (`E39_Actant`) en utilisant les propriétés `P1_est_identifié_par` et `P2_a_pour_type` avec une instance de `E55_Type` afin de préciser quelle partie du nom est représentée. Toutefois, il aurait été impossible de savoir quelles parties de l'appellation non préférée doivent être combinées entre elles pour créer une appellation complète. L'autre option, suggérée par le projet [Linked.art](https://linked.art/model/actor/#parts-of-names), était de lier l'appellation complète à l'actant pour ensuite la partitionner avec la propriété `P106_est_composé_de`. Cette deuxième solution a été adoptée par le RCIP, car elle facilite les requêtes et réduit les coûts de rendement. 

Pour déterminer le lieu associé à l'appellation, les valeurs du nœud de saisie [Lieu du séjour](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#lieu-du-sejour) peuvent être interrogées pour identifier le chevauchement entre l'utilisation de l'appellation pendant un certain temps ainsi que le lieu et le moment lors duquel cet évènement de séjour s'est produit; ce chevauchement pourrait correspondre au lieu auquel une appellation est associée. Toutefois, cela ne peut fonctionner que si l'on part du principe erroné que les données temporelles sont toujours enregistrées et disponibles. En outre, si un actant porte deux noms différents à la fois, il serait impossible d'utiliser un algorithme pour déterminer lequel a été utilisé pour quel lieu. Ainsi, la modélisation de la connexion entre une appellation et le lieu qui lui est associé est considérée comme une meilleure solution que de s'appuyer sur des requêtes pour le faire, et deux options sont possibles :

* La propriété `P16_a_mobilisé_l’objet_spécifique (a_été_mobilisé_pour)` est employée pour lier l'appellation à son activité de séjour, à partir de laquelle les informations sur le lieu sont rendues en utilisant la propriété `P7_a_eu_lieu_dans`. Cela permet d'indiquer que lors de son séjour dans ce lieu, l'actant a utilisé cette appellation;
* La propriété `P7_a_eu_lieu_dans` est utilisée pour lier directement l'activité d'utilisation de l'appellation au lieu où elle s'est produite. Cela suggère que l'appellation a été utilisée pour cette activité, qui s'est déroulée dans un ou plusieurs lieux.

Bien que ces options diffèrent légèrement en termes de sémantique, elles peuvent toutes les deux être utilisées pour indiquer le lieu associé à une appellation. Cependant, l'activité d'utilisation du nom peut elle-même ne pas être située dans un espace en soi. Par exemple, Charles Dodgson a utilisé le pseudonyme Lewis Carroll pour son activité d'écriture et il a également séjourné dans un lieu sous ce nom. Un lien direct entre l'activité d'utilisation du nom et le lieu implique que l'utilisation de ce nom pour l'écriture s'est effectivement produite dans ce lieu, mais ce n'est peut-être pas le cas. En revanche, il est plus exact de dire que lors de son séjour dans ce lieu, l'actant a porté cette appellation, qui était utilisée pour cette activité. Ainsi, l'association de l'évènement de séjour à l'appellation (première option) est recommandée par le RCIP pour l'environnement DOPHEDA. 

### Limitations

Même si le modèle ne requiert pas de documenter à la fois l'[Appellation de l'actant](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-de-lactant) et la [Partie de l’appellation de l'actant](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#partie-de-lappellation-de-lactant), la présence de ces deux informations permet une plus grande souplesse dans la rédaction des demandes tout en les simplifiant. Cependant, si l'une ou l'autre n'est pas documentée et catégorisée dans le jeu de données d'origine, il est difficilement possible de générer correctement des instances de l'une à l'autre automatiquement.

De plus, l'incapacité du modèle à gérer des appellations socialement partagées est un aspect important du domaine de la généalogie. Actuellement, le même prénom utilisé par deux personnes différentes a deux URI différents. Cet aspect particulier est dû à la complexité de la distinction entre les informations qui s'appliquent au nom partagé et celles qui s'appliquent spécifiquement au nom d'un actant particulier. Le RCIP a donc décidé d'attribuer un URI par nom et par actant, puisque les cas d'utilisation ne présentaient pas de données sur le nom générique en soi. Par conséquent, les informations relatives à l'appellation ne peuvent être trouvées que dans le contexte d'un actant spécifique, plutôt que dans le contexte historique indépendant de l'actant, ce qui limite les recherches généalogiques et onomastiques.

### Enjeux connexes sur GitHub

* [Enjeu n° 24 « Devrions-nous utiliser des booléens pour la préférence ou simplement un vocabulaire contrôlé? »](https://github.com/chin-rcip/chin-rcip/issues/24) (en anglais)
* [Enjeu n° 25 « Une appellation est-elle unique à son porteur? »](https://github.com/chin-rcip/chin-rcip/issues/25) (en anglais)
* [Enjeu n° 35 « Faut-il dater les appellations? »](https://github.com/chin-rcip/chin-rcip/issues/35) (en anglais)

### Cas limites

#### Exemple 1 {#cas-limites-exemple-1}

La Reine Elizabeth II, l'appellation de la personne qui a été chargée d'accorder officiellement le statut social de « Compagnon de l'Ordre du Canada » à Yousuf Karsh, est souvent utilisée pour identifier le monarque régnant actuellement au Royaume-Uni. Alors que les parties de l'appellation « Elizabeth » et « II » (Parties de l'appellation de l'actant) peuvent respectivement être catégorisées comme « Prénom » et « Suffixe » (Type de partie de l'appellation de l'actant), la partie de la valeur « Reine » peut devenir assez délicate lors du processus de cartographie. En effet, l’appellation « Reine » pourrait être traitée comme le « Titre » lié à un nom ou le « Statut social » de l'actant portant ce nom. Dans un tel cas, la personne chargée de la modélisation doit respecter l'intention de catalogage originale du soumissionnaire d'origine. Par exemple, si l’appellation « Reine » a été enregistrée comme une valeur dans le champ relatif à l'appellation, elle peut être considérée comme un « Titre » (Type de partie de l'appellation de l'actant).

#### Exemple 2 {#cas-limites-exemple-2}

Si un artiste de guerre se voyait attribuer le numéro M32 435 C84 (son numéro de matricule militaire), ce numéro serait qualifié comme l'Appellation de l'actant et le Type d'appellation de l'actant serait « Numéro de matricule militaire » ou « Identifiant militaire ». Si le Musée de la guerre est lié au ministère de la Défense nationale ou utilise les mêmes numéros pour identifier les artistes, ce numéro serait à la fois qualifié d'Appellation de l'actant (le numéro attribué par le ministère de la Défense nationale) et d'Identifiant de l'actant (le même numéro utilisé par le Musée de la guerre).

#### Exemple 3 {#cas-limites-exemple-3}

L'appellation française de Power Corporation of Canada est Power Corporation du Canada. Une institution souhaitant enregistrer ces deux appellations pourrait créer deux Appellations de l'actant (une pour Power Corporation of Canada avec pour Langue de l'appellation de l'actant l'anglais, et une pour Power Corporation du Canada avec pour Langue de l'appellation de l'actant le français), ou créer une seule appellation bilingue (Power Corporation of Canada/Power Corporation du Canada).

#### Exemple 4 {#cas-limites-exemple-4}

Il en va de même pour de nombreux organismes gouvernementaux au Canada, tels que PCH Canadian Heritage/Patrimoine canadien, où, en outre, la question de la langue de l'acronyme n'est pas claire : si PCH est l'Appellation de l'actant avec un Type d'appellation de l'actant désigné « Acronyme », il est possible de considérer cela comme une seule appellation bilingue.

#### Exemple 5 {#cas-limites-exemple-5}

Certaines institutions ont besoin de documenter les animaux en tant qu'actants et bien que la définition actuelle puisse s'y adapter, le modèle du CIDOC CRM pourrait ne pas le faire. Par exemple, Wojtek était un ours officiellement enrôlé dans l'armée polonaise (Wikipedia 2022b).

#### Exemple 6 {#cas-limites-exemple-6}

Une adresse IP peut être considérée comme un identifiant qui réfère à l'actant, mais ne le représente pas. Il est incertain si le Type d'identifiant de l'actant peut contenir l'adresse IP, étant donné que plusieurs actants peuvent utiliser un seul ordinateur, en particulier s'il s'agit d'un duo qui utilise l'ordinateur pour créer un objet de manière semi-automatique, de sorte que l'ordinateur prend part à la création. Dans le cas de l'art généré par les médias, il est également incertain si l'adresse IP fait partie des Identifiants de l'artefact, des Identifiants de l'actant, ou des deux.

#### Exemple 7 {#cas-limites-exemple-7}

SAMO est un graffiti qui a été utilisé à New York de 1977 à 1980, principalement par Jean-Michel Basquiat et Al Diaz. Il pourrait être considéré comme une Appellation de l'actant (Type d'appellation de l'actant « Pseudonyme »); si c'est le cas, les dates ne poseraient pas de problème (Date de fin d'utilisation de l’appellation de l’actant « 1980-12-31T23:59:59 »). Cependant, il pourrait également être considéré comme un Artefact (puisque SAMO a été utilisé partout dans la ville), et donc être utilisé par de multiples actants (Wikipedia 2021). Cela soulève la question de savoir si une date d'utilisation d'une appellation a une fin lorsque des personnes continuent d'utiliser l'appellation bien après la mort de l'actant. Il pourrait y avoir, dans ce cas, une Appellation de l'artefact et une Appellation de l'actant portant le même nom, mais la manière de gérer les dates pour chacune d'elles devrait être clarifiée.

## Bibliographie

Bekiari, Chryssoula, Martin Doerr, Patrick Le Bœuf, et Pat Riva, éds. *FRBR Object-Oriented Definition and Mapping from FRBRER, FRAD and FRSAD*. Documentations du FRBRoo, 2.4. Conseil international des musées (ICOM), 2015. [http://www.cidoc-crm.org/frbroo/sites/default/files/FRBRoo\_V2.4.pdf](http://www.cidoc-crm.org/frbroo/sites/default/files/FRBRoo_V2.4.pdf).

Bekiari, Chryssoula, George Bruseker, Martin Doerr, Christian-Emil Ore, Stephen Stead, et Athanasios Velios, éds. *Definition of the CIDOC Conceptual Reference Model*. Documentations du CIDOC CRM, 7.1. Paris, FR-IDF : CIDOC CRM Special Interest Group, 2021. [http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf](http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf).

Granger, Gilles Gaston. « À quoi servent les noms propres? ». *Langages* 16, n° 66 (1982) : 21-36. [https://doi.org/10.3406/lgge.1982.1124](https://doi.org/10.3406/lgge.1982.1124).

Green, Brian, et Mark Bide. *Unique Identifiers: A Brief Introduction*. 2Rev e. édition. Londres, UK-LDN : Book Industry Communication, 1997.

Lecolle, Michelle, Marie-Anne Paveau, et Sandrine Reboul-Touré. « Les sens des noms propres en discours ». *Les Carnets du Cediscor*. Publication du Centre de recherches sur la didacticité des discours ordinaires, 11 (mars 2009) : 9-20.

Patrimoine canadien, Gouvernement du Canada. « Karsh, Yousuf ». *Artistes au Canada*. Ottawa, CA-ON : Gouvernement du Canada, 2011. [https://app.pch.gc.ca/application/aac-aic/artiste_detailler_bas-artist_detail_bas.app?lang=en&rID=8494](https://app.pch.gc.ca/application/aac-aic/artiste_detailler_bas-artist_detail_bas.app?lang=en&rID=8494).

Wikipedia. « SAMO ». *Wikipedia*. San Francisco, US-CA : Wikipedia, 2021. [https://fr.wikipedia.org/wiki/SAMO](https://fr.wikipedia.org/wiki/SAMO).

Wikipedia. « Lewis Caroll ». *Wikipedia*. San Francisco, US-CA : Wikipedia, 2022a. [https://en.wikipedia.org/wiki/Lewis_Carroll](https://en.wikipedia.org/wiki/Lewis_Carroll).

Wikipedia. « Wojtek ». *Wikipedia*. San Francisco, US-CA : Wikipedia, 2022b. [https://fr.wikipedia.org/wiki/Wojtek](https://fr.wikipedia.org/wiki/Wojtek).

