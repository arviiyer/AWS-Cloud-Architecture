# AWS Cloud Architecture Implementation

## Objective

This project was performed as a college project and was aimed to design and implement a secure cloud infrastructure on AWS, spanning from September to October 2023. The architecture was meticulously planned to comply with the AWS Well-Architected Framework, ensuring operational excellence, security, reliability, performance efficiency, and cost optimization. By integrating AWS services such as IAM for identity and access management, VPC for network isolation and Security Groups for layered defense, the solution achieved a robust security posture. The architecture was built with a focus on implementing the principle of least privilege and role-based access controls to provide granular and appropriate access. Additionally, the infrastructure was fortified with advanced security measures including data encryption and comprehensive network security, alongside monitoring using AWS CloudWatch to ensure continuous security and compliance. This secure architecture forms a solid foundation for hosting sensitive applications and workloads in the cloud with confidence in their security and integrity.

### Skills Learned

- Proficiency in applying the AWS Well-Architected Framework for creating stable and efficient systems on the cloud.
- Expertise in configuring and managing AWS Identity and Access Management (IAM) to secure services with appropriate permissions.
- Competence in setting up and administering Amazon Virtual Private Cloud (VPC) to provide a logically isolated section of the AWS Cloud.
- Knowledge of configuring security groups as a virtual firewall for EC2 instances to control inbound and outbound traffic.
- Familiarity with role-based access control (RBAC) to enforce the least privilege principle and ensure users have access only to the resources necessary for their roles.
- Proficiency in utilizing AWS CloudWatch for monitoring the performance and health of AWS services and applications.
- Understanding of creating redundant and fault-tolerant architectures by distributing resources across multiple Availability Zones.
- Ability to design network architectures that incorporate both public and private subnets to optimize security and functionality.
- Expertise in allocating IP address ranges, planning subnetting, and managing spare capacity in network design.

### Tools Used

- Amazon Web Services (AWS) Cloud Platform
- AWS Identity and Access Management (IAM)
- Amazon Virtual Private Cloud (VPC)
- AWS Security Groups
- AWS CloudWatch for monitoring and logging
- NAT Gateways for outbound internet access from private subnets
- Internet Gateway to connect the VPC with the internet
- VPC Endpoints for private connections to AWS services
- AWS S3 for object storage and data backups
- IP Address Management (IPAM) for address allocation within the VPC

## Steps

### 1. Configuring MFA and IAM
- Set up Multi-Factor Authentication (MFA) for the root account.
  ![image](https://github.com/arviiyer/AWS-Cloud-Architecture/assets/26136879/1f9332bd-9790-45c6-9bd8-ad98b2c8983a)

- Create an IAM user and assign it to a group with Administrator Access.
  ![image](https://github.com/arviiyer/AWS-Cloud-Architecture/assets/26136879/da956c90-fb65-4056-b93c-8c7709dfd977)

### 2. Building the VPC
- Use the [AWS QuickStart guide's](https://aws-ia.github.io/cfn-ps-aws-vpc/) architecture as a reference to create the VPC with all the required components.
  ![image](https://github.com/arviiyer/AWS-Cloud-Architecture/assets/26136879/e11ca516-dd57-4423-b31e-8a7294f75f2e)
- Create additional subnets and a NAT Gateway in the new Availability Zone.
  ![image](https://github.com/arviiyer/AWS-Cloud-Architecture/assets/26136879/84746960-3b2a-4d0c-8ef3-ca3d17579c05)
  ![image](https://github.com/arviiyer/AWS-Cloud-Architecture/assets/26136879/cb03cd3c-cbb3-4682-9e64-dd322ab9501d)
- Set up a NAT Gateway and update the route tables.
  ![image](https://github.com/arviiyer/AWS-Cloud-Architecture/assets/26136879/2828f464-c7f4-4a3c-bcbb-c9c9459df18e)
- Finalize the VPC configuration with all route tables in place.
  ![image](https://github.com/arviiyer/AWS-Cloud-Architecture/assets/26136879/a5b78964-2d06-4070-9c36-df5e4020252b)

### 3. Adding EC2 Instance
- Launch and configure an EC2 instance with the necessary settings.
  ![image](https://github.com/arviiyer/AWS-Cloud-Architecture/assets/26136879/c75b746e-46a3-430c-aba7-521c99b61b04)
- Verify the instance's connectivity through SSH.
  ![image](https://github.com/arviiyer/AWS-Cloud-Architecture/assets/26136879/3b5d8c3f-2255-4042-8c09-0816b90f3489)

### 4. Setting Up a CloudWatch Alarm
- Create and configure a CloudWatch alarm for the EC2 instance.
  ![image](https://github.com/arviiyer/AWS-Cloud-Architecture/assets/26136879/82d4188a-a158-4d66-ac7c-2b1546637fe5)
- Trigger and validate the CloudWatch alarm functionality.
  ![image](https://github.com/arviiyer/AWS-Cloud-Architecture/assets/26136879/8d8ee06f-ec96-4f05-96f5-8ab48f62e868)
  ![image](https://github.com/arviiyer/AWS-Cloud-Architecture/assets/26136879/7ba70d3c-8a6f-491e-ba67-3decff8f4593)

### 5. Creating an S3 Bucket
- Set up an S3 bucket with proper security measures.
  ![image](https://github.com/arviiyer/AWS-Cloud-Architecture/assets/26136879/8c237c03-e4d0-4f7e-b29b-0d2b69f7bcb1)

### 6. Setting Up CloudTrail
- Enable CloudTrail for account activity monitoring.
  ![image](https://github.com/arviiyer/AWS-Cloud-Architecture/assets/26136879/a34217e1-d141-4c04-8bac-7ec600a246d6)
