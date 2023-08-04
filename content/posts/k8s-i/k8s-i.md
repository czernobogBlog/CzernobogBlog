+++
title = "My Amateur Experience with Kubernetes - I"
date = "2023-04-02T16:29:26+05:30"
author = "Czernobog"
authorTwitter = "" #do not include @
cover = ""
tags = ["#Kubernetes",  "#Challenges",  "#Learning",  "#Concepts",  "#MyFirstExperience",  "#Part-1of3"]
description = "In this three-part blog post series, I recount my first-hand experience of working with Kubernetes, detailing the challenges I faced and the valuable lessons I learned along the way. In Part 1, I describe the initial setup process and share insights on creating a Docker image and deploying it on Kubernetes. "
showFullContent = false
readingTime = false
hideComments = false
color = "" #color from the theme settings
+++

### Introduction

Recently, I had to work on a project that required me to learn Kubernetes within 30 days. This was not the typical way to learn Kubernetes, as I had to learn it on my own, due to work-related requirements. In this article, I will share my experience and the journey that I took to learn Kubernetes.

![K8S](/posts/k8s-i/k8s.png)

**Getting Started with Minikube:** My first Kubernetes installation was done using a VM instance. I had Virt-Manager on my system, as I was preparing for RHCSA. I started Minikube by running the command `minikube dashboard` instead of minikube start which was not technically correct, but it worked for me. I watched it run with all those emojis and stuff, which was both exciting and kind of dorky.

**Learning MySQL and Springboot:** Instead of starting with the basics of Kubernetes, I dived right in and started with MySQL and Springboot. I looked up some basic how-to guides on deploying MySQL and Springboot in Kubernetes, which recommended using the Spring Initializr to create a Springboot application. All I had to do was click on generate.

**Creating a Docker Image:** To create a custom Docker image, I used Docker. There is already an OpenJDK image available on Docker Hub, so I made sure I had the right JDK version (in my case, JDK 8), and I chose a lightweight image based on Alpine Linux. I wrote a Dockerfile that pulled the base image of JDK8-Alpine, copied my Springboot application into the image, and exposed the necessary ports. I created a Docker image with the command `docker build -t <dockerhub-username>/custom-image` and I had the Docker image ready with me. To test it out, I created a simple docker-compose.yml file and ran the command “docker-compose up -d,” which launched it in detached mode. I checked the webpage by going to `http://localhost:<port>` and checked if it’s working or not.

**Creating a Kubernetes Manifest:** I followed the rest of the guide by creating a Kubernetes manifest. I thought that typing the whole manifest instead of copy/pasting might give me some insight into how to type a manifest, but it didn’t work out as planned. I kept getting errors due to missing indentation or white space that I might have added by mistake. Typing the manifest with so many indentations felt like a nightmare. Eventually, I just deleted what I typed and replaced it by copying and pasting it from the tutorial I was following. And it worked!

**Adding Angular Application:** Now that I had the Springboot in Kubernetes, I decided to do the same with Angular application. I went to search for a tutorial with Angular Springboot in Kubernetes and followed it. Since everything was already there in the tutorial, it was fairly easy but took a bit of trial and error to get the Angular application working.

**Learning New Concepts:** There were some concepts that I didn’t know yet, like what services are, or what NodePort or ClusterIP are, but I didn’t care for now. I blindly followed the tutorial and got the Angular application working as well. I then tried again with a different tutorial, and it was during this time that I got a bit of a hang of it and started to understand what I was doing.

