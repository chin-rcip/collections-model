---
layout: page
language: fr
title: Provenance de l'enregistrement
permalink: /fr/modele-cible/actuel/provenance-de-lenregistrement
other_link: /en/target-model/current/record-provenance
sidebar: mc22
date: 2022-06-30
description: La Spécification du modèle cible des actants modélise sémantiquement les actants dans un contexte patrimonial. Les patrons conceptuels les plus pertinents pour la vie des actants sont présentés avec des diagrammes et des exemples qui les illustrent, ainsi qu'un compte rendu et une explication des décisions pertinentes qui ont été prises lors de l'élaboration desdits patrons conceptuels. Il s'agit d'une documentation théorique qui n'a jamais été testée ou mise en application.
---

## Aperçu {#apercu}

Ce patron conceptuel peut être utilisé pour représenter les informations relatives à la documentation d'un enregistrement par une organisation ou une personne responsable de sa création ou de sa dernière mise à jour. Il comprend : 

* L'appellation du contributeur de l'enregistrement;
* Les dates de création de l'enregistrement (y compris les dernières mises à jour).

Ce patron conceptuel se rapporte spécifiquement à la documentation de l'enregistrement lui-même, et non au jeu de données dont il provient ou au contenu de ses données. Il ne doit donc pas être utilisé pour enregistrer : 

* La provenance d'un artefact;
* L’emplacement où les données originales sont hébergées;
* La source primaire de l'information (p. ex. livres, archives, articles, etc.);
* L'appellation du soumissionnaire du jeu de données (voir le patron conceptuel [Provenance du jeu de données](/collections-model/fr/modele-cible/actuel/provenance-du-jeu-de-donnees));
* Les dates de soumission et de mise à jour du jeu de données (voir le patron conceptuel [Provenance du jeu de données](/collections-model/fr/modele-cible/actuel/provenance-du-jeu-de-donnees)).

## Introduction et contexte

### Historique théorique {#historique-theorique}

Le terme « enregistrement », issu du domaine juridique en tant que souvenir oral des procédures judiciaires, a évolué pour englober les preuves, les informations et les représentations d'activités, de transactions ou d'évènements et les documents liés à quelque chose (Duranti & Franks 2015). Le terme a ensuite été utilisé dans les sciences informatiques où il représente un regroupement de données en une unité structurelle axée sur une entité d'intérêt (Henderson 2009). À l'origine, dans un modèle de base de données à fichier plat, l'enregistrement est associé à la rangée ou à la colonne d'un tableau. Il contient des données sur une entité qui ont été structurées en champs. Une telle structure est utile pour ajouter, mettre à jour, récupérer, manipuler et rendre compte des données, et a été largement utilisée dans différents domaines, y compris le secteur patrimonial (Bruseker et al. 2021). 

En raison de leur structure en graphe, les données ouvertes et liées ne reposent pas sur des enregistrements comme unité de structure. Si, jusqu'à récemment, les enregistrements étaient définis par la structure de la base de données à fichiers plats (la rangée ou la colonne), ce n'est plus le cas pour les graphes. Pour rendre compte de l'existence de l'enregistrement, sa structure doit maintenant être représentée conceptuellement plutôt que structurellement. Cette représentation conceptuelle repose sur l'identification du groupe de nœuds qui constituait l'enregistrement à l'origine, ou sur la création d'un nœud qui agit conceptuellement comme l'enregistrement pour permettre la documentation d'informations connexes (en le centrant sur une entité d'intérêt qui, dans un projet centré sur les actants, est le plus souvent l'actant).

### Énoncé des besoins {#enonce-des-besoins}

