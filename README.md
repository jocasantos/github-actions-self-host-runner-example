# How to set up GitHub Actions with a Self Host Runner (AWS)

This is a guide on how to set up GitHub Actions with a self-hosted runner on AWS. This guide will walk you through the process of setting up a self-hosted runner on an EC2 instance and configuring it to work with GitHub Actions.

### Prerequisites

Before you begin, you will need the following:

- An AWS account
- A GitHub repository

### Step 1: Create an EC2 instance

The first step is to create an EC2 instance that will act as the self-hosted runner. Follow these steps to create an EC2 instance:

1. Log in to the AWS Management Console.
2. Click on the "Services" dropdown menu and select "EC2".
3. Click on the "Launch Instance" button.
4. Choose an Amazon Machine Image (AMI) for your instance. You can choose the default Ubuntu AMI.
5. Choose an instance type. You can choose the t2.micro instance type, which is eligible for the AWS Free Tier.
6. Configure the instance details. You can leave the default settings.
7. Add storage to your instance. You can leave the default settings.
8. Add tags to your instance. You can leave the default settings.
9. Configure the security group for your instance. You will need to add a rule to allow inbound traffic on port 22 (SSH) and port 443 (HTTPS).
10. Create a new key pair or select an existing key pair to connect to your instance.
11. Review your instance settings and click on the "Launch" button.

### Step 2: Connect to your EC2 instance

1. Connect to your EC2 instance using SSH. You can use the following command to connect to your instance:

```bash
ssh -i /path/to/your/key.pem
```

2. Install the required dependencies on your EC2 instance. You will need to install Git and Docker on your instance. You can use the following commands to install Git and Docker:

```bash
sudo apt update
sudo apt install git
sudo apt install docker.io
```



