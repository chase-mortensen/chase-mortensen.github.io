---
title: "FaceOverlay"
date: 2021-04-14T20:23:29-04:00
slug: "faceoverlay"
description: "FaceOverlay is an educational tool for machine learning."
keywords: ["faceoverlay", "machine learning", "ml", "data science"]
draft: false
tags: ["machine-learning", "data-science", "UX/UI"]
math: false
toc: true
---

## Intro

FaceOverlay (also known as [SmileyCluster](https://zhenbai.io/wp-content/uploads/2020/11/SmileyCluster_IDC20.pdf)) is an educational tool for machine learning under development in Dr. Zhen Bai's lab at the University of Rochester. I was able to work on the project through an NSF-funded internship over the summer of 2019. Dr. Bai and her lab were amazing to work with and I learned a lot about iterative design and experiment design through that experience. 

<br>
{{< figure src="/assets/faceoverlay/ur-library.jpg" caption="#### UR's Rush Rhees Library &uarr;" >}}

### Chernoff Faces

[Chernoff Faces](https://web.archive.org/web/20120415030406/http://www.apprendre-en-ligne.net/mathematica/3.3/chernoff.pdf) are a tool for visualizing multivariate data. Plotting data with more than two or three variables is challenging, and Chernoff Faces approaches this by connecting each variable to a facial feature - such as eye diameter, mouth shape, etc. This allows for three or more features to be assessed at a time. 

Some drawbacks to Chernoff faces are 1) that the features aren't easily measurable and 2) that some features are more salient than others.

<br>
{{< figure src="/assets/faceoverlay/chernoff-faces.png" caption="#### Traditional Chernoff Faces &uarr;" >}}

However, Chernoff faces can be a useful tool to become familiar with multivariate data since we are able to discern small differences between faces that would be more difficult to see with solely numerical data. It is also flexible in that a range of variables can be represented - facial features can be added or subtracted based on the number of variables in the data.

<br>
{{< figure src="/assets/faceoverlay/faceoverlay-faces-short.png" caption="#### FaceOverlay Variation &uarr;" >}}

## The Project

When I joined the project, Dr. Bai's lab had already come up with the FaceOverlay concept (and had some very cool transparent plastic faces which could be stacked to demonstrate the idea). The concept boils down to being able to stack these faces and easily see the differences. So, if you were comparing two faces to a third, you could easily determine which was more similar by stacking each of the faces over the third and comparing the differences.

### K-means Clustering

We set out to design a simple web interface using this FaceOverlay concept to explain the [k-means clustering algorithm](https://en.wikipedia.org/wiki/K-means_clustering#Standard_algorithm_(naive_k-means)). The idea was that the tool would be used in a K-12 setting to assist an instructor in teaching k-means clustering.

<br>
{{< figure src="/assets/faceoverlay/k-means.gif" caption="#### K-means Clustering &uarr;" >}}

### Classroom Study

We conducted an exploratory classroom study where we had an instructor walk through a lesson on k-means using FaceOverlay. We collected video, audio, and screen recordings and conducted group interviews following the lesson.

### Link to Project

This is a link to the [first iteration](https://augnitionlab.github.io/FaceOverlay_Publish/HTML/DataNarrative.html) of the project that I worked on with other members of Dr. Bai's lab. Our [paper](https://zhenbai.io/wp-content/uploads/2020/11/SmileyCluster_IDC20.pdf) was published in Interaction Design and Children (IDC) 2020. The findings in the paper are promising - participants improved on all six questions in our pre/post evaluation. If you are interested, I would suggest checking out the paper for more specific findings and details.

What do you think? Let me know at chase@chase-mortensen.dev.

Chase


<!-- {{< youtube ZJthWmvUzzc >}} -->



<!-- {{< tweet 1085870671291310081 >}} -->
