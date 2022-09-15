---
layout: page
language: fr
title: Formation et dissolution d'un groupe
permalink: /fr/modele-cible/actuel/formation-et-dissolution-dun-groupe
other_link: /en/target-model/current/formation-and-dissolution-of-a-group
sidebar: mc22
date: 2022-06-30
description: La Spécification du modèle cible des actants modélise sémantiquement les actants dans un contexte patrimonial. Les patrons conceptuels les plus pertinents pour la vie des actants sont présentés avec des diagrammes et des exemples qui les illustrent, ainsi qu'un compte rendu et une explication des décisions pertinentes qui ont été prises lors de l'élaboration desdits patrons conceptuels. Il s'agit d'une documentation théorique qui n'a jamais été testée ou mise en application.
---

## Aperçu {#apercu}

Ce patron conceptuel peut être utilisé pour représenter les informations relatives au début et à la fin d'un groupe de personnes (formation et dissolution). Il comprend : 

* La date et le lieu de la formation d'un groupe (son début);
* Les actants principalement responsables de la formation d'un groupe; 
* La date et le lieu de la dissolution d'un groupe (sa fin); 
* Les actants principalement responsables de la fin d'un groupe.

Il porte spécifiquement sur les informations vitales des groupes et non sur leur nature, leurs réseaux ou les informations vitales des personnes qui les composent (p. ex. la date de naissance de l'actant fondateur, le statut juridique autorisant la création d'un groupe, etc.). En tant que tel, il ne comprend pas : 

