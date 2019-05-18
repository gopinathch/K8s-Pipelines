# Kubernetes - Azure Pipelines
This repository demonstrates how to use Azure Pipelines to deploy containerized application to any Kubernetes cluster. 

We will start with how to confgure CI/CD pipeline using Azure Pipelines to Azure Kubernetes Service (AKS) and expand to any Kubernetes cluster.

You can learn more about [Azure Pipelines documentation](https://docs.microsoft.com/en-us/azure/devops/pipelines/languages/aks-template?view=azure-devops).

## Prerequistes

Below are the key pre-requisites:

* Any container based application with Dockerfile, you can fork this repo in GitHub
* Azure Subscription with an existing Azure Kubernetes Cluster
* Azure Container Registry


## Configuring CI/CD Pipeline 

First you need a container based application available for configuring CI/CD pipeline targeting to Kubernetes. Any language and any framework is fine - you just need a Dockerfile in your repo which can build the container image.

To get started easily you can fork this repo to try out and learn. You need to install and configure [Azure Pipelines application from GitHub marketplace](https://github.com/marketplace/azure-pipelines) on to this repo - it is completely free.

1) Now you can start creating a new pipeline, select a repository with Dockerfile - you can use the forked repo
2) Azure Pipeline analyses the repository and suggests the right set of Yaml templates – so you don’t need to figure it out. For example, for this repo it identified that the repository is a Nodejs application and a Dockerfile, so suggests you just to do CI (Docker) as well as CI+ CD (Deploy to AKS) templates.
3) Once you select AKS template, Azure Piplines will take cluster name, container registry and namespace as inputs to configure the Pipeline. These are the only inputs you need to provide for configuring the pipeline - remaining all image name and port will be autofilled in.
4) Azure Pipeline will now configure pipeline and auto create yml files required for the pipeline including Kubernetes manifest yml files for deploying to the cluster. All the files are committed to the code repo – so you get full configuration as code. You just need to click Save and Run.

That’s it, as you can see, you just need 4 steps to configure a pipeline for AKS cluster, once you click save and run – it will commit all the code and trigger the pipeline.



