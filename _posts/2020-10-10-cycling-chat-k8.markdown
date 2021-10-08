---
layout: post
title: Cycling Chat - Kubernetes Project
date: 2020-10-08 13:32:20 +0300
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: project_cyclingchat/3.png # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [Holidays, Hawaii]
---

After some time being full-stack developer, I become a DevOps enthusiast. In order to improve my DevOps skills, I started to think of a new project with Kubernetes. So, since I had an older laptop with 2GB of RAM without a screen I remembered to create a Kubernetes cluster. With this laptop, I created a cluster with: my laptop as a master (with ubuntu) and this old laptop as a worker node (also with ubuntu).

## Description

Initially, I researched how to create a cluster and easily I found some content to help me with that. After some hours I had my cluster with the setup finished.
After having the cluster configured, I started to create a Spring Boot API with 1 endpoint (list all messages). Also, was created a Dockerfile to create a docker image with the application that would be used by kubernetes.
After that, I created the YAML templates: the deployment and the service. With this, in order to automate the release of the spring boot app and all kubernetes templates, I used Helm and I configured all necessary YAMLs to automate a release of the app.
Since the main goal of the application was a Cycling Chat, I deployed with Helm a Postgresql statefulset to save all messages that were published on a RabbitMQ statefulset (that also was deployed with Helm). To test this application was created a Java Application to publish messages on RabbitMQ.

## More images of the project
<img src="{{site.baseurl}}/assets/img/project_cyclingchat/1.png" alt="Result" class="post-images">

![Main Page]({{site.baseurl}}/assets/img/project_cyclingchat/2.png)

![Main Page]({{site.baseurl}}/assets/img/project_cyclingchat/4.png)

## References
* [Github Project](https://github.com/brunocoelho1997/cycling-chat-k8)