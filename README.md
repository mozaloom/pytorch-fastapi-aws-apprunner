[![CI](https://github.com/mozaloom/pytorch-fastapi-aws-apprunner/actions/workflows/cicd.yml/badge.svg)](https://github.com/mozaloom/pytorch-fastapi-aws-apprunner/actions/workflows/cicd.yml) [![CI/CD Pipeline](https://github.com/mozaloom/pytorch-fastapi-aws-apprunner/actions/workflows/main.yml/badge.svg)](https://github.com/mozaloom/pytorch-fastapi-aws-apprunner/actions/workflows/main.yml)

# FastAPI + PyTorch Inference API

This project provides a simple image classification API using **FastAPI** and **PyTorch**, containerized with **Docker** and optionally deployed using **AWS App Runner**.

**Live Demo:** [Access the deployed service](https://pspcyz4qxx.us-east-1.awsapprunner.com)

---

## Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/mozaloom/pytorch-fastapi-aws-apprunner.git
cd pytorch-fastapi-aws-apprunner
```

### 2. Build the Docker Image
```bash
docker build -t pytorch .
```

### 3. Run the Docker Container
First, locate your image ID:
```bash
docker image ls
```
Then, run the container (replace `<image_id>` with your actual ID):
```bash
docker run -p 127.0.0.1:8080:8080 <image_id>
```

---

## Usage

### Option A: Run Locally
Start the FastAPI app:
```bash
python app.py
```

### Option B: Upload and Classify an Image
1. Navigate to the Swagger UI: `http://localhost:8080/docs`
2. Use the `POST /predict/` endpoint to upload an image (e.g., a cat 🐱).
3. View the classification results in the response.

### Option C: Deploy to AWS App Runner (Free Tier)
1. Push your Docker image to AWS ECR.
2. Use [AWS App Runner](https://docs.aws.amazon.com/apprunner/latest/dg/what-is-apprunner.html) to deploy the service.

---

## Swagger UI Screenshots

| Step | Screenshot |
|------|------------|
| 1. Launch Swagger UI | ![Step 1](https://user-images.githubusercontent.com/58792/131587003-f5667c28-7cbe-402e-8795-f32a6ca9a4d1.png) |
| 2. Upload Image | ![Step 2](https://user-images.githubusercontent.com/58792/131587286-341e795c-76dc-46a1-8ee9-528134410935.png) |
| 3. Receive Prediction | ![Step 3](https://user-images.githubusercontent.com/58792/131587004-198ad6d5-2197-4de5-a6dd-4eb3c41e675e.png) |
| 4. Final Output | ![Step 4](https://user-images.githubusercontent.com/58792/131587005-866b0974-63d7-4fed-abf2-9c634721669f.png) |

---

## Verify Swagger is Working
Visit:
```
http://localhost:8080/docs 
```
Or if deployed:
```
https://<your-app-runner-url>/docs
```

---

## References

- Adapted from the [official PyTorch REST API tutorial](https://pytorch.org/tutorials/intermediate/flask_rest_api_tutorial.html)

