# Task Delivery
* Please don't fork, branch or create a pull request within this repository. 
* Clone it and do your work there.
* When the task is ready, **Email** your zipped solution back to us (Only first submit count unless otherwise directed).

# Devops Test Task
Thank you for applying to Mode Transportation! We'd like to see how you can build out infrastructure and CI/CD.

## Hello World PHP App
Provided in `src` is a "hello world" PHP app with 2 files.

## Part 1: Infrastructure
Your goal is to set up this app so that it runs on AWS infrastructure. 
You can choose any appropriate AWS technology. Please utilize the AWS Free Tier if you do not have a personal AWS account already. https://aws.amazon.com/free

Your output for this step should be a **single or very few commands** that fully initializes and configures all required infrastructure.
Please **update** this **README** file as part of the solution to **document the execution procedure, assumptions, environment setups, considerations**, etc.

#### The code will be run on a blank AWS account with zero existing resources where you will need to provision everything as part of your infrastructure stack.

### Part 1 Solution Below ###

1. Create Security Group
aws ec2 create-security-group --group-name mode-interview --description "Basic security group" # copy groupId from output = sg-0ccb1d0520df53dc6

2. Edit security group to allow incoming connections on port 22 and 443
aws ec2 authorize-security-group-ingress --group-name mode-interview --protocol tcp --port 22 --cidr 0.0.0.0/0
aws ec2 authorize-security-group-ingress --group-name mode-interview --protocol tcp --port 443 --cidr 0.0.0.0/0
aws ec2 authorize-security-group-ingress --group-name mode-interview --protocol tcp --port 80 --cidr 0.0.0.0/0

3. Create a key-pair to access the instance
aws ec2 create-key-pair --key-name mode-interview-key --query 'KeyMaterial' --output text > mode-interview-key.pem


4. Run an instance in the secruity group
aws ec2 run-instances --image-id ami-0661cd3308ec33aaa --security-group-ids sg-0ccb1d0520df53dc6 --instance-type t2.micro --key-name mode-interview-key


5. SSH Into the instance and install Docker (This could be automated for future servers, just doing it manually now for simplicity)

    - ssh -i "key file.pem" ec2-user@ip-address
    - sudo yum update -y && sudo amazon-linux-extras install docker && sudo yum install docker


6. Start docker php server
    sudo docker run -d -p 80:80 --name server -v ~/php_app:/var/www/html php:7.2-apache

### Part 1 Solution Above ###

## Part 2: CI/CD
Your goal for this step is to set up an automated build and deployment pipeline. Please use a SaaS provider that has
the ability to be configured entirely by file. GitHub Actions, GitLab, CircleCI, TravisCI, or any other provider with a free tier.

The pipeline steps should be:

1. Check out the repository
2. Install any dependencies
3. Build the application
4. Deploy the code update to AWS

For extra credit, you can come up with a process to display the current version number (defined as the build number)
as an HTTP header or within the web application.

Your deliverable here should be a configuration file that we could run. You can also share access to the SaaS to show us
your own working pipeline.

### Part 2 Solution Below ###

Visit this url to view the running app: http://3.17.157.132 

Here is the working pipeline as a GitHub Action:
https://github.com/JackFay/mode-server/actions

### Part 2 Solution Above ###

Good luck!
