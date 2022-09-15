---
layout: page
language: fr
title: Évènement de séjour
permalink: /fr/modele-cible/actuel/evenement-de-sejour
other_link: /en/target-model/current/staying-event
sidebar: mc22
date: 2022-06-30
description: La Spécification du modèle cible des actants modélise sémantiquement les actants dans un contexte patrimonial. Les patrons conceptuels les plus pertinents pour la vie des actants sont présentés avec des diagrammes et des exemples qui les illustrent, ainsi qu'un compte rendu et une explication des décisions pertinentes qui ont été prises lors de l'élaboration desdits patrons conceptuels. Il s'agit d'une documentation théorique qui n'a jamais été testée ou mise en application.
---

## Aperçu {#apercu}

Ce patron conceptuel peut être utilisé pour représenter les informations relatives à la présence physique d'un ou de plusieurs actants quelque part pour une durée prolongée ou temporaire, y compris dans leur résidence/emplacement géographique habituel. Il comprend : 

* Le lieu géographique où un actant a séjourné;
* Le temps durant lequel un actant a séjourné dans le lieu géographique;
* L'appellation ou les appellations qu'un actant a utilisées lors de son séjour dans le lieu géographique;
* Dans le cas des groupes, l'évènement de séjour peut être défini comme le siège ou le quartier général.

Ce patron conceptuel ne doit pas être utilisé pour représenter :

* Le lieu géographique et les dates de l'occupation d'un actant (le patron conceptuel [Occupation](/collections-model/fr/modele-cible/actuel/occupation) doit plutôt être utilisé);
* Le lieu géographique et les dates du « floruit » d'un actant (le patron conceptuel [Floruit](/collections-model/fr/modele-cible/actuel/floruit) doit plutôt être utilisé);
* Le lieu géographique et les dates du statut social d'un actant (le patron conceptuel [Statut social](/collections-model/fr/modele-cible/actuel/statut-social) doit plutôt être utilisé);
* Le lieu de sépulture d'un actant (le patron conceptuel [Naissance et mort d'une personne](/collections-model/fr/modele-cible/actuel/naissance-et-mort-dune-personne) doit plutôt être utilisé).

## Introduction et contexte

### Historique théorique {#historique-theorique}

Les personnes, individuellement ou en groupe, se déplacent dans l'espace principalement pour des activités professionnelles, de loisirs ou éducatives et parfois par nécessité (p. ex. en cas de guerre), et les entreprises peuvent s'étendre ou se déplacer dans l'espace en acquérant de nouveaux biens immobiliers. Connaître l'emplacement d'un actant à un moment précis permet de mieux comprendre l'histoire de sa vie et les cultures qu'il a côtoyées. À plus grande échelle, le lieu permet d'identifier les enjeux, notamment politiques, tels que la colonisation et la déportation, auxquels il a pu être confronté et qui contribuent à la compréhension des flux migratoires.

En suivant les lieux visités par les actants, il est possible d'étudier les phénomènes de mondialisation et de comprendre comment chaque juridiction géographique y contribue positivement et négativement (p. ex. partage d'expertise, offre de stages, ouverture de nouveaux marchés, tourisme, fermeture de frontières, embargos, alliances, etc.). La mondialisation « n'est pas une force omnipotente et unidirectionnelle nivelant tout sur son passage » (Éditeurs de la Encyclopædia Britannica n.d.; notre traduction), son analyse passe inévitablement par les aspects particuliers de la vie qui sont affectés par ce processus. Par conséquent, les raisons qui poussent un actant à se déplacer ou à demeurer au même endroit sont multiples et rarement attribuables à un seul enjeu.

### Énoncé des besoins {#enonce-des-besoins}

Tout au long de sa vie ou de ses activités, un actant peut voyager, vivre ou être présent dans divers lieux. Ces informations peuvent être enregistrées, car elles fournissent des connaissances sur le contexte culturel dans lequel l'actant a évolué. Le fait de séjourner à un certain lieu et pendant une certaine période de temps peut ne pas être directement lié à une activité ou à un évènement spécifique, comme une occupation (y compris les activités professionnelles et récréatives), mais le fait de documenter les activités de séjour d'un actant fournit une chronologie continue de l'histoire de sa vie. En tant que telles, les informations relatives à ce type d'activité doivent être modélisées dans un patron conceptuel dédié.

Un autre élément lié au lieu géographique de la présence physique de l'actant est l'appellation de l'actant, qui est utilisée pour indiquer la ou les appellations utilisées à cet endroit, surtout dans le cas des groupes (voir le patron conceptuel [Identifiants et appellations de l'actant](/collections-model/fr/modele-cible/actuel/identifiants-et-appellations-de-lactant)). Par exemple, une compagnie pourrait avoir utilisé deux noms enregistrés différents associés à deux adresses différentes. L'un d'eux pourrait être le lieu utilisé pour l'activité du siège de la compagnie. 

## Description du patron conceptuel 

Pour chaque séjour, une instance de `E39_Actant` est d'abord liée par la propriété `P14_a_été_effectué_par` à une instance de `E7_Activité`, qui est ensuite qualifiée par une instance de `E55_Type` (un nœud doté d’un qualifiant spécifié) portant le libellé « Séjour » par la propriété `P2_a_pour_type`.

La durée du séjour est rendue à l'aide du patron conceptuel [Limites temporelles](/collections-model/fr/modele-cible/actuel/limites-temporelles) lié à l'instance de `E7_Activité` par la propriété `P4_a_pour_intervalle_temporel` avec des valeurs extraites des nœuds de saisie [Date de début du séjour](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-du-sejour), [Qualifiant de la date de début du séjour](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-du-sejour), [Date de fin du séjour](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-du-sejour) et [Qualifiant de la date de fin du séjour](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-du-sejour).

De plus, l'instance de `E7_Activité` est liée :

* Au [Lieu du séjour](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#lieu-du-sejour) (une instance de `E53_Lieu`) par la propriété `P7_a_eu_lieu_dans` ;
* À la valeur du [Type de séjour](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#type-de-sejour) (une instance de `E55_Type`) par la propriété `P21_a_eu_pour_finalité_générale`;
* Une instance de `E41_Appellation` et de `E33_Objet_linguistique` par la propriété `P16_a_mobilisé_l’objet_spécifique`, qui est liée à la valeur littérale de l'[Appellation utilisée du séjour](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-utilisee-du-sejour) par la propriété `P190_a_pour_contenu_symbolique`.

## Diagramme

<a name="052_PatronConceptuel_Sejour_p"></a>052_PatronConceptuel_Sejour_p

<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=052_PatronConceptuel_Sejour_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1HkLZI2Tw6ABDL1VLyo1kQe3ZXt0fyRKQ%26export%3Ddownload"></iframe>

## Exemples

### Exemple 1

Dès son arrivée au Canada le 31 décembre 1924 (`P82a_le_début_du_début`, Date de début du séjour « 1924-12-31T00:00:00 »), Yousuf Karsh déménage à Sherbrooke, CA-QC (`P7_a_eu_lieu_dans`, Lieu du séjour) pour vivre avec son oncle maternel George Nakash jusqu'en 1928 (`P82b_la_fin_de_la_fin`, Date de fin du séjour « 1928-12-31T23:59:59 ») avant de partir pour Boston, USA-MA (`P7_a_eu_lieu_dans`, Lieu du séjour). Il y est resté jusqu'en 1931 (`P82a_le_début_du_début`, Date de début du séjour « 1928-01-01T00:00:00 »; `P82b_la_fin_de_la_fin`, Date de fin du séjour « 1931-12-31T23:59:59 ») (Karsh, n.d.).

<div id="0001_100_staying-event" class="example"></div>

### Exemple 2

L'Académie royale des arts du Canada (Appellation utilisée du séjour), une organisation dont Yousuf Karsh était membre académicien, a déménagé son siège social (`P21_a_eu_pour_finalité_générale`, Type de séjour) au 50, promenade Sussex, Ottawa, ON K1M 2K1 (`P7_a_eu_lieu_dans`, Lieu du séjour) le 1er septembre 2020 (`P82a_le_début_du_début`, Date de début du séjour) (The Royal Canadian Academy of Arts 2020).

<div id="0001_119_staying-event" class="example"></div>

## Documentation connexe

### Modèles externes {#modeles-externes}

* Linked.art : [Actors: People and Organizations – Addresses](https://linked.art/model/actor/#addresses)

### Nœuds de saisie {#noeuds-de-saisie}

* [Date de début du séjour](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-du-sejour) \| Liste de vérification
* [Qualifiant de la date de début du séjour](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-du-sejour) \| Liste de vérification
* [Date de fin du séjour](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-du-sejour) \| Liste de vérification
* [Qualifiant de la date de fin du séjour](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-du-sejour) \| Liste de vérification
* [Lieu du séjour](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#lieu-du-sejour) \| Liste de vérification
* [Type de séjour](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#type-de-sejour) \| Liste de vérification
* [Appellation utilisée du séjour](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-utilisee-du-sejour) \| Liste de vérification

### Entités du CIDOC CRM {#entites-du-cidoc-crm}

* `E7_Activité` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E7)]
* `E33_Objet_linguistique` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E33)]
* `E39_Actant` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E39)]
* `E41_Appellation` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E41)]
* `E52_Intervalle_temporel` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E52)]
* `E53_Lieu` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E53)]
* `E55_Type` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E55)]
* `P1_est_identifié_par (identifie)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P1)]
* `P2_a_pour_type (est_le_type_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P2)]
* `P4_a_pour_intervalle_temporel (est_l’intervalle_temporel_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P4)]
* `P7_a_eu_lieu_dans (a_été_témoin_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P7)]
* `P14_a_été_effectué_par (a_effectué)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P14)]
* `P16_a_mobilisé_l’objet_spécifique (a_été_mobilisé_pour)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P16)]
* `P21_a_eu_pour_finalité_générale (a_été_la_finalité_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P21)]
* `P79_a_son_début_qualifié_par` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P79)]
* `P80_a_sa_fin_qualifiée_par` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P80)]
* `P82a_le_début_du_début`
* `P82b_la_fin_de_la_fin`
* `P190_a_pour_contenu_symbolique` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P190)]

## Discussion

### Justification

Dans le CIDOC CRM, il existe deux façons de documenter l'emplacement d'un objet physique :

* La première consiste à lier un objet physique directement à une instance de `E53_Lieu` par le biais des propriétés `P53_a_pour_localisation_actuelle_ou_antérieure`, `P54_a_actuellement_pour_localisation_fixe` ou `P55_a_actuellement_pour_localisation`. Ces propriétés permettent uniquement de documenter les limites temporelles de l'emplacement actuel;
* La deuxième option est de documenter l'action de mouvement à travers la classe `E9_Déplacement`, parce que le CIDOC CRM ne documente pas les états, mais seulement l'action définie de déplacer un objet d'un endroit à un autre. Dans cette option, le changement d'emplacement peut être daté. Cependant, les institutions patrimoniales n'enregistrent généralement pas les déplacements des actants, ce qui complexifie la cartographie de ces données.

Ces deux options ne sont applicables qu'aux objets physiques qui sont des instances de `E21_Personne` et non des instances de `E74_Groupe`. Selon le CIDOC CRM, les groupes ne se déplacent pas; seuls leurs membres ont la capacité de le faire. Par exemple, les Beatles en tant que groupe ne peuvent pas être présents lors d'un concert à Londres, seuls les quatre membres peuvent être documentés comme y étant présents.

L'emplacement d'un groupe peut être déduit de l’emplacement de ses membres au cours de la même période de temps. Cependant, cela pourrait être inexact, car un groupe peut être considéré comme étant quelque part même si tous les membres n'y sont pas présents.

Pour les groupes qui possèdent des biens immobiliers, leur emplacement peut être indiqué en utilisant la classe `E8_Acquisition` pour enregistrer leurs transferts de titres qui peuvent ensuite être datés et localisés géographiquement. Cela permet de retracer les bâtiments occupés par un groupe et de les situer sur une carte. Néanmoins, ce schéma ne peut être appliqué qu'aux cas où le groupe était/est effectivement le propriétaire légal de ces biens immobiliers. En tant que tel, le patron conceptuel ne peut pas être utilisé pour les cas où il n'y a pas de propriété ou dont la propriété est incertaine. La plupart du temps, à moins qu'il ne s'agisse de l'élément principal de la documentation des soumissionnaires de données, ces informations ne sont pas enregistrées.

Par conséquent, dans un souci de simplicité et de précision, les options ci-dessus ne sont pas mises en application dans le modèle DOPHEDA. L'utilisation de la classe `E7_Activité` pour rendre l'action d'être quelque part, appelée Évènement de séjour, a été adoptée, car elle peut rendre compte de l’emplacement de toutes sortes d'actants. 

Certains groupes utilisent un lieu dans le but précis d'en faire leur siège. Le terme « siège » désigne le type d'autorité à partir duquel les ordres sont émis plutôt que de faire référence à un emplacement physique (Free Dictionary 2020). Ainsi, plutôt que la propriété `P2_a_pour_type`, la propriété `P21_a_eu_pour_finalité_générale` est employée, car elle permet d'identifier les buts et les objectifs de l'activité au lieu de la catégoriser. 

En outre, l'appellation spécifique d'un actant est parfois utilisée à un emplacement précis. Pour indiquer cet emplacement précis, il est possible de construire une requête pour inférer le lieu en trouvant le temps de chevauchement entre une activité d'utilisation du nom et une ou plusieurs activités de séjour en utilisant le nœud de saisie [Lieu du séjour](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#lieu-du-sejour). Toutefois, cela ne peut fonctionner que si l'on part de l'hypothèse erronée que les données temporelles sont toujours enregistrées et disponibles. De plus, si un actant porte deux noms différents au même moment, il serait impossible d'utiliser un algorithme pour déterminer lequel a été utilisé à quel emplacement. Ainsi, la modélisation du lien entre l'appellation et son emplacement est considérée comme une meilleure solution. Deux options apparaissent :

* La propriété `P16_a_mobilisé_l’objet_spécifique (a_été_mobilisé_pour)` est utilisée pour relier l'appellation et l'activité de séjour, à partir de laquelle les informations sur le lieu sont rendues en utilisant la propriété `P7_a_eu_lieu_dans`. Cela signifie que lors de son séjour dans ce lieu, l'actant a utilisé cette appellation;
* La propriété `P7_a_eu_lieu_dans` est utilisée pour lier directement l'activité d'utilisation de l'appellation au lieu. Cela signifie que l'appellation a été utilisée pour cette activité qui s'est déroulée dans un ou plusieurs lieux.

Bien qu'elles diffèrent légèrement en termes de sémantique, ces deux options permettent d'indiquer l'emplacement associé à l'appellation. Cependant, l'activité d'utilisation du nom elle-même peut ne pas être située dans l'espace en soi. Par exemple, Charles Dodgson a utilisé le pseudonyme Lewis Carroll pour son activité d'écriture et il a séjourné dans un lieu sous ce nom. Un lien direct entre l'activité d'utilisation du nom et le lieu implique que l'utilisation de ce nom pour l'écriture s'est effectivement produite dans ce lieu, mais ce n'est pas forcément le cas. En revanche, il est plus exact de dire que lors de son séjour à cet endroit, l'actant a fait usage de cette appellation dans le cadre de cette activité. Il convient donc d'appliquer la première option (c.-à-d. lier l'évènement de séjour à l'appellation). 

### Limitations

Le modèle DOPHEDA ne permet pas de décrire correctement les flux migratoires, car il ne définit que les moments entre plusieurs déplacements. Selon l'hypothèse du monde ouvert, il est impossible de déterminer la durée d'un voyage en comparant la date de fin d'un évènement de séjour (Date de fin du séjour) à la date de début du suivant (Date de début du séjour) puisqu'il peut y avoir d'autres évènements entre les deux.

### Enjeux connexes sur GitHub

* [Enjeu n° 18 « Comment modéliser des groupes qui sont présents à différents lieux en même temps? »](https://github.com/chin-rcip/collections-model/issues/18) (en anglais)
* [Enjeu n° 31 « Déplacement, séjour, acquisition, établissement : comment modéliser la présence géographique des actants? »](https://github.com/chin-rcip/collections-model/issues/31) (en anglais)
* [Enjeu n° 49 « Comment modéliser l'attribution des sièges sociaux juridiques? »](https://github.com/chin-rcip/collections-model/issues/49) (en anglais)

### Cas limites

Yousuf Karsh a passé 29 jours sur le paquebot Versailles lorsqu'il a quitté le Liban pour immigrer au Canada (Karsh, n.d.). Il est donc resté 29 jours dans le même lieu (c.-à-d. dans le bateau). Toutefois, dans la pratique, il s'agit d'un voyage; il serait peut-être plus juste de documenter le temps passé par Karsh au Liban et au Canada respectivement. Évidemment, en procédant ainsi, les données ne documentent pas le voyage, qui a certainement eu un impact considérable sur la vie de l'artiste. Ce cas limite montre que la frontière entre se déplacer et séjourner est floue. Si une archive indique la présence d'une personne quelque part, il se peut qu'elle y ait vécu ou qu'elle se soit simplement rendue dans un autre lieu.

## Bibliographie

Bekiari, Chryssoula, George Bruseker, Martin Doerr, Christian-Emil Ore, Stephen Stead, et Athanasios Velios, éds. *Definition of the CIDOC Conceptual Reference Model*. Documentations du CIDOC CRM, 7.1. Paris, FR-IDF : CIDOC CRM Special Interest Group, 2021. [http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf](http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf).

Éditeurs de la Encyclopædia Britannica. « Cultural Globalization - The Persistence of Local Culture ». *Encyclopædia Britannica*. Londres, UK-LDN : Encyclopædia Britannica, n.d. [https://www.britannica.com/science/cultural-globalization](https://www.britannica.com/science/cultural-globalization).

Free Dictionary. « Headquarters ». *The Free Dictionary*. Huntington Valley, US-PA : Farlex, 2020. [https://www.thefreedictionary.com/headquarters](https://www.thefreedictionary.com/headquarters).

Karsh, Yousuf. « A Brief Biography ». *Yousuf Karsh* (blog). n.d. [https://karsh.org/a-brief-biography/](https://karsh.org/a-brief-biography/).

The Royal Canadian Academy of Arts (RCA). « News ». RCA/ARC, 2020. [https://rca-arc.ca/en/news](https://rca-arc.ca/en/news).

