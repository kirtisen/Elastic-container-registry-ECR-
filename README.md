# Elastic-container-registry-ECR-

What is Amazon Elastic Container Registry?
Amazon Elastic Container Registry (Amazon ECR) is an AWS managed container image registry service that is secure, scalable, and reliable . Amazon ECR supports private repositories with resource-based permissions using AWS IAM.

Components of Amazon ECR
Amazon ECR contains the following components:

Docker images :- This is the file that is used to execute code within a Docker container.

Repository :- The Docker images are stored in the Amazon ECR repository.

Repository policy :- You can control access to your repositories and the images within them with repository policies.

Registry :- AWS ECR assigns a registry to the accounts The users can create multiple repositories in the registry and then push and pull images in the repository.

Authorization token :- AWS ECR assigns authorization tokens to authentic users. So that only authentic users use the services and can push and pull the images.

Features of AWS ECR
There are many advanced features that make the AWS ECR unique and useful. Some of the most prominent features include:

Cross-region Replication
Cross-region replication allows users to access their repositories and docker images from wherever they want. This is done while registering for the AWS ECR, and it is executed on a per-region basis.

Image Scanning
Image scanning helps in identifying software vulnerabilities in your container images. Each repository can be configured to scan on push. This ensures that each new image pushed to the repository is scanned. You can then retrieve the results of the image scan.

Life Cycle Policies
Lifecycle policies help with managing the lifecycle of the images in your repositories. You define rules that result in the cleaning up of unused images. You can test rules before applying them to your repository.

