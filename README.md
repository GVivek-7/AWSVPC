# AWS-VPC
AWS VPC Setup: This project demonstrates creating and configuring an AWS VPC, including setting up subnets (public/private), configuring an Internet Gateway, and updating route tables for internet connectivity. Ideal for learning basic AWS networking and VPC management.

# AWS VPC Setup Guide

This README file provides a step-by-step guide for creating and configuring a Virtual Private Cloud (VPC) in AWS. Follow these instructions to set up your VPC, subnets, and internet gateway.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Creating a VPC](#creating-a-vpc)
- [Configuring Subnets](#configuring-subnets)
- [Setting Up Internet Gateway](#setting-up-internet-gateway)
- [Attaching the Internet Gateway](#attaching-the-internet-gateway)
- [Conclusion](#conclusion)

## Prerequisites

- An AWS account.
- AWS CLI installed and configured, or access to the AWS Management Console.

## Creating a VPC

1. **Sign in** to the AWS Management Console and open the VPC dashboard at [VPC Dashboard](https://console.aws.amazon.com/vpc/).

2. **Create a New VPC:**
   - Click on **"Your VPCs"** on the left navigation pane.
   - Click on the **"Create VPC"** button.
   - Enter the following details:
     - **Name tag:** A descriptive name for your VPC (e.g., `MyVPC`).
     - **IPv4 CIDR block:** The CIDR block for your VPC (e.g., `10.0.0.0/16`).
     - **IPv6 CIDR block:** (Optional) Choose if you need IPv6 support.
     - **Tenancy:** Default or Dedicated.
   - Click **"Create VPC"**.
  
     ![image](https://github.com/user-attachments/assets/7b0565c8-1f28-459d-96be-458c72916560)

## Configuring Subnets

1. **Create a Subnet:**
   - Click on **"Subnets"** on the left navigation pane.
   - Click on the **"Create subnet"** button.
   - Enter the following details:
     - **Name tag:** A descriptive name for your subnet (e.g., `MySubnet`).
     - **VPC:** Select the VPC you created earlier.
     - **Availability Zone:** Choose an availability zone within your region.
     - **CIDR block:** The CIDR block for your subnet (e.g., `10.0.1.0/24`).

2. **Configure Subnet Settings:**
   - Decide if the subnet will be **Public** or **Private**:
     - **Public Subnet:** Ensure this subnet will have access to the internet (i.e., it will have a route to the internet via an Internet Gateway).
     - **Private Subnet:** No direct access to the internet.
   - Click **"Create"**.
  
     ![image](https://github.com/user-attachments/assets/480fe683-8daa-4d41-9526-44169243fc18)


## Setting Up Internet Gateway

1. **Create an Internet Gateway:**
   - Click on **"Internet Gateways"** on the left navigation pane.
   - Click on the **"Create internet gateway"** button.
   - Enter a name tag for the internet gateway (e.g., `MyInternetGateway`).
   - Click **"Create internet gateway"**.

## Attaching the Internet Gateway

1. **Attach the Internet Gateway to Your VPC:**
   - Select the newly created internet gateway from the list.
   - Click on **"Actions"** and choose **"Attach to VPC"**.
   - Select the VPC you created earlier.
   - Click **"Attach"**.
  
After Attaching the internet gateway to the VPC that you have created, the console should look like this.

![image](https://github.com/user-attachments/assets/54966fca-154a-4e97-84d9-0e50a9eb4d4a)


2. **Update Route Tables:**
   - Navigate to **"Route Tables"** on the left navigation pane.
   - Select the route table associated with your VPC.
   - Click on the **"Routes"** tab and then **"Edit routes"**.
   - Click **"Add route"**:
     - **Destination:** `0.0.0.0/0` (for IPv4) or `::/0` (for IPv6).
     - **Target:** Select the internet gateway you created.
   - Click **"Save routes"**.

## Conclusion

Your VPC is now configured with a subnet, an internet gateway, and proper route settings. This setup allows for internet connectivity if the subnet is public or isolates it if it's private.

For more information and advanced configurations, refer to the [AWS VPC documentation](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-vpc.html).

