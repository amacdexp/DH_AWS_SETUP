# SAP Data Hub installation Steps on AWS
Example installation steps for Data Hub 2.4 on AWS

For official links to install documentation see:

[SAP NOTE 2686169 - Prerequisites for installing SAP Data Hub 2](https://launchpad.support.sap.com/#/notes/2686169)

[Installation Guide for SAP Data Hub](https://help.sap.com/viewer/e66c399612e84a83a8abe97c0eeb443a/2.4.latest/en-US/9f866d8ef9a94c30947f12e73eaf0dd9.html)  - Refer to AWS EKS Sections where applicable


Overview
---------
PREREQ : Assumes AWS account with basic knowledge of AWS services, principals and setup steps


0. Create an S3 Bucket for DH Snapshots (e.g. https://s3.console.aws.amazon.com/s3/buckets/<BUKETNAME>/<CLUSTER NAME FOLDER>
0. Reuse or create an EC2 Secuity Group / VPC ID / Subnet ID
1. Create IAM Role
```
For example create 'eksrole'  with following policies assigned :
*  AmazonEKSClusterPolicy
*  AmazonEC2ContainerRegistryFullAccess
*  AmazonEC2ContainerRegistryPowerUser  (Need to double check if this required)
*  AmazonEKSServicePolicy
```
2. Create Cluster in AWS EKS [AWS Kubernetes Cluster](https://docs.aws.amazon.com/eks/latest/userguide/getting-started.html) 
    
    NOTE: AWS Charge $0.20 per hour (~$144 p/mth) for each Amazon EKS cluster created
3. Get AWS ECR URL   (AWS Docker Registry 500Mb free  0.10 p/gb / mth)   [refer to jumpbox steps]  
4. Use AWS cloud formation to create 3 node R5.xlarge  cluster 
5. Create Jumpboxwith and follow install steps ( see [steps to run on Jump Box.txt](https://github.com/amacdonaldsap/DH_AWS_SETUP/blob/master/steps%20to%20run%20on%20Jump%20Box.txt) )

    NOTE: Used T3.Micro Instance type with minimum 100Gb [Deep Learning AMI (Amazon Linux) Version 21.0 - ami-055ab192b68ca4d2f]

