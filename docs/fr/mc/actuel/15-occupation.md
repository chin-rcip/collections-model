---
layout: page
language: fr
title: Occupation
permalink: /fr/modele-cible/actuel/occupation
other_link: /en/target-model/current/occupation
sidebar: mc22
date: 2022-06-30
description: La Spécification du modèle cible des actants modélise sémantiquement les actants dans un contexte patrimonial. Les patrons conceptuels les plus pertinents pour la vie des actants sont présentés avec des diagrammes et des exemples qui les illustrent, ainsi qu'un compte rendu et une explication des décisions pertinentes qui ont été prises lors de l'élaboration desdits patrons conceptuels. Il s'agit d'une documentation théorique qui n'a jamais été testée ou mise en application.
---

## Aperçu {#apercu}

Ce patron conceptuel peut être utilisé pour représenter les informations relatives à l'occupation ou aux occupations d'une personne ou d'un groupe, dans un sens plus large, en tant qu'activité·s principale·s de sa vie. Il comprend : 

* Le type d'occupation d'un actant, qui peut être une activité rémunérée ou non, une entreprise, une profession ou tout autre activité liée au travail;
* L'intervalle temporel durant lequel un actant a pratiqué l'occupation;
* Le lieu où un actant a exercé son occupation.

Ce patron conceptuel ne doit pas être utilisé pour représenter :

* Le rôle spécifique qu'un actant a joué dans la création d'un artefact (le patron conceptuel [Production d’artefact](/collections-model/fr/modele-cible/actuel/production-dartefact) doit plutôt être utilisé);
* Les techniques qu'un actant a employées pour la création d'un artefact (le patron conceptuel [Production d’artefact](/collections-model/fr/modele-cible/actuel/production-dartefact) doit plutôt être utilisé);
* Les techniques pour lesquelles un actant est connu (le patron conceptuel [Technique utilisée](/collections-model/fr/modele-cible/actuel/technique-utilisee) doit plutôt être utilisé);
* Les activités récréatives et professionnelles d'un individu faisant partie d'un groupe (p. ex. un musicien employé par un orchestre), y compris sa formation (p. ex. étudiant ou enseignant dans un établissement d'enseignement) (le patron conceptuel [Appartenance à un groupe](/collections-model/fr/modele-cible/actuel/appartenance-a-un-groupe) doit plutôt être utilisé);
* Le statut social d'un actant (le patron conceptuel [Statut social](/collections-model/fr/modele-cible/actuel/statut-social) doit plutôt être utilisé).

## Introduction et contexte

### Historique théorique {#historique-theorique}

Un actant réalise de nombreuses activités significatives et déterminantes tout au long de sa vie, en particulier lorsque cela nécessite une formation, des compétences et des qualifications qui peuvent être rémunérées (p. ex. un employé au sein d'une entreprise) ou non rémunérées (p. ex. un bénévole). Ces activités sont généralement considérées par l'actant ou par une communauté d'experts·es comme faisant partie de leurs principales activités au cours de leur vie (c.-à-d. comme une source de revenus ou pratiquées à d'autres fins, comme un passe-temps). 

De plus, les occupations constituent un marqueur identitaire important pour plusieurs communautés, même si l'on constate une légère diminution de son importance au fil du temps par rapport à d'autres marqueurs comme le genre ou la nationalité. En outre, le statut social est souvent intimement lié à l'occupation et joue un rôle central pour l'auto-identification, en particulier auprès des communautés de pratique qui partagent des problèmes et des besoins similaires (Ulfsdotter Eriksson et Linde 2014).

Documenter une occupation plutôt qu'une autre peut donc aider à mieux comprendre les valeurs portées par la communauté de pratique d'un actant. Ces valeurs peuvent être perçues soit par la communauté contemporaine de l'élément décrit, soit par la communauté à laquelle appartient l'institution du patrimoine culturel qui conserve ces informations.

### Énoncé des besoins {#enonce-des-besoins}

Ces métadonnées essentielles sont souvent documentées par les institutions du patrimoine culturel comme un moyen de différencier un actant d'autres actants ainsi que de documenter leur vie.

Par ailleurs, un actant peut pratiquer plus d'une occupation, chacune d'entre elles pouvant être exercée dans une période déterminée et dans un ou des lieux déterminés. Par exemple, Yousuf Karsh, avant d'entamer une carrière de 60 ans comme photographe portraitiste professionnel en 1932 avec son propre studio à Ottawa, CA-ON, a été apprenti à Boston, US-MA, de 1928 à 1931 (Wikipedia 2021). Ces données détaillées enrichissent les métadonnées de l'actant et présentent un intérêt pour la recherche (p. ex. analyse chronologique et/ou géographique). 

Documenter le cadre temporel et les lieux d'une occupation peut également fournir des informations utiles sur son contexte, ce qui peut aider à mieux comprendre les pratiques humaines, telles que l'évolution des occupations à travers le temps ou l'espace, ou encore leur importance à des périodes et/ou des lieux précis.

## Description du patron conceptuel

Pour chaque occupation, une instance de `E39_Actant` est d'abord liée par la propriété `P14_a_été_effectué_par` à une instance de `F51_Pratique` qui est qualifiée par la valeur du [Type d'occupation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#type-doccupation) (une instance de `E55_Type`) en utilisant la propriété `P2_a_pour_type`. Cette instance de `E55_Type` est de plus qualifiée par une instance de `E55_Type` (un nœud doté d’un qualifiant spécifié) portant le libellé « Occupation » par la propriété `P2_a_pour_type`.

La durée de la pratique est indiquée à l'aide du patron conceptuel [Limites temporelles](/collections-model/fr/modele-cible/actuel/limites-temporelles) lié à l'instance de `F51_Pratique` par la propriété `P4_a_pour_intervalle_temporel` avec des valeurs extraites des nœuds de saisie [Date de début de l'occupation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-de-loccupation), [Qualifiant de la date de début de l'occupation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-de-loccupation), [Date de fin de l'occupation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-de-loccupation) et [Qualifiant de la date de fin de l'occupation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-de-loccupation). 

De plus, l'instance de `F51_Pratique` est liée à la valeur du [Lieu de l'occupation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#lieu-de-loccupation) (une instance de `E53_Lieu`) par la propriété `P7_a_eu_lieu_dans`.

## Diagramme

<a name="033_PatronConceptuel_Occupation_p"></a>033_PatronConceptuel_Occupation_p

<iframe frameborder="0" style="width:100%;height:500px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=033_PatronConceptuel_Occupation_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D19qFoXGJPhlo-9aqYx6WVr8vhEOupBY9o%26export%3Ddownload"></iframe>

## Exemples

### Exemple 1

Yousuf Karsh a mené une carrière de photographe (`P2_a_pour_type`, Type d'occupation) s'étendant sur 60 ans, de 1932 (`P82a_le_début_du_début`, Date de début de l'occupation) à 1992 (`P82b_la_fin_de_la_fin`, Date de fin de l'occupation), principalement à Ottawa (CA-ON) (`P7_a_eu_lieu_dans`, Lieu de l'occupation) (Wikipedia 2021a).

<div id="0001_100_occupation" class="example"></div>

### Exemple 2

Marc Séguin est un artiste visuel (`P2_a_pour_type`, Type d'occupation), romancier (`P2_a_pour_type`, Type d'occupation) et agriculteur (`P2_a_pour_type`, Type d'occupation). Sa première exposition solo remonte à 1996 (`P2_a_pour_type`, Type d'occupation « Artiste visuel »; `P82a_le_début_du_début`, Date de début de l'occupation « 1996 »; `P79_a_son_début_qualifié_par` », Qualifiant de la date de début de l'occupation « Avant ») et il a exercé son occupation à Montréal, QC (`P7_a_eu_lieu_dans`, Lieu de l'occupation), Hemmingford, QC (`P7_a_eu_lieu_dans`, Lieu de l'occupation) et Brooklyn, NY (`P7_a_eu_lieu_dans`, Lieu de l'occupation). Son premier roman, *La Foi du braconnier*, a été publié en 2009 (`P2_a_pour_type`, Type d'occupation « Romancier »; `P82a_le_début_du_début`, Date de début de l'occupation « 2009 »; `P79_a_son_début_qualifié_par` », Qualifiant de la date de début de l'occupation « Avant »). Il est propriétaire d'une ferme familiale à Hemmingford, QC (`P2_a_pour_type`, Type d'occupation « Agriculteur »; `P82a_le_début_du_début`, Date de début de l'occupation « 2008 »; `P79_a_son_début_qualifié_par`, Qualifiant de la date de début de l'occupation « Avant »; `P7_a_eu_lieu_dans`, Lieu de l'occupation « Hemmingford, QC ») (Wikipedia 2022).

<div id="0001_128_occupation" class="example"></div>

## Documentation connexe

### Modèles externes {#modeles-externes}

* Linked.art : [Active Dates](https://linked.art/model/actor/#active-dates)
* SARI : [Person Reference Data Model – Activities](https://docs.swissartresearch.net/et/persons/#activities)
* Schema.org : [`hasOccupation` property](https://schema.org/hasOccupation)
* Wikidata : [`P106`(occupation)](https://www.wikidata.org/wiki/Property:P106)

### Nœuds de saisie {#noeuds-de-saisie}

* [Date de début de l'occupation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-de-loccupation) \| Liste de vérification
* [Date de fin de l'occupation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-de-loccupation) \| Liste de vérification
* [Lieu de l'occupation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#lieu-de-loccupation) \| Liste de vérification
* [Qualifiant de la date de début de l'occupation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-de-loccupation) \| Liste de vérification
* [Qualifiant de la date de fin de l'occupation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-de-loccupation) \| Liste de vérification
* [Type d'occupation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#type-doccupation) \| Liste de vérification

### Entités du CIDOC CRM {#entites-du-cidoc-crm}

* `F51_Pratique`
* `E39_Actant` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E39)]
* `E52_Intervalle_temporel` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E52)]
* `E53_Lieu` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E53)]
* `E55_Type` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E55)]
* `P2_a_pour_type (est_le_type_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P2)]
* `P4_a_pour_intervalle_temporel (est_l’intervalle_temporel_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P4)]
* `P7_a_eu_lieu_dans (a_été_témoin_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P7)]
* `P14_is_a_été_effectué_par (a_effectué)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P14)]
* `P79_a_son_début_qualifié_par` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P79)]
* `P80_a_sa_fin_qualifiée_par` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P80)]
* `P82a_le_début_du_début`
* `P82b_la_fin_de_la_fin`

## Discussion

### Justification

Modéliser une occupation comme une classification d'un actant, c'est-à-dire une instance de `E39_Actant` directement liée à une instance de `E55_Type`, peut devenir restrictif, car les données temporelles et géographiques relatives à l'occupation ne peuvent pas être enregistrées. La classe `F51_Pratique` de l'extension FRBRoo du CIDOC CRM offre plus de flexibilité à cet égard. 

De même, par définition, la classe `F51_Pratique` « comprend les périodes d'activité continue d'un actant dans un domaine ou un champ professionnel ou créatif spécifique » (Bekiari et al. 2015a, sect. F51 Pursuit; notre traduction). Comme sa portée est sémantiquement plus proche de la définition générale de l'occupation, qui englobe à la fois les activités professionnelles et récréatives, elle a été choisie pour modéliser la ou les occupations plutôt que sa super-classe `E7_Activité`.

Dans le tableau de mise en correspondance de FRAD à FRBRoo de la documentation du FRBRoo (v2.4) (Bekiari et al. 2015b), le chemin `F51_Pratique` -> `P2_a_pour_type` -> `E55_Type` est l'une des mises en correspondance suggérées pour des unités d'information telles que *Personne : Domaine d'activité*, *Personne : Profession/Occupation* et *Corps d'entreprise : Domaine d'activité*. Par définition, une instance de `F51_Pratique` peut être directement liée à une instance de `E1_Entité_CRM` ou l'une de ses sous-classes par la propriété `R59_avait_pour_sujet_de_la_pratique`. Cependant, l'exemple pour `R59_avait_pour_sujet_de_la_pratique` trouvé dans la documentation du FRBRoo (« L'activité de John Dover Wilson en tant que spécialiste de Shakespeare (F51) R59 avait pour sujet de la pratique William Shakespeare (F10) ») montre que cette propriété semble identifier le sujet plutôt que le type de pratique. Ainsi, la propriété `P2_a_pour_type` et la classe `E55_Type` sont considérées comme plus appropriées pour classer le type d'occupation de la pratique, tandis que la propriété `R59_avait_pour_sujet_de_la_pratique` peut être utilisée pour représenter son sujet, bien que cela ne soit pas fait actuellement.

Pour différencier ce type d'activité d'autres activités, particulièrement lors de l'exécution de requêtes, un nœud doté d’un qualifiant spécifié est nécessaire. Dans la version 1.5 de la Spécification du modèle cible, l'occupation était encore qualifiée par deux niveaux supplémentaires de la classe `E55_Type`, par exemple `E55_Type` (« Peintre ») -> `P2_a_pour_type` -> `E55_Type` (« Profession ») -> `P2_a_pour_type` -> `E55_Type` (« Occupation »). Cependant, trois niveaux de `E55_Type` peuvent rapidement gonfler le modèle de données et compliquer sa maintenance et sa gestion pour un simple besoin de qualification du type d'occupation. Par conséquent, deux niveaux de la classe `E55_Type` (le nœud de saisie pour le Type de statut social et le nœud doté d'un qualifiant spécifié portant le libellé « Statut social ») sont jugés suffisants. Si une hiérarchisation plus développée du statut social est nécessaire (p. ex. en distinguant différents types de statut social), elle doit être traitée en utilisant le vocabulaire de ce statut.

### Limitations

Comme il est indiqué dans la Justification, certaines occupations peuvent être qualifiées davantage en documentant le sujet de l'occupation par le biais de la propriété `R59_avait_pour_sujet_de_la_pratique`. Toutefois, cette information n'est pas encore prise en compte dans le modèle DOPHEDA en raison de l'insuffisance de cas d'utilisation.

### Enjeux connexes sur GitHub