L'objectif du projet DOPHEDA est d'agréger dans un seul graphe de connaissances des données provenant d'institutions patrimoniales au Canada et d'autres sources pertinentes susceptibles d'informer ou d'éclairer ces jeux de données fondamentaux. Les raisons de documenter la provenance de ces jeux de données sont détaillées dans le patron conceptuel [Provenance du jeu de données](/collections-model/fr/modele-cible/actuel/provenance-du-jeu-de-donnees). Pour les raisons décrites dans ce patron conceptuel, le RCIP a choisi de documenter les informations sur la provenance et les limites temporelles du soumissionnaire en l'appliquant au jeu de données soumis plutôt qu'à chaque enregistrement soumis (p. ex. des ensembles d'informations tabulaires).

Cependant, une description davantage granulaire des informations sur la provenance et les limites temporelles est parfois pertinente. Traditionnellement, l'information dans les institutions a été structurée au niveau de l'enregistrement où, par conséquent, la plupart des mises à jour sont effectuées par les soumissionnaires de données (Bruseker et al. 2021). Certaines informations, telles que les dates de mise à jour ou les sources, sont ainsi liées à des enregistrements spécifiques.

Afin de faire le suivi des informations liées spécifiquement aux enregistrements, une unité d'information (représentant l'enregistrement lui-même) doit être liée à l'entité d'intérêt. Cette unité d'information, représentée dans le diagramme ci-dessous, peut documenter la personne ayant créé l'enregistrement ainsi que ses limites temporelles. 

## Description du patron conceptuel

Comme mentionné ci-dessus, la Spécification du modèle cible applique des graphes nommés au niveau du jeu de données (Bruseker et al. 2021) et, par conséquent, représente les enregistrements en utilisant une entité conceptuelle. 

