+++
title = "My Amateur Experience with Kubernetes - III"
date = "2023-04-25T16:29:31+05:30"
author = "Czernobog"
authorTwitter = "" #do not include @
cover = ""
tags = ["#Kubernetes",  "#Challenges",  "#Learning",  "#Concepts",  "#MyFirstExperience",  "#Part-3of3"]
keywords = ["", ""]
description = "Part 3 or 3 - In this final blog post my kubernetes basics series, I recount my first-hand experience of working with Kubernetes, detailing the challenges I faced and the valuable lessons I learned along the way."
showFullContent = false
readingTime = false
hideComments = false
color = "" #color from the theme settings
+++


### Final Part

My recent experience with deploying an Angular application on Kubernetes was both challenging and exciting. I didn’t have the complete setup for the application and I knew it would take days to set up. So, my colleague provided me with a pre-built jar file. After that, I created a docker image of the Angular application and deployed it on Docker using a simple docker-compose.yml file to check if it worked.

Once I verified that the application was working in Docker, I created a kubernetes manifest for the Angular application with a service for it. This was a significant milestone for me as I had to go through many tutorials to understand the process. However, I faced an unexpected issue when I deployed the kubernetes manifest and checked the website with kubectl port-forward. Although the website was accessible, there was no data in it.

I spent a considerable amount of time investigating the issue and trying different solutions to resolve it, but nothing worked. I eventually realized that I might need an ingress service to fetch the details from the database. It was not an easy fix, and I had to search for creating an ingress service between the Spring Boot and Angular applications. During the process, I encountered another challenge where I could only access the website if I used the command kubectl port-forward. I wanted to access the website without using that command every time, so I had to deal with a load balancer as well.

Creating the ingress was a bit challenging, and I had to seek help from (another shout-out) Deaddy who assisted me in understanding the process. After successfully deploying the ingress, I could see all the data, and the website was now dynamic instead of static, which was a great achievement. I also deployed the load balancer, which allowed me to access the website directly using the IP Address and port.

Finally, I edited my `hosts` file and assigned a domain name to the URL, and now I had an actual website working on Kubernetes (without an SSL certificate). It was a thrilling experience to overcome the challenges and deploy the Angular application on Kubernetes, and I was happy to have achieved my goal.


### Challenges

These are some of the challenges I faced while learning Kubernetes:

**Lack of understanding of Kubernetes basics:** Directly diving in to MySQL and Springboot before learning the basics of Kubernetes. This approach may have made it difficult to understand how Kubernetes works and how it can be used to manage containers effectively.

**Copying instead of understanding:** I had difficulty with creating Kubernetes manifests and eventually copying and pasting them from a tutorial. While this approach may work initially, it may be challenging to modify or debug Kubernetes manifests without a fundamental understanding of them.

**Trial and error approach:** I used a trial and error approach to get the Angular application working in Kubernetes. While this may have been successful, it is a time-consuming and inefficient approach to problem-solving.

**Time constraints:** I had to learn Kubernetes within 30 days, which may have put pressure on me resulting in to take shortcuts or not fully understand the concepts before moving on to the next step. This may have affected the overall quality of the learning experience too.

### Conclusion

In conclusion, this experience has taught me a lot about the importance of attention to detail and taking the time to properly configure each aspect of the application.

It was also my first time working with a team and this also made me more productive in general and I had a lot of fun working on it.

While it was frustrating at times, the feeling of satisfaction when everything finally came together was worth it. I am excited to continue learning and expanding my skills in this field.