* La formation ou la dissolution de groupes d'objets (tels que les collections);
* La nature d'un groupe;
* L'appartenance d'un membre à un groupe (le patron conceptuel [Appartenance à un groupe](/collections-model/fr/modele-cible/actuel/appartenance-a-un-groupe) doit plutôt être utilisé);
* Le nom, la date et le lieu de naissance ou de mort des membres d'un groupe (les patrons conceptuels [Identifiants et appellations de l'actant](/collections-model/fr/modele-cible/actuel/identifiants-et-appellations-de-lactant) et [Naissance et mort d'une personne](/collections-model/fr/modele-cible/actuel/naissance-et-mort-dune-personne) doivent plutôt être utilisés);
* Les relations entre les membres d'un groupe, ou entre un groupe et d'autres groupes de personnes (le patron conceptuel [Relation](/collections-model/fr/modele-cible/actuel/relation) devrait plutôt être utilisé);
* Les rôles endossés par les membres d'un groupe, à l'exception des rôles de formation et de dissolution qui sont pris en compte par ce patron conceptuel;
* La cause de la formation ou de la dissolution d'un groupe.

## Introduction et contexte

### Historique théorique {#historique-theorique}

L'enregistrement des informations relatives à la formation et à la dissolution des groupes est une partie statistiquement et culturellement importante de la recherche patrimoniale et repose sur l'auto-identification des groupes ou leur identification ultérieure par des spécialistes. En tant que telles, ces informations sont souvent utilisées pour situer les actants dans des tendances sociétales plus larges, ce qui constitue un élément clé de la recherche historique (Yntema 2009, 145; Brumberg et al. 2012, 407). 

Ces informations sont non seulement significatives, mais également cruciales pour la désambiguïsation des actants (c.-à-d. que deux groupes différents peuvent avoir le même nom par hasard, ou un seul groupe peut être associé à plusieurs noms ou orthographes d'un nom), car elles peuvent être utilisées pour confirmer l'identité d'un groupe (OCLC 2019, 4). 

Les données sur la formation et la dissolution des groupes, cependant, risquent d'être très floues et nécessitent des évaluations spécialisées qui peuvent être très différentes pour déterminer de qui est constitué un groupe, quand il a été formé et dissous, et qui a joué un rôle dans sa formation et sa dissolution, ou même si un évènement de formation ou de dissolution a eu lieu. Elles reposent sur la perception du spécialiste en la matière ou des membres eux-mêmes comme ayant une cohésion et une unité en tant que groupe qui est distincte de celle des personnes qui le composent (Lickel et al. 2000, 223). 

### Énoncé des besoins {#enonce-des-besoins}

Comme les informations sur la formation et la dissolution d'un groupe sont couramment utilisées par les institutions patrimoniales et servent à des fins de désambiguïsation, elles sont probablement parmi les plus largement documentées. Cela signifie que ces données vitales seront vraisemblablement parmi les plus susceptibles d'être échangées et mobilisées par plusieurs soumissionnaires. L'interopérabilité avec d'autres modèles pertinents est donc importante pour le développement de ces patrons conceptuels. Il est donc nécessaire de déterminer quand, où et par qui un groupe a été formé ou dissous.

## Description du patron conceptuel

La formation d'un groupe est modélisée comme suit : 

* Une instance de `E74_Groupe` est liée à une instance de `E66_Formation` par la propriété `P95_a_fondé`. L'instance de `E66_Formation` est liée au fondateur du groupe (une instance de `E39_Actant`) par la propriété `P14_a_été_effectué_par`, qui est liée à une instance de `E41_Appellation` et de `E33_Objet_linguistique` par la propriété `P1_est_identifié_par`. Cette instance est ensuite liée à la valeur littérale de l'[Appellation de l'actant fondateur](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-de-lactant-fondateur) par la propriété `P190_a_pour_contenu_symbolique`;
* Le lieu où s'est déroulée la formation est indiqué en liant l'instance de `E66_Formation` à la valeur du [Lieu de formation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#lieu-de-formation) (une instance de `E53_Lieu`) mobilisée par la propriété `P7_a_eu_lieu_dans`;
* Le moment lors duquel la formation s'est produite est indiqué en utilisant le patron conceptuel [Limites temporelles](/collections-model/fr/modele-cible/actuel/limites-temporelles) lié à l'instance de `E66_Formation` par la propriété `P4_a_pour_intervalle_temporel` avec des valeurs extraites des nœuds de saisie [Date de début de la formation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-de-la-formation), [Qualifiant de la date de début de la formation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-de-la-formation), [Date de fin de la formation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-de-la-formation) et [Qualifiant de la date de fin de la formation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-de-la-formation). 

La dissolution d'un groupe est modélisée comme suit : 

* Une instance de `E74_Groupe` est liée à une instance de `E68_Dissolution` par la propriété `P99_a_dissous`. L'instance de `E68_Dissolution` est liée à l'actant du groupe responsable de la dissolution (une instance de `E39_Actant`) par la propriété `P14_a_été_effectué_par`, qui est liée à une instance de `E41_Appellation` et de `E33_Objet_linguistique` par la propriété `P1_est_identifié_par`. À partir de cette instance, la valeur littérale de l'[Appellation de l'actant effectuant la dissolution](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-de-lactant-effectuant-la-dissolution) est qualifiée par la propriété `P190_a_pour_contenu_symbolique`;
* Le lieu où s'est produite la dissolution est indiqué en liant l'instance de `E68_Dissolution` à la valeur du [Lieu de dissolution](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#lieu-de-dissolution) (une instance de `E53_Lieu`) par la propriété `P7_a_eu_lieu_dans`;
* Le moment lors duquel la dissolution a eu lieu est indiqué à l'aide du patron conceptuel [Limites temporelles](/collections-model/fr/modele-cible/actuel/limites-temporelles) lié à l'instance de `E68_Dissolution` par la propriété `P4_a_pour_intervalle_temporel` avec des valeurs extraites des nœuds de saisie [Date de début de la dissolution](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-de-la-dissolution), [Qualifiant de la date de début de la dissolution](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-de-la-dissolution), [Date de fin de la dissolution](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-de-la-dissolution) et [Qualifiant de la date de fin de la dissolution](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-de-la-dissolution). 

## Diagramme

<a name="042_PatronConceptuel_FormationEtDissolution_p"></a>042_PatronConceptuel_FormationEtDissolution_p

<iframe frameborder="0" style="width:100%;height:500px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=042_PatronConceptuel_FormationEtDissolution_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D14FQ5FXqGumVlD8VPia_G-AS48KOvvLlC%26export%3Ddownload"></iframe>

## Exemples

### Exemple 1

Yousuf Karsh est un Compagnon de l'Ordre du Canada (`P190_a_pour_contenu_symbolique`, Appellation de l'actant) qui a été créé le 1er juillet 1967 (`P82a_le_début_du_début`, Date de début de la formation; `P82b_la_fin_de_la_fin`, Date de fin de la formation) par le gouverneur général Roland Michener (`P190_a_pour_contenu_symbolique`, Appellation de l'actant fondateur) à Ottawa (ON, Canada) (`P7_a_eu_lieu_dans`, Lieu de formation) (Hillmer 2018; Skidmore 2015).

<div id="0001_110_formation" class="example"></div>

### Exemple 2

Le Canadian Group of Painters (`P190_a_pour_contenu_symbolique`, Appellation de l'actant) a été formé à Toronto (ON, Canada) (`P7_a_eu_lieu_dans`, Lieu de formation) en 1933 (`P82a_le_début_du_début`, Date de début de la formation; `P82b_la_fin_de_la_fin`, Date de fin de la formation) par 28 artistes canadiens, dont A. J. Casson (`P190_a_pour_contenu_symbolique`, Appellation de l’actant fondateur) (représenté seul dans l'exemple suivant pour des raisons de simplicité). Le groupe a été dissous en 1969 (`P82a_le_début_du_début`, Date de début de la dissolution; `P82b_la_fin_de_la_fin`, Date de fin de la dissolution) à un endroit inconnu par un actant inconnu (Toronto Public Library 2016).

<div id="0001_112_formation-dissolution" class="example"></div>

## Documentation connexe

### Modèles externes {#modeles-externes}

* Linked.art : [Birth and Death/Formation and Dissolution](https://linked.art/model/actor/#birth-and-death-formation-and-dissolution)
* SARI : [Group Reference Data Model – Existence](https://docs.swissartresearch.net/et/group/#existence)

### Nœuds de saisie {#noeuds-de-saisie}

* [Appellation de l'actant effectuant la dissolution](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-de-lactant-effectuant-la-dissolution) \| Liste de vérification
* [Appellation de l'actant fondateur](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-de-lactant-fondateur) \| Liste de vérification
* [Date de début de la formation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-de-la-formation) \| Liste de vérification
* [Date de début de la dissolution](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-de-la-dissolution) \| Liste de vérification
* [Date de fin de la formation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-de-la-formation) \| Liste de vérification
* [Date de fin de la dissolution](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-de-la-dissolution) \| Liste de vérification
* [Lieu de dissolution](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#lieu-de-dissolution) \| Liste de vérification
* [Lieu de formation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#lieu-de-formation) \| Liste de vérification
* [Qualifiant de la date de début de la dissolution](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-de-la-dissolution) \| Liste de vérification
* [Qualifiant de la date de début de la formation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-de-la-formation) \| Liste de vérification
* [Qualifiant de la date de fin de la dissolution](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-de-la-dissolution) \| Liste de vérification
* [Qualifiant de la date de fin de la formation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-de-la-formation) \| Liste de vérification

### Entités du CIDOC CRM {#entites-du-cidoc-crm}

* `E9_Déplacement` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E9)]
* `E39_Actant` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E39)]
* `E41_Appellation` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E41)]
* `E52_Intervalle_temporel` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E52)]
* `E53_Lieu` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E53)]
* `E66_Formation` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E66)]
* `E68_Dissolution` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E68)]
* `E74_Groupe` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E74)]
* `P1_est_identifié_par (identifie)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P1)]
* `P4_a_pour_intervalle_temporel (est_l’intervalle_temporel_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P4)]
* `P7_a_eu_lieu_dans (a_été_témoin_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P7)]
* `P14_a_été_effectué_par (a_effectué)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P14)]

