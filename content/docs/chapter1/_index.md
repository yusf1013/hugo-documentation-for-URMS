---
# Title, summary, and page position.
linktitle: Introduction
summary: Learn how to use Wowchemy's docs layout for publishing online courses, software documentation, and tutorials.
weight: 1
icon: book
icon_pack: fas

# Page metadata.
title: Introduction
type: book # Do not modify.
---

## University Result Management System

This is a result management software for university that manages academic information. It is used for student registration, course registration, course addition, result publication, personal information handling etc.  

The way this works is that the admin can add courses in the system. He can also enter student details. Next, the students can request to enroll in courses out of the ones added by the admin. Afterwards, the admin can approve the request to finalize the enrollment. At the end of the courses, the admin would want to add results to the system, which the students can access. 

During course enrollment and result publication, the website may face high traffic, so it must be able to take the load. And the admins should be notified in case the students face any problems. 

## Features
1. Student registration
2. Course addition
3. Course registration
4. Result publication

## DevOps features
1. Provisioned infrastructure using Terraform (Infrastructure as a code)
2. Running the backend and frontend on a cloud Kubernetes cluster
3. Created 3 CI/CD pipelines, one for backend, one for frontend, and one for documentation. 
4. Monitoring the Kubernetes cluster with Prometheus and Grafana.
5. Setting up Grafana alerts on critical metrics to automatically notify on slack.
6. Rolling out updates without downtime. 

[The website is accessible here](http://52.234.178.79/)