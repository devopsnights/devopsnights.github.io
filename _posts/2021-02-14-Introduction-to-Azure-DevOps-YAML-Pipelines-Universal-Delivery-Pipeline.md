---
layout: post
title: Introduction to Azure DevOps YAML Pipelines - Universal Delivery Pipeline
published: true
tags: devops devopsnights yamlpipelines udp universaldeliverypipeline
---


In the past Thusday my friend Emmanuel Brandão and I started an open source  project called UDP - Universal Delivery Pipeline that has the purpose to create build and deployment templates to deploy every kind of technology (dotnet, node, terraform, Java, etc), everywhere (public and private clouds such as Azure, AWS, GCP, VMWare, bare metal, etc).

We are creating this project in lives on the [DevOps Nights channel](https://youtu.be/hIkwU3CnJzU) and you can follow the progress every Thursday at 10 PM (CET) =).

In the first live we created a basic template to build an dotnet core application. Here I'll describe the steps that we did in the live.

<iframe width="400" height="300" src="https://www.youtube.com/embed/hIkwU3CnJzU" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Creating a dotnet core "client" application and a YAML build 

We had create an standar webapp application in dotnet core to be the "client" of our templates. 

<script src="https://gist.github.com/wesleycamargo/dc48c73e5040c422b48176336779738a.js?file=newDotNetApp.ps1"></script>


To show the steps from the begining, we started creating an standard YAML with build tasks, without template.

<script src="https://gist.github.com/wesleycamargo/dc48c73e5040c422b48176336779738a.js?file=azure-pipelines-v1.yml"></script>

## Creating template

After check that we have a valid YAML able to build our application, we moved it to a first version of our template. It was in the same repo to keep the things simple in the begining.

This is how the file structure looks like:

<script src="https://gist.github.com/wesleycamargo/dc48c73e5040c422b48176336779738a.js?file=folderStructure.txt"></script>

Pay attention that we have two files in the root:

- azure-pipelines.yml
- template.yml

The file azure-pipelines.yml is the file that will consume the template.

<script src="https://gist.github.com/wesleycamargo/dc48c73e5040c422b48176336779738a.js?file=azure-pipelines.yml"></script>


The template.yml is the file that contains all the steps necessary to build our application.

<script src="https://gist.github.com/wesleycamargo/dc48c73e5040c422b48176336779738a.js?file=template.yml"></script>

These files are the result of what we did during the live. If you want to know how we achieve it, watch the video on the top of the post =].

You can see the code at this stage on this tag: https://github.com/devopsnights/UDP-Application/releases/tag/v0.1


