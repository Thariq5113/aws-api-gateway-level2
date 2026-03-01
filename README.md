# aws-api-gateway-level2

# AWS API Gateway – Level 2 (Terraform Implementation)

##  Project Overview

This project implements an AWS API Gateway using Terraform (Infrastructure as Code).

The API Gateway exposes three routes:

1. `/json/{proxy+}` → Proxies requests to JSONPlaceholder API  
2. `/weather` → Fetches weather data from Open-Meteo API  
3. `/countries/{name}` → Fetches country details from RestCountries API  

All resources are provisioned using Terraform.

# Invoke URL 

invoke_url = "https://pwd8zruou0.execute-api.ap-south-1.amazonaws.com/v1"

# Prerequisites

Before deploying this project, ensure you have:

- AWS Account
- IAM User with AdministratorAccess
- AWS CLI installed and configured (`aws configure`)
- Terraform installed

# Deployment Steps

 1. Initialize Terraform
 2. Preview infrastructure changes ('terraform init')
 3. Deploy infrastructure ('terraform plan')
 4. Type `yes` when prompted ('terraform apply')
 5. Copy the generated `invoke_url` from the output.

# Testing the APIs

## 1️⃣ JSON Proxy API
  curl.exe https://pwd8zruou0.execute-api.ap-south-1.amazonaws.com/v1/json/posts/2
  Expected Output: JSON post data from JSONPlaceholder.
## 2️⃣ Weather API
  curl.exe "https://pwd8zruou0.execute-api.ap-south-1.amazonaws.com/v1/weather?latitude=12&longitude=77&hourly=temperature_2m"
  Expected Output: Hourly weather forecast data.
## 3️⃣ Countries API
  curl.exe https://pwd8zruou0.execute-api.ap-south-1.amazonaws.com/v1/countries/india
  Expected Output: Country details for India.

# Terraform Resources Created

- aws_api_gateway_rest_api
- aws_api_gateway_resource
- aws_api_gateway_method
- aws_api_gateway_integration
- aws_api_gateway_deployment
- aws_api_gateway_stage

All infrastructure is fully automated using Terraform.

# Screenshots

Screenshots of the following are included in the `screenshots/` folder:
- Terraform init
- Terraform apply
- API Gateway console (Resources view)
- Stage `v1`
- Curl output for each route

# Tear Down / Destroy Infrastructure

To delete all AWS resources created by Terraform ('terraform destroy')
Type `yes` when prompted.
This ensures no AWS charges continue after completion.

# Key Concepts Demonstrated

- Infrastructure as Code (IaC)
- AWS API Gateway automation
- HTTP_PROXY integrations
- Path parameters (`{proxy+}`, `{name}`)
- Query string parameter mapping
- Terraform deployment lifecycle

# Author

Thariq T
DevOps Assignment – Level 2







