---
title: Provisioning a server
linktitle: Provisioning a server
type: book
date: '2022-08-05T00:00:00+01:00'

# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 1
---

## The problem with the manual way

As a web app, it is obvious that it should be hosted on a server. The way that is generally done is by manually logging in to a cloud service provider's dashboard and to follow through the interface to provision a server. This approach is known as clickOps, as the operations are done by clicking through an interface. Many people think that there is nothing wrong with this common approach, since they expect to provision a server only once for a project. But it is a common misconception. 

1. ClickOps is boring and tedious - it often requires hundreds of clicks and routine activities to provision a server.
2. ClickOps is error prone - it is very easy to miss one or more of the routine tasks required to provision a server.
3. ClickOps has no scope for reuse - what if we need to replicate the production environment to create a test or staging environment?
    With ClickOps, we have to follow all steps again, which is error prone!

## What we are doing better with Terraform

We definitely have provisioned a server for the application. But instead of doing it manually, we have used Terraform. Terraform is an Infrastructure as a code tool (IaaC). This allows us to write some code that will automatically provision the server for us. This gives us full control over the type or amount of provisioned resources like CPU, RAM, storage, OS, etc. And it offers a number of advantages over the manual method (clickOps) - 
1. ClickOps is much more reliable and error free - once the code has been tested, it is guaranteed to always behave the same way without any errors. 
2. Easier to understand - It is much easier to understand the entire infrastructure by looking at well-defined and structured code, rather than having to browse through tens of dashboards and web pages like in clickOps. 
3. Reusable - No problem if the environment is to be replicated for testing / staging environment or for another project. The code can be used to easily provision the resources as many times as necessary with very little to no manual effort. 
4. Possible to version control - Since the infrastructure can be represented as code, it can be versioned. It allows the chance to rollback in case of errors. It also gives increased accountability. 

## How we are using Terraform
Use have used terraform to automate the 6 steps shown in the diagram below. Out of these, the 4th step, choose VM specification has more manual steps that we automated. Here we also specified the specifications of the provisioned VM. 

![img](/i1.PNG)

The end result is a provisioned Azure Kubernetes cluster ready to start serving!