`P79_a_son_début_qualifié_par` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P79)]

* `P80_a_sa_fin_qualifiée_par` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P80)]
* `P82a_le_début_du_début`
* `P82b_la_fin_de_la_fin`
* `P95_a_fondé (a_été_fondé_par)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P95)]
* `P99_a_dissous (a_été_dissous_par)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P99)]
* `P190_a_pour_contenu_symbolique` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P190)]

## Discussion

### Justification

Il existe une différence substantielle entre l'appartenance à un groupe et le fait de fonder ou de provoquer la dissolution de ce groupe. C'est pourquoi les informations relatives aux actants effectuant la formation ou la dissolution sont intégrées dans ce patron conceptuel plutôt que dans le patron conceptuel [Appartenance à un groupe](/collections-model/fr/modele-cible/actuel/appartenance-a-un-groupe). Par conséquent, seules les instances fondatrices et/ou de dissolution de `E39_Actant` doivent être représentées dans ce patron conceptuel, sachant que, parfois, les actants fondateurs peuvent ne pas être des membres actifs d'un groupe.

De plus, ce qui est considéré comme un groupe et qui doit être enregistré comme tel peut faire l'objet d'un débat (voir la section [Différences entre `E39_Actant`, `E21_Personne` et `E74_Groupe`](/collections-model/fr/modele-cible/actuel/concepts-generaux#differences-entre-e39_actant-e21_personne-et-e74_groupe)). Ce patron conceptuel concerne exclusivement les groupes de personnes et ne s'applique pas aux groupes d'objets tels que les collections ou autres fonds patrimoniaux. Cependant, il peut être difficile de déterminer si certains groupements doivent être cartographiés à l'aide de ce patron conceptuel. Par exemple, un mouvement artistique peut être considéré comme un groupe et modélisé comme tel, mais il peut aussi être considéré comme une interprétation d'un ensemble d'œuvres réalisées par des spécialistes (voir l'[Enjeu no 21](https://github.com/chin-rcip/collections-model/issues/21)). 

À l'heure actuelle, même lorsqu'un groupe peut être facilement identifié comme tel, par exemple dans le cas de l'Ordre du Canada, il demeure non déterminé, que ses membres quittent le groupe lors de sa dissolution ou qu'ils demeurent membres de ce groupe (voir l'[Enjeu no 36](https://github.com/chin-rcip/collections-model/issues/36)). 

### Limitations

La meilleure façon d'enregistrer l'existence et l'évolution des groupes moins formalisés qui existent, mais qui n'ont pas de membres enregistrés ou qui n'ont qu'une fraction de leurs membres enregistrés sciemment et officiellement comme tels, est également un défi. Par exemple, des mouvements tels que [Black Lives Matter](https://blacklivesmatter.com/), le [Sunrise Movement](https://www.sunrisemovement.org/), le [Occupy Movement](http://occupywallst.org/) ou d'autres groupes d'activistes sont notoirement décentralisés et englobent un large éventail de personnes qui épousent leurs valeurs et s'y affilient sans être officiellement des membres ou des donateurs. Les personnes qui font partie de ces mouvements sont souvent anonymes pour des raisons personnelles ou systémiques (p. ex. Sunrise est un mouvement dirigé par des jeunes qui rend l'engagement financier et officiel plus compliqué pour les adolescents·es si ils ou elles n'ont pas le soutien de leurs parents). Les leaders peuvent être documentés, mais l'établissement de fondateurs·rices officiels·les peut dans certains cas être difficile, encore plus pour les personnes qui s'affilient à un mouvement et sont des activistes, mais n'occupent pas une position officiellement ou officieusement reconnue par le mouvement. Actuellement, comme la note d'application de la classe `E74_Groupe` ne comprend que les groupes formels qui agissent collectivement, les groupes informels et les membres qui leur sont associés ne sont pas pris en compte par ce patron conceptuel, ni par le patron conceptuel [Appartenance à un groupe](/collections-model/fr/modele-cible/actuel/appartenance-a-un-groupe). 

### Enjeux connexes sur GitHub

* [Enjeu n° 11 : « Les années scolaires doivent-elles être modélisées comme étant un membre d'un groupe? En serait-il de même pour les professeurs·es? »](https://github.com/chin-rcip/collections-model/issues/11) (en anglais)
* [Enjeu n° 21 « Comment modéliser un mouvement artistique? »](https://github.com/chin-rcip/collections-model/issues/21) (en anglais)
* [Enjeu n° 36 « La dissolution d'un groupe implique-t-elle le départ de ses membres? »](https://github.com/chin-rcip/collections-model/issues/36) (en anglais)

### Cas limites

#### Exemple 1 {#cas-limites-exemple-1}

En 2008 (Date de début de la formation; Date de fin de la formation), l'épouse de Yousuf Karsh, Estrellita Karsh (Appellation de l'actant fondateur), a doté le poste de conservateur adjoint des photographies Estrellita et Yousuf Karsh (Appellation de l'actant) au Musée des beaux-arts (Appellation de l'actant fondateur) de Boston (MA, États-Unis) (Lieu de formation). Les conservateurs·rices qui ont endossé cette position ont formé un groupe du nom de « Estrellita and Yousuf Karsh Assistant Curator of Photographs », qui est également une occupation qu'ils et elles ont exercée (il serait possible d'utiliser le patron conceptuel Occupation, mais le groupe n'aurait jamais été « créé »). La dotation est en continu et, à ce titre, le groupe reste actif (Succession de Yousuf Karsh 2021). Pourtant, une question importante demeure : les membres du groupe (c.-à-d. les conservateurs·rices) peuvent-ils agir collectivement (et donc se qualifier en tant que groupe) même si un seul d'entre eux porte le titre à la fois? Dans ce contexte, la manière de traiter le groupe reste incertaine. 

#### Exemple 2 {#cas-limites-exemple-2}

La Abitibi Power and Paper Company a été acquise par Price Brothers en 1974. Price Brothers a ensuite été fusionnée avec Stone Consolidated en 1997, qui a elle-même été fusionnée avec Bowater pour former AbitibiBowater en 2007, maintenant connue sous le nom de Resolute Forest Products (Wikipedia 2021). Dans le cas de telles fusions et acquisitions, ce qui serait considéré comme la dissolution de la compagnie n'est pas clair.

#### Exemple 3 {#cas-limites-exemple-3}

Un groupe peut ne pas avoir qu'un seul Lieu de formation, car ses membres peuvent considérer faire partie d'un collectif sans partager un espace commun. De plus, lorsqu'un évènement se déroule en ligne ou dans un univers virtuel, il peut devenir difficile de déterminer son emplacement physique. Par exemple, un artiste pourrait fonder un groupe uniquement en ligne à partir d'un ordinateur situé à Winnipeg (MB, Canada), tout en utilisant une plateforme de rassemblement accessible sur un serveur Web qui pourrait également être considéré comme le lieu de formation du groupe. L'emplacement de chaque membre peut également poser problème (p. ex. l'emplacement physique de chaque personne jouant à un jeu en ligne).

## Bibliographie

Black Lives Matter. *Black Lives Matter*. Black Lives Matter, 28 juin 2021. [https://blacklivesmatter.com/](https://blacklivesmatter.com/).

Brumberg, H. L., D. Dozor, et S. G. Golombek. « History of the Birth Certificate: From Inception to the Future of Electronic Data ». *Journal of Perinatology* 32, no. 6 (2012) : 407-411. [https://doi.org/10.1038/jp.2012.3](https://doi.org/10.1038/jp.2012.3).

Doerr, Martin, et Christian Emil Ore, éds. *Definition of the CIDOC Conceptual Reference Model*. Documentations du CIDOC CRM, 7.0.1. Paris, FR-IDF : Conseil international des musées (ICOM), 2020. [http://www.cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.0.1_%2018-10-2020.pdf](http://www.cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.0.1_%2018-10-2020.pdf).

Éditeurs de la Encyclopædia Britannica. « Yousuf Karsh ». *Encyclopædia Britannica*. Londres, UK-LDN : Encyclopædia Britannica, n.d. [https://www.britannica.com/biography/Yousuf-Karsh](https://www.britannica.com/biography/Yousuf-Karsh).

Hillmer, Norman. « Roland Michener ». *L'Encyclopédie canadienne*. Toronto, CA-ON : Historica Canada, 2018 [2008]. [https://www.thecanadianencyclopedia.ca/fr/article/michener-daniel-roland](https://www.thecanadianencyclopedia.ca/fr/article/michener-daniel-roland).

Lickel, B., D. Hamilton, G. Wieczorkowska, A. Lewis, S. Sherman, et A. N. Uhles. « Varieties of Groups and the Perception of Group Entitativity ». *Journal of Personality and Social Psychology* 78, no. 2 (2000) : 223-246. [https://doi.org/10.1037/0022-3514.78.2.223](https://doi.org/10.1037/0022-3514.78.2.223).

Linked.art. *Linked Art Data Model*. Linked.art, 2021. [https://linked.art/model/index.html](https://linked.art/model/index.html).

OCLC. *Virtual International Authority File Guidelines*. Dublin, US-OH : OCLC, 2019 [2015]. [https://www.oclc.org/content/dam/oclc/viaf/VIAF%20Guidelines.pdf](https://www.oclc.org/content/dam/oclc/viaf/VIAF%20Guidelines.pdf).

Skidmore, Colleen. « Yousuf Karsh ». *L'Encyclopédie canadienne*. Toronto, CA-ON : Historica Canada, 2015 [2010]. [https://www.thecanadianencyclopedia.ca/fr/article/karsh-yousuf](https://www.thecanadianencyclopedia.ca/fr/article/karsh-yousuf).

Succession de Yousuf Karsh. *Yousuf Karsh*. Yousuf Karsh, 2021. [https://karsh.org/](https://karsh.org/).

Sunrise Movement. *Sunrise Movement - We Are The Climate Revolution*. Sunrise Movement, 28 juin 2021. [https://www.sunrisemovement.org/](https://www.sunrisemovement.org/).

Toronto Public Library. « February 20: Remembering A. J. Casson and the Group of Seven ». *Toronto Public Library Snapshots in History* (blogue). 20 février 2016. [https://torontopubliclibrary.typepad.com/arts_culture/2016/02/snapshots-in-history-february-20-remembering-a-j-casson-and-the-group-of-seven.html](https://torontopubliclibrary.typepad.com/arts_culture/2016/02/snapshots-in-history-february-20-remembering-a-j-casson-and-the-group-of-seven.html).

Wikipedia. « Resolute Forest Products ». *Wikipedia*. San Francisco, US-CA : Wikipedia, 2021. [https://en.wikipedia.org/w/index.php?title=Resolute_Forest_Products&oldid=1032134351](https://en.wikipedia.org/w/index.php?title=Resolute_Forest_Products&oldid=1032134351).

Yntema, Douwe. « Material Culture and Plural Identity in Early Roman Southern Italy ». *Ethnic Constructs in Antiquity: The Role of Power and Tradition*, édité par Ton Derks et Nico Roymans. Amsterdam Archæological Studies 13. Amsterdam, NL : Amsterdam University Press, 2009 : 145-166. [https://www.jstor.org/stable/j.ctt46n1n2.9](https://www.jstor.org/stable/j.ctt46n1n2.9).

