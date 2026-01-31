# AWS Event-Driven Serverless Project

## Project Overview
This project demonstrates an **event-driven serverless workflow** on AWS. An object uploaded to an Amazon S3 bucket automatically triggers an AWS Lambda function. The architecture was first validated manually to understand service interactions, and then codified using **CloudFormation** to make the infrastructure repeatable and version-controlled.

The project highlights **event-driven design**, **IAM permissions**, **CloudWatch monitoring**, and **Infrastructure as Code (IaC)** principles.

---

## Architecture Flow
1. Upload a file to the S3 bucket (event source).  
2. S3 triggers the Lambda function (compute).  
3. Lambda processes the event and logs output to CloudWatch (observability).  
4. IAM roles and permissions ensure secure interactions between services.  

---

## AWS Services Used
- **Amazon S3** – object storage and event source  
- **AWS Lambda** – serverless compute function triggered by events  
- **AWS CloudFormation** – defines and deploys the infrastructure as code  
- **AWS IAM** – manages permissions and security  
- **Amazon CloudWatch** – logs and monitors function execution  

---

## Infrastructure as Code (IaC)
The final architecture is codified using a CloudFormation template that provisions:

- An S3 bucket with event notifications  
- A Lambda function  
- IAM execution roles for secure Lambda execution  
- Lambda invoke permissions to allow S3 to trigger the function  

> Note: The infrastructure was first deployed manually to validate behavior before codifying it in CloudFormation.

---

## Challenges & Lessons Learned
- IAM policy validation errors due to incorrect versions or ARNs  
- CloudFormation property case sensitivity (`Event` vs `event`)  
- Lambda invoke permissions must exist before S3 notifications  
- S3 bucket names must be globally unique  
- Some CloudFormation failures required stack deletion and redeployment  

These challenges gave insight into **real-world cloud infrastructure debugging and deployment**.

---

## Future Improvements
- Persist S3 object metadata using DynamoDB  
- Add environment variables to Lambda for configuration flexibility  
- Refine IAM policies with strict least-privilege access  
- Expand monitoring with CloudWatch dashboards and alarms  

---

## Key Cloud Concepts Demonstrated
- **Event-Driven Infrastructure:** Reacts automatically to events like S3 uploads  
- **Infrastructure as Code (IaC):** Deploys resources in a repeatable, version-controlled way  
- **Compute:** Lambda functions for serverless processing  
- **Storage & Databases:** S3 for persistent object storage  
- **Networking & Security:** IAM roles control access between services  
- **Monitoring & Observability:** CloudWatch logs and metrics track system health  
- **Messaging & Event Systems:** S3 event notifications trigger compute asynchronously  

---

## Summary
This project shows practical experience in **building AWS serverless, event-driven architectures**. It demonstrates an understanding of **security, monitoring, and infrastructure management**, as well as the ability to codify and maintain infrastructure using **CloudFormation**.
