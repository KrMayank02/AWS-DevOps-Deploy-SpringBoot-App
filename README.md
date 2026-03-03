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

------------------------------------------------------------------------------------------------------------------------------

**High Level Project Diagram:**

<img width="958" height="497" alt="image" src="https://github.com/user-attachments/assets/525d106c-5d79-4ec6-88c5-6eb217f2ecd3" />

------------------------------------------------------------------------------------------------------------------------------

**High Level Tasks/Steps:**

-	Fork the Springboot app project GitHub repository.
-	Create Amazon ECR Public Repository.
-	Check and update the buildspec.yml and Dockerfile in GitHub Repo.
-	Create AWS CodeBuild project to build the source code and push the image to AWS ECR repository.
-	Create AWS ECS cluster with Fargate (launch type), Task Definition and Service to deploy & run containerized application.
-	Create & configure AWS CodePipeline to trigger on GitHub changes, integrating CodeBuild and ECS for automated deployment.
-	Check and monitor the CI/CD pipeline execution in AWS CodePipeline for GitHub repo changes.

Output Results Screenshots:
-------------------------------------------------------------------------------------------------------------------------------

Amazon ECR Public Repository with name “springboot”.

<img width="911" height="442" alt="image" src="https://github.com/user-attachments/assets/954ce97f-13db-4a59-8ff0-401391f02e8e" />

-------------------------------------------------------------------------------------------------------------------------------

modify the buildspec.yml under github repo: 

<img width="946" height="429" alt="image" src="https://github.com/user-attachments/assets/a2e7aae6-3613-42d4-ba6b-3d28a06248b3" />

---------------------------------------------------------------------------------------------------------------------------------

<img width="953" height="496" alt="image" src="https://github.com/user-attachments/assets/0eb9a99f-df76-4469-b113-ad2e88ef1752" />

----------------------------------------------------------------------------------------------------------------------------------

<img width="913" height="473" alt="image" src="https://github.com/user-attachments/assets/a65aebba-bfad-4f4a-ba0c-f45355c02147" />

-----------------------------------------------------------------------------------------------------------------------------------

The build logs displayed that the Build completed, Image created and pushed to ECR.

<img width="827" height="373" alt="image" src="https://github.com/user-attachments/assets/fb52f4d9-f27b-4a3b-a953-a9cdec11d80b" />

------------------------------------------------------------------------------------------------------------------------------------

Tail Logs Screesnhot:

<img width="928" height="633" alt="image" src="https://github.com/user-attachments/assets/6de6cb08-8ba0-49ee-b5b3-fd64a751e374" />
------------------------------------------------------------------------------------------------------------------
Image pushed to ECR Repository, screenshot:

<img width="959" height="294" alt="image" src="https://github.com/user-attachments/assets/a3439810-317b-44c4-81fd-cbbf0f98de8d" />

--------------------------------------------------------------------------------------------------------------------------------------

The Services “springboot-task-service-ya4jo0qk” has been created & deployed successfully in Amazon ECS:

<img width="942" height="344" alt="image" src="https://github.com/user-attachments/assets/0df5517f-8963-4ddc-bf37-24dcf9f86a40" />

--------------------------------------------------------------------------------------------------------------------------------------

CodePipeline got created.

The Execution of all the Stages of CodePipeline was done successfully.

<img width="935" height="404" alt="image" src="https://github.com/user-attachments/assets/66b1716c-7f30-470d-a1dd-d4a354dc6222" />

---------------------------------------------------------------------------------------------------------------------------------------

The CodePipeline – Build stage pushed the image to ECR successfully.

<img width="933" height="364" alt="image" src="https://github.com/user-attachments/assets/7b75b1b0-abc3-4e00-9d3b-402dc9c08a94" />

---------------------------------------------------------------------------------------------------------------------------------------

The CodePipeline – Deploy stage deployed the latest app image into the ECS under Services >> Task definitions.

<img width="908" height="439" alt="image" src="https://github.com/user-attachments/assets/57ff6428-2049-46ad-a65f-95f6877584c6" />
------------------------------------------------------------------------------------------------------

<img width="944" height="293" alt="image" src="https://github.com/user-attachments/assets/355db01e-8565-4aec-b00d-77a34fe1e273" />

------------------------------------------------------------------------------------------------------------------------------------------

copy the Public IP of deployed Application and access it on browser with below URL: http://44.202.24.165:8080/demo/data

<img width="949" height="340" alt="image" src="https://github.com/user-attachments/assets/107e4c20-20a0-4f4d-ba8f-a51c74f6e580" />
------------------------------------------------------------------------------------------------------------------

<img width="683" height="260" alt="image" src="https://github.com/user-attachments/assets/84b240af-b482-47fe-b01b-17be1f34fa9c" />


------------------------------------------------------------------------------------------------------------------------------------------

do some code changes in the Application GitHub Repository and then will check that due to Repository code changes if the AWS CodePipeline gets triggered:

<img width="795" height="576" alt="image" src="https://github.com/user-attachments/assets/6d9840e7-38c1-46b3-802e-08c537b8e349" />
---------------------------------------------------------------------------------------------------------

<img width="718" height="568" alt="image" src="https://github.com/user-attachments/assets/60c61828-dbcf-446b-8964-c422553f4baf" />

-------------------------------------------------------------------------------------------------------------------------------------------

Just after the code changes done in Github repo, the AWS CodePipeline execution started automatically.

<img width="935" height="386" alt="image" src="https://github.com/user-attachments/assets/f088a582-17ab-4693-8695-7a16fd747be4" />

----------------------------------------------------------------------------------------------------------------------------------------------

<img width="921" height="442" alt="image" src="https://github.com/user-attachments/assets/dee3ed5c-96ad-407d-af06-9e574081fcf5" />

-----------------------------------------------------------------------------------------------------------------------------------------------

<img width="960" height="410" alt="image" src="https://github.com/user-attachments/assets/d830b9a6-f7b2-4aa0-af24-18814cc00e12" />
---------------------------------------------------------------------------------------------------------------------------------

<img width="956" height="343" alt="image" src="https://github.com/user-attachments/assets/edc94427-72ac-4fc9-bbd7-31e93700f698" />

--------------------------------------------------------------------------------------------------------------------------------------------

Now copy the Public IP of latest deployed Application and access it on browser with below URL:

http://44.197.191.99:8080/demo/message


<img width="943" height="343" alt="image" src="https://github.com/user-attachments/assets/e5d31738-ed96-4129-83e9-1a0702106d7c" />

---------------------------------------------------------------------------------------------------------------------------------------------

**Hence, the AWS CodePipeline is correctly created & configured to automate the Build trigger and Deployment of the Application after any changes in GitHub repo.**
**So, finally the Project is complete and the Objective has been met.**

