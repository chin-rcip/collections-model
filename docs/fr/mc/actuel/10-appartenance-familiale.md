---
layout: page
language: fr
title: Appartenance familiale
permalink: /fr/modele-cible/actuel/appartenance-familiale
other_link: /en/target-model/current/family-belonging
sidebar: mc22
date: 2022-06-30
description: La Spécification du modèle cible des actants modélise sémantiquement les actants dans un contexte patrimonial. Les patrons conceptuels les plus pertinents pour la vie des actants sont présentés avec des diagrammes et des exemples qui les illustrent, ainsi qu'un compte rendu et une explication des décisions pertinentes qui ont été prises lors de l'élaboration desdits patrons conceptuels. Il s'agit d'une documentation théorique qui n'a jamais été testée ou mise en application.
---

## Aperçu {#apercu}

Ce patron conceptuel peut être utilisé pour documenter l'appartenance familiale d'une personne. Il comprend : 

* L'appellation de la famille (généralement le nom de famille);
* Les dates d'entrée dans la famille (généralement par naissance ou adoption) ou de départ (généralement par divorce ou décès) de la famille.

Il se rapporte spécifiquement à l'appartenance familiale, et non à :

* Une branche familiale appartenant à une branche familiale principale;
* La description des relations entre les membres de la famille ou différents individus (c.-à-d. leur rôle, pour ce cas spécifique, le patron conceptuel [Relation](/collections-model/fr/modele-cible/actuel/relation) doit plutôt être utilisé);
* L'appartenance à d'autres types de groupes (le patron conceptuel [Appartenance à un groupe](/collections-model/fr/modele-cible/actuel/appartenance-a-un-groupe) doit plutôt être utilisé).

## Introduction et contexte

### Historique théorique {#historique-theorique}

Le concept de « famille » peut varier temporellement et socialement, car différentes pratiques et croyances peuvent coexister ou s'opposer d'une famille à l'autre ou entre cultures. La définition de la famille est donc multiple et susceptible d'évoluer.

Il est important de différencier le concept de famille de celui de ménage. Contrairement aux ménages, qui sont déterminés par la situation géographique des actants, les familles sont déterminées par les relations entre les actants (Allan 2007, 1619). En outre, les personnes qui partagent un même foyer n'appartiennent pas nécessairement à la même famille.

Même au sein du concept de famille, il existe souvent une distinction informelle entre différentes variantes, par exemple la famille nucléaire et la famille élargie. Il est généralement accepté que la famille nucléaire est composée des parents et de leurs enfants, tandis que la famille élargie comprend d'autres personnes couvrant plus de deux générations et liées par la filiation ou l'alliance (Bruce & Yearley 2006).

Toutefois, les conceptions nucléaire et élargie de la famille ne sont pas universelles. Dans certaines sociétés, la famille nucléaire n'est pas composée uniquement des parents et de leurs enfants, mais inclut d'autres membres (Boudon & Bourricaud 2003, 170-171) tandis que dans d'autres, la distinction entre le ménage, la famille nucléaire et la famille élargie n'a pas de sens. Par exemple, la société romaine avait trois conceptions différentes de la famille qui coexistaient et se chevauchaient (Parkin & Pomeroy 2007, 72-73; Saller 1986; Smith 2006, 15-16) : 

* *familia*, qui comprenait le *pater familias*, sa femme, ses enfants et ses esclaves; 
* *domus*, qui comprenait la maison physique en plus de la *familia*, mais faisait également référence à des personnes extérieures au foyer, comme des amis proches; 
* *gens*, qui désignait les personnes partageant le même *nomen* ou nom de famille, issu exclusivement de la lignée masculine, de sorte que le *gens* comprenait plusieurs familles dont les membres ne partageaient pas le même *gens*.

Cet exemple montre que la conception courante de la famille n'est pas entièrement applicable à toutes les sociétés et qu'elle peut induire en erreur lorsqu'elle est utilisée dans un contexte historique, car elle ne peut pas englober entièrement l'évolution des idées et des conceptions de la cellule familiale dans les différentes cultures. 

### Énoncé des besoins {#enonce-des-besoins}

