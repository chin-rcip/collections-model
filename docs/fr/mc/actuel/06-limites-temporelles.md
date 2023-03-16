---
layout: page
language: fr
title: Limites temporelles
permalink: /fr/modele-cible/actuel/limites-temporelles
other_link: /en/target-model/current/temporal-bounds
sidebar: mc22
date: 2022-06-30
description: La Spécification du modèle cible des actants modélise sémantiquement les actants dans un contexte patrimonial. Les patrons conceptuels les plus pertinents pour la vie des actants sont présentés avec des diagrammes et des exemples qui les illustrent, ainsi qu'un compte rendu et une explication des décisions pertinentes qui ont été prises lors de l'élaboration desdits patrons conceptuels. Il s'agit d'une documentation théorique qui n'a jamais été testée ou mise en application.
---

## Aperçu {#apercu}

Ce patron conceptuel peut être utilisé pour enregistrer les dates des évènements enregistrés dans le graphe de connaissances DOPHEDA. Il comprend :

* Les limites de date pour la durée des évènements;
* Les qualifiants pour ces dates.

Ce patron conceptuel couvre les dates dans un format spécifique. Par conséquent, il ne couvre pas : 

* Les dates dans les chaînes de caractères (le patron conceptuel [Données désordonnées](/collections-model/fr/modele-cible/actuel/donnees-desordonnees) doit plutôt être utilisé);
* La chronologie relative des évènements (p. ex. ceci est arrivé avant cela); 
* Un processus de datation (p. ex. la datation au radiocarbone). 

## Introduction et contexte

### Historique théorique {#historique-theorique}

