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

Initially, I researched how to create a cluster and easily found some content to help me. After a few 
hours, I had my cluster fully installed. After configuring the cluster, I started creating a Spring Boot API with one endpoint (list all messages).<br>
I also created a Dockerfile to create a docker image. The last will have the application that is going
to be used by Kubernetes. After that, I created the YAML templates: the deployment and the service.
<br>Additionally, I used Helm to automate the release of the spring boot app and all Kubernetes templates.
Then I configured all necessary YAMLs to automate the release of the app. The main goal of the application is a Cycling Chat. 
So, I deployed a Postgresql statefulset with Helm. This way, it can save all published messages from another RabbitMQ statefulset (also deployed with Helm). Lastly, I created a Java Application to publish messages on RabbitMQ.

## More images of the project
<img src="{{site.baseurl}}/assets/img/project_cyclingchat/1.png" alt="Result" class="post-images">

![Main Page]({{site.baseurl}}/assets/img/project_cyclingchat/2.png)

![Main Page]({{site.baseurl}}/assets/img/project_cyclingchat/4.png)

## References
* [Github Project](https://github.com/brunocoelho1997/cycling-chat-k8)