Ceci est fait en utilisant une instance « d'enregistrement » de `E73_Objet_informationnel` liée à une instance de `E39_Actant` par la propriété `P67_renvoie_à`. Cette instance de `E73_Objet_informationnel` est également liée à une instance de `E55_Type` (un nœud doté d’un qualifiant spécifié) portant le libellé « Enregistrement » par le biais de la propriété `P2_a_pour_type`. Cette même instance de `E73_Objet_informationnel` est également liée par la propriété `P94_a_créé` à une instance de `E65_Création`, qui à son tour réfère à la personne ayant contribué à l'enregistrement (une autre instance de `E39_Actant`) par le biais de la propriété `P14_a_été_effectué_par`. Cette deuxième instance de `E39_Actant` est liée par la propriété `P1_est_identifié_par` à une instance de `E41_Appellation` et de `E33_Objet_linguistique` qui, à son tour, est liée à la valeur littérale de l’[Appellation du contributeur de l'enregistrement](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-du-contributeur-de-lenregistrement) à travers la propriété `P190_a_pour_contenu_symbolique`.

Le moment lors duquel la contribution a été effectuée est indiqué à l'aide du patron conceptuel [Limites temporelles](/collections-model/fr/modele-cible/actuel/limites-temporelles) lié à l'instance de `E65_Création` par la propriété `P4_a_pour_intervalle_temporel` avec des valeurs extraites des nœuds de saisie [Date de début de l'enregistrement](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-de-lenregistrement) et [Date de fin de l’enregistrement](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-de-lenregistrement).

Comme le RCIP n'a pas encore déterminé comment documenter les mises à jour de l'information, la date de création correspond actuellement à la dernière version modifiée de l'enregistrement.

## Diagramme

<a name="015a_PatronConceptuel_ProvenanceDeLenregistrement_Actant_p"></a>015a_PatronConceptuel_ProvenanceDeLenregistrement_Actant_p

<div class="mxgraph" style="max-width:100%;border:1px solid #cccccc;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;target&quot;:&quot;blank&quot;,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom layers lightbox&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;xml&quot;:&quot;&lt;mxfile modified=\&quot;2023-03-15T17:12:51.004Z\&quot; host=\&quot;app.diagrams.net\&quot; agent=\&quot;5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) draw.io/20.3.0 Chrome/104.0.5112.114 Electron/20.1.3 Safari/537.36\&quot; etag=\&quot;Wmx71VtCtu3jWAjhJv7a\&quot; version=\&quot;20.3.0\&quot;&gt;&lt;diagram id=\&quot;8FEECiLeWfE7_SmkeOaP\&quot; name=\&quot;Page-1\&quot;&gt;5Vptd6o4EP41fPQeBFH8qFa7b931nLZ7637hhCRIdgOhIVjdX78BQnmtbS217V1PjyWTSUhmnpl5CGrmIthfchD5Vwxhqhk62mvmhWYYhpb+6eiQN4d5c8sJagmuyb9YCXUlTQjCcU1RMEYFiepCyMIQQ1GTAc7ZQ13NY7R+1whscUtwDQFtS78TJHwlNXS97PgJk62vbm2PVEcACmUliH2A2ENFZC41c8EZE/lVsF9gmtqtsEs+bvVE7+PCOA7FSwbsg114+/2XX0M6t+/Qn/p9crkaqFl2gCZqw0tz6sygAHLSfNniUNiCsyREOJ1uqJnzB58IfB0BmPY+SMdLmS8Cqro9QumCUcazsabnuQiC9pqLBWAu8L4iUnu4xCzAgh+kiuq1TGVPBafRWLUfau7JZX7FM4UeUIjYPk5dGk1eKLu9woajlg3XhgOciCXcEYcIt+yIkYSYajIufLZlIaDLUjovLa3LVqnzG2ORsu/fWIiDiheQCFa3vrQvP9yp8Vljkza+WUXzYl/tvDio1pMOiuVuID5iBRXlAvAtFkf0zFwvtcFRd3NMgSC7ehh2+S4bOuMcHCoKESOhiCszr1NBiaKJXkeRaTeC53X68iJfQYmix62cDiyrDazxxJGu2TGCHW1hajP9Y8FV4mlTg1M3uPCeiMow2doUM8rrclDaOB8gh30D8k3JxGgn5Inp/OFKjzgk9BiXdYWktY72m54Rguaoj/RsNALF6kjPo3OmZ7NtUctybrLEPKby7nOXy6tteqUtDG0mMacvQ463JBYcBzjLA2nPfN6vzYFrja0ebD6ZvMDmZy2Jk3bmmo5kTYQ8y1pT9f2FctfpeWj8wjxkfKo8NG17cFSQGlkZMZc9tCOCHIGDiHHQTk8/JOt5qXPtT+XccTslji1noYIzKzC9ZjrbgCaGfVSXBvk3zDNmOmePZrvN79v1xhC3q+WaLrjVUV2KmEBkVwTF2jaAQ7GDcgO7iXAKLXnTimLHWJRUhj016uuEWsEBC9aXjzIKQtg3CbTb8dnpxg8jgZ2raT9RdoPKdShwPBK+Ak1YDflRkTT5aCR9rjJud5Bfw/m5UsD1vGD3/Dxhj10I7WMGP53enjXpdz8yto/N1sOUHuWJWuT/nDY7wp6HoUhUv7TKVwq4WGJfzNIzVSmAFMQxgYV4RWg5PSqUQhbiXKL63xaCxZnws2xr3HcMNg6FChXmeTEWLTj1cPRTbPULHcwa0/OF6W2MeXomAlNvUOBiWi+TbhFwF0CkOQ5lXxUalUuotjQ0W9emU9x43n8sjm6zmJbBvI+lxWdI3uGGBOqUl5Lwn3wpvhDpK4pZugVjBX0SDjgk0bctEX7ifiMslTKZgmFKt+NBkL81WXly/lUcYUg8AjMqPkA4HkAfB0SqxTiQCCD3CY6lHpDJJBsVMpygWGoOYkBiIldjpgtLBQjLHacXtLlJ4zkeUnW4Qu2pqOsBYEO9cQg7tN8PYbJZAdnpoMuo1v8IbXK/p2HN+NxYM86LtVaVCPfsr/nV8u7+xr9aDTfEvL+hHW/v1kMHx8IhSG5duvSDicZZz/u72EGn1d7nDVTrlZE5apzK6g1k5DtSo95EITq3aXSAY6oXZ3iQyWeAMHHiQ+Aymkb4V0HIu57gHgPMs8Aa9Q2slz6kHFt1lUGOhs4siuRYdcTXrDFLs3jVJCvLNpHpuxMYb6GbMPv0QTdtqx5eXS89zDPTzZp1dZRo2Q9TBCeSguGE98kE5Bjpo0/HA0BpgQFKBtXdP8sLng6qfnhBA4qr7NMHFCd1KHb+JMV6N64gReWviPLqUf4My1z+Bw==&lt;/diagram&gt;&lt;/mxfile&gt;&quot;}"></div>

<a name="015b_PatronConceptuel_ProvenanceDeLenregistrement_Artefact_p"></a>015b_PatronConceptuel_ProvenanceDeLenregistrement_Artefact_p

<div class="mxgraph" style="max-width:100%;border:1px solid #cccccc;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;target&quot;:&quot;blank&quot;,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom layers lightbox&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;xml&quot;:&quot;&lt;mxfile modified=\&quot;2023-03-15T17:12:51.235Z\&quot; host=\&quot;app.diagrams.net\&quot; agent=\&quot;5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) draw.io/20.3.0 Chrome/104.0.5112.114 Electron/20.1.3 Safari/537.36\&quot; etag=\&quot;MZFkWpGCJ09buyypKEsQ\&quot; version=\&quot;20.3.0\&quot;&gt;&lt;diagram id=\&quot;8FEECiLeWfE7_SmkeOaP\&quot; name=\&quot;Page-1\&quot;&gt;3Vpbd+I2EP41nH0ixxeuj0Agzba7SzfZbrIvPkKSsVLZIrJMoL++Y1vGNnYSShySlJNDrJFkSTPfzHwe07In/uZCopX3RRDKW5ZBNi37vGVZViv+M8g2bZppcykZqQiu2D9UCw0tjRihYWmgEoIrtioLsQgCilVJhqQUD+VhruDlVVdoSSuCK4x4VfqTEeVpqWUYecdvlC09vfSgozt8lA3WgtBDRDwURPa0ZU+kECq98jcTymO9ZXpJ580e6d1tTNJAHTLhK/9p2x6+ZPTuT3YZ3X0Xxqit77JGPNIH1ptV20wDlIBCdFNI5YmlCBCf5tKxFFFAaLyMAa18zB9CrEBogvCOKrXV1kWREiDylM91b/Uoel+hiCTW+9j46+DHz8+/B3w8uCF/GffRxazd05BAcknVE+P0seKzFBbQirqgwqdKbmGApBwpti4bH2kMLXfjcjXDhdZ0vdZrd9OpaH1uOchZwWkdtV3Rt7ABqF5ub/T8pHEbN866WfN8U+w83+rW8bazDrSdfaDtdLhpG2fG0Bimkw62p77dXDA4Rj5EuG4Im9s3+G7V4zFgVTAw7dvOtwVYyWGBKyQEEBYHNV5BQ27r2HAPHlP0aoUSXT9AAC7b1WWcTwQXMplru4Rgu/Oo0dZUKro5RM3dLK7psG53dfuhECazYOgVImTPeCWvsqsa7Xad68SfehxWHy8kXC3jq9bEao0Au8Y0kHTJQiWpTxPLxz3jcbM6R4tur9uAzvv9A3RunVLn/WokG3YglGHZmtit0VB/v2k8y0PYbSmCNR3PPmYuGlYt2MlyEcRCKqGH13iQo6i/ErImPP0vk9Whxh28K+P2qiGx13Um2jmTBNNopBtY2Ka4iexilyOdZZ8w0jkbMlrffl3Oby31Yzad84ns1mSX+cBCDqcOSbW5iJRTdRMSFfo/kqvQDVM32T3gOp1ldXUznxU3Xu5fg6p/1ZrBfCv/qt1NlchnCCBsnUEAcLJwOHJcFjiE7jACCxYG1cxLpzw2/KMjqf/WSHpfaXhQQ14t53KXgGtCy6MJ+EURvLfAePCUAY6nqycN4rVaNqv1jrkZ0500RKv0X42uqetSrCLdD1r5SA4Ygi+oUVwMAwHmKAwZzsQzxvPbk2xQIAKaSnT/y1wyK+Y9y55678ons20XndIeOiOsUFDN5S96QnQXBKMGXM4ans7lfoRUxvUKHD82c7SgvJwCF5nznCMFDxAGSb4KZCiV8E907xm88rCep8DdPTchaHpE4M7XzNcFM86Cv9MteErF9eFRvHVrhj0WtCVmq7MlU160OGMilgoIqzimwGHbT0vWMxfWnIUripnLcEKP24SGbexRn8GwkPpgeXYf0RDGIQgIyaxA0IiEMLIdIhYy2I0dbywWEAonjS/4/iGt57hF0dAarceirQFgmYZRRpY5eD1kQbMAruPBltCnp1FWxFQVeR8EZXDO4zBmvW+MWafFWCUrBBvxa/xlenN/7X2ZmbfMvr/mNa9M5qZDQ+UwAkcHk74xSdBsW9MCzbeznqbJdl1mr9XaoUX8Ywv2GkJ2Z69CauwhIz2RnrUHjv9W1a89plUDjqGR1dOwAD4fRE649ReCxx7+URDyqtXUpwDzLLA6b0UZn9p1kTF2TGe0WsFcXW7bzzFTO3vtA5llGUH4rgXGS+glTj5N0MtBt+xedS8g7BPTy5J2DRK1kl8DKMmAetFI7hhAa2q1IKEMh8czAZgDNnp3PADlGmiTqF08/bO84HGnaoYX7EFxlnyagGK/DMVOrwaK3dNxhfHnpeey2x6ef5sL45d3dee6NVxhCkws9faUJgCwRfaurPqOBTTk8E9e5CPWbKF+ao5Hw0kztG2/Vl9ridcq89SqvSYL9/oOHHEtGE0Vb1TU+Y7fSZ6W01nVzPsUuF+b0vXNPUc3m6J00Mx/fpUOz3+/Zk//BQ==&lt;/diagram&gt;&lt;/mxfile&gt;&quot;}"></div>

## Exemples

[Artistes au Canada](https://app.pch.gc.ca/application/aac-aic/description-about.app?lang=fr) est une liste collective bilingue qui identifie l'emplacement des dossiers de documentation sur les artistes mentionnés dans les enregistrements des institutions situées au Canada, qui soumettent elles-mêmes leurs informations (Musée des beaux-arts du Canada 2019a; Musée des beaux-arts du Canada 2019b). Dans cette liste, l'enregistrement sur Yousuf Karsh indique que l'information : 

* A été fournie par Bibliothèque et Archives du Musée des beaux-arts du Canada/Musée canadien de la photographie contemporaine (`P190_a_pour_contenu_symbolique`, Appellation du contributeur de l’enregistrement); 
* A été créée le 1985-03-13 (`P82a_le_début_du_début`, Date de début de l’enregistrement); 
* A été mise à jour le 2011-06-03 (`P82b_la_fin_de_la_fin`, Date de fin de l’enregistrement) (Patrimoine canadien, Gouvernement du Canada 2011).

<div id="0001_100_record-provenance" class="example"></div>

## Documentation connexe

### Modèles externes {#modeles-externes}

* CIDOC CRM : [Digital Provenance Ontology](http://www.cidoc-crm.org/Resources/a-digital-provenance-ontology-0)
* Nomisma.org : [VoID RDF](http://nomisma.org/documentation/contribute)

### Nœuds de saisie {#noeuds-de-saisie}

* [Appellation du contributeur de l’enregistrement](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-du-contributeur-de-lenregistrement) \| Liste de vérification
* [Date de début de l'enregistrement](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-debut-de-lenregistrement) \| Liste de vérification
* [Date de fin de l'enregistrement](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#date-de-fin-de-lenregistrement) \| Liste de vérification

### Entités du CIDOC CRM {#entites-du-cidoc-crm}

* `E33_Objet_linguistique` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E33)]
* `E39_Actant` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E39)]
* `E41_Appellation` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E41)]
* `E52_Intervalle_temporel` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E52)]
* `E55_Type` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E55)]
* `E65_Création` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E65)]
* `E73_Objet_informationnel` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E73)]
* `P1_est_identifié_par (identifie)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P1)]
* `P2_a_pour_type (est_le_type_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P2)]
* `P4_a_pour_intervalle_temporel (est_l’intervalle_temporel_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P4)]
* `P14_a_été_effectué_par (a_effectué)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P14)]
* `P67_renvoie_à (fait_l’objet_d’un_renvoi_par)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P67)]
* `P82a_le_début_du_début`
* `P82b_la_fin_de_la_fin`
* `P94_a_créé (a_été_créé_par)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P94)]
* `P190_a_pour_contenu_symbolique` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P190)]

