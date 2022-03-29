---
layout: page
language: fr
title: 101 - Choix d’un modèle de DOL
permalink: /fr/ressources/actuel/mode-demploi/choix-modele-dol
other_link: /en/resources/current/how-to/choosing-lod-model
sidebar: choixmodele
group: ressources
subgroup: mode d'emploi
date: 2022-03-22
description: Ce document présente un aperçu des éléments à prendre en compte dans le choix d’un modèle de données ouvertes et liées. 
---

**Version 1.0**

**Auteure** : Marie-Pier Blain, Karine Léonard Brouillet

**Public visé** : Grand public

**Date de création** : 2021-05-10

**Dernière mise à jour** : 2022-03-22

**Résumé** : Ce document présente un aperçu des éléments à prendre en compte dans le choix d’un modèle de données ouvertes et liées. 

## Choix d’un modèle {#choix-dun-modele}

Lors de la mise en place d’un écosystème de données ouvertes et liées (DOL), le développement d’une architecture de systèmes internes doit reposer en grande partie sur la sélection d’un ou de plusieurs modèles de données compatibles destinés à cartographier et à comprendre le paysage de l’information locale. Deux grandes options sont possibles à cet égard : 

* Choisir une ou plusieurs ontologies et développer un modèle appliqué dédié à un usage interne; 

* Sélectionner un modèle de données ou une combinaison de modèles de données répondant aux besoins de l’organisation.

Dans les deux cas, les critères présentés ci-dessous doivent être pris en considération (bien que dans le premier cas, il s’agisse d’exigences de développement plutôt que d’exigences de sélection). 

Il est probable qu’une organisation doive combiner plusieurs modèles ciblés sur les domaines que son paysage informationnel englobe. Ce faisant, les critères ci-dessous restent pertinents dans la sélection desdits modèles, même s’il est important de s’assurer que les modèles sélectionnés soient compatibles les uns avec les autres et puissent être liés quand et si cela est pertinent. 

Dans tous les cas, le [modèle](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire%23modele-nom-masculin) le mieux adapté à un projet est déterminé par plusieurs éléments relatifs à son objectif, sa portée et ses caractéristiques. En tant que tel, le choix d’un modèle dépend fortement de l’évaluation du projet lui-même pour s’assurer de sa concordance avec les besoins déclarés d’une organisation. La section suivante met l’accent sur les éléments qu’il pourrait être utile de prendre en compte lors de l’évaluation d’un projet du point de vue de la sélection du modèle de données. 

Les éléments suivants ne constituent pas des lignes directrices pour l’évaluation d’un projet dans son ensemble et, si ces informations peuvent être utiles à l’établissement d’une charte de projet, elles ne doivent pas être considérées comme suffisantes pour une telle entreprise. Le choix d’un modèle est également influencé par les caractéristiques précises et distinctives des organisations qui doivent, bien entendu, tenir compte de leur profil unique. 

### Évaluation du projet {#evaluation-du-projet}

#### Objectif du projet

L’utilisation de DOL dans une organisation peut être marquée par plusieurs éléments, notamment l’état de préparation technologique, la disponibilité des ressources et la culture organisationnelle. Ainsi, chaque organisation doit [déterminer quelle pourrait être l’utilité fondamentale des DOL](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/dol-avantages-defis) pour elle-même, tant au niveau de l’organisation que du projet. Les objectifs fréquents de la mobilisation de DOL dans le secteur du patrimoine sont les suivants : 

* Acquérir une compréhension pratique des DOL et renforcer les capacités à l'interne;

* Développer des protocoles d’échange avec les partenaires; 

* Moderniser l’infrastructure documentaire afin que les documents soient plus complets et plus faciles à consulter;

* Gagner en visibilité en ligne (pour une collection ou une institution).  

#### Ressources du projet

De même, l’organisation qui choisit un modèle doit tenir compte de ses ressources et de ses contraintes particulières pour déterminer la meilleure façon d’établir son écosystème de DOL. Quatre approches de développement sont couramment utilisées par les organisations patrimoniales : 

