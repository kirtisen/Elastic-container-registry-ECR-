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
[Create the Private Amazon ECR Repository](#creating-an-ecr-repository). 
- Build a **Docker Image**  of **Apache container** and configure web page, add this data ``Hello From ECS`` in web page. Then, Pull that **Docker Image** to Amazon ECR.
   - [Create a **Dockerfile**](#create-an-dockerfile)
   - [Build the **Image**](#build-the-docker-image)   
   - [Pull the **Docker Image** on ECR Repository](#push-the-image-apache2-to-elastic-container-registry)
-  Create a **Cluster** in Amazon Elastic Container Service (ECS). And in the **Task Defination** define that docker image. And run that task with that Docker Image.  
-   Finally, search the DNS in your Browser and check your web page show this =) ``Hello From ECS``
<br />
<br />
<br />

## key point  that you must have 

-   [AWS Credentials](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_users_create.html)  with permissions to interact with ECR.
-   [Docker installation in localy for Ubuntu OS](https://docs.docker.com/engine/install/ubuntu/). 
	 Docker installing for other operating system, click [here](https://docs.docker.com/get-docker/).
-   The  [AWS CLI installed locally](https://aws.amazon.com/cli/). And configure the credentials.