## Discussion

### Justification

Les raisons du développement d'une structure de données de provenance portant sur les jeux de données plutôt que sur les enregistrements sont documentées dans le patron conceptuel [Provenance du jeu de données](/collections-model/fr/modele-cible/actuel/provenance-du-jeu-de-donnees). Cependant, la forte dépendance des soumissionnaires à l'égard de la structure d'enregistrement entraîne la nécessité d'un patron conceptuel dédié. La différence entre une base de données tabulaire et un modèle sémantique est que la structure originale de l'enregistrement ne perdure pas dans le graphe de connaissances : elle peut plutôt être modélisée comme un élément sémantique et conceptuel, ainsi que symbolisée par l'utilisation d'une instance de `E73_Objet_informationnel` concernant l'entité d'intérêt, comme présenté ci-dessus.

### Limitations

Parce que l'enregistrement est un élément conceptuel concernant l'entité d'intérêt (une instance de `E39_Actant` dans ce cas) et parce qu'il n'est pas modélisé comme un graphe nommé, il ne peut pas être un ensemble de triplets concernant une entité spécifique. Plusieurs limites sont induites :

* Cela complexifie les requêtes de triplets appartenant spécifiquement à une entité d'intérêt, car tous les triplets relatifs à cette entité ne peuvent pas être récupérés en utilisant simplement l'URI de l'enregistrement (instance de `E73_Objet_informationnel`) dans une clause `GRAPH`, contrairement aux jeux de données pour lesquels c'est possible (voir le patron conceptuel [Provenance du jeu de données](/collections-model/fr/modele-cible/actuel/provenance-du-jeu-de-donnees)). Pour récupérer ces triplets, une requête plus complexe doit être rédigée, qui comprend une série de patrons conceptuels de triplets connectés et d'autres conditions spécifiques. Par exemple :

