# Three-Tier-Web-App-AWS


## Overview
This project demonstrates a serverless three-tier architecture on AWS, using:
- **Frontend (Presentation Layer):** Amazon S3 + CloudFront
- **Backend (Logic Layer):** API Gateway + AWS Lambda
- **Database (Data Layer):** Amazon DynamoDB

The application retrieves user data based on `userId`.

## Architecture Diagram
```
User -> CloudFront -> S3 (Static Website)
     -> API Gateway -> Lambda (Backend Logic)
     -> DynamoDB (Database)
```

## Steps to Deploy

### 1️⃣ Frontend (S3 + CloudFront)
- Create an **S3 bucket** and upload your `index.html`, `style.css`, and `script.js` files.
- Set up **CloudFront** for global content delivery.
- Enable **Origin Access Control (OAC)** for secure access to S3.
- Set the **Default Root Object** to `index.html`.
- Copy the CloudFront domain and update `script.js` to use this URL.

### 2️⃣ Backend (API Gateway + Lambda)
- Create an **AWS Lambda function** to process API requests.
- Choose the appropriate runtime and write the function logic.
- Create an **API Gateway** (REST API) and integrate it with Lambda.
- Deploy API Gateway and copy the **Invoke URL**.

### 3️⃣ Database (DynamoDB)
- Create a **DynamoDB table** with `userId` as the partition key.
- Insert sample user data in **JSON format**.
- Update Lambda permissions to allow access to DynamoDB.

### 4️⃣ Connecting Everything
- Modify `script.js` to fetch data using API Gateway.
- Enable **CORS** in API Gateway and allow CloudFront's domain.
- Test the application by refreshing the CloudFront URL.

## Key AWS Features Used
✔ **S3** - Object storage for frontend files
✔ **CloudFront** - Content delivery network (CDN) for faster performance
✔ **API Gateway** - Manages API requests and connects to Lambda
✔ **AWS Lambda** - Serverless function for backend logic
✔ **DynamoDB** - NoSQL database for storing user data

🚀 **Now your serverless three-tier web app is live!**

