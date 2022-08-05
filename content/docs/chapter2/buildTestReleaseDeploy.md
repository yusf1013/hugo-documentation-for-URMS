---
title: Build, test, release
linktitle: Build, test, release
toc: true
type: book
date: '2019-05-05T00:00:00+01:00'
# draft: true

# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 3
---

## CI/CD pipeline

For build, test, release, and deployment, we have automated these steps with CI/CD pipeline. CI/CD pipeline has been set for all three of our repositories - backend, frontend, and documentation. Backend and frontend uses GitHub Actions for CI/CD pipeline, and documentation has been set with netlify's pipeline. 

![img](/i3.PNG)

As soon as the code is pushed to the version control, it triggers the github actions. The github actions execute the following tasks - 
1. Checking out from version control
2. Execute build script
3. Execute test scripts
4. Docker containerize
5. Deploy

After step 4, the containers are pushed to an online container registry like DockerHub. 
During step 5, the containers are deployed to the kubernetes cluster. 

If the pipeline fails at any stage, the next actions are skipped.

Here is an example of a failed and a successful pipeline - 

![img](/i4.PNG)


![img](/i5.PNG)


