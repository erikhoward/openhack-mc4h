# Challenge 1 - Deloy Azure API for FHIR and FHIR-Proxy (OSS)

## Introduction

Welcome to Challenge 1!

In this challenge, you will deploy both Azure API for FHIR (PaaS) and FHIR-Proxy (Open Source Software).

## Background
FHIR is at the center of our healthcare products at Microsoft. FHIR data support in MC4H solutions rests on two fundamental components: Azure API for FHIR and FHIR-Proxy. In MC4H architectures, Azure API for FHIR is at the nexus of FHIR data activity, and FHIR-Proxy acts as a checkpoint, filtering data and enforcing Role-Based Access Control (RBAC) at the FHIR resource level.

## Learning Objectives 
+ Understand the prerequisites for deploying Azure API for FHIR and FHIR-Proxy
+ Become familiar with the Azure API for FHIR and FHIR-Proxy deployment process

## Prerequisites 
To help you set up your environment, we provide install scripts that gather (and export) information necessary for the proper deployment and configuration of Azure API for FHIR and supporting Open Source Software (OSS) components.

Before you run these install scripts, it is crucial that you have the following permissions in your Azure environment (or the install will not work):

+ Azure Subscription Prerequisite: User must have rights to deploy resources at the Subscription scope (ie Contributor role or Owner role).
+ Azure Active Directory (AAD) Prerequisite: User must have Application Administrator (built-in RBAC role) rights for the AAD tenant they are deploying into.
  

## Getting Started
Deploying Azure API for FHIR. 
For this challenge, we will walk through these steps: 
- Login to Azure CLI (via the Portal or directly at shell.azure.com)
- Clone the FHIR-Starter repo 
- Execute the deployment scripts 
- Set up Postman 
- Test Authentication 

To begin the deployment process, click on the "Launch Azure Shell" button.

[![Launch Azure Shell](./media/launchcloudshell.png "Launch Cloud Shell")](https://shell.azure.com/bash?target="_blank")

Select Bash Shell as the operating environment.

## Step 1 - FHIR Service deployment 
  
- Navigate to the FHIR-Starter repo https://github.com/microsoft/fhir-starter in your browser, review the main Readme.md, and the [Readme.md](https://github.com/microsoft/fhir-starter/blob/main/scripts/Readme.md) in the ./scripts folder.  

- Clone the Repo in your Azure Cloudshell environment.  
    ```azurecli-interactive
    git clone https://github.com/microsoft/fhir-starter.git
    ```

- Change the working directory to the ```./fhir-starter/scripts``` directory in the repo.  
    ```azurecli-interactive
    cd ./fhir-starter/scripts
    ```

- Make the Bash scripts for deployment and setup executable.  
    ```azurecli-interactive
    chmod +x *.bash
    ```

- Execute the ```deployFhirStarter.bash``` script.  
    ```azurecli-interactive
    ./deployFhirStarter.bash
    ```

- Be certain to GENERATE the POSTMAN Env

__Note__  During the live MC4H OpenHack session, Resource Groups names will be assigned. If you are performing the OpenHack on your own, you can use any Resource Group name. 

## Step 2 - Set up Postman
Using the Upload / Download button in the Azure Cloushell interface, download the _$fhirServiceName.postman_environment.json_ file to your computer. 

Import the Postman Search Collection if you have not already done so. See https://microsoft.github.io/openhack-mc4h/Challenge-1.html for the collection download.

Test access to your FHIR Service 

_[Need help with Postman - try this](https://github.com/daemel/fhir-postman)_ 


## Step 3 - Proxy Setup  
- Navigate to the FHIR-Proxy repo https://github.com/microsoft/fhir-proxy in your browser. 
- Review the main Readme.md and the [Readme.md](https://github.com/microsoft/fhir-proxy/blob/main/scripts/Readme.md) in the ./scripts folder.  
    
- Clone the Repo in your Azure Cloudshell environment.  
    ```azurecli-interactive
    git clone https://github.com/microsoft/fhir-proxy.git
    ```

- Change the working directory to the ```./fhir-proxy/scripts``` directory in the repo.  
    ```azurecli-interactive
    cd ./fhir-proxy/scripts
    ```

- Make the Bash scripts for deployment and setup executable.  
    ```azurecli-interactive
    chmod +x *.bash
    ```

- Execute the ```deployfhirproxy.bash``` script.  
    ```azurecli-interactive
    ./deployfhirproxy.bash
    ```

- Be certain to GENERATE the POSTMAN Env

__Note__  During the live MC4H OpenHack session, Resource Groups names will be assigned. If you are performing the OpenHack on your own, you can use any Resource Group name. 

## Step 4 - Set up Postman with Proxy 
Using the Upload / Download button in the Azure Cloudshell interface, download the _$fhirServiceName.postman_environment.json_ file to your computer. 



## Challenge Success
+ Azure API for FHIR (PaaS) installed and available 
+ FHIR-Proxy (Open Source Software) installed and able to communicate with Azure API for FHIR
