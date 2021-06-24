---
layout: page
language: en
title: How-To - diagrams.net Libraries
permalink: /en/resources/current/how-to/diagrams-net-libraries
other_link: /fr/ressources/actuel/mode-demploi/bibliotheques-logicielles-diagrams-net
sidebar: diagramsen
group: resources
subgroup: how-to
date: 2021-05-26
description: This document provides an overview of diagrams.net libraries and instructions on how to use them.
---


**Version**: 1.0

**Created date**: 2021-04-22

**Last update**: 2021-05-26

**Abstract**: This document provides an overview of diagrams.net libraries and instructions on how to use them.

**Contact**: For any questions and/or feedback, please contact us at pch.RCIP-CHIN.pch@canada.ca, indicating “diagrams.net libraries” in the subject line of the email.

## Main Use

  - To facilitate the visualization of data models based on [CIDOC CRM](http://www.cidoc-crm.org/) and [its extensions](http://www.cidoc-crm.org/collaborations) when using the diagrams.net tool.

## Context

**[diagrams.net](https://www.diagrams.net/) libraries** is a collection of custom shape library files (.xml) of ontologies used to represent semantic patterns through [diagrams.net](https://www.diagrams.net/). It is maintained by the Canadian Heritage Information Network (CHIN) and used to generate diagrams in the context of its Linked Open Data projects. Currently, CHIN provides seven libraries for the following CIDOC CRM ontologies (i.e. the ones that are officially released in RDFS format). The libraries are of benefit to users who design diagrams for data models that are based on CIDOC CRM.

  - CIDOC CRM base (version 6.2.1)

  - FRBRoo (version 2.4)

  - PRESSoo (version 1.0)

  - CRMdig (version 3.2.2)

  - CRMpc (version 1.1.1)

  - CRMarchaeo (version 1.4.1)

  - CRMgeo (version 1.2)

*This work is inspired by the [work of Nicola Carboni](https://github.com/ncarboni/Shapes_CIDOC-CRM).*

## Essential Vocabularies and Prior Knowledge

A custom library is a set of pre-designed shapes that can be easily dragged and dropped in the drawing canvas to facilitate the drawing process. It is usually found on the left side panel of the diagrams.net editor.

Each library contains the shapes of all the [classes](https://chin-rcip.github.io/collections-model/en/resources/current/glossary#class-noun) as well as the connectors for the [properties](https://chin-rcip.github.io/collections-model/en/resources/current/glossary#property-noun) of each ontology. The colour scheme (see below) is based on a proposal by George Bruseker for [CIDOC CRM](http://www.cidoc-crm.org/).

<table>
<tbody>
<tr><td style="background-color: #FFFFFF">`E1_CRM_Entity` and any subclasses that are not subclasses of the below classes (#FFFFFF)</td></tr>
<tr><td style="background-color: #82C3EC">`E2_Temporal_Entity` and its subclasses (#82C3EC)</td></tr>
<tr><td style="background-color: #FAB565">`E55_Type` and its subclasses (#FAB565)</td></tr>
<tr><td style="background-color: #86BCC8">`E52_Time-Span` and its subclasses (#86BCC8)</td></tr>
<tr><td style="background-color: #FEF3BA">`E41_Appellation` and its subclasses (#FEF3BA)</td></tr>
<tr><td style="background-color: #94CC7D">`E53_Place` and its subclasses (#94CC7D)</td></tr>
<tr><td style="background-color: #FDDC34">`E28_Conceptual_Object` and its subclasses (#FDDC34)</td></tr>
<tr><td style="background-color: #E1BA9C">`E18_Physical_Thing` and its subclasses (#E1BA9C)</td></tr>
<tr><td style="background-color: #FFBDCA">`E41_Actor` and its subclasses (#FFBDCA)</td></tr>
<tr><td style="background-color: #CC80FF">All PC_Classes (#CC80FF)</td></tr>
</tbody>
</table>

## Intended Audience(s) and Section Description

The tool can be used by anyone who wants to visualize data models that are based on CIDOC CRM and its extensions. There are two methods of loading the libraries depending on the version of diagrams.net being used:

  - [Desktop version](#opening-a-library-file)

  - [Online version](#loading-a-library-via-a-url)

The [Using the libraries](#using-the-libraries) section provides a more detailed description and guide to the usage of the libraries themselves.

## Instructions

### Loading the Libraries

To use the libraries, there are two options:

  - Opening a library XML file directly to the editor, or

  - Loading a library via URL.

#### Opening a Library File

*This option is most suitable for the diagrams.net desktop version.*

Launch the diagrams.net editor, click **File Open Library from**, then:

1.  If the Github repository or the XML file(s) are downloaded:
    
    1.  Select the service or device where the file(s) are stored;
    
    2.  Locate and select the library (the file extension will be
        .xml), and click **Choose**.

OR

2.  Directly use the Github URL for each library file in the folder **/cidoc-crm**:
    
    1.  CIDOC CRM base
        (https://raw.githubusercontent.com/chin-rcip/diagrams.net_libraries/main/cidoc-crm/crm_library.xml)
    
    2.  FRBRoo
        ([https://raw.githubusercontent.com/chin-rcip/diagrams.net_libraries/main/cidoc-crm/frbroo_library.xml](https://raw.githubusercontent.com/chin-rcip/diagrams.net_libraries/main/cidoc-crm/frbroo_library.xml))
    
    3.  PRESSoo
        (https://raw.githubusercontent.com/chin-rcip/diagrams.net_libraries/main/cidoc-crm/pressoo_library.xml)
    
    4.  CRMdig
        (https://raw.githubusercontent.com/chin-rcip/diagrams.net_libraries/main/cidoc-crm/crmdig_library.xml)
    
    5.  CRMpc
        ([https://raw.githubusercontent.com/chin-rcip/diagrams.net_libraries/main/cidoc-crm/crmpc_library.xml](https://raw.githubusercontent.com/chin-rcip/diagrams.net_libraries/main/cidoc-crm/crmpc_library.xml))
    
    6.  CRMarchaeo
        (([https://raw.githubusercontent.com/chin-rcip/diagrams.net_libraries/main/cidoc-crm/crmarchaeo_library.xml](https://raw.githubusercontent.com/chin-rcip/diagrams.net_libraries/main/cidoc-crm/crmpc_library.xml))
    
    7.  CRMgeo
        (([https://raw.githubusercontent.com/chin-rcip/diagrams.net_libraries/main/cidoc-crm/crmgeo_library.xml](https://raw.githubusercontent.com/chin-rcip/diagrams.net_libraries/main/cidoc-crm/crmpc_library.xml))

![](/collections-model/images/diagrams_net_en_1.png)

#### Loading a Library via a URL

*This option is most suitable for the diagrams.net online version.*

Click on the following URLs to open the diagrams.net editor with:

  - [CRM base library](https://app.diagrams.net/?splash=0&clibs=Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrm_library.xml)

  - [FRBRoo library](https://app.diagrams.net/?splash=0&clibs=Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Ffrbroo_library.xml)

  - [PRESSoo library](https://app.diagrams.net/?splash=0&clibs=Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fpressoo_library.xml)

  - [CRMdig library](https://app.diagrams.net/?splash=0&clibs=Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrmdig_library.xml)

  - [CRMpc library](https://app.diagrams.net/?splash=0&clibs=Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrmpc_library.xml)

  - [CRMarchaeo library](https://app.diagrams.net/?splash=0&clibs=Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrmarchaeo_library.xml)

  - [CRMgeo library](https://app.diagrams.net/?splash=0&clibs=Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrmgeo_library.xml)

  - [All libraries](https://app.diagrams.net/?splash=0&clibs=Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrm_library.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Ffrbroo_library.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrmdig_library.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrmpc_library.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fpressoo_library.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrmarchaeo_library.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrmgeo_library.xml)

Once loaded, the library is usually cached by the browser, so there is no need to load it every time, unless the browser data has been cleared.

### Using the Libraries

Each library contains two types of shapes:

  - Rounded rectangle shapes for classes (each shape is filled with colour, per the colour scheme described above).

  - Black arrows for properties.

Each shape has a label based on the CIDOC CRM naming convention, i.e. with an underscore after the entity’s code and between each string (`E2_Temporal_Entity`), and spaces in its title (E2 Temporal Entity) to facilitate the “**Search Shapes**” function located at the top of the left side panel.

![](/collections-model/images/diagrams_net_en_2.png)

To search for any shape, either classes or properties, enter its CIDOC CRM code and/or label.

![](/collections-model/images/diagrams_net_en_3.png)

## Memory Aids

  - Use [this link](https://app.diagrams.net/?splash=0&clibs=Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrm_library.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Ffrbroo_library.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrmdig_library.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrmpc_library.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fpressoo_library.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrmarchaeo_library.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrmgeo_library.xml) to load all libraries at once in the diagrams.net online version.

  - Use the Search tool to find an entity, either by code and/or label.

## For More Information

Consult the following resources for further information on how to generate, share and load diagrams.net’s custom libraries in general:

  - [https://desk.draw.io/support/solutions/articles/16000067790](https://desk.draw.io/support/solutions/articles/16000067790)

  - [http://jgraph.github.io/drawio-libs/](http://jgraph.github.io/drawio-libs/)

## Licence

Files in this repository are made available under the MIT License. To meet the attribution requirements of this license, you must indicate the copyright holder using the following:

> Copyright (c) 2021 Canadian Heritage Information Network, Canadian Heritage, Government of Canada - Réseau Canadien d'information sur le patrimoine, Patrimoine canadien, Gouvernement du Canada

> diagrams.net is distributed under [Apache License 2.0](https://github.com/jgraph/drawio/blob/dev/LICENSE).
> Copyright 2021 diagrams.net (JGraph)

## Bibliography

Benson, David. 2020. “Work with Custom Shape Libraries.” Legacy Desk - Do Not Use. September 15, 2020. [https://drawio.freshdesk.com/support/solutions/articles/16000067790-work-with-custom-shape-libraries](https://drawio.freshdesk.com/support/solutions/articles/16000067790-work-with-custom-shape-libraries).

Canadian Heritage Information Network (CHIN). 2021a. “class (noun).” In *Glossary*. Ottawa, ON: Government of Canada / Gouvernement du Canada. [https://chin-rcip.github.io/collections-model/en/resources/current/glossary#class-noun](https://chin-rcip.github.io/collections-model/en/resources/current/glossary#class-noun)

———. 2021b. “property (noun).” In *Glossary*. Ottawa, ON: Government of Canada / Gouvernement du Canada. [https://chin-rcip.github.io/collections-model/en/resources/current/glossary#property-noun](https://chin-rcip.github.io/collections-model/en/resources/current/glossary#property-noun)

Carboni, Nicola. (2020) 2021. Shapes_CIDOC-CRM. [https://github.com/ncarboni/Shapes_CIDOC-CRM](https://github.com/ncarboni/Shapes_CIDOC-CRM)

jgraph. n.d. “Diagrams.Net Libraries.” Drawio-Libs. Accessed May 13, 2021. [http://jgraph.github.io/drawio-libs/](http://jgraph.github.io/drawio-libs/)