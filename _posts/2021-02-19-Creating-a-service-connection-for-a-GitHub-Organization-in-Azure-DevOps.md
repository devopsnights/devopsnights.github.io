---
layout: post
title: Creating a service connection for a GitHub Organization in Azure DevOps
published: true
tags: devops devopsnights yamlpipelines udp universaldeliverypipeline github serviceconnection
---

In the second live for create the UDP - Universal Delivery Pipeline, we showed how to create a Service Connection for your GitHub Organization in Azure DevOps. In this post I'll walk trough those steps.

<iframe width="640" height="360" src="https://www.youtube.com/embed/kJ1JoZrrwMU" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## The intuitive way doesn't work =/

There is no explicit way to do this. Although GitHub is an option in Service Connections, it only links your personal account to Azure DevOps, so if you need to link your GitHub Organization it won't work.


<img src="../images/posts/2021-02-19-Creating-a-service-connection-for-a-GitHub-Organization-in-Azure-DevOps/githubspn.png" width="400">

*There is an option to link, but...*

<img src="../images/posts/2021-02-19-Creating-a-service-connection-for-a-GitHub-Organization-in-Azure-DevOps/personalrepos.png" width="600">


*Where is my org repo?*

## Linking the GitHub Organization

The option to link your organization is under of all your personal repositories. So you need to go all the way to the to bottom, and them select an specific connection:

<img src="../images/posts/2021-02-19-Creating-a-service-connection-for-a-GitHub-Organization-in-Azure-DevOps/specificconnection.png" width="600">


And then it will open a screen with the option to install the GitHub App:

<img src="../images/posts/2021-02-19-Creating-a-service-connection-for-a-GitHub-Organization-in-Azure-DevOps/installghapp.png" width="600">


It will redirect you to a GitHub page to choose your organization:

<img src="../images/posts/2021-02-19-Creating-a-service-connection-for-a-GitHub-Organization-in-Azure-DevOps/githubChooseOrg.png" width="600">


Now you need to give some credentials and after this you will have a service connection ready to use!

<img src="../images/posts/2021-02-19-Creating-a-service-connection-for-a-GitHub-Organization-in-Azure-DevOps/serviceconnection.png" width="600">


If you want more details, you can follow the video on the top of the post.

I hope it can be helpful and see you on the next post!


---

The UDP - Universal Delivery Pipeline is a set of YAML Pipelines templates that has the purpose to create build and deployment templates to deploy every kind of technology (dotnet, node, terraform, Java, etc), everywhere (public and private clouds such as Azure, AWS, GCP, VMWare, bare metal, etc).

We are creating this project in lives on the [DevOps Nights channel](https://youtu.be/hIkwU3CnJzU) and you can follow the progress every Thursday at 10 PM (CET) =).

You can see the code and contribute on our GitHub [tag](https://github.com/devopsnights/UDP-Application). 




