---
layout: page
title: Appendix E - Moving Events 
permalink: /target-model/current/appendix-e-moving-events
---
[Back to the Table of Contents](/target-model/current/information#table-of-contents)

An `E39 Actor` may have had multiple addresses throughout their  life. Recording all of these and locating them geographically and temporally requires the use of `E9 Move`. With such a pattern, it is not the addresses of the `E39 Actor` that are documented, but the moving events of the actor from one place to another, that are recorded. Using such an approach would amount to the following pattern:



<p id="gdcalert82" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-150.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert83">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-150.png "image_tooltip")


However, `E9 Moves` are only applicable to physical objects, which an `E39 Actor` is not (`E21 Persons` are, unlike `E74 Groups`). Institutions and groups do not move either. It is thus best to account for institutional moves through a list of buildings or real estate they possess (such as headquarters) and to account for groups moving through sojourns. 

One option for `E74 Group` is to record real estate properties, date them and locate them geographically. This would enable the tracing of buildings a group occupied and make it possible to situate them on a map.



<p id="gdcalert83" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-151.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert84">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-151.png "image_tooltip")


Considering the complexity of the first pattern and the relatively small amount of data CHIN is likely to receive when it comes to those fields, CHIN has elected to use the second pattern for the moment. 

It would also be possible to create an `E7 Activity` that would stand in for a sojourn. Both `E21 Person` and `E74 Group` would then have the same pattern and the model’s structure would be closer to museum data where documentation is most often about the fact that someone lived somewhere for a certain amount of time (as opposed to when the person moved). CHIN is currently debating this. 



<p id="gdcalert84" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/TM-Documentation-2-152.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert85">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/TM-Documentation-2-152.png "image_tooltip")