* Utiliser un modèle appliqué « prêt à l’emploi » sans l’adapter :

  * Il s’agit de l’approche la moins exigeante en termes de modélisation, car elle ne nécessite que le maintien de la conformité avec la version actuelle d’une seule norme; 

  * Seuls les classes, propriétés, patrons conceptuels et/ou champs existants peuvent être utilisés, et ils doivent être utilisés de la manière dont ils ont été prévus par la personne qui a développé le modèle, ce qui peut nécessiter des ressources pour adapter les données (ou limiter la portée du projet au modèle lui-même);

  * Cela présente l’inconvénient de permettre peu de personnalisation, de sorte que le modèle doit raisonnablement répondre aux besoins des projets; 

  * Le développement d’un tel écosystème est le plus souvent le fait d’organisations de petite taille ayant des besoins généraux (p. ex. des centres communautaires). 

* Utiliser un modèle appliqué « prêt à l’emploi » et l’adapter le moins possible tout en permettant la création de nouvelles classes, propriétés, patrons conceptuels et/ou champs en conformité avec la norme sur laquelle il est basé (c.-à-d. une ontologie) pour simplifier le processus de conversion des données :

  * Il s’agit d’une approche modérément exigeante, alors que de nouvelles classes, propriétés, patrons conceptuels et/ou champs sont créés lorsqu’un besoin spécifique qui ne peut être satisfait autrement émerge;

  * Cela présente l’avantage de répondre à des besoins précis, mais les nouveaux patrons conceptuels, classes, propriétés et/ou champs ne seront probablement pas riches sur le plan sémantique en dehors de l’organisation;

  * Cela nécessite une capacité à standardiser les classes, propriétés, patrons conceptuels et/ou champs locaux en les définissant clairement d’une manière qui correspond au reste du modèle afin qu’ils puissent être utilisés par les parties prenantes internes et externes; 

  * Cela nécessite une capacité à faire connaître les classes, propriétés, patrons conceptuels et/ou champs locaux afin qu’ils soient utilisés par les parties prenantes internes et externes; 

  * Cela nécessite une capacité à maintenir les classes, propriétés, patrons conceptuels et/ou champs locaux à jour et en phase avec le modèle « principal » afin qu’ils puissent être utilisés par les parties prenantes internes et externes; 

  * Le développement d’un tel écosystème est le plus souvent le fait d’organisations de taille moyenne ayant des besoins précis (p. ex. des musées spécialisés). 

* Utiliser plusieurs modèles compatibles tout en prévoyant du temps et des ressources pour actualiser régulièrement les liens entre eux afin de tenir compte des mises à jour et/ou des modifications apportées aux modèles. Cette approche peut inclure la création de nouvelles classes et/ou propriétés et, dans ce cas, les considérations mentionnées ci-dessus devraient être prises en compte. De plus : 

  * Il s’agit d’une approche très exigeante, car elle nécessite l’élaboration d’un modèle principal pour standardiser la correspondance entre les modèles; 

  * Cela nécessite une équipe dédiée à la mise à jour et à la maintenance du ou des modèles mis en œuvre et des liens entre eux; 

  * Le développement d’un tel écosystème est le plus souvent le fait d’organisations plus importantes ayant des besoins variés, mais interreliés (p. ex. les musées encyclopédiques). 

* Élaborer un modèle à l'interne : 

  * Il s’agit de l’approche la plus exigeante, car elle nécessite le dévouement de toute une équipe à l’acquisition d’expertise, à l’élaboration du modèle et de sa documentation, aux tests, à la diffusion, etc.; 

  * Cela nécessite une capacité à standardiser et à définir clairement le modèle afin qu’il puisse être utilisé par les parties prenantes internes et externes; 

  * Cela nécessite une capacité à faire connaître et à rendre disponible le modèle afin qu’il puisse être utilisé par les parties prenantes internes et externes; 

  * Cela nécessite la capacité de contextualiser le modèle, de le maintenir et d’offrir un soutien aux personnes et aux machines l'utilisant; 

  * Le développement d’un tel modèle appliqué est le plus souvent le travail d’une organisation (p. ex. des centres de recherche) au service de plusieurs parties prenantes de plus petite taille dont les besoins et les exigences doivent être pris en considération dans le processus. 

