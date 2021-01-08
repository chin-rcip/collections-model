---
layout: page
title: Entry Nodes
permalink: /semantic-paths-specification/current/entry-nodes
sidebar: sps
---

---

## Actor Appellation

|---|---|
|**Scope**|This field designates the entire identifying word(s), number(s), symbol(s) or code(s) by which an entity (personal or corporate) is distinguished from others, such as the name, title, or designation of an actor as it has been attributed by a contributing institution. It is an identifying agreed upon term that is descriptive or connotative. If it is made of the concatenation of numerous parts, it should include all of them (such as honorifics, titles, etc.).|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|E39\_Actor|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P1\_is\_identified\_by -\> crm:E41\_Appellation + crm:E33\_Linguistic\_Object -\> crm:P190\_has\_symbolic\_content -\> **xsd:string**</span>|
|**Target Model View(s)**|[Identifiers and Appellations](https://chin-rcip.github.io/collections-model/target-model/current/identification#identifiers-and-appellations)|
|**Semantic Valuation**|*Low*: The provided values contain unstructured information of the appellation, such as there is no systematic and automatic way to recognise the different part of an appellation or it cannot be parsed automatically by reconciliation tools, but still contains the required information.<br><br>*Medium*: The provided values contain structured information that can be automatically cleaned and reconciled with other entities in other datasets.<br>Accepted Value Type(s): String<br><br>*High*: The provided values only contain structured information that can be automatically reconciled with other entities in other datasets.<br>Accepted Value Type(s): String|
|**Typical Case(s)**|*Kitwancool*was painted by Emily Carr in 1928. In this case an institution could decide to enter “Emily Carr” in the Actor Appellation field. It would also be possible to use the Actor Appellation Part fields to create an “Emily” Actor Appellation Part (“First Name” in the Actor Appellation Part Type) and a “Carr” Actor Appellation Part (“Last Name” in the Actor Appellation Part Type).<br><br>However, such Appellations should be indicated as Non-Prefered under Actor Appellation Precedence so that original names have precedence. This would especially be the case for Indigenous creators who might have been assigned a name or number by Canadian governing bodies in lieu of their own name. In such cases CHIN advises institutions to always prefer the Appellation preferred by the Actor.<br><br>Power Corporation of Canada, headquartered in Montréal, has an important private collection of artworks. Another Actor Appellation could be created for “Power Corp” that is a brand name (under Actor Appellation Type) of Power Corporation of Canada. Its International Securities Identification Number (ISIN) is “CA7392391016” and it is traded as “TSX: POW”, both of which could have their dedicated Actor Appellations as well (with their respective Actor Appellation Type being “International Securities Identification Number” and “Stock Symbol”..|
|**Edge Case(s)**|If a war artist was assigned the number “M32 435 C84” (his military registration number), this number would qualify as an Actor Appellation and the Actor Appellation Type would be “Military Registration Number” or “Military ID”. If the War Museum is related to the Department of National Defence or uses these numbers to identify artists, this number would qualify both as an Actor Appellation (the number assigned by the Department of Defence) and as an Actor ID (the same number used by the War Museum).<br><br>The French appellation of the “Power Corporation of Canada” is “Power Corporation du Canada”. An institution wanting to record both these appellations could either create two Actor Appellations (one for Power Corporation of Canada indicated as English in the Actor Appellation Field, and one for Power Corporation du Canada indicated as French in the Actor Appellation Language field) or a single, bilingual one (Power Corporation of Canada/Power Corporation du Canada).<br><br>The same applies to many governmental bodies in Canada such as PCH Canadian Heritage/Patrimoine Canadien where, in addition, the question of the language of the acronym is unclear: if “PCH” is an Actor Appellation with a Actor Appellation Type “Acronym”, it is impossible to assign a single language to the Actor Appellation Language.<br><br>Unknown artists whose cultural affiliation has been determined are often referred to as such (e.g. “Unknown Canadian”)... how unknown artists should be recorded and where should be determined (considering “unknown Canadian” is not an Actor Appellation and the cultural affiliation of the individual can be recorded in the Cultural Affiliation field).<br><br>Whether to classify (artistic, but also others such as companies) collectives (e.g. Gilbert & George, BGL, etc.) as an organisation (using an Actor Appellation) or a group (using a Group Appellation) has not yet been determined. Provided the collective considers itself to be an autonomous artistic entity, it would not suit a Group Appellation considering Group belonging revolves around the multiplicity of entities. The same would apply for trios, etc. (e.g. BGL) as long as the “group” considers itself to be a single autonomous creator. For example, should BGL be recorded under Actor Appellation with the Actor Appellation Types “Acronym” and “Brand Name” (which begs the question: do we allow more than one type on a single Actor Appellation) or under Group Appellation with the members being recorded as Actors with the Actor Appellations “Jasmin Bilodeau”, “Sébastien Giguère”, and “Nicolas Laverdière”?<br><br>Some institutions need to document animals as actors and although the current definition could accommodate this, CIDOC CRM might not? For example, Wojtek was a bear officially enlisted in the Polish army.|
|**Value Origin(s)**|Actors Checklist: Actor Appellation: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|Bilingually named entities (such as the National Gallery of Canada/Musée des beaux-arts du Canada) should be recorded as two appellations (National Gallery of Canada and Musée des beaux-arts du Canada).|
|**Reference(s)**|[(Art & Architecture Thesaurus 2019d)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019d), [(Le Boeuf et al. 2015, sec. E82 Actor Appellation)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Le Boeuf et al. 2015, sec. E41 Appellation)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Free Dictionary 2019a)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019a), [(Free Dictionary 2019f)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019f)|

---

## Actor Appellation Language

|---|---|
|**Scope**|This field indicates the natural or technical language the Actor Appellation is written in. This is a qualifying field so that it necessarily relates to an Actor Appellation and there cannot be an Actor Appellation Language without an Actor Appellation.|
|**Generated Bond(s)**|E56\_Language|
|**Dependency(ies)**|[Actor Appellation](#actor-appellation)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P1\_is\_identified\_by -\> crm:E41\_Appellation + crm:E33\_Linguistic\_Object -\> crm:P72\_has\_language -\> **crm:E56\_Language**</span>|
|**Target Model View(s)**|[Identifiers and Appellations](https://chin-rcip.github.io/collections-model/target-model/current/identification#identifiers-and-appellations)|
|**Semantic Valuation**|*Low*: The value provided is a string that cannot be parsed automatically by reconciliation tools but still contains the required information.<br><br>*Medium*: The value provided is a string that can be automatically cleaned and reconciled using controlled vocabularies specified by CHIN. In the event that the value is adequately structured but does not reconcile with any terms from the controlled vocabulary, and provided that it is deemed relevant, CHIN will add the term to the vocabulary.<br>Accepted Value Type(s): String<br><br>*High*: The provided value is a string that can be automatically reconciled with the controlled vocabularies specified by CHIN.<br>Accepted Value Type(s): String, URI|
|**Typical Case(s)**|Some languages have alphabets that are specific (e.g. Inuktitut) so that determining the Language of the Appellation would not be problematic, for example: “ᕿᓐᓄᐊᔪᐊᖅᐋᓯᕙᒃ” is written in Inuktitut. That said, this does not account for dialects nor for the fact that identifying what alphabet an Actor Appellation is written in might be problematic. This begs the question of whether we should have a field dedicated to character sets/alphabets (e.g. latin, arabic, chinese, etc.).<br><br>Other cases are language-specific versions of a name, such as the Actor Appellation “Léonard de Vinci”, which would have and Actor Appellation Language value of “French”. “Leonardo da Vinci” on the other hand would be harder to classify as it has no intrinsic language, it is simply the name of the Actor (this is demonstrated by the fact that the same Actor Appellation is used both in English and in Italian). The same would apply to groups (e.g. “Aldo” is not specifically French or English, but “Second Cup Café et cie.” is the French equivalent to “Second Cup Coffee Co.”).|
|**Edge Case(s)**|The original appellation of a person is not fundamentally linked to a language (Leonardo da Vinci is “Leonardo da Vinci” both in English and in Italian, although in French he is referred to as “Léonard de Vinci”).<br><br>Any Actor Appellation that is a number would not fit nicely into a Languages Controlled Vocabulary either. For example, “0100101110101101.ORG”, a collective constituted of Eva and Franco Mattes.<br><br>Bilingual considerations apply to many governmental bodies in Canada such as PCH Canadian Heritage/Patrimoine Canadien where, in addition, the question of the language of the acronym is unclear: if “PCH” is an Actor Appellation with a Actor Appellation Type “Acronym”, it is impossible to assign a single language to the Actor Appellation Language. As such, would the Actor Appellation Language accomodate a list of languages as values? The Appellations could also be divided into Actor Appellation Parts with “PCH” having and Actor Appellation Part Type “Affix”, “Canadian Heritage” having and Appellation Part Type “Root” and “Patrimoine canadien” having an Appellation Part Type “Root” as well. This begs the question of the order and manner in which Actor Appellation Parts will be displayed.|
|**Value Origin(s)**|Actors Checklist: Actor Appellation Language: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|Internationally or nationally agreed codes and terminologies (such as ISO 639-3) can be used, and the field accommodates all UTF-8 compliant languages.<br><br>The language of the Actor Appellation can differ from that of the Actor Appellation Language (for example, the Actor Appellation can be “ᐃᓱᒪ”, yet the Actor Appellation Language can be “Inuktitut” rather than “ᐃᓄᒃᑎᑐᑦ”).<br><br>*Regarding the “Expected Value” link - Lexvo does not have any browse or search capability for identifying languages - you can keysmash into Lexvo and it will generate a URI for "hsdjkhsdhf" without verifying whether this is a recognized language or not. In order to find language URIs on Lexvo (as opposed to terms in a language), you need to look up by ISO-639 code. The ISO-639 Code Tables do not allow any browsing, only free searching, and do not cross-reference to geographic region. So the effort involved in verifying whether languages provided on the FNMIIO spreadsheet are recognized as languages with URIs or have ISO codes is far too much at this stage given that 99.9% of museum data is in English or French. This is something I would come back to once I have complete or near-complete datasets for all other fields.*<br><br>*We have decided to expand the definition of the field to accommodate both natural and technical languages because the limitation that only allowing natural languages would not bring about more meaning. Allowing both accounts for potential “artist names” for examples that would be technical (for example, an artist that would use @ID as their name). This is mostly to be more mindful of potential limit cases.*|
|**Reference(s)**|[(Le Boeuf et al. 2015, sec. E56 Language)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Wikipedia 2019ae)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019ae)|

---

## Actor Appellation Part

|---|---|
|**Scope**|One of the units the Actor Appellation is composed of (the latter can have any number of parts). These include manners of address (titles, honorifics) as well as personal and corporate appellation denominatives.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Actor Appellation](#actor-appellation)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P1\_is\_identified\_by -\> crm:E41\_Appellation + crm:E33\_Linguistic\_Object -\> crm:P106\_is\_composed\_of -\> crm:E41\_Appellation + crm:E33\_Linguistic\_Object -\> crm:P190\_has\_symbolic\_content -\> **xsd:string**</span>|
|**Target Model View(s)**|[Identifiers and Appellations](https://chin-rcip.github.io/collections-model/target-model/current/identification#identifiers-and-appellations)|
|**Semantic Valuation**|*Low*: The provided values contain unstructured information of the appellation part, such as it cannot be parsed automatically by reconciliation tools, but still contains the required information.<br><br>*Medium*: The provided values contain structured information that can be automatically cleaned and reconciled with other entities in other datasets.<br>Accepted Value Type(s): String<br><br>*High*: The provided values only contain structured information that can be automatically reconciled with other entities in other datasets.<br>Accepted Value Type(s): String|
|**Typical Case(s)**|*Kitwancool* was painted by Emily Carr in 1928. An institution could decide to enter “Emily Carr” in the Actor Appellation field. It would also be possible to use the Actor Appellation Part fields to create an “Emily” Actor Appellation Part (“First Name” in the Actor Appellation Part Type) and a “Carr” Actor Appellation Part (“Last Name” in the Actor Appellation Part Type).<br><br>“Groupe Hachette” can be recorded as a combination of the Actor Appellation Parts “Groupe” (Actor Appellation Part Type Legal Affix”) and “Hachette” (Actor Appellation Part Type “Brand Name” or “Root”).|
|**Edge Case(s)**|Middle names in general are hard to situate within an Actor Appellation. For example, Jean Paul Riopelle could be considered to be “Jean” (Actor Appellation Part Type “First Name”), “Paul” (Actor Appellation Part Type “Middle Name”) and “Riopelle” (Actor Appellation Part Type “Last Name”) just as it could be “Jean Paul” (Actor Appellation Part Type “First Name”) “Riopelle” (Actor Appellation Part Type “Last Name”). How to determine the order and display of parts will thus be a challenge.<br><br>The same applies to organisations’ appellations that might have multiple parts such as “Randy & Berenicci”, which would be composed of three Actor Appellation Parts (“Randy”, Actor Appellation Part Type “Root”; “&”, Actor Appellation Part Type “Affix”; “Berenicci”, Actor Appellation Part Type “Root”). In this case how to determine the order of the Actor Appellation Parts could not be automatised and would likely be problematic. In addition, whether to classify an artistic duo (or trio etc.) as an organisation (using an Actor Appellation) or a group (using a Group Appellation) has not yet been determined. Provided the duo considers itself to be an autonomous artistic entity, it would not suit a Group Appellation considering Group belonging revolves around the multiplicity of entities.|
|**Value Origin(s)**|Actors Checklist: Actor Appellation Part: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|Legal denominatives (LLC., Ltd., etc.) and honorifics (Her Majesty, Sir, Doctor, etc.) are included here as well as in the Actor Appellation because they could not be accommodated elsewhere unless a new field is created (this has not been done as this data will most likely not be available anyways).|
|**Reference(s)**|[(Wikipedia 2019h)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019h), [(Wikipedia 2019af)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019af)|

---

## Actor Appellation Part Type

|---|---|
|**Scope**|This field qualifies the Part of the Actor Appellation and conceptually characterizes Parts of the Actor Appellation in order to facilitate identification, belonging to larger entities (such as families or brands) and placement in the Appellation.|
|**Generated Bond(s)**|E55\_Type|
|**Dependency(ies)**|[Actor Appellation Part](#actor-appellation-part)|
|**Related SQN(s)**|Appellation Part Type: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P1\_is\_identified\_by -\> crm:E41\_Appellation + crm:E33\_Linguistic\_Object -\> crm:P106\_is\_composed\_of -\> crm:E41\_Appellation + crm:E33\_Linguistic\_Object -\> crm:P2\_has\_type -\> **crm:E55\_Type** (*-\> crm:P2\_has\_type -\> crm:E55\_Type\[" Appellation Part Type"\]*)</span>|
|**Target Model View(s)**|[Identifiers and Appellations](https://chin-rcip.github.io/collections-model/target-model/current/identification#identifiers-and-appellations)|
|**Semantic Valuation**|*Low*: The value provided is a string that cannot be parsed automatically by reconciliation tools but still contains the required information.<br><br>*Medium*: The value provided is a string that can be automatically cleaned and reconciled using controlled vocabularies specified by CHIN. In the event that the value is adequately structured but does not reconcile with any terms from the controlled vocabulary, and provided that it is deemed relevant, CHIN will add the term to the vocabulary.<br>Accepted Value Type(s): String<br><br>*High*: The provided value is a string that can be automatically reconciled with the controlled vocabularies specified by CHIN.<br>Accepted Value Type(s): String, URI|
|**Typical Case(s)**|The record of a painting in a collection by the painter Emily Carr entitled *Kitwancool*made in 1928. “Emily” is the first name actor appellation part type and “Carr” is the last name actor appellation part type.|
|**Edge Case(s)**|Middle names in general are hard to situate within an Actor Appellation. For example, Jean Paul Riopelle could be considered to be “Jean” (Actor Appellation Part Type “First Name”), “Paul” (Actor Appellation Part Type “Middle Name”) and “Riopelle” (Actor Appellation Part Type “Last Name”) just as it could be “Jean Paul” (Actor Appellation Part Type “First Name”) “Riopelle” (Actor Appellation Part Type “Last Name”). How to determine the order and display of parts will thus be a challenge.<br><br>The same applies to organisations’ appellations that might have multiple parts such as “Randy & Berenicci”, which would be composed of three Actor Appellation Parts (“Randy”, Actor Appellation Part Type “Root”; “&”, Actor Appellation Part Type “Affix”; “Berenicci”, Actor Appellation Part Type “Root”). In this case how to determine the order of the Actor Appellation Parts could not be automatised and would likely be problematic. In addition, whether to classify an artistic duo (or trio etc.) as an organisation (using an Actor Appellation) or a group (using a Group Appellation) has not yet been determined. Provided the duo considers itself to be an autonomous artistic entity, it would not suit a Group Appellation considering Group belonging revolves around the multiplicity of entities.<br><br>How to display and order affixes in general will be a challenge as well as some are typically displayed prior to the name (e.g. Sir) whilst others (e.g. Ph.D.) typically come after.|
|**Value Origin(s)**|Actors Checklist: Actor Appellation Part Type: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|Any part of the Actor Appellation can be typified here, including elements that are not typically thought of as names such as manners of address or legal affixes.|
|**Reference(s)**|[(Le Boeuf et al. 2015, sec. E55 Type)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Wikipedia 2019h)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019h), [(Wikipedia 2019af)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019af), [(Wikipedia 2019i)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019i)|

---

## Actor Appellation Precedence

|---|---|
|**Scope**|This field indicates if the institution contributing the data considers the related Actor Appellation to have precedence over other, alternative Actor Appellations.|
|**Generated Bond(s)**|E55\_Type|
|**Dependency(ies)**|[Actor Appellation](#actor-appellation)|
|**Related SQN(s)**|Precedence: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P1\_is\_identified\_by -\> crm:E41\_Appellation + crm:E33\_Linguistic\_Object -\> crm:P2\_has\_type -\> **crm:E55\_Type** (*-\> crm:P2\_has\_type -\> crm:E55\_Type\[“Precedence”\]*)</span>|
|**Target Model View(s)**|[Identifiers and Appellations](https://chin-rcip.github.io/collections-model/target-model/current/identification#identifiers-and-appellations)|
|**Semantic Valuation**|*Low*: The value provided contains a string that cannot be parsed by reconciliation tools. If the Actor Appellation Precedence is recorded using numbers or booleans, the stakeholder must provide an equivalency table aligned with the expected controlled vocabulary.<br><br>*Medium*: The node contains a string that can be semi-automatically reconciled using controlled vocabularies specified by CHIN. If the value is structured but does not reconcile with any terms from the controlled vocabularies, the aggregator will add the term to its vocabulary management environment. If the precedence is recorded using numbers or booleans, the stakeholder must provide an equivalency table aligned with the expected controlled vocabulary.<br>Accepted Value Type(s): String<br><br>*High*: The node contains a string (excluding numbers and booleans) that can be automatically reconciled with the controlled vocabulary specified by CHIN.<br>Accepted Value Type(s): String, URI|
|**Typical Case(s)**|A provider might have several artefacts from a single creator and different Actor Appellations for said creator. For example, the Tate might indicate in its records that *A View from an Apartment* (2004-2005) is by Jeff Wall (Actor Appellation “Jeff Wall”) and *Diagonal Composition* (1993) is by Jeffrey Wall (Actor Appellation “Jeffrey Wall”), thus creating two Actor Appellations for a single artist. In this case, a preferred Actor Appellation should be specified (e.g. “Actor Appellation Precedence” should be indicated as Preferred for “Jeff Wall” so that “Jeffrey Wall” will automatically be non-preferred).|
|**Edge Case(s)**|A provider might have more than two Actor Appellations for a single E39\_Actor and might wish not only to identify its preferred appellation, but to rank them. For example, “Actor Appellation Precendence” indicated as 1 (Preferred) for “Jeff Wall”, as 2 (Non-preferred to 1 but preferred to 3) for “Jeffrey Wall”, and as 3 (Non-preferred) for “J. Wall”. At the moment the model accommodates binary precedence rather than rankings.      This might especially be so for organisational names that are bilingual where no precedence should be determined based on the Language. For example, the “National Gallery of Canada” and “Musée des beaux-arts du Canada” would likely not want to ascribe a precedence to one or the other Appellations. But it might want to ascribe precedence to both of these Appellations over “NGC” or “National Gallery” or “MBAC” or “Musée des beaux-arts”. Only two Appellations (one in English and one in French in this case) is no problem as no precedence will be ascribed. But any more than two Appellations poses the problem of precedence. In addition, this does not indicate how the data should, ultimately, be displayed (e.g. English before French or vice-versa).|
|**Value Origin(s)**|Actors Checklist: Actor Appellation Precedence: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|NULL|
|**Comment(s)**|CHIN will not express or ascribe precedence to one value over another and only the provider of the information can do so.|
|**Reference(s)**|[(Art & Architecture Thesaurus 2019g)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019g), [(Art & Architecture Thesaurus 2019h)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019h), [(Free Dictionary 2019j)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019j)|

---

## Actor Appellation Type

|---|---|
|**Scope**|This field qualifies the Actor Appellation and conceptually characterizes Actor Appellations in order to facilitate identification and belonging to larger entities (such as families or brands).|
|**Generated Bond(s)**|E55\_Type|
|**Dependency(ies)**|[Actor Appellation](#actor-appellation)|
|**Related SQN(s)**|Appellation Type: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P1\_is\_identified\_by -\> crm:E41\_Appellation + crm:E33\_Linguistic\_Object -\> crm:P2\_has\_type -\> **crm:E55\_Type** (*-\> crm:P2\_has\_type -\> crm:E55\_Type\[“Appellation Type”\]*)</span>|
|**Target Model View(s)**|[Identifiers and Appellations](https://chin-rcip.github.io/collections-model/target-model/current/identification#identifiers-and-appellations)|
|**Semantic Valuation**|*Low*: The value provided is a string that cannot be parsed automatically by reconciliation tools but still contains the required information.<br><br>*Medium*: The value provided is a string that can be (semi-)automatically cleaned and reconciled using controlled vocabularies specified by CHIN. In the event that the value is adequately structured but does not reconcile with any terms from the controlled vocabulary, and provided that it is deemed relevant, CHIN will add the term to the vocabulary.<br>Accepted Value Type(s): String<br><br>*High*: The provided value is a string that can be automatically reconciled with the controlled vocabularies specified by CHIN.<br>Accepted Value Type(s): String, URI|
|**Typical Case(s)**|“DAIM” (Actor Appellation Type “Pseudonym”) is the artist name used by Mirko Reisser (Actor Appellation Type “Name”).<br><br>“Tate” (Actor Appellation Type “Corporate Name”) is the name used by the Tate institution which also has other, distinctive Actor Appellations for each of its branches (Actor Appellation “Tate”, Actor Appellation Type “Brand Name”; Actor Appellation “Tate Britain”, Actor Appellation Type “Brand Name”; Actor Appellation “Tate Modern”, Actor Appellation Type “Brand Name”; Actor Appellation “Tate Modern 1”, Actor Appellation Type “Brand Name”; Actor Appellation “Tate Modern 2”, Actor Appellation Type “Brand Name”; Actor Appellation “Tate St Ives”, Actor Appellation Type “Brand Name”; Actor Appellation “Tate Liverpool”, Actor Appellation Type “Brand Name”).|
|**Edge Case(s)**|Translated versions of an Actor Appellation, such as “Léonard de Vinci”, can be considered to be Actor Appellations in their own right with the Actor Appellation Type “Name”, but they could also be considered to be an Actor Appellation Type “Exonym” because this Actor Appellation is only used in the French Language. This begs the question of whether there can be more than one Actor Appellation Type for a single Actor Appellation (e.g. “Exonym” and “Name”) and how the providing institution represents this when contributing its data.|
|**Value Origin(s)**|Actors Checklist: Actor Appellation Type: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|This field qualifies the Actor Appellation and relates to an Actor Appellation so that there cannot be a Type of the Actor Appellation without an Actor Appellation.<br><br>It will be tricky to determine the completion of an appellation (for example, is the birth name of a married woman an Actor Appellation, we would contend that it is) so that the content of this field will heavily rely on what the institution considers to be an Actor Appellation. For example, Anne of Green Gables’ birth name would be Anne Shirley, and she became Anne Blythe by marrying Gilbert Blythe. A museum might enter Anne Shirley as her Actor Appellation, and another might consider Anne Shirley Blythe as her Actor Appellation, with Anne being the first name, Shirley being the maiden name, and Blythe being the married name. Once again, the institution’s authority will be respected here.<br><br>For marginalized communities where individuals have often been ascribed names that they do not consider their own it would be useful to link a E39\_Actor to the F52\_Name\_Use\_Activity. Some could be accounted for here (such as when the Actor Appellation is a “Slave name” for example), but there is no way to account for the “correct” name, nor to give precedence to the person’s preferred name (because CHIN is non-authoritative). For example, “Malcolm Little” could be typified as a slave name, and “Malcolm X” as a given name.|
|**Reference(s)**|[(Le Boeuf et al. 2015, sec. E55 Type)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Wikipedia 2019ad)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019ad), [(Wikipedia 2019h)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019h)|

---

## Actor Appellation Use Date Begin

|---|---|
|**Scope**|This field designates the earliest temporal instant of the use of the Actor Appellation|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Actor Appellation](#actor-appellation)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P1\_is\_identified\_by -\> crm:E41\_Appellation + crm:E33\_Linguistic\_Object -\> frbr:R64i\_was\_name\_used\_by -\> frbr:F52\_Name\_Use\_Activity -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82a\_begin\_of\_the\_begin -\> **xsd:dateTime**</span>|
|**Target Model View(s)**|[Identifiers and Appellations](https://chin-rcip.github.io/collections-model/target-model/current/identification#identifiers-and-appellations)|
|**Semantic Valuation**|*Low*: The value provided temporalizes the beginning of the event, but this information cannot be automatically extracted and formatted.<br><br>*Medium*: The date can be automatically extracted from the value provided (and from textual content that surrounds it if applicable) and can be formatted using the YYYY-MM-DD convention.<br>Accepted Value Type(s): String<br><br>*High*: The date is the sole value provided and is formatted using the date convention.<br>Accepted Value Type(s): DateTime (YYYY-MM-DDThh:mm:ss)|
|**Typical Case(s)**|Charles Lutwidge Dodgson published under the pen name “Lewis Carroll” for the first time in March 1856 when his poem *Solitude* appeared in *The Train*. The Actor Appellation Use Date Begin, in this case, would be “1856-03”.|
|**Edge Case(s)**|When it comes to Actor Appellations that are mostly attributable to relationships (such as nicknames for example), the Actor Appellation Use Date Begin will rely on when the Related Actor started using the Actor Appellation. Would the information recorded be from the earliest use by anyone to the latest use by anyone (e.g. the first person who used “W to refer to George W. Bush, and the last person that did/will do so) or from the earliest use by a specific actor and the latest use by a specific actor (e.g. the first time John Dickerson used “W” and the last time he uses it)?<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Actor Appellation Use Date Begin: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|Actor Appellation Use Date Begin is not following the CIDOC CRM rule which states that an event is something pontual which transforms something in reality. In the case of an appellation use, the date begin represents the beginning of the period where this name is used to identify the actor.|
|**Comment(s)**|Whenever possible, this node should be used in conjunction with Actor Appellation Use Date End to indicate the interval of the described event.|
|**Reference(s)**|[(Art & Architecture Thesaurus 2020e)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2020e), [(Bekiari et al. 2015, sec. F52 Name Use Activity)](/collections-model/semantic-paths-specification/current/bibliography#bekiari-et-al-2015), [(Free Dictionary 2020c)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2020c), [(Free Dictionary 2020d)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2020d)|

---

## Actor Appellation Use Date Begin Qualifier

|---|---|
|**Scope**|This field qualifies the earliest temporal instant of the use of the Actor Appellation.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Actor Appellation](#actor-appellation)<br><br>[Actor Appellation Use Date Begin](#actor-appellation-use-date-begin)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P1\_is\_identified\_by -\> crm:E41\_Appellation + crm:E33\_Linguistic\_Object -\> frbr:R64i\_was\_name\_used\_by -\> frbr:F52\_Name\_Use\_Activity -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P79\_beginning\_is\_qualified\_by -\> **xsd:string**</span>|
|**Target Model View(s)**|[Identifiers and Appellations](https://chin-rcip.github.io/collections-model/target-model/current/identification#identifiers-and-appellations)|
|**Semantic Valuation**|*Low*: The value provided qualifies the date of the event, but this information is unstructured and cannot be automatically formatted.<br><br>*Medium*: The value provided qualifies the date of the event and can be (semi-)automatically cleaned and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String<br><br>*High*: The qualifier is the sole value provided and is structured and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String|
|**Typical Case(s)**|Charles Lutwidge Dodgson published under the pen name “Lewis Carroll” for the first time in March 1856 when his poem *Solitude*appeared in *The Train*. The Actor Appellation Use Date Begin, in this case, would be “1856-03” and could include “BCE” as an Actor Appellation Use Date Begin Qualifier.|
|**Edge Case(s)**|There might be cases where the Actor Appellation Use Date Begin and the Actor Appellation Use Date Begin Qualifier would be the same, in particular when it comes to eras. For example, “Victorian Era” can be both the Actor Appellation Use Date Begin and the Actor Appellation Use Date Begin Qualifier. Determining what eras the qualifiers will entail (through the vocabulary used to handle them) will thus be paramount.<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Actor Appellation Use Date Begin Qualifier: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|There can be more than one qualifier at once for a single Death/Dissolution Date Begin (e.g. “BCE” and “BC”, which is the same information, the former being qualified using the non-christian acronym for “Before Common Era” and the latter using the christian “Before Christ”).|
|**Reference(s)**|[(Art & Architecture Thesaurus 2020e)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2020e), [(Bekiari et al. 2015, sec. F52 Name Use Activity)](/collections-model/semantic-paths-specification/current/bibliography#bekiari-et-al-2015), [(Free Dictionary 2020c)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2020c), [(Free Dictionary 2020d)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2020d)|

---

## Actor Appellation Use Date End

|---|---|
|**Scope**|This field designates the latest temporal instant of the use of the Actor Appellation.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Actor Appellation](#actor-appellation)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P1\_is\_identified\_by -\> crm:E41\_Appellation + crm:E33\_Linguistic\_Object -\> frbr:R64i\_was\_name\_used\_by -\> frbr:F52\_Name\_Use\_Activity -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82b\_end\_of\_the\_end -\> **xsd:dateTime**</span>|
|**Target Model View(s)**|[Identifiers and Appellations](https://chin-rcip.github.io/collections-model/target-model/current/identification#identifiers-and-appellations)|
|**Semantic Valuation**|*Low*: The value provided contains the date information but inconsistencies in the dataset prevent its automatic extraction or formatting by the aggregator.<br><br>*Medium*: The date can be extracted from the value provided (and from the textual content that surrounds it if applicable) and formatted using the YYYY-MM-DD convention.<br>Accepted Value Type(s): String<br><br>*High*: The date is the sole value provided and is formatted using the date convention.<br>Accepted Value Type(s): DateTime (YYYY-MM-DDThh:mm:ss)|
|**Typical Case(s)**|Charles Lutwidge Dodgson published under the pen name “Lewis Carroll” for the last time in February 1898 when his book *Three Sunsets and Other Poems* was published. The Actor Appellation Use Date End, in this case, would be “1898-02”.|
|**Edge Case(s)**|SAMO is a graffiti tag that was used in New York from 1977-1980, primarily by Jean-Michel Basquiat and Al Diaz. It could be considered an Actor Appellation (Actor Appellation Type “Pseudonym”), a Group Appellation (Group Type “Team”) and the dates would not be problematic (1980 as a Actor Appellation Use Date End), but it could also be considered to be Objects (as SAMO was graffitied across the City) and thus can be used by multiple Actors. This begs the question of can an Appellation Use Date have an end as people continue to use the Appellation well after the Actor’s death? There could be, in this case, an Object Appellation and an Actor Appellation of the same name, but how to handle the dates for each would have to be clarified.|
|**Value Origin(s)**|Actors Checklist: Actor Appellation Use Date End: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|Actor Appellation Use Date End is not following the CIDOC CRM rule which states that an event is a pontual CRM entity which transforms something in reality. In the case of an appellation use, the date end represents the end of the period where this name is used to identify the actor.|
|**Comment(s)**|Whenever possible, this node should be used in conjunction with Actor Appellation Use Date Begin to create the interval of the described event.<br><br>The Actor Appellation Date End temporalises an E5\_Event X regardless of the temporality of the other E5\_Event it is related to such that, for example, even though, Dodgson died (1898-01-14) prior to the publication of his last book (1898-02), the Actor Appellation Use Date End can exceed the Actor’s Death Date End.|
|**Reference(s)**|[(Art & Architecture Thesaurus 2020e)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2020e), [(Bekiari et al. 2015, sec. F52 Name Use Activity)](/collections-model/semantic-paths-specification/current/bibliography#bekiari-et-al-2015), [(Free Dictionary 2020c)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2020c), [(Free Dictionary 2020d)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2020d)|

---

## Actor Appellation Use Date End Qualifier

|---|---|
|**Scope**|This field qualifies the latest temporal instant of the use of the appellation.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Actor Appellation](#actor-appellation)<br><br>[Actor Appellation Use Date End](#actor-appellation-use-date-end-qualifier)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P1\_is\_identified\_by -\> crm:E41\_Appellation + crm:E33\_Linguistic\_Object -\> frbr:R64i\_was\_name\_used\_by -\> frbr:F52\_Name\_Use\_Activity -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P80\_end\_is\_qualified\_by -\> **xsd:string**</span>|
|**Target Model View(s)**|[Identifiers and Appellations](https://chin-rcip.github.io/collections-model/target-model/current/identification#identifiers-and-appellations)|
|**Semantic Valuation**|*Low*: The value provided qualifies the date of the event, but this information is unstructured and cannot be automatically formatted.<br><br>*Medium*: The value provided qualifies the date of the event and can be (semi-)automatically cleaned and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String<br><br>*High*: The qualifier is the sole value provided and is structured and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String|
|**Typical Case(s)**|Charles Lutwidge Dodgson published under the pen name “Lewis Carroll” for the last time in February 1898 when his book *Three Sunsets and Other Poems* was published. The Actor Appellation Use Date End, in this case, would be “1898-02” and a Actor Appellation Use Date End Qualifier could be “BCE”.|
|**Edge Case(s)**|There might be cases where the Actor Appellation Use Date Begin and the Actor Appellation Use Date Begin Qualifier would be the same, in particular when it comes to eras. For example, “Victorian Era” can be both the Actor Appellation Use Date Begin and the Actor Appellation Use Date Begin Qualifier. Determining what eras the qualifiers will entail (through the vocabulary used to handle them) will thus be paramount.<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Actor Appellation Use Date End Qualifier: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|There can be more than one qualifier at once for a single Actor Appellation Use Date End (e.g. “BCE” and “BC”, which is the same information, the former being qualified using the non-christian acronym for “Before Common Era” and the latter using the christian “Before Christ”).|
|**Reference(s)**|[(Art & Architecture Thesaurus 2020e)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2020e), [(Bekiari et al. 2015, sec. F52 Name Use Activity)](/collections-model/semantic-paths-specification/current/bibliography#bekiari-et-al-2015), [(Free Dictionary 2020c)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2020c), [(Free Dictionary 2020d)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2020d)|

---

## Actor Appellation Use Context

|---|---|
|**Scope**|This field designates the circumstances in which an appellation is employed either by an Actor to refer to themselves or by those around them to refer to them.|
|**Generated Bond(s)**|E55\_Type|
|**Dependency(ies)**|[Actor Appellation](#actor-appellation)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P1\_is\_identified\_by -\> crm:E41\_Appellation + crm:E33\_Linguistic\_Object -\> frbr:R64i\_was\_name\_used\_by -\> frbr:F52\_Name\_Use\_Activity -\> frbr:R61\_occured\_in\_kind\_of\_context -\> **crm:E55\_Type**</span>|
|**Target Model View(s)**|[Identifiers and Appellations](https://chin-rcip.github.io/collections-model/target-model/current/identification#identifiers-and-appellations)|
|**Semantic Valuation**|*Low*: The value provided is a string that cannot be parsed automatically by reconciliation tools but still contains the required information.<br><br>*Medium*: The value provided is a string that can be automatically cleaned and reconciled using controlled vocabularies specified by CHIN. In the event that the value is adequately structured but does not reconcile with any terms from the controlled vocabulary, and provided that it is deemed relevant, CHIN will add the term to the proper vocabulary.<br>Accepted Value Type(s): String<br><br>*High*: The provided value is a string that can be automatically reconciled with the controlled vocabularies specified by CHIN.<br>Accepted Value Type(s): String, URI|
|**Typical Case(s)**|Charles Lutwidge Dodgson wrote Alice's Adventures in Wonderland under his pen name “Lewis Carroll” while continuing to publish work as a mathematician under his birth name. He would thus have two Actor Appellations (“Charles Lutwidge Dodgson”, Actor Appellation Type “Birth Name”, Actor Appellation Use Context “Customary Name”; “Lewis Carroll”, Actor Appellation Type “Pen Name”, Actor Appellation Use Context “Children’s Book Writing”).|
|**Edge Case(s)**|N/A|
|**Value Origin(s)**|Actors Checklist: Actor Appellation Use Context: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|As the accepted vocabularies for this node will be reused in other nodes, the Actor Appellation Use Context might not be recorded in this field.|
|**Comment(s)**|*For this reason, this field might be deprecated upon future revision and any information it would hold will be recorded using either a curatorial note or an annotation. In the case of an annotation (if it is relevant), it is debatable whether it should be applied to the Appellation or to the Actor themself.*|
|**Reference(s)**|[(Art & Architecture Thesaurus 2020e)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2020e), [(Bekiari et al. 2015, sec. F52 Name Use Activity)](/collections-model/semantic-paths-specification/current/bibliography#bekiari-et-al-2015), [(Free Dictionary 2020c)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2020c), [(Free Dictionary 2020d)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2020d)|

---

## Actor ID

|---|---|
|**Scope**|This node designates the unique identifying combination of alphanumeric characters assigned to the actor by an institutionally recognised organisation.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|E39\_Actor|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P1\_is\_identified\_by -\> crm:E42\_Identifier -\> crm:P190\_has\_symbolic\_content -\> **xsd:string**</span>|
|**Target Model View(s)**|[Identifiers and Appellations](https://chin-rcip.github.io/collections-model/target-model/current/identification#identifiers-and-appellations)|
|**Semantic Valuation**|*Low*: The provided values contain IDs surrounded by other unstructured information such that there is no systematic way to isolate and automatically extract the IDs, whether because of varying ID structures or inconsistent syntax.<br><br>*Medium*: The provided values contain IDs surrounded by other information, but the ID can be systematically isolated and automatically extracted.<br>Accepted Value Type(s): String, Integer<br><br>*High*: The provided values only contain strings that represent the IDs and are unique within the dataset.<br>Accepted Value Type(s): String, Integer|
|**Typical Case(s)**|Power Corporation of Canada, headquartered in Montréal, has an important private collection of artworks. Its International Securities Identification Number is “CA7392391016” (Actor ID with an “ISIN” Actor ID Type) and it is traded as “TSX: POW”, which could have its dedicated Actor Appellations as well (Actor Appellation Type “Stock Symbol”).|
|**Edge Case(s)**|An IP Address might be considered to be an ID that refers to the Actor but does not represent it. Would Actor ID Type accommodate the IP Address considering multiple actors can use a single computer? Especially if it is a duo using the computer to semi-automatically create an object so that the computer takes part in the creation? In the case of media-generated art, would the IP Address be part of the Object IDs, the Actor IDs, or both?|
|**Value Origin(s)**|Actors Checklist: Actor ID: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|Uniqueness of the Actor ID to the E39\_Actor within the dataset is essential; if an Actor ID is assigned to several entities, either these will be subsumed under a single one mistakenly or a “Value already assigned” error will emerge.|
|**Comment(s)**|This entry node should be used precisely to identify the Actor, it should not be mistaken for the Object ID node.|
|**Reference(s)**|[(Art & Architecture Thesaurus 2019c)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019c), [(Art & Architecture Thesaurus 2019k)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019k), [(Bekiari et al. 2015, sec. F13 Identifier)](/collections-model/semantic-paths-specification/current/bibliography#bekiari-et-al-2015), [(Wikipedia 2019d)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019d), [(Wikipedia 2019ac)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019ac)|

---

## Actor ID Type

|---|---|
|**Scope**|This field specifies what classification the organization who issued the Actor ID ascribed to said ID.|
|**Generated Bond(s)**|E55\_Type|
|**Dependency(ies)**|[Actor ID](#actor-id)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P1\_is\_identified\_by -\> crm:E42\_Identifier -\> crm:P2\_has\_type -\> **crm:E55\_Type**</span>|
|**Target Model View(s)**|[Identifiers and Appellations](https://chin-rcip.github.io/collections-model/target-model/current/identification#identifiers-and-appellations)|
|**Semantic Valuation**|*Low*: The value provided is a string that cannot be parsed automatically by reconciliation tools but still contains the required information.<br><br>*Medium*: The value provided is a string that can be automatically cleaned and reconciled using controlled vocabularies specified by CHIN. In the event that the value is adequately structured but does not reconcile with any terms from the controlled vocabulary, and provided that it is deemed relevant, CHIN will add the term to the vocabulary.<br>Accepted Value Type(s): String<br><br>*High*: The provided value is a string that can be automatically reconciled with the controlled vocabularies specified by CHIN.<br>Accepted Value Type(s): String, URI|
|**Typical Case(s)**|Power Corporation of Canada, headquartered in Montréal, has an important private collection of artworks. Its International Securities Identification Number is “CA7392391016” (Actor ID with an “ISIN” Actor ID Type) and it is traded as “TSX: POW”, which could have its dedicated Actor Appellations as well (Actor Appellation Type “Stock Symbol”).|
|**Edge Case(s)**|An IP Address might be considered to be an ID that refers to the Actor but does not represent it. Would Actor ID Type accommodate the IP Address considering multiple actors can use a single computer? Especially if it is a duo using the computer to semi-automatically create an object so that the computer takes part in the creation? In the case of media-generated art, would the IP Address be part of the Object IDs, the Actor IDs, or both in such a case?|
|**Value Origin(s)**|Actors Checklist: Actor ID Type: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|The Target Model will account for the terms provided as values, but not for their definition or for the understanding the provider might have of them. As such, terms, rather than meaning, will be matched to controlled vocabularies so that the hierarchies of these vocabularies might not reflect the initial understanding of the provider as to the context of the term. This is one of the reasons why the use of recognized controlled vocabularies is of paramount importance.|
|**Comment(s)**|In most cases, this information will not be a value in the stakeholder’s dataset, in order to get this information the provider or the aggregator will probably have to reuse the proper field label.|
|**Reference(s)**|[(Le Boeuf et al. 2015, sec. E55 Type)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015)|


---

## Archival Document Call Number

|---|---|
|**Scope**|This field designates the identifying combination of alphanumeric characters, symbols, press-marks, or shelf-marks assigned to an archival document by its archiving institution in order to express its subject contents and/or shelving/storing location.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|E39\_Actor|
|**Related SQN(s)**|Archival Object: Definition<br><br>Call Number: Definition<br><br>Record: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P70i\_is\_documented\_in -\> crm:E31\_Document (*-\> crm:P2\_has\_type -\> crm:E55\_Type\["Record"\]*) -\> crm:P128i\_is\_carried\_by -\> crm:E22\_Human-Made\_Object (*-\> crm:P2\_has\_type -\> crm:E55\_Type\["Archival Object"\]*) -\> crm:P1\_is\_identified\_by -\> crm:E42\_Identifier (*-\> crm:P2\_has\_type -\> crm:E55\_Type\["Call Number"\]*) -\> crm:P190\_has\_symbolic\_content -\> **xsd:string**</span>|
|**Target Model View(s)**|[Archival Document Location](https://chin-rcip.github.io/collections-model/target-model/current/archival-document-location)|
|**Semantic Valuation**|*Low*: The provided values contain Call Numbers surrounded by other unstructured information such that there is no systematic way to isolate and automatically extract the Call Numbers, whether because of varying Call Number structures or inconsistent syntax.<br><br>*Medium*: The provided values contain Call Numbers surrounded by other information, but the Call Number can be systematically isolated and automatically extracted.<br>Accepted Value Type(s): String, Integer<br><br>*High*: The provided values only contain strings that represent the Call Numbers and are unique within the dataset.<br>Accepted Value Type(s): String, Integer|
|**Typical Case(s)**|*Who Do You Think You Are?* by Alice Munro is held at Library and Archives Canada (Archival Document Institution Appellation) under the call number “PS8576 U57 W46 1979” (Archival Document Call Number).|
|**Edge Case(s)**|It is unclear what “archival document” refers to: does it comprise historically significant objects, might an object be both an Archival Document and an Artefact? Would the United States Constitution, housed in the United States National Archives, be considered an Archival Document or an Artefact as it could be documented in both fields? If it is considered to be both how should it be documented?<br><br>The Archival Document Call Number records refers to the document’s identifier which in turn determines its location within an institution. However, an Archival Institution might have multiple physical addresses or branches. The building where the archival document is held currently has no assigned documentation field so that it could be documented under the Archival Document Call Number (e.g. “PS8576 U57 W46 1979 - Wellington General Collection”) or under Archival Document Place (e.g. “395 Wellington St, Ottawa, ON K1A 0N4 - Wellington General Collection”), or even in the Archival Document Institution Appellation (e.g. “Library and Archives Canada - Wellington General”).|
|**Value Origin(s)**|Actors Checklist: Archival Document Call Number: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|There is a debate on whether to name this field Archival Support or Archival Document.|
|**Reference(s)**|[(Art & Architecture Thesaurus 2019a)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019a), [(Free Dictionary 2019c)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019c)|

---

## Archival Document Institution Appellation

|---|---|
|**Scope**|This field designates the entire identifying word(s), number(s), symbol(s) or code(s) customarily used to refer to the establishment custodian of the physical support (e.g. file or object) in which the information is contained.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|E39\_Actor|
|**Related SQN(s)**|Archival Object: Definition<br><br>Record: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P70i\_is\_documented\_in -\> crm:E31\_Document (*-\> crm:P2\_has\_type -\> crm:E55\_Type\["Record"\]*) -\> crm:P128i\_is\_carried\_by -\> crm:E22\_Human-Made\_Object (*-\> crm:P2\_has\_type -\> crm:E55\_Type\["Archival Object"\]*) -\> crm:P49\_has\_current\_or\_former\_keeper -\> crm:E74\_Group -\> crm:P1\_is\_identified\_by -\> crm:E41\_Appellation + crm:E33\_Linguistic\_Object -\> crm:P190\_has\_symbolic\_content -\> **xsd:string**</span>|
|**Target Model View(s)**|[Archival Document Location](https://chin-rcip.github.io/collections-model/target-model/current/archival-document-location)|
|**Semantic Valuation**|*Low*: The provided values contain unstructured information of the appellation, such as it cannot be parsed automatically by reconciliation tools, but still contains the required information.<br><br>*Medium*: The provided values contain structured information that can be automatically cleaned and reconciled with other entities in other datasets.<br>Accepted Value Type(s): String<br><br>*High*: The provided values only contain structured information that can be automatically reconciled with other entities in other datasets.<br>Accepted Value Type(s): String|
|**Typical Case(s)**|*Who Do You Think You Are?*by Alice Munro is held at Library and Archives Canada (Archival Document Institution Appellation) under the call number “PS8576 U57 W46 1979” (Archival Document Call Number).|
|**Edge Case(s)**|The Archival Document Call Number records refers to the document’s identifier which in turn determines its location within an institution. However, an Archival Institution might have multiple physical addresses or branches. The building where the archival document is held currently has no assigned documentation field so that it could be documented under the Archival Document Call Number (e.g. “PS8576 U57 W46 1979 - Wellington General Collection”) or under Archival Document Place (e.g. “395 Wellington St, Ottawa, ON K1A 0N4 - Wellington General Collection”), or even in the Archival Document Institution Appellation (e.g. “Library and Archives Canada - Wellington General”).|
|**Value Origin(s)**|Actors Checklist: Archival Document Institution Appellation: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|This list is not limited to the Record Contributor Appellation List (i.e. a contributor could document archival documents that are not in their own collections, such as Artists in Canada documenting Artexte).<br><br>There is a debate on whether to name this field Archival Support or Archival Document.<br><br>This field is not yet modeled in the Target Model 2.0, but will be in a subsequent version.|
|**Reference(s)**|[(Art & Architecture Thesaurus 2019b)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019b), [(Art & Architecture Thesaurus 2019d)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019d), [(Le Boeuf et al. 2015, sec. E22 Man-Made Object)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Le Boeuf et al. 2015, sec. E31 Document)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Le Boeuf et al. 2015, sec. E73 Information Object)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Free Dictionary 2019a)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019a), [(Free Dictionary 2019e)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019e)|

---

## Archival Document Place

|---|---|
|**Scope**|This field designates the physical location of the physical support (e.g. file or object) in which the information is contained.|
|**Generated Bond(s)**|E53\_Place|
|**Dependency(ies)**|E39\_Actor|
|**Related SQN(s)**|Archival Object: Definition<br><br>Record: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P70i\_is\_documented\_in -\> crm:E31\_Document (*-\> crm:P2\_has\_type -\> crm:E55\_Type\["Record"\]*) -\> crm:P128i\_is\_carried\_by -\> crm:E22\_Human-Made\_Object (*-\> crm:P2\_has\_type -\> crm:E55\_Type\["Archival Object"\]*) -\> crm:P54\_has\_current\_permanent\_location -\> **crm:E53\_Place**</span>|
|**Target Model View(s)**|[Archival Document Location](https://chin-rcip.github.io/collections-model/target-model/current/archival-document-location)|
|**Semantic Valuation**|*Low*: The value provided is a string that cannot be parsed automatically by reconciliation tools but still contains the required information.<br><br>*Medium*: The value provided is a string that can be automatically cleaned and reconciled using controlled vocabularies specified by CHIN. In the event that the value is adequately structured but does not reconcile with any terms from the controlled vocabulary, and provided that it is deemed relevant, CHIN will add the term to the vocabulary.<br>Accepted Value Type(s): String<br><br>*High*: The provided value is a string that can be automatically reconciled with the controlled vocabularies specified by CHIN.<br>Accepted Value Type(s): String, URI|
|**Typical Case(s)**|*Who Do You Think You Are?*by Alice Munro is held at Library and Archives Canada (Archival Document Institution Appellation), located at “395 Wellington St, Ottawa, ON K1A 0N4 - Wellington General Collection” (Archival Document Place) under the call number “PS8576 U57 W46 1979” (Archival Document Call Number).|
|**Edge Case(s)**|The Archival Document Call Number records refers to the document’s identifier which in turn determines its location within an institution. However, an Archival Institution might have multiple physical addresses or branches. The building where the archival document is held currently has no assigned documentation field so that it could be documented under the Archival Document Call Number (e.g. “PS8576 U57 W46 1979 - Wellington General Collection”) or under Archival Document Place (e.g. “395 Wellington St, Ottawa, ON K1A 0N4 - Wellington General Collection”), or even in the Archival Document Institution Appellation (e.g. “Library and Archives Canada - Wellington General”).|
|**Value Origin(s)**|Actors Checklist: Archival Document Place: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|There is a debate on whether to name this field Archival Support or Archival Document.|
|**Reference(s)**|[(Art & Architecture Thesaurus 2019b)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019b), [(Le Boeuf et al. 2015, sec. E22 Man-Made Object)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Le Boeuf et al. 2015, sec. E31 Document)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Le Boeuf et al. 2015, sec. E73 Information Object)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Le Boeuf et al. 2015, sec. E53 Place)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Bekiari et al. 2015, sec. F9 Place)](/collections-model/semantic-paths-specification/current/bibliography#bekiari-et-al-2015), [(Free Dictionary 2019e)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019e), [(Free Dictionary 2019n)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019n)|

---

## Annotation

|---|---|
|**Scope**|This field records supplemental information associated with a particular piece of data about which it offers further knowledge, such as a comment, remark, description, explanation, note, grade or evaluation, etc.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|E39\_Actor<br><br>E22\_Human-Made\_Object<br><br>Any other field the annotation pertains to|
|**Full Path**|<span class="full-path">\<any CRM entity\> -\> crm:P3\_has\_note -\> **xsd:string**</span>|
|**Target Model View(s)**|[Annotations and Comments](https://chin-rcip.github.io/collections-model/target-model/current/general-concepts#annotations-and-comments)|
|**Semantic Valuation**|*Low*: The value is a string that contains the information needed, but also other and different information that cannot be automatically extracted.<br><br>*Medium*: The value is a string that contains the information needed, but also other and different information that can be automatically extracted.<br>Accepted Value Type(s): String<br><br>*High*: The value is a string that contains only the information needed.<br>Accepted Value Type(s): String|
|**Typical Case(s)**|A manufacturer named “Woodwork Construction Ltd.” (Actor Appellation) is named after the owner’s previous company (Annotation placed on the Actor Appellation: “Name based on the owner’s previous company”).<br><br>When the Art Gallery of Nova Scotia exhibited a December 14th, 1878 print originally titled *Negroes Bringing in Evergreens for the Arches*, the Associate Curator of Historical Prints Diane O’Neill decided to label the work as *Bringing in Evergreens for the Arches*. In this case “Originally titled *Negroes Bringing in Evergreens for the Arches*, labelled *Bringing in Evergreens for the Arches*under Associate Curator of Historical Prints Diane O’Neill” could be an Annotation placed on the Object Appellations (“Bringing in Evergreens for the Arches” and “Negroes Bringing in Evergreens for the Arches”).|
|**Edge Case(s)**|Marie-Guillemine Benoist’s *Portrait of Madeleine*was formerly titled *Portrait of a Negress*. Only recent scholarship has established the sitter’s name as “Madeleine”, although her last name remains unknown. An Annotation could be placed on its Object Appellations (“Portrait of Madeleine”, Prefered Appellation, “Formerly titled *Portrait of a Negress*” Annotation; “Portrait of a Negress”, Non-Prefered Appellation, “Now titled Portrait of Madeleine” Annotation; “Portrait d’une femme noire”, Non-Prefered Appellation, “Formerly titled *Portrait d’une négresse*” Annotation), but a Curatorial Note Content might also be used on the Actor Appellation “Madeleine” (“Sitter in *Portrait of Madeleine,* formerly titled *Portrait of a Negress*, identified as being named “Madeleine” by Viktoria Schmidt-Linsenhoff).|
|**Value Origin(s)**|Actors Checklist: Annotation: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|This field is meant for information that is supplemental to a specific piece of data. As such, it is not intended to be used as a container for curatorial information pertaining to an actor or object. For the later, Curatorial Note Content should be used.|
|**Reference(s)**|[(Art & Architecture Thesaurus 2020a)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2020a), [(Art & Architecture Thesaurus 2020b)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2020b), [(Art & Architecture Thesaurus 2020c)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2020c), [(Art & Architecture Thesaurus 2020d)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2020d), [(Le Boeuf et al. 2015, sec. P3 Has Note)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Free Dictionary 2020a)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2020a), [(Free Dictionary 2020b)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2020b), [(Prata 2016)](/collections-model/semantic-paths-specification/current/bibliography#prata-rosie-2016), [(Schmidt-Linsenhoff 2013)](/collections-model/semantic-paths-specification/current/bibliography#schmidt-linsenhoff-viktoria-2013), [(Waller 2018)](/collections-model/semantic-paths-specification/current/bibliography#waller-susan-2018), [(Wikipedia 2019as)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019as), [(Wikipedia 2019av)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019av), [(Wikipedia 2019aw)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019aw), [(Wikipedia 2019ax)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019ax)|

---

## Biography Content

|---|---|
|**Scope**|This field accommodates accounts of the main Actor’s life that are written, composed, or produced by either themselves or others.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|E39\_Actor|
|**Related SQN(s)**|Biography: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P67i\_is\_referred\_to\_by -\> crm:E33\_Linguistic\_Object (*-\> crm:P2\_has\_type -\> crm:E55\_Type\["Biography"\]*) -\> crm:P190\_has\_symbolic\_content -\> **xsd:string**</span>|
|**Target Model View(s)**|[Biography](https://chin-rcip.github.io/collections-model/target-model/current/descriptive-information#biography)|
|**Semantic Valuation**|*Low*: The value is a string that contains the information needed, but also other and different information that cannot be automatically extracted.<br><br>*Medium*: The value is a string that contains the information needed, but also other and different information that can be automatically extracted.<br>Accepted Value Type(s): String<br><br>*High*: The value is a string that contains only the information needed.<br>Accepted Value Type(s): String|
|**Typical Case(s)**|Wangechi Mutu’s Wikipedia entry goes as follows: “Wangechi Mutu (Kenyan-American, born 1972) is a prominent international contemporary visual artist known primarily for her painting, sculpture, film and performance work. Born in Kenya, she has lived and established her career in New York for over twenty years. Mutu's work has directed the female body as subject through collage painting, immersive installation, and live and video performance all the while exploring questions of self-image, gender constructs, cultural trauma and environmental destruction”.|
|**Edge Case(s)**|A Group’s Biography could be categorized either as a Curatorial Note Content or as a Biography Content. For example, Snarkitecture’s Wikipedia entry goes as follows: “Snarkitecture is a New York-based collaborative practice founded by Daniel Arsham and Alex Mustonen. Snarkitecture's work is focused on designing within existing spaces or collaboration with other artists and designers. They aim to reuse or misuse existing architecture to make architecture perform the unexpected. Arsham and Mustonen met while studying at the Cooper Union in New York City and established Snarkitecture as a formal practice in 2008”.<br><br>Relying on textual biographies will likely be a problem when it comes to the documentation of actors coming from cultures oriented towards orality of intangible heritage.|
|**Value Origin(s)**|Actors Checklist: Biography Content: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|TBD|
|**Reference(s)**|[(Art & Architecture Thesaurus 2019s)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019s), [(Free Dictionary 2019u)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019u), [(Wikipedia 2019x)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019x), [(Wikipedia 2019ao)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019ao), [(Wikipedia 2020a)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2020a)|

---

## Biography Language

|---|---|
|**Scope**|This field indicates the natural language the Biography Content is written, composed or produced in.|
|**Generated Bond(s)**|E56\_Language|
|**Dependency(ies)**|[Biography Content](#biography-content)|
|**Related SQN(s)**|Biography: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P67i\_is\_referred\_to\_by -\> crm:E33\_Linguistic\_Object (*-\> crm:P2\_has\_type -\> crm:E55\_Type\["Biography"\]*) -\> crm:P72\_has\_language -\> **crm:E56\_Language**</span>|
|**Target Model View(s)**|[Biography](https://chin-rcip.github.io/collections-model/target-model/current/descriptive-information#biography)|
|**Semantic Valuation**|*Low*: The value provided is a string that cannot be parsed automatically by reconciliation tools but still contains the required information.<br><br>*Medium*: The value provided is a string that can be automatically cleaned and reconciled using controlled vocabularies specified by CHIN. In the event that the value is adequately structured but does not reconcile with any terms from the controlled vocabulary, and provided that it is deemed relevant, CHIN will add the term to the vocabulary.<br>Accepted Value Type(s): String<br><br>*High*: The provided value is a string that can be automatically reconciled with the controlled vocabularies specified by CHIN.<br>Accepted Value Type(s): String, URI|
|**Typical Case(s)**|Wangechi Mutu’s Biography Content goes as follows: “Wangechi Mutu (Kenyan-American, born 1972) is a prominent international contemporary visual artist known primarily for her painting, sculpture, film and performance work” (Biography Language “English”).|
|**Edge Case(s)**|Some languages have alphabets that are specific (e.g. Inuktitut) so that determining the Language of the Appellation would not be problematic, for example: “ᕿᓐᓄᐊᔪᐊᖅᐋᓯᕙᒃ” is written in Inuktitut. That said, this does not account for dialects nor for the fact that identifying what alphabet an Actor Appellation is written in might be problematic. This begs the question of whether we should have a field dedicated to character sets/alphabets (e.g. latin, arabic, chinese, etc.).<br><br>Bilingual considerations could apply to Biographies as well so that it would either be impossible to assign a single Biography Language to the Biography Content, or the field would have to accomodate a list of values. For example, Harri Aalto’s Biography could be recorded as either Harri Aalto (Actor Appellation) “immigrated to Canada in 1952” (Biography Content with an “English” Biography Language) along with “a immigré au Canada en 1952” (Biography Content with a “French” Biography Language) or as “Harri Aalto immigrated to Canada in 1952 / Harri Aalto a immigré au Canada en 1952” (Biography Content with no way to record both languages in the Biography Language).|
|**Value Origin(s)**|Actors Checklist: Biography Language: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|Internationally or nationally agreed codes and terminologies can be used, and the field accommodates all UTF-8 compliant languages.<br><br>The language of the Biography Language can differ from that of the Biography Content (for example, the Biography Content can be “ᕿᓐᓄᐊᔪᐊᖅᐋᓯᕙᒃ(ᐃᓅᓕᖅᑐᖅ: 3 ᐅᑐᐱᕆ, 1927 - 8 ᔭᓐᓄᐊᓕ2013) ᓴᓇᙳᐊᖅᑐᖅ. ᓄᓇᖃᖅᑐᖅᑭᙵᐃᒻᒥ.”, yet the Language of the Biography Content can be “Inuktitut” rather than “ᐃᓄᒃᑎᑐᑦ”).|
|**Reference(s)**|[(Le Boeuf et al. 2015, sec. E56 Language)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Canadian Heritage 2016)](/collections-model/semantic-paths-specification/current/bibliography#canadian-heritage-2016), [(Wikipedia 2019ae)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019ae)|

---

## Biography Bibliographical Mention

|---|---|
|**Scope**|This designates an informational statement appended to the Biography Content for substantiation. It provides relevant information to cite the Biography Content such as author, year of publication, title, publisher, etc.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Biograph Content](#biography-content)|
|**Related SQN(s)**|Biography: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P67i\_is\_referred\_to\_by -\> crm:E33\_Linguistic\_Object (*-\> crm:P2\_has\_type -\> crm:E55\_Type\["Biography"\]*) -\> dct:source -\> **xsd:string**</span>|
|**Target Model View(s)**|[Biography](https://chin-rcip.github.io/collections-model/target-model/current/descriptive-information#biography)|
|**Semantic Valuation**|*Low*: The value provided is an unstructured string that contains the information of a bibliographic mention.<br><br>*Medium*: The value provided is a string of a bibliographic mention that follows a citation convention that is not the one adopted by CHIN.<br>Accepted Value Type: String<br><br>*High*: The value provided is a string of a bibliographic mention that follows the citation convention adopted by CHIN.<br>Accepted Value Type: String|
|**Typical Case(s)**|“Robertson, Carmen. 2016. *Norval Morrisseau: Life & Work*. Canadian Art Books. Toronto, ON: Art Canada Institute / Institut de l’art canadien, p. 4”<br><br>“Canadian Heritage. 2016. ‘Aalto, Harri’. In *Artists in Canada*. Ottawa, ON: Government of Canada / Gouvernement du Canada.[https://app.pch.gc.ca/application/aac-aic/artiste\_detailler\_ind-artist\_detail\_ind.app?lang=en\&qlang=en\&rID=1\&pID=1\&fID=2\&anm=Aalto%2C+Harri\&sort=AM\_ASC\&ps=50\&pID1=1\&ps1=50\&ansf=TAM\&sort1=ascending](https://app.pch.gc.ca/application/aac-aic/artiste_detailler_ind-artist_detail_ind.app?lang=en&qlang=en&rID=1&pID=1&fID=2&anm=Aalto%2C+Harri&sort=AM_ASC&ps=50&pID1=1&ps1=50&ansf=TAM&sort1=ascending).”|
|**Edge Case(s)**|A museum could decide to use a bibliography manager and link to the manager’s entry instead of copying it.|
|**Value Origin(s)**|Actors Checklist: Biography Biographical Mention: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|CHIN recommends the use of a recognized and standard citation format such as that of the Chicago Manual of Style (CMS), Modern Languages Association (MLA) or American Psychological Association (APA).|
|**Reference(s)**|[(Free Dictionary 2019ah)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019ah), [(Canadian Heritage 2016)](/collections-model/semantic-paths-specification/current/bibliography#canadian-heritage-2016), [(Robertson 2016)](/collections-model/semantic-paths-specification/current/bibliography#robertson-carmen-2016)|

---

## Birth/Formation Date Begin

|---|---|
|**Scope**|This field designates the earliest temporal instant of the actor/entity’s biological or organizational coming in existence into the world (i.e. for humans, outside of the womb).|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|E39\_Actor|
|**Full Path**|<span class="full-path">crm:E21\_Actor -\> crm:P98i\_was\_born -\> crm:E67\_Birth -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82a\_begin\_of\_the\_begin -\> xsd:dateTime<br><br>crm:E74\_Group -\> crm:P95i\_was\_formed\_by -\> crm:E66\_Formation -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82a\_begin\_of\_the\_begin -\> **xsd:dateTime**</span>|
|**Target Model View(s)**|[Birth/Death of People and Formation/Dissolution of Groups](https://chin-rcip.github.io/collections-model/target-model/current/life-events#birthdeath-of-people-and-formationdissolution-of-groups)|
|**Semantic Valuation**|*Low*: The value provided temporalizes the beginning of the event, but this information cannot be automatically extracted and formatted.<br><br>*Medium*: The date can be automatically extracted from the value provided (and from textual content that surrounds it if applicable) and can be formatted using the YYYY-MM-DD convention.<br>Accepted Value Type(s): String<br><br>*High*: The date is the sole value provided and is formatted using the date convention.<br>Accepted Value Type(s): DateTime (YYYY-MM-DDThh:mm:ss)|
|**Typical Case(s)**|Emily Carr (Actor Appellation) was born on 1871-12-13 (Birth/Formation Date Begin).<br><br>“David Altmejd” (Actor Appellation) was born in 1974 could be indicated as “1974” (Birth/Formation Date Begin) or “after” (Birth/Formation Date Begin Qualifier) “1973-12-31” (Birth/Formation Date End) and “before” (Birth/Formation Date End Qualifier) “1975-01-01” (Birth/Formation Date End).<br><br>The “Hudson’s Bay Company (HBC)” (Actor Appellation) was chartered on “2 May 1670” (Birth/Formation Date Begin) “CE” (Birth/Formation Date Begin Qualifier).|
|**Edge Case(s)**|Numerical entering of dates might be misleading. For example, 06-12-45 might refer to June 12th, 1845 just as much as December 6th, 1945.<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Birth/Formation Date Begin: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|CHIN recommends using the following format when entering dates: “YYYY-MM-DD HH:MM:SS”. However, if the data cannot be converted to such a format (such as in the case of an era), a string can be used (e.g. Han Dynasty).|
|**Reference(s)**|[(Art & Architecture Thesaurus 2019m)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019m), [(Art & Architecture Thesaurus 2019w)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019w), [(Le Boeuf et al. 2015, sec. E67 Birth)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Free Dictionary 2019x)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019x), [(Free Dictionary 2019y)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019y), [(Free Dictionary 2019b)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019b)|

---

## Birth/Formation Date Begin Qualifier

|---|---|
|**Scope**|This field qualifies the earliest temporal instant of the actor/entity’s biological or organizational coming in existence into the world (i.e. for humans, outside of the womb).|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Birth/Formation Date Begin](#birthformation-date-begin)|
|**Full Path**|<span class="full-path">crm:E21\_Actor -\> crm:P98i\_was\_born -\> crm:E67\_Birth -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P79\_beginning\_is\_qualified\_by -\> xsd:string<br><br>crm:E74\_Group -\> crm:P95i\_was\_formed\_by -\> crm:E66\_Formation -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P79\_beginning\_is\_qualified\_by -\> **xsd:string**</span>|
|**Target Model View(s)**|[Birth/Death of People and Formation/Dissolution of Groups](https://chin-rcip.github.io/collections-model/target-model/current/life-events#birthdeath-of-people-and-formationdissolution-of-groups)|
|**Semantic Valuation**|*Low*: The value provided qualifies the date of the event, but this information is unstructured and cannot be automatically formatted.<br><br>*Medium*: The value provided qualifies the date of the event and can be (semi-)automatically cleaned and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String<br><br>*High*: The qualifier is the sole value provided and is structured and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String|
|**Typical Case(s)**|“Jean Koch” (Actor Appellation) was born “circa” (Birth/Formation Date Begin Qualifier) “1765” (Birth/Formation Date Begin).<br><br>“David Altmejd” (Actor Appellation) was born in 1974 could be indicated as “1974” (Birth/Formation Date Begin) or “after” (Birth/Formation Date Begin Qualifier) “1973-12-31” (Birth/Formation Date End) and “before” (Birth/Formation Date End Qualifier) “1975-01-01” (Birth/Formation Date End).<br><br>The “Hudson’s Bay Company (HBC)” (Actor Appellation) was chartered on “2 May 1670” (Birth/Formation Date Begin) “CE” (Birth/Formation Date Begin Qualifier).|
|**Edge Case(s)**|There might be cases where the Birth/Formation Date Begin and the Birth/Formation Date Begin Qualifier would be the same, in particular when it comes to eras. For example, “Victorian Era” can be both the Birth/Formation Date Begin and the Birth/Formation Date Begin Qualifier. Determining what eras the qualifiers will entail (through the vocabulary used to handle them) will thus be paramount.<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Birth/Formation Date Begin Qualifier: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|There can be more than one qualifier at once for a single Birth/Formation Date Begin (e.g. “BCE” and “BC”, which is the same information, the former being qualified using the non-christian acronym for “Before Common Era” and the latter using the christian “Before Christ”).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020), [(Wikipedia 2019o)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019o), [(Wikipedia 2019r)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019r), [(Wikipedia 2019w)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019w)|

---

## Birth/Formation Date End

|---|---|
|**Scope**|This field designates the latest temporal instant of the actor/entity’s biological or organizational coming in existence into the world (i.e. for humans, outside of the womb).|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|E39\_Actor|
|**Full Path**|<span class="full-path">crm:E21\_Actor -\> crm:P98i\_was\_born -\> crm:E67\_Birth -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82b\_end\_of\_the\_end -\> xsd:dateTime<br><br>crm:E74\_Group -\> crm:P95i\_was\_formed\_by -\> crm:E66\_Formation -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82b\_end\_of\_the\_end -\> **xsd:dateTime**</span>|
|**Target Model View(s)**|[Birth/Death of People and Formation/Dissolution of Groups](https://chin-rcip.github.io/collections-model/target-model/current/life-events#birthdeath-of-people-and-formationdissolution-of-groups)|
|**Semantic Valuation**|*Low*: The value provided temporalizes the beginning of the event, but this information cannot be automatically extracted and formatted.<br><br>*Medium*: The date can be automatically extracted from the value provided (and from textual content that surrounds it if applicable) and can be formatted using the YYYY-MM-DD convention.<br>Accepted Value Type(s): String<br><br>*High*: The date is the sole value provided and is formatted using the date convention.<br>Accepted Value Type(s): DateTime (YYYY-MM-DDThh:mm:ss)|
|**Typical Case(s)**|“David Altmejd” (Actor Appellation) was born in 1974 could be indicated as “1974” (Birth/Formation Date Begin) or “after” (Birth/Formation Date Begin Qualifier) “1973-12-31” (Birth/Formation Date End) and “before” (Birth/Formation Date End Qualifier) “1975-01-01” (Birth/Formation Date End).|
|**Edge Case(s)**|Numerical entering of dates might be misleading. For example, 06-12-45 might refer to June 12th, 1845 just as much as December 6th, 1945.<br><br>This field does not document the end of the *life* of the Actor, but the end of their *birth*. In most cases, Birth/Formation Date Begin will be the same as Birth/Formation Date End except in instances when the birth started on a specific date (e.g. 1959-07-19) and finished on another (1959-07-20).<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Birth/Formation Date End: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|CHIN recommends using the following format when entering dates: “YYYY-MM-DD HH:MM:SS”. However, if the data cannot be converted to such a format (such as in the case of an era), a string can be used (e.g. Han Dynasty).<br><br>This field does not document the end of the *life*of the Actor, but the end of their *birth*. In most cases, Birth/Formation Date Begin will be the same as Birth/Formation Date End except in instances when the birth started on a specific date (e.g. 1959-07-19) and finished on another (1959-07-20).|
|**Reference(s)**|[(Art & Architecture Thesaurus 2019m)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019m), [(Art & Architecture Thesaurus 2019w)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019w), [(Le Boeuf et al. 2015, sec. E67 Birth)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Free Dictionary 2019x)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019x), [(Free Dictionary 2019y)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019y), [(Free Dictionary 2019b)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019b), [(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020)|

---

## Birth/Formation Date End Qualifier

|---|---|
|**Scope**|This field qualifies the latest temporal instant of the actor/entity’s biological or organizational coming in existence into the world (i.e. for humans, outside of the womb).|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Birth/Formation Date End](#birthformation-date-end)|
|**Full Path**|<span class="full-path">crm:E21\_Actor -\> crm:P98i\_was\_born -\> crm:E67\_Birth -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P80\_end\_is\_qualified\_by -\> xsd:string<br><br>crm:E74\_Group -\> crm:P95i\_was\_formed\_by -\> crm:E66\_Formation -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P80\_end\_is\_qualified\_by -\> **xsd:string**</span>|
|**Target Model View(s)**|[Birth/Death of People and Formation/Dissolution of Groups](https://chin-rcip.github.io/collections-model/target-model/current/life-events#birthdeath-of-people-and-formationdissolution-of-groups)|
|**Semantic Valuation**|*Low*: The value provided qualifies the date of the event, but this information is unstructured and cannot be automatically formatted.<br><br>*Medium*: The value provided qualifies the date of the event and can be (semi-)automatically cleaned and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String<br><br>*High*: The qualifier is the sole value provided and is structured and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String|
|**Typical Case(s)**|“David Altmejd” (Actor Appellation) was born in 1974 could be indicated as “1974” (Birth/Formation Date Begin) or “after” (Birth/Formation Date Begin Qualifier) “1973-12-31” (Birth/Formation Date End) and “before” (Birth/Formation Date End Qualifier) “1975-01-01” (Birth/Formation Date End).|
|**Edge Case(s)**|There might be cases where the Birth/Formation Date End and the Birth/Formation Date End Qualifier would be the same, in particular when it comes to eras. For example, “Victorian Era” can be both the Birth/Formation Date End and the Birth/Formation Use Date End Qualifier. Determining what eras the qualifiers will entail (through the vocabulary used to handle them) will thus be paramount.<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Birth/Formation Date End Qualifier: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|There can be more than one qualifier at once for a single Birth/Formation Date End (e.g. “BCE” and “BC”, which is the same information, the former being qualified using the non-christian acronym for “Before Common Era” and the latter using the christian “Before Christ”).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020), [(Wikipedia 2019o)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019o), [(Wikipedia 2019r)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019r), [(Wikipedia 2019w)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019w)|

---

## Birth/Formation Place

|---|---|
|**Scope**|This field identifies the location of the actor/entity’s biological or organizational coming in existence into the world (i.e. for humans, outside of the womb).|
|**Generated Bond(s)**|E53\_Place|
|**Dependency(ies)**|E39\_Actor|
|**Full Path**|<span class="full-path">crm:E21\_Actor -\> crm:P98i\_was\_born -\> crm:E67\_Birth -\> crm:P7\_took\_place\_at -\> crm:E53\_Place<br><br>crm:E74\_Group -\> crm:P95i\_was\_formed\_by -\> crm:E66\_Formation -\> crm:P7\_took\_place\_at -\> **crm:E53\_Place**</span>|
|**Target Model View(s)**|[Birth/Death of People and Formation/Dissolution of Groups](https://chin-rcip.github.io/collections-model/target-model/current/life-events#birthdeath-of-people-and-formationdissolution-of-groups)|
|**Semantic Valuation**|*Low*: The value provided is a string that cannot be parsed automatically by reconciliation tools but still contains the required information.<br><br>*Medium*: The value provided is a string that can be automatically cleaned and reconciled using controlled vocabularies specified by CHIN. In the event that the value is adequately structured but does not reconcile with any terms from the controlled vocabulary, and provided that it is deemed relevant, CHIN will add the term to the vocabulary.<br>Accepted Value Type(s): String<br><br>*High*: The provided value is a string that can be automatically reconciled with the controlled vocabularies specified by CHIN.<br>Accepted Value Type(s): String, URI|
|**Typical Case(s)**|“David Altmejd” (Actor Appellation) was born in “Montréal, QC” (Birth/Formation Place) in “1974” (Birth/Formation Date Begin).|
|**Edge Case(s)**|“Maud Kathleen Lewis” (Actor Appellation) was born in her “South Ohio, NS” (Birth/Formation Place) childhood home to John and Agnes Dowley. In addition to documenting the municipality where she was born, an institution might want to record that “she was born in her childhood home”. The latter could be considered an Annotation on the Birth/Formation Place or a Birth/Formation Place in and of itself.<br><br>A group might not have a single Formation Place as its members can consider themselves part of a collective without sharing a common space. Alternatively, this poses the question of whether an online meeting space is considered to be a Place. For example, would members of the Nettime mailing list be considered to be part of a group which would have the “nettime.org” Formation Place?|
|**Value Origin(s)**|Actors Checklist: Birth/Formation Place: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|This field accommodates all forms of modern and historical locations, physical features, or nations, on Earth or not.<br><br>A single Birth/Formation can be linked to several Birth/Formation places (e.g. Ottawa, Ontario, Canada).|
|**Reference(s)**|[(Le Boeuf et al. 2015, sec. E53 Place)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Bekiari et al. 2015, sec. F9 Place)](/collections-model/semantic-paths-specification/current/bibliography#bekiari-et-al-2015), [(Free Dictionary 2019m)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019m), [(Free Dictionary 2019n)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019n), [(Thesaurus of Geographic Names 2019)](/collections-model/semantic-paths-specification/current/bibliography#thesaurus-of-geographic-names-2019), [(Wikipedia 2019am)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019am)|

---

## Community

|---|---|
|**Scope**|This field indicates the status of belonging to a group or social unit with common norms, values, customs, practices and identities, along with shared beliefs, preferences, needs, and risks. This belonging does not have to be formalized through a governmental body and revolves, rather, around participation and fellowship (although official belonging can occur, such as in the case of Religious communities).|
|**Generated Bond(s)**|E74\_Group|
|**Dependency(ies)**|E39\_Actor|
|**Related SQN(s)**|Identity: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P143i\_was\_joined\_by -\> crm:E85\_Joining -\> crm:P144\_joined\_with -\> **crm:E74\_Group** (*-\> crm:E55\_Type -\> crm:P2\_has\_type -\> crm:E55\_Type\["Identity"\]*)<br><br>crm:E39\_Actor -\> crm:P145i\_left\_by -\> crm:E86\_Leaving -\> crm:P146\_separated\_from -\> **crm:E74\_Group** (*-\> crm:E55\_Type -\> crm:P2\_has\_type -\> crm:E55\_Type\["Identity"\]*)</span>|
|**Target Model View(s)**|[Nationality, Nationhood and Community with E74 Group](https://chin-rcip.github.io/collections-model/target-model/current/identification#nationality-nationhood-and-community-with-e74-group)|
|**Semantic Valuation**|*Low*: The value provided is a string that cannot be parsed automatically by reconciliation tools but still contains the required information.<br><br>*Medium*: The value provided is a string that can be automatically cleaned and reconciled using controlled vocabularies specified by CHIN. In the event that the value is adequately structured but does not reconcile with any terms from the controlled vocabulary, and provided that it is deemed relevant, CHIN will add the term to the vocabulary.<br>Accepted Value Type(s): String<br><br>*High*: The provided value is a string that can be automatically reconciled with the controlled vocabularies specified by CHIN.<br>Accepted Value Type(s): String, URI|
|**Typical Case(s)**|Rebecca Belmore is an “Anishinaabe” (Community) “Canadian” (Nationality) multidisciplinary artist and member of the “Lac Seul First Nation” (Nationhood). Belmore identifies as “Anishinaabe” (Cultural Affiliation Type).<br><br>Benjamin West is a “British” (Nationality) painter most associated with his depiction of what is now “Canada” (Community) despite his living and identifying most with “Europe” (Cultural Affiliation Type) during his lifetime.<br><br>Armand Vaillancourt is a “French-Canadian” (Community) “Canadian” (Nationality) sculptor, painter, and performance artist who identifies as “Québécois” (Cultural Affiliation Type).<br><br>Kehinde Wiley is an “American” (Nationality) “Nigerian-American” (Community) “Angeleno” (Community) portrait painter.<br><br>Mickalene Thomas is an “American” (Nationality) “African-American” (Community) “Queer” (Community) “New York” (Cultural Affiliation Type) based multimedia artist.|
|**Edge Case(s)**|Community and Cultural Affiliation Type are two fields that are extremely similar and it is highly likely that they will be confused as most people who are part of a community identify as part of that community (cultural affiliation type). Nonetheless, having both fields appears to be useful to differentiate between the community people are perceived to be part of (Community) from which they identify with. One of the types of information CHIN has not yet determined where to assign is smaller bodies such as provinces that could be recorded in Community or Cultural Affiliation Type. Other identity affiliation might also be difficult to categorize. For example, Armand Vaillancourt identified as a “souverainiste”, which could fit (although this is debatable) the scope of Cultural Affiliation Type.|
|**Value Origin(s)**|Actors Checklist: Community: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|Belonging to a community revolves around four major elements that can be used to assess it: membership (the actor shares a sense of personal relatedness); influence (the actor matters to the group and the group matters to the actor); reinforcement (the group contributes to the integration of the actor and the fulfillment of their needs); emotional connection.<br><br>*Tricky to find URIs. TGN often prefers English-language or historical names, and may not recognize Indigenous names or variations at all. Geonames has many alternate names, but they are tied to languages and relevancy/preference are not clearly defined (although it has the capabilities to do so, implementation is inconsistent). TGN has one determined “preferred name” whereas Geonames does not require a single controlled term.*|
|**Reference(s)**|[(Free Dictionary 2019i)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019i), [(Wikipedia 2019s)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019s)|

---

## Community Joining Date Begin

|---|---|
|**Scope**|This field designates the earliest temporal instant the actor started belonging, formally or informally, to the community.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Community](#community)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P143i\_was\_joined\_by -\> crm:E85\_Joining -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82a\_begin\_of\_the\_begin -\> **xsd:dateTime**</span>|
|**Target Model View(s)**|[Nationality, Nationhood and Community with E74 Group](https://chin-rcip.github.io/collections-model/target-model/current/identification#nationality-nationhood-and-community-with-e74-group)|
|**Semantic Valuation**|*Low*: The value provided temporalizes the beginning of the event, but this information cannot be automatically extracted and formatted.<br><br>*Medium*: The date can be automatically extracted from the value provided (and from textual content that surrounds it if applicable) and can be formatted using the YYYY-MM-DD convention.<br>Accepted Value Type(s): String<br><br>*High*: The date is the sole value provided and is formatted using the date convention.<br>Accepted Value Type(s): DateTime (YYYY-MM-DDThh:mm:ss)|
|**Typical Case(s)**|Arthur Guindon (Actor Appellation) was a poet and painter. He studied at the Grand Séminaire de Montréal and wanted to join the Compagnie des PrÕtres de Saint-Sulpice (Community). He mentions this early in 1894 (Community Joining Date Begin “1894”; Community Joining Date Begin Qualifier “early”) and becomes a member later in 1894 (Community Joining Date End “1894”; Community Joining Date End Qualifier “later”).<br><br>Joseph Légaré (Actor Appellation) was a painter born on March 10th, 1795. He studied at the Séminaire de Québec around 1811, but left soon after to study painting (Community “Diocesan”; Community Joining Date Begin “1811”; Community Joining Date Begin Qualifier “circa”; Community Joining Date End “1812”; Community Joining Date End Qualifier “before”; Community Leaving Date Begin “1811”; Community Leaving Date Begin Qualifier “circa”; Community Leaving Date End “1812”; Community Leaving Date End Qualifier “before”).<br><br>The Guerilla Girls (Group Appellation) are an anonymous group of artists who identify as feminists as of their formation in 1985 (Community “Feminist”; Community Joining Date Begin “1985”).|
|**Edge Case(s)**|Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Community Joining Date Begin: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|CHIN recommends using the following format when entering dates: “YYYY-MM-DD HH:MM:SS”. However, if the data cannot be converted to such a format (such as in the case of an era), a string can be used (e.g. Han Dynasty).|
|**Reference(s)**|[(Le Boeuf et al. 2015, sec. E85 Joining)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Free Dictionary 2019aa)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019aa)|

---

## Community Joining Date Begin Qualifier

|---|---|
|**Scope**|This field qualifies the earliest temporal instant the actor started belonging, formally or informally, to the community.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Community Joining Date Begin](#community-joining-date-begin)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P143i\_was\_joined\_by -\> crm:E85\_Joining -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P79\_beginning\_is\_qualified\_by -\> **xsd:string**</span>|
|**Target Model View(s)**|[Nationality, Nationhood and Community with E74 Group](https://chin-rcip.github.io/collections-model/target-model/current/identification#nationality-nationhood-and-community-with-e74-group)|
|**Semantic Valuation**|*Low*: The value provided qualifies the date of the event, but this information is unstructured and cannot be automatically formatted.<br><br>*Medium*: The value provided qualifies the date of the event and can be (semi-)automatically cleaned and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String<br><br>*High*: The qualifier is the sole value provided and is structured and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String|
|**Typical Case(s)**|Arthur Guindon (Actor Appellation) was a poet and painter. He studied at the Grand Séminaire de Montréal and wanted to join the Compagnie des PrÕtres de Saint-Sulpice (Community). He mentions this early in 1894 (Community Joining Date Begin “1894”; Community Joining Date Begin Qualifier “early”) and becomes a member later in 1894 (Community Joining Date End “1894”; Community Joining Date End Qualifier “later”).<br><br>Joseph Légaré (Actor Appellation) was a painter born on March 10th, 1795. He studied at the Séminaire de Québec around 1811, but left soon after to study painting (Community “Diocesan”; Community Joining Date Begin “1811”; Community Joining Date Begin Qualifier “circa”; Community Joining Date End “1812”; Community Joining Date End Qualifier “before”; Community Leaving Date Begin “1811”; Community Leaving Date Begin Qualifier “circa”; Community Leaving Date End “1812”; Community Leaving Date End Qualifier “before”).|
|**Edge Case(s)**|Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Community Joining Date Begin Qualifier: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|There can be more than one qualifier at once for a single Joining Date Begin (e.g. “BCE” and “BC”, which is the same information, the former being qualified using the non-christian acronym for “Before Common Era” and the latter using the christian “Before Christ”).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020), [(Wikipedia 2019o)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019o), [(Wikipedia 2019r)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019r), [(Wikipedia 2019w)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019w)|

---

## Community Joining Date End

|---|---|
|**Scope**|This field designates the latest temporal instant the actor started belonging, formally or informally, to the community.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Community](#community)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P143i\_was\_joined\_by -\> crm:E85\_Joining -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82b\_end\_of\_the\_end -\> **xsd:dateTime**</span>|
|**Target Model View(s)**|[Nationality, Nationhood and Community with E74 Group](https://chin-rcip.github.io/collections-model/target-model/current/identification#nationality-nationhood-and-community-with-e74-group)|
|**Semantic Valuation**|*Low*: The value provided temporalizes the beginning of the event, but this information cannot be automatically extracted and formatted.<br><br>*Medium*: The date can be automatically extracted from the value provided (and from textual content that surrounds it if applicable) and can be formatted using the YYYY-MM-DD convention.<br>Accepted Value Type(s): String<br><br>*High*: The date is the sole value provided and is formatted using the date convention.<br>Accepted Value Type(s): DateTime (YYYY-MM-DDThh:mm:ss)|
|**Typical Case(s)**|Arthur Guindon (Actor Appellation) was a poet and painter. He studied at the Grand Séminaire de Montréal and wanted to join the Compagnie des PrÕtres de Saint-Sulpice (Community). He mentions this early in 1894 (Community Joining Date Begin “1894”; Community Joining Date Begin Qualifier “early”) and becomes a member later in 1894 (Community Joining Date End “1894”; Community Joining Date End Qualifier “later”).<br><br>Joseph Légaré (Actor Appellation) was a painter born on March 10th, 1795. He studied at the Séminaire de Québec around 1811, but left soon after to study painting (Community “Diocesan”; Community Joining Date Begin “1811”; Community Joining Date Begin Qualifier “circa”; Community Joining Date End “1812”; Community Joining Date End Qualifier “before”; Community Leaving Date Begin “1811”; Community Leaving Date Begin Qualifier “circa”; Community Leaving Date End “1812”; Community Leaving Date End Qualifier “before”).|
|**Edge Case(s)**|Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Community Joining Date End: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|CHIN recommends using the following format when entering dates: “YYYY-MM-DD HH:MM:SS”. However, if the data cannot be converted to such a format (such as in the case of an era), a string can be used (e.g. Han Dynasty).|
|**Reference(s)**|[(Le Boeuf et al. 2015, sec. E85 Joining)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Free Dictionary 2019aa)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019aa)|

---

## Community Joining Date End Qualifier

|---|---|
|**Scope**|This field qualifies the latest temporal instant the actor started belonging, formally or informally, to the community.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Community Joining Date End](#community-joining-date-end)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P143i\_was\_joined\_by -\> crm:E85\_Joining -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P80\_end\_is\_qualified\_by -\> **xsd:string**</span>|
|**Target Model View(s)**|[Nationality, Nationhood and Community with E74 Group](https://chin-rcip.github.io/collections-model/target-model/current/identification#nationality-nationhood-and-community-with-e74-group)|
|**Semantic Valuation**|*Low*: The value provided qualifies the date of the event, but this information is unstructured and cannot be automatically formatted.<br><br>*Medium*: The value provided qualifies the date of the event and can be (semi-)automatically cleaned and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String<br><br>*High*: The qualifier is the sole value provided and is structured and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String|
|**Typical Case(s)**|Arthur Guindon (Actor Appellation) was a poet and painter. He studied at the Grand Séminaire de Montréal and wanted to join the Compagnie des PrÕtres de Saint-Sulpice (Community). He mentions this early in 1894 (Community Joining Date Begin “1894”; Community Joining Date Begin Qualifier “early”) and becomes a member later in 1894 (Community Joining Date End “1894”; Community Joining Date End Qualifier “later”).<br><br>Joseph Légaré (Actor Appellation) was a painter born on March 10th, 1795. He studied at the Séminaire de Québec around 1811, but left soon after to study painting (Community “Diocesan”; Community Joining Date Begin “1811”; Community Joining Date Begin Qualifier “circa”; Community Joining Date End “1812”; Community Joining Date End Qualifier “before”; Community Leaving Date Begin “1811”; Community Leaving Date Begin Qualifier “circa”; Community Leaving Date End “1812”; Community Leaving Date End Qualifier “before”).|
|**Edge Case(s)**|Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Community Joining Date End Qualifier: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|There can be more than one qualifier at once for a single Joining Date End (e.g. “BCE” and “BC”, which is the same information, the former being qualified using the non-christian acronym for “Before Common Era” and the latter using the christian “Before Christ”).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020), [(Wikipedia 2019o)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019o), [(Wikipedia 2019r)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019r), [(Wikipedia 2019w)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019w)|

---

## Community Leaving Date Begin

|---|---|
|**Scope**|This field designates the earliest temporal instant the actor stopped belonging, formally or informally, to the community.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Community](#community)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:PP145i\_left\_by -\> crm:E86\_Leaving -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82a\_begin\_of\_the\_begin -\> **xsd:dateTime**</span>|
|**Target Model View(s)**|[Nationality, Nationhood and Community with E74 Group](https://chin-rcip.github.io/collections-model/target-model/current/identification#nationality-nationhood-and-community-with-e74-group)|
|**Semantic Valuation**|*Low*: The value provided temporalizes the beginning of the event, but this information cannot be automatically extracted and formatted.<br><br>*Medium*: The date can be automatically extracted from the value provided (and from textual content that surrounds it if applicable) and can be formatted using the YYYY-MM-DD convention.<br>Accepted Value Type(s): String<br><br>*High*: The date is the sole value provided and is formatted using the date convention.<br>Accepted Value Type(s): DateTime (YYYY-MM-DDThh:mm:ss)|
|**Typical Case(s)**|Joseph Légaré (Actor Appellation) was a painter born on March 10th, 1795. He studied at the Séminaire de Québec around 1811, but left soon after to study painting (Community “Diocesan”; Community Joining Date Begin “1811”; Community Joining Date Begin Qualifier “circa”; Community Joining Date End “1812”; Community Joining Date End Qualifier “before”; Community Leaving Date Begin “1811”; Community Leaving Date Begin Qualifier “circa”; Community Leaving Date End “1812”; Community Leaving Date End Qualifier “before”).|
|**Edge Case(s)**|Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Community Leaving Date Begin: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|CHIN recommends using the following format when entering dates: “YYYY-MM-DD HH:MM:SS”. However, if the data cannot be converted to such a format (such as in the case of an era), a string can be used (e.g. Han Dynasty).|
|**Reference(s)**|[(Le Boeuf et al. 2015, sec. E86 Leaving)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Free Dictionary 2019ab)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019ab)|

---

## Community Leaving Date Begin Qualifier

|---|---|
|**Scope**|This field qualifies the earliest temporal instant the actor stopped belonging, formally or informally, to the community.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Community Leaving Date Begin](#community-leaving-date-begin)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P145i\_left\_by -\> crm:E86\_Leaving -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P79\_beginning\_is\_qualified\_by -\> **xsd:string**</span>|
|**Target Model View(s)**|[Nationality, Nationhood and Community with E74 Group](https://chin-rcip.github.io/collections-model/target-model/current/identification#nationality-nationhood-and-community-with-e74-group)|
|**Semantic Valuation**|*Low*: The value provided qualifies the date of the event, but this information is unstructured and cannot be automatically formatted.<br><br>*Medium*: The value provided qualifies the date of the event and can be (semi-)automatically cleaned and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String<br><br>*High*: The qualifier is the sole value provided and is structured and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String|
|**Typical Case(s)**|Joseph Légaré (Actor Appellation) was a painter born on March 10th, 1795. He studied at the Séminaire de Québec around 1811, but left soon after to study painting (Community “Diocesan”; Community Joining Date Begin “1811”; Community Joining Date Begin Qualifier “circa”; Community Joining Date End “1812”; Community Joining Date End Qualifier “before”; Community Leaving Date Begin “1811”; Community Leaving Date Begin Qualifier “circa”; Community Leaving Date End “1812”; Community Leaving Date End Qualifier “before”).|
|**Edge Case(s)**|Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Community Leaving Date Begin Qualifier: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|There can be more than one qualifier at once for a single Leaving Date Begin (e.g. “BCE” and “BC”, which is the same information, the former being qualified using the non-christian acronym for “Before Common Era” and the latter using the christian “Before Christ”).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020), [(Wikipedia 2019o)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019o), [(Wikipedia 2019r)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019r), [(Wikipedia 2019w)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019w)|

---

## Community Leaving Date End

|---|---|
|**Scope**|This field designates the latest temporal instant the actor stopped belonging, formally or informally, to the community.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Community](#community)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:PP145i\_left\_by -\> crm:E86\_Leaving -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82a\_begin\_of\_the\_begin -\> **xsd:dateTime**</span>|
|**Target Model View(s)**|[Nationality, Nationhood and Community with E74 Group](https://chin-rcip.github.io/collections-model/target-model/current/identification#nationality-nationhood-and-community-with-e74-group)|
|**Semantic Valuation**|*Low*: The value provided temporalizes the beginning of the event, but this information cannot be automatically extracted and formatted.<br><br>*Medium*: The date can be automatically extracted from the value provided (and from textual content that surrounds it if applicable) and can be formatted using the YYYY-MM-DD convention.<br>Accepted Value Type(s): String<br><br>*High*: The date is the sole value provided and is formatted using the date convention.<br>Accepted Value Type(s): DateTime (YYYY-MM-DDThh:mm:ss)|
|**Typical Case(s)**|Joseph Légaré (Actor Appellation) was a painter born on March 10th, 1795. He studied at the Séminaire de Québec around 1811, but left soon after to study painting (Community “Diocesan”; Community Joining Date Begin “1811”; Community Joining Date Begin Qualifier “circa”; Community Joining Date End “1812”; Community Joining Date End Qualifier “before”; Community Leaving Date Begin “1811”; Community Leaving Date Begin Qualifier “circa”; Community Leaving Date End “1812”; Community Leaving Date End Qualifier “before”).|
|**Edge Case(s)**|Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Community Leaving Date End: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|CHIN recommends using the following format when entering dates: “YYYY-MM-DD HH:MM:SS”. However, if the data cannot be converted to such a format (such as in the case of an era), a string can be used (e.g. Han Dynasty).|
|**Reference(s)**|[(Le Boeuf et al. 2015, sec. E86 Leaving)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Free Dictionary 2019ab)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019ab)|

---

## Community Leaving Date End Qualifier

|---|---|
|**Scope**|This field qualifies the latest temporal instant the actor stopped belonging, formally or informally, to the community.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Community Leaving Date End](#community-leaving-date-end)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:PP145i\_left\_by -\> crm:E86\_Leaving -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P80\_end\_is\_qualified\_by -\> **xsd:string**</span>|
|**Target Model View(s)**|[Nationality, Nationhood and Community with E74 Group](https://chin-rcip.github.io/collections-model/target-model/current/identification#nationality-nationhood-and-community-with-e74-group)|
|**Semantic Valuation**|*Low*: The value provided qualifies the date of the event, but this information is unstructured and cannot be automatically formatted.<br><br>*Medium*: The value provided qualifies the date of the event and can be (semi-)automatically cleaned and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String<br><br>*High*: The qualifier is the sole value provided and is structured and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String|
|**Typical Case(s)**|Joseph Légaré (Actor Appellation) was a painter born on March 10th, 1795. He studied at the Séminaire de Québec around 1811, but left soon after to study painting (Community “Diocesan”; Community Joining Date Begin “1811”; Community Joining Date Begin Qualifier “circa”; Community Joining Date End “1812”; Community Joining Date End Qualifier “before”; Community Leaving Date Begin “1811”; Community Leaving Date Begin Qualifier “circa”; Community Leaving Date End “1812”; Community Leaving Date End Qualifier “before”).|
|**Edge Case(s)**|Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Community Leaving Date End Qualifier: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|There can be more than one qualifier at once for a single Leaving Date End (e.g. “BCE” and “BC”, which is the same information, the former being qualified using the non-christian acronym for “Before Common Era” and the latter using the christian “Before Christ”).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020), [(Wikipedia 2019o)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019o), [(Wikipedia 2019r)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019r), [(Wikipedia 2019w)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019w)|

---

## Cultural Affiliation Type

|---|---|
|**Scope**|This field indicates cultural, rather than legal, belonging to a group that is characterized by shared customs, mores, and practices revolving around common elements such as location, history, language, beliefs, culinary practices, etc. It revolves around collective values and identities and, as such, it is possible to have multiple affiliations at once. This belonging is not official in the sense that assent from the concerned group is not formalized or explicit.|
|**Generated Bond(s)**|E55\_Type|
|**Dependency(ies)**|E21\_Person|
|**Related SQN(s)**|Cultural Affiliation: Definition|
|**Full Path**|<span class="full-path">crm:E21\_Person -\> crm:P2\_has\_type -\> **crm:E55\_Type** (*-\> crm:P2\_has\_type -\> crm:E55\_Type\["Cultural Affiliation"\]*)</span>|
|**Target Model View(s)**|[Rendering Gender and Cultural Affiliation with E55 Type](https://chin-rcip.github.io/collections-model/target-model/current/identification#rendering-gender-and-cultural-affiliation-with-e55-type)|
|**Semantic Valuation**|*Low*: The value provided is a string that cannot be parsed automatically by reconciliation tools but still contains the required information.<br><br>*Medium*: The value provided is a string that can be automatically cleaned and reconciled using controlled vocabularies specified by CHIN. In the event that the value is adequately structured but does not reconcile with any terms from the controlled vocabulary, and provided that it is deemed relevant, CHIN will add the term to the vocabulary.<br>Accepted Value Type(s): String<br><br>*High*: The provided value is a string that can be automatically reconciled with the controlled vocabularies specified by CHIN.<br>Accepted Value Type(s): String, URI|
|**Typical Case(s)**|Rebecca Belmore is an “Anishinaabe” (Community) “Canadian” (Nationality) multidisciplinary artist and member of the “Lac Seul First Nation” (Nationhood). Belmore identifies as “Anishinaabe” (Cultural Affiliation Type).<br><br>Benjamin West is a “British” (Nationality) painter most associated with his depiction of what is now “Canada” (Community) despite his living and identifying most with “Europe” (Cultural Affiliation Type) during his lifetime.<br><br>Armand Vaillancourt is a “French-Canadian” (Community) “Canadian” (Nationality) sculptor, painter, and performance artist who identifies as “Québécois” (Cultural Affiliation Type).<br><br>Kehinde Wiley is an “American” (Nationality) “Nigerian-American” (Community) “Angeleno” (Community) portrait painter.<br><br>Mickalene Thomas is an “American” (Nationality) “African-American” (Community) “Queer” (Community) “New York” (Cultural Affiliation Type) based multimedia artist.|
|**Edge Case(s)**|Community and Cultural Affiliation Type are two fields that are extremely similar and it is highly likely that they will be confused as most people who are part of a community identify as part of that community (cultural affiliation). Nonetheless, having both fields appears to be useful to differentiate between the community people are perceived to be part of (Community) from which they identify with. One of the types of information CHIN has not yet determined where to assign is smaller bodies such as provinces that could be recorded in Community or Cultural Affiliation Type. Other identity affiliation might also be difficult to categorize. For example, Armand Vaillancourt identified as a “souverainiste”, which could fit (although this is debatable) the scope of Cultural Affiliation Type.<br><br>Some Actors might identify themselves as “Cosmopolitan” first and foremost, and in such a case it would be recorded here.<br><br>Polities or other groups might identify as being culturally affiliated to larger groups, such as France with regards to Europe.|
|**Value Origin(s)**|Actors Checklist: Cultural Affiliation Type: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|*Vocab observations: AAT generally refers to “culture or style” whereas Wikidata primarily refers to ethnic groups. It’s a tricky field - culture and ethnicity are linked, as are culture and nationality, but they’re not 100% identical.*<br><br>It is distinct from and broader than nationality, which is a strictly legal concept independent of an actors’ explicit or implicit identification with a culture. For example, an artist born in France and endowed with the French nationality could live in Canada for most of their life and claim Canadian cultural affiliation despite not having Canadian citizenship.|
|**Reference(s)**|[(Art & Architecture Thesaurus 2019e)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019e), [(Free Dictionary 2019d)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019d), [(Wikipedia 2019u)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019u), [(Wikipedia 2019u)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019u)|

---

## Curatorial Note Content

|---|---|
|**Scope**|This field records information that is supplemental and associated with an Actor about which it offers further knowledge. It includes comments, remarks, descriptions that would not be biographical, explanations, notes, grades or evaluations, etc.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|E39\_Actor<br><br>Any other field the curatorial note pertains to|
|**Related SQN(s)**|Curatorial Note: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P67i\_is\_referred\_to\_by -\> crm:E33\_Linguistic\_Object (*-\> crm:P2\_has\_type -\> crm:E55\_Type\["Curatorial Note"\]*) -\> crm:P190\_has\_symbolic\_content -\> **xsd:string**</span>|
|**Target Model View(s)**|[Curatorial Note](https://chin-rcip.github.io/collections-model/target-model/current/descriptive-information#curatorial-note)|
|**Semantic Valuation**|*Low*: The value is a string that contains the information needed, but also other and different information that cannot be automatically extracted.<br><br>*Medium*: The value is a string that contains the information needed, but also other and different information that can be automatically extracted.<br>Accepted Value Type(s): String<br><br>*High*: The value is a string that contains only the information needed.<br>Accepted Value Type(s): String|
|**Typical Case(s)**|“Ingenium was called the Canada Science and Technology Museum Corporation up until 2018 and its name is based on the latin root for ingenuity” (Curatorial Note), a note pertaining to “Ingenium” (Actor Appellation or Dataset Provider Appellation).<br><br>“Isabella Mainville Ross (10 January 1808 – 23 April 1885), born to Ojibwe mother Josette Mainville and Scot father Joseph Ross, was the first female registered landowner in British Columbia” (Curatorial Note).<br><br>“Warby Parker” (Group Appellation) “uses a social entrepreneurship program under which the company pays for the production of a pair of glasses given to a non-profit organisation for each pair of glasses that is bought, better described as a “buy one, give one” model” (Curatorial Note).|
|**Edge Case(s)**|Marie-Guillemine Benoist’s *Portrait of Madeleine*was formerly titled *Portrait of a Negress*. Only recent scholarship has established the sitter’s name as “Madeleine”, although her last name remains unknown. An Annotation could be placed on its Object Appellations (“Portrait of Madeleine”, Prefered Appellation, “Formerly titled *Portrait of a Negress*” Annotation; “Portrait of a Negress”, Non-Prefered Appellation, “Now titled Portrait of Madeleine” Annotation; “Portrait d’une femme noire”, Non-Prefered Appellation, “Formerly titled *Portrait d’une négresse*” Annotation), but a Curatorial Note Content might also be used on the Actor Appellation “Madeleine” (“Sitter in *Portrait of Madeleine*, formerly titled *Portrait of a Negress*, identified as being named “Madeleine” by Viktoria Schmidt-Linsenhoff).|
|**Value Origin(s)**|Actors Checklist: Curatorial Note Content: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|This field is meant information that is supplemental to an Actor or Object rather than to a specific piece of data. As such, it is not intended to be used as a container for annotations pertaining to specific pieces of data. For the latter, Annotation should be used.<br><br>As part of the development of the Collections Model, a Caption field will be created and, as such, this field should not be used for Captions.|
|**Reference(s)**|[(Art & Architecture Thesaurus 2020a)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2020a), [(Art & Architecture Thesaurus 2020b)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2020b), [(Art & Architecture Thesaurus 2020c)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2020c), [(Art & Architecture Thesaurus 2020d)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2020d), [(Le Boeuf et al. 2015, sec. P3 Has Note)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Free Dictionary 2020a)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2020a), [(Free Dictionary 2020b)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2020b), [(Wikipedia 2019as)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019as), [(Wikipedia 2019av)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019av), [(Wikipedia 2019aw)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019aw), [(Wikipedia 2019ax)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019ax)|

---

## Curatorial Note Author Appellation

|---|---|
|**Scope**|This field designates the entire identifying word(s), number(s), symbol(s) or code(s) by which the person responsible for the intellectual content and general composition of the Curatorial Note Content, whether it was originally intended for publication or not, is identified.|
|**Generated Bond(s)**|E39\_Actor|
|**Dependency(ies)**|[Curatorial Note Content](#curatorial-note-content)|
|**Related SQN(s)**|Curatorial Note: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P67i\_is\_referred\_to\_by -\> crm:E33\_Linguistic\_Object (*-\> crm:P2\_has\_type -\> crm:E55\_Type\["Curatorial Note"\]*) -\> crm:P94i\_was\_created\_by -\> crm:E65\_Creation -\> crm:P14\_carried\_out\_by -\> crm:E39\_Actor -\> crm:P1\_is\_identified\_by -\> crm:E41\_Appellation + crm:E33\_Linguistic\_Object -\> crm:P190\_has\_symbolic\_content -\> **xsd:string**</span>|
|**Target Model View(s)**|[Curatorial Note](https://chin-rcip.github.io/collections-model/target-model/current/descriptive-information#curatorial-note)|
|**Semantic Valuation**|*Low*: The provided values contain unstructured information of the appellation, such as it cannot be parsed automatically by reconciliation tools, but still contains the required information.<br><br>*Medium*: The provided values contain structured information that can be automatically cleaned and reconciled with other entities in other datasets.<br>Accepted Value Type(s): String<br><br>*High*: The provided values only contain structured information that can be automatically reconciled with other entities in other datasets.<br>Accepted Value Type(s): String|
|**Typical Case(s)**|“Greg A. Hill” (Curatorial Note Author Appellation), as Audain Senior Curator of Indigenous Art at the National Gallery of Canada, might want to comment on an Actor.|
|**Edge Case(s)**|Institutions might want to indicate the position of the author rather than their name. For example “Audain Senior Curator of Indigenous Art at the National Gallery of Canada” rather than “Greg A. Hill” (Actor Appellation).<br><br>It is also possible the author of the note wants to add a bibliographical mention to keep track of the track that he is not the author of the text but of the note.|
|**Value Origin(s)**|Actors Checklist: Curatorial Note Author Appellation: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|CHIN recommends the use of the format “Last Name, First Name, Affix” (e.g. “Serota, Nicholas Andrew, Sir”) but any combination of the author’s Appellation Parts will be accommodated by the field.|
|**Reference(s)**|[(Art & Architecture Thesaurus 2020f)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2020f), [(Farlex 2020)](/collections-model/semantic-paths-specification/current/bibliography#farlex-2020), [(Wikipedia 2020b)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2020b)|

---

## Curatorial Note Language

|---|---|
|**Scope**|This field indicates the natural language the Curatorial Note Content is written or produced in.|
|**Generated Bond(s)**|E56\_Language|
|**Dependency(ies)**|[Curatorial Note Content](#curatorial-note-content)|
|**Related SQN(s)**|Curatorial Note: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P67i\_is\_referred\_to\_by -\> crm:E33\_Linguistic\_Object (*-\> crm:P2\_has\_type -\> crm:E55\_Type\["Curatorial Note"\]*) -\> crm:P72\_has\_language -\> **crm:E56\_Language**</span>|
|**Target Model View(s)**|[Curatorial Note](https://chin-rcip.github.io/collections-model/target-model/current/descriptive-information#curatorial-note)|
|**Semantic Valuation**|*Low*: The value provided is a string that cannot be parsed automatically by reconciliation tools but still contains the required information.<br><br>*Medium*: The value provided is a string that can be automatically cleaned and reconciled using controlled vocabularies specified by CHIN. In the event that the value is adequately structured but does not reconcile with any terms from the controlled vocabulary, and provided that it is deemed relevant, CHIN will add the term to the vocabulary.<br>Accepted Value Type(s): String<br><br>*High*: The provided value is a string that can be automatically reconciled with the controlled vocabularies specified by CHIN.<br>Accepted Value Type(s): String, URI|
|**Typical Case(s)**|“Rebecca Belmore was the first Indigenous woman to present at the Canadian pavilion of the Venice Biennale in 2005” (Curatorial Note) is written in English (Curatorial Note Language).|
|**Edge Case(s)**|Some languages have alphabets that are specific (e.g. Inuktitut) so that determining the Language of the Curatorial Note Content would not be problematic, for example: “ᕿᓐᓄᐊᔪᐊᖅᐋᓯᕙᒃ” is written in Inuktitut. That said, this does not account for dialects nor for the fact that identifying what alphabet a Curatorial Note Content is written in might be problematic. This begs the question of whether we should have a field dedicated to character sets/alphabets (e.g. latin, arabic, chinese, etc.).<br><br>Bilingual considerations could apply to Curatorial Notes as well so that it would either be impossible to assign a single Curatorial Note Language to the Curatorial Note Content, or the field would have to accomodate a list of values.|
|**Value Origin(s)**|Actors Checklist: Curatorial Note Language: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|Internationally or nationally agreed codes and terminologies can be used, and the field accommodates all UTF-8 compliant languages.<br><br>The language of the Curatorial Note Language can differ from that of the Curatorial Note Content (for example, the Curatorial Note Content can be “ᕿᓐᓄᐊᔪᐊᖅᐋᓯᕙᒃ(ᐃᓅᓕᖅᑐᖅ: 3 ᐅᑐᐱᕆ, 1927 - 8 ᔭᓐᓄᐊᓕ2013) ᓴᓇᙳᐊᖅᑐᖅ. ᓄᓇᖃᖅᑐᖅᑭᙵᐃᒻᒥ.”, yet the Language of the Curatorial Note Content can be “Inuktitut” rather than “ᐃᓄᒃᑎᑐᑦ”).|
|**Reference(s)**|[(Le Boeuf et al. 2015, sec. E56 Language)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Wikipedia 2019ae)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019ae)|

---

<div class="hidden-content">
## Dataset Creation Date Begin<br><br>**THIS NODE IS NOT DOCUMENTED YET IN THE TARGET MODEL**

|---|---|
|**Scope**|This field designates the earliest temporal instant of the creation of the dataset by the cataloguing entity (person or institution).|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|To be completed|
|**Full Path**|<span class="full-path">To be completed</span>|
|**Target Model View(s)**|To be completed|
|**Semantic Valuation**|*Low*: The value provided temporalizes the beginning of the event, but this information cannot be automatically extracted and formatted.<br><br>*Medium*: The date can be automatically extracted from the value provided (and from textual content that surrounds it if applicable) and can be formatted using the YYYY-MM-DD convention.<br>Accepted Value Type(s): String<br><br>*High*: The date is the sole value provided and is formatted using the date convention.<br>Accepted Value Type(s): DateTime (YYYY-MM-DDThh:mm:ss)|
|**Typical Case(s)**|To Come|
|**Edge Case(s)**|To Come|
|**Value Origin(s)**|Actors Checklist: Dataset Creation Date Begin: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|This does not indicate the date the dataset was created by CHIN; rather, it refers to the date the dataset was created by the cataloguer at the contributing institution. Since the dataset is created by CHIN, there is no need for the institution to record this date and this field has been deprecated.<br><br>CHIN recommends using the following format when entering dates: “YYYY-MM-DD HH:MM:SS”. However, if the data cannot be converted to such a format (such as in the case of an era), a string can be used (e.g. 2019?).|
|**Reference(s)**|[(Semantic Web Interest Group 2019)](/collections-model/semantic-paths-specification/current/bibliography#semantic-web-interest-group-2019), [(Wikipedia 2019d)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019d)|

---
</div>

<div class="hidden-content">
## Dataset Creation Date End<br><br>**THIS NODE IS NOT DOCUMENTED YET IN THE TARGET MODEL**

|---|---|
|**Scope**|This field designates the latest temporal instant of the creation of the dataset by the cataloguing entity (person or institution).|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|To be completed|
|**Full Path**|<span class="full-path">To be completed</span>|
|**Target Model View(s)**|To be completed|
|**Semantic Valuation**|*Low*: The value provided temporalizes the beginning of the event, but this information cannot be automatically extracted and formatted.<br><br>*Medium*: The date can be automatically extracted from the value provided (and from textual content that surrounds it if applicable) and can be formatted using the YYYY-MM-DD convention.<br>Accepted Value Type(s): String<br><br>*High*: The date is the sole value provided and is formatted using the date convention.<br>Accepted Value Type(s): DateTime (YYYY-MM-DDThh:mm:ss)|
|**Typical Case(s)**|To Come|
|**Edge Case(s)**|To Come|
|**Value Origin(s)**|Actors Checklist: Dataset Creation Date End: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|This does not indicate the date the record CHIN ended the creation of the dataset; rather, it refers to the date the cataloguer at the contributing institution ended the creation of the dataset. Since the dataset is created by CHIN, there is no need for the institution to record this date and this field has been deprecated.<br><br>CHIN recommends using the following format when entering dates: “YYYY-MM-DD HH:MM:SS”. However, if the data cannot be converted to such a format (such as in the case of an era), a string can be used (e.g. 2019?).|
|**Reference(s)**|[(Semantic Web Interest Group 2019)](/collections-model/semantic-paths-specification/current/bibliography#semantic-web-interest-group-2019), [(Wikipedia 2019d)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019d)|

---
</div>

<div class="hidden-content">
## Dataset Provider Appellation<br><br>**THIS NODE IS NOT DOCUMENTED YET IN THE TARGET MODEL**

|---|---|
|**Scope**|This field designates the entire identifying word(s), number(s), symbol(s) or code(s) by which an institution providing a dataset (collection of records) to CHIN is identified.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|To be completed|
|**Full Path**|<span class="full-path">To be completed</span>|
|**Target Model View(s)**|To be completed|
|**Semantic Valuation**|*Low*:<br><br>*Medium*:<br><br>*High*:|
|**Typical Case(s)**|If Ingenium submits a dataset to CHIN, the latter would be associated to “Ingenium” (Dataset Provider Appellation)|
|**Edge Case(s)**|A single institution might have two distinct databases that would be unconnected and thus two Dataset Provider IDs with a single Dataset Provider Appellation.<br><br>A single institution might have more than a single Dataset Provider Appellation as well and, in this case, CHIN would have to determine which one it will use. For example, a dataset coming from the “Canada Science and Technology Museum” (Dataset Provider Appellation) could also be considered to come from “Ingenium” (Dataset Provider Appellation).<br><br>Museums can be considered Actors just as much as Dataset Providers so that where to apply annotations and curatorial notes might be tricky in specific cases such as changes that were brought to the name (e.g. Ingenium), etc. For example, if Ingenium provided datasets prior to 2018 under their previous Appellation “Canada Science and Technology Museum Corporation” and are now providing under “Ingenium” CHIN will have to determine which Dataset Provider Appellation to use for a single ID, whether to have to Dataset Provider Appellations (each linked to a Dataset Provider ID) or when to use which Dataset Provider Appellation with the single Dataset Provider ID, as well as how to display that information.|
|**Value Origin(s)**|Actors Checklist: Dataset Provider Appellation: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|This field is mandatory and enables the identification of all records provided by a given institution, whether it is an aggregator (e.g. NovaMuse) or a GLAM (e.g. National Gallery of Canada).|
|**Reference(s)**|[(Art & Architecture Thesaurus 2019d)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019d), [(Le Boeuf et al. 2015, sec. E41 Appellation)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Free Dictionary 2019a)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019a), [(Free Dictionary 2019f)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019f)|

---
</div>

<div class="hidden-content">
## Dataset Provider ID<br><br>**THIS NODE IS NOT DOCUMENTED YET IN THE TARGET MODEL**

|---|---|
|**Scope**|This field designates the unique identifying combination of alphanumeric characters assigned to an institution providing data in order to distinguish it from other such institutions (that which is recorded in the Providing Institution Appellation).|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|To be completed|
|**Full Path**|<span class="full-path">To be completed</span>|
|**Target Model View(s)**|To be completed|
|**Semantic Valuation**|*Low*:<br><br>*Medium*:<br><br>*High*:|
|**Typical Case(s)**|Ingenium is assigned the Dataset Provider ID “5677342” by CHIN.|
|**Edge Case(s)**|A single institution might have two distinct databases that would be unconnected and thus two Dataset Provider IDs with a single Dataset Provider Appellation.<br><br>A single institution might have more than a single Dataset Provider Appellation as well and, in this case, CHIN would have to determine which one it will use. For example, a dataset coming from the “Canada Science and Technology Museum” (Dataset Provider Appellation) could also be considered to come from “Ingenium” (Dataset Provider Appellation).<br><br>Museums can be considered Actors just as much as Dataset Providers so that where to apply annotations and curatorial notes might be tricky in specific cases such as changes that were brought to the name (e.g. Ingenium), etc. For example, if Ingenium provided datasets prior to 2018 under their previous Appellation “Canada Science and Technology Museum Corporation” and are now providing under “Ingenium” CHIN will have to determine which Dataset Provider Appellation to use for a single ID, whether to have to Dataset Provider Appellations (each linked to a Dataset Provider ID) or when to use which Dataset Provider Appellation with the single Dataset Provider ID, as well as how to display that information.|
|**Value Origin(s)**|Actors Checklist: Dataset Provider ID: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|This ID is generated and administered by CHIN.|
|**Reference(s)**|[(Art & Architecture Thesaurus 2019c)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019c), [(Art & Architecture Thesaurus 2019k)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019k), [(Bekiari et al. 2015, sec. F13 Identifier)](/collections-model/semantic-paths-specification/current/bibliography#bekiari-et-al-2015), [(Wikipedia 2019d)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019d), [(Wikipedia 2019ac)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019ac)|

---
</div>

## Death/Dissolution Date Begin

|---|---|
|**Scope**|This field designates the earliest temporal instant of the actor/entity’s permanent cessation of all sustaining biological or organizational functions (i.e. for organizations, formal or informal dismissal of the partnership and all matters pertaining to it).|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|E39\_Actor|
|**Full Path**|<span class="full-path">crm:E21\_Person -\> crm:P100i\_died\_in -\> crm:E69\_Death -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82a\_begin\_of\_the\_begin -\> xsd:dateTime<br><br>crm:E74\_Group -\> crm:P99i\_was\_dissolved\_by -\> crm:E68\_Dissolution -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82a\_begin\_of\_the\_begin -\> **xsd:dateTime**</span>|
|**Target Model View(s)**|[Birth/Death of People and Formation/Dissolution of Groups](https://chin-rcip.github.io/collections-model/target-model/current/life-events#birthdeath-of-people-and-formationdissolution-of-groups)|
|**Semantic Valuation**|*Low*: The value provided temporalizes the beginning of the event, but this information cannot be automatically extracted and formatted.<br><br>*Medium*: The date can be automatically extracted from the value provided (and from textual content that surrounds it if applicable) and can be formatted using the YYYY-MM-DD convention.<br>Accepted Value Type(s): String<br><br>*High*: The date is the sole value provided and is formatted using the date convention.<br>Accepted Value Type(s): DateTime (YYYY-MM-DDThh:mm:ss)|
|**Typical Case(s)**|Jackson Beardy (Actor Appellation) died on 1984-12-07 (Death/Dissolution Date Begin) “CE” (Death/Dissolution Date Begin Qualifier).<br><br>“Florence Carlyle” (Actor Appellation) died in 1923, which could be indicated as “1923” (Death/Dissolution Date Begin) or “after” (Death/Dissolution Date Begin Qualifier) “1922-12-31” (Death/Dissolution Date End) and “before” (Death/Dissolution Date End Qualifier) “1924-01-01” (Death/Dissolution Date End).|
|**Edge Case(s)**|The “Abitibi Power and Paper Company” (Actor Appellation) was acquired by Price Brothers in 1974 (Death/Dissolution Date Begin) “CE” (Death/Dissolution Date Begin Qualifier). Price Brothers (Actor Appellation) was then merged with Stone Consolidated (Actor Appellation) in 1997 (Death/Dissolution Date Begin), which was in turn merged with Bowater (Actor Appellation) to form AbitibiBowater (Actor Appellation) in 2007 (Death/Dissolution Date Begin), now known under Resolute Forest Products (Actor Appellation). In the case of such mergers and acquisitions, what would be considered to be the dissolution of the company is unclear.<br><br>Considering this is a date field, how would an actor that is known to be dead but for which there is no associated date of death be accounted for here? In other words, how do we differentiate between someone that is *not dead*and someone who *is dead*but we do not know when?<br><br>Numerical entering of dates might be misleading. For example, 06-12-45 might refer to June 12th, 1845 just as much as December 6th, 1945.<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Death/Dissolution Date Begin: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|CHIN recommends using the following format when entering dates: “YYYY-MM-DD HH:MM:SS”. However, if the data cannot be converted to such a format (such as in the case of an era), a string can be used (e.g. Han Dynasty).|
|**Reference(s)**|[(Art & Architecture Thesaurus 2019u)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019u), [(Art & Architecture Thesaurus 2019v)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019v), [(Le Boeuf et al. 2015, sec. E68 Dissolution)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Le Boeuf et al. 2015, sec. E69 Death)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Free Dictionary 2019v)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019v), [(Free Dictionary 2019w)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019w), [(Wikipedia 2019g)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019g), [(Wikipedia 2019y)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019y)|

---

## Death/Dissolution Date Begin Qualifier

|---|---|
|**Scope**|This field qualifies the earliest temporal instant of the actor/entity’s permanent cessation of all sustaining biological or organizational functions (i.e. for organizations, formal or informal dismissal of the partnership and all matters pertaining to it).|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Death/Dissolution Date Begin](#deathdissolution-date-begin)|
|**Full Path**|<span class="full-path">crm:E21\_Person -\> crm:P100i\_died\_in -\> crm:E69\_Death -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P79\_beginning\_is\_qualified\_by -\> xsd:string<br><br>crm:E74\_Group -\> crm:P99i\_was\_dissolved\_by -\> crm:E68\_Dissolution -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P79\_beginning\_is\_qualified\_by -\> **xsd:string**</span>|
|**Target Model View(s)**|[Birth/Death of People and Formation/Dissolution of Groups](https://chin-rcip.github.io/collections-model/target-model/current/life-events#birthdeath-of-people-and-formationdissolution-of-groups)|
|**Semantic Valuation**|*Low*: The value provided qualifies the date of the event, but this information is unstructured and cannot be automatically formatted.<br><br>*Medium*: The value provided qualifies the date of the event and can be (semi-)automatically cleaned and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String<br><br>*High*: The qualifier is the sole value provided and is structured and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String|
|**Typical Case(s)**|Jackson Beardy (Actor Appellation) died on 1984-12-07 (Death/Dissolution Date Begin) “CE” (Death/Dissolution Date Begin Qualifier).<br><br>“Florence Carlyle” (Actor Appellation) died in 1923, which could be indicated as “1923” (Death/Dissolution Date Begin) or “after” (Death/Dissolution Date Begin Qualifier) “1922-12-31” (Death/Dissolution Date End) and “before” (Death/Dissolution Date End Qualifier) “1924-01-01” (Death/Dissolution Date End).|
|**Edge Case(s)**|There might be cases where the Death/Dissolution Date Begin and the Death/Dissolution Date Begin Qualifier would be the same, in particular when it comes to eras. For example, “Victorian Era” can be both the Death/Dissolution Date Begin and the Death/Dissolution Date Begin Qualifier. Determining what eras the qualifiers will entail (through the vocabulary used to handle them) will thus be paramount.<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Death/Dissolution Date Begin Qualifier: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|There can be more than one qualifier at once for a single Death/Dissolution Date Begin (e.g. “BCE” and “BC”, which is the same information, the former being qualified using the non-christian acronym for “Before Common Era” and the latter using the christian “Before Christ”).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020), [(Wikipedia 2019o)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019o), [(Wikipedia 2019r)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019r), [(Wikipedia 2019w)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019w)|

---

## Death/Dissolution Date End

|---|---|
|**Scope**|This field designates the latest temporal instant of the actor/entity’s permanent cessation of all sustaining biological or organizational functions (i.e. for organizations, formal or informal dismissal of the partnership and all matters pertaining to it).|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|E39\_Actor|
|**Full Path**|<span class="full-path">crm:E21\_Person -\> crm:P100i\_died\_in -\> crm:E69\_Death -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82b\_end\_of\_the\_end -\> xsd:dateTime<br><br>crm:E74\_Group -\> crm:P99i\_was\_dissolved\_by -\> crm:E68\_Dissolution -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82b\_end\_of\_the\_end -\> **xsd:dateTime**</span>|
|**Target Model View(s)**|[Birth/Death of People and Formation/Dissolution of Groups](https://chin-rcip.github.io/collections-model/target-model/current/life-events#birthdeath-of-people-and-formationdissolution-of-groups)|
|**Semantic Valuation**|*Low*: The value provided temporalizes the beginning of the event, but this information cannot be automatically extracted and formatted.<br><br>*Medium*: The date can be automatically extracted from the value provided (and from textual content that surrounds it if applicable) and can be formatted using the YYYY-MM-DD convention.<br>Accepted Value Type(s): String<br><br>*High*: The date is the sole value provided and is formatted using the date convention.<br>Accepted Value Type(s): DateTime (YYYY-MM-DDThh:mm:ss)|
|**Typical Case(s)**|To Come|
|**Edge Case(s)**|Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Death/Dissolution Date End: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|CHIN recommends using the following format when entering dates: “YYYY-MM-DD HH:MM:SS”. However, if the data cannot be converted to such a format (such as in the case of an era), a string can be used (e.g. Han Dynasty).|
|**Reference(s)**|[(Art & Architecture Thesaurus 2019u)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019u), [(Art & Architecture Thesaurus 2019v)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019v), [(Le Boeuf et al. 2015, sec. E68 Dissolution)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Le Boeuf et al. 2015, sec. E69 Death)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Free Dictionary 2019v)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019v), [(Free Dictionary 2019w)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019w), [(Wikipedia 2019g)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019g), [(Wikipedia 2019y)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019y)|

---

## Death/Dissolution Date End Qualifier

|---|---|
|**Scope**|This field qualifies the latest temporal instant of the actor/entity’s permanent cessation of all sustaining biological or organizational functions (i.e. for organizations, formal or informal dismissal of the partnership and all matters pertaining to it).|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Death/Dissolution Date End](#deathdissolution-date-end)|
|**Full Path**|<span class="full-path">crm:E21\_Person -\> crm:P100i\_died\_in -\> crm:E69\_Death -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P80\_end\_is\_qualified\_by -\> xsd:string<br><br>crm:E74\_Group -\> crm:P99i\_was\_dissolved\_by -\> crm:E68\_Dissolution -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P80\_end\_is\_qualified\_by -\> **xsd:string**</span>|
|**Target Model View(s)**|[Birth/Death of People and Formation/Dissolution of Groups](https://chin-rcip.github.io/collections-model/target-model/current/life-events#birthdeath-of-people-and-formationdissolution-of-groups)|
|**Semantic Valuation**|*Low*: The value provided qualifies the date of the event, but this information is unstructured and cannot be automatically formatted.<br><br>*Medium*: The value provided qualifies the date of the event and can be (semi-)automatically cleaned and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String<br><br>*High*: The qualifier is the sole value provided and is structured and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String|
|**Typical Case(s)**|To Come|
|**Edge Case(s)**|Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Death/Dissolution Date End Qualifier: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|There can be more than one qualifier at once for a single Death/Dissolution Date End (e.g. “BCE” and “BC”, which is the same information, the former being qualified using the non-christian acronym for “Before Common Era” and the latter using the christian “Before Christ”).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020), [(Wikipedia 2019o)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019o), [(Wikipedia 2019r)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019r), [(Wikipedia 2019w)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019w)|

---

## Death/Dissolution Place

|---|---|
|**Scope**|This field identifies the location of the actor/entity’s permanent cessation of all sustaining biological or organizational functions (i.e. for organizations, formal or informal dismissal of the partnership and all matters pertaining to it).|
|**Generated Bond(s)**|E53\_Place|
|**Dependency(ies)**|E39\_Actor|
|**Full Path**|<span class="full-path">crm:E21\_Person -\> crm:P100i\_died\_in -\> crm:E69\_Death -\> crm:P7\_took\_place\_at -\> crm:E53\_Place<br><br>crm:E74\_Group -\> crm:P99i\_was\_dissolved\_by -\> crm:E68\_Dissolution -\> crm:P7\_took\_place\_at -\> **crm:E53\_Place**</span>|
|**Target Model View(s)**|[Birth/Death of People and Formation/Dissolution of Groups](https://chin-rcip.github.io/collections-model/target-model/current/life-events#birthdeath-of-people-and-formationdissolution-of-groups)|
|**Semantic Valuation**|*Low*: The value provided is a string that cannot be parsed automatically by reconciliation tools but still contains the required information.<br><br>*Medium*: The value provided is a string that can be automatically cleaned and reconciled using controlled vocabularies specified by CHIN. In the event that the value is adequately structured but does not reconcile with any terms from the controlled vocabulary, and provided that it is deemed relevant, CHIN will add the term to the vocabulary.<br>Accepted Value Type(s): String<br><br>*High*: The provided value is a string that can be automatically reconciled with the controlled vocabularies specified by CHIN.<br>Accepted Value Type(s): String, URI|
|**Typical Case(s)**|To Come|
|**Edge Case(s)**|Just for the Birth/Formation Place, the death of an Actor happening in their childhood home could be considered an Annotation on the Death/Dissolution Place or a Death/Dissolution Place in and of itself.<br><br>A group might not have a single Dissolution Place as its members can consider themselves part of a collective without sharing a common space. Alternatively, this poses the question of whether an online meeting space is considered to be a Place.|
|**Value Origin(s)**|Actors Checklist: Death/Dissolution Place: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|This field accommodates all forms of modern and historical locations, physical features, or nations, on Earth or not.|
|**Reference(s)**|[(Le Boeuf et al. 2015, sec. E53 Place)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Bekiari et al. 2015, sec. F9 Place)](/collections-model/semantic-paths-specification/current/bibliography#bekiari-et-al-2015), [(Free Dictionary 2019m)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019m), [(Free Dictionary 2019n)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019n), [(Thesaurus of Geographic Names 2019)](/collections-model/semantic-paths-specification/current/bibliography#thesaurus-of-geographic-names-2019), [(Wikipedia 2019am)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019am)|

---

## Dissolving Actor Appellation

|---|---|
|**Scope**|This field designates the entire identifying word(s), number(s), symbol(s) or code(s) by which a group’s main agent in charge of or responsible for the group’s dissolution is distinguished from others, such as the name, title, or designation as it has been attributed by a contributing institution. Their appellation is an identifying agreed upon term that is descriptive or connotative. If it is made of the concatenation of numerous parts, it should include all of them (such as honorifics, titles, etc.).|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|E74\_Group|
|**Full Path**|<span class="full-path">crm:E74\_Group -\> crm:P99i\_was\_dissolved\_by -\> crm:E68\_Dissolution -\> crm:P14\_carried\_out\_by -\> crm:E39\_Actor -\> crm:P1\_is\_identified\_by -\> crm:E41\_Appellation + crm:E33\_Linguistic\_Object -\> crm:P190\_has\_symbolic\_content -\> **xsd:string**</span>|
|**Target Model View(s)**|[Birth/Death of People and Formation/Dissolution of Groups](https://chin-rcip.github.io/collections-model/target-model/current/life-events#birthdeath-of-people-and-formationdissolution-of-groups)|
|**Semantic Valuation**|*Low*: The provided values contain unstructured information of the appellation, such as it cannot be parsed automatically by reconciliation tools, but still contains the required information.<br><br>*Medium*: The provided values contain structured information that can be automatically cleaned and reconciled with other entities in other datasets.<br>Accepted Value Type(s): String<br><br>*High*: The provided values only contain structured information that can be automatically reconciled with other entities in other datasets.<br>Accepted Value Type(s): String|
|**Typical Case(s)**|“James M. Morgan” (Dissolving Actor Appellation) was the CEO of Atari (Group Appellation) from 1983 until its dissolution in July 1984 (Death/Dissolution Date Begin).<br><br>Painters Eleven was a Torontonian artists group that emerged in the 1950s and was composed of Jack Bush, Oscar Cahén, Hortense Gordon, Thomas Hodgson, Alexandra Luke, J.W.G. ("Jock") Macdonald, Ray Mead, Kazuo Nakamura, William Ronald, Harold Town, and Walter Yarwood. Following the death of Cahén, the move of Mead to Montréal and the resignation of Ronald, the nine remaining artists decided to disband (Jack Bush, Dissolving Actor Appellation; Hortense Gordon, Dissolving Actor Appellation; Thomas Hodgson, Dissolving Actor Appellation; Alexandra Luke, Dissolving Actor Appellation; J.W.G. ("Jock") Macdonald, Dissolving Actor Appellation; Kazuo Nakamura, Dissolving Actor Appellation; Harold Townand, Dissolving Actor Appellation; Walter Yarwood, Dissolving Actor Appellation).|
|**Edge Case(s)**|CIDOC CRM’s scope note indicates that it pertains to the dissolution of a Group. However, at the moment, companies can be classified as an Actor or a Group. For example, “James M. Morgan” (Dissolving Actor Appellation) was the CEO of Atari (Group/Actor Appellation) from 1983 until its dissolution in July 1984 (Death/Dissolution Date Begin).|
|**Value Origin(s)**|Actors Checklist: Dissolving Actor Appellation: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|TBD|
|**Reference(s)**|[(Art & Architecture Thesaurus 2019o)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019o), [(Free Dictionary 2019p)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019p), [(Wikipedia 2019c)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019c)|

---

## Father Appellation

|---|---|
|**Scope**|This field designates the entire identifying word(s), number(s), symbol(s) or code(s) by which an actor’s biological father is distinguished from others, such as the name, title, or designation as it has been attributed by a contributing institution. His appellation is an identifying agreed upon term that is descriptive or connotative. If it is made of the concatenation of numerous parts, it should include all of them (such as honorifics, titles, etc.).|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|E21\_Person|
|**Full Path**|<span class="full-path">crm:E21\_Person -\> crm:P98i\_was\_born -\> crm:E67\_Birth -\> crm:P97\_from\_father -\> crm:E21\_Person -\> crm:P1\_is\_identified\_by -\> crm:E41\_Appellation + crm:E33\_Linguistic\_Object -\> crm:P190\_has\_symbolic\_content -\> **xsd:string**</span>|
|**Target Model View(s)**|[Birth/Death of People and Formation/Dissolution of Groups](https://chin-rcip.github.io/collections-model/target-model/current/life-events#birthdeath-of-people-and-formationdissolution-of-groups)|
|**Semantic Valuation**|*Low*: The provided values contain unstructured information of the appellation, such as it cannot be parsed automatically by reconciliation tools, but still contains the required information.<br><br>*Medium*: The provided values contain structured information that can be automatically cleaned and reconciled with other entities in other datasets.<br>Accepted Value Type(s): String<br><br>*High*: The provided values only contain structured information that can be automatically reconciled with other entities in other datasets.<br>Accepted Value Type(s): String|
|**Typical Case(s)**|Diplomat “Peter Dale Scott” (Actor Appellation) was born to painter “Marian Mildred Dale Scott” (Mother Appellation) and poet and law professor “Francis Reginald Scott” (Father Appellation).<br><br>Painter “Emily Carr” (Actor Appellation) was born to “Emily (Saunders) Carr” (Mother Appellation) and Richard Carr (Father Appellation).|
|**Edge Case(s)**|To Come|
|**Value Origin(s)**|Actors Checklist: Father Appellation: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|A biological father is understood to be the male genetic contributor to the creation of the infant, through sexual intercourse or sperm donation.|
|**Reference(s)**|[(Art & Architecture Thesaurus 2019d)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019d), [(Art & Architecture Thesaurus 2019n)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019n), [(Le Boeuf et al. 2015, sec. E82 Actor Appellation)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Le Boeuf et al. 2015, sec. E41 Appellation)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Le Boeuf et al. 2015, sec. P97 from Father)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Free Dictionary 2019a)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019a), [(Free Dictionary 2019f)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019f), [(Free Dictionary 2019o)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019o), [(Wikipedia 2019ab)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019ab)|

---

## Final Disposition Place

|---|---|
|**Scope**|This field identifies the location where the deceased has been laid, usually following or in the context of funeral rites such as cremation, burial, or mummification.|
|**Generated Bond(s)**|E53\_Place|
|**Dependency(ies)**|E21\_Person|
|**Related SQN(s)**|Burial Place: Definition|
|**Full Path**|<span class="full-path">crm:E21\_Person -\> crm:P100i\_died\_in -\> crm:E69\_Death -\> crm:P120\_occurs\_before -\> crm:E9\_Move -\> crm:P26\_moved\_to -\> **crm:E53\_Place** (*-\> crm:P2\_has\_type -\> crm:E55\_Type\["Burial Place"\]*)</span>|
|**Target Model View(s)**|[Birth/Death of People and Formation/Dissolution of Groups](https://chin-rcip.github.io/collections-model/target-model/current/life-events#birthdeath-of-people-and-formationdissolution-of-groups)|
|**Semantic Valuation**|*Low*: The value provided is a string that cannot be parsed automatically by reconciliation tools but still contains the required information.<br><br>*Medium*: The value provided is a string that can be automatically cleaned and reconciled using controlled vocabularies specified by CHIN. In the event that the value is adequately structured but does not reconcile with any terms from the controlled vocabulary, and provided that it is deemed relevant, CHIN will add the term to the vocabulary.<br>Accepted Value Type(s): String<br><br>*High*: The provided value is a string that can be automatically reconciled with the controlled vocabularies specified by CHIN.<br>Accepted Value Type(s): String, URI|
|**Typical Case(s)**|“Emily Carr” (Actor Appellation) is buried in “Ross Bay Cemetery” (Final Disposition Place), “Victoria, British Columbia” (Final Disposition Place).<br><br>“…mile Nelligan” is buried in the “Notre-Dame-des-Neiges Cemetery in Montréal, QC” (Final Disposition Place).|
|**Edge Case(s)**|Uruguayan Air Force Flight 571 crashed on a glacier in the Andes on October 13, 1972. Over the 72 following days, many of the passengers and crew died and were either buried under the snow or eaten by the survivors who had no other source of sustenance. In such a case, can a group have a final disposition place considering the deceased were all buried in a single spot?|
|**Value Origin(s)**|Actors Checklist: Final Disposition Place: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|This field accommodates all forms of modern and historical locations, physical features, or nations, on Earth or not.<br><br>There can be more than one Final Disposition Place (e.g. a deceased’s ashes might have been laid in several locations).|
|**Reference(s)**|[(Le Boeuf et al. 2015, sec. E53 Place)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Bekiari et al. 2015, sec. F9 Place)](/collections-model/semantic-paths-specification/current/bibliography#bekiari-et-al-2015), [(Free Dictionary 2019m)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019m), [(Free Dictionary 2019n)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019n), [(Thesaurus of Geographic Names 2019)](/collections-model/semantic-paths-specification/current/bibliography#thesaurus-of-geographic-names-2019), [(Wikipedia 2019am)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019am)|

---

## Founding Actor Appellation

|---|---|
|**Scope**|This field designates the entire identifying word(s), number(s), symbol(s) or code(s) by which a group’s founder is distinguished from others, such as the name, title, or designation as it has been attributed by a contributing institution. Their appellation is an identifying agreed upon term that is descriptive or connotative. If it is made of the concatenation of numerous parts, it should include all of them (such as honorifics, titles, etc.).|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|E74\_Group|
|**Full Path**|<span class="full-path">crm:E74\_Group -\> crm:P95i\_was\_formed\_by -\> crm:E66\_Formation -\> crm:P14\_carried\_out\_by -\> crm:E21\_Person -\> crm:P1\_is\_identified\_by -\> crm:E41\_Appellation + crm:E33\_Linguistic\_Object -\> crm:P190\_has\_symbolic\_content -\> **xsd:string**</span>|
|**Target Model View(s)**|[Birth/Death of People and Formation/Dissolution of Groups](https://chin-rcip.github.io/collections-model/target-model/current/life-events#birthdeath-of-people-and-formationdissolution-of-groups)|
|**Semantic Valuation**|*Low*: The provided values contain unstructured information of the appellation, such as it cannot be parsed automatically by reconciliation tools, but still contains the required information.<br><br>*Medium*: The provided values contain structured information that can be automatically cleaned and reconciled with other entities in other datasets.<br>Accepted Value Type(s): String<br><br>*High*: The provided values only contain structured information that can be automatically reconciled with other entities in other datasets.<br>Accepted Value Type(s): String|
|**Typical Case(s)**|“Michael Audain” (Founding Actor Appellation) was one of the founders of the “British Columbia Civil Liberties Association” (Group Appellation).<br><br>“Jeffrey Raider” (Founding Actor Appellation), “Andrew Hunt” (Founding Actor Appellation), Neil Blumenthal” (Founding Actor Appellation), and “David Gilboa” (Founding Actor Appellation) founded “JAND Inc.” (Group Appellation) which does business as “Warby Parker” (Group Appellation) with Blumenthal and Gilboa acting as co-CEOs (Occupation Type).|
|**Edge Case(s)**|Collectives might have leaders without having official founders… in such a case, would all the initial members of the collective be considered a founder, would there be none, or would the main public figure/leader be considered to be the founder?|
|**Value Origin(s)**|Actors Checklist: Founding Actor Appellation: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|*See Issue \#16*<br><br>An institution’s founder is understood to be the person who establishes it.|
|**Reference(s)**|[(Art & Architecture Thesaurus 2019o)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019o), [(Free Dictionary 2019p)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019p), [(Wikipedia 2019c)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019c)|

---

## Flourishing Date Begin

|---|---|
|**Scope**|This field designates the earliest temporal instant of the actor’s period of highest productivity, excellence, or influence within a specific field thanks to having achieved full development or success.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|E39\_Actor|
|**Related SQN(s)**|Flourishing: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P11i\_participated\_in -\> crm:E5\_Event (*-\> crm:P2\_has\_type -\> crm:E55\_Type\["Flourishing"\]*) -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82a\_begin\_of\_the\_begin -\> **xsd:dateTime**</span>|
|**Target Model View(s)**|[Flourishing dates](https://chin-rcip.github.io/collections-model/target-model/current/life-events#flourishing-dates)|
|**Semantic Valuation**|*Low*: The value provided temporalizes the beginning of the event, but this information cannot be automatically extracted and formatted.<br><br>*Medium*: The date can be automatically extracted from the value provided (and from textual content that surrounds it if applicable) and can be formatted using the YYYY-MM-DD convention.<br>Accepted Value Type(s): String<br><br>*High*: The date is the sole value provided and is formatted using the date convention.<br>Accepted Value Type(s): DateTime (YYYY-MM-DDThh:mm:ss)|
|**Typical Case(s)**|Tom Thomson’s artistic peak is considered to run from March 1916 (Flourishing Date Begin “1916-03”) until his death in July 1917 (Flourishing Date End “1917-07-08”; Death Date Begin “1917-07-08”).|
|**Edge Case(s)**|There are three main cases where there could be more than a single flourishing for an artist: flourishing in different fields, flourishing in different mediums, and flourishings in a single field and medium interspersed by calmer periods of production. For example, Marc Séguin has had success both in visual and literary endeavours (and some would say cinematographic too). How would each of these flourishings be represented? Jean Paul Riopelle’s sculptural flourishing would be considered different than his painting one. If we do account for various flourishing periods, we would have to account for what distinguishes them and determine on what basis this differentiation occurs. Finally, an artist can have more than one important flourishings in a single domain with a long period of inactivity in between (e.g. Harper Lee).<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Flourishing Date Begin: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|CHIN recommends using the following format when entering dates: “YYYY-MM-DD HH:MM:SS”. However, if the data cannot be converted to such a format (such as in the case of an era), a string can be used (e.g. Han Dynasty).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020)|

---

## Flourishing Date Begin Qualifier

|---|---|
|**Scope**|This field qualifies the earliest temporal instant of the actor’s period of highest productivity, excellence, or influence within a specific field thanks to having achieved full development or success.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Flourishing Date Begin](#flourishing-date-begin)|
|**Related SQN(s)**|Flourishing: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P11i\_participated\_in -\> crm:E5\_Event (*-\> crm:P2\_has\_type -\> crm:E55\_Type\["Flourishing"\]*) -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P79\_beginning\_is\_qualified\_by -\> **xsd:string**</span>|
|**Target Model View(s)**|[Flourishing dates](https://chin-rcip.github.io/collections-model/target-model/current/life-events#flourishing-dates)|
|**Semantic Valuation**|*Low*: The value provided qualifies the date of the event, but this information is unstructured and cannot be automatically formatted.<br><br>*Medium*: The value provided qualifies the date of the event and can be (semi-)automatically cleaned and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String<br><br>*High*: The qualifier is the sole value provided and is structured and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String|
|**Typical Case(s)**|Tom Thomson’s artistic peak is considered to run from March 1916 (Flourishing Date Begin “1916-03”) “CE” (Flourishing Date Begin Qualifier) until his death in July 1917 (Flourishing Date End “1917-07-08”; Death Date Begin “1917-07-08”) “CE” (Flourishing Date End Qualifier).|
|**Edge Case(s)**|There might be cases where the Flourishing Date Begin and the Flourishing Date Begin Qualifier would be the same, in particular when it comes to eras. For example, “Victorian Era” can be both the Flourishing Date Begin and the Flourishing Date Begin Qualifier. Determining what eras the qualifiers will entail (through the vocabulary used to handle them) will thus be paramount.<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Flourishing Date Begin Qualifier: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|There can be more than one qualifier at once for a single Flourishing Date Begin (e.g. “BCE” and “BC”, which is the same information, the former being qualified using the non-christian acronym for “Before Common Era” and the latter using the christian “Before Christ”).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020), [(Wikipedia 2019o)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019o), [(Wikipedia 2019r)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019r), [(Wikipedia 2019w)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019w)|

---

## Flourishing Date End

|---|---|
|**Scope**|This field designates the latest temporal instant of the actor’s period of highest productivity, excellence, or influence within a specific field thanks to having achieved full development or success.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|E39\_Actor|
|**Related SQN(s)**|Flourishing: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P11i\_participated\_in -\> crm:E5\_Event (*-\> crm:P2\_has\_type -\> crm:E55\_Type\["Flourishing"\]*) -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82b\_end\_of\_the\_end -\> **xsd:dateTime**</span>|
|**Target Model View(s)**|[Flourishing dates](https://chin-rcip.github.io/collections-model/target-model/current/life-events#flourishing-dates)|
|**Semantic Valuation**|*Low*: The value provided temporalizes the beginning of the event, but this information cannot be automatically extracted and formatted.<br><br>*Medium*: The date can be automatically extracted from the value provided (and from textual content that surrounds it if applicable) and can be formatted using the YYYY-MM-DD convention.<br>Accepted Value Type(s): String<br><br>*High*: The date is the sole value provided and is formatted using the date convention.<br>Accepted Value Type(s): DateTime (YYYY-MM-DDThh:mm:ss)|
|**Typical Case(s)**|Tom Thomson’s artistic peak is considered to run from March 1916 (Flourishing Date Begin “1916-03”) until his death in July 1917 (Flourishing Date End “1917-07-08”; Death Date Begin “1917-07-08”).|
|**Edge Case(s)**|There are three main cases where there could be more than a single flourishing for an artist: flourishing in different fields, flourishing in different mediums, and flourishings in a single field and medium interspersed by calmer periods of production. For example, Marc Séguin has had success both in visual and literary endeavours (and some would say cinematographic too). How would each of these flourishings be represented? Jean Paul Riopelle’s sculptural flourishing would be considered different than his painting one. If we do account for various flourishing periods, we would have to account for what distinguishes them and determine on what basis this differentiation occurs. Finally, an artist can have more than one important flourishings in a single domain with a long period of inactivity in between (e.g. Harper Lee).<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Flourishing Date End: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|CHIN recommends using the following format when entering dates: “YYYY-MM-DD HH:MM:SS”. However, if the data cannot be converted to such a format (such as in the case of an era), a string can be used (e.g. Han Dynasty).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020)|

---

## Flourishing Date End Qualifier

|---|---|
|**Scope**|This field qualifies the latest temporal instant of the actor’s period of highest productivity, excellence, or influence within a specific field thanks to having achieved full development or success.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Flourishing Date End](#flourishing-date-end)|
|**Related SQN(s)**|Flourishing: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P11i\_participated\_in -\> crm:E5\_Event (*-\> crm:P2\_has\_type -\> crm:E55\_Type\["Flourishing"\]*) -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P80\_end\_is\_qualified\_by -\> **xsd:string**</span>|
|**Target Model View(s)**|[Flourishing dates](https://chin-rcip.github.io/collections-model/target-model/current/life-events#flourishing-dates)|
|**Semantic Valuation**|*Low*: The value provided qualifies the date of the event, but this information is unstructured and cannot be automatically formatted.<br><br>*Medium*: The value provided qualifies the date of the event and can be (semi-)automatically cleaned and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String<br><br>*High*: The qualifier is the sole value provided and is structured and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String|
|**Typical Case(s)**|Tom Thomson’s artistic peak is considered to run from March 1916 (Flourishing Date Begin “1916-03”) “CE” (Flourishing Date Begin Qualifier) until his death in July 1917 (Flourishing Date End “1917-07-08”; Death Date Begin “1917-07-08”) “CE” (Flourishing Date End Qualifier).|
|**Edge Case(s)**|There might be cases where the Flourishing Date End and the Flourishing Date End Qualifier would be the same, in particular when it comes to eras. For example, “Victorian Era” can be both the Flourishing Date End and the Flourishing Date End Qualifier. Determining what eras the qualifiers will entail (through the vocabulary used to handle them) will thus be paramount.<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Flourishing Date End Qualifier: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|There can be more than one qualifier at once for a single Flourishing Date End (e.g. “BCE” and “BC”, which is the same information, the former being qualified using the non-christian acronym for “Before Common Era” and the latter using the christian “Before Christ”).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020), [(Wikipedia 2019o)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019o), [(Wikipedia 2019r)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019r), [(Wikipedia 2019w)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019w)|

---

## Flourishing Place

|---|---|
|**Scope**|This field identifies the location(s) in which the actor had their period of highest productivity, excellence, or influence within a specific field thanks to having achieved full development or success.|
|**Generated Bond(s)**|E53\_Place|
|**Dependency(ies)**|E39\_Actor|
|**Related SQN(s)**|Flourishing: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P11i\_participated\_in -\> crm:E5\_Event (*-\> crm:P2\_has\_type -\> crm:E55\_Type\["Flourishing"\]*) -\> crm:P7\_took\_place\_at -\> **crm:E53\_Place**</span>|
|**Target Model View(s)**|[Flourishing dates](https://chin-rcip.github.io/collections-model/target-model/current/life-events#flourishing-dates)|
|**Semantic Valuation**|*Low*: The value provided is a string that cannot be parsed automatically by reconciliation tools but still contains the required information.<br><br>*Medium*: The value provided is a string that can be automatically cleaned and reconciled using controlled vocabularies specified by CHIN. In the event that the value is adequately structured but does not reconcile with any terms from the controlled vocabulary, and provided that it is deemed relevant, CHIN will add the term to the vocabulary.<br>Accepted Value Type(s): String<br><br>*High*: The provided value is a string that can be automatically reconciled with the controlled vocabularies specified by CHIN.<br>Accepted Value Type(s): String, URI|
|**Typical Case(s)**|Tom Thomson’s artistic peak is considered to run from March 1916 (Flourishing Date Begin “1916-03”) until his death in July 1917 (Flourishing Date End “1917-07-08”; Death Date Begin “1917-07-08”). During this period, Thomson mostly painted the “Ontario” (Flourishing Place) landscape as he travelled across the province .|
|**Edge Case(s)**|An actor might not have a single Flourishing Place or have a virtual one. For example, this poses the question of whether an online meeting space is considered to be a Place. For example, would members of the Nettime mailing list be considered to be part of a group which would have the “nettime.org” Flourishing Place?|
|**Value Origin(s)**|Actors Checklist: Flourishing Date Place: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|This field accommodates all forms of modern and historical locations, physical features, or nations, on Earth or not.<br><br>A single Flourishing can be linked to several Flourishing places.|
|**Reference(s)**|[(Le Boeuf et al. 2015, sec. E53 Place)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Bekiari et al. 2015, sec. F9 Place)](/collections-model/semantic-paths-specification/current/bibliography#bekiari-et-al-2015), [(Free Dictionary 2019m)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019m), [(Free Dictionary 2019n)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019n), [(Thesaurus of Geographic Names 2019)](/collections-model/semantic-paths-specification/current/bibliography#thesaurus-of-geographic-names-2019), [(Wikipedia 2019am)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019am)|

---

## Gender Type

|---|---|
|**Scope**|This field documents the cultural gender (not the biological one) that a person identifies as. As a socio-cultural concept it refers to a state or condition associated with a range of characteristics having to do with a person’s behaviour, mannerisms, interests, and appearance, and the way they are associated with gendered categories in a particular cultural context.|
|**Generated Bond(s)**|E55\_Type|
|**Dependency(ies)**|E21\_Person|
|**Related SQN(s)**|Gender: Definition|
|**Full Path**|<span class="full-path">crm:E21\_Person -\> crm:P2\_has\_type -\> **crm:E55\_Type** (*-\> crm:P2\_has\_type -\> crm:E55\_Type \["Gender"\]*)</span>|
|**Target Model View(s)**|[Rendering Gender and Cultural Affiliation with E55 Type](https://chin-rcip.github.io/collections-model/target-model/current/identification#rendering-gender-and-cultural-affiliation-with-e55-type)|
|**Semantic Valuation**|*Low*: The value provided is a string that cannot be parsed automatically by reconciliation tools but still contains the required information.<br><br>*Medium*: The value provided is a string that can be automatically cleaned and reconciled using controlled vocabularies specified by CHIN. In the event that the value is adequately structured but does not reconcile with any terms from the controlled vocabulary, and provided that it is deemed relevant, CHIN will add the term to the vocabulary.<br>Accepted Value Type(s): String<br><br>*High*: The provided value is a string that can be automatically reconciled with the controlled vocabularies specified by CHIN.<br>Accepted Value Type(s): String, URI|
|**Typical Case(s)**|“Edward Burtynsky” (Actor Appellation) is a “cisgender male” (Gender Type) “Canadian” (Nationality) “photographer” (Occupation Type).|
|**Edge Case(s)**|Zahele Muholi wants to be addressed using the pronoun “they” but has not specified a gender position. In such cases where the use of the pronoun can be attributable to gender fluidity as well as activism, what information should be entered in the Gender Type field is unclear.|
|**Value Origin(s)**|Actors Checklist: Gender Type: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|*May need to find another vocab for this. AAT & Wikidata do not capture gender in great accuracy.*<br><br>*AAT: Separates sex and gender, but groups gender by age (“men” and “boys”) with minimal options for non-cisgender identities.*<br><br>*Wikidata: Somewhat conflates sex and gender, but at least has options for transgender individuals, intersex, two-spirit, etc.*|
|**Reference(s)**|[(Art & Architecture Thesaurus 2019i)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019i), [(Wikipedia 2019q)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019q), [(Wikipedia 2019v)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019v)|

---

## Group Appellation

|---|---|
|**Scope**|This field designates the entire identifying word(s), number(s), symbol(s) or code(s) by which a group (formal or informal) is distinguished from others, such as its name, title, or designation as it has been attributed by a contributing institution. It is an identifying agreed upon term that is descriptive or connotative. If it is made of the concatenation of numerous parts, it should include all of them (such as honorifics, titles, etc.).|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|E39\_Actor|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P143i\_was\_joined\_by -\> crm:E85\_Joining -\> crm:P01i\_is\_domain\_of -\> crm:PC144\_joined\_with -\> crm:P02\_has\_range -\> crm:E74\_Group -\> crm:P1\_is\_identified\_by -\> crm:E41\_Appellation + crm:E33\_Linguistic\_Object -\> crm:P190\_has\_symbolic\_content -\> xsd:string<br><br>crm:E39\_Actor -\> crm:P145i\_left\_by -\> crm:E86\_Leaving -\> crm:P146\_separated\_from -\> crm:E74\_Group -\> rdfs:label -\> **xsd:string**</span>|
|**Target Model View(s)**|[Group Belonging](https://chin-rcip.github.io/collections-model/target-model/current/social-bonds#group-belonging)|
|**Semantic Valuation**|*Low*: The provided values contain unstructured information of the appellation, such as it cannot be parsed automatically by reconciliation tools, but still contains the required information.<br><br>*Medium*: The provided values contain structured information that can be automatically cleaned and reconciled with other entities in other datasets.<br>Accepted Value Type(s): String<br><br>*High*: The provided values only contain structured information that can be automatically reconciled with other entities in other datasets.<br>Accepted Value Type(s): String|
|**Typical Case(s)**|“Painters Eleven” (Group Appellation) was a Torontonian artists group that emerged in the 1950s (Group Joining Date Begin) and was composed of Jack Bush, Oscar Cahén, Hortense Gordon, Thomas Hodgson, Alexandra Luke, J.W.G. ("Jock") Macdonald, Ray Mead, Kazuo Nakamura, William Ronald, Harold Town, and Walter Yarwood.|
|**Edge Case(s)**|Whether to classify artistic collectives (e.g. Gilbert & George, BGL, etc.) as an organisation (using an Actor Appellation) or a group (using a Group Appellation) has not yet been determined. Provided the collective considers itself to be an autonomous artistic entity, it would not suit a Group Appellation considering Group belonging revolves around the multiplicity of entities. The same would apply for trios, etc. (e.g. BGL) as long as the “group” considers itself to be a single autonomous creator. For example, should BGL be recorded under Actor Appellation with the Actor Appellation Types “Acronym” and “Brand Name” (which begs the question: do we allow more than one type on a single Actor Appellation) or under Group Appellation with the members being recorded as Actors with the Actor Appellations “Jasmin Bilodeau”, “Sébastien Giguère”, and “Nicolas Laverdière”? Pseudonyms might also be used to refer to groups/duos, such as in the cas of “0100101110101101.ORG”, a collective constituted of Eva and Franco Mattes.<br><br>Certain groups are comprised of members that are entirely anonymous. Should such groups be recorded under Actor Appellation (or will CHIN convert them accordingly?). For example, the Guerilla Girls are an art collective whose members are shifting and wish to remain entirely anonymous.|
|**Value Origin(s)**|Actors Checklist: Group Appellation: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|A group is considered to be two or more people who interact with one another and who/whose work share(s) similar characteristics sufficient to invest them with a sense of unity, common endeavour/objective and/or consolidating relationship.|
|**Reference(s)**|[(Art & Architecture Thesaurus 2019t)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019t), [(Art & Architecture Thesaurus 2019x)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019x), [(Le Boeuf et al. 2015, sec. E74 Group)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Free Dictionary 2019z)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019z), [(Free Dictionary 2019af)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019af), [(Wikipedia 2019ak)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019ak), [(Wikipedia 2019an)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019an), [(Wikipedia 2019ap)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019ap)|

---

## Group Joining Date Begin

|---|---|
|**Scope**|This field designates the earliest temporal instant the actor became, formally or informally, a member of the Group.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Group Appellation](#group-appellation)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P143i\_was\_joined\_by -\> crm:E85\_Joining -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82a\_begin\_of\_the\_begin -\> **xsd:dateTime**</span>|
|**Target Model View(s)**|[Group Belonging](https://chin-rcip.github.io/collections-model/target-model/current/social-bonds#group-belonging)|
|**Semantic Valuation**|*Low*: The value provided temporalizes the beginning of the event, but this information cannot be automatically extracted and formatted.<br><br>*Medium*: The date can be automatically extracted from the value provided (and from textual content that surrounds it if applicable) and can be formatted using the YYYY-MM-DD convention.<br>Accepted Value Type(s): String<br><br>*High*: The date is the sole value provided and is formatted using the date convention.<br>Accepted Value Type(s): DateTime (YYYY-MM-DDThh:mm:ss)|
|**Typical Case(s)**|“Painters Eleven” (Group Appellation) was a Torontonian artists group that emerged in the 1950s (Group Joining Date Begin) and was composed of Jack Bush (Actor Appellation), Oscar Cahén (Actor Appellation), Hortense Gordon (Actor Appellation), Thomas Hodgson (Actor Appellation), Alexandra Luke (Actor Appellation), J.W.G. ("Jock") Macdonald (Actor Appellation), Ray Mead (Actor Appellation), Kazuo Nakamura (Actor Appellation), William Ronald (Actor Appellation), Harold Town (Actor Appellation), and Walter Yarwood (Actor Appellation).|
|**Edge Case(s)**|The “Abitibi Power and Paper Company” was acquired by Price Brothers in 1974. Price Brothers was then merged with Stone Consolidated in 1997, which was in turn merged with Bowater to form AbitibiBowater in 2007, now known under Resolute Forest Products. In the case of such mergers and acquisitions, what would be considered to be the leaving of a group and the joining of another, when the dissolution of the company itself is up for debate, would be unclear.<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Group Joining Date Begin: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|CHIN recommends using the following format when entering dates: “YYYY-MM-DD HH:MM:SS”. However, if the data cannot be converted to such a format (such as in the case of an era), a string can be used (e.g. Han Dynasty).|
|**Reference(s)**|[(Le Boeuf et al. 2015, sec. E85 Joining)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Free Dictionary 2019aa)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019aa)|

---

## Group Joining Date Begin Qualifier

|---|---|
|**Scope**|This field qualifies the earliest temporal instant the actor became, formally or informally, a member of the group.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Group Joining Date Begin](#group-joining-date-begin)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P143i\_was\_joined\_by -\> crm:E85\_Joining -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P79\_beginning\_is\_qualified\_by -\> **xsd:string**</span>|
|**Target Model View(s)**|[Group Belonging](https://chin-rcip.github.io/collections-model/target-model/current/social-bonds#group-belonging)|
|**Semantic Valuation**|*Low*: The value provided qualifies the date of the event, but this information is unstructured and cannot be automatically formatted.<br><br>*Medium*: The value provided qualifies the date of the event and can be (semi-)automatically cleaned and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String<br><br>*High*: The qualifier is the sole value provided and is structured and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String|
|**Typical Case(s)**|“Painters Eleven” (Group Appellation) was a Torontonian artists group that emerged “after” (Group Joining Date Begin Qualifier) 1949 (Group Joining Date Begin) and “before” (Group Joining Date End Qualifier) 1960 (Group Joining Date End). It was composed of Jack Bush (Actor Appellation), Oscar Cahén (Actor Appellation), Hortense Gordon (Actor Appellation), Thomas Hodgson (Actor Appellation), Alexandra Luke (Actor Appellation), J.W.G. ("Jock") Macdonald (Actor Appellation), Ray Mead (Actor Appellation), Kazuo Nakamura (Actor Appellation), William Ronald (Actor Appellation), Harold Town (Actor Appellation), and Walter Yarwood (Actor Appellation).|
|**Edge Case(s)**|There might be cases where the Group Joining Date Begin and the Group Joining Date Begin Qualifier would be the same, in particular when it comes to eras. For example, “Victorian Era” can be both the Group Joining Date Begin and the Group Joining Date Begin Qualifier. Determining what eras the qualifiers will entail (through the vocabulary used to handle them) will thus be paramount.<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Group Joining Date Begin Qualifier: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|There can be more than one qualifier at once for a single Joining Date Begin (e.g. “BCE” and “BC”, which is the same information, the former being qualified using the non-christian acronym for “Before Common Era” and the latter using the christian “Before Christ”).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020), [(Wikipedia 2019o)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019o), [(Wikipedia 2019r)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019r), [(Wikipedia 2019w)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019w)|

---

## Group Joining Date End

|---|---|
|**Scope**|This field designates the latest temporal instant the actor became, formally or informally, a member of the Group.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Group Appellation](#group-appellation)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P143i\_was\_joined\_by -\> crm:E85\_Joining -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82b\_end\_of\_the\_end -\> **xsd:dateTime**</span>|
|**Target Model View(s)**|[Group Belonging](https://chin-rcip.github.io/collections-model/target-model/current/social-bonds#group-belonging)|
|**Semantic Valuation**|*Low*: The value provided temporalizes the beginning of the event, but this information cannot be automatically extracted and formatted.<br><br>*Medium*: The date can be automatically extracted from the value provided (and from textual content that surrounds it if applicable) and can be formatted using the YYYY-MM-DD convention.<br>Accepted Value Type(s): String<br><br>*High*: The date is the sole value provided and is formatted using the date convention.<br>Accepted Value Type(s): DateTime (YYYY-MM-DDThh:mm:ss)|
|**Typical Case(s)**|“Painters Eleven” (Group Appellation) was a Torontonian artists group that emerged “after” (Group Joining Date Begin Qualifier) 1949 (Group Joining Date Begin) and “before” (Group Joining Date End Qualifier) 1960 (Group Joining Date End). It was composed of Jack Bush (Actor Appellation), Oscar Cahén (Actor Appellation), Hortense Gordon (Actor Appellation), Thomas Hodgson (Actor Appellation), Alexandra Luke (Actor Appellation), J.W.G. ("Jock") Macdonald (Actor Appellation), Ray Mead (Actor Appellation), Kazuo Nakamura (Actor Appellation), William Ronald (Actor Appellation), Harold Town (Actor Appellation), and Walter Yarwood (Actor Appellation).|
|**Edge Case(s)**|Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Group Joining Date End: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|CHIN recommends using the following format when entering dates: “YYYY-MM-DD HH:MM:SS”. However, if the data cannot be converted to such a format (such as in the case of an era), a string can be used (e.g. Han Dynasty).|
|**Reference(s)**|[(Le Boeuf et al. 2015, sec. E85 Joining)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Free Dictionary 2019aa)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019aa)|

---

## Group Joining Date End Qualifier

|---|---|
|**Scope**|This field qualifies the latest temporal instant the actor became, formally or informally, a member of the Group.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Group Joining Date End](#group-joining-date-end)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P143i\_was\_joined\_by -\> crm:E85\_Joining -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P80\_end\_is\_qualified\_by -\> **xsd:string**</span>|
|**Target Model View(s)**|[Group Belonging](https://chin-rcip.github.io/collections-model/target-model/current/social-bonds#group-belonging)|
|**Semantic Valuation**|*Low*: The value provided qualifies the date of the event, but this information is unstructured and cannot be automatically formatted.<br><br>*Medium*: The value provided qualifies the date of the event and can be (semi-)automatically cleaned and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String<br><br>*High*: The qualifier is the sole value provided and is structured and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String|
|**Typical Case(s)**|“Painters Eleven” (Group Appellation) was a Torontonian artists group that emerged “after” (Group Joining Date Begin Qualifier) 1949 (Group Joining Date Begin) and “before” (Group Joining Date End Qualifier) 1960 (Group Joining Date End). It was composed of Jack Bush (Actor Appellation), Oscar Cahén (Actor Appellation), Hortense Gordon (Actor Appellation), Thomas Hodgson (Actor Appellation), Alexandra Luke (Actor Appellation), J.W.G. ("Jock") Macdonald (Actor Appellation), Ray Mead (Actor Appellation), Kazuo Nakamura (Actor Appellation), William Ronald (Actor Appellation), Harold Town (Actor Appellation), and Walter Yarwood (Actor Appellation).|
|**Edge Case(s)**|There might be cases where the Group Joining Date End and the Group Joining Date End Qualifier would be the same, in particular when it comes to eras. For example, “Victorian Era” can be both the Group Joining Date End and the Group Joining Date End Qualifier. Determining what eras the qualifiers will entail (through the vocabulary used to handle them) will thus be paramount.<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Group Joining Date End Qualifier: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|There can be more than one qualifier at once for a single Joining Date End (e.g. “BCE” and “BC”, which is the same information, the former being qualified using the non-christian acronym for “Before Common Era” and the latter using the christian “Before Christ”).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020), [(Wikipedia 2019o)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019o), [(Wikipedia 2019r)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019r), [(Wikipedia 2019w)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019w)|

---

## Group Leaving Date Begin

|---|---|
|**Scope**|This field designates the earliest temporal instant the actor disassociated, formally or informally, from the Group.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Group Appellation](#group-appellation)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P145i\_left\_by -\> crm:E86\_Leaving -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82a\_begin\_of\_the\_begin -\> **xsd:dateTime**</span>|
|**Target Model View(s)**|[Group Belonging](https://chin-rcip.github.io/collections-model/target-model/current/social-bonds#group-belonging)|
|**Semantic Valuation**|*Low*: The value provided temporalizes the beginning of the event, but this information cannot be automatically extracted and formatted.<br><br>*Medium*: The date can be automatically extracted from the value provided (and from textual content that surrounds it if applicable) and can be formatted using the YYYY-MM-DD convention.<br>Accepted Value Type(s): String<br><br>*High*: The date is the sole value provided and is formatted using the date convention.<br>Accepted Value Type(s): DateTime (YYYY-MM-DDThh:mm:ss)|
|**Typical Case(s)**|“Painters Eleven” (Group Appellation) was a Torontonian artists group that emerged in the 1950s (Group Joining Date Begin) and was composed of Jack Bush (Actor Appellation), Oscar Cahén (Actor Appellation), Hortense Gordon (Actor Appellation), Thomas Hodgson (Actor Appellation), Alexandra Luke (Actor Appellation), J.W.G. ("Jock") Macdonald (Actor Appellation), Ray Mead (Actor Appellation), Kazuo Nakamura (Actor Appellation), William Ronald (Actor Appellation), Harold Town (Actor Appellation), and Walter Yarwood (Actor Appellation). The group voted to disband in 1960 (Group Leaving Date Begin).|
|**Edge Case(s)**|Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Group Leaving Date Begin: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|CHIN recommends using the following format when entering dates: “YYYY-MM-DD HH:MM:SS”. However, if the data cannot be converted to such a format (such as in the case of an era), a string can be used (e.g. Han Dynasty).|
|**Reference(s)**|[(Le Boeuf et al. 2015, sec. E86 Leaving)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Free Dictionary 2019ab)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019ab)|

---

## Group Leaving Date Begin Qualifier

|---|---|
|**Scope**|This field qualifies the earliest temporal instant the actor disassociated, formally or informally, from the Group.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Group Leaving Date Begin](#group-leaving-date-begin)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P145i\_left\_by -\> crm:E86\_Leaving -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P79\_beginning\_is\_qualified\_by -\> **xsd:string**</span>|
|**Target Model View(s)**|[Group Belonging](https://chin-rcip.github.io/collections-model/target-model/current/social-bonds#group-belonging)|
|**Semantic Valuation**|*Low*: The value provided qualifies the date of the event, but this information is unstructured and cannot be automatically formatted.<br><br>*Medium*: The value provided qualifies the date of the event and can be (semi-)automatically cleaned and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String<br><br>*High*: The qualifier is the sole value provided and is structured and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String|
|**Typical Case(s)**|“Painters Eleven” (Group Appellation) was a Torontonian artists group that emerged in the 1950s (Group Joining Date Begin) and was composed of Jack Bush (Actor Appellation), Oscar Cahén (Actor Appellation), Hortense Gordon (Actor Appellation), Thomas Hodgson (Actor Appellation), Alexandra Luke (Actor Appellation), J.W.G. ("Jock") Macdonald (Actor Appellation), Ray Mead (Actor Appellation), Kazuo Nakamura (Actor Appellation), William Ronald (Actor Appellation), Harold Town (Actor Appellation), and Walter Yarwood (Actor Appellation). The group voted to disband in “after” (Group Leaving Date Begin Qualifier) “1959-12-31” (Group Leaving Date Begin) and “before” (Group Leaving Date End Qualifier) “1961-01-01” (Group Leaving Date End).|
|**Edge Case(s)**|There might be cases where the Group Leaving Date Begin and the Group Leaving Date Begin Qualifier would be the same, in particular when it comes to eras. For example, “Victorian Era” can be both the Group Leaving Date Begin and the Group Leaving Date Begin Qualifier. Determining what eras the qualifiers will entail (through the vocabulary used to handle them) will thus be paramount.<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Group Leaving Date Begin Qualifier: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|There can be more than one qualifier at once for a single Leaving Date Begin (e.g. “BCE” and “BC”, which is the same information, the former being qualified using the non-christian acronym for “Before Common Era” and the latter using the christian “Before Christ”).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020), [(Wikipedia 2019o)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019o), [(Wikipedia 2019r)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019r), [(Wikipedia 2019w)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019w)|

---

## Group Leaving Date End

|---|---|
|**Scope**|This field designates the latest temporal instant the actor disassociated, formally or informally, from the group.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Group Appellation](#group-appellation)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P145i\_left\_by -\> crm:E86\_Leaving -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82b\_end\_of\_the\_end -\> **xsd:dateTime**</span>|
|**Target Model View(s)**|[Group Belonging](https://chin-rcip.github.io/collections-model/target-model/current/social-bonds#group-belonging)|
|**Semantic Valuation**|*Low*: The value provided temporalizes the beginning of the event, but this information cannot be automatically extracted and formatted.<br><br>*Medium*: The date can be automatically extracted from the value provided (and from textual content that surrounds it if applicable) and can be formatted using the YYYY-MM-DD convention.<br>Accepted Value Type(s): String<br><br>*High*: The date is the sole value provided and is formatted using the date convention.<br>Accepted Value Type(s): DateTime (YYYY-MM-DDThh:mm:ss)|
|**Typical Case(s)**|“Painters Eleven” (Group Appellation) was a Torontonian artists group that emerged in the 1950s (Group Joining Date Begin) and was composed of Jack Bush (Actor Appellation), Oscar Cahén (Actor Appellation), Hortense Gordon (Actor Appellation), Thomas Hodgson (Actor Appellation), Alexandra Luke (Actor Appellation), J.W.G. ("Jock") Macdonald (Actor Appellation), Ray Mead (Actor Appellation), Kazuo Nakamura (Actor Appellation), William Ronald (Actor Appellation), Harold Town (Actor Appellation), and Walter Yarwood (Actor Appellation). The group voted to disband in “after” (Group Leaving Date Begin Qualifier) “1959-12-31” (Group Leaving Date Begin) and “before” (Group Leaving Date End Qualifier) “1961-01-01” (Group Leaving Date End).|
|**Edge Case(s)**|Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Group Leaving Date End: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|CHIN recommends using the following format when entering dates: “YYYY-MM-DD HH:MM:SS”. However, if the data cannot be converted to such a format (such as in the case of an era), a string can be used (e.g. Han Dynasty).|
|**Reference(s)**|[(Le Boeuf et al. 2015, sec. E86 Leaving)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Free Dictionary 2019ab)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019ab)|

---

## Group Leaving Date End Qualifier

|---|---|
|**Scope**|This field qualifies the latest temporal instant the actor disassociated, formally or informally, from the group.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Group Leaving Date End](#group-leaving-date-end)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P145i\_left\_by -\> crm:E86\_Leaving -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P80\_end\_is\_qualified\_by -\> **xsd:string**</span>|
|**Target Model View(s)**|[Group Belonging](https://chin-rcip.github.io/collections-model/target-model/current/social-bonds#group-belonging)|
|**Semantic Valuation**|*Low*: The value provided qualifies the date of the event, but this information is unstructured and cannot be automatically formatted.<br><br>*Medium*: The value provided qualifies the date of the event and can be (semi-)automatically cleaned and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String<br><br>*High*: The qualifier is the sole value provided and is structured and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String|
|**Typical Case(s)**|“Painters Eleven” (Group Appellation) was a Torontonian artists group that emerged in the 1950s (Group Joining Date Begin) and was composed of Jack Bush (Actor Appellation), Oscar Cahén (Actor Appellation), Hortense Gordon (Actor Appellation), Thomas Hodgson (Actor Appellation), Alexandra Luke (Actor Appellation), J.W.G. ("Jock") Macdonald (Actor Appellation), Ray Mead (Actor Appellation), Kazuo Nakamura (Actor Appellation), William Ronald (Actor Appellation), Harold Town (Actor Appellation), and Walter Yarwood (Actor Appellation). The group voted to disband in “after” (Group Leaving Date Begin Qualifier) “1959-12-31” (Group Leaving Date Begin) and “before” (Group Leaving Date End Qualifier) “1961-01-01” (Group Leaving Date End).|
|**Edge Case(s)**|There might be cases where the Group Leaving Date End and the Group Leaving Date End Qualifier would be the same, in particular when it comes to eras. For example, “Victorian Era” can be both the Group Leaving Date End and the Group Leaving Date End Qualifier. Determining what eras the qualifiers will entail (through the vocabulary used to handle them) will thus be paramount.<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Group Leaving Date End Qualifier: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|There can be more than one qualifier at once for a single Leaving Date End (e.g. “BCE” and “BC”, which is the same information, the former being qualified using the non-christian acronym for “Before Common Era” and the latter using the christian “Before Christ”).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020), [(Wikipedia 2019o)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019o), [(Wikipedia 2019r)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019r), [(Wikipedia 2019w)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019w)|

---

## Group Member Role

|---|---|
|**Scope**|This field indicates the parts, activities, functions, and duties endorsed by the Actor with regards to a related group with which they have dealings ranging in duration from brief to enduring. These reflect a set of connected behaviours, rights, obligations, beliefs and norms expected from both parties and reflected in the contacts between them as well as the way they behave towards each other, as well as being based on the function of the group and/or the mutual interest between its members.|
|**Generated Bond(s)**|E55\_Type|
|**Dependency(ies)**|[Group Appellation](#group-appellation)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P143i\_was\_joined\_by -\> crm:E85\_Joining -\> crm:P01i\_is\_domain\_of -\> crm:PC144\_joined\_with -\> crm:P144.1\_kind\_of\_member -\> **crm:E55\_Type**</span>|
|**Target Model View(s)**|[Group Belonging](https://chin-rcip.github.io/collections-model/target-model/current/social-bonds#group-belonging)|
|**Semantic Valuation**|*Low*: The value provided is a string that cannot be parsed automatically by reconciliation tools but still contains the required information.<br><br>*Medium*: The value provided is a string that can be automatically cleaned and reconciled using controlled vocabularies specified by CHIN. In the event that the value is adequately structured but does not reconcile with any terms from the controlled vocabulary, and provided that it is deemed relevant, CHIN will add the term to the vocabulary.<br>Accepted Value Type(s): String<br><br>*High*: The provided value is a string that can be automatically reconciled with the controlled vocabularies specified by CHIN.<br>Accepted Value Type(s): String, URI|
|**Typical Case(s)**|The “Société d’art contemporain” (Group Appellation) was founded in Montréal (Birth/Formation Place) in January 1939 (Group Joining Date Begin) by John Lyman (Actor Appellation, Founding Actor Appellation) who was its founder (Group Member Role) along with 24 other artists.|
|**Edge Case(s)**|Being the recipient of an award might be considered as being part of a group that would be formed of all of the recipients of this specific award, although it is not a formal group. In such a case, would the founder of the group be considered to be the first recipient, or the granting organism? For example, the Governor General's Literary Awards were conceived and inaugurated in 1937 (Group Joining Date Begin) by John Buchan, 1st Baron Tweedsmuir who was then acting as 15th Governor General of Canada. He awarded the award for fiction to Laura G. Salverson for *The Dark Weaver*(Group Member Role “Member” or “Recipient”), that for Poetry of drama to E.J. Pratt for *The Fable of the Goats*(Group Member Role “Member” or “Recipient”), and the award for Non-fiction to Stephen Leacock for *My Discovery of the West*(Group Member Role “Member” or “Recipient”)*.* Considering the Group would be the “Recipients of the Governor General of Canada Literary Awards”, would the original recipients considered to be founders (Group Member Role) or would the founder of the award itself (John Buchan, 1st Baron Tweedsmuir) be considered to be the founder of the group as well?|
|**Value Origin(s)**|Actors Checklist: Group Member Role: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|TBD|
|**Reference(s)**|[(Free Dictionary 2019ac)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019ac), [(Free Dictionary 2019ad)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019ad), [(Free Dictionary 2019af)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019af)|

---

<div class="hidden-content">
## Group Type<br><br>**THIS NODE IS NOT DOCUMENTED YET IN THE TARGET MODEL (needs a new name)**

|---|---|
|**Scope**|This field conceptually characterizes organizations in order to categorize them in ensembles based on their formally or informally stated mission or function.|
|**Generated Bond(s)**|E55\_Type|
|**Dependency(ies)**|E74\_Group|
|**Related SQN(s)**|Group Type: Definition|
|**Full Path**|<span class="full-path">crm:E74\_Group -\> crm:P2\_has\_type -\> crm:E55\_Type (*-\> crm:P2\_has\_type -\> crm:E55\_Type\["Group Type"\]*)</span>|
|**Target Model View(s)**|[Group Type with E55 Type](https://chin-rcip.github.io/collections-model/target-model/current/identification#group-type-with-e55-type)|
|**Semantic Valuation**|*Low*: The value provided is a string that cannot be parsed automatically by reconciliation tools but still contains the required information.<br><br>*Medium*: The value provided is a string that can be automatically cleaned and reconciled using controlled vocabularies specified by CHIN. In the event that the value is adequately structured but does not reconcile with any terms from the controlled vocabulary, and provided that it is deemed relevant, CHIN will add the term to the vocabulary.<br>Accepted Value Type(s): String<br><br>*High*: The provided value is a string that can be automatically reconciled with the controlled vocabularies specified by CHIN.<br>Accepted Value Type(s): String, URI|
|**Typical Case(s)**|The “Société d’art contemporain” (Group Appellation) was an “Artist Group” (Group Type) founded in Montréal (Birth/Formation Place) in January 1939 (Group Joining Date Begin) by John Lyman (Actor Appellation, Founding Actor Appellation) who was its founder (Group Member Role) along with 24 other artists.|
|**Edge Case(s)**|Being the recipient of an award might be considered as being part of a group that would be formed of all of the recipients of this specific award. For example, the Governor General's Literary Awards recipients. In this case, what information would we want to confer in the group type? Authors? Award Recipients? Governor General's Literary Awards Recipients?|
|**Value Origin(s)**|Actors Checklist: Group Type: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|This refers to two broad categories of groups, each with more precise lists: social groups (crew, gang, team, etc.) and organizational groups (museum, university, company, government, etc.).<br><br>Families are not represented as groups. Family ties should be represented as ties between actors using relationships fields instead.|
|**Reference(s)**|[(Art & Architecture Thesaurus 2019t)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019t), [(Art & Architecture Thesaurus 2019v)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019v), [(Art & Architecture Thesaurus 2019w)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019w), [(Art & Architecture Thesaurus 2019x)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019x), [(Le Boeuf et al. 2015, sec. E55 Type)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Le Boeuf et al. 2015, sec. E74 Group)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Free Dictionary 2019z)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019z), [(Wikipedia 2019a)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019a), [(Wikipedia 2019c)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019c), [(Wikipedia 2019ak)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019ak), [(Wikipedia 2019al)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019al), [(Wikipedia 2019an)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019an), [(Wikipedia 2019ap)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019ap)|

---
</div>

## Image Bibliographical Mention

|---|---|
|**Scope**|This designates an informational statement appended to the Image. It provides relevant information to cite the Image such as author, year of creation, title, etc.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Image URL](#image-url)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P138i\_has\_representation -\> crm:E36\_Visual\_Item -\> dct:source -\> **xsd:string**</span>|
|**Target Model View(s)**|[Visual Item](https://chin-rcip.github.io/collections-model/target-model/current/descriptive-information#visual-item)|
|**Semantic Valuation**|*Low*: The value provided is an unstructured string that contains the information of a bibliographic mention.<br><br>*Medium*: The value provided is a string of a bibliographic mention that follows a citation convention that is not the one adopted by CHIN.<br>Accepted Value Type: String<br><br>*High*: The value provided is a string of a bibliographic mention that follows the citation convention adopted by CHIN.<br>Accepted Value Type: String|
|**Typical Case(s)**|*Mawu-che-hitoowin: A Gathering of People for any Purpose* is a 1992 (Object Record Date Begin & Object Record Date End) installation (Object Medium & Image Medium) by Rebecca Belmore (Actor Appellation). The mention appended to an image of Belmore’s work could be the following:<br><br>Belmore, Rebecca. 1992. *Mawu-Che-Hitoowin: A Gathering of People for Any Purpose*. Installation.|
|**Edge Case(s)**|*Mawu-che-hitoowin: A Gathering of People for any Purpose* is a 1992 (Object Record Date Begin & Object Record Date End) installation (Object Medium & Image Medium) by Rebecca Belmore (Actor Appellation). Whether the rights mention of such an image could be considered to be bibliographical is debatable. For example: “© Rebecca Belmore 1992”.|
|**Value Origin(s)**|Actors Checklist: Image Bibliographical Mention: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|The mention pertains to the Image itself so that there cannot be an Image Mention without an Image.<br><br>CHIN recommends the use of a recognized and standard citation format such as that of the Chicago Manual of Style (CMS), Modern Languages Association (MLA) or American Psychological Association (APA).<br><br>*Would this be equivalent to a notice? Because then it should be more substantial and the example as well as the definition should reflect that.*<br><br>This field is not yet modeled in the Target Model 2.0, but will be in a subsequent version.|
|**Reference(s)**|[(Free Dictionary 2019ah)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019ah)|

---

## Image URL

|---|---|
|**Scope**|Unique resource locator that, in addition to identifying the image, provides its address on the internet according to one of a variety of protocols.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|E39\_Actor|
|**Related SQN(s)**|URL: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P138i\_has\_representation -\> crm:E36\_Visual\_Item -\> crm:P165i\_is\_incorporated\_in -\> crmdig:D1\_Digital\_Object -\> crm:P1\_is\_identified\_by -\> crm:E41\_Appellation (*-\> crm:P2\_has\_type -\> crm:E55\_Type\["URL"\]*) -\> crm:P190\_has\_symbolic\_content -\> **xsd:string**</span>|
|**Target Model View(s)**|[Visual Item](https://chin-rcip.github.io/collections-model/target-model/current/descriptive-information#visual-item)|
|**Semantic Valuation**|*Low*: N/A<br><br>*Medium*: N/A<br>Accepted Value Type(s): URL<br><br>*High*: The value provided is an URL that follows the W3C conventions on URLs and should not be broken.<br>Accepted Value Type(s): URL|
|**Typical Case(s)**|*Mawu-che-hitoowin: A Gathering of People for any Purpose* is a 1992 (Object Record Date Begin & Object Record Date End) installation (Object Medium & Image Medium) by Rebecca Belmore (Actor Appellation). The mention appended to an image of Belmore’s work could be the following:<br><br>Belmore, Rebecca. 1992. *Mawu-Che-Hitoowin: A Gathering of People for Any Purpose*. Installation.<br><br>A URL associated to that image might be the following: “[https://www.rebeccabelmore.com/exhibit/Mawu-che-hitoowin.html](https://www.rebeccabelmore.com/exhibit/Mawu-che-hitoowin.html#null)”|
|**Edge Case(s)**|To Come|
|**Value Origin(s)**|Actors Checklist: Image URL: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|TBD|
|**Reference(s)**|[(Art & Architecture Thesaurus 2019y)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019y), [(Free Dictionary 2019ag)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019ag), [(Wikipedia 2019e)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019e)|

---

## Mark Bibliographical Mention

|---|---|
|**Scope**|This designates an informational statement appended to the Mark. It provides relevant information to cite the Image such as author, year of creation, title, etc.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Mark URL](#mark-url)|
|**Related SQN(s)**|Symbolic: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P02i\_is\_range\_of -\> crm:PC138\_represents (*-\> crm:P138.1\_mode\_of\_representation -\> crm:E55\_Type\["Symbolic"\]*) -\> crm:P01\_has\_domain -\> crm:E37\_Mark -\> dct:source -\> **xsd:string**</span>|
|**Target Model View(s)**|[Visual Item](https://chin-rcip.github.io/collections-model/target-model/current/descriptive-information#visual-item)|
|**Semantic Valuation**|*Low*: The value provided is an unstructured string that contains the information of a bibliographic mention.<br><br>*Medium*: The value provided is a string of a bibliographic mention that follows a citation convention that is not the one adopted by CHIN.<br>Accepted Value Type: String<br><br>*High*: The value provided is a string of a bibliographic mention that follows the citation convention adopted by CHIN.<br>Accepted Value Type: String|
|**Typical Case(s)**|Candice Breitz did *Profile Variation* in 2017. The video contains an image showing the back of a person's head with a shaved Visa Inc. logo.<br><br>The Visa logo could be marked within the image, in which case it would have to be quoted using Mark Bibliographical Mention (“Breitz, Candice. 2017. *Profile Variation*. HD video. Artwork.”). In this example the Mark Type would be “Logo” and the Mark URL would point to this image:<br><br>![Image\_2](media/image2.png)<br>Visa Inc. 2014. Logo detail.<br>Unknown (Vector graphics image by Fma12). This W3C-unspecified vector image was created with CorelDRAW, Public domain, via Wikimedia Commons.<br>[https://upload.wikimedia.org/wikipedia/commons/5/53/Visa_2014_logo_detail.svg](https://upload.wikimedia.org/wikipedia/commons/5/53/Visa_2014_logo_detail.svg) (Mark URL)<br><br>Considering the Visa logo is copyrighted, CHIN would have to check that the institution providing the image has the rights to both the video (of which there is a still image above) and the logo.<br><br>The National Gallery of Canada would have a “Logo” Mark Type for the Mark URL leading to the image of its logo. The “National Gallery of Canada / Musée des beaux-arts du Canada” (Mark Bibliographical Mention) could be added.|
|**Edge Case(s)**|How this differs from the Image Bibliographical Mention is unclear, especially when recording a notice. If recording the latter, it seems the Image Bibliographical Mention would be best as it could be more substantial, but the example as well as the definition should reflect that.|
|**Value Origin(s)**|Actors Checklist: Mark Bibliographical Mention: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|CHIN recommends the use of a recognized and standard citation format such as that of the Chicago Manual of Style (CMS), Modern Languages Association (MLA) or American Psychological Association (APA).<br><br>This field is not yet modeled in the Target Model 2.0, but will be in a subsequent version.|
|**Reference(s)**|[(Free Dictionary 2019ah)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019ah)|

---

## Mark Type

|---|---|
|**Scope**|This field refers to the specific branding element or means of expression used to create the visual identity depicted on the image.|
|**Generated Bond(s)**|E55\_Type|
|**Dependency(ies)**|[Mark URL](#mark-url)|
|**Related SQN(s)**|Symbolic: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P02i\_is\_range\_of -\> crm:PC138\_represents (*-\> crm:P138.1\_mode\_of\_representation -\> crm:E55\_Type\["Symbolic"\]*) -\> crm:P01\_has\_domain -\> crm:E37\_Mark -\> crm:P2\_has\_type -\> **crm:E55\_Type**</span>|
|**Target Model View(s)**|[Visual Item](https://chin-rcip.github.io/collections-model/target-model/current/descriptive-information#visual-item)|
|**Semantic Valuation**|*Low*: The value provided is a string that cannot be parsed automatically by reconciliation tools but still contains the required information.<br><br>*Medium*: The value provided is a string that can be automatically cleaned and reconciled using controlled vocabularies specified by CHIN. In the event that the value is adequately structured but does not reconcile with any terms from the controlled vocabulary, and provided that it is deemed relevant, CHIN will add the term to the vocabulary.<br>Accepted Value Type(s): String<br><br>*High*: The provided value is a string that can be automatically reconciled with the controlled vocabularies specified by CHIN.<br>Accepted Value Type(s): String, URI|
|**Typical Case(s)**|Candice Breitz did *Profile Variation* in 2017. The video contains an image showing the back of a person's head with a shaved Visa Inc. logo.<br><br>The Visa logo could be marked within the image, in which case it would have to be quoted using Mark Bibliographical Mention (“Breitz, Candice. 2017. *Profile Variation*. HD video. Artwork.”). In this example the Mark Type would be “Logo” and the Mark URL would point to this image:<br><br>![Image\_2](media/image2.png)<br>Visa Inc. 2014. Logo detail.<br>Unknown (Vector graphics image by Fma12). This W3C-unspecified vector image was created with CorelDRAW, Public domain, via Wikimedia Commons.<br>[https://upload.wikimedia.org/wikipedia/commons/5/53/Visa_2014_logo_detail.svg](https://upload.wikimedia.org/wikipedia/commons/5/53/Visa_2014_logo_detail.svg) (Mark URL)<br><br>Considering the Visa logo is copyrighted, CHIN would have to check that the institution providing the image has the rights to both the video (of which there is a still image above) and the logo.<br><br>The National Gallery of Canada would have a “Logo” Mark Type for the Mark URL leading to the image of its logo.|
|**Edge Case(s)**|In 2016 Anish Kapoor coated his 2006 sculpture *Cloud Gate* in Vantablack, a light-absorbing material to which he bought the exclusive rights in terms of artistic use.<br><br>The material has been developed and patented by Surrey NanoSystems. In this case, Vantablack could be considered to be a material (part of the sculpture) or a mark (as it was added to the sculpture years after it was first unveiled to the public) that amounts to a signature considering the use of Vantablack is limited to Kapoor. It is also debatable whether this is Mark Type for Surrey NanoSystems as well. This also poses the question of whether, if a mark is mainly used to enforce identity, it must enforce the identity of the main Actor, or if it can enforce that of a third party (e.g. even though *Cloud Gate* is by Kapoor, this could be considered to enforce Surrey NanoSystems’ identity just as much).<br><br>What constitutes a mark might also be complicated by what it is posed on. Would the mark have to be permanent? Would a tattoo constitute a Mark for example? Or a sunburn such as in Dennis Oppenheim’s *Reading Position for Second Degree Burn* performance showing two parallel before and after images of a man sunbathing on the sand. The before part has an open book facing down on the chest, and the after part has the sunburn mark of the book upon removal.|
|**Value Origin(s)**|Actors Checklist: Mark Type: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|Marks are most often used to enforce corporate identity through branding elements such as logos, taglines, slogans, etc.<br><br>This field is not yet modeled in the Target Model 2.0, but will be in a subsequent version.|
|**Reference(s)**|[(Le Boeuf et al. 2015, sec. E37 Mark)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Wikipedia 2019aa)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019aa)|

---

## Mark URL

|---|---|
|**Scope**|This designates symbols, signs, signatures or short texts applied to artefacts in order to indicate the creator, owner, dedications, purpose, etc.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|E39\_Actor|
|**Related SQN(s)**|Symbolic: Definition<br><br>URL: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P02i\_is\_range\_of -\> crm:PC138\_represents (*-\> crm:P138.1\_mode\_of\_representation -\> crm:E55\_Type\["Symbolic"\]*) -\> crm:P01\_has\_domain -\> crm:E37\_Mark -\> crm:P165i\_is\_incorporated\_in -\> crmdig:D1\_Digital\_Object -\> crm:P1\_is\_identified\_by -\> crm:E41\_Appellation (*-\> crm:P2\_has\_type -\> crm:E55\_Type\["URL"\]*) -\> crm:P190\_has\_symbolic\_content -\> **xsd:string**</span>|
|**Target Model View(s)**|[Visual Item](https://chin-rcip.github.io/collections-model/target-model/current/descriptive-information#visual-item)|
|**Semantic Valuation**|*Low*: N/A<br><br>*Medium*: N/A<br><br>*High*: The value provided is an URL that follows the W3C conventions on URLs and should not be broken.<br>Accepted Value Type(s): URL|
|**Typical Case(s)**|Candice Breitz did *Profile Variation* in 2017. The video contains an image showing the back of a person's head with a shaved Visa Inc. logo.<br><br>The Visa logo could be marked within the image, in which case it would have to be quoted using Mark Bibliographical Mention (“Breitz, Candice. 2017. *Profile Variation*. HD video. Artwork.”). In this example the Mark Type would be “Logo” and the Mark URL would point to this image:<br><br>![Image\_2](media/image2.png)<br>Visa Inc. 2014. Logo detail.<br>Unknown (Vector graphics image by Fma12). This W3C-unspecified vector image was created with CorelDRAW, Public domain, via Wikimedia Commons.<br>[https://upload.wikimedia.org/wikipedia/commons/5/53/Visa_2014_logo_detail.svg](https://upload.wikimedia.org/wikipedia/commons/5/53/Visa_2014_logo_detail.svg) (Mark URL)<br><br>Considering the Visa logo is copyrighted, CHIN would have to check that the institution providing the image has the rights to both the video (of which there is a still image above) and the logo.|
|**Edge Case(s)**|To Come|
|**Value Origin(s)**|Actors Checklist: Mark URL: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|Marks are most often used to enforce corporate identity through branding elements such as logos, taglines, slogans, etc.|
|**Reference(s)**|[(Le Boeuf et al. 2015, sec. E37 Mark)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Wikipedia 2019aa)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019aa)|

---

## Mother Appellation

|---|---|
|**Scope**|This field designates the entire identifying word(s), number(s), symbol(s) or code(s) by which an actor’s biological mother is distinguished from others, such as the name, title, or designation as it has been attributed by a contributing institution. Her appellation is an identifying agreed upon term that is descriptive or connotative. If it is made of the concatenation of numerous parts, it should include all of them (such as honorifics, titles, etc.).|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|E21\_Person|
|**Full Path**|<span class="full-path">crm:E21\_Person -\> crm:P98i\_was\_born -\> crm:E67\_Birth -\> crm:P96\_by\_mother -\> crm:E21\_Person -\> crm:P1\_is\_identified\_by -\> crm:E41\_Appellation + crm:E33\_Linguistic\_Object -\> crm:P190\_has\_symbolic\_content -\> **xsd:string**</span>|
|**Target Model View(s)**|[Birth/Death of People and Formation/Dissolution of Groups](https://chin-rcip.github.io/collections-model/target-model/current/life-events#birthdeath-of-people-and-formationdissolution-of-groups)|
|**Semantic Valuation**|*Low*: The provided values contain unstructured information of the appellation, such as it cannot be parsed automatically by reconciliation tools, but still contains the required information.<br><br>*Medium*: The provided values contain structured information that can be automatically cleaned and reconciled with other entities in other datasets.<br>Accepted Value Type(s): String<br><br>*High*: The provided values only contain structured information that can be automatically reconciled with other entities in other datasets.<br>Accepted Value Type(s): String|
|**Typical Case(s)**|Diplomat “Peter Dale Scott” (Actor Appellation) was born to painter “Marian Mildred Dale Scott” (Mother Appellation) and poet and law professor “Francis Reginald Scott” (Father Appellation).<br><br>Painter “Emily Carr” (Actor Appellation) was born to “Emily (Saunders) Carr” (Mother Appellation) and Richard Carr (Father Appellation).|
|**Edge Case(s)**|The female genetic contributor to the creation of the infant might not be the woman giving birth. In this case, who would be considered to be the mother is up for debate.|
|**Value Origin(s)**|Actors Checklist: Mother Appellation: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|A biological mother is understood to be the female genetic contributor to the creation of the infant, through sexual intercourse or egg donation.|
|**Reference(s)**|[(Art & Architecture Thesaurus 2019d)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019d), [(Art & Architecture Thesaurus 2019q)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019q), [(Le Boeuf et al. 2015, sec. E82 Actor Appellation)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Le Boeuf et al. 2015, sec. E41 Appellation)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Le Boeuf et al. 2015, sec. P96 by Mother)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Free Dictionary 2019a)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019a), [(Free Dictionary 2019f)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019f), [(Free Dictionary 2019r)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019r), [(Wikipedia 2019aq)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019aq)|

---

## Nationality

|---|---|
|**Scope**|This field indicates the status of belonging (by origin, birth, or naturalization) to a politically autonomous entity endowed with national independence. Unlike cultural affiliation type, which relies on self-association with a culture, nationality refers to the legal status of being a citizen or a subject of a recognized state. \*|
|**Generated Bond(s)**|E74\_Group|
|**Dependency(ies)**|E39\_Actor|
|**Related SQN(s)**|Identity: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P143i\_was\_joined\_by -\> crm:E85\_Joining -\> crm:P144\_joined\_with -\> **crm:E74\_Group** (*-\> crm:E55\_Type -\> crm:P2\_has\_type -\> crm:E55\_Type\["Identity"\]*)<br><br>crm:E39\_Actor -\> crm:P145i\_left\_by -\> crm:E86\_Leaving -\> crm:P146\_separated\_from -\> **crm:E74\_Group** (*-\> crm:E55\_Type -\> crm:P2\_has\_type -\> crm:E55\_Type\["Identity"\]*)</span>|
|**Target Model View(s)**|[Nationality, Nationhood and Community with E74 Group](https://chin-rcip.github.io/collections-model/target-model/current/identification#nationality-nationhood-and-community-with-e74-group)|
|**Semantic Valuation**|*Low*: The value provided is a string that cannot be parsed automatically by reconciliation tools but still contains the required information.<br><br>*Medium*: The value provided is a string that can be automatically cleaned and reconciled using controlled vocabularies specified by CHIN. In the event that the value is adequately structured but does not reconcile with any terms from the controlled vocabulary, and provided that it is deemed relevant, CHIN will add the term to the vocabulary.<br>Accepted Value Type(s): String<br><br>*High*: The provided value is a string that can be automatically reconciled with the controlled vocabularies specified by CHIN.<br>Accepted Value Type(s): String, URI|
|**Typical Case(s)**|Janet Cardiff (Actor Appellation) is a Canadian (Nationality) artist (Occupation Type) born on 1957-03-15 (Nationality Joining Date Begin) and who was active as an artist as of 1995.<br><br>Margaret Wade Labarge (Actor Appellation) was born in New York City in 1916 (Nationality “American”; Joining Date Begin “1916-07-18”) and moved to Canada with her husband in 1940. She renounced her US citizenship (Nationality “American”; Leaving Date Begin “1939”; Leaving Date Begin Qualifier “after”) and became a Canadian citizen (Nationality “Canadian”, Joining Date Begin “1940”, Joining Date Begin Qualifier “or after”), which she remained until her death on August 31, 2009 (Leaving Date Begin and Leaving Date End “2009-08-31”).<br><br>Aldo is a Canadian (Nationality) retailer operating worldwide.|
|**Edge Case(s)**|Mark Carney (Actor Appellation) is a Canadian economist and banker (Nationality “Canadian”) born in Fort Smith, Northwest Territories on March 16, 1965 (Nationality Joining Date Begin “1965-03-16”). He became an Irish citizen after 1988 (Nationality “Irish”; Joining Date Begin “1988”, Joining Date Begin Qualifier “after”). He acquired British nationality on November 21, 2018 (Nationality “British”; Joining Date Begin “2018-11-21”). He thus holds Canadian, Irish, and British citizenship. It is not clear how many nationalities an actor can hold nor is it established how this information should be recorded (e.g. should begin or end dates be used? should the joining date begin determine the beginning of the process or of the official holding of the nationality, considering the process is often several years long?).<br><br>Certain Indigenous people do not recognize the nationality they were legally ascribed at birth (e.g. deny their Canadian citizenship or any citizenship that is not that of their Indigenous community). How would *denial*of nationality be recorded here?<br><br>How an organization’s nationality is determined will have to be established. For example, Google is generally thought of as an American company, but it also has headquarters elsewhere as well as being incorporated outside the US as well as in Delaware.|
|**Value Origin(s)**|Actors Checklist: Nationality: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|The field can accommodate all UTF-8 compliant languages, although the use of English or French (exonyms) is recommended.<br><br>CHIN will be using legal recognition of the topmost level in this field. This means that provinces etc. (i.e. smaller political entities that are non-autonomous) would be entered under another field (whether culture or community).<br><br>AAT: Generally refers to “culture or style” (ex. Japanese (culture or style)), although the scope notes show they also use these terms to cover nationalities, ethnicities, and historical periods.|
|**Reference(s)**|[(Art & Architecture Thesaurus 2019f)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019f), [(Free Dictionary 2019g)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019g), [(Wikipedia 2019aj)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019aj)|

---

## Nationality Joining Date Begin

|---|---|
|**Scope**|This field designates the earliest temporal instant the actor formally started belonging to a politically autonomous entity endowed with national independence (holding a nationality status).|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Nationality](#nationality)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P143i\_was\_joined\_by -\> crm:E85\_Joining -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82a\_begin\_of\_the\_begin -\> **xsd:dateTime**</span>|
|**Target Model View(s)**|[Nationality, Nationhood and Community with E74 Group](https://chin-rcip.github.io/collections-model/target-model/current/identification#nationality-nationhood-and-community-with-e74-group)|
|**Semantic Valuation**|*Low*: The value provided temporalizes the beginning of the event, but this information cannot be automatically extracted and formatted.<br><br>*Medium*: The date can be automatically extracted from the value provided (and from textual content that surrounds it if applicable) and can be formatted using the YYYY-MM-DD convention.<br>Accepted Value Type(s): String<br><br>*High*: The date is the sole value provided and is formatted using the date convention.<br>Accepted Value Type(s): DateTime (YYYY-MM-DDThh:mm:ss)|
|**Typical Case(s)**|Janet Cardiff (Actor Appellation) is a Canadian (Nationality) artist (Occupation Type) born on 1957-03-15 (Nationality Joining Date Begin & Nationality Joining Date End) and who was active as an artist as of 1995.<br><br>Margaret Wade Labarge (Actor Appellation) was born in New York City in 1916 (Nationality “American”; Joining Date Begin “1916-07-18”) and moved to Canada with her husband in 1940. She renounced her US citizenship (Nationality “American”; Leaving Date Begin “1939”; Leaving Date Begin Qualifier “after”) and became a Canadian citizen (Nationality “Canadian”, Joining Date Begin “1940”, Joining Date Begin Qualifier “or after”; Joining Date End “1940”, Joining Date End Qualifier “after”), which she remained until her death on August 31, 2009 (Leaving Date Begin and Leaving Date End “2009-08-31”).|
|**Edge Case(s)**|Mark Carney (Actor Appellation) is a Canadian economist and banker (Nationality “Canadian”) born in Fort Smith, Northwest Territories on March 16, 1965 (Nationality Joining Date Begin “1965-03-16”). He became an Irish citizen after 1988 (Nationality “Irish”; Joining Date Begin “1988”, Joining Date Begin Qualifier “after”). He acquired British nationality on November 21, 2018 (Nationality “British”; Joining Date Begin “2018-11-21”). He thus holds Canadian, Irish, and British citizenship. It is not clear how many nationalities an actor can hold nor is it established how this information should be recorded (e.g. should begin or end dates be used? should the joining date begin determine the beginning of the process or of the official holding of the nationality, considering the process is often several years long?).<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Nationality Joining Date Begin: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|CHIN recommends using the following format when entering dates: “YYYY-MM-DD HH:MM:SS”. However, if the data cannot be converted to such a format (such as in the case of an era), a string can be used (e.g. Han Dynasty).|
|**Reference(s)**|[(Le Boeuf et al. 2015, sec. E85 Joining)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Free Dictionary 2019aa)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019aa)|

---

## Nationality Joining Date Begin Qualifier

|---|---|
|**Scope**|This field qualifies the earliest temporal instant the actor formally started belonging to a politically autonomous entity endowed with national independence (holding a nationality status).|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Nationality Joining Date Begin](#nationality-joining-date-begin)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P143i\_was\_joined\_by -\> crm:E85\_Joining -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P79\_beginning\_is\_qualified\_by -\> **xsd:string**</span>|
|**Target Model View(s)**|[Nationality, Nationhood and Community with E74 Group](https://chin-rcip.github.io/collections-model/target-model/current/identification#nationality-nationhood-and-community-with-e74-group)|
|**Semantic Valuation**|*Low*: The value provided qualifies the date of the event, but this information is unstructured and cannot be automatically formatted.<br><br>*Medium*: The value provided qualifies the date of the event and can be (semi-)automatically cleaned and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String<br><br>*High*: The qualifier is the sole value provided and is structured and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String|
|**Typical Case(s)**|Janet Cardiff (Actor Appellation) is a Canadian (Nationality) artist (Occupation Type) born on 1957-03-15 (Nationality Joining Date Begin & Nationality Joining Date End) and who was active as an artist as of 1995.<br><br>Margaret Wade Labarge (Actor Appellation) was born in New York City in 1916 (Nationality “American”; Joining Date Begin “1916-07-18”) and moved to Canada with her husband in 1940. She renounced her US citizenship (Nationality “American”; Leaving Date Begin “1939”; Leaving Date Begin Qualifier “after”) and became a Canadian citizen (Nationality “Canadian”, Joining Date Begin “1940”, Joining Date Begin Qualifier “or after”; Joining Date End “1940”, Joining Date End Qualifier “after”), which she remained until her death on August 31, 2009 (Leaving Date Begin and Leaving Date End “2009-08-31”).|
|**Edge Case(s)**|There might be cases where the Nationality Joining Date Begin and the Nationality Joining Date Begin Qualifier would be the same, in particular when it comes to eras. For example, “Victorian Era” can be both the Nationality Joining Date Begin and the Nationality Joining Date Begin Qualifier. Determining what eras the qualifiers will entail (through the vocabulary used to handle them) will thus be paramount.<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Nationality Joining Date Begin Qualifier: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|There can be more than one qualifier at once for a single Joining Date Begin (e.g. “BCE” and “BC”, which is the same information, the former being qualified using the non-christian acronym for “Before Common Era” and the latter using the christian “Before Christ”).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020), [(Wikipedia 2019o)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019o), [(Wikipedia 2019r)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019r), [(Wikipedia 2019w)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019w)|

---

## Nationality Joining Date End

|---|---|
|**Scope**|This field designates the latest temporal instant the actor formally started belonging to a politically autonomous entity endowed with national independence (holding a nationality status).|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Nationality](#nationality)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P143i\_was\_joined\_by -\> crm:E85\_Joining -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82b\_end\_of\_the\_end -\> **xsd:dateTime**</span>|
|**Target Model View(s)**|[Nationality, Nationhood and Community with E74 Group](https://chin-rcip.github.io/collections-model/target-model/current/identification#nationality-nationhood-and-community-with-e74-group)|
|**Semantic Valuation**|*Low*: The value provided temporalizes the beginning of the event, but this information cannot be automatically extracted and formatted.<br><br>*Medium*: The date can be automatically extracted from the value provided (and from textual content that surrounds it if applicable) and can be formatted using the YYYY-MM-DD convention.<br>Accepted Value Type(s): String<br><br>*High*: The date is the sole value provided and is formatted using the date convention.<br>Accepted Value Type(s): DateTime (YYYY-MM-DDThh:mm:ss)|
|**Typical Case(s)**|Janet Cardiff (Actor Appellation) is a Canadian (Nationality) artist (Occupation Type) born on 1957-03-15 (Nationality Joining Date Begin & Nationality Joining Date End) and who was active as an artist as of 1995.<br><br>Margaret Wade Labarge (Actor Appellation) was born in New York City in 1916 (Nationality “American”; Joining Date Begin “1916-07-18”) and moved to Canada with her husband in 1940. She renounced her US citizenship (Nationality “American”; Leaving Date Begin “1939”; Leaving Date Begin Qualifier “after”) and became a Canadian citizen (Nationality “Canadian”, Joining Date Begin “1940”, Joining Date Begin Qualifier “or after”; Joining Date End “1940”, Joining Date End Qualifier “after”), which she remained until her death on August 31, 2009 (Leaving Date Begin and Leaving Date End “2009-08-31”).|
|**Edge Case(s)**|Mark Carney (Actor Appellation) is a Canadian economist and banker (Nationality “Canadian”) born in Fort Smith, Northwest Territories on March 16, 1965 (Nationality Joining Date Begin “1965-03-16”). He became an Irish citizen after 1988 (Nationality “Irish”; Joining Date Begin “1988”, Joining Date Begin Qualifier “after”). He acquired British nationality on November 21, 2018 (Nationality “British”; Joining Date Begin “2018-11-21”). He thus holds Canadian, Irish, and British citizenship. It is not clear how many nationalities an actor can hold nor is it established how this information should be recorded (e.g. should begin or end dates be used? should the joining date begin determine the beginning of the process or of the official holding of the nationality, considering the process is often several years long?).<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Nationality Joining Date End: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|CHIN recommends using the following format when entering dates: “YYYY-MM-DD HH:MM:SS”. However, if the data cannot be converted to such a format (such as in the case of an era), a string can be used (e.g. Han Dynasty).|
|**Reference(s)**|[(Le Boeuf et al. 2015, sec. E85 Joining)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Free Dictionary 2019aa)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019aa)|

---

## Nationality Joining Date End Qualifier

|---|---|
|**Scope**|This field qualifies the latest temporal instant the actor formally started belonging to a politically autonomous entity endowed with national independence (holding a nationality status).|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Nationality Joining Date End](#nationality-joining-date-end)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P143i\_was\_joined\_by -\> crm:E85\_Joining -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P80\_end\_is\_qualified\_by -\> **xsd:string**</span>|
|**Target Model View(s)**|[Nationality, Nationhood and Community with E74 Group](https://chin-rcip.github.io/collections-model/target-model/current/identification#nationality-nationhood-and-community-with-e74-group)|
|**Semantic Valuation**|*Low*: The value provided qualifies the date of the event, but this information is unstructured and cannot be automatically formatted.<br><br>*Medium*: The value provided qualifies the date of the event and can be (semi-)automatically cleaned and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String<br><br>*High*: The qualifier is the sole value provided and is structured and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String|
|**Typical Case(s)**|Janet Cardiff (Actor Appellation) is a Canadian (Nationality) artist (Occupation Type) born on 1957-03-15 (Nationality Joining Date Begin & Nationality Joining Date End) and who was active as an artist as of 1995.<br><br>Margaret Wade Labarge (Actor Appellation) was born in New York City in 1916 (Nationality “American”; Joining Date Begin “1916-07-18”) and moved to Canada with her husband in 1940. She renounced her US citizenship (Nationality “American”; Leaving Date Begin “1939”; Leaving Date Begin Qualifier “after”) and became a Canadian citizen (Nationality “Canadian”, Joining Date Begin “1940”, Joining Date Begin Qualifier “or after”; Joining Date End “1940”, Joining Date End Qualifier “after”), which she remained until her death on August 31, 2009 (Leaving Date Begin and Leaving Date End “2009-08-31”).|
|**Edge Case(s)**|There might be cases where the Nationality Joining Date End and the Nationality Joining Date End Qualifier would be the same, in particular when it comes to eras. For example, “Victorian Era” can be both the Nationality Joining Date End and the Nationality Joining Date End Qualifier. Determining what eras the qualifiers will entail (through the vocabulary used to handle them) will thus be paramount.<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Nationality Joining Date End Qualifier: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|There can be more than one qualifier at once for a single Joining Date End (e.g. “BCE” and “BC”, which is the same information, the former being qualified using the non-christian acronym for “Before Common Era” and the latter using the christian “Before Christ”).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020), [(Wikipedia 2019o)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019o), [(Wikipedia 2019r)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019r), [(Wikipedia 2019w)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019w)|

---

## Nationality Leaving Date Begin

|---|---|
|**Scope**|This field designates the earliest temporal instant the actor formally stopped belonging to a politically autonomous entity endowed with national independence (holding a nationality status).|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Nationality](#nationality)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:PP145i\_left\_by -\> crm:E86\_Leaving -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82a\_begin\_of\_the\_begin -\> **xsd:dateTime**</span>|
|**Target Model View(s)**|[Nationality, Nationhood and Community with E74 Group](https://chin-rcip.github.io/collections-model/target-model/current/identification#nationality-nationhood-and-community-with-e74-group)|
|**Semantic Valuation**|*Low*: The value provided temporalizes the beginning of the event, but this information cannot be automatically extracted and formatted.<br><br>*Medium*: The date can be automatically extracted from the value provided (and from textual content that surrounds it if applicable) and can be formatted using the YYYY-MM-DD convention.<br>Accepted Value Type(s): String<br><br>*High*: The date is the sole value provided and is formatted using the date convention.<br>Accepted Value Type(s): DateTime (YYYY-MM-DDThh:mm:ss)|
|**Typical Case(s)**|Janet Cardiff (Actor Appellation) is a Canadian (Nationality) artist (Occupation Type) born on 1957-03-15 (Nationality Joining Date Begin & Nationality Joining Date End) and who was active as an artist as of 1995.<br><br>Margaret Wade Labarge (Actor Appellation) was born in New York City in 1916 (Nationality “American”; Joining Date Begin “1916-07-18”) and moved to Canada with her husband in 1940. She renounced her US citizenship (Nationality “American”; Leaving Date Begin “1939”; Leaving Date Begin Qualifier “after”) and became a Canadian citizen (Nationality “Canadian”, Joining Date Begin “1940”, Joining Date Begin Qualifier “or after”; Joining Date End “1940”, Joining Date End Qualifier “after”), which she remained until her death on August 31, 2009 (Leaving Date Begin and Leaving Date End “2009-08-31”).|
|**Edge Case(s)**|Margaret Wade Labarge (Actor Appellation) was born in New York City in 1916 (Nationality “American”; Joining Date Begin “1916-07-18”) and moved to Canada with her husband in 1940. She renounced her US citizenship (Nationality “American”; Leaving Date Begin “1939”; Leaving Date Begin Qualifier “after”) and became a Canadian citizen (Nationality “Canadian”, Joining Date Begin “1940”, Joining Date Begin Qualifier “or after”; Joining Date End “1940”, Joining Date End Qualifier “after”), which she remained until her death on August 31, 2009 (Leaving Date Begin and Leaving Date End “2009-08-31”). It is not clear how many nationalities an actor can hold nor is it established how this information should be recorded (e.g. should begin or end dates be used? can they overlap? should the Joining Date Begin determine the beginning of the process or should it be the official holding of the nationality, considering the process is often several years long?).<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Nationality Leaving Date Begin: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|CHIN recommends using the following format when entering dates: “YYYY-MM-DD HH:MM:SS”. However, if the data cannot be converted to such a format (such as in the case of an era), a string can be used (e.g. Han Dynasty).|
|**Reference(s)**|[(Le Boeuf et al. 2015, sec. E86 Leaving)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Free Dictionary 2019ab)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019ab)|

---

## Nationality Leaving Date Begin Qualifier

|---|---|
|**Scope**|This field qualifies the earliest temporal instant the actor formally stopped belonging to a politically autonomous entity endowed with national independence (holding a nationality status).|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Nationality Leaving Date Begin](#nationality-leaving-date-begin)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P145i\_left\_by -\> crm:E86\_Leaving -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P79\_beginning\_is\_qualified\_by -\> **xsd:string**</span>|
|**Target Model View(s)**|[Nationality, Nationhood and Community with E74 Group](https://chin-rcip.github.io/collections-model/target-model/current/identification#nationality-nationhood-and-community-with-e74-group)|
|**Semantic Valuation**|*Low*: The value provided qualifies the date of the event, but this information is unstructured and cannot be automatically formatted.<br><br>*Medium*: The value provided qualifies the date of the event and can be (semi-)automatically cleaned and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String<br><br>*High*: The qualifier is the sole value provided and is structured and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String|
|**Typical Case(s)**|Janet Cardiff (Actor Appellation) is a Canadian (Nationality) artist (Occupation Type) born on 1957-03-15 (Nationality Joining Date Begin & Nationality Joining Date End) and who was active as an artist as of 1995.<br><br>Margaret Wade Labarge (Actor Appellation) was born in New York City in 1916 (Nationality “American”; Joining Date Begin “1916-07-18”) and moved to Canada with her husband in 1940. She renounced her US citizenship (Nationality “American”; Leaving Date Begin “1939”; Leaving Date Begin Qualifier “after”) and became a Canadian citizen (Nationality “Canadian”, Joining Date Begin “1940”, Joining Date Begin Qualifier “or after”; Joining Date End “1940”, Joining Date End Qualifier “after”), which she remained until her death on August 31, 2009 (Leaving Date Begin and Leaving Date End “2009-08-31”).|
|**Edge Case(s)**|There might be cases where the Nationality Leaving Date Begin and the Nationality Leaving Date Begin Qualifier would be the same, in particular when it comes to eras. For example, “Victorian Era” can be both the Nationality Leaving Date Begin and the Nationality Leaving Date Begin Qualifier. Determining what eras the qualifiers will entail (through the vocabulary used to handle them) will thus be paramount.<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Nationality Leaving Date Begin Qualifier: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|There can be more than one qualifier at once for a single Leaving Date Begin (e.g. “BCE” and “BC”, which is the same information, the former being qualified using the non-christian acronym for “Before Common Era” and the latter using the christian “Before Christ”).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020), [(Wikipedia 2019o)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019o), [(Wikipedia 2019r)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019r), [(Wikipedia 2019w)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019w)|

---

## Nationality Leaving Date End

|---|---|
|**Scope**|This field designates the latest temporal instant the actor formally stopped belonging to a politically autonomous entity endowed with national independence (holding a nationality status).|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Nationality](#nationality)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:PP145i\_left\_by -\> crm:E86\_Leaving -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82b\_end\_of\_the\_end -\> **xsd:dateTime**</span>|
|**Target Model View(s)**|[Nationality, Nationhood and Community with E74 Group](https://chin-rcip.github.io/collections-model/target-model/current/identification#nationality-nationhood-and-community-with-e74-group)|
|**Semantic Valuation**|*Low*: The value provided temporalizes the beginning of the event, but this information cannot be automatically extracted and formatted.<br><br>*Medium*: The date can be automatically extracted from the value provided (and from textual content that surrounds it if applicable) and can be formatted using the YYYY-MM-DD convention.<br>Accepted Value Type(s): String<br><br>*High*: The date is the sole value provided and is formatted using the date convention.<br>Accepted Value Type(s): DateTime (YYYY-MM-DDThh:mm:ss)|
|**Typical Case(s)**|Janet Cardiff (Actor Appellation) is a Canadian (Nationality) artist (Occupation Type) born on 1957-03-15 (Nationality Joining Date Begin & Nationality Joining Date End) and who was active as an artist as of 1995.<br><br>Margaret Wade Labarge (Actor Appellation) was born in New York City in 1916 (Nationality “American”; Joining Date Begin “1916-07-18”) and moved to Canada with her husband in 1940. She renounced her US citizenship (Nationality “American”; Leaving Date Begin “1939”; Leaving Date Begin Qualifier “after”) and became a Canadian citizen (Nationality “Canadian”, Joining Date Begin “1940”, Joining Date Begin Qualifier “or after”; Joining Date End “1940”, Joining Date End Qualifier “after”), which she remained until her death on August 31, 2009 (Leaving Date Begin and Leaving Date End “2009-08-31”).|
|**Edge Case(s)**|Margaret Wade Labarge (Actor Appellation) was born in New York City in 1916 (Nationality “American”; Joining Date Begin “1916-07-18”) and moved to Canada with her husband in 1940. She renounced her US citizenship (Nationality “American”; Leaving Date Begin “1939”; Leaving Date Begin Qualifier “after”) and became a Canadian citizen (Nationality “Canadian”, Joining Date Begin “1940”, Joining Date Begin Qualifier “or after”; Joining Date End “1940”, Joining Date End Qualifier “after”), which she remained until her death on August 31, 2009 (Leaving Date Begin and Leaving Date End “2009-08-31”). It is not clear how many nationalities an actor can hold nor is it established how this information should be recorded (e.g. should begin or end dates be used? can they overlap? should the Joining Date Begin determine the beginning of the process or should it be the official holding of the nationality, considering the process is often several years long?).<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Nationality Leaving Date End: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|CHIN recommends using the following format when entering dates: “YYYY-MM-DD HH:MM:SS”. However, if the data cannot be converted to such a format (such as in the case of an era), a string can be used (e.g. Han Dynasty).|
|**Reference(s)**|[(Le Boeuf et al. 2015, sec. E86 Leaving)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Free Dictionary 2019ab)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019ab)|

---

## Nationality Leaving Date End Qualifier

|---|---|
|**Scope**|This field qualifies the latest temporal instant the actor formally stopped belonging to a politically autonomous entity endowed with national independence (holding a nationality status).|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Nationality Leaving Date End](#nationality-leaving-date-end)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:PP145i\_left\_by -\> crm:E86\_Leaving -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P80\_end\_is\_qualified\_by -\> **xsd:string**</span>|
|**Target Model View(s)**|[Nationality, Nationhood and Community with E74 Group](https://chin-rcip.github.io/collections-model/target-model/current/identification#nationality-nationhood-and-community-with-e74-group)|
|**Semantic Valuation**|*Low*: The value provided qualifies the date of the event, but this information is unstructured and cannot be automatically formatted.<br><br>*Medium*: The value provided qualifies the date of the event and can be (semi-)automatically cleaned and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String<br><br>*High*: The qualifier is the sole value provided and is structured and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String|
|**Typical Case(s)**|Janet Cardiff (Actor Appellation) is a Canadian (Nationality) artist (Occupation Type) born on 1957-03-15 (Nationality Joining Date Begin & Nationality Joining Date End) and who was active as an artist as of 1995.<br><br>Margaret Wade Labarge (Actor Appellation) was born in New York City in 1916 (Nationality “American”; Joining Date Begin “1916-07-18”) and moved to Canada with her husband in 1940. She renounced her US citizenship (Nationality “American”; Leaving Date Begin “1939”; Leaving Date Begin Qualifier “after”) and became a Canadian citizen (Nationality “Canadian”, Joining Date Begin “1940”, Joining Date Begin Qualifier “or after”; Joining Date End “1940”, Joining Date End Qualifier “after”), which she remained until her death on August 31, 2009 (Leaving Date Begin and Leaving Date End “2009-08-31”).|
|**Edge Case(s)**|There might be cases where the Nationality Leaving Date End and the Nationality Leaving Date End Qualifier would be the same, in particular when it comes to eras. For example, “Victorian Era” can be both the Nationality Leaving Date End and the Nationality Leaving Date End Qualifier. Determining what eras the qualifiers will entail (through the vocabulary used to handle them) will thus be paramount.<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Nationality Leaving Date End Qualifier: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|There can be more than one qualifier at once for a single Leaving Date End (e.g. “BCE” and “BC”, which is the same information, the former being qualified using the non-christian acronym for “Before Common Era” and the latter using the christian “Before Christ”).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020), [(Wikipedia 2019o)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019o), [(Wikipedia 2019r)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019r), [(Wikipedia 2019w)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019w)|

---

## Nationhood

|---|---|
|**Scope**|This field indicates the status of belonging to an autonomous polity endowed with official structures or institutionalized hierarchy (whether formalized or not) as well as shared customs, mores, and practices revolving around common elements such as location, history, language, beliefs, culinary practices, etc. Unlike cultural affiliation type*—*which relies on (self-)identification*—*or nationality*—*which refers to the legal status of being a citizen or a subject of a recognized state*—*,Nationhood describes official belonging with implicit or explicit assent from the group (as represented by its officials or influential members). It refers to the nation the actor identifies / is identified with regardless of their nationality or culture.|
|**Generated Bond(s)**|E74\_Group|
|**Dependency(ies)**|E39\_Actor|
|**Related SQN(s)**|Identity: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P143i\_was\_joined\_by -\> crm:E85\_Joining -\> crm:P144\_joined\_with -\> **crm:E74\_Group** (*-\> crm:E55\_Type -\> crm:P2\_has\_type -\> crm:E55\_Type\["Identity"\]*)<br><br>crm:E39\_Actor -\> crm:P145i\_left\_by -\> crm:E86\_Leaving -\> crm:P146\_separated\_from -\> **crm:E74\_Group** (*-\> crm:E55\_Type -\> crm:P2\_has\_type -\> crm:E55\_Type\["Identity"\]*)</span>|
|**Target Model View(s)**|[Nationality, Nationhood and Community with E74 Group](https://chin-rcip.github.io/collections-model/target-model/current/identification#nationality-nationhood-and-community-with-e74-group)<br><br>Example “Algonquin’, “Mi’kmaq”, “Québécois”, “Réunionais”, etc.|
|**Semantic Valuation**|*Low*: The value provided is a string that cannot be parsed automatically by reconciliation tools but still contains the required information.<br><br>*Medium*: The value provided is a string that can be automatically cleaned and reconciled using controlled vocabularies specified by CHIN. In the event that the value is adequately structured but does not reconcile with any terms from the controlled vocabulary, and provided that it is deemed relevant, CHIN will add the term to the vocabulary.<br>Accepted Value Type(s): String<br><br>*High*: The provided value is a string that can be automatically reconciled with the controlled vocabularies specified by CHIN.<br>Accepted Value Type(s): String, URI|
|**Typical Case(s)**|Rebecca Belmore is an “Anishinaabe” (Community) “Canadian” (Nationality) multidisciplinary artist and member of the “Lac Seul First Nation” (Nationhood). Belmore identifies as “Anishinaabe” (Cultural Affiliation Type).<br><br>Norval Morrisseau, whose Ojibwe name is “ᐅᓵᐚᐱᐦᑯᐱᓀᐦᓯ”, or “Copper Thunderbird” (Actor Appellations) was born March 14, 1932 of the Gregorian Calendar (Nationhood Joining Date Begin and Nationhood Joining Date End, Nationhood Joining Date Begin Qualifier), which corresponds to the “Ziissbaakgoke Giizas/Sugar Moon” (Nationhood Joining Date Begin and Nationhood Joining Date End, Nationhood Joining Date Begin Qualifier and Nationhood Joining Date End Qualifier “Ojibwe Calendar”). He is an “Ojibwe Anishinaabe” (Community) “Canadian” (Nationality) from the “Bingwi Neyaashi Anishinaabek First Nation” (Nationhood) and identified as “Ojibwe” (Cultural Affiliation Type). He died on December 4, 2007 (Nationhood Leaving Date Begin and Nationhood Leaving Date End), which corresponds to the “Mnidoons Giizis/Blue Moon - Big Spirit Moon” (Nationhood Leaving Date Begin and Nationhood Leaving Date End, Nationhood Leaving Date Begin Qualifier and Nationhood Leaving Date End Qualifier “Ojibwe Calendar”).|
|**Edge Case(s)**|Whether to assign provincial nationality (or any other sub-polities of larger ones) to Nationhood or Community could be debated.<br><br>It is also debatable whether Nationhood should be a field reserved for Indigenous actors. In addition, how to handle compounded affiliations (such as “Ojibwe Anishinaabe”) is to be determined.|
|**Value Origin(s)**|Actors Checklist: Nationhood: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|This field accommodates various types of nationhood, including ethnic, civic, tribal, and multicultural nationhood. Nationhood often revolves around shared practices and traditions transmitted from one generation to another, although it is not exclusively the case.<br><br>CHIN does not recommend using this field to record association with a religious order (which should be recorded under “Community”) as the latter revolves around an individual conviction and faith in the truthfulness of specific beliefs more so than belonging to the group itself.<br><br>Polities’ official structures can take the form of different political units such as civil or local government bodies, tribal assemblies, band councils, etc. Although polities often have control of a geographic area or resources, it is not always the case.<br><br>Inclusion of Indigenous-language names for peoples/groups is spotty in both AAT and Wikidata. Generally, English-language/historical names are more likely to be recognized.|
|**Reference(s)**|[(Art & Architecture Thesaurus 2019e)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019e), [(Art & Architecture Thesaurus 2019f)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019f), [(Free Dictionary 2019d)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019d), [(Free Dictionary 2019g)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019g), [(Free Dictionary 2019h)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019h), [(Free Dictionary 2019i)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019i), [(Ontario Native Literacy Coalition 2010)](/collections-model/semantic-paths-specification/current/bibliography#ontario-native-literacy-coalition-2010), [(Wikipedia 2019m)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019m), [(Wikipedia 2019s)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019s), [(Wikipedia 2019u)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019u), [(Wikipedia 2019u)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019u), [(Wikipedia 2019ah)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019ah), [(Wikipedia 2019aj)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019aj)|

---

## Nationhood Joining Date Begin

|---|---|
|**Scope**|This field designates the earliest temporal instant the actor started belonging to an autonomous polity endowed with official structures or institutionalized hierarchy (whether formalized or not) as well as shared customs, mores, and practices revolving around common elements such as location, history, language, beliefs, culinary practices, etc.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Nationhood](#nationhood)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P143i\_was\_joined\_by -\> crm:E85\_Joining -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82a\_begin\_of\_the\_begin -\> **xsd:dateTime**</span>|
|**Target Model View(s)**|[Nationality, Nationhood and Community with E74 Group](https://chin-rcip.github.io/collections-model/target-model/current/identification#nationality-nationhood-and-community-with-e74-group)|
|**Semantic Valuation**|*Low*: The value provided temporalizes the beginning of the event, but this information cannot be automatically extracted and formatted.<br><br>*Medium*: The date can be automatically extracted from the value provided (and from textual content that surrounds it if applicable) and can be formatted using the YYYY-MM-DD convention.<br>Accepted Value Type(s): String<br><br>*High*: The date is the sole value provided and is formatted using the date convention.<br>Accepted Value Type(s): DateTime (YYYY-MM-DDThh:mm:ss)|
|**Typical Case(s)**|Norval Morrisseau, whose Ojibwe name is “ᐅᓵᐚᐱᐦᑯᐱᓀᐦᓯ”, or “Copper Thunderbird” (Actor Appellations) was born March 14, 1932 of the Gregorian Calendar (Nationhood Joining Date Begin and Nationhood Joining Date End, Nationhood Joining Date Begin Qualifier), which corresponds to the “Ziissbaakgoke Giizas/Sugar Moon” (Nationhood Joining Date Begin and Nationhood Joining Date End, Nationhood Joining Date Begin Qualifier and Nationhood Joining Date End Qualifier “Ojibwe Calendar”). He is an “Ojibwe Anishinaabe” (Community) “Canadian” (Nationality) from the “Bingwi Neyaashi Anishinaabek First Nation” (Nationhood) and identified as “Ojibwe” (Cultural Affiliation Type). He died on December 4, 2007 (Nationhood Leaving Date Begin and Nationhood Leaving Date End), which corresponds to the “Mnidoons Giizis/Blue Moon - Big Spirit Moon” (Nationhood Leaving Date Begin and Nationhood Leaving Date End, Nationhood Leaving Date Begin Qualifier and Nationhood Leaving Date End Qualifier “Ojibwe Calendar”).|
|**Edge Case(s)**|What CHIN considers to be the earliest temporal moment of joining is debatable: does it involve official belonging to the nation through a formal process, or does it start as soon as the actor is in contact with the nation that will later consider them to be a member for example?<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Nationhood Joining Date Begin: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|CHIN recommends using the following format when entering dates: “YYYY-MM-DD HH:MM:SS”. However, if the data cannot be converted to such a format (such as in the case of an era), a string can be used (e.g. Han Dynasty).|
|**Reference(s)**|[(Le Boeuf et al. 2015, sec. E85 Joining)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Free Dictionary 2019aa)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019aa)|

---

## Nationhood Joining Date Begin Qualifier

|---|---|
|**Scope**|This field qualifies the earliest temporal instant the actor started belonging to an autonomous polity endowed with official structures or institutionalized hierarchy (whether formalized or not) as well as shared customs, mores, and practices revolving around common elements such as location, history, language, beliefs, culinary practices, etc.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Nationhood Joining Date Begin](#nationhood-joining-date-begin-qualifier)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P143i\_was\_joined\_by -\> crm:E85\_Joining -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P79\_beginning\_is\_qualified\_by -\> **xsd:string**</span>|
|**Target Model View(s)**|[Nationality, Nationhood and Community with E74 Group](https://chin-rcip.github.io/collections-model/target-model/current/identification#nationality-nationhood-and-community-with-e74-group)|
|**Semantic Valuation**|*Low*: The value provided qualifies the date of the event, but this information is unstructured and cannot be automatically formatted.<br><br>*Medium*: The value provided qualifies the date of the event and can be (semi-)automatically cleaned and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String<br><br>*High*: The qualifier is the sole value provided and is structured and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String|
|**Typical Case(s)**|Norval Morrisseau, whose Ojibwe name is “ᐅᓵᐚᐱᐦᑯᐱᓀᐦᓯ”, or “Copper Thunderbird” (Actor Appellations) was born March 14, 1932 of the Gregorian Calendar (Nationhood Joining Date Begin and Nationhood Joining Date End, Nationhood Joining Date Begin Qualifier), which corresponds to the “Ziissbaakgoke Giizas/Sugar Moon” (Nationhood Joining Date Begin and Nationhood Joining Date End, Nationhood Joining Date Begin Qualifier and Nationhood Joining Date End Qualifier “Ojibwe Calendar”). He is an “Ojibwe Anishinaabe” (Community) “Canadian” (Nationality) from the “Bingwi Neyaashi Anishinaabek First Nation” (Nationhood) and identified as “Ojibwe” (Cultural Affiliation Type). He died on December 4, 2007 (Nationhood Leaving Date Begin and Nationhood Leaving Date End), which corresponds to the “Mnidoons Giizis/Blue Moon - Big Spirit Moon” (Nationhood Leaving Date Begin and Nationhood Leaving Date End, Nationhood Leaving Date Begin Qualifier and Nationhood Leaving Date End Qualifier “Ojibwe Calendar”).|
|**Edge Case(s)**|There might be cases where the Nationhood Joining Date Begin and the Nationhood Joining Date Begin Qualifier would be the same, in particular when it comes to eras. For example, “Victorian Era” can be both the Nationhood Joining Date Begin and the Nationhood Joining Date Begin Qualifier. Determining what eras the qualifiers will entail (through the vocabulary used to handle them) will thus be paramount.<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Nationhood Joining Date Begin Qualifier: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|There can be more than one qualifier at once for a single Joining Date Begin (e.g. “BCE” and “BC”, which is the same information, the former being qualified using the non-christian acronym for “Before Common Era” and the latter using the christian “Before Christ”).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020), [(Wikipedia 2019o)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019o), [(Wikipedia 2019r)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019r), [(Wikipedia 2019w)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019w)|

---

## Nationhood Joining Date End

|---|---|
|**Scope**|This field designates the latest temporal instant the actor started belonging to an autonomous polity endowed with official structures or institutionalized hierarchy (whether formalized or not) as well as shared customs, mores, and practices revolving around common elements such as location, history, language, beliefs, culinary practices, etc.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Nationhood](#nationhood)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P143i\_was\_joined\_by -\> crm:E85\_Joining -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82b\_end\_of\_the\_end -\> **xsd:dateTime**</span>|
|**Target Model View(s)**|[Nationality, Nationhood and Community with E74 Group](https://chin-rcip.github.io/collections-model/target-model/current/identification#nationality-nationhood-and-community-with-e74-group)|
|**Semantic Valuation**|*Low*: The value provided temporalizes the beginning of the event, but this information cannot be automatically extracted and formatted.<br><br>*Medium*: The date can be automatically extracted from the value provided (and from textual content that surrounds it if applicable) and can be formatted using the YYYY-MM-DD convention.<br>Accepted Value Type(s): String<br><br>*High*: The date is the sole value provided and is formatted using the date convention.<br>Accepted Value Type(s): DateTime (YYYY-MM-DDThh:mm:ss)|
|**Typical Case(s)**|Norval Morrisseau, whose Ojibwe name is “ᐅᓵᐚᐱᐦᑯᐱᓀᐦᓯ”, or “Copper Thunderbird” (Actor Appellations) was born March 14, 1932 of the Gregorian Calendar (Nationhood Joining Date Begin and Nationhood Joining Date End, Nationhood Joining Date Begin Qualifier), which corresponds to the “Ziissbaakgoke Giizas/Sugar Moon” (Nationhood Joining Date Begin and Nationhood Joining Date End, Nationhood Joining Date Begin Qualifier and Nationhood Joining Date End Qualifier “Ojibwe Calendar”). He is an “Ojibwe Anishinaabe” (Community) “Canadian” (Nationality) from the “Bingwi Neyaashi Anishinaabek First Nation” (Nationhood) and identified as “Ojibwe” (Cultural Affiliation Type). He died on December 4, 2007 (Nationhood Leaving Date Begin and Nationhood Leaving Date End), which corresponds to the “Mnidoons Giizis/Blue Moon - Big Spirit Moon” (Nationhood Leaving Date Begin and Nationhood Leaving Date End, Nationhood Leaving Date Begin Qualifier and Nationhood Leaving Date End Qualifier “Ojibwe Calendar”).|
|**Edge Case(s)**|What CHIN considers to be the latest temporal moment of joining is debatable: does it involve official belonging to the nation through a formal process, or does it start as soon as the actor is in contact with the nation that will later consider them to be a member, with the Nationhood Joining Date End being the date of official granting of the status for example?<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Nationhood Joining Date End: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|CHIN recommends using the following format when entering dates: “YYYY-MM-DD HH:MM:SS”. However, if the data cannot be converted to such a format (such as in the case of an era), a string can be used (e.g. Han Dynasty).|
|**Reference(s)**|[(Le Boeuf et al. 2015, sec. E85 Joining)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Free Dictionary 2019aa)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019aa)|

---

## Nationhood Joining Date End Qualifier

|---|---|
|**Scope**|This field qualifies the latest temporal instant the actor started belonging to an autonomous polity endowed with official structures or institutionalized hierarchy (whether formalized or not) as well as shared customs, mores, and practices revolving around common elements such as location, history, language, beliefs, culinary practices, etc.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Nationhood Joining Date End](#nationhood-joining-date-end)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P143i\_was\_joined\_by -\> crm:E85\_Joining -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P80\_end\_is\_qualified\_by -\> **xsd:string**</span>|
|**Target Model View(s)**|[Nationality, Nationhood and Community with E74 Group](https://chin-rcip.github.io/collections-model/target-model/current/identification#nationality-nationhood-and-community-with-e74-group)|
|**Semantic Valuation**|*Low*: The value provided qualifies the date of the event, but this information is unstructured and cannot be automatically formatted.<br><br>*Medium*: The value provided qualifies the date of the event and can be (semi-)automatically cleaned and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String<br><br>*High*: The qualifier is the sole value provided and is structured and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String|
|**Typical Case(s)**|Norval Morrisseau, whose Ojibwe name is “ᐅᓵᐚᐱᐦᑯᐱᓀᐦᓯ”, or “Copper Thunderbird” (Actor Appellations) was born March 14, 1932 of the Gregorian Calendar (Nationhood Joining Date Begin and Nationhood Joining Date End, Nationhood Joining Date Begin Qualifier), which corresponds to the “Ziissbaakgoke Giizas/Sugar Moon” (Nationhood Joining Date Begin and Nationhood Joining Date End, Nationhood Joining Date Begin Qualifier and Nationhood Joining Date End Qualifier “Ojibwe Calendar”). He is an “Ojibwe Anishinaabe” (Community) “Canadian” (Nationality) from the “Bingwi Neyaashi Anishinaabek First Nation” (Nationhood) and identified as “Ojibwe” (Cultural Affiliation Type). He died on December 4, 2007 (Nationhood Leaving Date Begin and Nationhood Leaving Date End), which corresponds to the “Mnidoons Giizis/Blue Moon - Big Spirit Moon” (Nationhood Leaving Date Begin and Nationhood Leaving Date End, Nationhood Leaving Date Begin Qualifier and Nationhood Leaving Date End Qualifier “Ojibwe Calendar”).|
|**Edge Case(s)**|There might be cases where the Nationhood Joining Date End and the Nationhood Joining Date End Qualifier would be the same, in particular when it comes to eras. For example, “Victorian Era” can be both the Nationhood Joining Date End and the Nationhood Joining Date End Qualifier. Determining what eras the qualifiers will entail (through the vocabulary used to handle them) will thus be paramount.<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Nationhood Joining Date End Qualifier: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|There can be more than one qualifier at once for a single Joining Date End (e.g. “BCE” and “BC”, which is the same information, the former being qualified using the non-christian acronym for “Before Common Era” and the latter using the christian “Before Christ”).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020), [(Wikipedia 2019o)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019o), [(Wikipedia 2019r)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019r), [(Wikipedia 2019w)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019w)|

---

## Nationhood Leaving Date Begin

|---|---|
|**Scope**|This field designates the earliest temporal instant the actor stopped belonging to an autonomous polity endowed with official structures or institutionalized hierarchy (whether formalized or not) as well as shared customs, mores, and practices revolving around common elements such as location, history, language, beliefs, culinary practices, etc.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Nationhood](#nationhood)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:PP145i\_left\_by -\> crm:E86\_Leaving -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82a\_begin\_of\_the\_begin -\> **xsd:dateTime**</span>|
|**Target Model View(s)**|[Nationality, Nationhood and Community with E74 Group](https://chin-rcip.github.io/collections-model/target-model/current/identification#nationality-nationhood-and-community-with-e74-group)|
|**Semantic Valuation**|*Low*: The value provided temporalizes the beginning of the event, but this information cannot be automatically extracted and formatted.<br><br>*Medium*: The date can be automatically extracted from the value provided (and from textual content that surrounds it if applicable) and can be formatted using the YYYY-MM-DD convention.<br>Accepted Value Type(s): String<br><br>*High*: The date is the sole value provided and is formatted using the date convention.<br>Accepted Value Type(s): DateTime (YYYY-MM-DDThh:mm:ss)|
|**Typical Case(s)**|Norval Morrisseau, whose Ojibwe name is “ᐅᓵᐚᐱᐦᑯᐱᓀᐦᓯ”, or “Copper Thunderbird” (Actor Appellations) was born March 14, 1932 of the Gregorian Calendar (Nationhood Joining Date Begin and Nationhood Joining Date End, Nationhood Joining Date Begin Qualifier), which corresponds to the “Ziissbaakgoke Giizas/Sugar Moon” (Nationhood Joining Date Begin and Nationhood Joining Date End, Nationhood Joining Date Begin Qualifier and Nationhood Joining Date End Qualifier “Ojibwe Calendar”). He is an “Ojibwe Anishinaabe” (Community) “Canadian” (Nationality) from the “Bingwi Neyaashi Anishinaabek First Nation” (Nationhood) and identified as “Ojibwe” (Cultural Affiliation Type). He died on December 4, 2007 (Nationhood Leaving Date Begin and Nationhood Leaving Date End), which corresponds to the “Mnidoons Giizis/Blue Moon - Big Spirit Moon” (Nationhood Leaving Date Begin and Nationhood Leaving Date End, Nationhood Leaving Date Begin Qualifier and Nationhood Leaving Date End Qualifier “Ojibwe Calendar”).|
|**Edge Case(s)**|What constitutes the leaving of a nation should be defined, or even if a nation can be left. Is it only an actor that can leave a nation, or can he be officially banned?<br><br>Some cultures might consider Nationhood to be an “eternal” belonging in the sense that it would not end with the death of the Actor, such that the leaving date might not be inferrable.<br><br>The best way to represent the ending of a nation is also unclear. For example, New France could be considered to be a Nation that started with the exploration of the Gulf of Saint Lawrence by Jacques Cartier (Actor Appellation) in 1534 (Nationhood Joining Date Begin). New France ended on February 10, 1763 (Nationhood Leaving Date End) with the Treaty of Paris (which could be a Nationhood Leaving Date End Qualifier although it is in itself an event) after Pierre Fran¡ois de Rigaud, the last French governor-general of New France, surrendered to Britain September 8, 1760 (Nationhood Leaving Date Begin). In this case, would all actors of New France “leave” the Nation and “join” the British nationality? In this case, one way of joining Nationality would have to be through conquest.<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Nationhood Leaving Date Begin: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|CHIN recommends using the following format when entering dates: “YYYY-MM-DD HH:MM:SS”. However, if the data cannot be converted to such a format (such as in the case of an era), a string can be used (e.g. Han Dynasty).|
|**Reference(s)**|[(Le Boeuf et al. 2015, sec. E86 Leaving)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Free Dictionary 2019ab)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019ab)|

---

## Nationhood Leaving Date Begin Qualifier

|---|---|
|**Scope**|This field qualifies the earliest temporal instant the actor stopped belonging to an autonomous polity endowed with official structures or institutionalized hierarchy (whether formalized or not) as well as shared customs, mores, and practices revolving around common elements such as location, history, language, beliefs, culinary practices, etc.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Nationhood Leaving Date Begin](#nationhood-leaving-date-begin)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P145i\_left\_by -\> crm:E86\_Leaving -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P79\_beginning\_is\_qualified\_by -\> **xsd:string**</span>|
|**Target Model View(s)**|[Nationality, Nationhood and Community with E74 Group](https://chin-rcip.github.io/collections-model/target-model/current/identification#nationality-nationhood-and-community-with-e74-group)|
|**Semantic Valuation**|*Low*: The value provided qualifies the date of the event, but this information is unstructured and cannot be automatically formatted.<br><br>*Medium*: The value provided qualifies the date of the event and can be (semi-)automatically cleaned and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String<br><br>*High*: The qualifier is the sole value provided and is structured and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String|
|**Typical Case(s)**|Norval Morrisseau, whose Ojibwe name is “ᐅᓵᐚᐱᐦᑯᐱᓀᐦᓯ”, or “Copper Thunderbird” (Actor Appellations) was born March 14, 1932 of the Gregorian Calendar (Nationhood Joining Date Begin and Nationhood Joining Date End, Nationhood Joining Date Begin Qualifier), which corresponds to the “Ziissbaakgoke Giizas/Sugar Moon” (Nationhood Joining Date Begin and Nationhood Joining Date End, Nationhood Joining Date Begin Qualifier and Nationhood Joining Date End Qualifier “Ojibwe Calendar”). He is an “Ojibwe Anishinaabe” (Community) “Canadian” (Nationality) from the “Bingwi Neyaashi Anishinaabek First Nation” (Nationhood) and identified as “Ojibwe” (Cultural Affiliation Type). He died on December 4, 2007 (Nationhood Leaving Date Begin and Nationhood Leaving Date End), which corresponds to the “Mnidoons Giizis/Blue Moon - Big Spirit Moon” (Nationhood Leaving Date Begin and Nationhood Leaving Date End, Nationhood Leaving Date Begin Qualifier and Nationhood Leaving Date End Qualifier “Ojibwe Calendar”).|
|**Edge Case(s)**|There might be cases where the Nationhood Leaving Date Begin and the Nationhood Leaving Date Begin Qualifier would be the same, in particular when it comes to eras. For example, “Victorian Era” can be both the Nationhood Leaving Date Begin and the Nationhood Leaving Date Begin Qualifier. Determining what eras the qualifiers will entail (through the vocabulary used to handle them) will thus be paramount.<br><br>The best way to represent the ending of a nation is also unclear. For example, New France could be considered to be a Nation that started with the exploration of the Gulf of Saint Lawrence by Jacques Cartier (Actor Appellation) in 1534 (Nationhood Joining Date Begin). New France ended on February 10, 1763 (Nationhood Leaving Date End) with the Treaty of Paris (which could be a Nationhood Leaving Date End Qualifier although it is in itself an event) after Pierre Fran¡ois de Rigaud, the last French governor-general of New France, surrendered to Britain September 8, 1760 (Nationhood Leaving Date Begin). In this case, would all actors of New France “leave” the Nation and “join” the British nationality? In this case, one way of joining Nationality would have to be through conquest.<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Nationhood Leaving Date Begin Qualifier: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|There can be more than one qualifier at once for a single Leaving Date Begin (e.g. “BCE” and “BC”, which is the same information, the former being qualified using the non-christian acronym for “Before Common Era” and the latter using the christian “Before Christ”).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020), [(Wikipedia 2019o)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019o), [(Wikipedia 2019r)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019r), [(Wikipedia 2019w)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019w)|

---

## Nationhood Leaving Date End

|---|---|
|**Scope**|This field designates the latest temporal instant the actor stopped belonging to an autonomous polity endowed with official structures or institutionalized hierarchy (whether formalized or not) as well as shared customs, mores, and practices revolving around common elements such as location, history, language, beliefs, culinary practices, etc.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Nationhood](#nationhood)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:PP145i\_left\_by -\> crm:E86\_Leaving -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82b\_end\_of\_the\_end -\> **xsd:dateTime**</span>|
|**Target Model View(s)**|[Nationality, Nationhood and Community with E74 Group](https://chin-rcip.github.io/collections-model/target-model/current/identification#nationality-nationhood-and-community-with-e74-group)|
|**Semantic Valuation**|*Low*: The value provided temporalizes the beginning of the event, but this information cannot be automatically extracted and formatted.<br><br>*Medium*: The date can be automatically extracted from the value provided (and from textual content that surrounds it if applicable) and can be formatted using the YYYY-MM-DD convention.<br>Accepted Value Type(s): String<br><br>*High*: The date is the sole value provided and is formatted using the date convention.<br>Accepted Value Type(s): DateTime (YYYY-MM-DDThh:mm:ss)|
|**Typical Case(s)**|Norval Morrisseau, whose Ojibwe name is “ᐅᓵᐚᐱᐦᑯᐱᓀᐦᓯ”, or “Copper Thunderbird” (Actor Appellations) was born March 14, 1932 of the Gregorian Calendar (Nationhood Joining Date Begin and Nationhood Joining Date End, Nationhood Joining Date Begin Qualifier), which corresponds to the “Ziissbaakgoke Giizas/Sugar Moon” (Nationhood Joining Date Begin and Nationhood Joining Date End, Nationhood Joining Date Begin Qualifier and Nationhood Joining Date End Qualifier “Ojibwe Calendar”). He is an “Ojibwe Anishinaabe” (Community) “Canadian” (Nationality) from the “Bingwi Neyaashi Anishinaabek First Nation” (Nationhood) and identified as “Ojibwe” (Cultural Affiliation Type). He died on December 4, 2007 (Nationhood Leaving Date Begin and Nationhood Leaving Date End), which corresponds to the “Mnidoons Giizis/Blue Moon - Big Spirit Moon” (Nationhood Leaving Date Begin and Nationhood Leaving Date End, Nationhood Leaving Date Begin Qualifier and Nationhood Leaving Date End Qualifier “Ojibwe Calendar”).|
|**Edge Case(s)**|The best way to represent the ending of a nation is also unclear. For example, New France could be considered to be a Nation that started with the exploration of the Gulf of Saint Lawrence by Jacques Cartier (Actor Appellation) in 1534 (Nationhood Joining Date Begin). New France ended on February 10, 1763 (Nationhood Leaving Date End) with the Treaty of Paris (which could be a Nationhood Leaving Date End Qualifier although it is in itself an event) after Pierre Fran¡ois de Rigaud, the last French governor-general of New France, surrendered to Britain September 8, 1760 (Nationhood Leaving Date Begin). In this case, would all actors of New France “leave” the Nation and “join” the British nationality? In this case, one way of joining Nationality would have to be through conquest.<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Nationhood Leaving Date End: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|CHIN recommends using the following format when entering dates: “YYYY-MM-DD HH:MM:SS”. However, if the data cannot be converted to such a format (such as in the case of an era), a string can be used (e.g. Han Dynasty).|
|**Reference(s)**|[(Le Boeuf et al. 2015, sec. E86 Leaving)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Free Dictionary 2019ab)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019ab)|

---

## Nationhood Leaving Date End Qualifier

|---|---|
|**Scope**|This field qualifies the latest temporal instant the actor stopped belonging to an autonomous polity endowed with official structures or institutionalized hierarchy (whether formalized or not) as well as shared customs, mores, and practices revolving around common elements such as location, history, language, beliefs, culinary practices, etc.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Nationhood Leaving Date End](#nationhood-leaving-date-end)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:PP145i\_left\_by -\> crm:E86\_Leaving -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P80\_end\_is\_qualified\_by -\> **xsd:string**</span>|
|**Target Model View(s)**|[Nationality, Nationhood and Community with E74 Group](https://chin-rcip.github.io/collections-model/target-model/current/identification#nationality-nationhood-and-community-with-e74-group)|
|**Semantic Valuation**|*Low*: The value provided qualifies the date of the event, but this information is unstructured and cannot be automatically formatted.<br><br>*Medium*: The value provided qualifies the date of the event and can be (semi-)automatically cleaned and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String<br><br>*High*: The qualifier is the sole value provided and is structured and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String|
|**Typical Case(s)**|Norval Morrisseau, whose Ojibwe name is “ᐅᓵᐚᐱᐦᑯᐱᓀᐦᓯ”, or “Copper Thunderbird” (Actor Appellations) was born March 14, 1932 of the Gregorian Calendar (Nationhood Joining Date Begin and Nationhood Joining Date End, Nationhood Joining Date Begin Qualifier), which corresponds to the “Ziissbaakgoke Giizas/Sugar Moon” (Nationhood Joining Date Begin and Nationhood Joining Date End, Nationhood Joining Date Begin Qualifier and Nationhood Joining Date End Qualifier “Ojibwe Calendar”). He is an “Ojibwe Anishinaabe” (Community) “Canadian” (Nationality) from the “Bingwi Neyaashi Anishinaabek First Nation” (Nationhood) and identified as “Ojibwe” (Cultural Affiliation Type). He died on December 4, 2007 (Nationhood Leaving Date Begin and Nationhood Leaving Date End), which corresponds to the “Mnidoons Giizis/Blue Moon - Big Spirit Moon” (Nationhood Leaving Date Begin and Nationhood Leaving Date End, Nationhood Leaving Date Begin Qualifier and Nationhood Leaving Date End Qualifier “Ojibwe Calendar”).|
|**Edge Case(s)**|There might be cases where the Nationhood Leaving Date End and the Nationhood Leaving Date End Qualifier would be the same, in particular when it comes to eras. For example, “Victorian Era” can be both the Nationhood Leaving Date End and the Nationhood Leaving Date End Qualifier. Determining what eras the qualifiers will entail (through the vocabulary used to handle them) will thus be paramount.<br><br>The best way to represent the ending of a nation is also unclear. For example, New France could be considered to be a Nation that started with the exploration of the Gulf of Saint Lawrence by Jacques Cartier (Actor Appellation) in 1534 (Nationhood Joining Date Begin). New France ended on February 10, 1763 (Nationhood Leaving Date End) with the Treaty of Paris (which could be a Nationhood Leaving Date End Qualifier although it is in itself an event) after Pierre Fran¡ois de Rigaud, the last French governor-general of New France, surrendered to Britain September 8, 1760 (Nationhood Leaving Date Begin). In this case, would all actors of New France “leave” the Nation and “join” the British nationality? In this case, one way of joining Nationality would have to be through conquest.<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Nationhood Leaving Date End Qualifier: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|There can be more than one qualifier at once for a single Leaving Date End (e.g. “BCE” and “BC”, which is the same information, the former being qualified using the non-christian acronym for “Before Common Era” and the latter using the christian “Before Christ”).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020), [(Wikipedia 2019o)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019o), [(Wikipedia 2019r)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019r), [(Wikipedia 2019w)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019w)|

---

## Object Appellation

|---|---|
|**Scope**|This field designates the entire identifying word(s), number(s), symbol(s) or code(s) by which an object is distinguished from others, such as its common noun, title, or designation as it has been attributed by a contributing institution. It is an identifying agreed upon term that is descriptive or connotative. If it is made of the concatenation of numerous parts, it should include all of them (such as honorifics, titles, etc.).|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|E22\_Human-Made\_Object|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P02i\_is\_range\_of -\> crm:PC14\_carried\_out\_by -\> crm:P01\_has\_domain -\> crm:E12\_Production -\> crm:P108\_has\_produced -\> crm:E22\_Human-Made\_Object -\> crm:P1\_is\_identified\_by -\> crm:E41\_Appellation + crm:E33\_Linguistic\_Object -\> crm:P190\_has\_symbolic\_content -\> **xsd:string**</span>|
|**Target Model View(s)**|[Artefact (Before the Development of the Objects Facet)](https://chin-rcip.github.io/collections-model/target-model/current/artefacts#artefact-before-the-development-of-the-objects-facet)|
|**Semantic Valuation**|*Low*: The provided values contain unstructured information of the appellation, such as it cannot be parsed automatically by reconciliation tools, but still contains the required information.<br><br>*Medium*: The provided values contain structured information that can be automatically cleaned and reconciled with other entities in other datasets.<br>Accepted Value Type(s): String<br><br>*High*: The provided values only contain structured information that can be automatically reconciled with other entities in other datasets.<br>Accepted Value Type(s): String|
|**Typical Case(s)**|*Flightstop* (Object Appellation; Object Appellation Language “English”; Object Appellation Type “Title”; Object Appellation Preference “Preferred”) is a sculpture (Object Medium and Technique) by artist (Occupation Type) Michael Snow (Actor Appellation), sometimes titled *Flight Stop*(Object Appellation; Object Appellation Language “English”; Object Appellation Type “Title”; Object Appellation Preference “Non-Preferred”). It has been displayed at the Toronto Eaton Centre (Object Record Contributor Appellation) since 1979 (Object Record Date Begin) when it was made and installed.|
|**Edge Case(s)**|How to distinguish works that are titled *Untitled*and those that are not titled might be problematic when ingesting the data. Conversely, it would be difficult to distinguish an object for there is no title from an object for which we do not have the title.<br><br>Marie-Guillemine Benoist’s *Portrait of Madeleine*was formerly titled *Portrait of a Negress*. Only recent scholarship has established the sitter’s name as “Madeleine”, although her last name remains unknown. There are a number of works in Canadian collections that have offensive or otherwise insensitive titles fraught with racist and colonialist terminology. handling such appellations, and there level of preference, will have to be determined by CHIN. Should such titles be displayed? Should they be non-preferred? Should there be an Object Appellation Type to signal revision (e.g. Revised Titled) with a prompt to generate a note as to why the title was revised?|
|**Value Origin(s)**|Actors Checklist: Object Appellation: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|Bilingually named objects should be recorded as having two different appellations.|
|**Reference(s)**|[(Art & Architecture Thesaurus 2019d)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019d), [(Le Boeuf et al. 2015, sec. E82 Actor Appellation)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Le Boeuf et al. 2015, sec. E41 Appellation)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Free Dictionary 2019a)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019a), [(Free Dictionary 2019f)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019f)|

---

## Object Appellation Language

|---|---|
|**Scope**|This field indicates the natural or technical language the Object Appellation is written in. This is a qualifying field so that it necessarily relates to an Object Appellation and there cannot be a Language of the Object Appellation without an Object Appellation.|
|**Generated Bond(s)**|E56\_Language|
|**Dependency(ies)**|[Object Appellation](#object-appellation)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P02i\_is\_range\_of -\> crm:PC14\_carried\_out\_by -\> crm:P01\_has\_domain -\> crm:E12\_Production -\> crm:P108\_has\_produced -\> crm:E22\_Human-Made\_Object -\> crm:P1\_is\_identified\_by -\> crm:E41\_Appellation + crm:E33\_Linguistic\_Object -\> crm:P72\_has\_language -\> **crm:E56\_Language**</span>|
|**Target Model View(s)**|[Artefact (Before the Development of the Objects Facet)](https://chin-rcip.github.io/collections-model/target-model/current/artefacts#artefact-before-the-development-of-the-objects-facet)|
|**Semantic Valuation**|*Low*: The value provided is a string that cannot be parsed automatically by reconciliation tools but still contains the required information.<br><br>*Medium*: The value provided is a string that can be automatically cleaned and reconciled using controlled vocabularies specified by CHIN. In the event that the value is adequately structured but does not reconcile with any terms from the controlled vocabulary, and provided that it is deemed relevant, CHIN will add the term to the vocabulary.<br>Accepted Value Type(s): String<br><br>*High*: The provided value is a string that can be automatically reconciled with the controlled vocabularies specified by CHIN.<br>Accepted Value Type(s): String, URI|
|**Typical Case(s)**|*Flightstop* (Object Appellation; Object Appellation Language “English”; Object Appellation Type “Title”; Object Appellation Preference “Preferred”) is a sculpture (Object Medium and Technique) by artist (Occupation Type) Michael Snow (Actor Appellation), sometimes titled *Flight Stop*(Object Appellation; Object Appellation Language “English”; Object Appellation Type “Title”; Object Appellation Preference “Non-Preferred”). It has been displayed at the Toronto Eaton Centre (Object Record Contributor Appellation) since 1979 (Object Record Date Begin) when it was made and installed.|
|**Edge Case(s)**|The same bilingual considerations that apply to Actor Appellations also apply to Object Appellations. It is impossible to assign a single language to a Bilingual Object Appellation. As such, would the Object Appellation Language accomodate a list of languages as values?|
|**Value Origin(s)**|Actors Checklist: Object Appellation Language: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|Internationally or nationally agreed codes and terminologies can be used, and the field accommodates all UTF-8 compliant languages.<br><br>The language of the Language of the Object Appellation can differ from that of the Language of the Object Appellation (for example, the Actor Appellation can be ᐃᓱᒪ, yet the Actor Appellation Language can be “Inuktitut” rather than “ᐃᓄᒃᑎᑐᑦ”).<br><br>*Regarding the “Expected Value” link - Lexvo does not have any browse or search capability for identifying languages - you can keysmash into Lexvo and it will generate a URI for "hsdjkhsdhf" without verifying whether this is a recognized language or not. In order to find language URIs on Lexvo (as opposed to terms in a language), you need to look up by ISO-639 code. The ISO-639 Code Tables do not allow any browsing, only free searching, and do not cross-reference to geographic region. So the effort involved in verifying whether languages provided on the FNMIIO spreadsheet are recognized as languages with URIs or have ISO codes is far too much at this stage given that 99.9% of museum data is in English or French. This is something I would come back to once I have complete or near-complete datasets for all other fields.*|
|**Reference(s)**|[(Le Boeuf et al. 2015, sec. E56 Language)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Wikipedia 2019ae)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019ae)|

---

## Object Appellation Precedence

|---|---|
|**Scope**|This field indicates if the institution contributing the data considers the related Object Appellation to have precedence over other, alternative Object Appellations. This is a qualifying field that is used to assess priority and distinguish preferred terms from non-preferred terms so that it necessarily relates to an Object Appellation and there cannot be a Preference of the Object Appellation without an Object Appellation.|
|**Generated Bond(s)**|E55\_Type|
|**Dependency(ies)**|[Object Appellation](#object-appellation)|
|**Related SQN(s)**|Precedence: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P02i\_is\_range\_of -\> crm:PC14\_carried\_out\_by -\> crm:P01\_has\_domain -\> crm:E12\_Production -\> crm:P108\_has\_produced -\> crm:E22\_Human-Made\_Object -\> crm:P1\_is\_identified\_by -\> crm:E41\_Appellation + crm:E33\_Linguistic\_Object -\> crm:P2\_has\_type -\> **crm:E55\_Type** (*-\> crm:P2\_has\_type -\> crm:E55\_Type\[“Precedence”\]*)</span>|
|**Target Model View(s)**|[Artefact (Before the Development of the Objects Facet)](https://chin-rcip.github.io/collections-model/target-model/current/artefacts#artefact-before-the-development-of-the-objects-facet)|
|**Semantic Valuation**|*Low*: The value provided is a string that cannot be parsed automatically by reconciliation tools but still contains the required information.<br><br>*Medium*: The value provided is a string that can be automatically cleaned and reconciled using controlled vocabularies specified by CHIN. In the event that the value is adequately structured but does not reconcile with any terms from the controlled vocabulary, and provided that it is deemed relevant, CHIN will add the term to the vocabulary.<br>Accepted Value Type(s): String<br><br>*High*: The provided value is a string that can be automatically reconciled with the controlled vocabularies specified by CHIN.<br>Accepted Value Type(s): String, URI|
|**Typical Case(s)**|*Flightstop* (Object Appellation; Object Appellation Language “English”; Object Appellation Type “Title”; Object Appellation Preference “Preferred”) is a sculpture (Object Medium and Technique) by artist (Occupation Type) Michael Snow (Actor Appellation), sometimes titled *Flight Stop*(Object Appellation; Object Appellation Language “English”; Object Appellation Type “Title”; Object Appellation Preference “Non-Preferred”). It has been displayed at the Toronto Eaton Centre (Object Record Contributor Appellation) since 1979 (Object Record Date Begin) when it was made and installed.|
|**Edge Case(s)**|Marie-Guillemine Benoist’s *Portrait of Madeleine*was formerly titled *Portrait of a Negress*. Only recent scholarship has established the sitter’s name as “Madeleine”, although her last name remains unknown. There are a number of works in Canadian collections that have offensive or otherwise insensitive titles fraught with racist and colonialist terminology. handling such appellations, and there level of preference, will have to be determined by CHIN. Should such titles be displayed? Should they be non-preferred? Should there be an Object Appellation Type to signal revision (e.g. Revised Titled) with a prompt to generate a note as to why the title was revised?|
|**Value Origin(s)**|Actors Checklist: Object Appellation Preference: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|An object could have multiple Preferred Appellations if different museums use different appellations as their preferred term. CHIN will not express any preference or ascribe any priority to one over another.<br><br>Should this field be a boolean one? As it is a true/false field, that could maybe be useful?|
|**Reference(s)**|[(Art & Architecture Thesaurus 2019g)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019g), [(Art & Architecture Thesaurus 2019h)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019h), [(Free Dictionary 2019j)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019j)|

---

## Object Appellation Type

|---|---|
|**Scope**|This field qualifies the Object Appellation and conceptually characterizes Object Appellations in order to facilitate identification and belonging to larger entities (such as families or brands).|
|**Generated Bond(s)**|E55\_Type|
|**Dependency(ies)**|[Object Appellation](#object-appellation)|
|**Related SQN(s)**|Appellation Type: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P02i\_is\_range\_of -\> crm:PC14\_carried\_out\_by -\> crm:P01\_has\_domain -\> crm:E12\_Production -\> crm:P108\_has\_produced -\> crm:E22\_Human-Made\_Object -\> crm:P1\_is\_identified\_by -\> crm:E41\_Appellation + crm:E33\_Linguistic\_Object -\> crm:P2\_has\_type -\> **crm:E55\_Type** (*-\> crm:P2\_has\_type -\> crm:E55\_Type\[“Appellation Type”\]*)</span>|
|**Target Model View(s)**|[Artefact (Before the Development of the Objects Facet)](https://chin-rcip.github.io/collections-model/target-model/current/artefacts#artefact-before-the-development-of-the-objects-facet)|
|**Semantic Valuation**|*Low*: The value provided is a string that cannot be parsed automatically by reconciliation tools but still contains the required information.<br><br>*Medium*: The value provided is a string that can be automatically cleaned and reconciled using controlled vocabularies specified by CHIN. In the event that the value is adequately structured but does not reconcile with any terms from the controlled vocabulary, and provided that it is deemed relevant, CHIN will add the term to the vocabulary.<br>Accepted Value Type(s): String<br><br>*High*: The provided value is a string that can be automatically reconciled with the controlled vocabularies specified by CHIN.<br>Accepted Value Type(s): String, URI|
|**Typical Case(s)**|*Flightstop* (Object Appellation; Object Appellation Language “English”; Object Appellation Type “Title”; Object Appellation Preference “Preferred”) is a sculpture (Object Medium and Technique) by artist (Occupation Type) Michael Snow (Actor Appellation), sometimes titled *Flight Stop*(Object Appellation; Object Appellation Language “English”; Object Appellation Type “Title”; Object Appellation Preference “Non-Preferred”). It has been displayed at the Toronto Eaton Centre (Object Record Contributor Appellation) since 1979 (Object Record Date Begin) when it was made and installed.|
|**Edge Case(s)**|Marie-Guillemine Benoist’s *Portrait of Madeleine*was formerly titled *Portrait of a Negress*. Only recent scholarship has established the sitter’s name as “Madeleine”, although her last name remains unknown. There are a number of works in Canadian collections that have offensive or otherwise insensitive titles fraught with racist and colonialist terminology. handling such appellations, and there level of preference, will have to be determined by CHIN. Should such titles be displayed? Should they be non-preferred? Should there be an Object Appellation Type to signal revision (e.g. Revised Titled) with a prompt to generate a note as to why the title was revised?|
|**Value Origin(s)**|Actors Checklist: Object Appellation Type: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|N/A|
|**Reference(s)**|[(Le Boeuf et al. 2015, sec. E55 Type)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Wikipedia 2019ad)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019ad), [(Wikipedia 2019h)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019h)|

---

## Object ID

|---|---|
|**Scope**|This field designates the unique identifying combination of alphanumeric characters assigned to the object by the source institution.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|E22\_Human-Made\_Object|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P02i\_is\_range\_of -\> crm:PC14\_carried\_out\_by -\> crm:P01\_has\_domain -\> crm:E12\_Production -\> crm:P108\_has\_produced -\> crm:E22\_Human-Made\_Object -\> crm:P1\_is\_identified\_by -\> crm:E42\_Identifier -\> crm:P190\_has\_symbolic\_content -\> **xsd:string**</span>|
|**Target Model View(s)**|[Artefact (Before the Development of the Objects Facet)](https://chin-rcip.github.io/collections-model/target-model/current/artefacts#artefact-before-the-development-of-the-objects-facet)|
|**Semantic Valuation**|*Low*: The provided values contain IDs surrounded by other unstructured information such that there is no systematic way to isolate and automatically extract the IDs, whether because of varying ID structures or inconsistent syntax.<br><br>*Medium*: The provided values contain IDs surrounded by other information, but the ID can be systematically isolated and automatically extracted.<br>Accepted Value Type(s): String, Integer<br><br>*High*: The provided values only contain strings that represent the IDs and are unique within the dataset.<br>Accepted Value Type(s): String, Integer|
|**Typical Case(s)**|John William Waterhouse’s *" 'I am half sick of shadows,' said The Lady of Shalott" (Alfred, Lord Tennyson, The Lady of Shalott, Part II)*is a 1915 painting in the Art Gallery of Ontario’s collection with the object number “71/18” (Object ID) assigned by the contributor (Object ID Type “AGO\_ID”).|
|**Edge Case(s)**|Different institutions categorise objects differently. For example, the Tom Thomson Memorial Art Gallery records Don Phillips’ *Triptych*as three objects:<br><br>- Object Appellation: *Triptych (1978) (left panel)*<br>  Object ID: 994.039.1<br>  Object ID Type: TTMAG\_ID<br>- Object Appellation: *Triptych (1978) (centre panel)*<br>  Object ID: 994.039.2<br>  Object ID Type: TTMAG\_ID<br>- Object Appellation: *Triptych (1978) (right panel)*<br>  Object ID: 994.039.3<br>  Object ID Type: TTMAG\_ID<br><br>On the other hand, the Vancouver Art Gallery records B.C. Binning’s *Mariner’s Triptych: For Night Navigation* as a single work:<br><br>  Object Appellation: *Mariner’s Triptych: For Night Navigation*<br>  Object ID: 65.11<br>  Object ID Type: VAG\_ID<br><br>Such cases indicate how multi-parts objects might be problematic to record both in terms of IDs, but also in the case of other fields such as appellations. For the moment, the ID becomes the bearer of the federation of the objects, which CHIN might not have intended and might have to address in the Object ID Type as well.|
|**Value Origin(s)**|Actors Checklist: Object ID: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|This ID is assigned to the object by the institution contributing the information of the record and CHIN has no authority or bearing on it.|
|**Reference(s)**|[(Art & Architecture Thesaurus 2019c)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019c), [(Art & Architecture Thesaurus 2019k)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019k), [(Bekiari et al. 2015, sec. F13 Identifier)](/collections-model/semantic-paths-specification/current/bibliography#bekiari-et-al-2015), [(Wikipedia 2019d)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019d), [(Wikipedia 2019ac)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019ac)|

---

## Object ID Type

|---|---|
|**Scope**|This field specifies which contributor provided an Object ID so that there cannot be an Object ID Type without an Object ID.|
|**Generated Bond(s)**|E55\_Type|
|**Dependency(ies)**|[Object ID](#object-id)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P02i\_is\_range\_of -\> crm:PC14\_carried\_out\_by -\> crm:P01\_has\_domain -\> crm:E12\_Production -\> crm:P108\_has\_produced -\> crm:E22\_Human-Made\_Object -\> crm:P1\_is\_identified\_by -\> crm:E42\_Identifier -\> crm:P2\_has\_type -\> **crm:E55\_Type**</span>|
|**Target Model View(s)**|[Artefact (Before the Development of the Objects Facet)](https://chin-rcip.github.io/collections-model/target-model/current/artefacts#artefact-before-the-development-of-the-objects-facet)|
|**Semantic Valuation**|*Low*: The value provided is a string that cannot be parsed automatically by reconciliation tools but still contains the required information.<br><br>*Medium*: The value provided is a string that can be automatically cleaned and reconciled using controlled vocabularies specified by CHIN. In the event that the value is adequately structured but does not reconcile with any terms from the controlled vocabulary, and provided that it is deemed relevant, CHIN will add the term to the vocabulary.<br>Accepted Value Type(s): String<br><br>*High*: The provided value is a string that can be automatically reconciled with the controlled vocabularies specified by CHIN.<br>Accepted Value Type(s): String, URI|
|**Typical Case(s)**|John William Waterhouse’s *" 'I am half sick of shadows,' said The Lady of Shalott" (Alfred, Lord Tennyson, The Lady of Shalott, Part II)*is a 1915 painting in the Art Gallery of Ontario’s collection with the object number “71/18” (Object ID) assigned by the contributor (Object ID Type “AGO\_ID”).|
|**Edge Case(s)**|Different institutions categorise objects differently. For example, the Tom Thomson Memorial Art Gallery records Don Phillips’ *Triptych*as three objects:<br><br>- Object Appellation: *Triptych (1978) (left panel)*<br>  Object ID: 994.039.1<br>  Object ID Type: TTMAG\_ID<br>- Object Appellation: *Triptych (1978) (centre panel)*<br>  Object ID: 994.039.2<br>  Object ID Type: TTMAG\_ID<br>- Object Appellation: *Triptych (1978) (right panel)*<br>  Object ID: 994.039.3<br>  Object ID Type: TTMAG\_ID<br><br>On the other hand, the Vancouver Art Gallery records B.C. Binning’s *Mariner’s Triptych: For Night Navigation* as a single work:<br><br>  Object Appellation: *Mariner’s Triptych: For Night Navigation*<br>  Object ID: 65.11<br>  Object ID Type: VAG\_ID<br><br>Such cases indicate how multi-parts objects might be problematic to record both in terms of IDs, but also in the case of other fields such as appellations. For the moment, the ID becomes the bearer of the federation of the objects, which CHIN might not have intended and might have to address in the Object ID Type as well.|
|**Value Origin(s)**|Actors Checklist: Object ID Type: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|CHIN generates, lists, and administers these ID Types.|
|**Reference(s)**|[(Le Boeuf et al. 2015, sec. E55 Type)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015)|

---

## Object Image URL

|---|---|
|**Scope**|This field accommodates visual depictions of the object.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|E22\_Human-Made\_Object|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P02i\_is\_range\_of -\> crm:PC14\_carried\_out\_by -\> crm:P01\_has\_domain -\> crm:E12\_Production -\> crm:P108\_has\_produced -\> crm:E22\_Human-Made\_Object -\> crm:P138i\_has\_representation -\> crm:E36\_Visual\_Item -\> crm:P165i\_is\_incorporated\_in -\> crmdig:D1\_Digital\_Object -\> crm:P1\_is\_identified\_by -\> crm:E41\_Appellation -\> crm:P190\_has\_symbolic\_content -\> **xsd:string**</span>|
|**Target Model View(s)**|[Artefact (Before the Development of the Objects Facet)](https://chin-rcip.github.io/collections-model/target-model/current/artefacts#artefact-before-the-development-of-the-objects-facet)|
|**Semantic Valuation**|*Low*: N/A<br><br>*Medium*: N/A<br><br>*High*: The value provided is an URL that follows the W3C conventions on URLs and should not be broken.<br>Accepted Value Type(s): URL|
|**Typical Case(s)**|*Flightstop* (Object Appellation; Object Appellation Language “English”; Object Appellation Type “Title”; Object Appellation Preference “Preferred”) is a sculpture (Object Medium and Technique) by artist (Occupation Type) Michael Snow (Actor Appellation), sometimes titled *Flight Stop* (Object Appellation; Object Appellation Language “English”; Object Appellation Type “Title”; Object Appellation Preference “Non-Preferred”). It has been displayed at the Toronto Eaton Centre (Object Record Contributor Appellation) since 1979 (Object Record Date Begin) when it was made and installed.<br><br>![Flightstop](media/flightstop.jpg)<br><br>[https://upload.wikimedia.org/wikipedia/commons/4/4d/Flight\_Stop\_by\_Michael\_Snow\_-\_Eaton_Center%2C\_Toronto%2C\_Ontario%2C\_Canada\_-\_August\_10%2C\_2015\_01.jpg](https://upload.wikimedia.org/wikipedia/commons/4/4d/Flight_Stop_by_Michael_Snow_-_Eaton_Center%2C_Toronto%2C_Ontario%2C_Canada_-_August_10%2C_2015_01.jpg) (Object Image URL)<br>Snow, Michael. 1979. *Flight Stop*. Toronto, ON: Toronto Eaton Centre. Source by Giorgio Galeotti, [CC BY 4.0](https://creativecommons.org/licenses/by/4.0), via Wikimedia Commons. (Object Image Bibliographical Mention).|
|**Edge Case(s)**|An institution might want to deposit either an image in a format we have not anticipated, or an entirely different type of visual such as a video, a meme, etc.|
|**Value Origin(s)**|Actors Checklist: Object Image: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|*Would this accommodate the image or the URL to the image? What formats are to be expected here?*<br><br>This field is not yet modeled in the Target Model 2.0, but will be in a subsequent version.|
|**Reference(s)**|[(Free Dictionary 2019ai)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019ai)|

---

## Object Image Bibliographical Mention

|---|---|
|**Scope**|This designates an informational statement appended to the Object Image. It provides relevant information to cite the Image such as author, year of creation, title, etc.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Object Image URL](#object-image-url)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P02i\_is\_range\_of -\> crm:PC14\_carried\_out\_by -\> crm:P01\_has\_domain -\> crm:E12\_Production -\> crm:P108\_has\_produced -\> crm:E22\_Human-Made\_Object -\> crm:P138i\_has\_representation -\> crm:E36\_Visual\_Item -\> dct:source -\> **xsd:string**</span>|
|**Target Model View(s)**|[Artefact (Before the Development of the Objects Facet)](https://chin-rcip.github.io/collections-model/target-model/current/artefacts#artefact-before-the-development-of-the-objects-facet)|
|**Semantic Valuation**|*Low*: The value provided is an unstructured string that contains the information of a bibliographic mention.<br><br>*Medium*: The value provided is a string of a bibliographic mention that follows a citation convention that is not the one adopted by CHIN.<br>Accepted Value Type: String<br><br>*High*: The value provided is a string of a bibliographic mention that follows the citation convention adopted by CHIN.<br>Accepted Value Type: String|
|**Typical Case(s)**|*Flightstop* (Object Appellation; Object Appellation Language “English”; Object Appellation Type “Title”; Object Appellation Preference “Preferred”) is a sculpture (Object Medium and Technique) by artist (Occupation Type) Michael Snow (Actor Appellation), sometimes titled *Flight Stop*(Object Appellation; Object Appellation Language “English”; Object Appellation Type “Title”; Object Appellation Preference “Non-Preferred”). It has been displayed at the Toronto Eaton Centre (Object Record Contributor Appellation) since 1979 (Object Record Date Begin) when it was made and installed.<br><br>![Flightstop](media/flightstop.jpg)<br><br>[https://upload.wikimedia.org/wikipedia/commons/4/4d/Flight\_Stop\_by\_Michael\_Snow\_-\_Eaton_Center%2C\_Toronto%2C\_Ontario%2C\_Canada\_-\_August\_10%2C\_2015\_01.jpg](https://upload.wikimedia.org/wikipedia/commons/4/4d/Flight_Stop_by_Michael_Snow_-_Eaton_Center%2C_Toronto%2C_Ontario%2C_Canada_-_August_10%2C_2015_01.jpg) (Object Image URL)<br>Snow, Michael. 1979. *Flight Stop*. Toronto, ON: Toronto Eaton Centre. Source by Giorgio Galeotti, [CC BY 4.0](https://creativecommons.org/licenses/by/4.0), via Wikimedia Commons. (Object Image Bibliographical Mention).|
|**Edge Case(s)**|It might be unclear if the author of the image is that of the work depicted or of the picture. For example, the photo above was not taken by Snow but he is the author of the work and thus the notice of the sculpture is appended rather than that of the image. It might be preferable to specify either with a type or a not what the notice applies to.|
|**Value Origin(s)**|Actors Checklist: Object Image Bibliographical Mention: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|CHIN recommends the use of a recognized and standard citation format such as that of the Chicago Manual of Style (CMS), Modern Languages Association (MLA) or American Psychological Association (APA).<br><br>*Would this be equivalent to a notice? Because then it should be more substantial and the example as well as the definition should reflect that.*<br><br>This field is not yet modeled in the Target Model 2.0, but will be in a subsequent version.|
|**Reference(s)**|[(Free Dictionary 2019ah)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019ah)|

---

## Object Medium

|---|---|
|**Scope**|This field identifies the specific artistic technique or means that enabled the creation of the work. It is often determined by a combination of the materials used and/or the creative methods involved.|
|**Generated Bond(s)**|E55\_Type|
|**Dependency(ies)**|E22\_Human-Made\_Object|
|**Related SQN(s)**|Medium: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P02i\_is\_range\_of -\> crm:PC14\_carried\_out\_by -\> crm:P01\_has\_domain -\> crm:E12\_Production -\> crm:P108\_has\_produced -\> crm:E22\_Human-Made\_Object -\> crm:P2\_has\_type -\> **crm:E55\_Type** (*-\> crm:P2\_has\_type -\> crm:E55\_Type\["Medium"\]*)</span>|
|**Target Model View(s)**|[Artefact(Before the Development of the Objects Facet)](https://chin-rcip.github.io/collections-model/target-model/current/artefacts#artefact-before-the-development-of-the-objects-facet)|
|**Semantic Valuation**|*Low*: The value provided is a string that cannot be parsed automatically by reconciliation tools but still contains the required information.<br><br>*Medium*: The value provided is a string that can be automatically cleaned and reconciled using controlled vocabularies specified by CHIN. In the event that the value is adequately structured but does not reconcile with any terms from the controlled vocabulary, and provided that it is deemed relevant, CHIN will add the term to the vocabulary.<br>Accepted Value Type(s): String<br><br>*High*: The provided value is a string that can be automatically reconciled with the controlled vocabularies specified by CHIN.<br>Accepted Value Type(s): String, URI|
|**Typical Case(s)**|*Mawu-che-hitoowin: A Gathering of People for any Purpose* is a 1992 (Object Record Date Begin & Object Record Date End) installation (Object Medium) by Rebecca Belmore (Actor Appellation).<br><br>*Flightstop* (Object Appellation; Object Appellation Language “English”; Object Appellation Type “Title”; Object Appellation Preference “Preferred”) is a sculpture (Object Medium and Technique) by artist (Occupation Type) Michael Snow (Actor Appellation), sometimes titled *Flight Stop*(Object Appellation; Object Appellation Language “English”; Object Appellation Type “Title”; Object Appellation Preference “Non-Preferred”). It has been displayed at the Toronto Eaton Centre (Object Record Contributor Appellation) since 1979 (Object Record Date Begin) when it was made and installed.|
|**Edge Case(s)**|In the case above, whether to record “sculpture” as a medium, a technique, or both, is up for debate.<br><br>Snarkitecture’s *The Beach*(Object Appellation) is an interactive architectural installation. Can Image Mediums be compounded either by adding various ones to the same node (e.g. “Interaction”, “Architecture”, “Installation”)?|
|**Value Origin(s)**|Actors Checklist: Object Medium: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|Medium is distinct from Technique, although both concepts often intersect and the former is covered in the Actors Facet. Whilst Medium pertains to the object, Technique pertains to the actor.<br><br>This field is not yet modeled in the Target Model 2.0, but will be in a subsequent version.|
|**Reference(s)**|[(Art & Architecture Thesaurus 2019j)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019j), [(Canadian Heritage Information Network (CHIN) 1999)](/collections-model/semantic-paths-specification/current/bibliography#canadian-heritage-information-network-1999), [(Free Dictionary 2019k)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019k), [(Museum of Modern Art 2019)](/collections-model/semantic-paths-specification/current/bibliography#museum-of-modern-art-2019), [(Société des musées du Québec (SMQ) 2015)](/collections-model/semantic-paths-specification/current/bibliography#société-des-musées-du-québec-2015), [(Wikipedia 2019z)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019z)|

---

## Occupation Type

|---|---|
|**Scope**|This field indicates the activities, businesses, professions and other labour-related roles of an actor. These can be either paid or unpaid (contributing directly or indirectly to their livelihood) and they are considered by either the actor or an expert community to be one of their primary endeavours in life. As such the occupation of an actor relates to how they are suited, trained, skilled, or qualified for it.|
|**Generated Bond(s)**|E55\_Type|
|**Dependency(ies)**|E39\_Actor|
|**Related SQN(s)**|Occupation: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P14i\_performed -\> frbr:F51\_Pursuit -\> crm:P2\_has\_type -\> **crm:E55\_Type** (*-\> crm:P2\_has\_type -\> crm:E55\_Type\["Occupation"\]*)</span>|
|**Target Model View(s)**|[Occupation](https://chin-rcip.github.io/collections-model/target-model/current/life-events#occupation)|
|**Semantic Valuation**|*Low*: The value provided is a string that cannot be parsed automatically by reconciliation tools but still contains the required information.<br><br>*Medium*: The value provided is a string that can be automatically cleaned and reconciled using controlled vocabularies specified by CHIN. In the event that the value is adequately structured but does not reconcile with any terms from the controlled vocabulary, and provided that it is deemed relevant, CHIN will add the term to the vocabulary.<br>Accepted Value Type(s): String<br><br>*High*: The provided value is a string that can be automatically reconciled with the controlled vocabularies specified by CHIN.<br>Accepted Value Type(s): String, URI|
|**Typical Case(s)**|Marc Séguin (Actor Appellation) is a visual artist (Occupation Type), novelist (Occupation Type), and farmer (Occupation Type). His first solo exhibition dates back to 1996 (Occupation Type “Visual Artist”; Occupation Date Begin “1996”; Occupation Date Begin Qualifier “before”) and he has practiced in Montréal, QC, Hemmingford, QC and Brooklyn, NY (Occupation Places). His first novel, *La Foi du braconnier*, was published in 2009 (Occupation Type “Novelist”; Occupation Date Begin “2009”; Occupation Date Begin Qualifier “circa”). He owns a family farm in Hemmingford, QC (Occupation Type “Farmer”; Occupation Date Begin “2008”; Occupation Date Begin Qualifier “before”; Occupation Place “Hemmingford, QC”).|
|**Edge Case(s)**|Molly Bobak (Actor Appellation) was a Canadian artist (Occupation Type) who served as Second Lieutenant (Occupation Type) during World War II. She served from November 1942 when she enlisted in the Canadian Women’s Army Corps to September 1945 (Occupation Type “Second Lieutenant”; Occupation Date Begin “1942-11”; Occupation Date End “1945-09”; Occupation Place “Canada”; Occupation Place “Europe”). She sketched in her diaries throughout the war and it is only three years after her enrollment that she was officially made a “War Artist” (Occupation Type) by the Canadian War Artists Selection Committee. In this case, it is unclear how best to record the information as the beginning date of the Occupation Type “War Artist” would be after the end of her serving as such. It is thus unclear if the Occupation Type is determined by the act of completing tasks or by that of holding a position.|
|**Value Origin(s)**|Actors Checklist: Occupation Type: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|A single actor can carry multiple different occupations at one time, just like they can carry a single occupation multiple times simultaneously.|
|**Reference(s)**|[(Art & Architecture Thesaurus 2019r)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019r), [(Free Dictionary 2019s)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019s)), [(Wikipedia 2019b)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019b), [(Wikipedia 2019f)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019f), [(Wikipedia 2019l)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019l), [(Wikipedia 2019p)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019p), [(Wikipedia 2019t)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019t), [(Wikipedia 2019ag)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019ag), [(Wikipedia 2019ai)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019ai)|

---

## Occupation Date Begin

|---|---|
|**Scope**|This field designates the earliest temporal instant the actor assumed the occupation recorded.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Occupation Type](#occupation-type)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P14i\_performed -\> frbr:F51\_Pursuit -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82a\_begin\_of\_the\_begin -\> **xsd:dateTime**</span>|
|**Target Model View(s)**|[Occupation](https://chin-rcip.github.io/collections-model/target-model/current/life-events#occupation)|
|**Semantic Valuation**|*Low*: The value provided temporalizes the beginning of the event, but this information cannot be automatically extracted and formatted.<br><br>*Medium*: The date can be automatically extracted from the value provided (and from textual content that surrounds it if applicable) and can be formatted using the YYYY-MM-DD convention.<br>Accepted Value Type(s): String<br><br>*High*: The date is the sole value provided and is formatted using the date convention.<br>Accepted Value Type(s): DateTime (YYYY-MM-DDThh:mm:ss)|
|**Typical Case(s)**|Marc Séguin (Actor Appellation) is a visual artist (Occupation Type), novelist (Occupation Type), and farmer (Occupation Type). His first solo exhibition dates back to 1996 (Occupation Type “Visual Artist”; Occupation Date Begin “1996”; Occupation Date Begin Qualifier “before”) and he has practiced in Montréal, QC, Hemmingford, QC and Brooklyn, NY (Occupation Places). His first novel, *La Foi du braconnier*, was published in 2009 (Occupation Type “Novelist”; Occupation Date Begin “2009”; Occupation Date Begin Qualifier “circa”). He owns a family farm in Hemmingford, QC (Occupation Type “Farmer”; Occupation Date Begin “2008”; Occupation Date Begin Qualifier “before”; Occupation Place “Hemmingford, QC”).|
|**Edge Case(s)**|Molly Bobak (Actor Appellation) was a Canadian artist (Occupation Type) who served as Second Lieutenant (Occupation Type) during World War II. She served from November 1942 when she enlisted in the Canadian Women’s Army Corps to September 1945 (Occupation Type “Second Lieutenant”; Occupation Date Begin “1942-11”; Occupation Date End “1945-09”; Occupation Place “Canada”; Occupation Place “Europe”). She sketched in her diaries throughout the war and it is only three years after her enrollment that she was officially made a “War Artist” (Occupation Type) by the Canadian War Artists Selection Committee. In this case, it is unclear how best to record the information as the beginning date of the Occupation Type “War Artist” would be after the end of her serving as such. It is thus unclear if the Occupation Type is determined by the act of completing tasks or by that of holding a position.<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Occupation Date Begin: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|CHIN recommends using the following format when entering dates: “YYYY-MM-DD HH:MM:SS”. However, if the data cannot be converted to such a format (such as in the case of an era), a string can be used (e.g. Han Dynasty).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020)|

---

## Occupation Date Begin Qualifier

|---|---|
|**Scope**|This field qualifies the earliest temporal instant the actor assumed the occupation recorded.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Occupation Date Begin](#occupation-date-begin)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P14i\_performed -\> frbr:F51\_Pursuit -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P79\_beginning\_is\_qualified\_by -\> **xsd:string**</span>|
|**Target Model View(s)**|[Occupation](https://chin-rcip.github.io/collections-model/target-model/current/life-events#occupation)|
|**Semantic Valuation**|*Low*: The value provided qualifies the date of the event, but this information is unstructured and cannot be automatically formatted.<br><br>*Medium*: The value provided qualifies the date of the event and can be (semi-)automatically cleaned and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String<br><br>*High*: The qualifier is the sole value provided and is structured and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String|
|**Typical Case(s)**|Marc Séguin (Actor Appellation) is a visual artist (Occupation Type), novelist (Occupation Type), and farmer (Occupation Type). His first solo exhibition dates back to 1996 (Occupation Type “Visual Artist”; Occupation Date Begin “1996”; Occupation Date Begin Qualifier “before”) and he has practiced in Montréal, QC, Hemmingford, QC and Brooklyn, NY (Occupation Places). His first novel, *La Foi du braconnier*, was published in 2009 (Occupation Type “Novelist”; Occupation Date Begin “2009”; Occupation Date Begin Qualifier “circa”). He owns a family farm in Hemmingford, QC (Occupation Type “Farmer”; Occupation Date Begin “2008”; Occupation Date Begin Qualifier “before”; Occupation Place “Hemmingford, QC”).|
|**Edge Case(s)**|There might be cases where the Occupation Date Begin and the Occupation Date Begin Qualifier would be the same, in particular when it comes to eras. For example, “Victorian Era” can be both the Occupation Date Begin and the Occupation Date Begin Qualifier. Determining what eras the qualifiers will entail (through the vocabulary used to handle them) will thus be paramount.<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Occupation Date Begin Qualifier: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|There can be more than one qualifier at once for a single Occupation Date Begin (e.g. “BCE” and “BC”, which is the same information, the former being qualified using the non-christian acronym for “Before Common Era” and the latter using the christian “Before Christ”).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020), [(Wikipedia 2019o)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019o), [(Wikipedia 2019r)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019r), [(Wikipedia 2019w)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019w)|

---

## Occupation Date End

|---|---|
|**Scope**|This field designates the latest temporal instant the actor assumed the occupation recorded.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Occupation Type](#occupation-type)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P14i\_performed -\> frbr:F51\_Pursuit -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82b\_end\_of\_the\_end -\> **xsd:dateTime**</span>|
|**Target Model View(s)**|[Occupation](https://chin-rcip.github.io/collections-model/target-model/current/life-events#occupation)|
|**Semantic Valuation**|*Low*: The value provided temporalizes the beginning of the event, but this information cannot be automatically extracted and formatted.<br><br>*Medium*: The date can be automatically extracted from the value provided (and from textual content that surrounds it if applicable) and can be formatted using the YYYY-MM-DD convention.<br>Accepted Value Type(s): String<br><br>*High*: The date is the sole value provided and is formatted using the date convention.<br>Accepted Value Type(s): DateTime (YYYY-MM-DDThh:mm:ss)|
|**Typical Case(s)**|Molly Bobak (Actor Appellation) was a Canadian artist (Occupation Type) who served as Second Lieutenant (Occupation Type) during World War II. She served from November 1942 when she enlisted in the Canadian Women’s Army Corps to September 1945 (Occupation Type “Second Lieutenant”; Occupation Date Begin “1942-11”; Occupation Date End “1945-09”; Occupation Place “Canada”; Occupation Place “Europe”.|
|**Edge Case(s)**|Molly Bobak (Actor Appellation) was a Canadian artist (Occupation Type) who served as Second Lieutenant (Occupation Type) during World War II. She served from November 1942 when she enlisted in the Canadian Women’s Army Corps to September 1945 (Occupation Type “Second Lieutenant”; Occupation Date Begin “1942-11”; Occupation Date End “1945-09”; Occupation Place “Canada”; Occupation Place “Europe”). She sketched in her diaries throughout the war and it is only three years after her enrollment that she was officially made a “War Artist” (Occupation Type) by the Canadian War Artists Selection Committee. In this case, it is unclear how best to record the information as the beginning date of the Occupation Type “War Artist” would be after the end of her serving as such. It is thus unclear if the Occupation Type is determined by the act of completing tasks or by that of holding a position.<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Occupation Date End: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|CHIN recommends using the following format when entering dates: “YYYY-MM-DD HH:MM:SS”. However, if the data cannot be converted to such a format (such as in the case of an era), a string can be used (e.g. Han Dynasty).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020)|

---

## Occupation Date End Qualifier

|---|---|
|**Scope**|This field qualifies the latest temporal instant the actor assumed the occupation recorded.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Occupation Date End](#occupation-date-end)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P14i\_performed -\> frbr:F51\_Pursuit -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P80\_end\_is\_qualified\_by -\> **xsd:string**</span>|
|**Target Model View(s)**|[Occupation](https://chin-rcip.github.io/collections-model/target-model/current/life-events#occupation)|
|**Semantic Valuation**|*Low*: The value provided qualifies the date of the event, but this information is unstructured and cannot be automatically formatted.<br><br>*Medium*: The value provided qualifies the date of the event and can be (semi-)automatically cleaned and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String<br><br>*High*: The qualifier is the sole value provided and is structured and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String|
|**Typical Case(s)**|Molly Bobak (Actor Appellation) was a Canadian artist (Occupation Type) who served as Second Lieutenant (Occupation Type) during World War II. She served from November 1942 when she enlisted in the Canadian Women’s Army Corps until the end of the war in September 1945 (Occupation Type “Second Lieutenant”; Occupation Date Begin “1942-11”; Occupation Date End “1946”; Occupation Date End Qualifier “1945-09-02”; Occupation Date End Qualifier “circa”; Occupation Place “Canada”; Occupation Place “Europe”).|
|**Edge Case(s)**|There might be cases where the Occupation Date End and the Occupation Date End Qualifier would be the same, in particular when it comes to eras. For example, “Victorian Era” can be both the Occupation Date End and the Occupation Date End Qualifier. Determining what eras the qualifiers will entail (through the vocabulary used to handle them) will thus be paramount.<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Occupation Date End Qualifier: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|There can be more than one qualifier at once for a single Occupation Date End (e.g. “BCE” and “BC”, which is the same information, the former being qualified using the non-christian acronym for “Before Common Era” and the latter using the christian “Before Christ”).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020), [(Wikipedia 2019o)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019o), [(Wikipedia 2019r)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019r), [(Wikipedia 2019w)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019w)|

---

## Occupation Place

|---|---|
|**Scope**|This field identifies the location(s) in which the actor performed their occupation.|
|**Generated Bond(s)**|E53\_Place|
|**Dependency(ies)**|[Occupation Type](#occupation-type)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P14i\_performed -\> frbr:F51\_Pursuit -\> crm:P7\_took\_place\_at -\> **crm:E53\_Place**</span>|
|**Target Model View(s)**|[Occupation](https://chin-rcip.github.io/collections-model/target-model/current/life-events#occupation)|
|**Semantic Valuation**|*Low*: The value provided is a string that cannot be parsed automatically by reconciliation tools but still contains the required information.<br><br>*Medium*: The value provided is a string that can be automatically cleaned and reconciled using controlled vocabularies specified by CHIN. In the event that the value is adequately structured but does not reconcile with any terms from the controlled vocabulary, and provided that it is deemed relevant, CHIN will add the term to the vocabulary.<br>Accepted Value Type(s): String<br><br>*High*: The provided value is a string that can be automatically reconciled with the controlled vocabularies specified by CHIN.<br>Accepted Value Type(s): String, URI|
|**Typical Case(s)**|Marc Séguin (Actor Appellation) is a visual artist (Occupation Type), novelist (Occupation Type), and farmer (Occupation Type). His first solo exhibition dates back to 1996 (Occupation Type “Visual Artist”; Occupation Date Begin “1996”; Occupation Date Begin Qualifier “before”) and he has practiced in Montréal, QC, Hemmingford, QC and Brooklyn, NY (Occupation Places). His first novel, *La Foi du braconnier*, was published in 2009 (Occupation Type “Novelist”; Occupation Date Begin “2009”; Occupation Date Begin Qualifier “circa”). He owns a family farm in Hemmingford, QC (Occupation Type “Farmer”; Occupation Date Begin “2008”; Occupation Date Begin Qualifier “before”; Occupation Place “Hemmingford, QC”).|
|**Edge Case(s)**|To Come|
|**Value Origin(s)**|Actors Checklist: Occupation Place: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|This field accommodates all forms of modern and historical locations, physical features, or nations, on Earth or not.|
|**Reference(s)**|[(Le Boeuf et al. 2015, sec. E53 Place)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Bekiari et al. 2015, sec. F9 Place)](/collections-model/semantic-paths-specification/current/bibliography#bekiari-et-al-2015), [(Free Dictionary 2019m)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019m), [(Free Dictionary 2019n)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019n), [(Thesaurus of Geographic Names 2019)](/collections-model/semantic-paths-specification/current/bibliography#thesaurus-of-geographic-names-2019), [(Wikipedia 2019am)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019am)|

---

## Production Actor Priority

|---|---|
|**Scope**|This field situates the Actor in an order of precedence and importance when it comes to the production of the work.|
|**Generated Bond(s)**|E55\_Type|
|**Dependency(ies)**|E39\_Actor<br><br>E22\_Human-Made\_Object|
|**Related SQN(s)**|Actor Priority: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P02i\_is\_range\_of -\> crm:PC14\_carried\_out\_by -\> crm:P14.1\_in\_the\_role\_of -\> **crm:E55\_Type** (*-\> crm:E55\_Type\[“Actor Priority”\]*)</span>|
|**Target Model View(s)**|[Artefact Creation and the Role of the Actor in the Creation](https://chin-rcip.github.io/collections-model/target-model/current/artefacts#artefact-creation-and-the-role-of-the-actor-in-the-creation)|
|**Semantic Valuation**|*Low*: The value provided is a string that cannot be parsed automatically by reconciliation tools but still contains the required information.<br><br>*Medium*: The value provided is a string that can be automatically cleaned and reconciled using controlled vocabularies specified by CHIN. In the event that the value is adequately structured but does not reconcile with any terms from the controlled vocabulary, and provided that it is deemed relevant, CHIN will add the term to the vocabulary.<br>Accepted Value Type(s): String<br><br>*High*: The provided value is a string that can be automatically reconciled with the controlled vocabularies specified by CHIN.<br>Accepted Value Type(s): String, URI|
|**Typical Case(s)**|*Canadissimo* (Object Appellation) was made by art collective BGL and presented at the Canada Pavilion of the Venice Biennale (Production Place) in 2015 (Production Date Begin “2015”; Production Date Begin Qualifier “or before”; Production Date End “2015”; Production Date End Qualifier “or before”). BGL is comprised of Jasmin Bilodeau (Production Actor Priority “1”; Production Actor Role “Creator”), Sébastien Giguére (Production Actor Priority “1”; Production Actor Role “Creator”), and Nicolas Laverdiére (Production Actor Priority “1”; Production Actor Role “Creator”).|
|**Edge Case(s)**|How to situate and visualise this priority has yet to be determined. How will the “1”, “2”, “10”, etc. be compiled? Is it an order of priority? Or is it the part of the work relative to others (such as in a flexbox)?|
|**Value Origin(s)**|Actors Checklist: Production Actor Priority: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|TBD|
|**Reference(s)**|[(Free Dictionary 2019ak)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019ak), [(w3schools.com 2019)](/collections-model/semantic-paths-specification/current/bibliography#w3schools-2019)|


---

## Production Actor Role

|---|---|
|**Scope**|This field indicates the parts, activities, functions, and duties endorsed by the main actor with regards to the creation of an object.|
|**Generated Bond(s)**|E55\_Type|
|**Dependency(ies)**|E39\_Actor<br><br>E22\_Human-Made\_Object|
|**Related SQN(s)**|Actor Role: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P02i\_is\_range\_of -\> crm:PC14\_carried\_out\_by -\> crm:P14.1\_in\_the\_role\_of -\> crm:E55\_Type (*-\> crm:P2\_has\_type -\> **crm:E55\_Type**\[“Actor Role”\]*)</span>|
|**Target Model View(s)**|[Artefact Creation and the Role of the Actor in the Creation](https://chin-rcip.github.io/collections-model/target-model/current/artefacts#artefact-creation-and-the-role-of-the-actor-in-the-creation)|
|**Semantic Valuation**|*Low*: The value provided is a string that cannot be parsed automatically by reconciliation tools but still contains the required information.<br><br>*Medium*: The value provided is a string that can be automatically cleaned and reconciled using controlled vocabularies specified by CHIN. In the event that the value is adequately structured but does not reconcile with any terms from the controlled vocabulary, and provided that it is deemed relevant, CHIN will add the term to the vocabulary.<br>Accepted Value Type(s): String<br><br>*High*: The provided value is a string that can be automatically reconciled with the controlled vocabularies specified by CHIN.<br>Accepted Value Type(s): String, URI|
|**Typical Case(s)**|*Canadissimo*(Object Appellation) was made by art collective BGL and presented at the Canada Pavilion of the Venice Biennale (Production Place) in 2015 (Production Date Begin “2015”; Production Date Begin Qualifier “or before”; Production Date End “2015”; Production Date End Qualifier “or before”). BGL is comprised of Jasmin Bilodeau (Production Actor Priority “1”; Production Actor Role “Creator”), Sébastien Giguére (Production Actor Priority “1”; Production Actor Role “Creator”), and Nicolas Laverdiére (Production Actor Priority “1”; Production Actor Role “Creator”).|
|**Edge Case(s)**|How to determine the role and the priority will likely rely heavily on eachother. For example, Jeff Koons would likely have the highest Production Actor Priority in any of his works despite the fact that he does not *make* them most of the time. As such, his Production Actor Role might be Creator or Ideator, and the designers, engineers, etc. he employs would have lower Production Actor Priority. As such, would roles either have a Production Actor Priority ascribed to them, or would there be qualified roles such as “Ideator” and “Executant”? In general, how to think the ideation process with regards to the production process will be of interest to CHIN.|
|**Value Origin(s)**|Actors Checklist: Production Actor Role: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|The Production Actor Role defines an actor’s part in a production event so that there cannot be a Production Actor Role without an Object to relate it to.<br><br>A single production/object can be associated with multiple roles (e.g. an actor can be both a creator and a seller).|
|**Reference(s)**|[(Art & Architecture Thesaurus 2019l)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019l), [(Deutsche National Bibliothek 2019)](/collections-model/semantic-paths-specification/current/bibliography#deutsche-national-bibliothek-2019), [(Free Dictionary 2019ae)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019ae), [(Free Dictionary 2019l)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019l), [(Masolo et al. 2004)](/collections-model/semantic-paths-specification/current/bibliography#masolo-et-al-2004), [[(Wenglinsky 2017)](](/collections-model/semantic-paths-specification/current/bibliography#wenglinsky-martin-2017), [(Wikipedia 2019ar)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019ar), [(Wikipedia 2019n)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019n)|

---

## Production Date Begin

|---|---|
|**Scope**|This field designates the earliest temporal instant of the creation of the object.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|E22\_Human-Made\_Object|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P02i\_is\_range\_of -\> crm:PC14\_carried\_out\_by -\> crm:P01\_has\_domain -\> crm:E12\_Production -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82a\_begin\_of\_the\_begin -\> **xsd:dateTime**</span>|
|**Target Model View(s)**|[Artefact Creation and the Role of the Actor in the Creation](https://chin-rcip.github.io/collections-model/target-model/current/artefacts#artefact-creation-and-the-role-of-the-actor-in-the-creation)|
|**Semantic Valuation**|*Low*: The value provided temporalizes the beginning of the event, but this information cannot be automatically extracted and formatted.<br><br>*Medium*: The date can be automatically extracted from the value provided (and from textual content that surrounds it if applicable) and can be formatted using the YYYY-MM-DD convention.<br>Accepted Value Type(s): String<br><br>*High*: The date is the sole value provided and is formatted using the date convention.<br>Accepted Value Type(s): DateTime (YYYY-MM-DDThh:mm:ss)|
|**Typical Case(s)**|*Canadissimo*(Object Appellation) was made by art collective BGL and presented at the Canada Pavilion of the Venice Biennale (Production Place) in 2015 (Production Date Begin “2015”; Production Date Begin Qualifier “or before”; Production Date End “2015”; Production Date End Qualifier “or before”). BGL is comprised of Jasmin Bilodeau (Production Actor Priority “1”; Production Actor Role “Creator”), Sébastien Giguère (Production Actor Priority “1”; Production Actor Role “Creator”), and Nicolas Laverdière (Production Actor Priority “1”; Production Actor Role “Creator”).|
|**Edge Case(s)**|How to determine the role and the priority will likely rely heavily on eachother. For example, Jeff Koons would likely have the highest Production Actor Priority in any of his works despite the fact that he does not *make* them most of the time. As such, his Production Actor Role might be Creator or Ideator, and the designers, engineers, etc. he employs would have lower Production Actor Priority. As such, would roles either have a Production Actor Priority ascribed to them, or would there be qualified roles such as “Ideator” and “Executant”? In general, how to think the ideation process with regards to the production process will be of interest to CHIN. For example, would the Production of a work begin with its ideation, or with its physical *making*into the world? What about performance or intangible productions? Would there be a “Conceptual” Qualifier ascribed to dates?<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Production Date Begin: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|CHIN recommends using the following format when entering dates: “YYYY-MM-DD HH:MM:SS”. However, if the data cannot be converted to such a format (such as in the case of an era), a string can be used (e.g. Han Dynasty).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020)|

---

## Production Date Begin Qualifier

|---|---|
|**Scope**|This field qualifies the earliest temporal instant of the creation of the object.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Production Date Begin](#production-date-begin)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P02i\_is\_range\_of -\> crm:PC14\_carried\_out\_by -\> crm:P01\_has\_domain -\> crm:E12\_Production -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P79\_beginning\_is\_qualified\_by -\> **xsd:string**</span>|
|**Target Model View(s)**|[Artefact Creation and the Role of the Actor in the Creation](https://chin-rcip.github.io/collections-model/target-model/current/artefacts#artefact-creation-and-the-role-of-the-actor-in-the-creation)|
|**Semantic Valuation**|*Low*: The value provided qualifies the date of the event, but this information is unstructured and cannot be automatically formatted.<br><br>*Medium*: The value provided qualifies the date of the event and can be (semi-)automatically cleaned and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String<br><br>*High*: The qualifier is the sole value provided and is structured and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String|
|**Typical Case(s)**|*Canadissimo*(Object Appellation) was made by art collective BGL and presented at the Canada Pavilion of the Venice Biennale (Production Place) in 2015 (Production Date Begin “2015”; Production Date Begin Qualifier “or before”; Production Date End “2015”; Production Date End Qualifier “or before”). BGL is comprised of Jasmin Bilodeau (Production Actor Priority “1”; Production Actor Role “Creator”), Sébastien Giguère (Production Actor Priority “1”; Production Actor Role “Creator”), and Nicolas Laverdière (Production Actor Priority “1”; Production Actor Role “Creator”).|
|**Edge Case(s)**|There might be cases where the Production Date Begin and the Production Date Begin Qualifier would be the same, in particular when it comes to eras. For example, “Victorian Era” can be both the Production Date Begin and the Production Date Begin Qualifier. Determining what eras the qualifiers will entail (through the vocabulary used to handle them) will thus be paramount.<br><br>How to determine the role and the priority will likely rely heavily on eachother. For example, Jeff Koons would likely have the highest Production Actor Priority in any of his works despite the fact that he does not *make* them most of the time. As such, his Production Actor Role might be Creator or Ideator, and the designers, engineers, etc. he employs would have lower Production Actor Priority. As such, would roles either have a Production Actor Priority ascribed to them, or would there be qualified roles such as “Ideator” and “Executant”? In general, how to think the ideation process with regards to the production process will be of interest to CHIN. For example, would the Production of a work begin with its ideation, or with its physical *making*into the world? What about performance or intangible productions? Would there be a “Conceptual” Qualifier ascribed to dates?<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Production Date Begin Qualifier: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|There can be more than one qualifier at once for a single Production Date Begin (e.g. “BCE” and “BC”, which is the same information, the former being qualified using the non-christian acronym for “Before Common Era” and the latter using the christian “Before Christ”).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020)|

---

## Production Date End

|---|---|
|**Scope**|This field designates the latest temporal instant of the creation of the object.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|E22\_Human-Made\_Object|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P02i\_is\_range\_of -\> crm:PC14\_carried\_out\_by -\> crm:P01\_has\_domain -\> crm:E12\_Production -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82b\_end\_of\_the\_end -\> **xsd:dateTime**</span>|
|**Target Model View(s)**|[Artefact Creation and the Role of the Actor in the Creation](https://chin-rcip.github.io/collections-model/target-model/current/artefacts#artefact-creation-and-the-role-of-the-actor-in-the-creation)|
|**Semantic Valuation**|*Low*: The value provided temporalizes the beginning of the event, but this information cannot be automatically extracted and formatted.<br><br>*Medium*: The date can be automatically extracted from the value provided (and from textual content that surrounds it if applicable) and can be formatted using the YYYY-MM-DD convention.<br>Accepted Value Type(s): String<br><br>*High*: The date is the sole value provided and is formatted using the date convention<br>Accepted Value Type(s): DateTime (YYYY-MM-DDThh:mm:ss)|
|**Typical Case(s)**|*Canadissimo*(Object Appellation) was made by art collective BGL and presented at the Canada Pavilion of the Venice Biennale (Production Place) in 2015 (Production Date Begin “2015”; Production Date Begin Qualifier “or before”; Production Date End “2015”; Production Date End Qualifier “or before”). BGL is comprised of Jasmin Bilodeau (Production Actor Priority “1”; Production Actor Role “Creator”), Sébastien Giguère (Production Actor Priority “1”; Production Actor Role “Creator”), and Nicolas Laverdière (Production Actor Priority “1”; Production Actor Role “Creator”).|
|**Edge Case(s)**|How to determine the role and the priority will likely rely heavily on eachother. For example, Jeff Koons would likely have the highest Production Actor Priority in any of his works despite the fact that he does not *make* them most of the time. As such, his Production Actor Role might be Creator or Ideator, and the designers, engineers, etc. he employs would have lower Production Actor Priority. As such, would roles either have a Production Actor Priority ascribed to them, or would there be qualified roles such as “Ideator” and “Executant”? In general, how to think the ideation process with regards to the production process will be of interest to CHIN. For example, would the Production of a work begin with its ideation, or with its physical *making*into the world? What about performance or intangible productions? Would there be a “Conceptual” Qualifier ascribed to dates?<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Production Date End: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|CHIN recommends using the following format when entering dates: “YYYY-MM-DD HH:MM:SS”. However, if the data cannot be converted to such a format (such as in the case of an era), a string can be used (e.g. Han Dynasty).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020)|

---

## Production Date End Qualifier

|---|---|
|**Scope**|This field qualifies the latest temporal instant of the creation of the object.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Production Date End](#production-date-end)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P02i\_is\_range\_of -\> crm:PC14\_carried\_out\_by -\> crm:P01\_has\_domain -\> crm:E12\_Production -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P80\_end\_is\_qualified\_by -\> **xsd:string**</span>|
|**Target Model View(s)**|[Artefact Creation and the Role of the Actor in the Creation](https://chin-rcip.github.io/collections-model/target-model/current/artefacts#artefact-creation-and-the-role-of-the-actor-in-the-creation)|
|**Semantic Valuation**|*Low*: The value provided qualifies the date of the event, but this information is unstructured and cannot be automatically formatted.<br><br>*Medium*: The value provided qualifies the date of the event and can be (semi-)automatically cleaned and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String<br><br>*High*: The qualifier is the sole value provided and is structured and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String|
|**Typical Case(s)**|*Canadissimo*(Object Appellation) was made by art collective BGL and presented at the Canada Pavilion of the Venice Biennale (Production Place) in 2015 (Production Date Begin “2015”; Production Date Begin Qualifier “or before”; Production Date End “2015”; Production Date End Qualifier “or before”). BGL is comprised of Jasmin Bilodeau (Production Actor Priority “1”; Production Actor Role “Creator”), Sébastien Giguère (Production Actor Priority “1”; Production Actor Role “Creator”), and Nicolas Laverdière (Production Actor Priority “1”; Production Actor Role “Creator”).|
|**Edge Case(s)**|There might be cases where the Production Date End and the Production Date End Qualifier would be the same, in particular when it comes to eras. For example, “Victorian Era” can be both the Production Date End and the Production Date End Qualifier. Determining what eras the qualifiers will entail (through the vocabulary used to handle them) will thus be paramount.<br><br>How to determine the role and the priority will likely rely heavily on eachother. For example, Jeff Koons would likely have the highest Production Actor Priority in any of his works despite the fact that he does not *make* them most of the time. As such, his Production Actor Role might be Creator or Ideator, and the designers, engineers, etc. he employs would have lower Production Actor Priority. As such, would roles either have a Production Actor Priority ascribed to them, or would there be qualified roles such as “Ideator” and “Executant”? In general, how to think the ideation process with regards to the production process will be of interest to CHIN. For example, would the Production of a work begin with its ideation, or with its physical *making*into the world? What about performance or intangible productions? Would there be a “Conceptual” Qualifier ascribed to dates?<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Production Date End Qualifier: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|There can be more than one qualifier at once for a single Production Date End (e.g. “BCE” and “BC”, which is the same information, the former being qualified using the non-christian acronym for “Before Common Era” and the latter using the christian “Before Christ”).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020)|

---

## Production Place

|---|---|
|**Scope**|This field identifies the location(s) in which the Actor created the object.|
|**Generated Bond(s)**|E53\_Place|
|**Dependency(ies)**|E22\_Human-Made\_Object|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P02i\_is\_range\_of -\> crm:PC14\_carried\_out\_by -\> crm:P01\_has\_domain -\> crm:E12\_Production -\> crm:P7\_took\_place\_at -\> **crm:E53\_Place**</span>|
|**Target Model View(s)**|[Artefact Creation and the Role of the Actor in the Creation](https://chin-rcip.github.io/collections-model/target-model/current/artefacts#artefact-creation-and-the-role-of-the-actor-in-the-creation)|
|**Semantic Valuation**|*Low*: The value provided is a string that cannot be parsed automatically by reconciliation tools but still contains the required information.<br><br>*Medium*: The value provided is a string that can be automatically cleaned and reconciled using controlled vocabularies specified by CHIN. In the event that the value is adequately structured but does not reconcile with any terms from the controlled vocabulary, and provided that it is deemed relevant, CHIN will add the term to the vocabulary.<br>Accepted Value Type(s): String<br><br>*High*: The provided value is a string that can be automatically reconciled with the controlled vocabularies specified by CHIN.<br>Accepted Value Type(s): String, URI|
|**Typical Case(s)**|*Canadissimo*(Object Appellation) was made by art collective BGL and presented at the Canada Pavilion of the Venice Biennale (Production Place) in 2015 (Production Date Begin “2015”; Production Date Begin Qualifier “or before”; Production Date End “2015”; Production Date End Qualifier “or before”). BGL is comprised of Jasmin Bilodeau (Production Actor Priority “1”; Production Actor Role “Creator”), Sébastien Giguère (Production Actor Priority “1”; Production Actor Role “Creator”), and Nicolas Laverdière (Production Actor Priority “1”; Production Actor Role “Creator”).|
|**Edge Case(s)**|In the case above, it could be argued that the Venice Biennale is the Exhibition Place (which will have to be modeled in a later version) rather than the Production Place, or both considering it is an installation.|
|**Value Origin(s)**|Actors Checklist: Production Place: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|This field accommodates all forms of modern and historical locations, physical features, or nations, on Earth or not.|
|**Reference(s)**|[(Le Boeuf et al. 2015, sec. E53 Place)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Bekiari et al. 2015, sec. F9 Place)](/collections-model/semantic-paths-specification/current/bibliography#bekiari-et-al-2015), [(Free Dictionary 2019m)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019m), [(Free Dictionary 2019n)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019n), [(Thesaurus of Geographic Names 2019)](/collections-model/semantic-paths-specification/current/bibliography#thesaurus-of-geographic-names-2019), [(Wikipedia 2019am)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019am)|

---

## Record Contributor Appellation

|---|---|
|**Scope**|This field designates the entire identifying word(s), number(s), symbol(s) or code(s) by which a contributor, whether individual or not, providing data for a record (actor or object) is identified. This can include names, titles, or other designations.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|E39\_Actor or E22\_Human-Made\_Object|
|**Related SQN(s)**|Record: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P67i\_is\_referred\_to\_by -\> crm:E73\_Information\_Object (*-\> crm:P2\_has\_type -\> crm:E55\_Type\["Record"\]*) -\> crm:P94i\_was\_created\_by -\> crm:E65\_Creation -\> crm:P14\_carried\_out\_by -\> crm:E39\_Actor -\> crm:P1\_is\_identified\_by -\> crm:E41\_Appellation + crm:E33\_Linguistic\_Object -\> crm:P190\_has\_symbolic\_content -\> **xsd:string**</span>|
|**Target Model View(s)**|[Record Provenance with Aggregated Contributors](https://chin-rcip.github.io/collections-model/target-model/current/general-concepts#record-provenance-with-aggregated-contributors)|
|**Semantic Valuation**|*Low*: The provided values contain unstructured information of the appellation, such as it cannot be parsed automatically by reconciliation tools, but still contains the required information.<br><br>*Medium*: The provided values contain structured information that can be automatically cleaned and reconciled with other entities in other datasets.<br>Accepted Value Type(s): String<br><br>*High*: The provided values only contain structured information that can be automatically reconciled with other entities in other datasets.<br>Accepted Value Type(s): String|
|**Typical Case(s)**|*Flightstop* (Object Appellation; Object Appellation Language “English”; Object Appellation Type “Title”; Object Appellation Preference “Preferred”) is a sculpture (Object Medium and Technique) by artist (Occupation Type) Michael Snow (Actor Appellation), sometimes titled *Flight Stop*(Object Appellation; Object Appellation Language “English”; Object Appellation Type “Title”; Object Appellation Preference “Non-Preferred”). It has been displayed at the Toronto Eaton Centre (Record Contributor Appellation) since 1979 (Record Date Begin) when it was made and installed.|
|**Edge Case(s)**|The scope of what a contributor is in this case is blurry: would it include data that CHIN would retrieve for enrichment purposes for example (e.g. would Wikidata have a Record Contributor Appellation?)?|
|**Value Origin(s)**|Actors Checklist: Record Contributor Appellation: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|This field is only used when the Dataset Provider is an aggregator and will be used to record an institution who contributed their data to this aggregator (Dataset Provider) and then submits it to CHIN (such as is the case with Artists in Canada).<br><br>This enables the identification of the contributor of a specific record, whether it is through an aggregator (e.g. NovaMuse) or not. When an institution contributes a record to an aggregator, this institution will be identified here through a group.<br><br>When an individual contributes a record through crowdsourcing or other similar practices, this person will be identified here as an Actor.<br><br>Every Record Contributor Appellation institution must have either a Source URI Person or a Source URI Institution as a cataloguer.|
|**Reference(s)**|[(Art & Architecture Thesaurus 2019d)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019d), [(Le Boeuf et al. 2015, sec. E41 Appellation)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Free Dictionary 2019a)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019a), [(Free Dictionary 2019f)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019f)|

---

## Record Date Begin

|---|---|
|**Scope**|This field designates the earliest temporal instant of the creation of the record by the cataloguing entity (person or institution).|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|E39\_Actor or E22\_Human-Made\_Object|
|**Related SQN(s)**|Record: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P67i\_is\_referred\_to\_by -\> crm:E73\_Information\_Object (*-\> crm:P2\_has\_type -\> crm:E55\_Type\["Record"\]*) -\> crm:P94i\_was\_created\_by -\> crm:E65\_Creation -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82a\_begin\_of\_the\_begin -\> **xsd:dateTime**</span>|
|**Target Model View(s)**|[Record Provenance with Aggregated Contributors](https://chin-rcip.github.io/collections-model/target-model/current/general-concepts#record-provenance-with-aggregated-contributors)|
|**Semantic Valuation**|*Low*: The value provided temporalizes the beginning of the event, but this information cannot be automatically extracted and formatted.<br><br>*Medium*: The date can be automatically extracted from the value provided (and from textual content that surrounds it if applicable) and can be formatted using the YYYY-MM-DD convention.<br>Accepted Value Type(s): String<br><br>*High*: The date is the sole value provided and is formatted using the date convention.<br>Accepted Value Type(s): DateTime (YYYY-MM-DDThh:mm:ss)|
|**Typical Case(s)**|If the National Gallery of Canada created a record in its database for an object by an unknown artist on August 20th, 2019, the Record Date Begin will be “2019-08-20”.<br><br>*Flightstop* (Object Appellation; Object Appellation Language “English”; Object Appellation Type “Title”; Object Appellation Preference “Preferred”) is a sculpture (Object Medium and Technique) by artist (Occupation Type) Michael Snow (Actor Appellation), sometimes titled *Flight Stop*(Object Appellation; Object Appellation Language “English”; Object Appellation Type “Title”; Object Appellation Preference “Non-Preferred”). It has been displayed at the Toronto Eaton Centre (Record Contributor Appellation) since 1979 (Record Date Begin) when it was made and installed.|
|**Edge Case(s)**|Recently created records will most likely have specific dates, but older ones created when collections management relied on paperwork rather than databases might have blurrier dates that would refer to periods of the institution’s history such as “under the curatorship of Stéphane Aquin” or “before the museum was instituted”, etc.|
|**Value Origin(s)**|Actors Checklist: Record Date Begin: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|This does not indicate the date the record was created by CHIN nor the date it was updated; rather, it refers to the date the record was created by the cataloguer at the contributing institution.<br><br>CHIN recommends using the following format when entering dates: “YYYY-MM-DD HH:MM:SS”. However, if the data cannot be converted to such a format (such as in the case of an era), a string can be used (e.g. 2019?).|
|**Reference(s)**|[(Semantic Web Interest Group 2019)](/collections-model/semantic-paths-specification/current/bibliography#semantic-web-interest-group-2019), [(Wikipedia 2019d)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019d)|

---

## Record Date End

|---|---|
|**Scope**|This field designates the latest temporal instant of the creation of the record by the cataloguing entity (person or institution).|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|E39\_Actor or E22\_Human-Made\_Object|
|**Related SQN(s)**|Record: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P67i\_is\_referred\_to\_by -\> crm:E73\_Information\_Object (*-\> crm:P2\_has\_type -\> crm:E55\_Type\["Record"\]*) -\> crm:P94i\_was\_created\_by -\> crm:E65\_Creation -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82b\_end\_of\_the\_end -\> **xsd:dateTime**</span>|
|**Target Model View(s)**|[Record Provenance with Aggregated Contributors](https://chin-rcip.github.io/collections-model/target-model/current/general-concepts#record-provenance-with-aggregated-contributors)|
|**Semantic Valuation**|*Low*: The value provided temporalizes the beginning of the event, but this information cannot be automatically extracted and formatted.<br><br>*Medium*: The date can be automatically extracted from the value provided (and from textual content that surrounds it if applicable) and can be formatted using the YYYY-MM-DD convention.<br>Accepted Value Type(s): String<br><br>*High*: The date is the sole value provided and is formatted using the date convention.<br>Accepted Value Type(s): DateTime (YYYY-MM-DDThh:mm:ss)|
|**Typical Case(s)**|If the National Gallery of Canada finished creating a record in its database for an object by an unknown artist on August 20th, 2019, the Record Date End will be “2019-08-20”.<br><br>*Flightstop* (Object Appellation; Object Appellation Language “English”; Object Appellation Type “Title”; Object Appellation Preference “Preferred”) is a sculpture (Object Medium and Technique) by artist (Occupation Type) Michael Snow (Actor Appellation), sometimes titled *Flight Stop*(Object Appellation; Object Appellation Language “English”; Object Appellation Type “Title”; Object Appellation Preference “Non-Preferred”). It has been displayed at the Toronto Eaton Centre (Record Contributor Appellation) since 1979 (Record Date Begin) when it was made and installed.|
|**Edge Case(s)**|Recently created records will most likely have specific dates, but older ones created when collections management relied on paperwork rather than databases might have blurrier dates that would refer to periods of the institution’s history such as “under the curatorship of Stéphane Aquin” or “before the museum was instituted”, etc.<br><br>It is also debatable whether a record *can*end since, as long as we have a date, there is still a record where it is documented.|
|**Value Origin(s)**|Actors Checklist: Record Date End: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|This does not indicate the date the record CHIN ended the creation of the record; rather, it refers to the date the cataloguer at the contributing institution ended the creation of the record.<br><br>CHIN recommends using the following format when entering dates: “YYYY-MM-DD HH:MM:SS”. However, if the data cannot be converted to such a format (such as in the case of an era), a string can be used (e.g. 2019?).|
|**Reference(s)**|[(Semantic Web Interest Group 2019)](/collections-model/semantic-paths-specification/current/bibliography#semantic-web-interest-group-2019), [(Wikipedia 2019d)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019d)|

---

## Related Actor Appellation

|---|---|
|**Scope**|This field designates the entire identifying word(s), number(s), symbol(s) or code(s) by which a related Actor (personal or corporate) is distinguished from others, such as the name, title, or designation of an actor as it has been attributed by a contributing institution. It is an identifying agreed upon term that is descriptive or connotative. If it is made of the concatenation of numerous parts, it should include all of them (such as honorifics, titles, etc.).|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|E39\_Actor|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P02i\_is\_range\_of -\> crm:PC14\_carried\_out\_by -\> crm:P01\_has\_domain -\> crm:E7\_Activity -\> crm:P01i\_is\_domain\_of -\> crm:PC14\_carried\_out\_by -\> crm:P02\_has\_range -\> crm:E39\_Actor -\> crm:P1\_is\_identified\_by -\> crm:E41\_Appellation + crm:E33\_Linguistic\_Object -\> crm:P190\_has\_symbolic\_content -\> **xsd:string**</span>|
|**Target Model View(s)**|[Relationships](https://chin-rcip.github.io/collections-model/target-model/current/life-events#influences)|
|**Semantic Valuation**|*Low*: The provided values contain unstructured information of the appellation, such as it cannot be parsed automatically by reconciliation tools, but still contains the required information.<br><br>*Medium*: The provided values contain structured information that can be automatically cleaned and reconciled with other entities in other datasets.<br>Accepted Value Type(s): String<br><br>*High*: The provided values only contain structured information that can be automatically reconciled with other entities in other datasets.<br>Accepted Value Type(s): String|
|**Typical Case(s)**|Molly Bobak (Actor Appellation) married Brunislaw Jacob Bobak (Related Actor Appellation; Related Actor Role “Spouse”; Relationship Actor Role “Spouse”; Relationship Date Begin “1945-05-08”; Relationship date Begin Qualifier “after”; Relationship Date End “2012-09-24”; Relationship Type “Marital”) whom she met after Victory in Europe Day in London, England. They married in 1945 and had two children, Alexander (Related Actor Appellation; Related Actor Role “Child”; Relationship Actor Role “Parent”; Relationship Date Begin “1946”; Relationship date Begin Qualifier “during”; Relationship Date End “2014-03-02”; Relationship Type “Parental”) and Anny (Related Actor Appellation; Related Actor Role “Child”; Relationship Actor Role “Parent”; Relationship Date Begin “1957”; Relationship date Begin Qualifier “during”; Relationship Date End “2014-03-02”; Relationship Type “Parental”).|
|**Edge Case(s)**|At the moment it is unclear how groups can be represented when it comes to relationships. The Relationship field should not be used to indicate an individual’s belonging to a group, but it can be used to record groups’ relationships to one another, including corporations. So for example, these fields would not be used to record Tom Thomson being part of the Group of Seven, but it would be used to record the Canadian War Artists Selection Committee (Group Appellation) is related to the Canadian War Records (Group Appellation), Canada’s Second World War art program. However, this points to Actor relationships, and groups *can be actors*per current definitions.|
|**Value Origin(s)**|Actors Checklist: Related Actor Appellation: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|This describes corporate as well as individual entities, but does not record belonging to groups; to do so use, use Group Appellation.|
|**Reference(s)**|[(Art & Architecture Thesaurus 2019d)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019d), [(Le Boeuf et al. 2015, sec. E82 Actor Appellation)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Le Boeuf et al. 2015, sec. E41 Appellation)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Free Dictionary 2019a)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019a), [(Free Dictionary 2019f)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019f)|

---

## Related Actor Role

|---|---|
|**Scope**|This field indicates the parts, activities, functions, and duties endorsed by the Related Actor with regards to the main Actor with which they have dealings ranging in duration from brief to enduring. These reflect a set of connected behaviours, rights, obligations, beliefs and norms expected from both parties and reflected in the contacts between them as well as the way they behave towards each other.|
|**Generated Bond(s)**|E55\_Type|
|**Dependency(ies)**|[Related Actor Appellation](#related-actor-appellation)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P02i\_is\_range\_of -\> crm:PC14\_carried\_out\_by -\> crm:P01\_has\_domain -\> crm:E7\_Activity -\> crm:P01i\_is\_domain\_of -\> crm:PC14\_carried\_out\_by -\> crm:P14.1\_in\_the\_role\_of -\> **crm:E55\_Type**</span>|
|**Target Model View(s)**|[Relationships](https://chin-rcip.github.io/collections-model/target-model/current/life-events#influences)|
|**Semantic Valuation**|*Low*: The value provided is a string that cannot be parsed automatically by reconciliation tools but still contains the required information.<br><br>*Medium*: The value provided is a string that can be automatically cleaned and reconciled using controlled vocabularies specified by CHIN. In the event that the value is adequately structured but does not reconcile with any terms from the controlled vocabulary, and provided that it is deemed relevant, CHIN will add the term to the vocabulary.<br>Accepted Value Type(s): String<br><br>*High*: The provided value is a string that can be automatically reconciled with the controlled vocabularies specified by CHIN.<br>Accepted Value Type(s): String, URI|
|**Typical Case(s)**|Molly Bobak (Actor Appellation) married Brunislaw Jacob Bobak (Related Actor Appellation; Related Actor Role “Spouse”; Relationship Actor Role “Spouse”; Relationship Date Begin “1945-05-08”; Relationship date Begin Qualifier “after”; Relationship Date End “2012-09-24”; Relationship Type “Marital”) whom she met after Victory in Europe Day in London, England. They married in 1945 and had two children, Alexander (Related Actor Appellation; Related Actor Role “Child”; Relationship Actor Role “Parent”; Relationship Date Begin “1946”; Relationship date Begin Qualifier “during”; Relationship Date End “2014-03-02”; Relationship Type “Parental”) and Anny (Related Actor Appellation; Related Actor Role “Child”; Relationship Actor Role “Parent”; Relationship Date Begin “1957”; Relationship date Begin Qualifier “during”; Relationship Date End “2014-03-02”; Relationship Type “Parental”).|
|**Edge Case(s)**|At the moment it is unclear how groups can be represented when it comes to relationships. The Relationship field should not be used to indicate an individual’s belonging to a group, but it can be used to record groups’ relationships to one another, including corporations. So for example, these fields would not be used to record Tom Thomson being part of the Group of Seven, but it would be used to record the Canadian War Artists Selection Committee (Group Appellation) is related to the Canadian War Records (Group Appellation), Canada’s Second World War art program. However, this points to Actor relationships, and groups *can be actors*per current definitions.|
|**Value Origin(s)**|Actors Checklist: Related Actor Role: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|The Related Actor Role defines a related actor’s part in a relationship so that there cannot be a Related Actor Role without a Relationship Type as well as an Actor Role.<br><br>A single relationship can be associated with multiple roles (e.g. an actor can be both a professional contact and an employer).|
|**Reference(s)**|[(Art & Architecture Thesaurus 2019l)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019l), [(Deutsche National Bibliothek 2019)](/collections-model/semantic-paths-specification/current/bibliography#deutsche-national-bibliothek-2019), [(Free Dictionary 2019ae)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019ae), [(Free Dictionary 2019l)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019l), [(Masolo et al. 2004)](/collections-model/semantic-paths-specification/current/bibliography#masolo-et-al-2004), [[(Wenglinsky 2017)](](/collections-model/semantic-paths-specification/current/bibliography#wenglinsky-martin-2017), [(Wikipedia 2019ar)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019ar), [(Wikipedia 2019n)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019n)|


---

## Relationship Actor Role

|---|---|
|**Scope**|This field indicates the parts, activities, functions, and duties endorsed by the main Actor with regards to a Related Actor with which they have dealings ranging in duration from brief to enduring. These reflect a set of connected behaviours, rights, obligations, beliefs and norms expected from both parties and reflected in the contacts between them as well as the way they behave towards each other.|
|**Generated Bond(s)**|E55\_Type|
|**Dependency(ies)**|E39\_Actor|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P02i\_is\_range\_of -\> crm:PC14\_carried\_out\_by -\> crm:P14.1\_in\_the\_role\_of -\> **crm:E55\_Type**</span>|
|**Target Model View(s)**|[Relationships](https://chin-rcip.github.io/collections-model/target-model/current/life-events#influences)|
|**Semantic Valuation**|*Low*: The value provided is a string that cannot be parsed automatically by reconciliation tools but still contains the required information.<br><br>*Medium*: The value provided is a string that can be automatically cleaned and reconciled using controlled vocabularies specified by CHIN. In the event that the value is adequately structured but does not reconcile with any terms from the controlled vocabulary, and provided that it is deemed relevant, CHIN will add the term to the vocabulary.<br>Accepted Value Type(s): String<br><br>*High*: The provided value is a string that can be automatically reconciled with the controlled vocabularies specified by CHIN.<br>Accepted Value Type(s): String, URI|
|**Typical Case(s)**|Molly Bobak (Actor Appellation) married Brunislaw Jacob Bobak (Related Actor Appellation; Related Actor Role “Spouse”; Relationship Actor Role “Spouse”; Relationship Date Begin “1945-05-08”; Relationship date Begin Qualifier “after”; Relationship Date End “2012-09-24”; Relationship Type “Marital”) whom she met after Victory in Europe Day in London, England. They married in 1945 and had two children, Alexander (Related Actor Appellation; Related Actor Role “Child”; Relationship Actor Role “Parent”; Relationship Date Begin “1946”; Relationship date Begin Qualifier “during”; Relationship Date End “2014-03-02”; Relationship Type “Parental”) and Anny (Related Actor Appellation; Related Actor Role “Child”; Relationship Actor Role “Parent”; Relationship Date Begin “1957”; Relationship date Begin Qualifier “during”; Relationship Date End “2014-03-02”; Relationship Type “Parental”).|
|**Edge Case(s)**|At the moment it is unclear how groups can be represented when it comes to relationships. The Relationship field should not be used to indicate an individual’s belonging to a group, but it can be used to record groups’ relationships to one another, including corporations. So for example, these fields would not be used to record Tom Thomson being part of the Group of Seven, but it would be used to record the Canadian War Artists Selection Committee (Group Appellation) is related to the Canadian War Records (Group Appellation), Canada’s Second World War art program. However, this points to Actor relationships, and groups *can be actors*per current definitions.|
|**Value Origin(s)**|Actors Checklist: Relationship Actor Role: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|The Relationship Actor Role defines an actor’s part in a relationship so that there cannot be a Relationship Actor Role without a Relationship Type as well as a Related Actor Role.<br><br>A single relationship can be associated with multiple roles (e.g. an actor can be both a professional contact and an employer).|
|**Reference(s)**|[(Art & Architecture Thesaurus 2019l)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019l), [(Deutsche National Bibliothek 2019)](/collections-model/semantic-paths-specification/current/bibliography#deutsche-national-bibliothek-2019), [(Free Dictionary 2019ae)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019ae), [(Free Dictionary 2019l)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019l), [(Masolo et al. 2004)](/collections-model/semantic-paths-specification/current/bibliography#masolo-et-al-2004), [[(Wenglinsky 2017)](](/collections-model/semantic-paths-specification/current/bibliography#wenglinsky-martin-2017), [(Wikipedia 2019ar)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019ar), [(Wikipedia 2019n)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019n)|

---

## Relationship Date Begin

|---|---|
|**Scope**|This field designates the earliest temporal instant of the association or acquaintance between Actors, which may range in duration from brief to enduring and refers to the contacts between them as well as the way they behave towards each other.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|E39\_Actor|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P02i\_is\_range\_of -\> crm:PC14\_carried\_out\_by -\> crm:P01\_has\_domain -\> crm:E7\_Activity -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82a\_begin\_of\_the\_begin -\> **xsd:dateTime**</span>|
|**Target Model View(s)**|[Relationships](https://chin-rcip.github.io/collections-model/target-model/current/life-events#influences)|
|**Semantic Valuation**|*Low*: The value provided temporalizes the beginning of the event, but this information cannot be automatically extracted and formatted.<br><br>*Medium*: The date can be automatically extracted from the value provided (and from textual content that surrounds it if applicable) and can be formatted using the YYYY-MM-DD convention.<br>Accepted Value Type(s): String<br><br>*High*: The date is the sole value provided and is formatted using the date convention.<br>Accepted Value Type(s): DateTime (YYYY-MM-DDThh:mm:ss)|
|**Typical Case(s)**|Molly Bobak (Actor Appellation) married Brunislaw Jacob Bobak (Related Actor Appellation; Related Actor Role “Spouse”; Relationship Actor Role “Spouse”; Relationship Date Begin “1945-05-08”; Relationship date Begin Qualifier “after”; Relationship Date End “2012-09-24”; Relationship Type “Marital”) whom she met after Victory in Europe Day in London, England. They married in 1945 and had two children, Alexander (Related Actor Appellation; Related Actor Role “Child”; Relationship Actor Role “Parent”; Relationship Date Begin “1946”; Relationship date Begin Qualifier “during”; Relationship Date End “2014-03-02”; Relationship Type “Parental”) and Anny (Related Actor Appellation; Related Actor Role “Child”; Relationship Actor Role “Parent”; Relationship Date Begin “1957”; Relationship date Begin Qualifier “during”; Relationship Date End “2014-03-02”; Relationship Type “Parental”).|
|**Edge Case(s)**|At the moment it is unclear how groups can be represented when it comes to relationships. The Relationship field should not be used to indicate an individual’s belonging to a group, but it can be used to record groups’ relationships to one another, including corporations. So for example, these fields would not be used to record Tom Thomson being part of the Group of Seven, but it would be used to record the Canadian War Artists Selection Committee (Group Appellation) is related to the Canadian War Records (Group Appellation), Canada’s Second World War art program. However, this points to Actor relationships, and groups *can be actors*per current definitions.<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Relationship Date Begin: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|CHIN recommends using the following format when entering dates: “YYYY-MM-DD HH:MM:SS”. However, if the data cannot be converted to such a format (such as in the case of an era), a string can be used (e.g. Han Dynasty).|
|**Reference(s)**|[(Deutsche National Bibliothek 2019)](/collections-model/semantic-paths-specification/current/bibliography#deutsche-national-bibliothek-2019), [(Free Dictionary 2019ae)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019ae), [(Wikipedia 2019ar)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019ar)|

---

## Relationship Date Begin Qualifier

|---|---|
|**Scope**|This field qualifies the earliest temporal instant of the association or acquaintance between Actors, which may range in duration from brief to enduring and refers to the contacts between them as well as the way they behave towards each other.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Relationship Date Begin](#relationship-date-begin)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P02i\_is\_range\_of -\> crm:PC14\_carried\_out\_by -\> crm:P01\_has\_domain -\> crm:E7\_Activity -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P79\_beginning\_is\_qualified\_by -\> **xsd:string**</span>|
|**Target Model View(s)**|[Relationships](https://chin-rcip.github.io/collections-model/target-model/current/life-events#influences)|
|**Semantic Valuation**|*Low*: The value provided qualifies the date of the event, but this information is unstructured and cannot be automatically formatted.<br><br>*Medium*: The value provided qualifies the date of the event and can be (semi-)automatically cleaned and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String<br><br>*High*: The qualifier is the sole value provided and is structured and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String|
|**Typical Case(s)**|Molly Bobak (Actor Appellation) married Brunislaw Jacob Bobak (Related Actor Appellation; Related Actor Role “Spouse”; Relationship Actor Role “Spouse”; Relationship Date Begin “1945-05-08”; Relationship date Begin Qualifier “after”; Relationship Date End “2012-09-24”; Relationship Type “Marital”) whom she met after Victory in Europe Day in London, England. They married in 1945 and had two children, Alexander (Related Actor Appellation; Related Actor Role “Child”; Relationship Actor Role “Parent”; Relationship Date Begin “1946”; Relationship date Begin Qualifier “during”; Relationship Date End “2014-03-02”; Relationship Type “Parental”) and Anny (Related Actor Appellation; Related Actor Role “Child”; Relationship Actor Role “Parent”; Relationship Date Begin “1957”; Relationship date Begin Qualifier “during”; Relationship Date End “2014-03-02”; Relationship Type “Parental”).|
|**Edge Case(s)**|There might be cases where the Relationship Date Begin and the Relationship Date Begin Qualifier would be the same, in particular when it comes to eras. For example, “Victorian Era” can be both the Relationship Date Begin and the Relationship Date Begin Qualifier. Determining what eras the qualifiers will entail (through the vocabulary used to handle them) will thus be paramount.<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Relationship Date Begin Qualifier: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|There can be more than one qualifier at once for a single Relationship Date Begin (e.g. “BCE” and “BC”, which is the same information, the former being qualified using the non-christian acronym for “Before Common Era” and the latter using the christian “Before Christ”).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020), [(Wikipedia 2019o)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019o), [(Wikipedia 2019r)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019r), [(Wikipedia 2019w)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019w)|

---

## Relationship Date End

|---|---|
|**Scope**|This field designates the latest temporal instant of the association or acquaintance between entities, which may range in duration from brief to enduring and refers to the contacts between them as well as the way they behave towards each other.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|E39\_Actor|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P02i\_is\_range\_of -\> crm:PC14\_carried\_out\_by -\> crm:P01\_has\_domain -\> crm:E7\_Activity -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82b\_end\_of\_the\_end -\> **xsd:dateTime**</span>|
|**Target Model View(s)**|[Relationships](https://chin-rcip.github.io/collections-model/target-model/current/life-events#influences)|
|**Semantic Valuation**|*Low*: The value provided temporalizes the beginning of the event, but this information cannot be automatically extracted and formatted.<br><br>*Medium*: The date can be automatically extracted from the value provided (and from textual content that surrounds it if applicable) and can be formatted using the YYYY-MM-DD convention.<br>Accepted Value Type(s): String<br><br>*High*: The date is the sole value provided and is formatted using the date convention.<br>Accepted Value Type(s): DateTime (YYYY-MM-DDThh:mm:ss)|
|**Typical Case(s)**|Molly Bobak (Actor Appellation) married Brunislaw Jacob Bobak (Related Actor Appellation; Related Actor Role “Spouse”; Relationship Actor Role “Spouse”; Relationship Date Begin “1945-05-08”; Relationship date Begin Qualifier “after”; Relationship Date End “2012-09-24”; Relationship Type “Marital”) whom she met after Victory in Europe Day in London, England. They married in 1945 and had two children, Alexander (Related Actor Appellation; Related Actor Role “Child”; Relationship Actor Role “Parent”; Relationship Date Begin “1946”; Relationship date Begin Qualifier “during”; Relationship Date End “2014-03-02”; Relationship Type “Parental”) and Anny (Related Actor Appellation; Related Actor Role “Child”; Relationship Actor Role “Parent”; Relationship Date Begin “1957”; Relationship date Begin Qualifier “during”; Relationship Date End “2014-03-02”; Relationship Type “Parental”).|
|**Edge Case(s)**|At the moment it is unclear how groups can be represented when it comes to relationships. The Relationship field should not be used to indicate an individual’s belonging to a group, but it can be used to record groups’ relationships to one another, including corporations. So for example, these fields would not be used to record Tom Thomson being part of the Group of Seven, but it would be used to record the Canadian War Artists Selection Committee (Group Appellation) is related to the Canadian War Records (Group Appellation), Canada’s Second World War art program. However, this points to Actor relationships, and groups *can be actors*per current definitions.<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Relationship Date End: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|CHIN recommends using the following format when entering dates: “YYYY-MM-DD HH:MM:SS”. However, if the data cannot be converted to such a format (such as in the case of an era), a string can be used (e.g. Han Dynasty).|
|**Reference(s)**|[(Deutsche National Bibliothek 2019)](/collections-model/semantic-paths-specification/current/bibliography#deutsche-national-bibliothek-2019), [(Free Dictionary 2019ae)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019ae), [(Wikipedia 2019ar)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019ar)|

---

## Relationship Date End Qualifier

|---|---|
|**Scope**|This field qualifies the latest temporal instant of the association or acquaintance between entities, which may range in duration from brief to enduring and refers to the contacts between them as well as the way they behave towards each other.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Relationship Date End](#relationship-date-end)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P02i\_is\_range\_of -\> crm:PC14\_carried\_out\_by -\> crm:P01\_has\_domain -\> crm:E7\_Activity -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P80\_end\_is\_qualified\_by -\> **xsd:string**</span>|
|**Target Model View(s)**|[Relationships](https://chin-rcip.github.io/collections-model/target-model/current/life-events#influences)|
|**Semantic Valuation**|*Low*: The value provided qualifies the date of the event, but this information is unstructured and cannot be automatically formatted.<br><br>*Medium*: The value provided qualifies the date of the event and can be (semi-)automatically cleaned and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String<br><br>*High*: The qualifier is the sole value provided and is structured and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String|
|**Typical Case(s)**|Molly Bobak (Actor Appellation) married Brunislaw Jacob Bobak (Related Actor Appellation; Related Actor Role “Spouse”; Relationship Actor Role “Spouse”; Relationship Date Begin “1945-05-08”; Relationship date Begin Qualifier “after”; Relationship Date End “2012-09-24”; Relationship Type “Marital”) whom she met after Victory in Europe Day in London, England. They married in 1945 and had two children, Alexander (Related Actor Appellation; Related Actor Role “Child”; Relationship Actor Role “Parent”; Relationship Date Begin “1946”; Relationship date Begin Qualifier “during”; Relationship Date End “2014-03-02”; Relationship Type “Parental”) and Anny (Related Actor Appellation; Related Actor Role “Child”; Relationship Actor Role “Parent”; Relationship Date Begin “1957”; Relationship date Begin Qualifier “during”; Relationship Date End “2014-03-02”; Relationship Type “Parental”).|
|**Edge Case(s)**|There might be cases where the Relationship Date End and the Relationship Date End Qualifier would be the same, in particular when it comes to eras. For example, “Victorian Era” can be both the Relationship Date End and the Relationship Date End Qualifier. Determining what eras the qualifiers will entail (through the vocabulary used to handle them) will thus be paramount.<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Relationship Date End Qualifier: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|There can be more than one qualifier at once for a single Relationship Date End (e.g. “BCE” and “BC”, which is the same information, the former being qualified using the non-christian acronym for “Before Common Era” and the latter using the christian “Before Christ”).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020), [(Wikipedia 2019o)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019o), [(Wikipedia 2019r)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019r), [(Wikipedia 2019w)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019w)|

---

## Relationship Type

|---|---|
|**Scope**|This field qualifies the association or acquaintance between entities, which may range in duration from brief to enduring and refers to the contacts between them as well as the way they behave towards each other. It conceptually characterizes relationships in order to identify them based on interconnections between entities, whether they be actors or organizations.|
|**Generated Bond(s)**|E55\_Type|
|**Dependency(ies)**|E39\_Actor|
|**Related SQN(s)**|Relationship: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P02i\_is\_range\_of -\> crm:PC14\_carried\_out\_by -\> crm:P01\_has\_domain -\> crm:E7\_Activity -\> crm:P2\_has\_type -\> **crm:E55\_Type** (*-\> crm:P2\_has\_type -\> crm:E55\_Type\["Relationship"\]*)</span>|
|**Target Model View(s)**|[Relationships](https://chin-rcip.github.io/collections-model/target-model/current/life-events#influences)|
|**Semantic Valuation**|*Low*: The value provided is a string that cannot be parsed automatically by reconciliation tools but still contains the required information.<br><br>*Medium*: The value provided is a string that can be automatically cleaned and reconciled using controlled vocabularies specified by CHIN. In the event that the value is adequately structured but does not reconcile with any terms from the controlled vocabulary, and provided that it is deemed relevant, CHIN will add the term to the vocabulary.<br>Accepted Value Type(s): String<br><br>*High*: The provided value is a string that can be automatically reconciled with the controlled vocabularies specified by CHIN.<br>Accepted Value Type(s): String, URI|
|**Typical Case(s)**|Molly Bobak (Actor Appellation) married Brunislaw Jacob Bobak (Related Actor Appellation; Related Actor Role “Spouse”; Relationship Actor Role “Spouse”; Relationship Date Begin “1945-05-08”; Relationship date Begin Qualifier “after”; Relationship Date End “2012-09-24”; Relationship Type “Marital”) whom she met after Victory in Europe Day in London, England. They married in 1945 and had two children, Alexander (Related Actor Appellation; Related Actor Role “Child”; Relationship Actor Role “Parent”; Relationship Date Begin “1946”; Relationship date Begin Qualifier “during”; Relationship Date End “2014-03-02”; Relationship Type “Parental”) and Anny (Related Actor Appellation; Related Actor Role “Child”; Relationship Actor Role “Parent”; Relationship Date Begin “1957”; Relationship date Begin Qualifier “during”; Relationship Date End “2014-03-02”; Relationship Type “Parental”).|
|**Edge Case(s)**|At the moment it is unclear how groups can be represented when it comes to relationships. The Relationship field should not be used to indicate an individual’s belonging to a group, but it can be used to record groups’ relationships to one another, including corporations. So for example, these fields would not be used to record Tom Thomson being part of the Group of Seven, but it would be used to record the Canadian War Artists Selection Committee (Group Appellation) is related to the Canadian War Records (Group Appellation), Canada’s Second World War art program. However, this points to Actor relationships, and groups *can be actors*per current definitions.|
|**Value Origin(s)**|Actors Checklist: Relationship Type: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|TBD|
|**Reference(s)**|[(Deutsche National Bibliothek 2019)](/collections-model/semantic-paths-specification/current/bibliography#deutsche-national-bibliothek-2019), [(Free Dictionary 2019ae)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019ae), [(Wikipedia 2019ar)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019ar)|

---

## Social Status Type

|---|---|
|**Scope**|This field indicates the relative rank and possible honour or prestige an actor holds relative to how well they are perceived to match society’s goals and ideals, as well as their associated hierarchical position in the group’s social stratification. Status reflects a set of connected behaviours, activities, functions, rights, obligations, duties, beliefs, lifestyle, and norms. It relies on the interactions between said actor and a community whose conference of the status upon the actor is a determining factor in the latter having tasks, rights, and beliefs associated with said status.|
|**Generated Bond(s)**|E55\_Type|
|**Dependency(ies)**|E39\_Actor|
|**Related SQN(s)**|Social Status: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P14i\_performed -\> crm:E7\_Activity -\> crm:P2\_has\_type -\> **crm:E55\_Type** (*-\> crm:P2\_has\_type -\> crm:E55\_Type\["Social Status"\]*)</span>|
|**Target Model View(s)**|[Social Status](https://chin-rcip.github.io/collections-model/target-model/current/life-events#social-status)|
|**Semantic Valuation**|*Low*: The value provided is a string that cannot be parsed automatically by reconciliation tools but still contains the required information.<br><br>*Medium*: The value provided is a string that can be automatically cleaned and reconciled using controlled vocabularies specified by CHIN. In the event that the value is adequately structured but does not reconcile with any terms from the controlled vocabulary, and provided that it is deemed relevant, CHIN will add the term to the vocabulary.<br>Accepted Value Type(s): String<br><br>*High*: The provided value is a string that can be automatically reconciled with the controlled vocabularies specified by CHIN.<br>Accepted Value Type(s): String, URI|
|**Typical Case(s)**|Aung San Suu Kyi was awarded honorary Canadian citizenship (Social Status Type “Honorary Citizenship”) in 2007 (Social Status Date Begin; Social Status Date Begin Qualifier “during”). The honour was revoked by the House of Commons on September 27, 2018 and by the Senate on October 2, 2018 due to human rights concerns over her treatment of the Rohingya (Social Status Date End “2018-09-27” (debatable); Social Status Date End Qualifier “before” (debatable); Social Status Place “Canada”).|
|**Edge Case(s)**|Alice Ann Munro (Actor Appellation) is a Canadian short story writer and recipient of the Nobel Prize in Literature (Social Status Type “Nobel Laureate”), which she was awarded in Stockholm in 2013 (Social Status Place “Stockholm”; Social Status Date Begin “2013-10-10”). Munro died in 2013 shortly after having received the award (Social Status Date End “2013-10-10”; Social Status Date End Qualifier “after). It is debatable whether there is a natural end to a status (i.e. when the actor dies) or if the only way to end a status is by the official revocation of that status (i.e. those that conferred it strip the recipient of it).|
|**Value Origin(s)**|Actors Checklist: Social Status Type: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|Defining a social status type requires identifying the generalizable characteristics and symbols applicable to all who are said to have that status. These characteristics must be contingent, relational, and dynamic in the sense that what they entail might change over time, but they must nonetheless remain salient.<br><br>A single actor can carry multiple different statuses at one time, just like they can carry a single status multiples times simultaneously. An actor’s status tends to vary with social context: in certain societies, lineage is the main determinant of status whilst in others professional occupations are more predominant.|
|**Reference(s)**|[(Art & Architecture Thesaurus 2019z)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019z), [(Encyclopædia Britannica 2019)](/collections-model/semantic-paths-specification/current/bibliography#encyclopædia-britannica-2019), [(Free Dictionary 2019aj)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019aj), [(Wikipedia 2019at)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019at), [(Wikipedia 2019au)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019au)|

---

## Social Status Date Begin

|---|---|
|**Scope**|This field designates the earliest temporal instant at which the Actor assumed the social status recorded.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Social Status Type](#social-status-type)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P14i\_performed -\> crm:E7\_Activity -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82a\_begin\_of\_the\_begin -\> **xsd:dateTime**</span>|
|**Target Model View(s)**|[Social Status](https://chin-rcip.github.io/collections-model/target-model/current/life-events#social-status)|
|**Semantic Valuation**|*Low*: The value provided temporalizes the beginning of the event, but this information cannot be automatically extracted and formatted.<br><br>*Medium*: The date can be automatically extracted from the value provided (and from textual content that surrounds it if applicable) and can be formatted using the YYYY-MM-DD convention.<br>Accepted Value Type(s): String<br><br>*High*: The date is the sole value provided and is formatted using the date convention.<br>Accepted Value Type(s): DateTime (YYYY-MM-DDThh:mm:ss)|
|**Typical Case(s)**|Aung San Suu Kyi was awarded honorary Canadian citizenship (Social Status Type “Honorary Citizenship”) in 2007 (Social Status Date Begin; Social Status Date Begin Qualifier “during”). The honour was revoked by the House of Commons on September 27, 2018 and by the Senate on October 2, 2018 due to human rights concerns over her treatment of the Rohingya (Social Status Date End “2018-09-27” (debatable); Social Status Date End Qualifier “before” (debatable); Social Status Place “Canada”).|
|**Edge Case(s)**|For prizes and other awards it is easier to identify a Social Status Date Begin, but even then it could be argued that the award differs from the status and that it is a recognition of a status that the actor already held. As such, it could be argued that such Social Status Date Begin would require qualifiers.<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Social Status Date Begin: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|CHIN recommends using the following format when entering dates: “YYYY-MM-DD HH:MM:SS”. However, if the data cannot be converted to such a format (such as in the case of an era), a string can be used (e.g. Han Dynasty).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020)|

---

## Social Status Date Begin Qualifier

|---|---|
|**Scope**|This field qualifies the earliest temporal instant at which the actor assumed the social status recorded.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Social Status Date Begin](#social-status-date-begin)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P14i\_performed -\> crm:E7\_Activity -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P79\_beginning\_is\_qualified\_by -\> **xsd:string**</span>|
|**Target Model View(s)**|[Social Status](https://chin-rcip.github.io/collections-model/target-model/current/life-events#social-status)|
|**Semantic Valuation**|*Low*: The value provided qualifies the date of the event, but this information is unstructured and cannot be automatically formatted.<br><br>*Medium*: The value provided qualifies the date of the event and can be (semi-)automatically cleaned and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String<br><br>*High*: The qualifier is the sole value provided and is structured and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String|
|**Typical Case(s)**|Aung San Suu Kyi was awarded honorary Canadian citizenship (Social Status Type “Honorary Citizenship”) in 2007 (Social Status Date Begin; Social Status Date Begin Qualifier “during”). The honour was revoked by the House of Commons on September 27, 2018 and by the Senate on October 2, 2018 due to human rights concerns over her treatment of the Rohingya (Social Status Date End “2018-09-27” (debatable); Social Status Date End Qualifier “before” (debatable); Social Status Place “Canada”).|
|**Edge Case(s)**|There might be cases where the Social Status Date Begin and the Social Status Date Begin Qualifier would be the same, in particular when it comes to eras. For example, “Victorian Era” can be both the Social Status Date Begin and the Social Status Date Begin Qualifier. Determining what eras the qualifiers will entail (through the vocabulary used to handle them) will thus be paramount.<br><br>For prizes and other awards it is easier to identify a Social Status Date Begin, but even then it could be argued that the award differs from the status and that it is a recognition of a status that the actor already held. As such, it could be argued that such Social Status Date Begin would require qualifiers.<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Social Status Date Begin Qualifier: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|There can be more than one qualifier at once for a single Social Status Date Begin (e.g. “BCE” and “BC”, which is the same information, the former being qualified using the non-christian acronym for “Before Common Era” and the latter using the christian “Before Christ”).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020), [(Wikipedia 2019o)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019o), [(Wikipedia 2019r)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019r), [(Wikipedia 2019w)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019w)|

---

## Social Status Date End

|---|---|
|**Scope**|This field designates the latest temporal instant at which the actor assumed the social status recorded.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Social Status Type](#social-status-type)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P14i\_performed -\> crm:E7\_Activity -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82b\_end\_of\_the\_end -\> **xsd:dateTime**</span>|
|**Target Model View(s)**|[Social Status](https://chin-rcip.github.io/collections-model/target-model/current/life-events#social-status)|
|**Semantic Valuation**|*Low*: The value provided temporalizes the beginning of the event, but this information cannot be automatically extracted and formatted.<br><br>*Medium*: The date can be automatically extracted from the value provided (and from textual content that surrounds it if applicable) and can be formatted using the YYYY-MM-DD convention.<br>Accepted Value Type(s): String<br><br>*High*: The date is the sole value provided and is formatted using the date convention.<br>Accepted Value Type(s): DateTime (YYYY-MM-DDThh:mm:ss)|
|**Typical Case(s)**|Aung San Suu Kyi was awarded honorary Canadian citizenship (Social Status Type “Honorary Citizenship”) in 2007 (Social Status Date Begin; Social Status Date Begin Qualifier “during”). The honour was revoked by the House of Commons on September 27, 2018 and by the Senate on October 2, 2018 due to human rights concerns over her treatment of the Rohingya (Social Status Date End “2018-09-27” (debatable); Social Status Date End Qualifier “before” (debatable); Social Status Place “Canada”).|
|**Edge Case(s)**|Alice Ann Munro (Actor Appellation) is a Canadian short story writer and recipient of the Nobel Prize in Literature (Social Status Type “Nobel Laureate”), which she was awarded in Stockholm in 2013 (Social Status Place “Stockholm”; Social Status Date Begin “2013-10-10”). Munro died in 2013 shortly after having received the award (Social Status Date End “2013-10-10”; Social Status Date End Qualifier “after). It is debatable whether there is a natural end to a status (i.e. when the actor dies) or if the only way to end a status is by the official revocation of that status (i.e. those that conferred it strip the recipient of it).<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Social Status Date End: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|CHIN recommends using the following format when entering dates: “YYYY-MM-DD HH:MM:SS”. However, if the data cannot be converted to such a format (such as in the case of an era), a string can be used (e.g. Han Dynasty).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020)|

---

## Social Status Date End Qualifier

|---|---|
|**Scope**|This field qualifies the latest temporal instant at which the actor assumed the social role recorded.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Social Status Date End](#social-status-date-end)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P14i\_performed -\> crm:E7\_Activity -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P80\_end\_is\_qualified\_by -\> **xsd:string**</span>|
|**Target Model View(s)**|[Social Status](https://chin-rcip.github.io/collections-model/target-model/current/life-events#social-status)|
|**Semantic Valuation**|*Low*: The value provided qualifies the date of the event, but this information is unstructured and cannot be automatically formatted.<br><br>*Medium*: The value provided qualifies the date of the event and can be (semi-)automatically cleaned and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String<br><br>*High*: The qualifier is the sole value provided and is structured and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String|
|**Typical Case(s)**|Aung San Suu Kyi was awarded honorary Canadian citizenship (Social Status Type “Honorary Citizenship”) in 2007 (Social Status Date Begin; Social Status Date Begin Qualifier “during”). The honour was revoked by the House of Commons on September 27, 2018 and by the Senate on October 2, 2018 due to human rights concerns over her treatment of the Rohingya (Social Status Date End “2018-09-27” (debatable); Social Status Date End Qualifier “before” (debatable); Social Status Place “Canada”).|
|**Edge Case(s)**|Alice Ann Munro (Actor Appellation) is a Canadian short story writer and recipient of the Nobel Prize in Literature (Social Status Type “Nobel Laureate”), which she was awarded in Stockholm in 2013 (Social Status Place “Stockholm”; Social Status Date Begin “2013-10-10”). Munro died in 2013 shortly after having received the award (Social Status Date End “2013-10-10”; Social Status Date End Qualifier “after). It is debatable whether there is a natural end to a status (i.e. when the actor dies) or if the only way to end a status is by the official revocation of that status (i.e. those that conferred it strip the recipient of it).<br><br>There might be cases where the Social Status Date End and the Social Status Date End Qualifier would be the same, in particular when it comes to eras. For example, “Victorian Era” can be both the Social Status Date End and the Social Status Date End Qualifier. Determining what eras the qualifiers will entail (through the vocabulary used to handle them) will thus be paramount.<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Social Status Date End Qualifier: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|There can be more than one qualifier at once for a single Social Status Date End (e.g. “BCE” and “BC”, which is the same information, the former being qualified using the non-christian acronym for “Before Common Era” and the latter using the christian “Before Christ”).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020), [(Wikipedia 2019o)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019o), [(Wikipedia 2019r)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019r), [(Wikipedia 2019w)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019w)|

---

## Social Status Place

|---|---|
|**Scope**|This field identifies the location(s) in which the Actor assumed their social status.|
|**Generated Bond(s)**|E53\_Place|
|**Dependency(ies)**|[Social Status Type](#social-status-type)|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P14i\_performed -\> crm:E7\_Activity -\> crm:P7\_took\_place\_at -\> **crm:E53\_Place**</span>|
|**Target Model View(s)**|[Social Status](https://chin-rcip.github.io/collections-model/target-model/current/life-events#social-status)|
|**Semantic Valuation**|*Low*: The value provided is a string that cannot be parsed automatically by reconciliation tools but still contains the required information.<br><br>*Medium*: The value provided is a string that can be automatically cleaned and reconciled using controlled vocabularies specified by CHIN. In the event that the value is adequately structured but does not reconcile with any terms from the controlled vocabulary, and provided that it is deemed relevant, CHIN will add the term to the vocabulary.<br>Accepted Value Type(s): String<br><br>*High*: The provided value is a string that can be automatically reconciled with the controlled vocabularies specified by CHIN.<br>Accepted Value Type(s): String, URI|
|**Typical Case(s)**|Aung San Suu Kyi was awarded honorary Canadian citizenship (Social Status Type “Honorary Citizenship”) in 2007 (Social Status Date Begin; Social Status Date Begin Qualifier “during”). The honour was revoked by the House of Commons on September 27, 2018 and by the Senate on October 2, 2018 due to human rights concerns over her treatment of the Rohingya (Social Status Date End “2018-09-27” (debatable); Social Status Date End Qualifier “before” (debatable); Social Status Place “Canada”).|
|**Edge Case(s)**|Alice Ann Munro (Actor Appellation) is a Canadian short story writer and recipient of the Nobel Prize in Literature (Social Status Type “Nobel Laureate”), which she was awarded in Stockholm in 2013 (Social Status Place “Stockholm”; Social Status Date Begin “2013-10-10”). Munro died in 2013 shortly after having received the award (Social Status Date End “2013-10-10”; Social Status Date End Qualifier “after). It is debatable whether a status is limited to a Place? Is Munro not a Nobel Prize recipient worldwide?|
|**Value Origin(s)**|Actors Checklist: Social Status Place: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|This field accommodates all forms of modern and historical locations, physical features, or nations, on Earth or not.|
|**Reference(s)**|[(Le Boeuf et al. 2015, sec. E53 Place)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Bekiari et al. 2015, sec. F9 Place)](/collections-model/semantic-paths-specification/current/bibliography#bekiari-et-al-2015), [(Free Dictionary 2019m)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019m), [(Free Dictionary 2019n)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019n), [(Thesaurus of Geographic Names 2019)](/collections-model/semantic-paths-specification/current/bibliography#thesaurus-of-geographic-names-2019), [(Wikipedia 2019am)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019am)|

---

## Stay Date Begin

|---|---|
|**Scope**|This field designates the earliest temporal instant of the Actor remaining somewhere for a prolonged or temporary duration, including at their customary residence/geographical location.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|E39\_Actor|
|**Related SQN(s)**|Stay: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P14i\_performed -\> crm:E7\_Activity (*-\> crm:P2\_has\_type -\> crm:E55\_Type\["Stay"\]*) -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82a\_begin\_of\_the\_begin -\> **xsd:dateTime**</span>|
|**Target Model View(s)**|[E7 Activity Stay for E21 Person and E74 Group](https://chin-rcip.github.io/collections-model/target-model/current/life-events#e7-activity-stay-for-e21-person-and-e74-group)|
|**Semantic Valuation**|*Low*: The value provided temporalizes the beginning of the event, but this information cannot be automatically extracted and formatted.<br><br>*Medium*: The date can be automatically extracted from the value provided (and from textual content that surrounds it if applicable) and can be formatted using the YYYY-MM-DD convention.<br>Accepted Value Type(s): String<br><br>*High*: The date is the sole value provided and is formatted using the date convention.<br>Accepted Value Type(s): DateTime (YYYY-MM-DDThh:mm:ss)|
|**Typical Case(s)**|Molly Bobak (Actor Appellation) was a Canadian artist (Occupation Type) who served as Second Lieutenant (Occupation Type) during World War II from November 1942 when she enlisted in the Canadian Women’s Army Corps to September 1945. She went to London, GB (Stay Place) after Victory in Europe Day and met her future husband there, Brunislaw Jacob Bobak (Stay Date Begin “1945-05-08”; Stay Date Begin Qualifier “after”; Stay Date End “1945-09”; Stay Date End Qualifier “during”).|
|**Edge Case(s)**|Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Stay Date Begin: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|CHIN recommends using the following format when entering dates: “YYYY-MM-DD HH:MM:SS”. However, if the data cannot be converted to such a format (such as in the case of an era), a string can be used (e.g. Han Dynasty).|
|**Reference(s)**|[(Art & Architecture Thesaurus 2019p)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019p), [(Free Dictionary 2019q)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019q), [(Free Dictionary 2019t)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019t), [(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020), [(Wikipedia 2019k)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019k)|

---

## Stay Date Begin Qualifier

|---|---|
|**Scope**|This field qualifies the earliest temporal instant of the actor remaining somewhere for a prolonged or temporary duration, including at their customary residence/geographical location.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Stay Date Begin](#stay-date-begin)|
|**Related SQN(s)**|Stay: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P14i\_performed -\> crm:E7\_Activity (*-\> crm:P2\_has\_type -\> crm:E55\_Type\["Stay"\]*) -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P79\_beginning\_is\_qualified\_by -\> **xsd:string**</span>|
|**Target Model View(s)**|[E7 Activity Stay for E21 Person and E74 Group](https://chin-rcip.github.io/collections-model/target-model/current/life-events#e7-activity-stay-for-e21-person-and-e74-group)|
|**Semantic Valuation**|*Low*: The value provided qualifies the date of the event, but this information is unstructured and cannot be automatically formatted.<br><br>*Medium*: The value provided qualifies the date of the event and can be (semi-)automatically cleaned and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String<br><br>*High*: The qualifier is the sole value provided and is structured and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String|
|**Typical Case(s)**|Molly Bobak (Actor Appellation) was a Canadian artist (Occupation Type) who served as Second Lieutenant (Occupation Type) during World War II from November 1942 when she enlisted in the Canadian Women’s Army Corps to September 1945. She went to London, GB (Stay Place) after Victory in Europe Day and met her future husband there, Brunislaw Jacob Bobak (Stay Date Begin “1945-05-08”; Stay Date Begin Qualifier “after”; Stay Date End “1945-09”; Stay Date End Qualifier “during”).|
|**Edge Case(s)**|There might be cases where the Stay Date Begin and the Stay Date Begin Qualifier would be the same, in particular when it comes to eras. For example, “Victorian Era” can be both the Stay Date Begin and the Stay Date Begin Qualifier. Determining what eras the qualifiers will entail (through the vocabulary used to handle them) will thus be paramount.<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Stay Date Begin Qualifier: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|There can be more than one qualifier at once for a single Stay Date Begin (e.g. “BCE” and “BC”, which is the same information, the former being qualified using the non-christian acronym for “Before Common Era” and the latter using the christian “Before Christ”).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020), [(Wikipedia 2019o)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019o), [(Wikipedia 2019r)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019r), [(Wikipedia 2019w)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019w)|

---

## Stay Date End

|---|---|
|**Scope**|This field designates the latest temporal instant of the Actor remaining somewhere for a prolonged or temporary duration, including at their customary residence/geographical location.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|E39\_Actor|
|**Related SQN(s)**|Stay: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P14i\_performed -\> crm:E7\_Activity (*-\> crm:P2\_has\_type -\> crm:E55\_Type\["Stay"\]*) -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P82b\_end\_of\_the\_end -\> **xsd:dateTime**</span>|
|**Target Model View(s)**|[E7 Activity Stay for E21 Person and E74 Group](https://chin-rcip.github.io/collections-model/target-model/current/life-events#e7-activity-stay-for-e21-person-and-e74-group)|
|**Semantic Valuation**|*Low*: The value provided temporalizes the beginning of the event, but this information cannot be automatically extracted and formatted.<br><br>*Medium*: The date can be automatically extracted from the value provided (and from textual content that surrounds it if applicable) and can be formatted using the YYYY-MM-DD convention.<br>Accepted Value Type(s): String<br><br>*High*: The date is the sole value provided and is formatted using the date convention.<br>Accepted Value Type(s): DateTime (YYYY-MM-DDThh:mm:ss)|
|**Typical Case(s)**|Molly Bobak (Actor Appellation) was a Canadian artist (Occupation Type) who served as Second Lieutenant (Occupation Type) during World War II from November 1942 when she enlisted in the Canadian Women’s Army Corps to September 1945. She went to London, GB (Stay Place) after Victory in Europe Day and met her future husband there, Brunislaw Jacob Bobak (Stay Date Begin “1945-05-08”; Stay Date Begin Qualifier “after”; Stay Date End “1945-09”; Stay Date End Qualifier “during”).|
|**Edge Case(s)**|Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Stay Date End: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|CHIN recommends using the following format when entering dates: “YYYY-MM-DD HH:MM:SS”. However, if the data cannot be converted to such a format (such as in the case of an era), a string can be used (e.g. Han Dynasty).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020)|

---

## Stay Date End Qualifier

|---|---|
|**Scope**|This field qualifies the latest temporal instant of the actor remaining somewhere for a prolonged or temporary duration, including at their customary residence/geographical location.|
|**Generated Bond(s)**|rdfs:Literal|
|**Dependency(ies)**|[Stay Date End](#stay-date-end)|
|**Related SQN(s)**|Stay: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P14i\_performed -\> crm:E7\_Activity (*-\> crm:P2\_has\_type -\> crm:E55\_Type\["Stay"\]*) -\> crm:P4\_has\_time-span -\> crm:E52\_Time-Span -\> crm:P80\_end\_is\_qualified\_by -\> **xsd:string**</span>|
|**Target Model View(s)**|[E7 Activity Stay for E21 Person and E74 Group](https://chin-rcip.github.io/collections-model/target-model/current/life-events#e7-activity-stay-for-e21-person-and-e74-group)|
|**Semantic Valuation**|*Low*: The value provided qualifies the date of the event, but this information is unstructured and cannot be automatically formatted.<br><br>*Medium*: The value provided qualifies the date of the event and can be (semi-)automatically cleaned and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String<br><br>*High*: The qualifier is the sole value provided and is structured and formatted using CHIN’s convention regarding qualifiers (to be decided)<br>Accepted Value Type(s): String|
|**Typical Case(s)**|Molly Bobak (Actor Appellation) was a Canadian artist (Occupation Type) who served as Second Lieutenant (Occupation Type) during World War II from November 1942 when she enlisted in the Canadian Women’s Army Corps to September 1945. She went to London, GB (Stay Place) after Victory in Europe Day and met her future husband there, Brunislaw Jacob Bobak (Stay Date Begin “1945-05-08”; Stay Date Begin Qualifier “after”; Stay Date End “1945-09”; Stay Date End Qualifier “during”).|
|**Edge Case(s)**|There might be cases where the Stay Date End and the Stay Date End Qualifier would be the same, in particular when it comes to eras. For example, “Victorian Era” can be both the Stay Date End and the Stay Date End Qualifier. Determining what eras the qualifiers will entail (through the vocabulary used to handle them) will thus be paramount.<br><br>Some important dates in history have alternative names that could be considered to be either alternate appellations or qualifiers, such as 9/11, Victory in Europe Day, D-Day, etc.|
|**Value Origin(s)**|Actors Checklist: Stay Date End Qualifier: Provider Data|
|**Controlled List/Term**|TBD|
|**Potential Error(s)**|TBD|
|**Comment(s)**|There can be more than one qualifier at once for a single Stay Date End (e.g. “BCE” and “BC”, which is the same information, the former being qualified using the non-christian acronym for “Before Common Era” and the latter using the christian “Before Christ”).|
|**Reference(s)**|[(Hart \[2019\] 2020)](/collections-model/semantic-paths-specification/current/bibliography#hart-2020), [(Wikipedia 2019o)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019o), [(Wikipedia 2019r)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019r), [(Wikipedia 2019w)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019w)|

---

## Stay Place

|---|---|
|**Scope**|This field identifies the location of the actor remaining somewhere for a prolonged or temporary duration, including at their customary residence/geographical location.|
|**Generated Bond(s)**|E53\_Place|
|**Dependency(ies)**|E39\_Actor|
|**Related SQN(s)**|Stay: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P14i\_performed -\> crm:E7\_Activity (*-\> crm:P2\_has\_type -\> crm:E55\_Type\["Stay"\]*) -\> crm:P7\_took\_place\_at -\> **crm:E53\_Place**</span>|
|**Target Model View(s)**|[E7 Activity Stay for E21 Person and E74 Group](https://chin-rcip.github.io/collections-model/target-model/current/life-events#e7-activity-stay-for-e21-person-and-e74-group)|
|**Semantic Valuation**|*Low*: The value provided is a string that cannot be parsed automatically by reconciliation tools but still contains the required information.<br><br>*Medium*: The value provided is a string that can be automatically cleaned and reconciled using controlled vocabularies specified by CHIN. In the event that the value is adequately structured but does not reconcile with any terms from the controlled vocabulary, and provided that it is deemed relevant, CHIN will add the term to the vocabulary.<br>Accepted Value Type(s): String<br><br>*High*: The provided value is a string that can be automatically reconciled with the controlled vocabularies specified by CHIN.<br>Accepted Value Type(s): String, URI|
|**Typical Case(s)**|Molly Bobak (Actor Appellation) was a Canadian artist (Occupation Type) who served as Second Lieutenant (Occupation Type) during World War II from November 1942 when she enlisted in the Canadian Women’s Army Corps to September 1945. She went to London, GB (Stay Place) after Victory in Europe Day and met her future husband there, Brunislaw Jacob Bobak (Stay Date Begin “1945-05-08”; Stay Date Begin Qualifier “after”; Stay Date End “1945-09”; Stay Date End Qualifier “during”).|
|**Edge Case(s)**|Could a Stay take place in a virtual environment, such as Second Life? If so, is the Actor sojourning the individual operating the avatar and is the avatar an alternate appellation, or an actor in and of itself?|
|**Value Origin(s)**|Actors Checklist: Stay Place: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|This field accommodates all forms of modern and historical locations, physical features, or nations, on Earth or not.|
|**Reference(s)**|[(Le Boeuf et al. 2015, sec. E53 Place)](/collections-model/semantic-paths-specification/current/bibliography#le-boeuf-et-al-2015), [(Bekiari et al. 2015, sec. F9 Place)](/collections-model/semantic-paths-specification/current/bibliography#bekiari-et-al-2015), [(Free Dictionary 2019m)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019m), [(Free Dictionary 2019n)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019n), [(Thesaurus of Geographic Names 2019)](/collections-model/semantic-paths-specification/current/bibliography#thesaurus-of-geographic-names-2019), [(Wikipedia 2019am)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019am)|

---

## Technique Used

|---|---|
|**Scope**|This field identifies the combination of ability, skills, methods and materials used by the creator to achieve a particular product or endeavour.|
|**Generated Bond(s)**|E55\_Type|
|**Dependency(ies)**|E39\_Actor|
|**Related SQN(s)**|Technique: Definition|
|**Full Path**|<span class="full-path">crm:E39\_Actor -\> crm:P2\_has\_type -\> **crm:E55\_Type** (*-\> crm:P2\_has\_type -\> crm:E55\_Type\["Technique"\]*)</span>|
|**Target Model View(s)**|[Technique Used](https://chin-rcip.github.io/collections-model/target-model/current/life-events#technique-used)|
|**Semantic Valuation**|*Low*: The value provided is a string that cannot be parsed automatically by reconciliation tools but still contains the required information.<br><br>*Medium*: The value provided is a string that can be automatically cleaned and reconciled using controlled vocabularies specified by CHIN. In the event that the value is adequately structured but does not reconcile with any terms from the controlled vocabulary, and provided that it is deemed relevant, CHIN will add the term to the vocabulary.<br>Accepted Value Type(s): String<br><br>*High*: The provided value is a string that can be automatically reconciled with the controlled vocabularies specified by CHIN.<br>Accepted Value Type(s): String, URI|
|**Typical Case(s)**|*Flightstop* (Object Appellation; Object Appellation Language “English”; Object Appellation Type “Title”; Object Appellation Preference “Preferred”) is a sculpture (Object Medium and Technique Used) by artist (Occupation Type) Michael Snow (Actor Appellation), sometimes titled *Flight Stop*(Object Appellation; Object Appellation Language “English”; Object Appellation Type “Title”; Object Appellation Preference “Non-Preferred”). It has been displayed at the Toronto Eaton Centre (Object Record Contributor Appellation) since 1979 (Object Record Date Begin) when it was made and installed.|
|**Edge Case(s)**|In the case above, whether to record “sculpture” as a medium, a technique, or both, is up for debate.|
|**Value Origin(s)**|Actors Checklist: Technique Used: Provider Data|
|**Controlled List/Term**|N/A|
|**Potential Error(s)**|TBD|
|**Comment(s)**|Technique is distinct from medium, although both concepts often intersect and the latter will eventually be covered in the Objects Facet. Whilst Technique pertains to the actor, medium pertains to the object.|
|**Reference(s)**|[(Art & Architecture Thesaurus 2019j)](/collections-model/semantic-paths-specification/current/bibliography#art-architecture-thesaurus-2019j), [(Canadian Heritage Information Network (CHIN) 1999)](/collections-model/semantic-paths-specification/current/bibliography#canadian-heritage-information-network-1999), [(Free Dictionary 2019k)](/collections-model/semantic-paths-specification/current/bibliography#free-dictionary-2019k), [(Museum of Modern Art 2019)](/collections-model/semantic-paths-specification/current/bibliography#museum-of-modern-art-2019), [(Société des musées du Québec (SMQ) 2015)](/collections-model/semantic-paths-specification/current/bibliography#société-des-musées-du-québec-2015), [(Wikipedia 2019z)](/collections-model/semantic-paths-specification/current/bibliography#wikipedia-2019z)|

