# Udagram
In this project I used Udacity's startup application Udagram to demonstrate the process of hosting a full stack application with Amazon Web Services and to showcase the workflow of automating CI/CD pipeline with CircleCI.

## Application URL
http://udacitygram-frontend.s3-website-us-west-2.amazonaws.com/home

## Infrastructure outline
- This project is setup using a personal AWS account
- Startup project file cloned from https://github.com/udacity/nd0067-c4-deployment-process-project-starter
- AWS RDS Postgres 12.5 database is used to keep the project within the free price tier, access set to public, VPC security group default, password authentication, no backup, no encryption, performance insights disabled, no enhanced monitoring, no log reports, and deletion protection disabled. 
- AWS Elastic Beanstalk is a web server environment, platform is a NodeJS version 12.
- AWS S3 with 3 buckets setup for application post files, front end build, and another front end test build. 
- CircleCI is setup with a GitHub repository https://github.com/fre5/udagram, configuration file here https://github.com/fre5/udagram/blob/main/.circleci/config.yml and Environment Variables set with each appropriate values from .env file that is stored locally. 

## AWS RDS Console
![RDS Management Console](https://raw.githubusercontent.com/fre5/udagram/main/udagram-diagrams/RDS%20Management%20Console.png)

## AWS EB Console
![EB Management Console](https://raw.githubusercontent.com/fre5/udagram/main/udagram-diagrams/EB%20Management%20Console.png)

## AWS S3 Console
![S3 Management Console](https://raw.githubusercontent.com/fre5/udagram/main/udagram-diagrams/S3%20Management%20Console.png)

## AWS Architecture Diagram
![Udagram AWS Architecture](https://raw.githubusercontent.com/fre5/udagram/main/udagram-diagrams/Udagram.jpg)

## CircleCI Architecture Diagram
![Udagram CircleCI Successful Build Pipeline](https://raw.githubusercontent.com/fre5/udagram/main/udagram-diagrams/Udagram%20CircleCI%20Pipeline.jpg)

![Udagram CircleCI Successful Build Pipeline](https://raw.githubusercontent.com/fre5/udagram/main/udagram-diagrams/UdagramCircleCI.png)

### CircleCI Environment Variables
![Udagram CircleCI Environment Variables](https://raw.githubusercontent.com/fre5/udagram/main/udagram-diagrams/Environment%20Variables%20-%20udagram.png)

### CircleCI Pipeline Outline
- CircleCI initialized with version 2.1
- Orbs used are:
  - Node: circleci/node@4.7
  - AWS CLI: circleci/aws-cli@1.3.1
  - EB CLI: circleci/aws-elastic-beanstalk@2.0.1
- Pipeline steps:
  - Install Node latest stable version
  - Checkout
  - AWS CLI setup
  - AWS Elastic Beanstalk setup
  - Application Frontend install
  - Application Backend install
  - Install Node Version Manager
  - Install Node version 14 to fix front end build failed bug with openssl related to node beyond version 14
  - Application Frontend build
  - Application Backend build
  - Application Frontend deploy to S3
  - Application Backend deploy to Elastic Beanstalk with EB CLI using eb deploy

## Project requirement

- [x] Provision the necessary AWS services Udagram needs
- [x] Deploy Udagram application to AWS services
- [x] Connect the GitHub repo to CircleCI
- [x] Configure a CircleCI pipeline to automate deployments
- [x] Document the infrastructure needs (RDS, S3, Elastic Beanstalk) and explain the pipeline steps
- [x] Create architecture diagrams for an overview of the infrastructure and the pipeline

## File/document requirement

- [x] .circleci/config.yml
- [x] a root level package.json
- [x] a documentation Readme
- [x] a docs folder to include architecture diagram and more detailed documentation files on infrastructure description, app dependencies, and pipeline process