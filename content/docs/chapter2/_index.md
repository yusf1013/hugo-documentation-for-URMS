---
# Title, summary, and page position.
linktitle: DevOps Life Cycle
summary: How the solution was implemented step by step
weight: 2
icon: book-reader
icon_pack: fas

# Page metadata.
title: DevOps Life Cycle
date: '2018-09-09T00:00:00Z'
type: book # Do not modify.
---

## Introduction
The devops approach involves 8 steps that are iteratively applied uring the software development lifecycle. The steps are - 
1. Requirement Analysis (Planning)
2. Code
3. Build
4. Test
5. Release
6. Deploy
7. Operate
8. Monitor

We have addressed all 8 of these phases in our project. 

## What our app attempts to solve - 
Our solution attempts to solve the following problems identified or mentioned by the given scenario - 
1. Inconsistent load on server - We have used Kubernetes for scaling. During high load, we can spin up more replicas in the cluster to handle the load. If that is not enough, then the number of nodes can be automatically scaled in our out to fit the required amount of pods. 
2. Website may need frequent updates - 
    First we setup three CI/CD pipelines for backend, frontend, and documentations respectively. This way the changes will automatically be built, tested, and deployed when developers push code to VCS. 
3. It may be tedious to keep updating documentation - We have setup a CI/CD pipeline for documentation so that we can keep updating the documents as we go without having to worry about reformatting and reuploading them every time. 
4. The problem of having to run every single tests again after making a small change - CI/CD solves this too.
5. The deployment may face problems sometimes - Constant monitoring with prometheus and Grafana can help prevent errors before they arise. In case an error arises, the admins can be immediately notified using Grafana and Slack. 
6. The possibility of having to replicate the production server -  Using Terraform allows us to replicate the environment with little to no manual work. 
7. Requiring updates without downtime - with kubernetes deployment strategies like blue/green deployment, rollout deployment, canary deployment, etc. 

## Tools and technology
1. MongoDB
2. Express.js
3. Angular
4. Node.js
5. Terraform
6. Kubernetes, Azure Kubernetes Service (AKS)
7. Kubectl
8. Microsoft Azure 
9. GitHub
10. Github actions
11. Hugo (For documentations)
12. Prometheus
13. Grafana
14. PromQL
15. Slack (For receiving alerts)
16. Docker