Dans certains domaines patrimoniaux centrés sur les relations humaines, tels que la généalogie, la sociologie, l'histoire sociale, etc., il est bénéfique d'identifier l'appartenance d'un individu à une famille spécifique, notamment lorsque cette famille est particulièrement prééminente (p. ex. les Julii dans l'Antiquité romaine ou les Médicis dans l'Italie de la Renaissance), ou pour des questions de recherche spécifiques (p. ex. onomastiques ou démographiques). En outre, dans certaines cultures, la famille en tant que concept est au centre de la vie sociale et/ou politique (Bruce & Yearley 2006). 

Il est pertinent de documenter les familles en tant qu'entités spécifiques afin qu'elles puissent être décrites et liées aux personnes qui en font partie. Un tel patron conceptuel permet de lier des personnes à des familles, même si la nature spécifique de leur relation avec la famille demeure inconnue. En plus des relations, les données familiales sont précieuses pour l'analyse des réseaux sociaux.

## Description du patron conceptuel

Comme l’indique l'ontologie du CIDOC CRM, les familles sont considérées comme des exemples particuliers de la classe `E74_Groupe` (Bekiari et al. 2021, 44-45). Il est donc approprié de considérer les personnes comme des membres d'un groupe familial, et les évènements d'entrée et de départ peuvent aider à documenter le moment lors duquel une personne entre et quitte cette même famille. 

Ainsi, une instance de `E74_Groupe` est d'abord liée à une instance de `E55_Type` (un nœud doté d’un qualifiant spécifié) portant le libellé « Famille » à travers la propriété `P2_a_pour_type` afin de différencier les familles des autres types d'instances de `E74_Groupe` dans le graphe de connaissances.

L'instance de `E74_Groupe` est ensuite liée à une instance de `E41_Appellation` et de `E33_Objet_linguistique` par la propriété `P1_est_identifié_par` qui rend la valeur littérale de l’[Appellation de la famille](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-de-la-famille) par la propriété `P190_a_pour_contenu_symbolique`.

L'unité centrale de la partie « entrée » du patron conceptuel représente l'actant principal (une instance de `E21_Personne`) entrant dans la famille (une instance de `E85_Adhésion`) à travers la propriété `P143i_a_adhéré_par`. Cette instance de `E85_Adhésion` pointe vers le groupe familial auquel elle se rapporte (une instance de `E74_Groupe`) par la propriété `P144_a_fait_adhérer_à`. 

L'unité centrale de la partie « départ » du patron conceptuel représente l'actant principal (une instance de `E21_Personne`) quittant la famille (une instance de `E86_Départ`) par la propriété `P145i_s’est_dissocié_par`. Cette instance de `E86_Départ` pointe vers le groupe familial auquel elle se rapporte (une instance de `E74_Groupe`) par la propriété `P146_a_dissocié_de`.

