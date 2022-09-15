---
layout: page
language: fr
title: Floruit
permalink: /fr/modele-cible/actuel/floruit
other_link: /en/target-model/current/flourishing
sidebar: mc22
date: 2022-06-30
description: La Spécification du modèle cible des actants modélise sémantiquement les actants dans un contexte patrimonial. Les patrons conceptuels les plus pertinents pour la vie des actants sont présentés avec des diagrammes et des exemples qui les illustrent, ainsi qu'un compte rendu et une explication des décisions pertinentes qui ont été prises lors de l'élaboration desdits patrons conceptuels. Il s'agit d'une documentation théorique qui n'a jamais été testée ou mise en application.
---

## Aperçu {#apercu}

Ce patron conceptuel peut être utilisé pour représenter les informations relatives à la période de productivité et d'excellence ou d'influence la plus élevée d'un actant dans un domaine au cours de sa vie. Cette période est souvent appelée « floruit ». Ce patron conceptuel comprend : 

* Les dates indiquant le début et la fin d'un floruit; 
* Le lieu le plus associé à un floruit. 

Elle concerne spécifiquement le floruit dans le contexte des personnes et des groupes de personnes, et non pas la nature du floruit. Ce patron conceptuel ne comprend pas : 

* La période de reconnaissance et d'influence d'artistes;
* Le floruit de mouvements stylistiques (p. ex. la période durant laquelle les principes d'un mouvement stylistique sont les plus visibles et les plus courants dans les artefacts);
* Le floruit de phénomènes (p. ex. un certain type d'exercice qui était le plus utilisé à un moment spécifique); 
* Le floruit d'objets (p. ex. la période durant laquelle un texte littéraire était le plus largement reconnu comme un chef-d'œuvre ou un texte important);
* Le floruit de concepts ou de périodes (p. ex. l'avènement de la science moderne ou de l'ère industrielle);
* Les spécialistes effectuant l'évaluation du floruit; 
* La discipline dans le contexte de laquelle le floruit est évalué;
* La documentation de l'occupation d'un actant (le patron conceptuel [Occupation](/collections-model/fr/modele-cible/actuel/occupation) doit plutôt être utilisé).

## Introduction et contexte

### Historique théorique {#historique-theorique}

Plusieurs disciplines du patrimoine s'intéressent à la période d'activité la plus reconnue qui est attribuée à une personne ou à un groupe. Puisque chaque discipline a un objectif spécifique, la façon dont le concept est compris et utilisé varie considérablement. Par exemple, en généalogie, il est le plus souvent associé à la période durant laquelle un actant était actif, et est utilisé pour indiquer quand il est établi que cet actant était en vie s'il n'y a pas d'enregistrement de sa naissance et/ou de sa mort (World Heritage Encyclopedia 2021). 

En histoire de l'art et en littérature, le floruit d'un·e artiste, créateur·rice, penseur·euse ou mouvement désigne la période durant laquelle il ou elle produisait ses œuvres les plus accomplies ou les plus connues. Le floruit n'est donc pas identifié par l'artiste ou le mouvement lui-même; il s'agit plutôt d'une évaluation réalisée par les historiens·nes de manière rétrospective et qualitative (Naas 2016, 1). 

Puisqu'il s'agit d'une évaluation spécifique, le floruit est souvent utilisé pour résoudre les ambiguïtés entre les actants, tout comme le patron conceptuel [Naissance et mort d'une personne](/collections-model/fr/modele-cible/actuel/naissance-et-mort-dune-personne) (c.-à-d. que deux personnes différentes peuvent avoir le même nom par hasard, ou une seule personne peut être associée à plusieurs noms ou orthographes d'un nom) comme elle peut être utilisée pour confirmer l'identité d'une personne (OCLC 2019, 4).

### Énoncé des besoins {#enonce-des-besoins}

L'utilisation de ce concept par plusieurs disciplines établit un besoin de représenter plusieurs de ses aspects et de ses éléments associés. En particulier, il peut s'appliquer non seulement à des personnes et à des groupes de personnes, mais aussi à des mouvements stylistiques et à des œuvres culturelles, car ces derniers peuvent aussi connaître des périodes de renouveau ou être largement reconnus et célébrés à une date différente de celle de leur publication initiale (Naas 2016, 1). Il est donc nécessaire d'indiquer à quels aspects et éléments associés le floruit se rapporte, les années durant lesquelles il se produit ainsi que le lieu auquel il est le plus associé. 

## Description du patron conceptuel

Le patron conceptuel actuel ne s'applique qu'aux actants, de sorte que la personne ou le groupe de personnes dont le floruit est représenté est identifié comme une instance de `E39_Actant` liée par la propriété `P11_a_eu_pour_actant_participant` à une instance de `E5_Évènement`, qui est le nœud central de ce patron conceptuel et représente le floruit lui-même :

* L'évènement du floruit est qualifié comme tel par une instance de `E55_Type` (un nœud doté d’un qualifiant spécifié) portant le libellé « Floruit » qui est liée à l'instance de `E5_Évènement` par la propriété `P2_a_pour_type`;
* L'évènement du floruit (l'instance de `E5_Évènement`) est situé dans le temps à l'aide du patron conceptuel [Limites temporelles](/collections-model/fr/modele-cible/actuel/limites-temporelles) par la propriété `P4_a_pour_intervalle_temporel` avec des valeurs extraites des nœuds de saisie [Date de début du floruit](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-du-floruit), [Qualifiant de la date de début du floruit](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-du-floruit), [Date de fin du floruit](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-du-floruit) et [Qualifiant de la date de fin du floruit](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-du-floruit);
* L'évènement est également situé dans l'espace en reliant l'instance de `E5_Évènement` à la valeur du [Lieu du floruit](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#lieu-du-floruit) (une instance de `E53_Lieu`) par le biais de la propriété `P7_a_eu_lieu_dans`.

