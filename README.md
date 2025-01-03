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

1. Once your instance is running, you will need to connect to it using SSH. You can use the following command to connect to your instance:

```bash
ssh -i /path/to/your/key.pem ubuntu@your-instance-public-ip
```

2. Update the package list and install the required packages:

```bash
sudo apt update
sudo apt install git
```

### Step 3: Clone this repository

1. Clone this repository to your local machine using the following command:

```bash
git clone https://github.com/jocasantos/github-actions-self-host-runner-example.git
```

2. Navigate to the repository directory:

```bash
cd github-actions-self-host-runner-example
```

### Step 4: Follow the instructions for create a self-hosted runner

1. On your GitHub repository, go to "Settings" -> "Actions" -> "Add runner".
2. Press "New self-hosted runner".
3. Choose Linux as the operating system.
4. Follow the instructions to download, configure and connect to the runner.
5. You should see in your terminal "Listening for Jobs" if the runner is correctly configured.

### Step 5: Modify the workflow file

1. Open the `.github/workflows/example-actions.yml` file in your repository.
2. Modify the `runs-on` parameter to use the self-hosted runner you created in the previous step. For example:

```yaml
jobs:
  build:
    runs-on: self-hosted
```

3. Commit and push the changes to your repository.
4. You shoulde see the in your terminal the runner executing the workflow.

> Congratulations! You have successfully set up GitHub Actions with a self-hosted runner on AWS :tada:







