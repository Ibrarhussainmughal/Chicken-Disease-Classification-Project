## Chicken Disease Classification Project
This project aims to classify chicken diseases using deep learning models.

### Workflows
  Update config.yaml
  Update secrets.yaml (Optional)
  Update params.yaml
  Update entity classes
  Update the configuration manager in src/config
  Update the components
  Update the pipeline
  Update main.py
  Update dvc.yaml

### How to Run?
####  Steps to Setup the Project

###   1- Clone the Repository
 git clone https://github.com/your-username/Chicken-Disease-Classification-Project.git
 cd Chicken-Disease-Classification-Project

###   2-  Create a Conda Environment
    conda create -n cnncls python=3.8 -y
    conda activate cnncls

### 3- Install the Required Dependencies
    pip install -r requirements.txt

### 4- Install the Required Dependencies
    pip install -r requirements.txt

### 5- Run the Application
    python app.py

### 6- Open the Application in Your Browser
* If running locally, open:
http://127.0.0.1:80
 * If deployed on a server, replace 127.0.0.1 with your server IP or domain name.


## DVC Commands
To manage data versioning using DVC (Data Version Control):
dvc init
dvc repro
dvc dag



## AWS CI/CD Deployment with GitHub Actions


### 1️⃣ Login to AWS Console
Make sure you have an AWS account and access to the AWS Management Console.


### 2️⃣ Create an IAM User for Deployment
Assign the following permissions:
* EC2 Access → For managing virtual machines.
* ECR (Elastic Container Registry) → To store Docker images.
      -Save the URI: 559050243996.dkr.ecr.eu-north-1.amazonaws.com/chicken

### 3️⃣ Create an ECR Repository
To store and manage your Docker images.


### 4️⃣ Launch an EC2 Instance (Ubuntu)
This will host your application.


### 5️⃣ Install Docker on the EC2 Instance
sudo apt-get update -y
sudo apt-get upgrade -y
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo usermod -aG docker ubuntu
newgrp docker


### 6️⃣ Configure EC2 as a Self-Hosted Runner

GitHub → Your Repository → Settings → Actions → Runners → New Self-Hosted Runner
Follow the instructions to connect your EC2 instance.

### 7️⃣ Setup GitHub Secrets
In GitHub Actions → Repository Secrets, add:
AWS_ACCESS_KEY_ID=
AWS_SECRET_ACCESS_KEY=
AWS_REGION= eu-north-1
AWS_ECR_LOGIN_URL=
ECR_REPOSITORY_NAME = simple-app



## Azure CI/CD Deployment with GitHub Actions

 ### 1️⃣ Build and Push the Docker Image
 docker build -t chickenapp.azurecr.io/chicken:latest .
 docker login chickenapp.azurecr.io
 docker push chickenapp.azurecr.io/chicken:latest


## 2️⃣ Deploy the Application
* Build the Docker image.
* Push it to Azure Container Registry.
* Launch the Web App Server in Azure.
* Pull the Docker image to the server and run it.