## Diagramme

<a name="037_PatronConceptuel_Floruit_p"></a>037_PatronConceptuel_Floruit_p

<iframe frameborder="0" style="width:100%;height:500px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=037_PatronConceptuel_Floruit_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1740thXfym6MlrdhKM4dfDtYR8TfuK7Ky%26export%3Ddownload"></iframe>

## Exemples

### Exemple 1

Yousuf Karsh est considéré comme l'un des plus importants photographes du floruit du photojournalisme dans les années 1940 (`P82a_le_début_du_début`, Date de début du floruit « 1940-01-01T00:00:00 ») et 1950 (`P82b_la_fin_de_la_fin`, Date de fin du floruit « 1959-12-31T23:59:59 »), travaillant avec des magazines tels que *Life* (Allen 2014).

<div id="0001_100_flourishing" class="example"></div>

### Exemple 2

Cyril Henry Barraud, un peintre anglais qui a participé à la Première Guerre mondiale en tant qu'artiste de guerre pour l'armée canadienne, est considéré par Artistes au Canada comme ayant prospéré entre 1913 (`P82a_le_début_du_début`, Date de début du floruit) et 1915 (`P82b_la_fin_de_la_fin`, Date de fin du floruit) (Patrimoine canadien, Gouvernement du Canada 2021). 

<div id="0001_114_flourishing" class="example"></div>

### Exemple 3

Le floruit artistique de Tom Thomson est considéré comme ayant eu lieu au Canada (`P7_a_eu_lieu_dans`, Lieu du floruit) et s'être déroulé de mars 1916 (`P82a_le_début_du_début`, Date de début du floruit) jusqu'à sa mort le 8 juillet 1917 (`P82b_la_fin_de_la_fin`, Date de fin du floruit) (Silcox 2015, 16).

<div id="0001_115_flourishing" class="example"></div>

## Documentation connexe

### Modèles externes {#modeles-externes}

* Linked.art : [Active Dates](https://linked.art/model/actor/#active-dates)
* SARI : [Person Reference Data Model – Activities](https://docs.swissartresearch.net/et/persons/#activities)
* SARI : [Group Reference Data Model – Activities](https://docs.swissartresearch.net/et/group/#activities) 

### Nœuds de saisie {#noeuds-de-saisie}

* [Date de début du floruit](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-du-floruit) \| Liste de vérification
* [Date de fin du floruit](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-du-floruit) \| Liste de vérification
* [Lieu du floruit](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#lieu-du-floruit) \| Liste de vérification
* [Qualifiant de la date de début du floruit](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-debut-du-floruit) \| Liste de vérification
* [Qualifiant de la date de fin du floruit](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#qualifiant-de-la-date-de-fin-du-floruit) \| Liste de vérification

### Entités du CIDOC CRM {#entites-du-cidoc-crm}

* `E5_Évènement` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E5)]
* `E39_Actant` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E39)]
* `E52_Intervalle_temporel` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E52)]
* `E53_Lieu` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E53)]
* `E55_Type` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E55)]
* `P2_a_pour_type (est_le_type_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P2)]
* `P4_a_pour_intervalle_temporel (est_l’intervalle_temporel_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P4)]
* `P7_a_eu_lieu_dans (a_été_témoin_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P7)]
* `P11_a_eu_pour_actant_participant (a_participé_à)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P11)]
* `P79_a_son_début_qualifié_par` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P79)]
* `P80_a_sa_fin_qualifiée_par` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P80)]
* `P82a_le_début_du_début`
* `P82b_la_fin_de_la_fin`

## Discussion

### Justification

Étant donné que le développement actuel du modèle est axé sur les actants plutôt que sur les objets et les collections, le floruit des agents non humains (p. ex. les mouvements artistiques, la vie intelligente, etc.) ne peut pas être documenté pour le moment. C'est pourquoi le floruit est lié à une instance de `E39_Actant` plutôt qu'à une autre entité. 

Le floruit aurait pu être modélisé comme une instance de `E7_Activité` liée à l'actant par la propriété `P14_a_été_effectué_par`, mais cela aurait impliqué de considérer le floruit comme une pratique active et intentionnelle de la part de l'actant. Parce que le floruit d'un actant est typiquement un évènement subjectif déterminé *a posteriori* par les chercheurs·ses, il ne peut pas être réalisé intentionnellement et activement. Il est donc plus juste de considérer l'actant comme un participant à son propre floruit, ce qui est représenté dans ce patron conceptuel par une instance de `E5_Évènement` liée à l'actant concerné par la propriété `P11_a_eu_pour_actant_participant`. Malheureusement, les spécialistes qui procèdent à l'évaluation du floruit ne sont pas actuellement pris en compte par ce patron conceptuel au-delà de la provenance plus générique de l'information (à travers l'utilisation du patron conceptuel [Provenance du jeu de données](/collections-model/fr/modele-cible/actuel/provenance-du-jeu-de-donnees) ou [Provenance de l’enregistrement](/collections-model/fr/modele-cible/actuel/provenance-de-lenregistrement)). 

### Limitations

L'instance du floruit est qualifiée dans ce patron conceptuel par une instance de `E55_Type` contenant l'URI de la valeur « Floruit », afin qu'elle puisse être facilement récupérée dans une requête SPARQL. Cependant, aucun autre terme de vocabulaire ne peut être associé à cette instance du floruit. Il n'est donc pas possible de décrire dans quel domaine un actant a connu une période de floruit. Si le besoin d'un tel terme descriptif se fait sentir, une autre instance de `E55_Type`, liée à une instance de `E5_Évènement` par la propriété `P2_a_pour_type`, pourrait être ajoutée au patron conceptuel.

### Enjeux connexes sur GitHub

