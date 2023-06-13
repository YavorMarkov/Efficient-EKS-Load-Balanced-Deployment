
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
## Part 1: Set Up an EKS Cluster

In this part, we will create an Amazon Elastic Kubernetes Service (EKS) cluster using the `eksctl` command-line tool.

1. **Create the EKS Cluster**

   Run the following command to create the cluster. Make sure to replace `<cluster-name>` with your desired cluster name and `<node-type>` with the type of node you want to use:

   ```bash
   eksctl create cluster -f cluster.yaml



