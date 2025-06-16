## The Bingo App Deployment project using Jenkins, SonarQube, and Trivy! 

# Jenkins, SonarQube, and Trivy Setup

This repository contains the configuration and setup for a project that integrates Jenkins, SonarQube, and Trivy for CI/CD and security scanning. The project use Docker for containerization and Terraform for infrastructure management.

## Prerequisites

Before getting started, ensure you have the following installed:

1. Jenkins installation on Ubuntu 
2. Install Docker &  SonarQube  as container in the EC2 Instance 
3. Install Trivy on the Instance
4. Terraform Installation
5. Install kubectl
6. Install AWS CLI 
7. eksctl installation 

## Setup and Installation

### 1. Clone the Repository

Start by cloning this repository to your local machine:

```bash
git clone <https://github.com/lengockieuanh/nt548-terraform-github-actions.git>
cd nt548-jenkins-sonarqube-trivy
```

### 2. Build Docker Containers

Run the following command to build the Docker containers for Jenkins, SonarQube, and any other necessary services:

```bash
docker-compose up --build
```

This will build and start the services defined in the `docker-compose.yml`.

### 3. Jenkins Setup

1. **Jenkins URL**: After starting the Docker container, Jenkins should be available at `http://localhost:8080`. 
2. **Unlock Jenkins**: To unlock Jenkins, find the initial password by running the following command:

   ```bash
   docker exec -it <jenkins_container_name> cat /var/jenkins_home/secrets/initialAdminPassword
   ```

3. Follow the setup wizard to complete the Jenkins setup.

### 4. SonarQube Setup

1. **SonarQube URL**: SonarQube will be available at `http://localhost:9000`.
2. Login with the default credentials:
   - Username: `admin`
   - Password: `admin`

   Follow the SonarQube setup instructions to configure your first project.

### 5. Trivy Setup

Trivy is used for container security scanning. To use Trivy, you can run the following commands:

1. Scan a Docker image for vulnerabilities:

   ```bash
   trivy image <image-name>
   ```

### 6. Running the Application

If you want to run the application, use the following commands:

1. Install dependencies:

   ```bash
   npm install
   ```

2. Run the development server:

   ```bash
   npm run dev
   ```

   The application will be available at `http://localhost:3000`.

### 7. Terraform Setup (Optional)

If you wish to manage infrastructure using Terraform, you can run the following commands to initialize and apply the Terraform configuration:

```bash
cd Terraform
terraform init
terraform apply
```



