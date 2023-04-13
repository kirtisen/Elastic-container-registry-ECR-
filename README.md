#  What is Amazon Elastic Container Registry?

**Amazon Elastic Container Registry** (Amazon ECR) is an AWS managed container image registry service that is secure, scalable, and reliable . Amazon ECR supports private repositories with resource-based permissions using AWS IAM.

# Components of Amazon ECR
Amazon ECR contains the following components:
-  **Docker images :-** This is the file that is used to execute code within a Docker container.

-  **Repository :-** The Docker images are stored in the Amazon ECR repository. 

-  **Repository policy :-** You can control access to your repositories and the images within them with repository policies.

-  **Registry :-**   AWS ECR assigns a registry to the accounts The users can create multiple repositories in the registry and then push and pull images in the repository.

-   **Authorization token :-** AWS ECR assigns authorization tokens to authentic users. So that only authentic users use the services and can push and pull the images.

## **Features of AWS ECR**
There are many advanced features that make the AWS ECR unique and useful. Some of the most prominent features include:

**Cross-region Replication** <br />
Cross-region replication allows users to access their repositories and docker images from wherever they want. This is done while registering for the AWS ECR, and it is executed on a per-region basis.

**Image Scanning** <br />
Image scanning helps in identifying software vulnerabilities in your container images. Each repository can be configured to **scan on push**. This ensures that each new image pushed to the repository is scanned. You can then retrieve the results of the image scan.

**Life Cycle Policies** <br /> 
Lifecycle policies help with managing the lifecycle of the images in your repositories. You define rules that result in the cleaning up of unused images. You can test rules before applying them to your repository.

## Task :-
[Create the Private Amazon ECR Repository](#ECR-Repository). 
- Build a **Docker Image**  of **Apache container** and configure web page, add this data ``Hello From ECS`` in web page. Then, Pull that **Docker Image** to Amazon ECR.
   - [Create a **Dockerfile**](#Create-Dockerfile)
   - [Build the **Image**](#build-the-docker-image)   
   - [Pull the **Docker Image** on ECR Repository](#push-the-image-apache2-to-elastic-container-registry)
-  Create a **Cluster** in Amazon Elastic Container Service (ECS). And in the **Task Defination** define that docker image. And run that task with that Docker Image.  
-   Finally, search the DNS in your Browser and check your web page show this =) ``Hello From ECS``
<br />
<br />
<br />

## Pre-Requisites 

-   [AWS Credentials](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_users_create.html)  with permissions to interact with ECR.
-   [Docker installation in localy for Ubuntu OS](https://docs.docker.com/engine/install/ubuntu/). 
	 Docker installing for other operating system, click [here](https://docs.docker.com/get-docker/).
-   The  [AWS CLI installed locally](https://aws.amazon.com/cli/). And configure the credentials.

#### ECR Repository
- Sign in your [Amazon console](https://aws.amazon.com/console/).
- Press key [Alt+S] and type ECR. Then click on [Elastic Container Registry](https://us-west-1.console.aws.amazon.com/ecr/home?region=us-west-1)

#### Configuring Your Repository
-  Click on ``Get started`` to create the repository. <br /> 
     <img alt="coding" width="700" src="https://github.com/kirtisen/Elastic-container-registry-ECR-/blob/main/Images/Screenshot%20from%202023-04-13%2022-32-33.png">  <br />
-  In the setting that appears click on `private` and give any name to your repository.
     <img alt="coding" width="700" src="https://github.com/kirtisen/Elastic-container-registry-ECR-/blob/main/Images/Screenshot%20from%202023-04-13%2023-21-03.png">  <br />
     
     -   Afterthat click to `create repository`.
 
-   Now private ECR repository is created .
     <img alt="coding" width="700" src="https://github.com/kirtisen/Elastic-container-registry-ECR-/blob/main/Images/Screenshot%20from%202023-04-13%2023-35-23.png">  <br />
     

# Build & Push Docker Image to AWS ECR using GitHub Actions
 <img alt="coding" width="500" src="https://miro.medium.com/v2/resize:fit:828/format:webp/1*jrdZWe4JRU5KDbWfnRxenA.png">  <br />
- In this blog post, I’ll explain to you how to build & push docker images to AWS ECR **(Elastic Container Registry)** using GitHub Actions.

# **_Getting Started_**
- Create Dockerfile 

First of all, build the application on your local environment and then create a repository in GitHub .
- Run this command to create a directory  and go in that directory. ``$ mkdir Repo && cd Repo ``
- Create a file with name **Dockerfile** and add this data. 
```
	FROM ubuntu:22.04

	RUN apt update && apt install -y apache2

	ENV APACHE_RUN_USER www-data
	ENV APACHE_RUN_GROUP www-data
	ENV APACHE_LOG_DIR /var/log/apache2
	ENV APACHE_RUN_DIR /var/www/html

	RUN echo "<font size = "20" color="green"><b><u>Hello From ECS ;)</u></b></font><br />" > /var/www/html/index.html

	ENTRYPOINT ["/usr/sbin/apache2"]
	CMD ["-D", "FOREGROUND"]
```
 <img alt="coding" width="700" src="https://github.com/kirtisen/Elastic-container-registry-ECR-/blob/main/Images/Screenshot%20from%202023-04-14%2000-03-47.png"> <br />
