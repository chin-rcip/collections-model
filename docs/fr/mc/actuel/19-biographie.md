---
layout: page
language: fr
title: Biographie
permalink: /fr/modele-cible/actuel/biographie
other_link: /en/target-model/current/biography
sidebar: mc22
date: 2022-06-30
description: La Spécification du modèle cible des actants modélise sémantiquement les actants dans un contexte patrimonial. Les patrons conceptuels les plus pertinents pour la vie des actants sont présentés avec des diagrammes et des exemples qui les illustrent, ainsi qu'un compte rendu et une explication des décisions pertinentes qui ont été prises lors de l'élaboration desdits patrons conceptuels. Il s'agit d'une documentation théorique qui n'a jamais été testée ou mise en application.
---

## Aperçu {#apercu}

Ce patron conceptuel peut être utilisé pour représenter les informations textuelles relatives à la biographie d'un actant (personne ou groupe de personnes). Il comprend :

* Le texte d'une biographie;
* La langue dans laquelle le texte d'une biographie est rédigé;
* Les sources et les références qui ont été utilisées pour rédiger le texte d'une biographie.

Ce patron conceptuel ne contient pas :

* Les données tabulaires représentées ailleurs dans le modèle; 
* La personne ou le groupe de personnes responsable de la création du texte; seule la documentation de la provenance d'un jeu de données entier est modélisée par le patron conceptuel [Provenance du jeu de données](/collections-model/fr/modele-cible/actuel/provenance-du-jeu-de-donnees);
* Les notes curatoriales concernant l'actant, qui doivent être documentées à l'aide du patron conceptuel [Note curatoriale](/collections-model/fr/modele-cible/actuel/note-curatoriale). 

## Introduction et contexte

### Historique théorique {#historique-theorique}

Les biographies dépeignent généralement la vie d'un être humain à l'aide d'un texte littéral, une pratique qui remonte à l'Antiquité avec les *Vies parallèles* de Plutarque (Kendall 2019; Viala 2021). Contrairement à la recherche patrimoniale, qui met l’accent sur des périodes ou des groupes, les biographies portent sur la vie d'individus particuliers qui peuvent eux-mêmes être contextualisés par la description d'une période ou d'un groupe.

### Énoncé des besoins {#enonce-des-besoins}

