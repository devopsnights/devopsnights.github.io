---
layout: post
title: Introduction to Azure DevOps YAML Pipelines - Universal Delivery Pipeline
published: true
tags: devops devopsnights yamlpipelines udp universaldeliverypipeline
---


In the past Thusday my friend Emmanuel Brandão and I started an open source  project called UDP - Universal Delivery Pipeline that has the purpose to create build and deployment templates to deploy every kind of technology (dotnet, node, terraform, Java, etc), everywhere (public and private clouds such as Azure, AWS, GCP, VMWare, bare metal, etc).

We are creating this project in lives on the [DevOps Nights channel](https://youtu.be/hIkwU3CnJzU) and you can follow the progress every Thursday at 10 PM (CET) =).

In the first live we created a basic template to build an dotnet core application. Here I'll describe the steps that we did in the live.

<iframe width="968" height="545" src="https://www.youtube.com/embed/hIkwU3CnJzU" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Creating a dotnet core "client" application and a YAML build 

We had create an standar webapp application in dotnet core to be the "client" of our templates. 

```cli
dotnet new webapp
```

To show the steps from the begining, we started creating an standard YAML with build tasks, without template.

```yaml
trigger:
- main

pool:
  vmImage: 'ubuntu-latest'

steps:

- task: DotNetCoreCLI@2
  inputs:
    command: 'build'

- task: DotNetCoreCLI@2
  inputs:
    command: 'publish'
    publishWebProjects: true
    arguments: '--output $(Build.ArtifactStagingDirectory)'

- task: PublishBuildArtifacts@1
  inputs:
    PathtoPublish: '$(Build.ArtifactStagingDirectory)'
    ArtifactName: 'drop'
    publishLocation: 'Container'
```
<!-- 
<script src="http://gist-it.appspot.com/https://github.com/wesleycamargo/UDP-Application/blob/98b0aafa737b006d4dd0d9bbc5a529516df470c7/azure-pipelines.yml"></script> -->

## Creating template

After chevk that we have a valid YAML able to build our application, we moved it to a first version of our template. It was in the same repo to keep the things simple in the begining.



