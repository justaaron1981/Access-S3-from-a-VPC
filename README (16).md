<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Access S3 from a VPC

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-s3)

**Author:** Aaron  
**Email:** Justaaron1981@yahoo.com

---

## Access S3 from a VPC

![Image](http://learn.nextwork.org/gleeful_red_proud_durian/uploads/aws-networks-s3_3e1e79a2)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC is AWS's foundational networking service that alows us create our own isolated network within an AWS region and control network traffic and security etc  

### How I used Amazon VPC in this project

In today's project, I used Amazon VPC to launch a public subnet and EC2 instance, and directly accessed/managed an Amazon s3 bucket through the EC2 instance using AWS CLI 

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was that access keys are required for EC2 instances / other applications to get access to my AWS enviroment.

### This project took me...

This project took me 90 minutes.

---

## In the first part of my project...

### Step 1 - Architecture set up

In this step, I will launch a VPC with a public subnet. I will also launch an EC2 instance inside the public subnet

### Step 2 - Connect to my EC2 instance

In this step, I will directly access an EC2 instance using EC2 instance connect because...

### Step 3 - Set up access keys

In this step, I will create access keys so my EC2 instance can access my AWS environment, specifically the ability to interact with the S3 bucket

---

## Architecture set up

I started my project by launching a VPC with a public subnet and an EC2 instance inside the public subnet

I also set up a S3 bucket with two files inside

![Image](http://learn.nextwork.org/gleeful_red_proud_durian/uploads/aws-networks-s3_4334d777)

---

## Running CLI commands

AWS CLI is a software I can download into a local computer's terminal so that I have access to AWS account  and different actions without needing to use the AWS management console. I have access to AWS CLI because it's pre-installed in EC2

The first command I ran was AWS s3 ls. This command is used to access S3 buckets inside AWS account (that the EC2 instance/application) has access to

The second command I ran was AWS configure. This command is used to set up my EC2 instances credentials in order to access my AWS enviroment

![Image](http://learn.nextwork.org/gleeful_red_proud_durian/uploads/aws-networks-s3_e7fa8776)

---

## Access keys

### Credentials

To set up my EC2 instance to interact with my AWS environment, I configured an Access key ID, secret key ID, default region, and a default output format.

Access keys are credentials that my EC2 instance and other applications/servers need in order to get access to my AWS environment. IE interact with my AWS resources/services.  

Secret access keys are like passwords. For our keys/ credentials. Our EC2 instance/ other application needs secret access keys as authentication and login to our AWS enviroment

### Best practice

Although I'm using access keys in this project, a best practice alternative is to use i should be using IAM roles with permissions attached. This is a more secure way to grant access to an EC2 instance because it is much easier to track, attach, and detach IAM policies 

---

## In the second part of my project...

### Step 4 - Set up an S3 bucket

In this step, I will launch an Amazon S3 bucket with two files inside. The S3 bucket will be accessed by my EC2 instance later in the project to test whether or not my access keys have successfully given AWS access to my EC2 instance 

### Step 5 - Connecting to my S3 bucket

In this step, I will use AWS commands to try control/manage my S3 bucket. This means interacting with S3 bucket through my EC2 instanace/VPC AWS management console

---

## Connecting to my S3 bucket

The first command I ran was AWS s3 ls. This command is used to access S3 buckets inside AWS account (that the EC2 instance/application) has access to

When I ran the command AWS s3 ls again, the terminal responded with my list of S3 bucket. This indicated that my access key works. Ie my EC2 instance has access to my AWS enviroment

![Image](http://learn.nextwork.org/gleeful_red_proud_durian/uploads/aws-networks-s3_4334d778)

---

## Connecting to my S3 bucket

Another CLI command I ran was  aws s3 ls s3://nextwork-aaron-project   which returned the list of objects in my S3 bucket

![Image](http://learn.nextwork.org/gleeful_red_proud_durian/uploads/aws-networks-s3_4334d779)

---

## Uploading objects to S3

To upload a new file to my bucket, I first ran the command sudo touch /tmp/test.txt .This command creates a blank file called test txt in my EC2 instance local directory .

The second command I ran was  aws s3 cp /tmp/test.txt s3://nextwork-aaron-project  This command will 'copy' ie upload the blank file created in my S3 bucket

The third command I ran was aws s3 ls s3://nextwork-aaron-project which validated that I uploaded all the objects in my S3 bucket - including test.txt. This valided that my EC2 instance through AWS CLI commands can get access to other AWS services (S3)

![Image](http://learn.nextwork.org/gleeful_red_proud_durian/uploads/aws-networks-s3_3e1e79a2)

---

---
