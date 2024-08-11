---
# Build Orchestration Using Jenkins

## Lab Requirements

### AWS Cloud Platform


1. **Create an AWS Free-Tier Account**
   - Visit: [AWS Console](https://aws.amazon.com/console/)
   - The free-tier account is available for 12 months.

2. **Prerequisites for AWS Account Creation**
   - An active Email ID.
   - A mobile number.
   - An active credit or debit card that supports international transactions for authentication.

3. **Setting Up a New AWS Account**
   - Clear your browser history and cache before creating a new account.
   - Create a new AWS account using a different Email ID.

4. **Logging into the AWS Console**
   - Log in as the root user using:
     - **Email ID**
     - **Password**

### EC2 Instance Management

1. **Create EC2 Instances / Virtual Machines (VMs)**
   - After logging into the AWS console, navigate to the EC2 dashboard and create your desired EC2 instances.
   - Select the appropriate instance type, storage, and security settings according to your project needs.

2. **Establish Connection to VMs / EC2 Instances**

   - **Using AWS Instance Connect:**
     - This is a browser-based SSH client provided by AWS that allows you to connect to your EC2 instances directly from the AWS Management Console.

   - **Using SSH Clients:**
     - **MobaXterm:** 
       - Download from [MobaXterm Official Site](https://mobaxterm.mobatek.net/download.html)
     - **PuTTY:**
       - A widely-used SSH client.

   - **Using Terminal:**
     - If you're using a Unix-based operating system, you can establish a connection to your EC2 instances directly through the terminal.

- **It is recommended to use IAM users and roles for all AWS tasks instead of the root account. The root account should be reserved for essential tasks that require the highest level of access. Any necessary changes to permissions or access should be managed through IAM to ensure better security and control over your AWS environment.**

### IAM (Identity and Access Management) Setup

1. **Understanding IAM**
   - IAM allows you to manage access to AWS services and resources securely.
   - You can create and manage AWS users and groups, and use permissions to allow or deny their access to AWS resources.

2. **Creating an IAM User**
   - Navigate to the IAM service in the AWS console.
   - Create a new IAM user for managing your EC2 instances and Jenkins setup.
   - Assign the necessary permissions to the IAM user, such as `AmazonEC2FullAccess` and `AmazonS3FullAccess`, depending on your project requirements.

3. **Configuring IAM Roles**
   - IAM roles can be used to delegate access to users, applications, or services that don’t normally have access to your AWS resources.
   - Create a new IAM role for your EC2 instances:
     - Attach necessary policies, such as `AmazonEC2RoleforSSM`, to allow your EC2 instances to interact with other AWS services.
     - Assign this role to your EC2 instances during the creation or afterward by modifying the instance settings.

4. **Securing IAM User Access**
   - Enable Multi-Factor Authentication (MFA) for the IAM user to add an extra layer of security.
   - Regularly review and rotate access keys for IAM users to minimize security risks.

5. **Using IAM Policies**
   - IAM policies define permissions that specify what actions are allowed or denied for specific resources.
   - Create custom policies if the predefined policies don’t meet your security requirements.
   - Attach these policies to IAM users, groups, or roles according to your needs.


Jenkins Orchestration Setup
Overview

    Jenkins is an open-source build orchestration tool used to automate parts of software development related to building, testing, and deploying, facilitating Continuous Integration/Continuous Deployment (CI/CD).

Jenkins Architecture
Master/Slave Architecture

    Jenkins Master Node:
        The master node is where Jenkins is installed and is responsible for scheduling build jobs, dispatching builds to the slave nodes for execution, monitoring the slaves (possibly taking them online and offline as required), and recording and presenting the build results.
        It is used to create CI/CD pipeline projects, which are scheduled to run on slave nodes.

    Jenkins Slave Nodes:
        Slave nodes are where the actual build processes are executed.
        They are connected to the master node, and they perform application builds as assigned by the master node.

Example Setup

    Jenkins Master Node:
        Installed with Jenkins.
        Used for creating CI/CD pipeline jobs/projects.
        Assigns build tasks to slave nodes.

    Jenkins Slave Nodes:
        Node 1: Java Application - Build tool: Maven
        Node 1.1: Java Application - Build tool: Maven
        Node 2: Python Application
        Node 3: NodeJS Application
        Node 4: NodeJS Application
        Node 5: .NET Application

Alternatives to Jenkins

    Azure Pipelines
    GitLab CI
    AWS CodePipeline
    Bamboo

Jenkins Deployment Architecture
Overview

This document outlines the deployment architecture of Jenkins, including the roles and configurations of Master and Slave nodes. Jenkins is utilized to create and manage Continuous Integration and Continuous Delivery (CI/CD) pipeline jobs. The system is designed to handle various types of build processes and applications, including Java, Python, NodeJS, and .NET.
Jenkins Master Node

    Role: Central node responsible for managing Jenkins operations and scheduling jobs.
    Configuration:
        Jenkins Installation: Jenkins is installed and configured on this node.
        Build Tools: Maven is used for building Java applications.
        Functionality:
            Creation and management of CI/CD pipeline jobs/projects.
            Scheduling and dispatching jobs to slave nodes.
            Monitoring job execution and reporting results.

Jenkins Slave Nodes

Slave nodes (also known as agent nodes) are dedicated machines configured to execute build jobs dispatched by the Master node. Each slave node is specialized for different types of builds.
Jenkins Slave Node 1

    Role: Executes jobs related to Java applications.
    Configuration:
        Build Tool: Maven
        Application Type: Java

Jenkins Slave Node 1.1

    Role: Executes jobs related to Java applications.
    Configuration:
        Build Tool: Maven
        Application Type: Java

Jenkins Slave Node 2

    Role: Executes jobs related to Python applications.
    Configuration:
        Build Tool: Python-specific tools (e.g., pip, pytest)
        Application Type: Python

Jenkins Slave Node 3

    Role: Executes jobs related to NodeJS applications.
    Configuration:
        Build Tool: npm/yarn
        Application Type: NodeJS

Jenkins Slave Node 4

    Role: Executes jobs related to NodeJS applications.
    Configuration:
        Build Tool: npm/yarn
        Application Type: NodeJS

Jenkins Slave Node 5

    Role: Executes jobs related to .NET applications.
    Configuration:
        Build Tool: MSBuild
        Application Type: .NET

Summary

    Master Node: Central management of Jenkins operations and scheduling.
    Slave Nodes:
        Node 1 & Node 1.1: Java applications with Maven.
        Node 2: Python applications.
        Node 3 & Node 4: NodeJS applications.
        Node 5: .NET applications.

This architecture allows for a scalable and organized approach to managing diverse build processes, leveraging dedicated nodes for each application type to optimize performance and resource utilization.


Roles and Responsibilities of a DevOps Engineer
Developer's Perspective

    Consumers: Developers consume the CI/CD pipelines and other services managed by DevOps.

DevOps Perspective

    Jenkins Administration:
        Installation and configuration of Jenkins.
        Managing Jenkins plugins.
        Tool management within Jenkins.
        User and security management.
        Global Jenkins system management.
        Creating CI/CD pipeline projects.
        Creating and managing Jenkins slave nodes.
        Onboarding applications to the DevOps Jenkins CI/CD process.
        Troubleshooting issues within Jenkins.
        Periodic backup and recovery of Jenkins components.
        Periodic upgrades of Jenkins and its plugins.

Jenkins Installation Guide

    Official Jenkins installation guide: Jenkins Installation Documentation

Installation on AWS Cloud

    Launch a Linux Ubuntu Machine on AWS EC2:
        Choose Linux Ubuntu v22.04 as the Amazon Machine Image (AMI).

    Install Jenkins:

Package Managers for Linux Distributions:

    CentOS/RHEL: yum
    Ubuntu/Debian: apt-get / apt
    Fedora: dnf

Jenkins can be accessed as a web service, using port 8080 by default.

Commands for Jenkins Installation on Ubuntu:

    sudo apt update
    sudo apt install fontconfig openjdk-17-jre
    java -version
    

    sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
    https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
    echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]" \
    https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
    /etc/apt/sources.list.d/jenkins.list > /dev/null
    sudo apt-get update
    sudo apt-get install jenkins

AWS EC2 Usage Considerations

    Running a VM:
        1 VM = 750 hours/month.
        10 VMs = 75 hours/month (per VM).