* [Enjeu no 1 « Techniques versus Occupation »](https://github.com/chin-rcip/collections-model/issues/1) (en anglais)
* [Enjeu n° 11 : « Les années scolaires doivent-elles être modélisées comme étant un membre d'un groupe? En serait-il de même pour les professeurs·es? »](https://github.com/chin-rcip/collections-model/issues/11) (en anglais)
* [Enjeu n° 27 « Comment devrions-nous modéliser le ou les patrons conceptuels du statut social? »](https://github.com/chin-rcip/collections-model/issues/27) (en anglais)
* [Enjeu n° 29 « Avons-nous besoin de trois niveaux de types dans le patron conceptuel Occupation? »](https://github.com/chin-rcip/collections-model/issues/29) (en anglais)
* [Enjeu n° 37 « Utilité de `E55_Type` »](https://github.com/chin-rcip/collections-model/issues/37) (en anglais)

### Cas limites

#### Exemple 1 {#cas-limites-exemple-1}

Elizabeth II, la personne qui a été chargée d'accorder officiellement le statut social de « Compagnon de l'Ordre du Canada » à Yousuf Karsh, est connue comme étant la reine du Royaume-Uni et de 15 autres royaumes du Commonwealth. Si certains voient le « fait d'être reine » comme une occupation qui s'accompagne d'activités et de tâches très spécifiques, d'autres y voient un statut social. À cette dualité s'ajoute la possibilité de documenter le terme « Reine » comme un titre/préfixe au nom de la personne. Si les données ne précisent pas comment l'information est comprise dans le cadre d'un jeu de données spécifique, la modélisation pourrait conduire à une incertitude et à une mauvaise interprétation de la question.

#### Exemple 2 {#cas-limites-exemple-2}

Molly Bobak a fait des croquis dans ses journaux intimes tout au long de la guerre et ce n'est que trois ans après son enrôlement qu'elle a été officiellement nommée artiste de guerre (Type d'occupation) par le Comité de sélection des artistes de guerre canadiens (Wikipedia 2021b). Dans ce cas, la meilleure façon d'enregistrer l'information n'est pas claire, car la date de début du Type d'occupation serait postérieure à la fin de son service. Il n'est pas clair non plus si le Type d'occupation est déterminé par l'accomplissement de tâches ou par le fait d'occuper un poste.

## Bibliographie

Bekiari, Chryssoula, Martin Doerr, Patrick Le Bœuf, et Pat Riva, éds. « F51 Pursuit ». *FRBR Object-Oriented Definition and Mapping from FRBRER, FRAD and FRSAD*. Documentations du FRBRoo, 2.4. Conseil international des musées (ICOM), 2015. [http://www.cidoc-crm.org/frbroo/sites/default/files/FRBRoo\_V2.4.pdf](http://www.cidoc-crm.org/frbroo/sites/default/files/FRBRoo_V2.4.pdf).

Bekiari, Chryssoula, Martin Doerr, Patrick Le Bœuf, et Pat Riva, éds. « 3.5. FRAD to FRBROO Mappings ». *FRBR Object-Oriented Definition and Mapping from FRBRER, FRAD and FRSAD*. Documentations du FRBRoo, 2.4. Conseil international des musées (ICOM), 2015. [http://www.cidoc-crm.org/frbroo/sites/default/files/FRBRoo\_V2.4.pdf](http://www.cidoc-crm.org/frbroo/sites/default/files/FRBRoo_V2.4.pdf).

Bekiari, Chryssoula, George Bruseker, Martin Doerr, Christian-Emil Ore, Stephen Stead, et Athanasios Velios, éds. *Definition of the CIDOC Conceptual Reference Model*. Documentations du CIDOC CRM, 7.1. Paris, FR-IDF : CIDOC CRM Special Interest Group, 2021. [http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf](http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf).

Free Dictionary. « Occupation ». *The Free Dictionary*. Huntington Valley, US-PA : Farlex, 2021. [https://www.thefreedictionary.com/role](https://www.thefreedictionary.com/role).

Ulfsdotter Eriksson, Ylva, et Malin Linde. « 'Being' or 'Doing' a Profession: Work as a Matter of Social Identity ». *The International Journal of Interdisciplinary Cultural Studies* 8, no. 1 (2014) : 33‑43.

Wikipedia. « Yousuf Karsh ». *Wikipedia*. San Francisco, US-CA : Wikipedia, 2021a. [https://fr.wikipedia.org/wiki/Yousuf_Karsh](https://fr.wikipedia.org/wiki/Yousuf_Karsh).

–––. « Molly Lamb Bobak ». *Wikipedia*. San Francisco, US-CA : Wikipedia, 2021b. [https://fr.wikipedia.org/wiki/Molly_Lamb_Bobak](https://fr.wikipedia.org/wiki/Molly_Lamb_Bobak). 

–––. « Marc Séguin ». *Wikipedia*. San Francisco, US-CA : Wikipedia, 2022. [https://fr.wikipedia.org/wiki/Marc_Séguin](https://fr.wikipedia.org/wiki/Marc_Séguin).

