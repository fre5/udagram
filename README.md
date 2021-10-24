# Udagram
Udagram is a startup project by Udacity used as students final project to demonstrate the ability to host a full stack application with Amazon Web Services and the workflow of automating CI/CD pipeline with CircleCI.

## Application URL
http://udacitygram-frontend.s3-website-us-west-2.amazonaws.com/home


## Infrastructure outline
- This project is setup using a personal AWS account
- Startup project file cloned from https://github.com/udacity/nd0067-c4-deployment-process-project-starter
- AWS RDS Postgres 12.5 database is used to keep the project within the free price tier, access set to public, VPC security group default, password authentication, no backup, no encryption, performance insights disabled, no enhanced monitoring, no log reports, and deletion protection disabled. 
- AWS Elastic Beanstalk is a web server environment, platform is a NodeJS version 12.
- AWS S3 with 3 buckets setup for application post files, front end build, and another front end test build. 
- CircleCI is setup with a GitHub repository https://github.com/fre5/udagram, configuration file here https://github.com/fre5/udagram/blob/main/.circleci/config.yml and Environment Variables set with each appropriate values from .env file that is stored locally. 

## AWS
### Relational Database Service (RDS)
![RDS Management Console](https://raw.githubusercontent.com/fre5/udagram/main/udagram-diagrams/EB%20Management%20Console.png)

### Elastic Beanstalk (EB)

### Simple Storage Service (S3)

## CircleCi 


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