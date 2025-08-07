# DevOps Internship Task 3 – Terraform + Docker

## 🚀 Objective
Provision a local Docker container using **Terraform**.

## 🛠 Tools Used
- Terraform
- Docker

## 📁 Files
- `main.tf` – Terraform configuration file to provision an NGINX container
- Terraform logs (init, plan, apply, destroy)

## 📦 Resources Provisioned
- **Docker Image**: `nginx:latest`
- **Docker Container**: Accessible at `localhost:8080`

## 🔧 Steps to Run

```bash
# 1. Initialize Terraform
terraform init

# 2. Check what will be created
terraform plan

# 3. Apply changes (create container)
terraform apply

# 4. Access the container
# Visit http://localhost:8080 in your browser

# 5. Destroy the container when done
terraform destroy
```
## 📚 Key Learnings
- Infrastructure as Code (IaC)
- Using Terraform Docker provider
- Managing state with Terraform
