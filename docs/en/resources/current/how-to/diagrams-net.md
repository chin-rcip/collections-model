---
layout: page
language: en
title: How-To - diagrams.net Libraries
permalink: /en/resources/current/how-to/diagrams-net-libraries
other_link: /fr/ressources/actuel/mode-demploi/bibliotheques-logicielles-diagrams-net
sidebar: diagramsen
group: resources
subgroup: how-to
date: 2024-07-16
description: This document provides an overview of diagrams.net libraries and instructions on how to use them.
---


**Version**: 1.0

**Created date**: 2021-04-22

**Last update**: 2024-07-16

**Abstract**: This document provides an overview of diagrams.net libraries and instructions on how to use them.

**Contact**: For any questions and/or feedback, please contact us at rcip-chin@pch.gc.ca, indicating “diagrams.net libraries” in the subject line of the email.

## Main Use

  - To facilitate the visualization of data models based on [CIDOC CRM](http://www.cidoc-crm.org/) and [its extensions](http://www.cidoc-crm.org/collaborations) when using the diagrams.net tool.

## Context

**[diagrams.net](https://www.diagrams.net/) libraries** is a collection of custom shape library files (.xml) of ontologies used to represent semantic patterns through [diagrams.net](https://www.diagrams.net/). It is maintained by the Canadian Heritage Information Network (CHIN) and used to generate diagrams in the context of its Linked Open Data projects. Currently, CHIN provides eight libraries for the following CIDOC CRM ontologies (i.e. the ones that are officially released in RDFS format). The libraries are of benefit to users who design diagrams for data models that are based on CIDOC CRM.

  - CIDOC CRM base (version 7.1.3): includes two libraries, one with properties' quantification, and one without.

  - FRBRoo (version 2.4)

  - PRESSoo (version 1.0)

  - CRMdig (version 3.2.2)

  - CRMpc (version 7.1.3)

  - CRMarchaeo (version 1.4.1)

  - CRMgeo (version 1.2)

*This work is inspired by the [work of Nicola Carboni](https://github.com/ncarboni/Shapes_CIDOC-CRM).*

## Essential Vocabularies and Prior Knowledge

A custom library is a set of pre-designed shapes that can be easily dragged and dropped in the drawing canvas to facilitate the drawing process. It is usually found on the left side panel of the diagrams.net editor.

Each library contains the shapes of all the [classes](https://chin-rcip.github.io/collections-model/en/resources/current/glossary#class-noun) as well as the connectors for the [properties](https://chin-rcip.github.io/collections-model/en/resources/current/glossary#property-noun) of each ontology. The colour scheme (see below) is based on a proposal by CIDOC CRM SIG for [CIDOC CRM](http://www.cidoc-crm.org/).

<table>
<tbody>
<tr><td style="background-color: #FFFFFF"><code class="language-plaintext highlighter-rouge">E1 CRM Entity</code> and any subclasses that are not subclasses of the below classes (#FFFFFF)</td></tr>
<tr><td style="background-color: #82DDFF"><code class="language-plaintext highlighter-rouge">E2 Temporal Entity</code> and its subclasses (#82DDFF)</td></tr>
<tr><td style="background-color: #C78E66"><code class="language-plaintext highlighter-rouge">E18 Physical Thing</code> and its subclasses (#C78E66)</td></tr>
<tr><td style="background-color: #FDDC34"><code class="language-plaintext highlighter-rouge">E28 Conceptual Object</code> and its subclasses (#FDDC34)</td></tr>
<tr><td style="background-color: #FFBDCA"><code class="language-plaintext highlighter-rouge">E39 Actor</code> and its subclasses (#FFBDCA)</td></tr>
<tr><td style="background-color: #FEF3BA"><code class="language-plaintext highlighter-rouge">E41 Appellation</code> and its subclasses (#FEF3BA)</td></tr>
<tr><td style="background-color: #86BCC8"><code class="language-plaintext highlighter-rouge">E52 Time-Span</code> and its subclasses (#86BCC8)</td></tr>
<tr><td style="background-color: #94CC7D"><code class="language-plaintext highlighter-rouge">E53 Place</code> and its subclasses (#94CC7D)</td></tr>
<tr><td style="background-color: #B8B8B8"><code class="language-plaintext highlighter-rouge">E54 Dimension</code> and its subclasses (#B8B8B8)</td></tr>
<tr><td style="background-color: #FAB565"><code class="language-plaintext highlighter-rouge">E55 Type</code> and its subclasses (#FAB565)</td></tr>
<tr><td style="background-color: #F0F0F0"><code class="language-plaintext highlighter-rouge">E59 Primitive Value</code> and its subclasses (#F0F0F0)</td></tr>
<tr><td style="background-color: #CC80FF"><code class="language-plaintext highlighter-rouge">E92 Spacetime Volume</code> and its subclasses (#CC80FF)</td></tr>
<tr><td style="background-color: #FFFFFF">All <code class="language-plaintext highlighter-rouge">PC Classes</code> (#FFFFFF)</td></tr>
<tr><td style="background-color: #FFFFFF">Instances (#FFFFFF)</td></tr>
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

        a. Without properties' quantification
           (https://raw.githubusercontent.com/chin-rcip/diagrams.net_libraries/main/cidoc-crm/crm_library.xml)

        b. With properties' quantification
           (https://raw.githubusercontent.com/chin-rcip/diagrams.net_libraries/main/cidoc-crm/crm_quantifications_library.xml)
    
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

  - [CRM base library (without properties' quantification)](https://app.diagrams.net/?splash=0&clibs=Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrm_library.xml)

  - [CRM base library (with properties' quantification)](https://app.diagrams.net/?splash=0&clibs=Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrm_quantifications_library.xml)

  - [FRBRoo library](https://app.diagrams.net/?splash=0&clibs=Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Ffrbroo_library.xml)

  - [PRESSoo library](https://app.diagrams.net/?splash=0&clibs=Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fpressoo_library.xml)

  - [CRMdig library](https://app.diagrams.net/?splash=0&clibs=Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrmdig_library.xml)

  - [CRMpc library](https://app.diagrams.net/?splash=0&clibs=Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrmpc_library.xml)

  - [CRMarchaeo library](https://app.diagrams.net/?splash=0&clibs=Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrmarchaeo_library.xml)

  - [CRMgeo library](https://app.diagrams.net/?splash=0&clibs=Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrmgeo_library.xml)

  - [All libraries](https://app.diagrams.net/?splash=0&clibs=Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrm_library.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrm_quantifications_library.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Ffrbroo_library.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrmdig_library.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrmpc_library.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fpressoo_library.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrmarchaeo_library.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrmgeo_library.xml)

Once loaded, the library is usually cached by the browser, so there is no need to load it every time, unless the browser data has been cleared.

### Using the Libraries

Each library contains two types of shapes:

1. Rounded rectangle shapes for classes (each shape is filled with colour, per the colour scheme described above).

    - Shape:

        - Rounded rectangle

        - Border:

            - solid 
            
            - black
            
            - 1 pt
        
        - Width: 140

        - Height: 70 

        - Fill: per the colour scheme described above

    - Text:

        - Font: Helvetica

        - Size: 16

        - Color: black

        - Horizontal align: center

        - Vertical align: middle

        - Weight: bold

        - Word wrap

        - Value: entity name without underscore

    - Data:

        - URI
        
        - Labels in available languages
        
        - No scope note
        
        - Link (clickable)

2. Black arrows for properties.

    - Shape:

        - One-way arrow

        - Stroke width: 2 pt
        
        - Color: black

    - Text:

        - Font: Helvetica

        - Size: 14

        - Color: black

        - Horizontal align: center

        - Vertical align: middle

        - Weight: bold

        - Background color: white

        - Value: entity name without underscore, quantifications

    - Data:

        - URI
        
        - Labels in available languages
        
        - No scope note
        
        - Link (clickable)

![](/collections-model/images/diagrams_net_en_2.png)

To search for any shape, either classes or properties, enter its CIDOC CRM code and/or label.

![](/collections-model/images/diagrams_net_en_3.png)

## Memory Aids

  - Use [this link](https://app.diagrams.net/?splash=0&clibs=Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrm_library.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrm_quantifications_library.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Ffrbroo_library.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrmdig_library.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrmpc_library.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fpressoo_library.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrmarchaeo_library.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fchin-rcip%2Fdiagrams.net_libraries%2Fmain%2Fcidoc-crm%2Fcrmgeo_library.xml) to load all libraries at once in the diagrams.net online version.

  - Use the Search tool to find an entity, either by code and/or label.

## For More Information

Consult the following resources for further information on how to generate, share and load diagrams.net’s custom libraries in general:

  - [https://desk.draw.io/support/solutions/articles/16000067790](https://desk.draw.io/support/solutions/articles/16000067790)

  - [http://jgraph.github.io/drawio-libs/](http://jgraph.github.io/drawio-libs/)

## Licence

Files in this repository are made available under the MIT License. To meet the attribution requirements of this license, you must indicate the copyright holder using the following:

> Copyright (c) 2021-2022 Canadian Heritage Information Network, Canadian Heritage, Government of Canada - Réseau Canadien d'information sur le patrimoine, Patrimoine canadien, Gouvernement du Canada

> diagrams.net is distributed under [Apache License 2.0](https://github.com/jgraph/drawio/blob/dev/LICENSE).
> Copyright 2021 diagrams.net (JGraph)

## Bibliography

Benson, David. 2020. “Work with Custom Shape Libraries.” Legacy Desk - Do Not Use. September 15, 2020. [https://drawio.freshdesk.com/support/solutions/articles/16000067790-work-with-custom-shape-libraries](https://drawio.freshdesk.com/support/solutions/articles/16000067790-work-with-custom-shape-libraries).

Canadian Heritage Information Network (CHIN). 2021a. “class (noun).” In *Glossary*. Ottawa, ON: Government of Canada / Gouvernement du Canada. [https://chin-rcip.github.io/collections-model/en/resources/current/glossary#class-noun](https://chin-rcip.github.io/collections-model/en/resources/current/glossary#class-noun)

———. 2021b. “property (noun).” In *Glossary*. Ottawa, ON: Government of Canada / Gouvernement du Canada. [https://chin-rcip.github.io/collections-model/en/resources/current/glossary#property-noun](https://chin-rcip.github.io/collections-model/en/resources/current/glossary#property-noun)

Carboni, Nicola. (2020) 2021. Shapes_CIDOC-CRM. [https://github.com/ncarboni/Shapes_CIDOC-CRM](https://github.com/ncarboni/Shapes_CIDOC-CRM)

jgraph. n.d. “Diagrams.Net Libraries.” Drawio-Libs. Accessed May 13, 2021. [http://jgraph.github.io/drawio-libs/](http://jgraph.github.io/drawio-libs/)