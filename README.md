# Hello World Nginx App

This is a simple Hello World Nginx application deployed on AWS.

## Overview

This application serves a static HTML page using Nginx web server. It is deployed as a Docker container running on an ECS (Elastic Container Service) cluster farget.

## System Diagram

## Deployment

### Prerequisites

- VS Code.
- Docker installed locally.
- Access to an AWS account.

### Steps to Deploy

1. Build the Docker image:

   ```bash
   docker build -t hello-world-nginx .
   ```

2. Tag the Docker image:

   ```bash
   docker tag hello-world-nginx:latest <your-repository-uri>/hello-world-nginx:latest
   ```

3. Push the Docker image to ECR Or Docker hub.

4. Deploy the ECS service using the CloudFormation template provided in this repository.

5. Access the application using the public URL of the load balancer associated with the ECS service.

## Directory Structure

- **Dockerfile**: Specifies the instructions to build the Docker image for the Nginx application.
- **deploy/service.yaml**: CloudFormation template to deploy the ECS service.
- **deploy/infra.yaml**: CloudFormation template to deploy the common infrastructure needed for ecs service.
- **index.html**: Static HTML page served by Nginx.

## Troubleshooting

- If you encounter any issues during deployment, check the CloudFormation stack events for error messages.
- Ensure that your IAM user has the necessary permissions to create ECS resources.

## Authors

- Dinesh Lawate <dinesh.lawate.me@gmail.com>

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