Les biographies écrites constituent une partie importante de la recherche et de la documentation et sont couramment utilisées par les historiens et les sociologues pour replacer la vie des individus et des groupes dans un contexte chronologique, géographique ou sociologique (Levallois 2002). Cela dépend en partie de l'enregistrement de la paternité des sources, primaires ou originales, utilisées dans le processus d'enregistrement (sources qui se rapportent à l'information biographique elle-même, et non au jeu de données en général; pour ce dernier, le patron conceptuel [Provenance du jeu de données](/collections-model/fr/modele-cible/actuel/provenance-du-jeu-de-donnees) doit être utilisé).

Même si le développement de requêtes biographiques complexes repose sur des données structurées, liées et sémantiques, un champ de texte littéral permettant d'accueillir de longs textes en langage naturel est également nécessaire, car il répond aux besoins immédiats des soumissionnaires de données qui s'appuient principalement sur des textes pour documenter de manière précise et originale la vie des actants. En outre, ce champ de texte littéral pourrait éventuellement être analysé à l'aide d'outils de traitement du langage naturel afin de générer des données structurées et sémantiques à partir de son contenu. 

## Description du patron conceptuel

Comme pour les autres informations textuelles (voir la section [Contenu littéral](/collections-model/fr/modele-cible/actuel/concepts-generaux#contenu-litteral)), le contenu d'une biographie est modélisé comme une instance de `E33_Objet_linguistique` liée à la valeur littérale du [Contenu de la biographie](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#contenu-de-la-biographie) par la propriété `P190_a_pour_contenu_symbolique`. Cette instance de `E33_Objet_linguistique` est aussi liée à l'actant décrit dans la biographie (une instance de `E39_Actant`) par la propriété `P67_renvoie_à`.

La façon la plus simple de fournir les sources et les mentions bibliographiques utilisées dans la création d'une biographie est de s'appuyer sur la propriété `dct:source` de l'ontologie de la [Dublin Core](https://www.dublincore.org/specifications/dublin-core/dcmi-terms/), reliant l'instance de `E33_Objet_linguistique` à la valeur littérale de la [Mention bibliographique de la biographie](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#mention-bibliographique-de-la-biographie). De plus, à partir de la même instance de `E33_Objet_linguistique`, la valeur de la [Langue de la biographie](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#langue-de-la-biographie) (une instance de `E56_Langue`) est rendue par la propriété `P72_a_pour_langue`.

## Diagramme

<a name="061_PatronConceptuel_Biographie_p"></a>061_PatronConceptuel_Biographie_p

<div class="mxgraph" style="max-width:100%;border:1px solid #cccccc;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;target&quot;:&quot;blank&quot;,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom layers lightbox&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;xml&quot;:&quot;&lt;mxfile modified=\&quot;2023-03-15T17:12:54.301Z\&quot; host=\&quot;app.diagrams.net\&quot; agent=\&quot;5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) draw.io/20.3.0 Chrome/104.0.5112.114 Electron/20.1.3 Safari/537.36\&quot; etag=\&quot;uf8PKJnbTx_khH-7BmE3\&quot; version=\&quot;20.3.0\&quot;&gt;&lt;diagram id=\&quot;MXu5EEb1o1QtSemSzmGb\&quot; name=\&quot;Page-1\&quot;&gt;1VjRcps6EP0aHslgMDh+dBzbnbnJbW7TTpO+MAJkUCsQRSK2+/VdGcmAjR0ntZvcmUwGLbtCOjqcs9hwxulyVqA8uWURpoZtRUvDuTZs2zbknxWtqmGvGsYFiXYC9+QXVkFLRUsSYd5KFIxRQfJ2MGRZhkPRiqGiYIt22pzR9lNzFOOdwH2I6G70K4lEoqI9y6pvfMAkTtSjL111I0U6WQV4giK2aIScieGMC8ZEdZUux5hK3DQuVd10z93NwgqciWMKWHb373/XH5hd0oWXPD7MVmFiOtUsT4iWasN3vaHlIz9nZeEDqAJnpc9XacAo+Qk51VbESuODI4BLDVkhEhazDNFJHb0qWJlFWC7CglGdc8NYDsEeBL9jIVbq7FEpGIQSkVJ1F/ZXrB5k/YWrh49quvXgetkarfRoSUSjDEaPeka4rovkQNfsgqpw5oBHqPYcmisv/1XORtd3vBz8yG4WXzxTkxMVMRYHEFdvg8St8QB1ZDPMUgx7gIQCUyTIU5uGSLE53uRtSu8YgSXblnrp3EtFO/XW9R2rPUW1IVVV0wYuGsuoQ2sydROrE47hLrG8gQ+wPjGCfWPsGCPrbcnUolLNrD1k4nCwYiQFBQIhRZyTUIenhNbTRzopYxmuIur+0fzq5E0Hvw7x8HT8ajHjAA0OrbpBg4kz9EehQIp2zeOvD1dCuUiIwPc5WqOyAGNpH+QcQB0zyop1rTOfB1GI9sL7hAuBlwcB0W5ltV8cx3Wr8aIh/1rTk4bye9aLMfzCcfEx+C59y7YoCjCtSg3bozDrVQAXsbwYV0IsXRSvU+FfQFgs7ZZgnQ6zbyo2UxQ6suSA7IiLgmRxtVJKsh/VAxMhpJ+O5ELtaZiQzCxCkl/ERCRlcEGYjDJKYaWEZdxMK4ufzmH2Kc9xSOYkRPKeCW5thglOCaRxnMI5S9/gkIdCUa6rMobLiEOmyRHhcv2OchoZo8hsbs1+jmJ24zgVJV/LqRPQp99327o7PB99YNhg0AvE+XJXnG3t+WKVvyuX771EmJXmNlXZaqtyLd21MB88+tcYf2de/62EORn5D9a3r/9cmsHHZOGS2cPtp47GL5IcGqnt/o+cWbd5urGrqmzd8/2FPq8T4Dfz4UOrbvmw40vlED7YAHxlcVH19x5KpSpmAc83OJ3Ko6ModPonEdkjPNo5jcgeh29/F1/X9T+vtXTbiI2xbYwAWeuqYXOWjF6dGG8UuJ57BlPbfJ2fwdSOw9vddbDBxsIoAkK/jYZ1atHgsBa9VvjOb1neqTWs+1t14LRf5x3avPpb9egG+0ZR5g/664nr+TcN5r2j7rp6IZ5prvcz4DTN9bnMwBtu/9LxVzvuoym2ba23sGU40jXTAqoP5eezLGwYSQcv3/VXXlpt2dza8DPE3N9evZuvvm0O2oPzGWQHByFU/45cqWL9Q7wz+Q0=&lt;/diagram&gt;&lt;/mxfile&gt;&quot;}"></div>

## Exemples

### Exemple 1

La biographie en anglais (`P72_a_pour_langue`, Langue de la biographie) de Yousuf Karsh sur Wikipedia (Wikipedia 2021) est la suivante :

« Yousuf Karsh CC (December 23, 1908 – July 13, 2002) was an Armenian-Canadian photographer known for his portraits of notable individuals. He has been described as one of the greatest portrait photographers of the 20th century.

An Armenian genocide survivor, Karsh migrated to Canada as a refugee. By the 1930s he established himself as a significant photographer in Ottawa, where he lived most of his adult life, though he travelled extensively for work. His iconic 1941 photograph of Winston Churchill was a breakthrough point in his 60-year career, through which he took numerous photos of known political leaders, men and women of arts and sciences. Over 20 photos by Karsh appeared on the cover of *Life* magazine, until he retired in 1992 » (`P190_a_pour_contenu_symbolique`, Contenu de la biographie).

Les œuvres suivantes sont citées :

* Berman, Eliza. « Yousuf Karsh's Masterful Portraits From Churchill to Hepburn ». *Time*. 18 mars 2015 (`dct:source`, Mention bibliographique de la biographie);
* Thurber, Jon. « Yousuf Karsh, 93; Photographs Captured Face of 20th Century ». *Los Angeles Times*. 14 juillet 2002 (`dct:source`, Mention bibliographique de la biographie).

<div id="0001_100_biography" class="example"></div>

### Exemple 2

La biographie en anglais (`P72_a_pour_langue`, Langue de la biographie) du Canadian Group of Painters par l'Institut de l'art canadien (Institut de l'art canadien n.d.) est la suivante :

« Founded in 1933 after the disbanding of the Group of Seven by former members and their associates, the Canadian Group of Painters championed modernist painting styles against the entrenched traditionalism of the Royal Canadian Academy of Arts. It provided a platform for artists across Canada who were pursuing a variety of new concerns, from the formal experimentation of Bertram Brooker to the modern-figure subjects of Prudence Heward and Pegi Nicol MacLeod and the expressive landscapes of Emily Carr » (`P190_a_pour_contenu_symbolique`, Contenu de la biographie).

Aucun ouvrage n'est cité comme source du texte.

<div id="0001_112_biography" class="example"></div>

## Documentation connexe

### Modèles externes {#modeles-externes}

* SARI : [Information Carrier Reference Data Model – Description](https://docs.swissartresearch.net/et/carrier/#description)

### Nœuds de saisie {#noeuds-de-saisie}

* [Contenu de la biographie](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#contenu-de-la-biographie) \| Liste de vérification
* [Langue de la biographie](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#langue-de-la-biographie) \| Liste de vérification
* [Mention bibliographique de la biographie](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#mention-bibliographique-de-la-biographie) \| Liste de vérification

### Entités du CIDOC CRM {#entites-du-cidoc-crm}

* `dct:source`
* `E33_Objet_linguistique` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E33)]
* `E39_Actant` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E39)]
* `E55_Type` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E55)]
* `E56_Langue` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E56)]
* `P2_a_pour_type (est_le_type_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P2)]
* `P67_renvoie_à (fait_l'objet_d'un_renvoi_par)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P67)]
* `P72_a_pour_langue (est_la_langue_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P72)]
* `P190_a_pour_contenu_symbolique` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P190)]

## Discussion

### Justification 

Par souci de simplicité, l'ontologie de la Dublin Core est utilisée pour documenter les mentions bibliographiques, car elle est la plus utilisée par les bibliothèques et les archives patrimoniales à cette fin. La propriété `dct:source` liée à la chaîne de caractères descriptive semble suffisante dans ce cas. Actuellement, la paternité est attribuée par défaut au soumissionnaire du jeu de données plutôt qu'à une personne, contrairement aux sources qui sont enregistrées. 

La distinction entre une note curatoriale concernant un actant et une biographie peut être difficile à évaluer. Si une description textuelle contient uniquement des récits de la vie d'un actant, elle doit être modélisée à l'aide du patron conceptuel Biographie; si elle contient d'autres types d'information, elle doit être modélisée à l'aide du patron conceptuel Note curatoriale.

### Limitations

Parce qu'il repose sur des descriptions textuelles sous forme de chaînes de caractères, le champ biographie contient beaucoup d'informations non structurées qui peuvent néanmoins, et pour cette raison, être particulièrement détaillées. Ainsi, il est nécessaire de rendre compte des éléments de la vie des actants qui n'ont pas pu être documentés dans des champs structurés et dédiés. Cependant, de tels contenus sont difficiles à interroger en raison de l'incapacité à identifier leur nature sans les lire et les comprendre, ce que seuls des êtres humains ou de puissants logiciels d'intelligence artificielle peuvent faire. 

Bien que la vie des objets ou d'autres entités qui ne sont pas des actants présente un grand intérêt, elle n'a pas été modélisée dans la Spécification du modèle cible en raison de la portée limitée du projet.

La classe `E33_Objet_linguistique` inclut le texte écrit dans sa note d'application, mais aussi la parole enregistrée et le langage des signes (Bekiari et al. 2021). Toutefois, le modèle DOPHEDA ne prend actuellement en compte que les contenus textuels des biographies, car il n'existe pas de patron conceptuel pour documenter tout autre type d'objet linguistique (p. ex. la documentation orale ou les récits multimédias). Par conséquent, certains témoignages (p. ex. des enregistrements audio ou vidéo) ne peuvent pas être documentés.

### Cas limites

#### Exemple 1 {#cas-limites-exemple-1}

La biographie d'un groupe peut être catégorisée soit comme un Contenu de la note curatoriale, soit comme un Contenu de la biographie. En outre, un soumissionnaire pourrait décider d'utiliser un gestionnaire de bibliographie et lier la mention bibliographique à la saisie du gestionnaire au lieu de la copier.

#### Exemple 2 {#cas-limites-exemple-2}

Les considérations bilingues pourraient s'appliquer au Contenu de la biographie, de sorte qu'il s'agirait soit de deux nœuds Contenu de la biographie liés à leur nœud Langue de la biographie correspondant, soit d'un nœud Contenu de la biographie lié à deux nœuds Langue de la biographie.

#### Exemple 3 {#cas-limites-exemple-3}

Certains textes peuvent être écrits dans un dialecte spécifique d'une langue (p. ex. le français canadien peut être considéré comme un dialecte français). Les langues et les dialectes sont des valeurs valables; le choix de documenter les uns ou les autres dépend du vocabulaire utilisé par l'institution.

## Bibliographie

Bekiari, Chryssoula, George Bruseker, Martin Doerr, Christian-Emil Ore, Stephen Stead, et Athanasios Velios, éds. *Definition of the CIDOC Conceptual Reference Model*. Documentations du CIDOC CRM, 7.1. Paris, FR-IDF : CIDOC CRM Special Interest Group, 2021. [http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf](http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf).

Institut de l'art canadien. « Glossaire de l'histoire de l'art canadien ». Institut de l'art canadien. 13 octobre 2021. [https://www.aci-iac.ca/glossary/C/](https://www.aci-iac.ca/glossary/C/).

Kendall, Paul Murray. « Biography ». *Encyclopædia Britannica*. Londres, UK-LDN : Encyclopædia Britannica, 2019. [https://www.britannica.com/art/biography-narrative-genre](https://www.britannica.com/art/biography-narrative-genre).

Levallois, Anne. « Le retour de la biographie historique. L'histoire et la psychanalyse s'y rejoindraient-elles? ». *L'Homme & la Société* 146, no 4 (2002) : 127-140. [https://doi.org/10.3917/lhs.146.0127](https://doi.org/10.3917/lhs.146.0127).

National Women’s History Museum. *Biographies*. National Women’s History Museum. 8 septembre 2021. [https://www.womenshistory.org/students-and-educators/biographies](https://www.womenshistory.org/students-and-educators/biographies).

Viala, Alain. « Biographie ». *Encyclopædia Universalis*, *Encyclopædia Britannica*. Londres, UK-LDN : Encyclopædia Britannica, 2021. [https://www.universalis.fr/encyclopedie/biographie/](https://www.universalis.fr/encyclopedie/biographie/).

Wikipedia. « Yousuf Karsh ». *Wikipedia*. San Francisco, US-CA : Wikipedia, 2021. [https://fr.wikipedia.org/wiki/Yousuf_Karsh](https://fr.wikipedia.org/wiki/Yousuf_Karsh).