* [Enjeu no 2 « Dates du floruit »](https://github.com/chin-rcip/collections-model/issues/2) (en anglais)

### Cas limites

Un·e artiste peut connaître plus d'un seul floruit au cours de sa vie, notamment si il ou elle a exercé plusieurs occupations de domaines différents, a employé différents médiums ou a exercé une seule occupation dans un seul domaine et employé un seul médium, mais que ses périodes de production étaient entrecoupées de périodes d'inactivité. Par exemple, Marc Séguin a connu du succès tant dans le domaine visuel que littéraire et cinématographique. La manière dont chacun de ces floruits serait représenté n'est pas claire. De plus, le floruit en sculpture de Jean Paul Riopelle serait considéré comme différent de son floruit en peinture. Un autre exemple : Harper Lee a été largement reconnue comme une auteure accomplie après la publication de *To Kill a Mockingbird*, mais a très peu publié pendant une longue période avant d'écrire sa suite *Go Set a Watchman* (Éditeurs de la Encyclopædia Britannica 2021). On peut considérer qu'il s'agit soit d'une longue période de floruit couvrant la majeure partie de sa carrière de romancière, soit de deux années de floruit distinctes.

## Bibliographie

Allen, Evanne. « Tales of a Historic Career: Yousuf Karsh ». *National Portrait Gallery, Smithsonian* (blogue). 2014. [https://npg.si.edu/blog/tales-historic-career-yousuf-karsh](https://npg.si.edu/blog/tales-historic-career-yousuf-karsh).

Art & Architecture Thesaurus. « Flourishing ». *Art & Architecture Thesaurus Online Full Record Display*. 1er octobre 2019. [http://www.getty.edu/vow/AATFullDisplay?find=flourished&logic=AND&note=&english=N&prev_page=1&subjectid=300393178][http://www.getty.edu/vow/AATFullDisplay?find=flourished&logic=AND&note=&english=N&prev_page=1&subjectid=300393178].

Bruseker, George, et Nicola Carboni. « Digital Object Reference Data Model (SARI Documentation) ». *Swiss Art Research Infrastructure*. 8 décembre 2020. [https://docs.swissartresearch.net/et/do/](https://docs.swissartresearch.net/et/do/).

Doerr, Martin, et Christian Emil Ore, éds. *Definition of the CIDOC Conceptual Reference Model*. Documentations du CIDOC CRM, 7.0.1. Paris, FR-IDF : Conseil international des musées (ICOM), 2020. [http://www.cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.0.1_%2018-10-2020.pdf](http://www.cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.0.1_%2018-10-2020.pdf).

Dunn, Stuart, et Simon Mahoney, éds. *The Digital Classicist. Bulletin of the Institute of Classical Studies Supplement 122*. Londres, UK-LDN : University of London Press, 2019 [2013]. [https://library.oapen.org/handle/20.500.12657/39396](https://library.oapen.org/handle/20.500.12657/39396).

Éditeurs de la Encyclopædia Britannica. « Harper Lee ». *Encyclopædia Britannica*. Londres, UK-LDN : Encyclopædia Britannica, 2021a. [https://www.britannica.com/biography/Harper-Lee](https://www.britannica.com/biography/Harper-Lee).

–––. « Johann Sebastian Bach ». *Encyclopædia Britannica*. Londres, UK-LDN : Encyclopædia Britannica, 2021b. [https://www.britannica.com/biography/Johann-Sebastian-Bach](https://www.britannica.com/biography/Johann-Sebastian-Bach).

Free Dictionary. « Flourishing ». *The Free Dictionary*. Huntingdon Valley, US-PA : Farlex, 2019. [https://www.thefreedictionary.com/flourishing](https://www.thefreedictionary.com/flourishing).

Linked.art. *Linked Art Data Model*. Linked.art, 2021. [https://linked.art/model/index.html](https://linked.art/model/index.html).

Merriam-Webster. « Floruit ». *Merriam-Webster*. Springfield, US-MA : Merriam-Webster, 2021. [https://www.merriam-webster.com/dictionary/floruit](https://www.merriam-webster.com/dictionary/floruit).

Naas, Michael. « Floruit ». *Derrida Today* 9, no. 1 (2016) : 1-20. [https://doi.org/10.3366/drt.2016.0116](https://doi.org/10.3366/drt.2016.0116).

OCLC. *Virtual International Authority File Guidelines*. Dublin, US-OH : OCLC, 2019 [2015]. [https://www.oclc.org/content/dam/oclc/viaf/VIAF%20Guidelines.pdf](https://www.oclc.org/content/dam/oclc/viaf/VIAF%20Guidelines.pdf).

Patrimoine canadien, Gouvernement du Canada. « Barraud, Cyril Henry ». *Artistes au Canada*. Ottawa, CA-ON : Gouvernement du Canada, 2021. [https://app.pch.gc.ca/application/aac-aic/artiste_detailler_bas-artist_detail_bas.app?lang=fr&qlang=en&rID=34489&pID=1&fID=2&an=barraud&ps=50&sort=AM_ASC](https://app.pch.gc.ca/application/aac-aic/artiste_detailler_bas-artist_detail_bas.app?lang=fr&qlang=en&rID=34489&pID=1&fID=2&an=barraud&ps=50&sort=AM_ASC).

Silcox, David P. *Tom Thomson : Sa vie et son œuvre. Projet de livre d'art canadien en ligne*. Toronto, CA-ON : Institut de l'art canadien, 2015. [https://www.aci-iac.ca/fr/livres-dart/tom-thomson/](https://www.aci-iac.ca/fr/livres-dart/tom-thomson/).

Whitney Museum of American Art. « David Wojnarowicz: History Keeps Me Awake at Night ». *Whitney Exhibitions and Events* (blogue). 2018. [https://whitney.org/exhibitions/david-wojnarowicz](https://whitney.org/exhibitions/david-wojnarowicz).

Wikipedia. « Floruit ». *Wikipedia*. San Francisco, US-CA : Wikipedia, 1er octobre 2019. [https://en.wikipedia.org/w/index.php?title=Floruit&oldid=917796873](https://en.wikipedia.org/w/index.php?title=Floruit&oldid=917796873).

World Heritage Encyclopedia. « Floruit ». *Projet Gutenberg*. 28 juin 2021. [http://www.self.gutenberg.org/articles/eng/floruit](http://www.self.gutenberg.org/articles/eng/floruit).

