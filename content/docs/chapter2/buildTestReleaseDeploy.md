---
title: Build, test, release, deploy
linktitle: Build, test, release, deploy
toc: true
type: book
date: '2019-05-05T00:00:00+01:00'
# draft: true

# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 3
---

For build, test, release, and deployment, we have automated these steps with CI/CD pipeline with GitHub actions. CI/CD pipeline has been set for all three of our repositories - backend, frontend, and documentation. 

![img](/i3.PNG)

As soon as the code is pushed to the version control, it triggers the github actions. The github actions execute the following tasks - 
1. Checking out from version control
2. Execute build script
3. Execute test scripts
4. Docker containerize
5. Deploy

If the pipeline fails at any stage, the next actions are skipped. If needed, it might rollback any permanent changes too. 

Here is an example of a failed and a successful pipeline - 
