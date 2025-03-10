# NetworkCA1
Overview
This project showcases an automated deployment pipeline for a containerized web application hosted on an Azure Virtual Machine. The deployment process integrates Terraform for infrastructure provisioning, Ansible for configuration management, and GitHub Actions for continuous deployment.

Architecture
The deployment pipeline consists of the following components:

Terraform: Provisions the Azure infrastructure, including virtual machines, networking, and security settings.
Ansible: Automates VM configuration, ensuring necessary dependencies such as Docker are installed.
GitHub Actions: Manages continuous deployment by building, testing, and deploying the application whenever changes are pushed to the repository.
Prerequisites
Ensure the following are installed before running this project:

Terraform
Ansible
Docker
An Azure account with necessary permissions
A GitHub repository with Actions enabled
Setup Instructions
1. Clone the Repository
sh
Copy
Edit
git clone https://github.com/your-repo.git
cd your-repo
2. Configure Terraform
Update the terraform.tfvars file with your Azure credentials and desired configurations, then run:

sh
Copy
Edit
terraform init
terraform apply
3. Run Ansible Playbook
Once Terraform provisions the VM, configure it using Ansible:

sh
Copy
Edit
ansible-playbook -i inventory.ini setup.yml
4. Configure GitHub Actions
Ensure your GitHub repository has the following secrets set:

AZURE_CREDENTIALS (for Azure authentication)
DOCKER_USERNAME and DOCKER_PASSWORD (for container registry access)
Push changes to trigger the CI/CD pipeline:

sh
Copy
Edit
git add .
git commit -m "Initial commit"
git push origin main
Workflow
Terraform provisions the required Azure infrastructure.
Ansible configures the VM by installing necessary dependencies.
GitHub Actions automates the build, test, and deployment process.
The application is deployed and accessible via the configured domain or IP.
Contributing
Contributions are welcome! Feel free to submit issues and pull requests to enhance the project.