Chaque évènement est lié à son instance respective de `E52_Intervalle_temporel` par la propriété `P4_a_pour_intervalle_temporel` afin de documenter le moment lors duquel la personne est entrée dans la famille et l’a quittée (voir le patron conceptuel [Limites temporelles](/collections-model/fr/modele-cible/actuel/limites-temporelles) avec des valeurs extraites des nœuds de saisie [Date de début de l'entrée dans la famille](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-de-lentree-dans-la-famille), [Qualifiant de la date de début de l'entrée dans la famille](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-de-lentree-dans-la-famille), [Date de fin de l'entrée dans la famille](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-de-lentree-dans-la-famille), [Qualifiant de la date de fin de l'entrée dans la famille](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-de-lentree-dans-la-famille), [Date de début du départ de la famille](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-du-depart-de-la-famille), [Qualifiant de la date de début du départ de la famille](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-du-depart-de-la-famille), [Date de fin du départ de la famille](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-du-depart-de-la-famille) et [Qualifiant de la date de fin du départ de la famille](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-du-depart-de-la-famille). 

## Diagramme

<a name="098_PatronConceptuel_AppartenanceFamiliale_p"></a>098_PatronConceptuel_AppartenanceFamiliale_p

<div class="mxgraph" style="max-width:100%;border:1px solid #cccccc;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;target&quot;:&quot;blank&quot;,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom layers lightbox&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;xml&quot;:&quot;&lt;mxfile host=\&quot;app.diagrams.net\&quot; modified=\&quot;2023-03-15T17:12:57.115Z\&quot; agent=\&quot;5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) draw.io/20.3.0 Chrome/104.0.5112.114 Electron/20.1.3 Safari/537.36\&quot; etag=\&quot;vLMHHs3kDapmUjGUStXB\&quot; version=\&quot;20.3.0\&quot;&gt;&lt;diagram id=\&quot;M10G-2mTQvHYUXy7SPrL\&quot; name=\&quot;Page-1\&quot;&gt;5Vxbl6I4EP41nn2yj4SbPtrd9uzO7p7tPT175vLCiRA100gcCNM6v34TSLijqKA40w82FAnk8lXlq6rAQH1Yb9/5cLP6mzjIHYCRsx2ojwMAxmDCfrlgFwuU+HTpY6ckeME/kBCOhDTEDgpyBSkhLsWbvNAmnodsmpNB3ydv+WIL4uafuoFLVBK82NAtSz9ih65kp8xU/jvCy5V8smKI7q6hLCx6EqygQ94yInU2UB98Qmh8tN4+IJePnByXuN5TzdWkYT7yaEWF/wLk/zP/yscEjFw4Z5MSFZrpuvVht0EDYLis3v3cZ0dLfjR4AIPpPSv9BNfYZQPAbshE9/fxk+SDkbOYvH8/dFcvH778eP/kfvznz9VQTTqUNDSgOzmIPgk9B/H6CnvO2wpT9LKBNr/6xjDDZCu6dsXlBXv2A3GJH9VVF3CuG3q5s6L/35FP0TYjEo14h8gaUX/HioirQ2UkZkIAUZUz85ZOrCJlq8ykGkIGBZaWyb3T4WYHoufyNDMB1TNYOZCip9+hG4rBe1Y0zYLWAmJanjMLOqvBgzqYTnzkW9GRhFs6/MhhkBanxKcrsiQedGep9D6doBE7S8v8RchGTMtXROlO6CcMKclPWkChT6dc35jAIx6SsifMhyS6LfIcWcJ2YRBgOxaKIkp0xob1U1KenXzmJ3e6PH3cZi8+7sRZLTwCEvo22jPeQo9ZU5eI7imnqHFBPpZ70eYjF1L8PW8+qpAjqj4T7NEUpWYOopo5uZtk//K3i1st7lDAYtKkKng2w6JRwqIEoIO/SwQ+c3Bu2DBbrBXIZ4XdxLawp2ZKVlS2KFpviM8XjOoat4vkLaafUuyys8+yMjtOYcxPdllMf8oD/nNWM66HfuUy6Gc22rjT81baMKXkQrDX1CobrGKG89Taxv8sNujXAOmpSDkFlaeja9wQXWbb4KpZlJtNv1ma/dlYt6Zy5gNMvNKUn0NwxsBWkd0GwQFmnuBoencEp9lYjstjCRTrGfkBp+utDuNiMXds2MUw6mZiga42kJOySRoDaLnIcmJYzkNqlemhE2au36ahApewVHJ9O7wQar2yVdJLzuNibrnMX8BeFSCQuHabYDD7BQa9X2BQSmCY6cD6I6HlFXhI+XebK5oxt+3xvjk4wxp36bU3HGdQVjognSAahVZuUbcuY2jVhrrV1N0WMBndKRND2OZTfRBZhCwWATrSs6iNtpma9Y5NrgTFfmB1GEVrjx2NL8YxK4JodeOcWDZp2B4h5QFMJ/rJUKBY4v7GtSAWRyWgF0Q3ZD8LGf1MIhLzYgQjtZ/bgM3H1GEP+4DXYo5d7L3GrVpRysPUU95B8GSvsDf0bby5W2K6Cud3mHApYQ+zKfMqguE6jp0/Ldj9n4INsvEC25BfGzooGNortMasWIDW0KP4W4hYo5+gTcOolkdQ6ASs5DCAOMCsNSpvGBc4iHWeH7i834gJWIeHLhwmnT0MTq09cLaBQ1XLxwnAqP9AjHjXr4lA1vUz8af3C3/K5Kr4a0hVyg74s6IZFkeZg4OA2FgEspyrsJbW0wZ9Docpk6Z+xYVyDUB6szuJzIuHWrUqfOrYQkFlOCMH2WvHXpUs1LrMUTUGzrht3JznJ5WDVrOxYT3G08cGohyR6kkcNU9x+xD/AxWBHp54K+tITSoukzKu9flvyOALw61kzXZixA9l13qnt+BCBl/Vx4XsmqE0Nfnl1UPP38ocFcAfj09nawcoh7t+lZj4JdgKaBqpAf0KiYOK6FwmJN7LAPjopJlXrj7zrce/a8yWWkjIKQVL0zFLBeUNARV7WWpi7Qf3wBy5BaYvgXnlolnSFuJ+YSqJuacIxPysERcR8wvZAe9vFH05JuAC+hXwK+LtFgLPIt73qyEvivWdjrt+BfqKuDP7GOcD5a2az+aE+YcB8XJst+QMfguhy+b9NkMqCS/KuYFgvx94OjFqvDEANA3EyIjD6E41ciiTDKf9XGZ5z6Wh5REOivSqxpFjTjrcZYpteIGgnsYNVSX/IFXV97esVEHJveLADuI2tMv2yhsAn8cjrktV4RbuU+R0CP0cSmReX4kmRyuRYkpn9Di9OR/JxpFI1vYhuUJFC9WT2MsBFe12c0OJ+/wbKwL08hzHuWQuPqA+9pa940bfkqERhKjF1Hy83PSGMQ21SQGt435S9QZw7S5jf2s4PTuBH9vz/qJUvSxKm5ERGfk68A7WHq5/+B2sChegLy9jVed5DhD8yyd6GkdMVXAcpxndjUxNOc8V2FVWaOAYFEmHPgbFXFFLnoFa8ED0ibq3ZaXyeo5+deMXqOV8U5UqSlchWjlOUkHUMx08UZ2qdbczv6K5Dh65tfiCfkUR1wY4Tg8MfXyEV1HUb0Npqt89cSv20i0puFQ+4Nb43LnpgXgp6w2d0wofd9BBd8moLnyOY7HcTWrh1kB8XqZBbfF9iw4gbIAuM6pNXJLp9tWevVAHb4av08e3L1RVfgzlgtyLnRN9e3WwgoRUDmLre2aql3izAKnkZbr292hVdhPUUuYFidqZosj4FhJ5YRhEOGAGZ6Qom216MWHZSrRDGDtshupc1/gJNbyZqSTNI8xH7KFwHhXgIBBcjZXW7wf6I7e+Ll56TGAjvsuDCbhqM8PmTsWFNXacCO7RAnAP7ddlBPzce1j8rxJj+5StZESSD16JFg+y35SqY7G6XkgyncJpSxgrbCI/6Ge2ha2qr3RMRvV7YtmAUeSFFTnQYLeeE5cvRFcxbX3by7rPYB00bE23hCUBDmAWvnnUXeqzLeSVX1qYqarFV1JqMda0DHFAYzQVoTbTFGu62bBnRHSoBLdzNnfZ0V8LPEQxCoHRqjeu1XZYSGPenBu1n5LkwrSH+5hsvdb1lshe+EN7TJR+VTHW+fTDlOrsfw==&lt;/diagram&gt;&lt;/mxfile&gt;&quot;}"></div>

## Exemples

### Exemple 1

Yousuf Karsh est devenu membre de la famille Karsh (`P190_a_pour_contenu_symbolique`, Appellation de la famille) par naissance le 1908-12-23 (`P82a_le_début_du_début`, Date de début de l'entrée dans la famille; `P82b_la_fin_de_la_fin`, Date de fin de l'entrée dans la famille) et a quitté la famille par décès le 2002-07-13 (`P82a_le_début_du_début`, Date de début du départ de la famille; `P82b_la_fin_de_la_fin`, Date de fin du départ de la famille).

<div id="0001_100_family-belonging" class="example"></div>

### Exemple 2

En 1981 (`P82a_le_début_du_début`, Date de début de l'entrée dans la famille; `P82b_la_fin_de_la_fin`, Date de fin de l'entrée dans la famille), Lady Diana Spencer est devenue membre de la famille royale britannique (`P190_a_pour_contenu_symbolique`, Appellation de la famille) en épousant Charles, Prince de Galles; on peut considérer qu'elle a quitté la famille par divorce en 1996 (`P82a_le_début_du_début`, Date de début du départ de la famille; `P82b_la_fin_de_la_fin`, Date de fin du départ de la famille).

<div id="0001_122_family-belonging" class="example"></div>

## Documentation connexe

### Modèles externes {#modeles-externes}

* SARI : [Person Reference Data Model – Social Relations](https://docs.swissartresearch.net/et/persons/#social-relations)

### Nœuds de saisie {#noeuds-de-saisie}

* [Appellation de la famille](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-de-la-famille) \| Liste de vérification
* [Date de début de l'entrée dans la famille](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-de-lentree-dans-la-famille) \| Liste de vérification
* [Date de début du départ de la famille](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-du-depart-de-la-famille) \| Liste de vérification
* [Date de fin de l'entrée dans la famille](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-de-lentree-dans-la-famille) \| Liste de vérification
* [Date de fin du départ de la famille](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-du-depart-de-la-famille) \| Liste de vérification
* [Qualifiant de la date de début de l'entrée dans la famille](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-de-lentree-dans-la-famille) \| Liste de vérification
* [Qualifiant de la date de début du départ de la famille](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-du-depart-de-la-famille) \| Liste de vérification
* [Qualifiant de la date de fin de l'entrée dans la famille](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-de-lentree-dans-la-famille) \| Liste de vérification
* [Qualifiant de la date de fin du départ de la famille](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-du-depart-de-la-famille) \| Liste de vérification

### Entités du CIDOC CRM {#entites-du-cidoc-crm}

* `E39_Actant` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E39)]
* `E52_Intervalle_temporel` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E52)]
* `E55_Type` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E55)]
* `E74_Groupe` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E74)]
* `E85_Adhésion` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E85)]
* `E86_Départ` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E86)]
* `P2_a_pour_type (est_le_type_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P2)]
* `P4_a_pour_intervalle_temporel (est_l’intervalle_temporel_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P4)]
* `P79_a_son_début_qualifié_par` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P79)]
* `P80_a_sa_fin_qualifiée_par` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P80)]
* `P82a_le_début_du_début`
* `P82b_la_fin_de_la_fin`
* `P143_a_fait_adhérer (a_adhéré_par)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P143)]
* `P144_a_fait_adhérer_à (a_accueilli_le_membre_par)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P144)]
* `P145_a_dissocié (est_dissocié_par)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P145)]
* `P146_a_dissocié_de (a_perdu_le_membre_par)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P146)]
* `P190_a_pour_contenu_symbolique` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P190)]

