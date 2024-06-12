# Kidney-Disease-Detection-Classification-MLflow-DVC-AWS-Using-Deep-Learning-Models
### This repository consists of two main parts. In the first part, we apply deep learning to our classification task using various deep learning models to identify the best-performing model. In the second part, we focus on deploying this deep learning model to the cloud, enabling easy access for everyone. For deployment, we utilize a CI/CD pipeline and an EC2 instance server.

The AWS Cloud Deployment Part was followed from [@krishnaik06](https://github.com/krishnaik06) Sir's Youtube Channel and you can find that repository here [Kidney-Disease-Classification-Deep-Learning-Project](https://github.com/krishnaik06/Kidney-Disease-Classification-Deep-Learning-Project)

# Part-1: Kidney Disease Classification using Deep Learning Architectures
You can find these code file under the folder Part-1-DeepLearningArchitectures-CNN+ResNet18+SqueezeNet

## Dataset Overview:
https://www.kaggle.com/datasets/nazmul0087/ct-kidney-dataset-normal-cyst-tumor-and-stone

![image](https://github.com/Sivaramasaran2773/Kidney-Disease-Detection-using-Deep-Learning/assets/96780921/eb0a3061-7807-4b22-8607-f03b474a99c0)

## Methodology:

![image](https://github.com/Sivaramasaran2773/Kidney-Disease-Detection-using-Deep-Learning/assets/96780921/d9194f3f-6e95-4777-af0d-1c06428aa0b3)

## Simulation Architecture:
### Platform & Tools

### Library
- PyTorch

### Platform
- Kaggle

### Hardware
- P100 GPU acceleration

### Hyperparameters

- Optimizer: ADAM
- Learning Rate: 0.001
- Batch size: 32

### Training Parameters

- Epochs: 100
- Dropout Value: 0.5

## Best Model Results:
Out of the 3 models which have we have Implemented, ResNet18 have achieved an highest accuracy of 99.92%. You can see the Validation Loss and Accuracy plots along with the t-SNE plots below.

![image](https://github.com/Sivaramasaran2773/Kidney-Disease-Detection-using-Deep-Learning/assets/96780921/789b50bc-aee8-4312-a4d9-1289ca30c78a)

![image](https://github.com/Sivaramasaran2773/Kidney-Disease-Detection-using-Deep-Learning/assets/96780921/e3b023fa-3bc0-4f90-814a-06c853d5d066)


# Part-2: Deployment in AWS Cloud using CI/CD Pipeline in EC2
## User Interface:

![image](https://github.com/Sivaramasaran2773/Kidney-Disease-Detection-using-Deep-Learning/assets/96780921/27093667-00a7-4399-a808-cf2dbd60fb83)

![image](https://github.com/Sivaramasaran2773/Kidney-Disease-Detection-using-Deep-Learning/assets/96780921/aa337982-91d5-4175-a3c6-9a4ac1cb294d)


## Workflows

1. Update config.yaml
2. Update secrets.yaml [Optional]
3. Update params.yaml
4. Update the entity
5. Update the configuration manager in src config
6. Update the components
7. Update the pipeline 
8. Update the main.py
9. Update the dvc.yaml
10. app.py

# How to run?
### STEPS:

Clone the repository

```bash
https://github.com/Sivaramasaran2773/Kidney-Disease-Detection-using-Deep-Learning.git
```
### STEP 01- Create a conda environment after opening the repository

```bash
conda create -n kidney python=3.8 -y
```

```bash
conda activate kidney
```


### STEP 02- install the requirements
```bash
pip install -r requirements.txt
```

```bash
# Finally run the following command
python app.py
```

Now,
```bash
open up you local host and port
```

### DVC cmd

1. dvc init
2. dvc repro
3. dvc dag


## About MLflow & DVC

MLflow

 - Its Production Grade
 - Trace all of your expriements
 - Logging & taging your model


DVC 

 - Its very lite weight for POC only
 - lite weight expriements tracker
 - It can perform Orchestration (Creating Pipelines)



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
    - Save the URI: 566373416292.dkr.ecr.us-east-1.amazonaws.com/chicken

	
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

####