```

prefix crm:   <http://www.cidoc-crm.org/cidoc-crm/> 

prefix g:     <https://dopheda.info/graph/> 

prefix actor: <https://dopheda.info/e39/>





CONSTRUCT {

    actor:163 ?p1 ?o1.

    ?o1 ?p2 ?o2.

    ?o2 ?p3 ?o3.

    ?o3 ?p4 ?o4.

    ?o4 ?p5 ?o5.

    ?o5 ?p6 ?o6. #le nombre de triplets dépend du patron conceptuel avec la hiérarchie la plus profonde.

  }

WHERE {

         actor:163 ?p1 ?o1.

         OPTIONAL {?o1 ?p2 ?o2. FILTER (!regex(str(?o1),"/e39/") || (regex(str(?o1),"/e39/") && (?p2=rdf:type || ?p2=rdfs:label)))

      OPTIONAL {?o2 ?p3 ?o3. FILTER (!regex(str(?o2),"/e39/") || (regex(str(?o2),"/e39/") && (?p3=rdf:type || ?p3=rdfs:label)))

         OPTIONAL {?o3 ?p4 ?o4. FILTER (!regex(str(?o3),"/e39/") || (regex(str(?o3),"/e39/") && (?p4=rdf:type || ?p4=rdfs:label)))

            OPTIONAL {?o4 ?p5 ?o5.

                      FILTER (!regex(str(?o4),"/e39/") || (regex(str(?o4),"/e39/") && (?p5=rdf:type || ?p5=rdfs:label)))

                      OPTIONAL {?o5 ?p6 ?o6.

                      FILTER (!regex(str(?o5),"/e39/") || (regex(str(?o5),"/e39/") && (?p6=rdf:type || ?p6=rdfs:label)))

                     } } } } } 

}

```

