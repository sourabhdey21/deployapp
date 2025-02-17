# FastAPI Hello World Application

A simple FastAPI application with automated deployment to AWS EC2 using GitHub Actions.

## Local Development

1. Build the Docker image:
```bash
docker build -t fastapi-hello .
```

2. Run the container:
```bash
docker run -d -p 8080:8080 fastapi-hello
```

3. Access the application:
- API endpoint: http://localhost:8080
- API documentation: http://localhost:8080/docs

## Deployment

This application uses GitHub Actions for automated deployment to AWS EC2. To set up deployment, you need to configure the following secrets in your GitHub repository:

### Docker Hub Secrets
- `DOCKER_USERNAME`: Your Docker Hub username
- `DOCKER_PASSWORD`: Your Docker Hub password/access token

### AWS Credentials
- `AWS_ACCESS_KEY_ID`: Your AWS access key ID
- `AWS_SECRET_ACCESS_KEY`: Your AWS secret access key
- `AWS_REGION`: Your AWS region (e.g., us-east-1)

### EC2 Instance Details
- `EC2_HOST`: Your EC2 instance's public IP or DNS
- `EC2_USERNAME`: SSH username (usually 'ec2-user' or 'ubuntu')
- `EC2_SSH_KEY`: Your EC2 instance's SSH private key

The deployment will automatically trigger when you push to the main branch. 