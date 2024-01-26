Repo url : https://github.com/mohsmohamed/staytus

Application url : awseb--AWSEB-SA9JwQjvuwyG-2066204051.eu-north-1.elb.amazonaws.com

# Test Assignment A: Docker and Microservices
# Project Overview
The project is a web application consisting of three services: App (PHP), MySQL, and Redis. The goal is to containerize these services using Docker, ensuring each service has its own Dockerfile. A docker-compose.yml file is created to orchestrate the services, enabling communication between them and scalability.

# Project Structure
# App (PHP):

Dockerfile: Describes the setup of the PHP service.
Application Code: PHP application files.
# MySQL:
Dockerfile: Configures the MySQL service.
Database Initialization Script: Shell script to initialize the MySQL database.
# Redis:
Dockerfile: Specifies the Redis service setup.
Configuration Files: Redis configuration files.
# docker-compose.yml:
Defines services, networks, and volumes for orchestration.


# Instructions to Build and Run
1. Clone the Repository
    git clone https://github.com/mohsmohamed/staytus.git
    cd staytus
2. Build and Run Containers:
    docker-compose up -d
3. Access the Application:
    PHP Application: http://localhost
    MySQL Database: Hostname: mysql, Port: 3306
    Redis Service: Hostname: redis, Port: 6379
4. Scaling Services:
    docker-compose up -d --scale app=2
5. Cleanup:
    docker-compose down

# Assumptions
The environment variables are set in a .env file for sensitive configurations.
The MySQL database is configured to allow connections from any host (MYSQL_ROOT_HOST: '%').


# Test Assignment B: Continuous Integration/Continuous Deployment (CI/CD)

# CI/CD Pipeline Setup
The CI/CD pipeline is established using AWS CodePipeline, which includes stages for building, testing, and deploying the application. The pipeline is triggered automatically upon code changes.

# Pipeline Structure
1. Source Stage (GitHub):
    Monitors the GitHub repository for changes.
2. Build Stage:
    Uses AWS CodeBuild to build the Docker images and execute tests.
3. Deploy Stage (Elastic Beanstalk):
    Utilizes AWS Elastic Beanstalk for deployment, scaling, and managing the application.

# Instructions
    The pipeline is configured to automatically trigger on changes to the main branch.

# Test Assignment C: Deployment to a Cloud or Server Environment

# Deployment Process
The CI/CD pipeline is extended to include a deployment stage, deploying the application to AWS Elastic Beanstalk with Docker runtime. Basic monitoring and logging are implemented in the AWS environment.

# Deployment Steps
1. CI/CD Pipeline:
    The pipeline automatically deploys changes to AWS Elastic Beanstalk after the build stage.
2. Deployment Configuration:
    Elastic Beanstalk is configured for scalability, with environment configurations set in the AWS console.
3. Monitoring and Logging:
    AWS CloudWatch is used for basic monitoring and logging.
4. Accessing the Deployed Application:
    The application is accessible through the Elastic Beanstalk URL.

# Security and Monitoring
    * Security Groups and Virtual Networks: Configured to follow security best practices.
    * Monitoring: Basic monitoring enabled using AWS CloudWatch.
    * the service is published through a load balancer that can be configured with "ssl certificate and waf "but that didn't happen as i don't have a published domain.
