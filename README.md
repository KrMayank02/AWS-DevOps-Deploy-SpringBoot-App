# AWS DevOps - CI/CD Pipeline for Spring Boot Application Deployment

**Objective:** To implement a CI/CD pipeline using AWS services for automating the deployment of a Spring Boot Application on Amazon ECS with Docker, integrating CodePipeline, CodeBuild and ECR for seamless updates.

**Real-time scenario:** Imagine a retail company that has a Spring Boot-based inventory management system. The system is used by several departments and is hosted in containers to ensure scalability. 
The company wants to reduce the manual intervention required to deploy updates by automating the build and deployment process. By setting up a CI/CD pipeline, developers can push updates to a GitHub repository, automatically triggering a sequence of actions that build, containerize, and deploy the application without downtime. This ensures faster and more reliable system updates, minimizing operational delays.

**Major Tools, AWS Services, Environment Used in this Project:**

- AWS CodePipeline
- AWS CodeBuild
- AWS ECR
- AWS ECS
- Docker
- IAM


**High Level Project Diagram:**

<img width="958" height="497" alt="image" src="https://github.com/user-attachments/assets/525d106c-5d79-4ec6-88c5-6eb217f2ecd3" />
-----------------------------------------------------------------------------------------------------------------------

**High Level Tasks/Steps:**

-	Fork the Springboot app project GitHub repository.
-	Create Amazon ECR Public Repository.
-	Check and update the buildspec.yml and Dockerfile in GitHub Repo.
-	Create AWS CodeBuild project to build the source code and push the image to AWS ECR repository.
-	Create AWS ECS cluster with Fargate (launch type), Task Definition and Service to deploy & run containerized application.
-	Create & configure AWS CodePipeline to trigger on GitHub changes, integrating CodeBuild and ECS for automated deployment.
-	Check and monitor the CI/CD pipeline execution in AWS CodePipeline for GitHub repo changes.
