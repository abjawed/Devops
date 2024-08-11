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