#### Objectifs de la sémantisation {#objectifs-de-la-semantisation}

La détermination de l’objectif du projet a un impact direct sur le domaine que le modèle doit couvrir. Il s’agit donc d’une étape fondamentale qu’il ne faut pas sous-estimer, car elle détermine également qui est concerné et quelle est la portée du projet en termes de livrables et de ressources. Par exemple, les objectifs ci-dessus peuvent prendre différentes formes lorsqu’ils sont considérés comme des projets en soi : 

* Acquérir une compréhension pratique des DOL et renforcer les capacités internes en réalisant une preuve de concept à petite échelle dans une section précise avec l’intention d’adopter à terme les données ouvertes à grande échelle dans toute l’organisation :

  * Un projet testant l’évolutivité doit adopter un modèle qui répondra aux besoins du projet final plutôt qu’à ceux de la preuve de concept; 

  * Si le renforcement des capacités est l’un des objectifs du projet, il convient de sélectionner un modèle soigneusement documenté (c.-à-d. avec des exemples, des ressources, etc.); 

  * Si le développement de partenariats pour l’harmonisation et le partage des données est un objectif final du projet, il est important de donner la priorité à l’ouverture des données pertinentes et, à ce titre, le modèle doit être déterminé en fonction de ces données.

* Développer des protocoles d’échange avec des partenaires par l’entremise d’un projet pilote : 

  * Un projet de collaboration en matière de test doit adopter un modèle qui couvre les besoins de toutes les parties concernées; 

  * Il est important de s’assurer que le modèle de DOL déjà utilisé par un partenaire soit compatible avec celui choisi par le projet (le cas échéant). 

* Moderniser l’infrastructure documentaire pour que les documents soient plus riches (grâce à l’enrichissement et à l’externalisation ouverte, par exemple) en ciblant une collection à enrichir par l’externalisation ouverte : 

  * Un projet testant l’enrichissement devrait adopter un modèle qui couvre plusieurs domaines pertinents afin de pouvoir s’adapter à la variété des informations qui pourraient être soumis par les utilisateurs·rices; 

  * Un modèle qui peut accueillir du texte libre est également utile dans ce contexte;

  * Un modèle pouvant être consulté avec des requêtes simples et complexes facilite le travail et favorise l’efficacité dans le cadre d’un tel projet. 

* Gagner en visibilité en ligne (pour une collection ou une institution) en créant ou en réutilisant des URI pour identifier ou décrire des artefacts, en les soumettant à de grands dépôts comme Wikidata et en les soutenant activement : 

  * Un projet axé sur la création d'URI ne garantira pas tant la visibilité que l’accessibilité et, à ce titre, le modèle choisi doit être sélectionné en fonction de son utilisation par le reste de la communauté plus que de l’enrichissement des jeux de données originaux; 

  * Les dépôts plus importants et bien connus sont utiles pour les URI, mais n’apportent peut-être pas grand-chose de plus, de sorte qu’il peut être intéressant de les utiliser en conjonction avec d’autres modèles compatibles.

#### Caractéristiques du jeu de données {#caracteristiques-du-jeu-de-donnees}

La portée du projet détermine les besoins de l’organisation ou de l’entreprise et, parallèlement, le ou les jeux de données à sémantiser. L’évaluation du ou des jeux de données choisis devrait tenir compte des aspects suivants : 

* Le sujet et/ou le domaine couvert : 

  * Le domaine du modèle devrait couvrir celui du ou des jeux de données et, idéalement, il devrait être soit plus vaste (couvrant plus de sujets que les seules données disponibles), soit plus granulaire (couvrant très précisément les sujets inclus dans les données disponibles) que celui du ou des jeux de données pour que la sémantisation soit pertinente; 

  * Il y a suffisamment d'information dans le jeu de données et le modèle sélectionné pour les mettre en correspondance de manière adéquate. 

