# PyTorch FastAPI Image Classification API

[![CI](https://github.com/mozaloom/pytorch-fastapi-aws-apprunner/actions/workflows/cicd.yml/badge.svg)](https://github.com/mozaloom/pytorch-fastapi-aws-apprunner/actions/workflows/cicd.yml) [![CI/CD Pipeline](https://github.com/mozaloom/pytorch-fastapi-aws-apprunner/actions/workflows/main.yml/badge.svg)](https://github.com/mozaloom/pytorch-fastapi-aws-apprunner/actions/workflows/main.yml)

A containerized image classification API built with FastAPI and PyTorch, ready for deployment on AWS App Runner.

**[Live Demo](https://pspcyz4qxx.us-east-1.awsapprunner.com)**

## Quick Start

### Local Setup

```bash
# Clone repository
git clone https://github.com/mozaloom/pytorch-fastapi-aws-apprunner.git
cd pytorch-fastapi-aws-apprunner

# Run with Docker
docker build -t pytorch-api .
docker run -p 8080:8080 pytorch-api

# Or run directly
pip install -r requirements.txt
python app.py
```

### Using the API

1. Access the Swagger UI: `http://localhost:8080/docs`
2. Use the `POST /predict/` endpoint to upload an image
3. View classification results in the response

## Deployment

### AWS App Runner Deployment

1. Push your Docker image to AWS ECR
2. Create a new service in AWS App Runner using your ECR image
3. Access your deployed API at the provided AWS App Runner URL

## Project Structure

```
.
├── app.py                    # FastAPI application entry point
├── main.py                   # Core application logic
├── Dockerfile                # Container configuration
├── requirements.txt          # Dependencies
├── imagenet_class_index.json # Classification labels
├── mylib/                    # Helper library
└── utils/                    # Utility scripts
```

## Screenshots

![Swagger UI Interface](https://user-images.githubusercontent.com/58792/131587003-f5667c28-7cbe-402e-8795-f32a6ca9a4d1.png)

## References

Based on the [PyTorch REST API tutorial](https://pytorch.org/tutorials/intermediate/flask_rest_api_tutorial.html)