## Discussion

### Justification

La modélisation de la famille comme une instance de `E74_Groupe` respecte les contraintes de la note d'application du CIDOC CRM qui se limite au rassemblement de personnes humaines pouvant agir collectivement au nom de la relation qui les unit (Bekiari et al. 2021, 44-45).

Pour le moment, le rôle d'une personne au sein d'une famille n'a pas été inclus dans ce patron conceptuel, mais plutôt dans le patron conceptuel [Appartenance à un groupe](/collections-model/fr/modele-cible/actuel/appartenance-a-un-groupe), car les rôles familiaux, comme l'unité familiale elle-même, fluctuent en fonction des évènements qui affectent la dynamique de la famille. Parce que la propriété `P144.1_sorte_de_membre` est de nature invariable, l'utiliser pour ce patron conceptuel pourrait induire en erreur. Ainsi, les rôles familiaux doivent être documentés à l'aide du patron conceptuel [Relation](/collections-model/fr/modele-cible/actuel/relation) ou du patron conceptuel [Appartenance à un groupe](/collections-model/fr/modele-cible/actuel/appartenance-a-un-groupe). Cette absence de rôle de la personne au sein de la famille est ce qui différencie ce patron conceptuel du patron conceptuel 'Appartenance à un groupe.

### Limitations