* Le degré de désordre du ou des jeux de données et le nettoyage nécessaire des données (un jeu de données désordonné ne générera probablement qu’une série de nœuds en texte libre de faible valeur sémantique) : 

  * Si la valeur sémantique ajoutée n’est pas le but du projet et qu’une série de nœuds en texte libre est jugée pertinente (comme lors de la création d’URI), il est important de choisir un modèle qui peut accueillir de tels nœuds afin qu’ils puissent être récupérés même si leur contenu ne peut pas être facilement recherché; 

  * Des données utilisables ne sont pas seulement synonymes d’ordre, mais aussi de normalisation par l’entremise d’autres outils et ressources tels que les vocabulaires contrôlés qui doivent être compatibles avec les champs ou les nœuds du modèle sélectionné; 

  * Comme les données évolueront inévitablement sur ce plan, l’enregistrement des mises à jour doit être pris en compte si cela constitue un élément important du projet. 

* L'information représentée dans le ou les jeux de données (c.-à-d. quelles données se trouvent dans les champs à sémantiser) : 

  * Les données peuvent couvrir des domaines différents de l’objet principal du ou des jeux de données et doivent donc être prises en considération afin que le ou les modèles tiennent compte de la variabilité et la couvrent de manière adéquate; 

  * L'information destinée à être ingérée par l’entremise de la sémantisation (c.-à-d. les données que les spécialistes en la matière aimeraient tirer du processus) doit également être prise en considération, de même que les données auxquelles lesdits spécialistes souhaiteraient avoir accès à la suite du processus de sémantisation; 

  * Les besoins précis de l’organisation (en termes d'information spécialisée ou juridique) doivent être couverts par le modèle, ou ce dernier doit pouvoir être adapté pour les couvrir.

* L’étendue du modèle et du ou des jeux de données est comparable : 

  * Un jeu de données très précis mis en correspondance avec un modèle très large (et vice versa) aura peu de valeur sémantique, de sorte que les niveaux d’expressivité doivent être équivalents pour répondre adéquatement aux besoins descriptifs du jeu de données; 

  * Dans tous les cas, un modèle plus expressif est toujours préférable, à condition qu’il puisse être maintenu. 


### Évaluation du modèle {#evaluation-du-modele}

#### Couverture des patrons conceptuels

L’évaluation précédente met en lumière les éléments les plus importants pour la réussite du projet en termes de données, ce qui permet de déterminer quels [patrons conceptuels](https://chin-rcip.github.io/collections-model/fr/ressources/actuel/glossaire#patron-conceptuel-nom-masculin) doivent impérativement être couverts par le modèle choisi et lesquels sont auxiliaires. Il est conseillé d’établir un échantillon de patrons conceptuels de base à examiner de plus près lors de la comparaison des patrons afin de s’assurer que le sens voulu des données soit correctement représenté par la sémantique du modèle. 

Les éléments pertinents à prendre en compte dans ce contexte sont les suivants : 

* Le patron conceptuel est-il bien documenté et défini de sorte qu’il puisse être facilement évalué par des spécialistes du domaine? Cela se traduit généralement, entre autres, par : 

  * Une documentation complète, cohérente et bien organisée; 

  * Des exemples qui illustrent une bonne utilisation du patron conceptuel; 

  * Une indication explicite des pièges potentiels ou des limites du patron conceptuel. 

* Le patron conceptuel traite-t-il les données d’une manière qui correspond à la signification prévue des données qu’il va accueillir? Cela peut généralement être évalué des façons suivantes : 

  * Examiner les cas d’utilisation et les exemples qui ont conduit à la création du patron conceptuel et déterminer s’ils mobilisent des concepts similaires aux données; 

  * Évaluer la manière dont les informations sont traitées (sur la base de la documentation) plutôt que le nom du patron conceptuel (qui est un bon indicateur, mais peut parfois être trompeur). 

* Le format des données des valeurs est-il adapté aux patrons conceptuels (p. ex. dates, lieux géographiques)? Dans de nombreux cas, les patrons conceptuels s’adaptent à plusieurs formats de données :  

  * Des formats plus précis et structurés permettront une plus grande sémantisation, tandis que le texte en format libre générera peu de liens sémantiques; 

  * Si les données comprennent plusieurs formats et que le nettoyage n’est pas possible ou prévu, le patron conceptuel devrait s’adapter à tous ces formats. 

* L’utilisation du patron conceptuel nécessite-t-elle de nettoyer, d’améliorer ou d’enrichir les données (p. ex. des formats de date plus cohérents, des emplacements géographiques plus précis)?

* Le patron conceptuel correspond-il au reste du modèle et à la structure générale, et la vision du monde qu’il présente correspond-elle à celle des données?

Dans de nombreux cas, cet examen peut révéler des divergences entre les niveaux de précision du ou des jeux de données et du modèle sémantique. Si le modèle peut être plus détaillé pour certains aspects (p. ex. les dates, les lieux géographiques), les données peuvent être plus précises pour d’autres (p. ex. les professions, les statuts). Dans ce cas, il peut être pertinent de sélectionner et d’utiliser plusieurs modèles sémantiquement (c.-à-d. que les notes d’application des entités ont la même signification inhérente) et techniquement (c.-à-d. que les exigences minimales doivent être les mêmes en termes de format et de spécification) compatibles, dédiés à des aspects précis du ou des jeux de données, afin de représenter adéquatement leur richesse et leur complexité.  

Lorsque le modèle est le plus détaillé, les données peuvent être nettoyées et enrichies avant la cartographie afin d’obtenir de meilleurs résultats. Néanmoins, dans certains cas, les informations les plus précises ne sont pas disponibles, de sorte qu’il est important d’évaluer comment des informations plus étendues sont traitées par un modèle précis : le modèle choisi doit s’adapter à différentes complexités de données sans induire de faussetés. 

D’autre part, lorsque les données sont plus détaillées que le patron conceptuel, il est important de déterminer si les informations qu’elles contiennent sont couvertes ailleurs dans le modèle par un autre patron conceptuel (c.-à-d. que la cartographie doit être affinée, ce qui peut nécessiter un nettoyage des données si plusieurs informations se trouvent dans un seul champ), ou pas du tout (auquel cas l’importance de ces informations doit être évaluée afin de déterminer si le modèle est toujours adéquat).

#### Pertinence

L’adéquation du modèle au projet dépend fortement de ses patrons conceptuels couvrant les besoins de représentation des personnes et des machines qui vont l'utiliser. Cela dit, d’autres éléments peuvent avoir une incidence sur l’utilité d’un modèle. Les questions suivantes doivent être prises en compte : 

* Le modèle est-il également adopté par les partenaires, les parties prenantes et/ou le reste de la communauté ou répond-il à leurs besoins? C’est important, car : 

  * Dans les domaines où l’adoption des DOL n’en est qu’à ses débuts, la plupart des parties prenantes peuvent être internes à l’organisation, mais elles finiront par mener une adoption à plus grande échelle; 

  * Un taux d’adoption élevé par les personnes concernées conduira probablement à davantage de liens inter-institutionnels et, par conséquent, à une meilleure sémantisation et un meilleur enrichissement. 

* Les problèmes sont-ils abordés de manière adéquate et ouverte et, le cas échéant, résolus dans l’intérêt de la communauté? C’est essentiel, car : 

  * Les problèmes auxquels le projet sera confronté ont peut-être déjà été résolus par d’autres; 

  * Toute question qui n’aurait pas été abordée peut être soumise. 

* Le modèle répond-il adéquatement à l’évolution des pratiques dans le domaine couvert par le projet? Cela se traduit par le fait que : 

  * L'information devenue récemment la norme à documenter est représentée ou discutée; 

  * Les préoccupations propres au domaine de pratique sont reflétées dans la documentation; 

  * De nouvelles entités peuvent être liées (grâce à des vocabulaires contrôlés) ou ajoutées (grâce à un protocole de soumission clair). 

* Dans le cas des projets relatifs au patrimoine, les éléments suivants sont souvent importants : 

  * Provenance des données : il est souvent nécessaire d’indiquer ou de vérifier qui a créé ou enregistré une information, notamment lorsqu’il existe des points de vue contradictoires sur un sujet (p. ex. un désaccord sur la date de naissance d’une personne); 

  * Datation du contenu : les informations relatives au moment où quelque chose s’est produit sont souvent importantes, mais sont rarement assez précises pour déterminer une date et une heure. Il est donc important de pouvoir utiliser des intervalles de temps (p. ex. pour une période stylistique); 

  * Flou des données : un certain champ de données dans la base de données d’origine peut contenir plusieurs formats de données (p. ex. des descriptions textuelles de dates comme « au cours du printemps 1992 » et des dates structurées telles que « 1992-05-14 »), de sorte qu’il est souvent nécessaire d'adapter les contenus textuels en plus des contenus structurés (ceci s’applique également lorsqu’il existe plusieurs niveaux de qualité des données). 

#### Adaptabilité {#adaptabilite}

En outre, même si le modèle est à la fois pertinent et adéquat en termes de couverture du domaine, il doit pouvoir s’adapter aux particularités du contenu du ou des jeux de données qui, par exemple, peuvent évoluer dans le temps au fur et à mesure qu’une collection se développe. Pour s’en assurer, il convient de prendre en considération les éléments suivants : 

* Le modèle est-il suffisamment souple pour répondre aux exigences locales? Cela se traduit par le fait que : 

  * Il est compatible avec d’autres modèles pertinents qui sont compatibles avec lui sur le plan sémantique (c.-à-d. que les notes d’application des entités ont la même signification inhérente) et sur le plan technique (c.-à-d. que les exigences minimales doivent être les mêmes en termes de format et de spécification);

  * Il est extensible dans le sens où des champs, des classes, des propriétés et/ou des patrons conceptuels locaux peuvent facilement être développés et ajoutés pour répondre à des besoins précis tout en respectant les contraintes de la norme; 

  * Il peut être utilisé conjointement avec des vocabulaires contrôlés et des thésaurus pour améliorer le niveau de précision des classes, des propriétés et/ou des patrons conceptuels afin de répondre à des besoins précis qui ne peuvent être satisfaits autrement. 

* Le modèle prend-il en compte à la fois les données non structurées (c.-à-d. le texte descriptif interne, etc.) et les données structurées (c.-à-d. les vocabulaires contrôlés, etc.) afin que les deux puissent être représentées? Cela se traduit généralement par : 

  * La présence de patrons conceptuels et/ou de champs de données destinés à accueillir et à traiter des contenus longs non structurés, généralement identifiés par les termes « objet linguistique », « données textuelles », « description », etc; 

  * La présence de patrons conceptuels et/ou de champs de données destinés à accueillir et à traiter un contenu structuré, généralement identifié par des termes tels que « vocabulaire contrôlé », « thésaurus » ou l’utilisation d’URI; 

  * L’utilisation de « chaîne » comme format minimal requis pour les valeurs soumises. 

* Existe-t-il des structures qui permettent de traiter des informations plus précises ou plus larges? Cela se traduit généralement par : 

  * La présence d’une hiérarchie de classes, de propriétés, de patrons conceptuels et/ou de champs qui permet l’utilisation de concepts de plus haut niveau pour représenter de manière significative les informations lorsque les classes et les propriétés plus précises ne représentent pas correctement le contenu des données; 

  * La disponibilité de patrons conceptuels et/ou de champs à la fois généraux et précis qui peuvent être utilisés conjointement; 

  * Des recommandations concernant l’utilisation de vocabulaires contrôlés et de thésaurus pour mieux qualifier les informations. 

#### Durabilité et maintenance {#durabilite-et-maintenance}

Enfin, il est important de s’assurer que le modèle choisi peut être utilisé pour l’ensemble du projet prévu et, éventuellement, pour tout déploiement qui pourrait suivre. Bien qu’il ne soit jamais possible d’avoir une certitude à ce sujet, le responsable du modèle doit : 

* Être une organisation bien établie et réputée qui consacre des ressources à la maintenance et au développement du modèle, ce qui est généralement établi par : 

  * Des mentions dans la planification stratégique ou la déclaration de mission de l’organisation; 

  * L’implication dans la communauté; 

  * L’entretien et l'amélioration réguliers du modèle; 

  * Un point de contact clair où signaler les problèmes ou poser des questions. 

* Établir clairement ses principes et ses politiques de gouvernance : 

  * Ceux-ci doivent correspondre à ceux du projet; 

  * La licence du modèle doit être en accord avec les besoins du projet (idéalement une licence ouverte comme CC0 ou CC-BY).

* Documenter son processus de modélisation et rendre ses résultats utilisables en proposant le modèle dans des formats pertinents comme XML ou RDF. 

* Effectuer des mises à jour cohérentes et pertinentes qui maintiennent le modèle à jour, comme en témoignent : 

  * Les mentions des mises à jour sur le site Web (avec indication de la date et de la nature de la mise à jour); 

  * Les discussions des problèmes (dans les forums dédiés, les sections de commentaires, ou autres); 

  * Le développement de nouveaux patrons conceptuels ou l'ajustement des patrons conceptuels existants pour joindre l’évolution générale du domaine de pratique couvert. 

## Bibliographie

Bailey, Jason. « Solving Art’s Data Problem - Part One, Museums ». *Artnome* (blogue). 29 avril 2019. [https://www.artnome.com/news/2019/4/29/solving-arts-data-problem-part-one-museums](https://www.artnome.com/news/2019/4/29/solving-arts-data-problem-part-one-museums).

Open Art Data. « Museums: Interactive Map with Wikidata ». *Open Data Art* (blogue). 16 décembre 2018. [https://www.openartdata.org/2018/12/museums-map-wikidata.html](https://www.openartdata.org/2018/12/museums-map-wikidata.html).

Edson, Michael Peter. « Wikimania 2019 Keynote Address ». Discours présenté à *Wikimania 2019*, Stockholm, SE, 29 avril 2019. [https://www.youtube.com/watch?v=9NBonp9KLz8](https://www.youtube.com/watch?v=9NBonp9KLz8).

Frosterus, Matias, David Hansson, Maral Dadvar, Ilias Kyriazis, Sofia Zapounidou et Friedel Grant. « Best Practices for Library Linked Open Data (LOD) Publication. » La Haye, NL-ZH : LIBER (Ligue des bibliothèques européennes de recherche), 2021. [https://libereurope.eu/article/libers-linked-open-data-working-group-publishes-best-practices-for-library-linked-open-data-lod-publication/](https://libereurope.eu/article/libers-linked-open-data-working-group-publishes-best-practices-for-library-linked-open-data-lod-publication/).

Goldman, Kathryn. « Open Access Images of Public Domain Work ». *Creative Law Center* (blogue). 2018. [https://creativelawcenter.com/museums-open-access-images/](https://creativelawcenter.com/museums-open-access-images/).

Hyland, Bernadette, Ghislain A. Atemezing, et Boris Villazón-Terrazas. « Best Practices for Publishing Linked Data ». Note du groupe de travail de W3C. 9 janvier 2014. [https://www.w3.org/TR/ld-bp/](https://www.w3.org/TR/ld-bp/).

Kela, Riitta. « Opening Collections as Open Data: Challenges and Possibilities ». *Documenting Culture: A Culture of Documentation*. Tokyo, JP : International Council of Museums (ICOM), 2019.

McCarthy, Douglas. « Licensing Policy and Practice in Open Glam ». *Medium*, 30 mai 2019. [https://medium.com/open-glam/licensing-policy-and-practice-in-open-glam-49c867b49de8](https://medium.com/open-glam/licensing-policy-and-practice-in-open-glam-49c867b49de8).

Oomen, Johan, Enno Meijers, et Wilbert Helmus. « Network Digital Heritage: Towards A Distributed Network of Heritage Information ». *International Conference on Digital Preservation* (IPRES). Amsterdam, NL : Dutch Digital Heritage Network, 2016. [https://www.netwerkdigitaalerfgoed.nl/wp-content/uploads/2018/02/NDE_PositionPaper_NetworkHeritageInformation-EN-v2.pdf](https://www.netwerkdigitaalerfgoed.nl/wp-content/uploads/2018/02/NDE_PositionPaper_NetworkHeritageInformation-EN-v2.pdf).

Open GLAM. *Declaration on Open Access for Cultural Heritage*. 21 janvier 2020. [https://docs.google.com/document/d/1CpDGlWLgkEYJC5A2HJ_Os8XYEv7ONOIBYAobSFzWm14/edit?usp=embed_facebook](https://docs.google.com/document/d/1CpDGlWLgkEYJC5A2HJ_Os8XYEv7ONOIBYAobSFzWm14/edit?usp=embed_facebook).

Fondation Open Knowledge. « Resources ». *OpenGLAM*. 27 novembre 2012. [https://openglam.org/resources/](https://openglam.org/resources/).

Openness: Politics, Practices, Poetics. *Archives vivantes*. Malmˆ, SE : Université de Malmˆ, 2017. [http://muep.mau.se/bitstream/handle/2043/23606/openness_final.pdf?sequence=2\&isAllowed=y#page=14](http://muep.mau.se/bitstream/handle/2043/23606/openness_final.pdf?sequence=2\&isAllowed=y#page=14).

Sanderhoff, Merete, éd. *Sharing Is Caring: Openness and Sharing in The Cultural Heritage Sector*. Traduit par Néné La Beet et René Lauritsen. Copenhague, DK : Statens Museum for Kunst, 2014. [https://www.smk.dk/en/article/the-sharing-is-caring-anthology/](https://www.smk.dk/en/article/the-sharing-is-caring-anthology/).

Schrier, Bill. « Government Open Data: Benefits, Strategies, and Use ». *The Evans School Review*, Alumni Perspective, 4, no. 1 (2014) : 12-27.

Stimler, Neal et Louise Rawlinson. « Where Are The Edit and Upload Buttons? Dynamic Futures for Museum Collections Online ». *MuseWeb*. Boston, MA : MuseWeb, 2019. [https://mw19.mwconf.org/paper/where-are-the-edit-and-upload-buttons-dynamic-futures-for-museum-collections-online/](https://mw19.mwconf.org/paper/where-are-the-edit-and-upload-buttons-dynamic-futures-for-museum-collections-online/).

Stinson, Alex. « Wikidata in Collections: Building a Universal Language for Connecting GLAM Catalogs ». *Medium* (blogue). 9 avril 2018. [https://medium.com/freely-sharing-the-sum-of-all-knowledge/wikidata-in-collections-building-a-universal-language-for-connecting-glam-catalogs-59b14aa3214c](https://medium.com/freely-sharing-the-sum-of-all-knowledge/wikidata-in-collections-building-a-universal-language-for-connecting-glam-catalogs-59b14aa3214c).

Vathana, Anly et Dev Pramil Audsin. « An Open Analysis on Open Data ». Document de soumission. *Open Data on the Web*, 4. Londres, GB : W3C, 2013. https://www.w3.org/2013/04/odw/odw13_submission_33.pdf.

Wallace, Andrea. « Access and the Digital Surrogate: Openness as a Philosophy ». Présenté au *National Digital Forum*, Wellington, NZ, 27 novembre 2017. [https://www.youtube.com/watch?v=crKUIxIX3sY](https://www.youtube.com/watch?v=crKUIxIX3sY).
