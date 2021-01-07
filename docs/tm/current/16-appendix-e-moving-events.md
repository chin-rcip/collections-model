---
layout: page
title: Appendix E - Moving Events 
permalink: /target-model/current/appendix-e-moving-events
sidebar: tm
---
<!-- [Back to the Table of Contents](/collections-model/target-model/current/information#table-of-contents)
 -->
<div class="hidden-content">
## On This Page

* [Moving Events](#moving-events)
</div>

An `E39_Actor` may have had multiple addresses throughout their  life. Recording all of these and locating them geographically and temporally requires the use of `E9_Move`. With such a pattern, it is not the addresses of the `E39_Actor` that are documented, but the moving events of the actor from one place to another, that are recorded. Using such an approach would amount to the following pattern:

<a name="092_Pattern_Movement_p"></a>092_Pattern_Movement_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=092_Pattern_Movement_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1jicIEoSjQTFbQ3t6aDThpEj8xdI-oUnQ%26export%3Ddownload"></iframe>

However, `E9_Moves` are only applicable to physical objects, which an `E39_Actor` is not (`E21_Persons` are, unlike `E74_Groups`). Institutions and groups do not move either. It is thus best to account for institutional moves through a list of buildings or real estate they possess (such as headquarters) and to account for groups moving through sojourns. 

One option for `E74_Group` is to record real estate properties, date them and locate them geographically. This would enable the tracing of buildings a group occupied and make it possible to situate them on a map.

<a name="093_Pattern_GroupRealEstateAcquisition_p"></a>093_Pattern_GroupRealEstateAcquisition_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=093_Pattern_GroupRealEstateAcquisition_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1_sUihasZypveNX8v7TE7av8oEQYcAJJE%26export%3Ddownload"></iframe>

Considering the complexity of the first pattern and the relatively small amount of data CHIN is likely to receive when it comes to those fields, CHIN has elected to use the second pattern for the moment. 

It would also be possible to create an `E7_Activity` that would stand in for a sojourn. Both `E21_Person` and `E74_Group` would then have the same pattern and the model’s structure would be closer to museum data where documentation is most often about the fact that someone lived somewhere for a certain amount of time (as opposed to when the person moved). CHIN is currently debating this. 

<a name="094_Pattern_Sojourn_p"></a>094_Pattern_Sojourn_p
<iframe frameborder="0" style="width:100%;height:600px;" src="https://viewer.diagrams.net/?target=blank&highlight=0000ff&edit=_blank&layers=1&nav=1&title=094_Pattern_Sojourn_p.drawio#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1EjJKURs3c5ltx-ZMRJQdbEA-iVkC7zeM%26export%3Ddownload"></iframe>


> Previous:[Appendix D](/collections-model/target-model/current/appendix-d-relationships)<br>Next: [Appendix F](/collections-model/target-model/current/appendix-f-discussions)
