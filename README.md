

Overview
This project showcases an automated deployment pipeline for a containerized web application hosted on an Azure Virtual Machine. The deployment process utilizes Terraform for infrastructure setup, Ansible for configuration management, and GitHub Actions for continuous deployment.

Architecture
The deployment pipeline consists of the following components:

Terraform: Provisions the Azure infrastructure, including virtual machines, networking, and security settings.
Ansible: Automates the configuration of the VM, ensuring required dependencies like Docker are installed.
GitHub Actions: Manages continuous deployment by building, testing, and deploying the application whenever changes are pushed to the repository.
Prerequisites
Before setting up this project, ensure you have the following installed:

Terraform
Ansible
Docker
An active Azure account with the required permissions
A GitHub repository with Actions enabled
Setup Instructions
1. Clone the Repository
sh
Copy
Edit
git clone https://github.com/your-repo.git
cd your-repo
2. Configure Terraform
Modify the terraform.tfvars file to include your Azure credentials and preferred configurations.

sh
Copy
Edit
terraform init
terraform apply
3. Run Ansible Playbook
Once Terraform completes provisioning, use Ansible to configure the virtual machine:

sh
Copy
Edit
ansible-playbook -i inventory.ini setup.yml
4. Configure GitHub Actions
Ensure your GitHub repository contains the following secrets:

AZURE_CREDENTIALS (for authentication with Azure)
DOCKER_USERNAME and DOCKER_PASSWORD (for container registry access)
Push changes to trigger the CI/CD pipeline:

sh
Copy
Edit
git add .
git commit -m "Initial commit"
git push origin main
Workflow
Terraform provisions the necessary Azure infrastructure.
Ansible configures the VM by installing required dependencies.
GitHub Actions automates the application's build, test, and deployment.
The deployed application becomes accessible through the designated domain or IP.
Contributing
Contributions are welcome! Feel free to submit issues or pull requests to enhance the project.
