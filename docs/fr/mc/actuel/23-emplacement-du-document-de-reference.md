---
layout: page
language: fr
title: Emplacement du document de référence
permalink: /fr/modele-cible/actuel/emplacement-du-document-de-reference
other_link: /en/target-model/current/reference-document-location
sidebar: mc22
date: 2022-06-30
description: La Spécification du modèle cible des actants modélise sémantiquement les actants dans un contexte patrimonial. Les patrons conceptuels les plus pertinents pour la vie des actants sont présentés avec des diagrammes et des exemples qui les illustrent, ainsi qu'un compte rendu et une explication des décisions pertinentes qui ont été prises lors de l'élaboration desdits patrons conceptuels. Il s'agit d'une documentation théorique qui n'a jamais été testée ou mise en application.
---

## Aperçu {#apercu}

Ce patron conceptuel peut être utilisé pour représenter les informations de base relatives à l'identification d'un document contenant des informations sur un actant à des fins de référence. Il comprend : 

* La cote attribuée à un document de référence par son institution d'archivage;
* L'appellation de l'institution d'archivage d'un document de référence;
* L'emplacement physique d'un document de référence.

Ce patron conceptuel ne doit pas être utilisé pour représenter :

* La description détaillée d'un document de référence;
* L'emplacement de la représentation numérique d'un document de référence.

## Introduction et contexte

### Historique théorique {#historique-theorique}

En 1993, Margaret Hedstrom prévoyait que l'arrivée des technologies de l'information allait induire un changement de paradigme dans les sciences de l'information; la pratique principale des archivistes, qui consiste à augmenter les rares informations descriptives, allait s'adapter pour mettre l’accent sur l'identification, la sélection et la récupération des connaissances (Hedstrom 1993, 59). Cette évolution des pratiques, combinée à la numérisation de l'information qui a conduit les utilisateurs·rices à devenir de plus en plus mondiaux, a mis l'accent sur la localisation de l'incarnation physique de l'information comme moyen de classer les documents, de les distinguer les uns des autres et de les retrouver (Hjørland & Gnoli 2016). 

Les organisations patrimoniales comme les musées organisent souvent leurs données de base selon des principes qui diffèrent de ceux des archives et des bibliothèques, tels que des systèmes de classification par sujet ou par exposition plutôt que des systèmes qui seraient classifiés par discipline ou par phénomène. Néanmoins, ils mobilisent souvent les normes pertinentes des bibliothèques et des archives pour organiser les informations, telles que les matériaux de référence, par exemple les bibliographies utilisées dans le contexte de la recherche (Hjørland & Gnoli 2016). Ainsi, la documentation exacte de l'emplacement d'un document est cruciale et, même si elle est parfois étroitement liée au concept de provenance (voir les patrons conceptuels [Provenance du jeu de données](/collections-model/fr/modele-cible/actuel/provenance-du-jeu-de-donnees) et [Provenance de l’enregistrement](/collections-model/fr/modele-cible/actuel/provenance-de-lenregistrement)), elle doit en être distinguée, car l'emplacement se rapporte au lieu physique où se trouve un document, quel que soit son ou sa gardien·ne (Tognoli & Guimaraes 2018).

Enregistrer l'emplacement physique d'un document stocké est d'autant plus important considérant qu'il est souvent nécessaire pour les personnes de ce domaine de consulter les originaux. L'emplacement d'un document ou de son ou sa principal·e gardien·ne peut parfois différer de l'endroit où le document est stocké. Il est donc nécessaire d'identifier et de localiser le document physique contenant les informations de référence du patrimoine pour une description exacte des informations et leur récupération. 

Il est important d'identifier : 