Comme l’indique l'Historique théorique, le concept de « famille » englobe différentes significations à travers le temps et les cultures. Les membres d'une famille peuvent varier considérablement, allant d'une unité restreinte limitée aux parents et à leurs enfants, à des structures plus larges comprenant plusieurs autres unités ou personnes au service d'une unité principale. La gestion de cette variabilité dépend en grande partie de l'utilisation de vocabulaires contrôlés. Deux options sont possibles :

* Toujours utiliser une définition large de la famille afin que tous les concepts qui lui sont apparentés soient englobés par un seul terme (p. ex. *gens*, *familia* et *domus* seraient tous classés dans la catégorie famille, et la précision de ces termes serait réduite à l'utilité de la famille au sens large);
* Utiliser des termes précis (développés ou réutilisés) afin de distinguer différentes compréhensions d'un concept plus large (p. ex. *gens*, *familia* et *domus* seraient tous traités comme des concepts en soi, mais ne seraient souvent pas liés à d'autres concepts de la famille en raison de la complexité inhérente à l'identification et au traitement des équivalences et des hiérarchies dans un large éventail de définitions, et subséquemment, à la mise en correspondance et à l'interrogation des données). 

Pour l'instant, parce qu'elle est plus facile à mettre en application, la première option a été retenue. 

