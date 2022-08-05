---
title: Requirement Analysis
linktitle: Requirement Analysis
type: book
date: '2022-08-05T00:00:00+01:00'

# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 1
---

## Planning

Any project is bound to fail without proper planning. For this project, we have also planned the flow of the entire project. We started with requirement analysis  including user story, quality function deployment, and database modelling. 

## Requirement analysis
### User story
1. Student registration - The admin enters student information - ID, name, gender, and year. The system stores the information for a new student entry. 
2. Course addition - The admin enters the course id, course name and course description. The system stores the information for a new entry for course. 
3. Course registration - The student enters his id and the ID of the course he wishes to take. The information is stored in the system in a pending state. 
4. Course registration approval - The admin checks all pending requests for course registration. He can approve or decline a pending request, which the system will record. 
5. Result addition - The admin can add result for each student for the courses that he has enrolled in. 
6. Result publication - The admin can choose the publish the result. The students can enter their ID to access all their grades. 

### Quality Function Deployment (QFD)
#### Normal requirements
1. Student registration
2. Course addition
3. Course registration
4. Course registration approval
5. Result addition
6. Result publication
#### Expected requirements
1. Scalability
2. Automating server provisioning, build, test, and deploy
3. Monitoring and alerting
#### Exciting features
1. Updates without downtime
2. Separate, publicly accessible website for documentation
3. Automation pipeline for documentation

#### Database design
