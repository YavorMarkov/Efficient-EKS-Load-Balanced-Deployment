
[![Project Status: Under Construction](https://img.shields.io/badge/Project%20Status-Under%20Construction-yellow)](https://github.com/YavorMarkov/Efficient-EKS-Load-Balanced-Deployment/)


<i><sub>**NOTE**: This project is currently under construction. Please check back later for updates.</i></sub>

 

# Efficient-EKS-Load-Balanced-Deployment

The complete project involves setting up an Amazon Elastic Kubernetes Service (EKS) cluster, deploying an application, and making it accessible through an Elastic Load Balancer (ELB). The project is divided into several parts, each covering specific tasks and configurations.

## Contents:

**Prerequsite:** We're going to install three tools on Ubuntu Linux: the AWS CLI for interacting with Amazon Web Services, kubectl for managing Kubernetes clusters, and eksctl for creating and controlling Amazon EKS clusters. After installation, we'll confirm that each tool has been successfully installed and is ready to use.

- **Part 1: Set Up an EKS Cluster**
  - Create an EKS cluster using eksctl and configure it with the necessary parameters.
  - Verify the successful creation of the cluster using the AWS Management Console.
    
- **Part 2: Deploy an Application to Your EKS Cluster**
  - Build and push a Docker image of the application to a container registry (Docker Hub)*.
  - Create a Kubernetes namespace and verify its creation.
  - Configure a deployment manifest for the application, specifying details like the container image, replicas, and environment variables.
  - Apply the deployment manifest and verify the successful creation of the deployment.
  - Create a service manifest to enable load balancing and expose the application externally.
  - Apply the service manifest and verify the successful creation of the service.

- **Part 3: Troubleshoot Service Account Issues**
  - Troubleshoot common issues related to the Kubernetes service account, IAM policies, and AWS Load Balancer Controller.
  - Resolve issues such as failed CloudFormation stacks, incorrect command values, and formatting errors.

- **Part 4: Install the AWS Load Balancer Controller**
  - Install Cert Manager, a Kubernetes add-on for managing TLS certificates.
  - Install the AWS Load Balancer Controller, which manages Elastic Load Balancers for the EKS cluster.
  - Configure necessary parameters in the load-balancer-controller.yaml file, such as VPC ID and AWS region.
  - Apply the load-balancer-controller.yaml file to install the AWS Load Balancer Controller.
  - Create IngressClassParams and IngressClass to enable the creation of an Elastic Load Balancer.
  - Create an Ingress for the application to direct traffic to the appropriate service and pods.
  - Verify the creation of the Elastic Load Balancer in the AWS Management Console.
  - Access the application using the provided DNS name once the load balancer is active.

- **Part 5: Clean Up**
  - Manually delete the load balancers from the AWS Console.
  - Use eksctl to delete the EKS cluster.
  - Manually check and delete any remaining resources related to VPC, EC2, CloudFormation, and EKS in the AWS Console.


By following these steps, you can successfully set up an EKS cluster, deploy an application, create an Elastic Load Balancer, and clean up the resources when they are no longer needed.

# Walkthrough
# Preraqusite

**Step 1: Install AWS CLI on Linux**

The AWS CLI tool gives you a way to interact with AWS services from your command line rather than the AWS console interface. Let's install it on Linux.

1.**Open your terminal.**

2.**If you are uncertain about your Linux distribution, you can find it by running:**
```bash
lsb_release -a
```
3. Go to the AWS documentation page that describes how to install the AWS CLI. Look for the installation instructions for Linux.
4. You can install AWS CLI using the curl command, but you need to know your CPU type (X86 or ARM). Run the following command to find out:
```bash
uname -m
```
5. In this tutorial, we'll use Snap, a package manager for Linux, to install the AWS CLI. Run:
```bash
sudo snap install aws-cli --classic
```
6. Once the installation is complete, test if it worked by running:
```bash
aws help
```
**Step 2: Install kubectl on Linux**

kubectl is a command-line tool that allows you to interact with Kubernetes clusters. Let's install it on Linux.

1.Go to the "Install and Set Up kubectl on Linux" page in the official Kubernetes documentation.

2.There are several ways to install kubectl on Linux, but to maintain consistency, we'll use Snap. You can find the snap instructions under the "Other Package Management" section. Run:

```bash
sudo snap install kubectl --classic
```
3. After installation, check if it's installed correctly by running:
```bash
kubectl
```
If you see a list of commands, that means kubectl is installed.

***Step 3: Install eksctl on Linux***

eksctl is a command-line tool that allows you to create and manage AWS EKS clusters.

1.Go to the "Installing or updating eksctl" page in the official AWS documentation.

2. Click on the tab for Linux. Note that there's no snap package for eksctl, so we'll use curl to download the executable. Run:

```bash
curl --silent --location "https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_$(uname -s)_amd64.tar.gz" | tar xz -C /tmp
```

3.Move the executable to your /usr/local/bin directory:

```bash
sudo mv /tmp/eksctl /usr/local/bin
```
4.Verify the installation by running:

```bash
eksctl
```
If you see a list of commands, that means eksctl is properly installed.

Now, you have successfully installed AWS CLI, kubectl, and eksctl on your Ubuntu Linux system. Great work!
[Empty space line]
Once you have fulfilled the prerequisites mentioned above, you can proceed with the following steps to get started:


**Part 1: Set Up an EKS Cluster**

In this part, we will create an Amazon Elastic Kubernetes Service (EKS) cluster using the `eksctl` command-line tool.

1. **Create the EKS Cluster**

   Run the following command to create the cluster.

   ```bash
   eksctl create cluster -f cluster.yaml
   ```
2. **Define the cluster configuration**

  For this cluster, we are using a cluster.yaml file to define our cluster setup.You can find this file in the main project directory.
  The process of forming a cluster might take some time, potentially up to half an hour. Once it's done, a notification similar to this will appear.
  
  ![](https://github.com/YavorMarkov/Efficient-EKS-Load-Balanced-Deployment/blob/main/images/Created_cluster_1.JPG)
  ![](https://github.com/YavorMarkov/Efficient-EKS-Load-Balanced-Deployment/blob/main/images/Created_cluster_2.jpg)

  
3. **Verify the creation of the EKS Cluster**

   To verify that your EKS cluster has been successfully created, you can check it in the AWS Management Console.
   
   - Open the AWS Management Console in your web browser.
   - Navigate to the EKS service.
   - Your cluster "my-eks" should be listed once its creation has been successful. We have successfully created the EKS cluster "my-eks", as confirmed by the AWS Management Console, as shown in the screenshot below.

  ![](https://github.com/YavorMarkov/Efficient-EKS-Load-Balanced-Deployment/blob/main/images/Created_Cluster_3.JPG)

That concludes Part 1 of the project. In the upcoming parts, we will go over deploying an application to the EKS cluster, setting up load balancing, and cleaning up the resources when they are no longer needed.

**Part 2:** ***Coming Soon***







*<sub><i>We leveraged a pre-built and uploaded Docker image in this project.</i></sub>