* Cela complexifie la mise à jour des triplets appartenant à une entité d'intérêt particulière et augmente le risque d'erreurs. Comme dans l'exemple ci-dessus, la récupération des informations à mettre à jour et des impacts de ces mises à jour est un processus précis et compliqué impliquant des requêtes SPARQL complexes. Par conséquent, il est plus simple de mettre à jour le jeu des données que les enregistrements spécifiques, même si peu d'informations ont changé (Gearson et al. 2013).

Pour l'instant, aucun rôle n'a été précisé pour le ou les actants impliqués dans la création ou la mise à jour de l'enregistrement. Dans le cas où plusieurs actants ont été responsables de la création ou de la mise à jour de l'enregistrement (p. ex. avec des rôles différents, tels que rédacteur ou chercheur), il n'est pas possible d'identifier et de documenter ces rôles, et tous les actants sont simplement liés à l'évènement de création ou de mise à jour sans autre qualification. S'il s'avère nécessaire de documenter de manière plus détaillée de telles informations, une révision du patron conceptuel pourrait devenir impérative.

### Enjeux connexes sur GitHub

* [Enjeu n° 14 « Devons-nous gérer les mises à jour des enregistrements (et des graphes nommés?) »](https://github.com/chin-rcip/collections-model/issues/14) (en anglais)
* [Enjeu n° 34 « Les catalogueurs doivent-ils être documentés dans le patron conceptuel Provenance de l'enregistrement? »](https://github.com/chin-rcip/collections-model/issues/34) (en anglais)
* [Enjeu n° 45 « Graphes nommés : Enregistrement vs Jeu de données »](https://github.com/chin-rcip/collections-model/issues/45) (en anglais)

### Cas limites

Certaines institutions patrimoniales peuvent avoir des entités d'intérêt autres que des actants ou des objets. Par exemple, certaines institutions pourraient mettre l’accent sur les lieux et décrire principalement leurs emplacements, leurs appellations, leurs descriptions, etc., de sorte que les enregistrements seraient axés sur les lieux plutôt que sur les actants ou les objets. Pour documenter ces cas, il faudrait accepter que d'autres sous-classes de `E1_Entité_CRM` soient liées aux instances de `E73_Objet_informationnel` en plus des instances de `E39_Actant` et `E22_Objet_élaboré_par_l’humain`.

Les documents créés récemment auront très probablement des dates précises, mais les documents plus anciens, créés lorsque la gestion des collections reposait sur des documents papier plutôt que sur des bases de données, peuvent avoir des dates plus floues référant à des périodes de l'histoire de l'institution, telles que « Sous la responsabilité du conservateur X » ou « Avant la création du musée ». On peut également se demander si un enregistrement peut prendre fin puisque, tant qu'il y a une date, il y a toujours un enregistrement documenté. En outre, la définition d'un contributeur pourrait être floue et inclure des données que le RCIP pourrait récupérer à des fins d'enrichissement (p. ex. Wikidata pourrait avoir une Appellation du contributeur de l'enregistrement).

## Bibliographie

Bruseker, George, Trang Dang, Philippe Michon et Stephen Hart. *Rapport d'enquête sur l'utilisation des graphes nommés du patrimoine culturel (partie 1)*. Rapports techniques DOPHEDA. Ottawa, CA-ON : Réseau canadien d'information sur le patrimoine (RCIP), 2021. [/collections-model/en/technical-reports/current/named-graph-survey-report-1](/collections-model/en/technical-reports/current/named-graph-survey-report-1).

Duranti, Luciana, et Patricia C. Franks, éds. « Record(s) ». *Encyclopedia of Archival Science*. Lanham, US-MD; Londres, UK-LDN : Rowman & Littlefield, 2015 : 315-319.

Gearson, Paula, Alexandre Passant, et Axel Polleres. « SPARQL 1.1 Update ». Recommandation du W3C. 21 mars 2013. [https://www.w3.org/TR/sparql11-update/](https://www.w3.org/TR/sparql11-update/).

Henderson, Harry. « Data ». *Encyclopedia of Computer Science and Technology, Revised Edition* 128. New York, US-NY : Facts on File, Inc., 2009.

Musée des beaux-arts du Canada. « Artistes au Canada ». Gouvernemental. Site Web du Gouvernement du Canada. 12 décembre 2019a. [https://app.pch.gc.ca/application/aac-aic/description-about.app?lang=fr](https://app.pch.gc.ca/application/aac-aic/description-about.app?lang=fr).

———. « Artistes au Canada Droit d'auteur ». Gouvernemental. Site Web du Gouvernement du Canada. 12 décembre 2019b. [https://app.pch.gc.ca/application/aac-aic/droit_auteur-copyright.app?lang=fr](https://app.pch.gc.ca/application/aac-aic/droit_auteur-copyright.app?lang=fr).

Patrimoine canadien, Gouvernement du Canada. « Karsh, Yousuf ». *Artistes au Canada*. Ottawa, CA-ON : Gouvernement du Canada, 2011. [https://app.pch.gc.ca/application/aac-aic/artiste_detailler_bas-artist_detail_bas.app?lang=fr&qlang=en&rID=8494&pID=1&fID=1&ps=50&sort=AM_ASC](https://app.pch.gc.ca/application/aac-aic/artiste_detailler_bas-artist_detail_bas.app?lang=fr&qlang=en&rID=8494&pID=1&fID=1&ps=50&sort=AM_ASC).