Les conceptions du temps diffèrent selon les sociétés et peuvent être linéaires, cycliques ou inclure des compréhensions coexistantes du passé, du présent et du futur (Fuentes 2009; Peer 2009; Simonton 2009). Même si une approche linéaire et continue est aujourd'hui courante (Pollard 2009, 126-127; Emery et al. 2020; Savitt 2017), le calendrier grégorien étant le principal calendrier commercial au niveau international, d'autres calendriers sont fréquemment utilisés au niveau local (voir une liste actuelle sur [Wikipédia](https://en.wikipedia.org/wiki/Calendar_era)), et parfois simultanément, car les populations peuvent utiliser plus d'un calendrier dans leur vie quotidienne. Cela s'applique également à l'histoire, car les différentes méthodes d'enregistrement du temps (p. ex. le calendrier solaire ou lunaire) entraînent des difficultés considérables en matière de datation du patrimoine (p. ex. il y a une différence d'environ 11 jours entre une année solaire et une année lunaire, les calendriers grégorien et hijri ne coïncident pas l'un avec l'autre) (Richards 1999, 89-100).

Il s'agit d'un défi historique, car la date d'un évènement fournit des informations sur son contexte qui sont cruciales pour sa bonne compréhension. Les sciences sociales qui s'intéressent au passé, comme l'histoire ou l'archéologie, s'appuient fortement sur la compréhension du temps lorsqu'elles créent des lignes du temps ou situent les évènements historiques dans une séquence chronologique mesurée. Elles ont développé deux types de chronologie pour traiter le séquencement des évènements : la chronologie relative et la chronologie absolue.

* La chronologie relative est la structuration des évènements ou des périodes les uns par rapport aux autres, indépendamment de leurs dates respectives. Elle est particulièrement utile en archéologie, où les séquences stratigraphiques ou typologiques permettent de comprendre l'histoire d'un site ou de structurer la périodisation d'une période. L'établissement de relations entre différentes chronologies relatives (comme deux stratigraphies différentes et éloignées au sein d'un site archéologique, ou entre plusieurs typologies) est cependant difficile sans chronologie absolue.
* La chronologie absolue est la localisation dans le temps d'un évènement particulier ou la mesure du temps écoulé entre deux évènements. Elle permet d'établir où, dans une ligne de temps, un évènement s'est produit afin de mieux le contextualiser par rapport à d'autres évènements contemporains. La chronologie absolue peut être obtenue en analysant les évènements enregistrés dans les sources textuelles, ou à l'aide des sciences modernes de datation telles que la datation au radiocarbone.

Pour bien comprendre les évènements passés, les deux types de chronologie doivent être utilisés ensemble, en plaçant les évènements dans une séquence les uns par rapport aux autres (chronologie relative), ainsi qu'en affinant la séquence par une datation précise (chronologie absolue). 

### Énoncé des besoins {#enonce-des-besoins}

Dans le secteur patrimonial, comme dans les sciences sociales, les données chronologiques sont fondamentales pour la contextualisation et la compréhension des informations. Les spécialistes du domaine doivent régulièrement situer les évènements dans le temps et les relier à d'autres entités pour vérifier la pertinence et la validité des informations. De plus, en particulier dans les domaines historiques tels que l'histoire de l'art ou l'archéologie, l'imprécision des dates est non seulement fréquente, mais également significative, de sorte que l'incertitude chronologique doit être reflétée de manière adéquate dans les jeux de données et les modèles pour lesquels ils sont mis en correspondance.

En outre, avec l'avènement de l'analyse quantitative dans les sciences sociales et culturelles, les chercheurs·ses ont souvent besoin d'interroger et de mobiliser ces données pour offrir des perspectives statistiques sur celles-ci ou pour les visualiser sous forme de chronologies, par exemple. Pour faciliter ce travail à l'échelle, il est préférable d'encoder les dates de manière homogène et standardisée.

Il existe une distinction entre l'acte de dater un évènement et la date qui résulte du processus de datation. Bien que l'activité de datation puisse également être exprimée dans un graphe de connaissances sémantique, ce patron conceptuel se concentre sur la date elle-même et sur la manière de la représenter dans un graphe de connaissances, sans représentation sémantique des chronologies relatives. 

## Description du patron conceptuel

Les intervalles de temps dans le CIDOC CRM sont modélisés en utilisant la classe `E52_Intervalle_temporel`. Chaque instance de `E2_Entité_temporelle` ou de l'une de ses sous-classes est liée à une instance de `E52_Intervalle_temporel` par la propriété `P4_a_pour_intervalle_temporel`.

Cette instance de `E52_Intervalle_temporel` peut être délimitée par l'utilisation d'au moins une des quatre propriétés représentant des dates précises : 

* `P82a_le_début_du_début` indique que l’intervalle temporel de l'évènement peut avoir commencé au plus tôt à cette date;
* `P81a_la_fin_du_début` indique que l'intervalle temporel de l'évènement peut avoir commencé au plus tard à cette date;
* `P81b_le_début_de_la_fin` indique que l'intervalle temporel de l'évènement peut s'être terminé au plus tôt à cette date;
* `P82b_la_fin_de_la_fin` indique que l'intervalle temporel de l'évènement peut s'être terminé au plus tard à cette date.

Les propriétés `P82a_le_début_du_début` et `P82b_début_de_la_fin` étant les délimiteurs les plus englobants de l'évènement, elles doivent être utilisées systématiquement. Les propriétés `P81a_la_fin_du_début` et `P81b_le_début_de_la_fin` ne doivent être utilisées que lorsque ces informations précises sont disponibles.

Les dates structurées doivent être formatées en utilisant la norme `xsd:dateTime`. Pour de plus amples informations sur cette norme, voir la [Spécification du W3C](https://www.w3.org/TR/xmlschema-2/#isoformats).

Il est également possible d'ajouter des qualifiants aux dates avec les propriétés `P79_a_son_début_qualifié_par` et `P80_a_sa_fin_qualifiée_par` en conjonction avec une instance de `rdfs:Literal`. Ces qualifiants peuvent inclure des commentaires (p. ex. date présumée) ou des qualificatifs typiquement utilisés (p. ex. circa, av. J.-C., etc.). Au lieu d'ajouter des qualifiants pour exprimer le temps (comme avant, après, etc.), les responsables du catalogage sont encouragés à documenter les intervalles temporels uniquement avec les propriétés du CIDOC CRM afin de permettre de meilleurs mécanismes de calcul des intervalles temporels. Par exemple, si un évènement s'est produit avant un jour précis, seule la propriété `P82b_la_fin_de_la_fin` doit être utilisée, sans qu'il soit nécessaire de la qualifier avec la chaîne de caractères « Avant ». De même, si une date est qualifiée par « Circa », il est préférable de documenter ses limites temporelles avec l'intervalle temporel approprié en fonction du contexte des données.

## Diagramme

<a name="018_PatronConceptuel_LimitesTemporelles_p"></a>018_PatronConceptuel_LimitesTemporelles_p

<div class="mxgraph" style="max-width:100%;border:1px solid #cccccc;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;target&quot;:&quot;blank&quot;,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom layers lightbox&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;xml&quot;:&quot;&lt;mxfile modified=\&quot;2023-03-15T17:12:51.684Z\&quot; host=\&quot;app.diagrams.net\&quot; agent=\&quot;5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) draw.io/20.3.0 Chrome/104.0.5112.114 Electron/20.1.3 Safari/537.36\&quot; etag=\&quot;JSD2GvadJABnUpXJlPfq\&quot; version=\&quot;20.3.0\&quot;&gt;&lt;diagram id=\&quot;yNd9t-YoSMj7FANq12WV\&quot; name=\&quot;Page-1\&quot;&gt;1VjbbqMwEP0aHluBzS2PbZrtVnur1Eq7+4RcbMArB7PGJNCvXxNMgZJGyTZtiZQHz2EG22fOjHEMOF+W1wJlyTeOCTOAiUsDXhkAAKP+mbhqTKsxY0HxCLijj0SDpkYLikk+cJScM0mzIRjyNCWhHGBICL4eukWcDWfNUExGwF2I2Bj9SbFMNApMs3vwmdA40VP7tn6wRK2zBvIEYb7uQXBhwLngXDajZTknrOat5aWJ+/TC06eFCZLKfQKcxzWcA3DzI0Kyuv9ufTlDzpnfvGWFWKE3fOvNAhTkPA2wMYfGxeyhkMHfAjEa0QYI1Jx6S7JqeSJY0aZNLmTCY54itujQS8GLFJN6MaayOp+vnGcKtBT4h0hZaQ2gQnIFJXLJ9FO1T1H9quPPndb8rV+3Ma7KgVW1VkllE2ZbrrY3ceezmaftLrQ2+pG3RNAlkURobEy7zkTOCxGSHVy38kUiJnKHn9P41Yz2JtBJvSZcrUZUykGXl9qWM9MxgjAk6WqoXaRLIH4KfXrbLadqF50Lj6Jcra0nIzXoTdpBG3EdILTZWGg+CBjpqwwXPes0FQacnsCsneJ6eyHZewrpMNVcCIGqnkNWayjfIiqtT8fRDVD3f+g+61PP/CFwdvmrQbOCo8qzPW4G+jTrRoiCiKbDBkhOtwN6U9KnNwl9utZh+vThR+jT2tY/HwLWyBMTPTpNVTo+7Mvy3DTBBM9l99BzGTqWPfVzeawrA7hM0XCJ6UoN43q4cEBwkyqulZs6slsPNWHPaUucJMuMi/oysD3gmVY7JdayWidUkrsMbXK3VheLoeoiyticMy42sdB3H8LQ36WDFRGSlPtkzgHDjgA8ba97NwCosaT38a87wdbMDhJ3aJbguPptdThlStoB7RLT8X06XeD/6xbsWbfWsY+ZV6USjFK5AMEilVTq21WbRJWWoxYICCEJ36A6LGtLdYD3rA57RGmZK/8LjCS5V4fE63g8AmXAHX4y2PZHU+a8QFkuBU3jDyfMhlMjzJ26xlxzapR509aY570fYcrs/uhrPt26f0rh4h8=&lt;/diagram&gt;&lt;/mxfile&gt;&quot;}"></div>

## Exemples

### Exemple 1

Yousuf Karsh est né à un moment donné le 23 décembre 1908. Le moment le plus tôt auquel son évènement de naissance peut s'être produit est la première minute de ce jour (`P82a_le_début_du_début`, Date de début de la naissance « 1908-12-23T00:00:00 »), et le moment le plus tardif auquel son évènement de naissance peut s'être terminé est la dernière minute de ce jour (`P82b_la_fin_de_la_fin`, Date de fin de la naissance « 1908-12-23T23:59:59 »).

<div id="0001_100_temporal-bounds" class="example"></div>

### Exemple 2

Appius Claudius Cæcus, responsable de la construction de la Via Appia de la Rome antique, est souvent mentionné dans les sources littéraires, bien que sa date de naissance soit inconnue. La première date enregistrée à laquelle il est considéré avoir été vivant est celle où il a été nommé censeur en 312 AEC, ce qui indique que sa naissance a eu lieu avant cette date (`P82b_la_fin_de_la_fin`, Date de fin de la naissance « -312-12-31T23:59:59 ») (Humm 2005).

<div id="0001_101_temporal-bounds" class="example"></div> 

## Documentation connexe

### Modèles externes {#modeles-externes}

* Linked.art : [Time-Span](https://linked.art/model/base/#time-span-details)
* SARI : [Event Reference Data Model – Existence](https://docs.swissartresearch.net/et/event/#existence)

### Nœuds de saisie {#noeuds-de-saisie}

* [Date de début de la création du jeu de données](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-de-la-creation-du-jeu-de-donnees) \| Liste de vérification
* [Date de début de la dissolution](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-de-la-dissolution) \| Liste de vérification
* [Date de début de la formation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-de-la-formation) \| Liste de vérification
* [Date de début de la mort](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-de-la-mort) \| Liste de vérification
* [Date de début de la naissance](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-de-la-naissance) \| Liste de vérification
* [Date de début de la production](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-de-la-production) \| Liste de vérification
* [Date de début de la relation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-de-la-relation) \| Liste de vérification
* [Date de début de l'enregistrement](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-de-lenregistrement) \| Liste de vérification
* [Date de début de l'entrée dans la famille](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-de-lentree-dans-la-famille) \| Liste de vérification
* [Date de début de l'adhésion au groupe](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-de-ladhesion-au-groupe) \| Liste de vérification
* [Date de début de l'occupation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-de-loccupation) \| Liste de vérification
* [Date de début d'utilisation de l'appellation de l'actant](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-dutilisation-de-lappellation-de-lactant) \| Liste de vérification
* [Date de début du départ de la famille](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-du-depart-de-la-famille) \| Liste de vérification
* [Date de début du départ du groupe](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-du-depart-du-groupe) \| Liste de vérification
* [Date de début du floruit](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-du-floruit) \| Liste de vérification
* [Date de début du séjour](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-du-sejour) \| Liste de vérification
* [Date de début du statut social](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-du-statut-social) \| Liste de vérification
* [Date de fin de la création du jeu de données](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-de-la-creation-du-jeu-de-donnees) \| Liste de vérification
* [Date de fin de la dissolution](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-de-la-dissolution) \| Liste de vérification
* [Date de fin de la formation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-de-la-formation) \| Liste de vérification
* [Date de fin de la mort](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-de-la-mort) \| Liste de vérification
* [Date de fin de la naissance](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-de-la-naissance) \| Liste de vérification
* [Date de fin de la production](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-de-la-production) \| Liste de vérification
* [Date de fin de la relation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-de-la-relation) \| Liste de vérification
* [Date de fin de l'enregistrement](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-de-lenregistrement) \| Liste de vérification
* [Date de fin de l'entrée dans la famille](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-de-lentree-dans-la-famille) \| Liste de vérification
* [Date de fin de l'adhésion au groupe](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-de-ladhesion-au-groupe) \| Liste de vérification
* [Date de fin de l'occupation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-de-loccupation) \| Liste de vérification
* [Date de fin d'utilisation de l'appellation de l'actant](//collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-dutilisation-de-lappellation-de-lactant) \| Liste de vérification
* [Date de fin du départ de la famille](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-du-depart-de-la-famille) \| Liste de vérification
* [Date de fin du départ du groupe](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-du-depart-du-groupe) \| Liste de vérification
* [Date de fin du floruit](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-du-floruit) \| Liste de vérification
* [Date de fin du séjour](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-du-sejour) \| Liste de vérification
* [Date de fin du statut social](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-du-statut-social) \| Liste de vérification
* [Qualifiant de la date de début de la dissolution](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-de-la-dissolution) \| Liste de vérification
* [Qualifiant de la date de début de la formation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-de-la-formation) \| Liste de vérification
* [Qualifiant de la date de début de la mort](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-de-la-mort) \| Liste de vérification
* [Qualifiant de la date de début de la naissance](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-de-la-naissance) \| Liste de vérification
* [Qualifiant de la date de début de la production](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-de-la-production) \| Liste de vérification
* [Qualifiant de la date de début de la relation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-de-la-relation) \| Liste de vérification
* [Qualifiant de la date de début de l'entrée dans la famille](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-de-lentree-dans-la-famille) \| Liste de vérification
* [Qualifiant de la date de début de l'adhésion au groupe](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-de-ladhesion-au-groupe) \| Liste de vérification
* [Qualifiant de la date de début de l'occupation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-de-loccupation) \| Liste de vérification
* [Qualifiant de la date de début d'utilisation de l'appellation de l'actant](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-dutilisation-de-lappellation-de-lactant) \| Liste de vérification
* [Qualifiant de la date de début du départ de la famille](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-début-du-départ-de-la-famille) \| Liste de vérification
* [Qualifiant de la date de début du départ du groupe](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-du-depart-du-groupe) \| Liste de vérification
* [Qualifiant de la date de début du floruit](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-du-floruit) \| Liste de vérification
* [Qualifiant de la date de début du séjour](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-du-sejour) \| Liste de vérification
* [Qualifiant de la date de début du statut social](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-du-statut-social) \| Liste de vérification
* [Qualifiant de la date de fin de la dissolution](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-de-la-dissolution) \| Liste de vérification
* [Qualifiant de la date de fin de la formation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-de-la-formation) \| Liste de vérification
* [Qualifiant de la date de fin de la mort](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-de-la-mort) \| Liste de vérification
* [Qualifiant de la date de fin de la naissance](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-de-la-naissance) \| Liste de vérification
* [Qualifiant de la date de fin de la production](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-de-la-production) \| Liste de vérification
* [Qualifiant de la date de fin de la relation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-de-la-relation) \| Liste de vérification
* [Qualifiant de la date de fin de l'entrée dans la famille](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-de-lentree-dans-la-famille) \| Liste de vérification
* [Qualifiant de la date de fin de l'adhésion au groupe](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-de-ladhesion-au-groupe) \| Liste de vérification
* [Qualifiant de la date de fin de l'occupation](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-de-loccupation) \| Liste de vérification
* [Qualifiant de la date de fin d'utilisation de l'appellation de l'actant](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-dutilisation-de-lappellation-de-lactant) \| Liste de vérification
* [Qualifiant de la date de fin du départ de la famille](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-du-depart-de-la-famille) \| Liste de vérification
* [[Qualifiant de la date de fin du départ du groupe](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-du-depart-du-groupe) \| Liste de vérification
* [Qualifiant de la date de fin du floruit](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-du-floruit) \| Liste de vérification
* [Qualifiant de la date de fin du séjour](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-du-sejour) \| Liste de vérification
* [Qualifiant de la date de fin du statut social](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-du-statut-social) \| Liste de vérification

### Entités du CIDOC CRM {#entites-du-cidoc-crm}

* `E52_Intervalle_temporel` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E52)]
* `P4_a_pour_intervalle_temporel (est l'intervalle temporel de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P4)]
* `P79_a_son_début_qualifié_par` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P79)]
* `P80_a_sa_fin_qualifiée_par` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P80)]
* `P81a_la_fin_du_début`
* `P81b_le_début_de_la_fin`
* `P82a_le_début_du_début`
* `P82b_la_fin_de_la_fin`

## Discussion

### Justification

Les entités temporelles (c.-à-d. perdurantes, comme les évènements ou les périodes) sont au cœur de l'ontologie du CIDOC CRM. Elles rassemblent des actants et des objets (conceptuels ou physiques), et servent de contraintes géographiques et temporelles aux entités endurantes (c.-à-d. auxdits actants et objets). La description du temps dans le CIDOC CRM se fait toujours par le biais d'intervalles temporels et rien ne peut être défini par un seul point dans le temps (Bekiari et al. 2021, 34-46; CRM SIG 2020). Deux façons de définir les périodes sont possibles dans le CIDOC CRM : 

* En documentant la durée d'un évènement;
* En documentant les limites d'un intervalle temporel. Il y a quatre limites possibles :

  * `P82a_le_début_du_début`, qui indique que la durée d'un évènement a commencé au plus tôt à cette date;

  * `P81a_la_fin_du_début`, qui indique que la durée d'un évènement a commencé au plus tard à cette date;

  * `P81b_le_début_de_la_fin`, qui indique que la durée d'un évènement s'est terminée au plus tôt à cette date;

  * `P82b_la_fin_de_la_fin`, qui indique que la durée d'un évènement s'est terminée au plus tard à cette date.

Le diagramme ci-dessous illustre les différences entre ces quatre propriétés (voir la [documentation du CIDOC CRM](http://www.cidoc-crm.org/guidelines-for-using-p82a-p82b-p81a-p81b) pour plus d'informations) :

<a name="017_PatronConceptuel_E2EntitesTemporelles_p"></a>017_PatronConceptuel_E2EntitesTemporelles_p

<div class="mxgraph" style="max-width:100%;border:1px solid #cccccc;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;target&quot;:&quot;blank&quot;,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom layers lightbox&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;xml&quot;:&quot;&lt;mxfile host=\&quot;app.diagrams.net\&quot; modified=\&quot;2023-03-15T17:12:51.462Z\&quot; agent=\&quot;5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) draw.io/20.3.0 Chrome/104.0.5112.114 Electron/20.1.3 Safari/537.36\&quot; etag=\&quot;wILFtMIWW0QxyGuBkDxF\&quot; version=\&quot;20.3.0\&quot;&gt;&lt;diagram id=\&quot;IUiCQd-6hd5ed0ko5zII\&quot; name=\&quot;Page-1\&quot;&gt;7VpZc9owEP41TJ7a8YHBPAZy9KWZzKSdtk+MsARWY1tUljny6yvZ8iXZkMMhtJBhJtpdaSXt960u6NmTcHNLwdL/SiAKepYBNz37qmdZVk98DLjNRDMTFxRDTfGAn5BUGlKbYIjiWkVGSMDwsq70SBQhj9V0gFKyrlebk6De6xIskKZ48ECga39gyHypNQej0vAF4YUvu3atYWYIQV5ZziT2ASTrisq+7tkTSgjLSuFmggIRtzwuWbubFmsxMIoi9pwGd8O76Xr0e/g4H9hs+PPpO45uP0lsViBI5ITlYNk2jwCK4KUIJJciEnHl2GdhwCWTF7nxBgdCMrgUM0oe0YQEhKZt7cHEvR7fFJY8gnzuY334ckYI1hCRk7lFJESMbnmFdYmDI2PrVxDIdRQFgOFVHUcg6bAo3BU93BPMR2IZkrWudCNZaw+MuoeYJNRDslE17IqfgbXHEQN0gZjmiMccbCvVlqJC3D5ey2jup21c6gTNPfX7xgvrtwRQ1ueFbIa5VIG4VKUUfgGd7dfQGYLYR1ASusLtOYlYlcvpXyPLc8uxc9ocKZi4ryS16sg0nkfqrnDuvwhnLwBxjD115eJD+CkXrlT4JYTPTi5ebarGq62UWjHOprxj0M5RcWHYERWcfZx6Zyo4GhW+oXAZa3xgaMPqDKjnsVwM5nw3U1QgwItI0Igjjrh+vEKUYX5EuJSGEEMouhmvfczQwxJ4os81PwtxHSVJBNPlZSd7hE+02cmLfEOxlYDnSFZ402/gjWW0U6QGyksRGLw9GY994VT3stErk0Xdc+3D5spQR2pi99zRioc94TRnQrzkJ9tBIHJlRnlpIUp/eH3LCC4y+yr950YoROnkYmFcUgITLIr/a+IpeefqaVdsg00U7DzvXA3NtH/nZBAwnQ9e+UYaAicVf/uj458/EpzP+y13vK7O+6qjQ5/3TfMM9C6g7a6AVh0dHGjrDPQuoPtdAa06OjjQ+lPNvWuBaYCmMDtlzhKmH0SnMKnZj3KnbaNdBztwceSRsA30HdhtYF//3XZg/SWGwzibBmA6x9EUIlk6PaT6x4aUfk2/d02QI6Wn2olnmnVs+OmXd47frL5gNsF4uilo9/dDaB4SQv3GnuOFc7juSBILmMCKRKKw++UlEsb4AsUsjZVogCKP0PJBpthD+YiLTv4RKuRfHnZABfXYZLgaFUYHzWb96eCNVChYcIa9hN1RvxQ1n4e7+i7bGe75U0iHuDfkern6n2mQPV84NRqYTTRwOkl/LpY/6cguS+VvYuzrvw==&lt;/diagram&gt;&lt;/mxfile&gt;&quot;}"></div>

Dans le modèle DOPHEDA, les évènements sont définis par deux limites externes : le premier moment lors duquel un évènement peut avoir commencé et le dernier moment lors duquel il peut s'être terminé. L'intervalle entre ces deux limites peut être aussi long que nécessaire pour représenter la nature incertaine d'un élément d'information (p. ex. si l'on sait seulement que quelque chose s'est produit en 1999, l'intervalle temporel peut être aussi précis que 1999-01-01 à 1999-12-31, et ensuite spécifié à l'aide de qualifiants). 

Les propriétés `P82a_le_début_du_début` et `P82b_la_fin_de_la_fin` sont utilisées par défaut comme limites pour décrire les intervalles temporels plutôt que les propriétés `P81a_la_fin_du_début` et `P81b_le_début_de_la_fin`, car :

* Il est plus facile pour les personnes utilisant le modèle de se fier à deux propriétés plutôt qu'à quatre, surtout lorsque la distinction entre toutes ces propriétés n'est pas facile à saisir;
* Le fait de s'appuyer sur les limites extrêmes est moins susceptible de produire des erreurs, car il s'agit des propriétés les plus englobantes, une pratique qui produit également moins de nœuds de saisie pour le patron conceptuel Limites temporelles. 

Par exemple, pour dater une date de naissance, il est plus conforme à la majorité des données disponibles d'utiliser les propriétés `P82a_le_début_du_début` et `P82b_la_fin_de_la_fin`, et d'indiquer que l'évènement s'est produit à un moment donné entre la première et la dernière seconde du jour, que d'utiliser les propriétés `P81a_la_fin_du_début` et `P81b_le_début_de_la_fin`.

Toutefois, dans certains cas, l'utilisation isolée des propriétés `P82a_le_début_du_début` et `P82b_la_fin_de_la_fin` pourrait être problématique. Par exemple, l'existence d'une occupation à titre de peintre ne pourrait être connue que par la publication d'une œuvre d'art. Dans ce cas, le début de l'occupation serait daté à une époque inconnue avant la publication de cette première œuvre et au plus tard juste avant. Il n'est donc possible de documenter que le dernier moment lors duquel le début de l'occupation s'est produit; en d'autres termes, la propriété `P81a_la_fin_du_début` peut être utilisée, mais la propriété `P82a_le_début_du_début` ne peut pas l'être, car le premier instant du début de l'occupation est inconnu.

Pour des raisons de simplicité et pour limiter le nombre de nœuds du patron conceptuel Limites temporelles, le RCIP recommande de ne s'appuyer que sur les propriétés `P82a_le_début_du_début` et `P82b_la_fin_de_la_fin`. Si une personne souhaite tout de même mettre en application les propriétés `P81a_la_fin_du_début` et `P81b_le_début_de_la_fin`, une discussion avec le RCIP devrait avoir lieu au préalable (voir l'[Enjeu no 80](https://github.com/chin-rcip/collections-model/issues/80)). 

En s'appuyant sur la norme `xsd:dateTime`, certaines règles spécifiques doivent être appliquées sur les dates avant l'ère commune (AEC), mais celles-ci diffèrent selon la version de `xsd:dateTime` utilisée :

* Version 1.0 : Dans cette version, la valeur « 0001 » est interprétée comme l'année 1 EC et « -0001 » comme l'année 1 AEC. Comme il n'existe pas d'année 0, la valeur « 0000 » est considérée comme une représentation lexicale invalide (Biron & Malhotra 2004);
* Version 1.1 : Dans cette version plus récente, la valeur « 0000 » est acceptée et valide, et représente l'année 1 AEC. La valeur « -0001 » représente donc l'année 2 AEC. Cette représentation est censée simplifier l'arithmétique des intervalles, mais peut évidemment créer certaines difficultés dans l'enregistrement et la mise en correspondance des dates avant l'ère commune (Peterson et al. 2012) (voir l'[Enjeu no 81](https://github.com/chin-rcip/collections-model/issues/81)). 

Comme l’indique la Description du patron conceptuel, chaque date peut être qualifiée par l'ajout d'une chaîne de caractères attachée à une instance de `E52_Intervalle_temporel`. Cela permet plus d'expressivité dans la description du temps, car tout type d'information textuelle liée aux dates peut être ajouté, comme « Circa », « Autour de », « Incertain », etc. Cependant, comme ces qualifiants sont des chaînes de caractères et non des instances de `E55_Type`, il n'est pas possible d'utiliser directement des URI pour eux, de sorte qu'aucun vocabulaire en DOL ne peut être utilisé pour les qualifiants, même s'il est possible de limiter le nombre de termes employés comme qualifiants.

### Limitations

S'appuyer principalement sur les propriétés `P82a_le_début_du_début` et `P82b_la_fin_de_la_fin` est plus facile pour gérer les dates et moins contraignant pour les personnes qui l'utilisent; elles n'ont pas besoin de comprendre la complexité des différentes propriétés temporelles du CIDOC CRM. Toutefois, cette option par défaut est moins polyvalente sur le plan sémantique.

L'utilisation de la norme `xsd:dateTime` présente des avantages importants, car elle permet de réaliser des requêtes informatiques complexes reposant sur des dates. Toutefois, cette norme ne peut pas gérer les formats non structurés tels que les chaînes de caractères (p. ex. « la durée de la dynastie Ming »), qui doivent alors être documentés à l'aide du patron conceptuel [Données désordonnées](/collections-model/fr/modele-cible/actuel/donnees-desordonnees). De plus, la norme `xsd:dateTime` repose sur une structure année/mois/jour qui n'est pas utilisée dans de nombreuses cultures (p. ex. aux États-Unis, où la structure est année/jour/mois ou dans des cultures utilisant un calendrier différent). Cela peut entraîner des erreurs si les dates ne sont pas soigneusement mises en correspondance ou converties par le soumissionnaire.

L'utilisation de la norme `xsd:dateTime` impose également l'utilisation du calendrier grégorien pour documenter le temps, ce qui indique qu'il est obligatoire de convertir toutes les dates en leur équivalent du calendrier grégorien avant de faire la mise en correspondance des informations avec la Spécification du modèle cible. En plus de cette difficulté technique, la diversité culturelle des informations affichées est limitée.

Parce que les informations de datation sont souvent incertaines, l'utilisation de qualifiants (les propriétés `P79_a_son_début_qualifié_par` et `P80_a_sa_fin_qualifiée_par`) comme chaînes de caractères est parfois nécessaire. Cependant, cela est moins riche sémantiquement que si les qualifiants s'appuyaient sur des vocabulaires contrôlés en plus d'être interprétables uniquement par des humains. Par conséquent, ces informations sont perdues dans le contexte des requêtes quantitatives.

Ce patron conceptuel ne représente pas des chronologies relatives et sa fonction est d'aider à traduire des dates connues dans un système de dates. Il existe des propriétés dédiées à la représentation de la chronologie relative dans le CIDOC CRM, mais elles n'ont pas été mobilisées ici (Bekiari 2021, 43-47) (voir l'[Enjeu no 79](https://github.com/chin-rcip/collections-model/issues/79)).

### Enjeux connexes sur GitHub

* [Enjeu n° 51 « Devrions-nous essayer d'éviter les qualifiants de date? »](https://github.com/chin-rcip/collections-model/issues/51) (en anglais)
* [Enjeu no 79 « Un modèle de chronologie relative est-il nécessaire? »](https://github.com/chin-rcip/collections-model/issues/79) (en anglais)
* [Enjeu n° 80 « Comment gérer l'utilisation de P81a et P81b dans le modèle cible? »](https://github.com/chin-rcip/collections-model/issues/80) (en anglais)
* [Enjeu n° 81 « Comment utiliser XSD:dateTime pour les dates AEC? »](https://github.com/chin-rcip/collections-model/issues/81) (en anglais)

### Cas limites

#### Exemple 1 {#cas-limites-exemple-1}

La production de certains objets, comme le bol en porcelaine blanche et bleue no G01.2.20 de la période Wanli de la dynastie Ming du Gardiner Museum (Gardiner Museum 2021), a pu être datée avec le nom d'une période alors que la date de la production elle-même est inconnue. Cette utilisation du nom d'une période pour délimiter l'intervalle temporel d'un évènement pourrait également se produire pour des périodes qui n'ont pas de limites chronologiques claires (c.-à-d. dont les limites pourraient être mises à jour ou documentées plus précisément par des recherches supplémentaires sur la période plutôt que sur l'objet). Ce patron conceptuel ne permet pas une telle documentation relative, et le nom d'une période doit être modélisé selon le patron conceptuel [Données désordonnées](/collections-model/fr/modele-cible/actuel/donnees-desordonnees) (voir l'[Enjeu no 79](https://github.com/chin-rcip/collections-model/issues/79) pour des discussions sur la chronologie relative).

#### Exemple 2 {#cas-limites-exemple-2}

Comme la date associée à la propriété `P82b_la_fin_de_la_fin` est inclusive, la date de fin est incluse dans l'intervalle temporel décrit (voir [Linked.art – Enjeu no 371](https://github.com/linked-art/linked.art/issues/371) et [CRM SIG – Enjeu no 417](http://www.cidoc-crm.org/Issue/ID-417-beginofthebegin-endoftheend-is-excluded-from-time-range)). Cela peut entraîner une certaine confusion lorsque les évènements se poursuivent dans les tout derniers instants. Par exemple, il est impossible de documenter l'intervalle temporel qui marque la fin de l'année de naissance de Yousuf Karsh. Le moment associé à `P82b_la_fin_de_la_fin` serait indiqué par la valeur « 1908-12-31T23:59:59 » et, par conséquent, tout ce qui s'est passé dans les derniers instants de l'année 1908 ne serait pas pris en compte par le modèle. Pour inclure les derniers moments de l'année 1908, il faudrait utiliser la valeur « 1909-01-01T00:00:00 », mais dans ce cas, le début de 1909 ferait partie de l'évènement de fin d'année de 1908. Les évènements qui impliquent un changement d'une période à une autre peuvent donc être classés de différentes manières selon la compréhension de la personne qui saisit l'information.

## Bibliographie

Bekiari, Chryssoula, George Bruseker, Martin Doerr, Christian-Emil Ore, Stephen Stead et Athanasios Velios, éds. *Definition of the CIDOC Conceptual Reference Model*. Documentations du CIDOC CRM, 7.1.1. Paris, FR-IDF : Conseil international des musées (ICOM), 2021. [http://www.cidoc-crm.org/sites/default/files/cidoc_crm_v.7.1.1.pdf](http://www.cidoc-crm.org/sites/default/files/cidoc_crm_v.7.1.1.pdf).

Biron, Paul V., et Malhotra Ashok. *XML Schema Part 2: Datatypes Second Edition*. Recommandation du W3C, 2004. [https://www.w3.org/TR/xmlschema-2/#dateTime](https://www.w3.org/TR/xmlschema-2/#dateTime).

CIDOC CRM Special Interest Group. « Issue 417: begin_of_the_begin/end_of_the_end is Excluded from Time Range? ». *CIDOC CRM Issues*. 2020. [http://www.cidoc-crm.org/Issue/ID-417-beginofthebegin-endoftheend-is-excluded-from-time-range](http://www.cidoc-crm.org/Issue/ID-417-beginofthebegin-endoftheend-is-excluded-from-time-range).

Emery, Nina, Ned Markosian, et Meghan Sullivan. « Time ». *The Stanford Encyclopedia of Philosophy*. Stanford, US-CA : Metaphysics Research Lab, Stanford University, 2020.

Fuentes, Catherine M. Mitchell. « Dreamtime, Arboriginal ». *Encyclopedia of Time: Science, Philosophy, Theology, & Culture*, édité par H. James Birx. Thousand Oaks, US-CA : Sage Publications, 2009 : 346-348.

Gardiner Museum. *Bowl with Fruit and Lotus*. Gardiner Museum. 2021. [http://emuseum.gardinermuseum.com/objects/2005/bowl-with-fruit-and-lotus](http://emuseum.gardinermuseum.com/objects/2005/bowl-with-fruit-and-lotus).

Hornung, Erik, Rolf Krauss, et David A. Warburton, éds. *Ancient Egyptian Chronology*. Leiden, NL-ZH; Boston, US-MA : Brill, 2006.

Humm, Michel. « Les sources littéraires sur Appius Claudius Cæcus ». *Appius Claudius Cæcus : La République accomplie*. Rome, ITA-RM : Publications de l'École française de Rome, 2005 : 35-97.

Linked.art. « Issue 371: End_of_the_end Is Included, Not Excluded ». Issues. GitHub. 2020. [https://github.com/linked-art/linked.art/issues/371](https://github.com/linked-art/linked.art/issues/371).

Peer, Bethany. « Calendar, Mayan ». *Encyclopedia of Time: Science, Philosophy, Theology, & Culture*, édité par H. James Birx. Thousand Oaks, US-CA : Sage Publications, 2009 : 134-135.

Peterson, David, Shudi (Sandy) Gao, Ashok Malhotra, C. M. Sperberg-McQueen et Henry S. Thompson. *W3C XML Schema Definition Language (XSD) 1.1 Part 2: Datatypes*. Recommandation du W3C, 5 avril 2012. [https://www.w3.org/TR/xmlschema11-2/#dateTime](https://www.w3.org/TR/xmlschema11-2/#dateTime).

Phillips, Jocelyn. « Calendar, Astronomical ». *Encyclopedia of Time: Science, Philosophy, Theology, & Culture*, édité par H. James Birx. Thousand Oaks, US-CA : Sage Publications, 2009 : 124-125.

Pollard, A. M. « Measuring the Passage of Time: Achievements and Challenges in Archæological Dating ». *The Oxford Handbook of Archæology*, édité par Chris Gosden, Barry Cunliffe et Rosemary A. Joyce. New York, US-NY; Oxford, UK-OXF : Oxford University Press, 2009 : 123-139.

Railways Archive. « Statutes (Definition of Time) Act ». *Archives des chemins de fer*. 2021. [https://www.railwaysarchive.co.uk/docsummary.php?docID=929](https://www.railwaysarchive.co.uk/docsummary.php?docID=929).

Richards, E. G. *Mapping Time: The Calendar and Its History*. Oxford, UK-OXF : Oxford University Press, 1999.

Salmon, Helena Theresa. « Calendar, Islamic ». *Encyclopedia of Time: Science, Philosophy, Theology, & Culture*, édité par H. James Birx. Thousand Oaks, US-CA : Sage Publications, 2009 : 131-132.

Savitt, Steven. « Being and Becoming in Modern Physics ». *The Stanford Encyclopedia of Philosophy*. Stanford, US-CA : Metaphysics Research Lab, Stanford University, 2017. [https://plato.stanford.edu/entries/spacetime-bebecome/](https://plato.stanford.edu/entries/spacetime-bebecome/).

Simonton, Michæl J. « Calendar, Megalithic ». *Encyclopedia of Time: Science, Philosophy, Theology, & Culture*, édité par H. James Birx. Thousand Oaks, US-CA : Sage Publications, 2009 : 137-141.

Smyntyna, Olena V. « Chronology ». *Encyclopedia of Time: Science, Philosophy, Theology, & Culture*, édité par H. James Birx. Thousand Oaks, US-CA : Sage Publications, 2009 : 183-186.

Wikipedia. « Calendar Era ». *Wikipedia*. San Francisco, US-CA : Wikipedia, 2022. [https://en.wikipedia.org/w/index.php?title=Calendar_era&oldid=1096791211](https://en.wikipedia.org/w/index.php?title=Calendar_era&oldid=1096791211).

