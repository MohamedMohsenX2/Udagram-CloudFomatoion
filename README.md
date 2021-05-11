# Udagram
## Description
Udacity Cloud DevOps Engineer project to deploy a high-availability web app, Udagram, using CloudFormation:
1. Create a Launch Configuration for application servers that deploy four servers, two located in each private subnets. 
2. Auto-scaling group that uses the launch configuration. 
3. Each server has two vCPUs and at least 4GB of RAM. A Machine Image (AMI) is chosen that uses Ubuntu 18 with at least 10GB of disk space so that app does not run into issues. 
4. App communicates on the default HTTP Port: 80, so servers need this inbound port open to be used with the Load Balancer and the Load Balancer Health Check. 
5. Outbound, the servers will have unrestricted internet access to be able to download and update its software. 
6. Inbound public traffic (0.0.0.0/0) is allowed on port 80, which is the default HTTP port. 
7. Public URL of the LoadBalancer is an output exported from the CloudFormation script.

## Setup 
1. Update your IP in Project2-bastion-param.json file to be allowed to access the bastion servers.
2. Create the network stack
>sh create.sh UdagramNetwork Project2-Network.yml Project2-network-param.json
3. Create the servers stack
>sh create.sh UdagramServers Project2-Servers.yml Project2-servers-param.json
4. Create the bastion servers stack
>sh create.sh UdagramBastion Project2-bastion.yml Project2-bastion-param.json

![Udagram_app](https://github.com/MohamedMohsenx2/Udagram/blob/master/UdagramProject.jpeg)

## Dependencies
* AWS CLI