### Enjeux connexes sur GitHub

* [Enjeu n° 16 « Avons-nous besoin d'un patron conceptuel Relations familiales? Et que faire des parents? »](https://github.com/chin-rcip/collections-model/issues/16) (en anglais)
* [Enjeu n° 57 « De quels champs avons-nous besoin pour gérer l'identité d'un actant? »](https://github.com/chin-rcip/collections-model/issues/57) (en anglais)

### Cas limites

#### Exemple 1 {#cas-limites-exemple-1}

La portée de la classe `E74_Groupe` indique qu'une famille est un rassemblement de personnes qui peuvent agir collectivement (Bekiari et al. 2021, 44-45). Cependant, d'autres groupes, formels ou informels, pourraient être considérés comme comparables à une famille (p. ex. lorsque des personnes élèvent un enfant qui n'est pas formellement adopté, ou un groupe d'amis très proches). La personne responsable du catalogage ou experte en données détermine si ces groupes doivent être documentés en utilisant le patron conceptuel Appartenance familiale ou le patron conceptuel Appartenance à un groupe, car la distinction entre ces deux patrons conceptuels peut être floue.

#### Exemple 2 {#cas-limites-exemple-2}

Il peut être argumenté que le rôle d'une personne au sein d'une famille peut rester le même, quels que soient les membres actuels de la famille. Par exemple, un enfant adopté pourrait être documenté comme portant le rôle « Adopté » avec l'ensemble du groupe familial. Dans ce cas, cela impliquerait l'utilisation du patron conceptuel Appartenance à un groupe et l'ajout du type famille au groupe.

## Bibliographie

Allan, Graham. « Family Structure ». *The Blackwell Encyclopedia of Sociology*, éditée par George Ritzer. Malden, USA; Oxford, UK-OXF; Carlton, AUS-VIC : Blackwell Publishing, 2007 : 1618-1621.

Bekiari, Chryssoula, George Bruseker, Martin Doerr, Christian-Emil Ore, Stephen Stead, et Athanasios Velios, éds. *Definition of the CIDOC Conceptual Reference Model*. Documentations du CIDOC CRM, 7.1. Paris, FR-IDF : CIDOC CRM Special Interest Group, 2021. [http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf](http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf).

Boudon, Raymond, et François Bourricaud. « Family ». *A Critical Dictionary of Sociology*, traduit par Peter Hamilton. Londres, UK-LDN : Routledge, 1999 : 169-176.

Bruce, Steve, et Steven Yearly. « Family. » *The SAGE Dictionary of Sociology*. Londres, UK-LDN : SAGE Publication Ltd, 2006 : 103-104.

Parkin, Tim G., et Arthur J. Pomeroy. *Roman Social History. A Sourcebook*. Abingdon, US-NY : Routledge, Taylor & Francis Group, 2007.

Saller, Richard P. « 'Familia, Domus', and the Roman Conception of Family ». *Phoenix* 38, no 4 (1984) : 336-355.

Smith, C. J. *The Roman Clan: The Gens from Ancient Ideology to Modern Anthropology*. Cambridge, UK-CAM : Cambridge University Press, 2006.

