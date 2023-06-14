
[![Project Status: Under Construction](https://img.shields.io/badge/Project%20Status-Under%20Construction-yellow)](https://github.com/YavorMarkov/Efficient-EKS-Load-Balanced-Deployment/)


**NOTE**: This project is currently under construction. Please check back later for updates.



# Efficient-EKS-Load-Balanced-Deployment

The complete project involves setting up an Amazon Elastic Kubernetes Service (EKS) cluster, deploying an application, and making it accessible through an Elastic Load Balancer (ELB). The project is divided into several parts, each covering specific tasks and configurations.

## Contents:



- **Part 1: Set Up an EKS Cluster**
  - Create an EKS cluster using eksctl and configure it with the necessary parameters.
  - Verify the successful creation of the cluster using the AWS Management Console.

- **Part 2: Deploy an Application to the EKS Cluster**
  - Create and configure the necessary Kubernetes resources, such as ConfigMaps and Secrets, for the application.
  - Build and push a Docker image of the application to a container registry (Docker Hub).
  - Deploy the application to the EKS cluster using Kubernetes manifests.

- **Part 3: Deploy an Application to Your EKS Cluster**
  - Create a Kubernetes namespace and verify its creation.
  - Configure a deployment manifest for the application, specifying details like the container image, replicas, and environment variables.
  - Apply the deployment manifest and verify the successful creation of the deployment.
  - Create a service manifest to enable load balancing and expose the application externally.
  - Apply the service manifest and verify the successful creation of the service.

- **Part 4: Troubleshoot Service Account Issues**
  - Troubleshoot common issues related to the Kubernetes service account, IAM policies, and AWS Load Balancer Controller.
  - Resolve issues such as failed CloudFormation stacks, incorrect command values, and formatting errors.

- **Part 5: Install the AWS Load Balancer Controller**
  - Install Cert Manager, a Kubernetes add-on for managing TLS certificates.
  - Install the AWS Load Balancer Controller, which manages Elastic Load Balancers for the EKS cluster.
  - Configure necessary parameters in the load-balancer-controller.yaml file, such as VPC ID and AWS region.
  - Apply the load-balancer-controller.yaml file to install the AWS Load Balancer Controller.
  - Create IngressClassParams and IngressClass to enable the creation of an Elastic Load Balancer.
  - Create an Ingress for the application to direct traffic to the appropriate service and pods.
  - Verify the creation of the Elastic Load Balancer in the AWS Management Console.
  - Access the application using the provided DNS name once the load balancer is active.

- **Part 6: Clean Up**
  - Manually delete the load balancers from the AWS Console.
  - Use eksctl to delete the EKS cluster.
  - Manually check and delete any remaining resources related to VPC, EC2, CloudFormation, and EKS in the AWS Console.


By following these steps, you can successfully set up an EKS cluster, deploy an application, create an Elastic Load Balancer, and clean up the resources when they are no longer needed.

# Walkthrough
# Preraqusite

AWS CLI Installation
The AWS CLI is a unified tool to manage your AWS services from a terminal session. It brings the power of the AWS console to your terminal.

1. **Installation Steps**
Install AWS CLI using the Snap package management tool:
  ```bash
  sudo snap install aws-cli --classic

Part 1: Set Up an EKS Cluster

In this part, we will create an Amazon Elastic Kubernetes Service (EKS) cluster using the `eksctl` command-line tool.

1. **Create the EKS Cluster**

   Run the following command to create the cluster.

   
   eksctl create cluster -f cluster.yaml

2. **Define the cluster configuration**

  For this cluster, we are using a cluster.yaml file to define our cluster setup.You can find this file in the main project directory.
  
3. **Verify the creation of the EKS Cluster**

   To verify that your EKS cluster has been successfully created, you can check it in the AWS Management Console. 

   - Open the AWS Management Console in your web browser.
   - Navigate to the EKS service.
   - Your cluster "my-eks" should be listed once its creation has been successful.

That concludes Part 1 of the project. In the upcoming parts, we will go over deploying an application to the EKS cluster, setting up load balancing, and cleaning up the resources when they are no longer needed.



