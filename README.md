# SAP Data Hub installation Steps on AWS
Example installation steps for Data Hub 2.4 on AWS

For official links to install documentation see:

[SAP NOTE 2686169 - Prerequisites for installing SAP Data Hub 2](https://launchpad.support.sap.com/#/notes/2686169)
[Installation Guide for SAP Data Hub](https://help.sap.com/viewer/e66c399612e84a83a8abe97c0eeb443a/2.4.latest/en-US/9f866d8ef9a94c30947f12e73eaf0dd9.html)  - Refer to AWS EKS Sections where applicable

Overview
---------
PREREQ : Assumes AWS account with basic knowledge of AWS services, principals and setup steps


0) Create IAM Role
    e.g. eksrole  with following assigned policies
         AmazonEKSClusterPolicy
         AmazonEC2ContainerRegistryFullAccess
         AmazonEC2ContainerRegistryPowerUser
         AmazonEKSServicePolicy
1) Create Cluster in AWS EKS (AWS Kubernetes Cluster)
2) Get AWS ECR URL   (AWS Docker REgistry) [refer to umpbox steps]
3) Use AWS cloud formation to create 3 node R5.xlarge  cluster 
3) Create Jumpboxwith and follow install steps ( see 'steps to run on Jump Box.txt')
    NOTE: Used T3.Micro Instance type with minimum 100Gb [Deep Learning AMI (Amazon Linux) Version 21.0 - ami-055ab192b68ca4d2f]

