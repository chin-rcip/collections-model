---
layout: page
language: fr
title: Appartenance à un groupe
permalink: /fr/modele-cible/actuel/appartenance-a-un-groupe
other_link: /en/target-model/current/group-belonging
sidebar: mc22
date: 2022-06-30
description: La Spécification du modèle cible des actants modélise sémantiquement les actants dans un contexte patrimonial. Les patrons conceptuels les plus pertinents pour la vie des actants sont présentés avec des diagrammes et des exemples qui les illustrent, ainsi qu'un compte rendu et une explication des décisions pertinentes qui ont été prises lors de l'élaboration desdits patrons conceptuels. Il s'agit d'une documentation théorique qui n'a jamais été testée ou mise en application.
---

## Aperçu {#apercu}

Ce patron conceptuel peut être utilisé pour représenter les informations relatives à l'association officielle d'une personne (ou d'un groupe) avec un (autre) groupe, le plus souvent sous la forme d'un enregistrement d'adhésion ou d'inscription. Il comprend : 

* Le groupe avec lequel il y a une association; 
* Le rôle endossé par un actant dans le contexte d'un groupe; 
* Les dates indiquant le moment lors duquel un actant a rejoint et quitté un groupe (début et fin de l'appartenance à un groupe).

Il se rapporte spécifiquement à l'appartenance dans le contexte de personnes et de groupes de personnes, et non à la nature d'un groupe. Ce patron conceptuel ne comprend pas : 

* L'affiliation (et le rôle) des actants avec des groupes dont les frontières ne sont pas formellement définies;
* La non-appartenance (p. ex. le rejet d'un groupe dont une personne n'a jamais été membre);
* L'appartenance à des mouvements stylistiques (p. ex. la période durant laquelle les principes d'un mouvement stylistique sont les plus visibles et les plus courants dans les artefacts); 
* L'appartenance d'agents non humains (p. ex. un animal utilisé dans le cadre d'une recherche ne fait pas partie de l'équipe de recherche); 
* La famille d'un actant (le patron conceptuel [Appartenance familiale](/collections-model/fr/modele-cible/actuel/appartenance-familiale) doit plutôt être utilisé);
* La culture à laquelle un actant s'associe ou est associé, telle que « Étrusque »;
* L'appartenance non formalisée de l'actant à une communauté, telle que « LGBTQIA+ »; 
* L'appartenance formelle ou officielle à une nation qui est de nature juridique, telle que « Canadienne »;
* L'appartenance formelle ou officielle à une nation qui n'est pas de nature juridique, telle que « Hñähñu ». 

## Introduction et contexte

### Historique théorique {#historique-theorique}

L'appartenance à des groupes, des solidarités, des collectivités ou des organisations est une partie intrinsèque du monde social qui se trouve à l'intersection du soi et du social, car les personnes se rassemblent autour de points communs. L'appartenance opère à différentes échelles, de la cellule familiale domestique aux communautés mondiales et internationales. De telles appartenances ont été enregistrées et étudiées par les humains depuis au moins l'Antiquité, comme le démontrent les enregistrements d'accords, de pactes, de conventions et de lois (Epstein & Zalta 2018). 

Un certain nombre de types d'appartenance à un groupe sont couramment représentés dans les jeux de données des musées dans des champs dédiés (p. ex. communauté, affiliation culturelle, famille, nation, nationalité). Pourtant, l'appartenance peut être beaucoup plus variée et riche que ces champs le permettent, car la compréhension de ce concept a radicalement évolué en raison des processus de mondialisation et des changements sociétaux qui ont perturbé les liens typiques entre l'identité, la citoyenneté et le lieu en faveur d'affiliations plus flexibles à des entités sociales (Halse 2018). 

En outre, l'appartenance à une solidarité ne se limite souvent pas aux humains qui peuvent avoir des sentiments d'appartenance à un groupe envers ou englobant d'autres entités ou agents qui incluent, mais ne sont pas limités à : 

* Terre et/ou territoire; 
* Animaux domestiques et/ou sauvages; 
* Traditions et/ou récits conceptuels (Wright 2015, 392-393). 

Les éléments importants qui déterminent le fonctionnement de l'appartenance à un groupe et ce qu'elle englobe sont les suivants : 

* Le lieu et l'époque dans lesquels une personne évolue (c.-à-d. son contexte social);
* La manière dont elle s'identifie en tant que membre d'un groupe, le plus souvent par l’entremise de pratiques ou de mœurs sociales qui la lient à une solidarité ou à un espace socio-culturel particulier (c.-à-d. son rôle); 
* Les valeurs qu'elle affiche dans le contexte des frontières culturelles et géographiques (c.-à-d. sa vision du monde) (Halse 2018). 

Enfin, il est important de reconnaître que l'appartenance à un groupe fonctionne fondamentalement comme une force d'inclusion et d'exclusion. L'examen de cette question met en lumière la façon dont le statut de *non-appartenance* (c.-à-d. le fait d'être rejeté par un groupe sans en avoir jamais été membre) peut aussi être significatif en soi, car il peut être symptomatique d'une volonté individuelle ou collective (Halse 2018).

### Énoncé des besoins {#enonce-des-besoins}

L'appartenance à un groupe est souvent envisagée en termes de relations ou d'interactions avec d'autres personnes, dont la durée varie de brève à longue. Une évaluation succincte des termes relatifs à de telles relations dans les thésaurus et les dictionnaires indique qu'elles reflètent souvent un ensemble de comportements, de droits, d'obligations, de croyances et de normes liés entre eux, qui sont déterminés par la façon dont les membres se comportent les uns envers les autres, leurs intérêts mutuels ou leurs points communs, ainsi que la fonction du groupe lui-même (Art & Architecture Thesaurus 2019; Free Dictionary 2019b; 2019c; 2019a; Wikipedia 2019e; 2019a; 2019c; 2019b; 2019d). 

Une évaluation d'autres modèles patrimoniaux concernés par ces types de relations révèle qu'ils ont principalement mis l'accent sur les organisations comme principe opérationnel autour duquel documenter l'appartenance avec des concepts tels que l'[appartenance organisationnelle](https://linked.art/model/actor/#organization-membership)  ou *organization membership* (Linked.art) ou l'[affiliation et association institutionnelles](https://docs.swissartresearch.net/et/persons/#social-relations) ou *institutional affiliation and association* (Person Reference Data Model). 

Dans tous les cas, l'appartenance à un groupe a été exclusivement envisagée comme un espace d'interaction interhumaine dans lequel les personnes sont liées par des relations directes (c.-à-d. que les membres se connaissent) ou indirectes (c.-à-d. que les membres n'ont pas nécessairement d'interactions personnelles, mais fonctionnent sur la base de points communs). Ces dernières peuvent inclure des « sociétés d'étrangers » qui ont des relations dispersées dans des réseaux qui peuvent être très étendus et diversifiés et qui ne reposent pas sur le fait que les personnes « se connaissent », comme les forums, les regroupements de fans, etc. (Amin 2012, 12-13).

Cet aperçu général met en lumière la nécessité d'un modèle qui prenne en compte le rôle qu'un actant endosse en tant que membre d'un groupe et, comme indiqué précédemment, le contexte temporel dans lequel il le fait. 

## Description du patron conceptuel

Ce patron conceptuel comporte trois ensembles principaux : la description d'un groupe, l'entrée d'un actant dans un groupe et le départ d'un groupe par un actant. 

Les informations relatives à un groupe sont concentrées autour d'une instance de `E74_Groupe` pointant vers une instance de `E41_Appellation` et de `E33_Objet_linguistique` par la propriété `P1_est_identifié_par` qui rend la valeur littérale de l'[Appellation du groupe](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-du-groupe) par la propriété `P190_a_pour_contenu_symbolique`. 

Les informations relatives à l'enrôlement d'un actant dans un groupe sont axées sur une instance de `E85_Adhésion` qui fonctionne comme un nœud de jonction entre une instance de `E39_Actant` et une instance de `E74_Groupe`. L'adhésion d'un actant à un groupe est modélisée comme suit : 

* Une instance de `E39_Actant` est liée à une instance de `E85_Adhésion` par la propriété `P143_a_fait_adhérer`;
* Le moment lors duquel un actant a joint un groupe est indiqué à l'aide du patron conceptuel [Limites temporelles](/collections-model/fr/modele-cible/actuel/limites-temporelles) lié à l'instance de `E85_Adhésion` par la propriété `P4_a_pour_intervalle_temporel` avec des valeurs extraites des nœuds de saisie [Date de début de l'adhésion au groupe](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-de-ladhesion-au-groupe), [Qualifiant de la date de début de l'adhésion au groupe](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-de-ladhesion-au-groupe), [Date de fin de l'adhésion au groupe](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-de-ladhesion-au-groupe) et [Qualifiant de la date de fin de l'adhésion au groupe](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-de-ladhesion-au-groupe). L'instance de `E85_Adhésion` est également liée par la propriété `P01_a_pour_domaine` à une instance de `PC144_a_fait_adhérer_à`, qui est également liée à l'instance de `E74_Groupe` par la propriété `P02_a_pour_portée`;
* Le rôle pour lequel un actant s'est engagé comme membre est indiqué en liant l'instance de `PC144_a_fait_adhérer_à` à la valeur du [Rôle du membre du groupe](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#role-du-membre-du-groupe) (une instance de `E55_Type`) par le biais de la propriété `P144.1_sorte_de_membre`.

Les informations relatives à la dissociation d'un groupe par un actant sont concentrées autour d'une instance de `E86_Départ` qui fonctionne comme un nœud de départ entre une instance de `E39_Actant` et une instance de `E74_Groupe`. Le départ d'un groupe par un actant est modélisé comme suit : 

* Une instance de `E39_Actant` est liée à une instance de `E86_Départ` par la propriété `P145_a_dissocié`;
* Le moment lors duquel un actant a quitté un groupe est indiqué à l'aide du patron conceptuel [Limites temporelles](/collections-model/fr/modele-cible/actuel/limites-temporelles) lié à l'instance de `E86_Départ` par la propriété `P4_a_pour_intervalle_temporel` avec des valeurs extraites des nœuds de saisie [Date de début du départ du groupe](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-du-depart-du-groupe), [Qualifiant de la date de début du départ du groupe](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-du-depart-du-groupe), [Date de fin du départ du groupe](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-du-depart-du-groupe) et [Qualifiant de la date de fin du départ du groupe)(/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-du-depart-du-groupe). L'instance de `E86_Départ` est aussi liée par la propriété `P146_a_dissocié_de` à l'instance de `E74_Groupe`.

## Diagramme

<a name="059_PatronConceptuel_AppartenanceGroupe_p"></a>059_PatronConceptuel_AppartenanceGroupe_p

<div class="mxgraph" style="max-width:100%;border:1px solid #cccccc;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;target&quot;:&quot;blank&quot;,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom layers lightbox&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;xml&quot;:&quot;&lt;mxfile modified=\&quot;2023-03-15T17:12:54.079Z\&quot; host=\&quot;app.diagrams.net\&quot; agent=\&quot;5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) draw.io/20.3.0 Chrome/104.0.5112.114 Electron/20.1.3 Safari/537.36\&quot; etag=\&quot;I4quK_H0anXSu0OnLzEy\&quot; version=\&quot;20.3.0\&quot;&gt;&lt;diagram id=\&quot;1Ug6chx4mSOkaXSsk2il\&quot; name=\&quot;Page-1\&quot;&gt;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&lt;/diagram&gt;&lt;/mxfile&gt;&quot;}"></div>

## Exemples

### Exemple 1

Yousuf Karsh est un Compagnon (`P144.1_sorte_de_membre`, Rôle du membre du groupe) de l'Ordre du Canada (`P190_a_pour_contenu_symbolique`, Appellation du groupe) qui a été créé le 1er juillet 1967 (`P82a_le_début_du_début`, Date de début de la formation; `P82b_la_fin_de_la_fin`, Date de fin de la formation) par le Gouverneur Général Roland Michener (`P190_a_pour_contenu_symbolique`, Appellation de l'actant fondateur) à Ottawa (ON, Canada) (`P7_a_eu_lieu_dans`, Lieu de formation) (Hillmer 2018; Skidmore 2015). Karsh est devenu Compagnon en 1990 (`P82a_le_début_du_début`, Date de début de l'adhésion au groupe; `P82b_la_fin_de_la_fin`, Date de fin de l'adhésion au groupe). 

<div id="0001_100_group-belonging" class="example"></div>

### Exemple 2

A. J. Casson (`P190_a_pour_contenu_symbolique`, Appellation de l'actant) a rejoint en 1933 (`P82a_le_début_du_début`, Date de début de l'adhésion au groupe; `P82b_la_fin_de_la_fin`, Date de fin de l'adhésion au groupe) le Canadian Group of Painters (`P190_a_pour_contenu_symbolique`, Appellation du groupe) (Toronto Public Library 2016).

<div id="0001_113_group-belonging" class="example"></div>

## Documentation connexe

### Modèles externes {#modeles-externes}

* Linked.art : [Organization Membership](https://linked.art/model/actor/#organization-membership)
* SARI : [Group Reference Data Model – Member (Actor Relations)](https://docs.swissartresearch.net/et/group/#actor-relations)
* SARI : [Person Reference Data Model – Institutional Affiliation (Social Relations)](https://docs.swissartresearch.net/et/persons/#social-relations)
* SARI : [Person Reference Data Model – Associate (Social Relations)](https://docs.swissartresearch.net/et/persons/#social-relations)

### Nœuds de saisie {#noeuds-de-saisie}

* [Appellation du groupe](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-du-groupe) \| Liste de vérification
* [Date de début de l'adhésion au groupe](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-de-ladhesion-au-groupe) \| Liste de vérification
* [Date de début du départ du groupe](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-du-depart-du-groupe) \| Liste de vérification
* [Date de fin de l'adhésion au groupe](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-de-ladhesion-au-groupe) \| Liste de vérification
* [Date de fin du départ du groupe](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-du-depart-du-groupe) \| Liste de vérification
* [Qualifiant de la date de début de l'adhésion au groupe](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-de-ladhesion-au-groupe) \| Liste de vérification
* [Qualifiant de la date de début du départ du groupe](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-du-depart-du-groupe) \| Liste de vérification
* [Qualifiant de la date de fin de l'adhésion au groupe](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-de-ladhesion-au-groupe) \| Liste de vérification
* [Qualifiant de la date de fin du départ du groupe](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-du-depart-du-groupe) \| Liste de vérification
* [Rôle du membre du groupe](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#role-du-membre-du-groupe) \| Liste de vérification

### Entités du CIDOC CRM {#entites-du-cidoc-crm}

* `E33_Objet_linguistique` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E33)]
* `E39_Actant` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E39)]
* `E41_Appellation` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E41)]
* `E52_Intervalle_temporel` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E52)]
* `E55_Type` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E55)]
* `E74_Groupe` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E74)]
* `E85_Adhésion` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E85)]
* `E86_Départ` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E86)]
* `PC144_a_fait_adhérer_à`
* `P01_a_pour_domaine (est_le_domaine_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P01)]
* `P02_a_pour_portée (est_la_portée_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P02)]
* `P1_est_identifié_par (identifie)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P1)]
* `P4_a_pour_intervalle_temporel (est_l’intervalle_temporel_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P4)]
* `P79_a_son_début_qualifié_par` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P79)]
* `P80_a_sa_fin_qualifiée_par` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P80)]
* `P82a_le_début_du_début`
* `P82b_la_fin_de_la_fin`
* `P143_a_fait_adhérer (a_adhéré_par)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P143)]
* `P144.1_sorte_de_membre` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P144.1)]
* `P145_a_dissocié (est_dissocié_par)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P145)]
* `P146_a_dissocié_de (a_perdu_le_membre_par)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P146)]
* `P190_a_pour_contenu_symbolique` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P190)]

## Discussion

### Justification

Dans le CIDOC CRM, la propriété `P107_a_pour_membre_actuel_ou_antérieur` permet de lier directement une instance de `E39_Actant` à une instance de `E74_Groupe`. Cependant, un tel chemin empêcherait de documenter les dates d'entrée et de départ du groupe, ainsi que le rôle du membre. Pour permettre une description plus granulaire à l'aide du modèle DOPHEDA, le RCIP a décidé de mettre en application le chemin le plus long en utilisant les classes `E85_Adhésion` et `E86_Départ`. Ce chemin plus long est recommandé, car il est toujours possible de réduire la taille du modèle, alors que l'utilisation de l'option la plus courte résulterait en des données manquantes. Le chemin le plus long permet également d'enregistrer le rôle du membre avec l'utilisation de la propriété-classe `PC144_a_fait_adhérer_à`.

### Limitations

La seule façon de documenter l'évolution du rôle d'un membre est d'enregistrer un évènement de départ suivi d'un nouvel évènement d'entrée pour le nouveau rôle de l'actant. L'ajout d'instances de `E86_Départ` et de `E85_Adhésion` est problématique, car ces évènements supplémentaires ne se sont jamais réellement produits : en réalité, l'actant est resté dans le groupe et son rôle a changé.

Bien qu'il y ait un mécanisme dans ce patron conceptuel pour représenter le départ d'un groupe par un actant, il n'y a pas de modélisation pour la non-appartenance d'un actant à un groupe, qui devrait être documentée dans un patron conceptuel dédié. Ce dernier pourrait représenter l'acte de rejet comme une instance de `E5_Évènement`. Par exemple, un réfugié dont la demande est rejetée par un pays d'asile ne serait pas enregistré comme un statut de non-appartenance, mais comme une action du pays en question. Ceci n'est pas couvert par ce patron conceptuel. 

La meilleure façon d'enregistrer l'existence et l'évolution des groupes moins formalisés qui existent, mais qui n'ont pas de membres enregistrés ou qui n'ont qu'une fraction de leurs membres enregistrés sciemment et officiellement comme tels, est également un défi. Par exemple, des mouvements tels que [Black Lives Matter](https://blacklivesmatter.com/), le [Sunrise Movement](https://www.sunrisemovement.org/), le [Occupy Movement](http://occupywallst.org/) ou d'autres groupes d'activistes sont notoirement décentralisés et englobent un large éventail de personnes qui épousent leurs valeurs et s'y affilient sans être officiellement des membres ou des donateurs. Les personnes qui font partie de ces mouvements sont souvent anonymes pour des raisons personnelles ou systémiques (p. ex. Sunrise est un mouvement dirigé par des jeunes qui rend l'engagement financier et officiel plus compliqué pour les adolescents·es si ils ou elles n'ont pas le soutien de leurs parents). Les leaders peuvent être documentés, mais l'établissement de fondateurs·rices officiels·les peut dans certains cas être difficile, encore plus pour les personnes qui s'affilient à un mouvement et sont des activistes, mais n'occupent pas une position officiellement ou officieusement reconnue par rapport au mouvement. Actuellement, comme la note d'application de la classe `E74_Groupe` ne comprend que les groupes formels qui agissent collectivement, les groupes informels et les membres qui leur sont associés ne sont pas pris en compte par ce patron conceptuel, ni par le patron conceptuel [Formation et dissolution d'un groupe](/collections-model/fr/modele-cible/actuel/formation-et-dissolution-dun-groupe).

De même, la note d'application de la classe `E74_Groupe` restreint également l'appartenance du groupe à une personne ou à un groupe de personnes, ce qui limite donc la possibilité de documenter l'appartenance à des agents non humains, malgré ce que les recherches actuelles mettent en évidence (voir l'[Enjeu no 21](https://github.com/chin-rcip/collections-model/issues/21)). 

### Enjeux connexes sur GitHub

* [Enjeu n° 21 « Comment modéliser un mouvement artistique? »](https://github.com/chin-rcip/collections-model/issues/21) (en anglais)
* [Enjeu n° 36 « La dissolution d'un groupe implique-t-elle le départ de ses membres? »](https://github.com/chin-rcip/collections-model/issues/36) (en anglais)
* [Enjeu n° 66 « Proposition de création de PC11_avait_pour_participant et P11.1_dans_le_rôle_de »](https://github.com/chin-rcip/collections-model/issues/66) (en anglais)

### Cas limites

#### Exemple 1 {#cas-limites-exemple-1}

La Abitibi Power and Paper Company a été acquise par Price Brothers en 1974. Price Brothers a ensuite été fusionnée avec Stone Consolidated en 1997, qui a elle-même été fusionnée avec Bowater pour former AbitibiBowater en 2007, maintenant connue sous le nom de Resolute Forest Products (Wikipedia 2021). Dans le cas de telles fusions et acquisitions, ce qui serait considéré comme le départ d'un groupe et l'entrée dans un autre, alors que la dissolution de la société elle-même est à débattre, ne serait pas clair.

#### Exemple 2 {#cas-limites-exemple-2}

Le lauréat d'un prix peut être considéré comme faisant partie d'un groupe qui comprend toutes les personnes lauréates de ce prix spécifique, bien qu'il ne s'agisse pas d'un groupe formel. Dans ce cas, l'actant fondateur du groupe peut être considéré comme le premier bénéficiaire au même titre que l'organisme qui octroie le prix. Par exemple, les Prix littéraires du Gouverneur général ont été conçus et inaugurés en 1937 par John Buchan, 1er Baron Tweedsmuir, qui était alors le 15e Gouverneur général du Canada. Il a décerné le prix Fiction à Laura G. Salverson pour *The Dark Weaver*, le prix Poésie dramatique à E.J. Pratt pour *The Fable of the Goats* et le prix Non-Fiction à Stephen Leacock pour *My Discovery of the West* (Conseil des arts du Canada n.d.). Considérant que le groupe serait les « Récipiendaires des Prix littéraires du Gouverneur général », le ou les actants fondateurs originaux pourraient être uniquement John Buchan, 1er Baron Tweedsmuir, ou les premiers récipiendaires, arguant qu'ils ont joué un rôle concret dans la fondation du groupe.

## Bibliographie

Amin, Ash. *Land of Strangers*. Cambridge, UK-CAM : Polity, 2012.

Art & Architecture Thesaurus. 2019. « Roles ». *Art & Architecture Thesaurus Online Full Record Display*. 27 septembre 2019. [http://www.getty.edu/vow/AATFullDisplay?find=role&logic=AND&note=&english=N&prev_page=1&subjectid=300435108](http://www.getty.edu/vow/AATFullDisplay?find=role&logic=AND&note=&english=N&prev_page=1&subjectid=300435108).

Bruseker, George, et Nicola Carboni. *Digital Object Reference Data Model (SARI Documentation)*. Swiss Art Research Infrastructure, 8 décembre 2020. [https://docs.swissartresearch.net/et/do/](https://docs.swissartresearch.net/et/do/).

Conseil des arts du Canada. « Prix littéraires du Gouverneur général ». Conseil des arts du Canada. n.d. [https://conseildesarts.ca/financement/prix/prix-litteraires-du-gouverneur-general](https://conseildesarts.ca/financement/prix/prix-litteraires-du-gouverneur-general).

Conseil des arts du Canada. « Gagnants et finalistes précédents ». Prix littéraires du Gouverneur général. n.d. [https://livresgg.ca/gagnants-et-finalistes-precedents](https://livresgg.ca/gagnants-et-finalistes-precedents).

Doerr, Martin, et Christian Emil Ore, éds. *Definition of the CIDOC Conceptual Reference Model*. Documentations du CIDOC CRM, 7.0.1. Paris, FR-IDF : Conseil international des musées (ICOM), 2020. [http://www.cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.0.1_%2018-10-2020.pdf](http://www.cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.0.1_%2018-10-2020.pdf).

Epstein, Brian. « Social Ontology ». *The Stanford Encyclopedia of Philosophy*, éditée par Edward N. Zalta. Standford, US-CA : Metaphysics Research Lab, Stanford University, 2018. [https://plato.stanford.edu/archives/sum2018/entries/social-ontology/](https://plato.stanford.edu/archives/sum2018/entries/social-ontology/).

Free Dictionary. « Role ». *The Free Dictionary*. Huntington Valley, US-PA : Farlex, 2019a. [https://www.thefreedictionary.com/role](https://www.thefreedictionary.com/role).

–––. « Member ». *The Free Dictionary*. Huntington Valley, US-PA : Farlex, 2019b. [https://www.thefreedictionary.com/member](https://www.thefreedictionary.com/member).

–––. « Membership ». *The Free Dictionary*. Huntington Valley, US-PA : Farlex, 2019c. [https://www.thefreedictionary.com/membership](https://www.thefreedictionary.com/membership).

Halse, Christine. « Theories and Theorising of Belonging ». *Interrogating Belonging for Young People in Schools*, édité par Christine Halse. Intercultural Relations in Education. Londres, UK-LDN : Palgrave Macmillan, 2018. [https://doi.org/10.1007/978-3-319-75217-4_1](https://doi.org/10.1007/978-3-319-75217-4_1).

Hillmer, Norman. « Roland Michener ». *L'Encyclopédie canadienne*. Toronto, CA-ON : Historica Canada, 2018 [2008]. [https://www.thecanadianencyclopedia.ca/fr/article/michener-daniel-roland](https://www.thecanadianencyclopedia.ca/fr/article/michener-daniel-roland).

Linked.art. *Linked Art Data Model*. Linked.art, 2021. [https://linked.art/model/index.html](https://linked.art/model/index.html).

Skidmore, Colleen. « Yousuf Karsh ». *L'Encyclopédie canadienne*. Toronto, CA-ON : Historica Canada, 2015 [2010]. [https://www.thecanadianencyclopedia.ca/fr/article/karsh-yousuf](https://www.thecanadianencyclopedia.ca/fr/article/karsh-yousuf).

Toronto Public Library. « February 20: Remembering A. J. Casson and the Group of Seven ». *Toronto Public Library Snapshots in History* (blogue). 20 février 2016. [https://torontopubliclibrary.typepad.com/arts_culture/2016/02/snapshots-in-history-february-20-remembering-a-j-casson-and-the-group-of-seven.html](https://torontopubliclibrary.typepad.com/arts_culture/2016/02/snapshots-in-history-february-20-remembering-a-j-casson-and-the-group-of-seven.html).

Varley, Christopher. « Société d'art contemporain ». *L'Encyclopédie canadienne*. Toronto, CA-ON : Historica Canada, 2015 [2006]. [https://www.thecanadianencyclopedia.ca/fr/article/societe-dart-contemporain](https://www.thecanadianencyclopedia.ca/fr/article/societe-dart-contemporain).

Wikipedia. « Organizational Founder. » *Wikipedia*. San Francisco, US-CA : Wikipedia, 2019a. [https://en.wikipedia.org/w/index.php?title=Organizational_founder&oldid=906165130](https://en.wikipedia.org/w/index.php?title=Organizational_founder&oldid=906165130).

–––. « Role ». *Wikipedia*. San Francisco, US-CA : Wikipedia, 2019b. [https://en.wikipedia.org/w/index.php?title=Role&oldid=913886933](https://en.wikipedia.org/w/index.php?title=Role&oldid=913886933).

–––. « Peer Group ». *Wikipedia*. San Francisco, US-CA : Wikipedia, 2019c. [https://en.wikipedia.org/w/index.php?title=Peer_group&oldid=917584897](https://en.wikipedia.org/w/index.php?title=Peer_group&oldid=917584897).

–––. « Social Movement ». *Wikipedia*. San Francisco, US-CA : Wikipedia, 2019d. [https://en.wikipedia.org/w/index.php?title=Social_movement&oldid=917693866](https://en.wikipedia.org/w/index.php?title=Social_movement&oldid=917693866).

–––. « Organization ». *Wikipedia*. San Francisco, US-CA : Wikipedia, 2019e. [https://en.wikipedia.org/w/index.php?title=Organization&oldid=918006362](https://en.wikipedia.org/w/index.php?title=Organization&oldid=918006362).

–––. « Resolute Forest Products ». *Wikipedia*. San Francisco, US-CA : Wikipedia, 2021. [https://en.wikipedia.org/w/index.php?title=Resolute_Forest_Products&oldid=1032134351](https://en.wikipedia.org/w/index.php?title=Resolute_Forest_Products&oldid=1032134351).

Wright, Sarah. « More-Than-Human, Emergent Belongings: A Weak Theory Approach ». *Progress in Human Geography* 39, no 4 (2015) : 391-411. [https://doi.org/10.1177/0309132514537132](https://doi.org/10.1177/0309132514537132).

