# End-to-End Text Summarizer

This repository contains an end-to-end text summarization project, leveraging state-of-the-art NLP techniques to summarize long-form text efficiently. The project is modular, scalable, and designed for seamless deployment.

## Table of Contents
- [Features](#features)
- [Folder Structure](#folder-structure)
- [Installation](#installation)
- [Usage](#usage)
- [Configuration](#configuration)
- [Docker Support](#docker-support)
- [AWS CICD Deployment with GitHub Actions](#aws-cicd-deployment-with-github-actions)
- [License](#license)

## Features
- **Customizable text summarization**: Supports various text lengths and summarization parameters.
- **End-to-end pipeline**: From preprocessing to generating summaries.
- **Dockerized Deployment**: Easy deployment using Docker.
- **Configurable Parameters**: Flexible settings via a YAML configuration file.
- **Modular Codebase**: Easily extendable for further development.

## Folder Structure
```
.
├── .github/workflows  # GitHub workflows for CI/CD
├── config             # Configuration files
├── research           # Research and exploration notebooks
├── src/textSummarizer # Core modules for text summarization
├── .gitignore         # Git ignore rules
├── Dockerfile         # Dockerfile for containerization
├── LICENSE            # License file
├── README.md          # Project documentation
├── app.py             # Application entry point
├── main.py            # Main pipeline script
├── params.yaml        # Parameter configuration file
├── requirements.txt   # Python dependencies
├── setup.py           # Setup script for packaging
├── template.py        # Template script for new modules
```

## Installation
### Prerequisites
- Python 3.8+
- pip
- Docker (optional)

### Steps
1. Clone the repository:
   ```bash
   git clone https://github.com/FAbdullah17/End-to-End-Text-Summarizer.git
   cd End-to-End-Text-Summarizer
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. (Optional) Install the package:
   ```bash
   python setup.py install
   ```

## Usage
### Running the Application
Run the pipeline using the following command:
```bash
python main.py
```

### Using the Web App
Start the application:
```bash
python app.py
```
Access the app at `http://127.0.0.1:5000` in your web browser.

## Configuration
Update the `params.yaml` file to configure the model and other settings:
```yaml
text_length: 1000
summary_length: 150
model_name: bert-based-summarizer
```

## Docker Support
### Build the Docker Image
```bash
docker build -t text-summarizer .
```

### Run the Docker Container
```bash
docker run -p 5000:5000 text-summarizer
```

# AWS-CICD-Deployment-with-Github-Actions

## 1. Login to AWS console.

## 2. Create IAM user for deployment

	#with specific access

	1. EC2 access : It is virtual machine

	2. ECR: Elastic Container registry to save your docker image in aws


	#Description: About the deployment

	1. Build docker image of the source code

	2. Push your docker image to ECR

	3. Launch Your EC2 

	4. Pull Your image from ECR in EC2

	5. Lauch your docker image in EC2

	#Policy:

	1. AmazonEC2ContainerRegistryFullAccess

	2. AmazonEC2FullAccess

	
## 3. Create ECR repo to store/save docker image
    - Save the URI: 566373416292.dkr.ecr.us-east-1.amazonaws.com/text-s

	
## 4. Create EC2 machine (Ubuntu) 

## 5. Open EC2 and Install docker in EC2 Machine:
	
	
	#optinal

	sudo apt-get update -y

	sudo apt-get upgrade
	
	#required

	curl -fsSL https://get.docker.com -o get-docker.sh

	sudo sh get-docker.sh

	sudo usermod -aG docker ubuntu

	newgrp docker
	
# 6. Configure EC2 as self-hosted runner:
    setting>actions>runner>new self hosted runner> choose os> then run command one by one


# 7. Setup github secrets:

    AWS_ACCESS_KEY_ID=

    AWS_SECRET_ACCESS_KEY=

    AWS_REGION = us-east-1

    AWS_ECR_LOGIN_URI = demo>>  566373416292.dkr.ecr.ap-south-1.amazonaws.com

    ECR_REPOSITORY_NAME = simple-app

 
 ## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

