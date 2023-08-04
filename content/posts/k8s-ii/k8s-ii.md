+++
title = "My Amateur Experience with Kubernetes - II"
date = "2023-04-04T16:29:29+05:30"
author = "Czernobog"
authorTwitter = "" #do not include @
cover = ""
tags = ["#Kubernetes",  "#Challenges",  "#Learning",  "#Concepts",  "#MyFirstExperience",  "#Part-2of3"]
keywords = ["", ""]
description = " Part 2 or 3 - In this three-part blog post series, I recount my first-hand experience of working with Kubernetes, detailing the challenges I faced and the valuable lessons I learned along the way. In Part 1, I describe the initial setup process and share insights on creating a Docker image and deploying it on Kubernetes."
showFullContent = false
readingTime = false
hideComments = false
color = "" #color from the theme settings
+++

### Recap

I am continuing to share my amateur experience learning Kubernetes for work. So far I have discussed my journey with Kubernetes, including how I got started with Minikube, learned MySQL and Springboot, created a Docker image, and created a Kubernetes manifest. I will also talk about adding an Angular application to my Kubernetes setup and how I have learned new concepts along the way.

**Starting the Project and Setting up the Database:** So, I finally got to the real deployment this time. I was given the task to build a docker image and deploy it. It was quite exciting to get hands-on experience with something practical like this. The good thing was that I didn’t have to worry too much about messing up because it was all being done locally on my laptop using minikube. However, I was on a tight deadline and had to work quickly.

To start off, I created a mysql manifest. I didn’t bother with creating secrets or anything like that. I simply used the variables like root password, db_HOST, and all that in the manifest as one does in docker-compose.yml. I know that’s not the right way to do it, but I was feeling the pressure and had to get things done by the end of the day. It turns out that I needed an exact copy of the database for the spring application to work. I had to use the kubectl port-forward command and install DBeaver to access it. With the help of my colleague, we set up the database, which frankly was kind of annoying. Why would anyone require a database as a dependency?

**Building the Spring Boot Application and Docker Image:** After that, one of my colleagues provided me with a pre-built jar file of the Spring Boot application. I used the same Dockerfile that I had used in PART I for building the spring boot application. I used the split window feature in VSCode and used the tutorial spring boot manifest as a template. I followed it thoroughly, but soon I realized that there was an issue. The spring boot application required a custom URL. After searching online for a bit, I added a variable as an argument in the Dockerfile, re-created the docker image, and pushed it to Docker Hub. This way, I could add the spring datasource details and change them as required.

**Deploying the Spring Boot Manifest and Troubleshooting:** Deploying a Spring boot manifest was really annoying. Typing the manifest was not that bad, but there was a minor issue where although the Springboot application was deployed, it kept crashing for some reason. I checked the logs, and I kept getting the error message “communication link failure”. This basically meant that Springboot application was not able to access the database on MySQL. I spent two days straight with one of my colleagues who has worked on the application to figure out the issue. (She is a java developer and barely knows how Kubernetes worked) but I must say, she also spent some time with me to understand the fundamentals of Kubernetes and she is very smart (just wanted to give her a shoutout.). Anyways, we finally found the issue in the JDBC URL, which was missing the “&allowpublickeyretrieval” string at the end. As soon as I added this to the MySQL database in Kubernetes and tried again, it worked. It was very frustrating, but the satisfaction that we got when it finally worked made me feel kind of invincible, and being the noob I am, I wanted more of it.

Stay tuned for part - III
