✅ Final CI/CD GitHub Actions Pipeline

🎯 What it does:
Builds frontend & backend Docker images
Tags and pushes both with ${{ github.sha }}
Runs Terraform:
Initializes and applies terraform/backend
Initializes and applies terraform/infrastructure
Deploys the app to EC2 via Ansible using the SHA-based image tags

🗂️ Repository Structure (Expected)

.
├── .github/
│   └── workflows/
│       └── deploy.yml           # ← GitHub Actions workflow
├── terraform/
│   ├── backend/
│   │   └── main.tf              # Terraform backend config (S3)
│   └── infrastructure/
│       └── main.tf              # EC2 instance, security groups
├── ansible_ec2_setup/
│   ├── inventory.ini
│   ├── playbook.yml             # Modified to use image_tag variable
│   └── templates/
│       └── docker-compose.yml.j2
├── frontend/
├── backend/
