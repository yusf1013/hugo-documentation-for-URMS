---
title: Monitoring
linktitle: Monitoring
type: book
date: '2022-08-05T00:00:00+01:00'

# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 5
---

When there are many containers, one container may crash. This can cause other containers that depend on its service to fail. This can cause a chain of failures which can result in reduced capacity to handle requests. In the worst case, the entire service may become unavailable. When such problems arise, it can become very time consuming to trace the problem from the intricate architecture of tens of servers and hundreds of containers. This can cause unwanted downtime.

The solution is to prevent the problem before it occurs by constantly monitoring the system and to have automated alerts for probable failures. But this is no easy task since the biggest challenge is knowing which metrics to monitor and what implications they can have. Besides experience, it requires a good understanding of the system architecture and an in-depth understanding of the related tools. Like any responsible DevOps team, our DevOps team has been continuously working on monitoring the system. As a part of the team, I was tasked with creating a dashboard that would give better observability into the system.

Since there are literally thousands of available metrics to monitor, it is certainly not possible to have all of them in one place. Hence I intended to make a dashboard in Grafana that would serve as a wayfinder for the monitoring team. It will highlight information about the major elements of the architecture which will tell the team exactly what and where to look for details to prevent or solve a problem. It should serve as the first step in diagnosing the system, which will tell us which steps to take next. I created 4 dashboards. The dashboard portrays different metrics on the Kubernetes cluster. The visualization starts from a very high level overview, giving major but general information about the cluster. It then slowly works its way to more details and specifics of each component. The highest level of visualization is of the entire cluster, showing which nodes make up the cluster and what the resource utilization is for each node. The next section in the dashboard shows details about a specific node including their status, and if they are under any pressure like memory pressure or CPU pressure, etc. The next level is about the deployments in each node and the number of replicas of each deployment, their status, etc. Each deployment is made up of pods and each pod has containers. Hence the next sections are dedicated to statistics on pods and containers. 

Automated alerts can be set based on these metrics. We will be alerted by slack channel.