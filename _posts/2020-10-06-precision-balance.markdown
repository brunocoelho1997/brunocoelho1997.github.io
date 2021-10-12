---
layout: post
title: Precision Balance
date: 2020-10-08 13:32:20 +0300
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: project_precisionbalance/1.jpeg # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [Holidays, Hawaii]
---
I was requested by a friend to develop the firmware of a balance and an Android app. This balance will be used to know the weight of each dogs leg and create wheels dog chairs for dogs that need some help to walk.

## Description
For this project was supplied an Arduino board and 16 cells/sensors (HX711). As is shown in the next pictures, on this project the user is able to:
* Connect the app to the balance;
* See the weight of each leg (average of 4 cells);
* Tare the actual values;
* Export values, that is, share the actual values with a C# application (already developed by my friend) and this app will create a PDF.

<img src="{{site.baseurl}}/assets/img/project_precisionbalance/1.jpeg" alt="Result" class="post-images">

![Main Page]({{site.baseurl}}/assets/img/project_precisionbalance/2.jpeg)

## References
* [Github Project](https://github.com/brunocoelho1997/PrecisionBalanceMW)
