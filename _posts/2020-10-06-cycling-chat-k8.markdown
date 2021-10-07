---
layout: post
title: Cycling Chat - Kubernetes Project
date: 2020-10-08 13:32:20 +0300
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: project_cyclingchat/cycling_chat_logo.png # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [Holidays, Hawaii]
---

After some time being full-stack developer, I become a DevOps enthusiast. In order to improve my DevOps skills, I started to think of a new project with Kubernetes. So, since I had an older laptop with 2GB of RAM without a screen I remembered to create a Kubernetes cluster. With this laptop, I created a cluster with: my laptop as a master (with ubuntu) and this old laptop as a worker node (also with ubuntu).

## Description

Initially, I researched how to create a cluster and easily I found some content to help me with that. After some hours I had my cluster with the setup finished.

After having the cluster configured, I started to create a Spring Boot API with 1 endpoint (list all messages).
Secondly, I created the YAML templates of the deployment (of the spring boot app) and the service. With this, in order to automate the release of the spring boot app and all kubernetes templates, I used Helm and I configured all necessary YAMLs to automate the release.

Since the main goal of the application was a Cycling Chat, I deployed with Helm a Postgresql statefulset to save all messages that were published on a RabbitMQ statefulset (that also was deployed with Helm). To test this application was created a Java Application to publish messages on RabbitMQ.


--------------------------

<img src="{{site.baseurl}}/assets/img/project_wilsonshousecontroller/3.jpeg" alt="Result" class="post-images">

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
<img src="{{site.baseurl}}/assets/img/project_wilsonshousecontroller/1.jpeg" alt="Result" class="post-images">

<img src="{{site.baseurl}}/assets/img/project_wilsonshousecontroller/2.jpeg" alt="Result" class="post-images">

<img src="{{site.baseurl}}/assets/img/project_wilsonshousecontroller/4.jpeg" alt="Result" class="post-images">

<img src="{{site.baseurl}}/assets/img/project_wilsonshousecontroller/5.jpeg" alt="Result" class="post-images">

## References
* [Github Project](https://github.com/brunocoelho1997/Wilson-s-House-Controller)