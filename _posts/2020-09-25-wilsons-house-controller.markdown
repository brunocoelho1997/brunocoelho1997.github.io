---
layout: post
title: Wilson's House Controller
date: 2020-09-16 13:32:20 +0300
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: project_wilsonshousecontroller/2.jpeg # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [Holidays, Hawaii]
---

During my master's degree, I was challenged by Marco Wilson to develop something that he would be enabled to control his house. He was already developing a controller with a PLC (Siemens PLC 1200) and with an HMI (Beijer), however, he also likes to have an android controller.
I embraced the challenge as if the controller would be used to my house.


## Description


<img src="{{site.baseurl}}/assets/img/project_wilsonshousecontroller/2.jpeg" alt="Result" class="post-images">

Firstly I did research about PLCs and how I could communicate with it. After some research, I developed an architecture diagram (the result can be seen in the following picture).

As it's possible to see in the picture, we have 4 elements:
* S7 - the Siemens PLC 1200. To develop was always used an emulator was installed on my computer since I didn't have a PLC to execute my tests.
* API - Was developed a Java API using Spring Boot. I used a library to communicate with the PLC. This API is where all logic was developed.
* Database - all data was persisted on a Postgresql database.
* Android - where the user could control the house.

![Main Page]({{site.baseurl}}/assets/img/project_wilsonshousecontroller/Architecture-v0.2.drawio.png)


## Features (in real-time)

* Watch which windows are open/closed
* Watch which blinders are open/closed
* Close/open blinders (e.g: 10%, 25%, etc)
* Close/open gates
* Watch all smart devices (blinders, gates, etc) with filters (e.g: filter by room, device type, etc)
* Actual temperature - inside and outside the house
* Watch the actual humidity and wind velocity outside the house
* Easily configurable - the API was developed to be agile and flexible. It's only necessary to have an Excel sheet and after the start API, the system is configured. E.g: new sensors, new gates, etc.

In this project, since the API and the database would run on a Raspberry 24/7, was developed a shell script that could install all system on a new raspberry. All this setup was tested using a Raspberry emulator.

[![Video of the final result]({{site.baseurl}}/assets/img/project_wilsonshousecontroller/6.png)](https://www.youtube.com/watch?v=eyZEG0dXo7Q)


## More images of the project
<img src="{{site.baseurl}}/assets/img/project_wilsonshousecontroller/1.JPG" alt="Result" class="post-images">

<img src="{{site.baseurl}}/assets/img/project_wilsonshousecontroller/3.jpeg" alt="Result" class="post-images">

<img src="{{site.baseurl}}/assets/img/project_wilsonshousecontroller/4.jpeg" alt="Result" class="post-images">

<img src="{{site.baseurl}}/assets/img/project_wilsonshousecontroller/5.jpeg" alt="Result" class="post-images">

<img src="{{site.baseurl}}/assets/img/project_wilsonshousecontroller/6.jpeg" alt="Result" class="post-images">

<img src="{{site.baseurl}}/assets/img/project_wilsonshousecontroller/7.jpeg" alt="Result" class="post-images">

## References
* [Github Project](https://github.com/brunocoelho1997/Wilson-s-House-Controller)