* Qui gère (par opposition à possède) le document (c.-à-d. le nom de l'institution d'archivage qui gère le document) afin de pouvoir la contacter en cas de besoin; 
* L'endroit où se trouve son lieu de stockage (c.-à-d. l'adresse de l'institution d'archivage qui gère le document) afin qu'une personne puisse accéder au document; 
* Où retrouver le document dans cet établissement (c.-à-d. l'emplacement du document dans le lieu de stockage) afin qu'il puisse être consulté par une personne. 

### Énoncé des besoins {#enonce-des-besoins}

La plupart des musées ainsi que d'autres organisations patrimoniales détiennent des enregistrements sur les actants qu'ils documentent. Par exemple, la base de données [Artistes au Canada](https://app.pch.gc.ca/application/aac-aic/description-about.app?lang=fr) documente les sources primaires des informations sur ses enregistrements dans le champ de données « Emplacement du fichier ». Ces informations peuvent donner accès à d'autres ressources dans lesquelles d'autres données sur l'actant pourraient être documentées.

Trois informations de base sont nécessaires pour identifier rapidement et accéder éventuellement à ces sources de référence. Avant tout, il convient d'indiquer l'institution qui détient l'enregistrement, c'est-à-dire son appellation. L'institution elle-même peut avoir plusieurs succursales à différents endroits, mais l'endroit spécifique où l'enregistrement est conservé doit être documenté. En outre, les archives traitées et leurs éléments se voient toujours attribuer des cotes à des fins d'identification et de recherche. 

## Description du patron conceptuel

L'objet documentaire de référence, une instance de `E22_Objet_élaboré_par_l’humain`, est lié à :

* Une instance de `E55_Type` (un nœud doté d’un qualifiant spécifié) portant le libellé « Document de référence » par la propriété `P2_a_pour_type`;
* La valeur du [Lieu du document de référence](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#lieu-du-document-de-reference) (une instance de `E53_Lieu`) par la propriété `P54_a_actuellement_pour_localisation_fixe`;
* L'institution dépositaire, qui est une instance de `E74_Groupe`, par la propriété `P49_a_pour_actant_détenteur_actuel_ou_antérieur`. Cette instance de `E74_Groupe` est liée à une instance de `E41_Appellation` et de `E33_Objet_linguistique` par la propriété `P1_est_identifié_par` qui rend la valeur littérale de l'[Appellation de l’institution détenant le document de référence](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-de-linstitution-detenant-le-document-de-reference) par la propriété `P190_a_pour_contenu_symbolique`;
* Une instance de `E42_Identifiant` par la propriété `P1_est_identifié_par`. Cette instance de `E42_Identifiant` est qualifiée par une instance de `E55_Type` (un nœud doté d’un qualifiant spécifié) portant le libellé « Cote » par la propriété `P2_a_pour_type`. La même instance de `E42_Identifiant` rend également la valeur littérale de la [Cote du document de référence](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#cote-du-document-de-reference) par la propriété `P190_a_pour_contenu_symbolique`;
* Une instance de `E31_Document` par la propriété `P128_est_le_support_de`. Cette instance de `E31_Document` est ensuite liée à l'actant documenté dans l'objet documentaire de référence (une instance de `E39_Actant`) par la propriété `P70_documente` et est qualifiée par une instance de `E55_Type` (un nœud doté d’un qualifiant spécifié) portant le libellé « Enregistrement » par la propriété `P2_a_pour_type`.

## Diagramme

<a name="074_PatronConceptuel_DocumentDeReference_p"></a>074_PatronConceptuel_DocumentDeReference_p

<iframe frameborder="0" style="width:100%;height:500px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=074_PatronConceptuel_DocumentDeReference_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1pBwf5BPW9tJvxG33NMQGlikP67EsA6Nm%26export%3Ddownload"></iframe>

## Exemples

Les archives de Yousuf Karsh se trouvent à Bibliothèque et Archives Canada (`P190_a_pour_contenu_symbolique`, Appellation de l'institution détenant le document de référence) au 625 boulevard Carr, Gatineau QC Canada (`P54_a_actuellement_pour_localisation_fixe`, Lieu du document de référence). Son numéro de référence est R613-0-5-E (`P190_a_pour_contenu_symbolique`, Cote du document de référence) (Bibliothèque et Archives Canada 2022). 

<div id="0001_100_reference-document-location" class="example"></div>

## Documentation connexe

### Modèles externes {#modeles-externes}

* Linked.art : [Texts and Documents](https://linked.art/model/document/)
* SARI : [Archival Unit Reference Data Model](https://docs.swissartresearch.net/et/archival/) 

### Nœuds de saisie {#noeuds-de-saisie}

* [Appellation de l’institution détenant le document de référence](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#appellation-de-linstitution-detenant-le-document-de-reference) \| Liste de vérification
* [Cote du document de référence](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#cote-du-document-de-reference) | [Liste de vérification](lien à venir)]
* [Lieu du document de référence](/collections-model/fr/specification-des-chemins-semantiques/actuel/noeuds-de-saisie#lieu-du-document-de-reference) \| Liste de vérification

### Entités du CIDOC CRM {#entites-du-cidoc-crm}

* `E22_Objet_élaboré_par_l’humain` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E22)]
* `E31_Document` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E31)]
* `E33_Objet_linguistique` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E33)]
* `E39_Actant` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E39)]
* `E41_Appellation` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E41)]
* `E42_Identifiant` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E42)]
* `E53_Lieu` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E53)]
* `E55_Type` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E55)]
* `E74_Groupe` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/classes/E74)]
* `P1_est_identifié_par (identifie)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P1)]
* `P2_a_pour_type (est_le_type_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P2)]
* `P49_a_pour_actant_détenteur_actuel_ou_antérieur (est_l'actant_détenteur_actuel_ou_antérieur_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P49)]
* `P54_a_actuellement_pour_localisation_fixe (est_actuellement_la_localisation_fixe_de)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P54)]
* `P70_documente (est_documenté_dans)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P70)]
* `P128_est_le_support_de (a_pour_support)` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P128)]
* `P190_a_pour_contenu_symbolique` [[Note d'application](https://chin-rcip.github.io/cidoc_crm_fr-ca/v7.1/proprietes/P190)]

## Discussion

### Justification

Dans le CIDOC CRM, il existe une distinction entre l'information et le support physique de cette information (tel qu'un livre, un document, etc.) (Bekiari et al. 2021, sect. E73 Information Object). Il est donc nécessaire d'employer la classe `E22_Objet_élaboré_par_l’humain` conjointement avec la classe `E31_Document` pour documenter l'actant de référence (`E39_Actant`) en utilisant la propriété `P70_documente`.

La classe `E73_Objet_informationnel` englobe un large ensemble de concepts qui ont une « structure objectivement reconnaissable et sont documentés comme des unités uniques » (Le Bœuf et al. 2015, sect. E73 Information Object; notre traduction)]. Cependant, il est également conseillé que « les instances de `E73_Objet_informationnel` de nature documentaire [...] soient déclarées comme des instances de la sous-classe `E31_Document` » (Le Bœuf et al. 2015, sect. E73 Information Object; notre traduction), c'est pourquoi cette dernière indication a été appliquée pour le modèle DOPHEDA. 

En ce qui concerne l'institution détenant l'objet documentaire de référence, il y a une distinction entre son emplacement physique (p. ex. la ville, l'adresse ou le bâtiment où il est établi - qui est documenté comme une instance de `E53_Place`) et l'institution elle-même (c.-à-d. une instance de `E74_Groupe`). 

### Limitations

Actuellement, ce patron conceptuel est modélisé pour documenter les données minimales relatives au document de référence en relation avec l'actant concerné. Ainsi, les autres détails descriptifs du document de référence ne sont pas pris en compte. 

### Enjeux connexes sur GitHub

[Enjeu no 4 « Emplacement des fichiers papiers et AiC »](https://github.com/chin-rcip/chin-rcip/issues/4) (en anglais)

### Cas limites

La cote d'un document de référence réfère à l'identifiant d'un document qui, à son tour, détermine son emplacement au sein d'une institution. Cependant, une institution archivistique peut avoir plusieurs adresses physiques ou succursales. Si le bâtiment où est conservé le document de référence n'a pas de zone de documentation assignée, il pourrait être documenté sous le nœud de saisie Cote du document de référence (p. ex. « PS8576 U57 W46 1979 - Collection générale Wellington »), le nœud de saisie Lieu du document de référence (p. ex. « 395 Wellington St, Ottawa, ON K1A 0N4 - Collection générale Wellington ») ou le nœud de saisie Appellation de l'institution détenant le document de référence (p. ex. « Bibliothèque et Archives Canada - Collection générale Wellington »). Cela pourrait être problématique en termes de saisie de données, mais serait atténué par le fait que toutes ces informations sont représentées dans un seul patron conceptuel. Cela peut toutefois créer des informations contradictoires ou déroutantes. 

## Bibliographie

Bekiari, Chryssoula, George Bruseker, Martin Doerr, Christian-Emil Ore, Stephen Stead, et Athanasios Velios, éds. *Definition of the CIDOC Conceptual Reference Model*. Documentations du CIDOC CRM, 7.1. Paris, FR-IDF : CIDOC CRM Special Interest Group 2021. [http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf](http://cidoc-crm.org/sites/default/files/CIDOC%20CRM_v.7.1%20%5B8%20March%202021%5D.pdf).

Bibliothèque et Archives Canada. « Yousuf Karsh Fonds [Multiple Media] ». Bibliothèque et Archives Canada, 2022. [https://recherche-collection-search.bac-lac.gc.ca/eng/home/record?app=fonandcol&IdNumber=138136](https://recherche-collection-search.bac-lac.gc.ca/eng/home/record?app=fonandcol&IdNumber=138136).

Hedstrom, Margaret. « Descriptive Practices for Electronic Records: Deciding What Is Essential and Imagining What Is Possible ». Archivaria 36 (1er janvier 1993) : 53‑63.

Hjørland, Birger, et Claudio Gnoli. « Knowledge Organization ». *Encyclopedia of Knowledge Organization*. Nancy, FR-GES : International Society for Knowledge Organization, 2016. [https://www.isko.org/cyclo/knowledge_organization](https://www.isko.org/cyclo/knowledge_organization).

Le Bœuf, Patrick, Martin Doerr, Christian Emil Ore, et Stephen Stead, éds. « E73 Information Object ». *Definition of the CIDOC Conceptual Reference Model*. Documentations du CIDOC CRM, 6.2.1. Paris, FR-IDF : Conseil international des musées (ICOM), 2015. [http://www.cidoc-crm.org/sites/default/files/cidoc_crm_version_6.2.1.pdf](http://www.cidoc-crm.org/sites/default/files/cidoc_crm_version_6.2.1.pdf).

Tognoli, Natália Bolfarini, and José Augusto Chaves Guimarães. "Provenance." *Encyclopedia of Knowledge Organization*. Nancy, FR-GES: International Society for Knowledge Organization, 2018. [https://www.isko.org/cyclo/provenance](https://www.isko.org/cyclo/provenance).