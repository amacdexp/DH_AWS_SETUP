# SAP Data Hub installation Steps on AWS
Example instllation steps for install DG 2.4 on AWS


OVerview
---------

0) Create IAM Role
1) Create Cluster in AWS EKS (AWS Kubernetes Cluster)
2) Get AWS ECR URL   (AWS Docker REgistry)
3) Use AWS cloud formation to create 3 node R5.xlarge  cluster 
3) Create Jumpboxwith and follow install steps  (e.g. micro with 



0)  create role   e.g. eksrole  with policies
  AmazonEKSClusterPolicy
 AmazonEC2ContainerRegistryFullAccess
  AmazonEC2ContainerRegistryPowerUser
  AmazonEKSServicePolicy




Links
https://launchpad.support.sap.com/#/notes/2686169
https://help.sap.com/viewer/e66c399612e84a83a8abe97c0eeb443a/2.4.latest/en-US/9f866d8ef9a94c30947f12e73eaf0dd9.html
