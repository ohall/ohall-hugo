+++
date = "2016-02-02T08:33:38-05:00"
tags = [
    "devops",
    "cloud"
]
categories = [
    "DevOps",
    "cloud"
]
title = "Intro to OneOps"
+++
![OneOps Banner](http://www.businesscloudnews.com/files/2016/01/Walmart-OneOps.jpg)

#OneOps

[WalmartLabs](http://www.walmartlabs.com/) has recently open sources their cloud management platform [OneOps](http://www.walmartlabs.com/2016/01/oneops-now-available/).  You can dive into the documentation [here](http://oneops.com/) or examine the source code [here](https://github.com/oneops/). As a OneOps user, I'd like to offer a quick spin around OneOps and an overview of what it does.

# What is it?

OneOps allows you to configure VM clusters using a GUI or a RESTful API in a way that is cloud provider agnostic. Meaning, you can use cores from AWS or any other cloud provider or a private cloud.

Configurations and environment settings are maintained in OneOps and can easily be ported between cloud providers.

# How does it work?
OneOps has a few basic organizational concepts which you'll see repeatedly.

## Organization:
An Organization is group of users, clouds and assemblies that share settings, quotas and permissions. From the Organization view you can see a summary of users, clouds, assemblies, notifications, ongoing deployments, VM health statistics and reports for all cores in the Organization that includes allocation and quotas.

## Assembly:
This essentially a project. The Assembly consists of 3 phases. __Design__, __Transition__, __Operate__.

## Design:
The Design is basically the template for how your VM cluster will be configured.

Think of a design as a prototype which will be inherited in the Transition then instantiated in an environment

A design consists of one or more Platforms for which you'll configure the prototype in the design phase. 

#### Platform 

The Platform represents a VM cluster. A Design will contain one or more. For example, you can have a design that contains just a backend server OR it could contain server, database and apache components, depending how you want to organize things. Platforms can be built from scratch, but is generally built from a [Pack](http://oneops.github.io/user/references/#platform-packs) which is a set of preconfigured Components.

#### Components 

Components represent configurations and installed software and files on the VMs. Some examples include:

 - Node
 - Java
 - SSH keys
 - Load Balancer
 - Redis DB
 - Mounted volumes
 - Cron jobs
 - File

The NodeJS component for example installs a node binary on your cluster, and includes fields for the user to define, version, install location, log file location, etc.

Another example is a File component which allows to you place a file in an arbitrary location on your cluster and provides a field for and execute command. You might use this to execute a shell script on your cluster.

![](https://raw.githubusercontent.com/oneops/oneops.github.io/master/assets/local/images/design-graph.png)

## Transition:
In the transition phase you will: Configure environments. (PROD, STAGE, QA, etc.) Determine which clouds our platforms will be deployed on in those environments. Set environment specific configurations. It is also in the transition phase that you deploy your platforms.

When you create an environment you'll "Pull" your design into it in order to set all the configurations for that environment. In the Transition tab in the GUI you'll see the same fields as in Design, pre-populated with the values set in the Design. However you can change any of those values and that change will be reflected in this environment. This change will be overwritten next time you pull a design change UNLESS you LOCK the field.

![lock](https://raw.githubusercontent.com/oneops/oneops.github.io/master/assets/local/images/lock.png)

Once you've configured your environment, you'll commit the changes and deploy them. This phase actually provisions and configures your VMs in real life on real machines. All components will be deployed in the initial deployment. On subsequent deployments, on components that have been changed or explicitly "Touched" will be deployed.

You can touch a component any time from its bread crumb menu.
![transition](https://raw.githubusercontent.com/oneops/oneops.github.io/master/assets/local/images/GettingStartedEC2CommitAndDeploy.png)

## Operate:
The Operate phase is how you view monitor and control your clusters now that they are active. You can see the health of individual computes, stop, repair or replace them. you can also see vital information about your VMs including IPs and host names.

Drilling down in a component in the Operate view will show all the computes it is installed on and a summary of attributes. You can select a compute and see the state of that component as it exists on that compute. This view shows the configuration, notifications, logs and some actions you can execute on the component.

![operate](https://raw.githubusercontent.com/oneops/oneops.github.io/master/assets/local/images/assess-health-operate.png)

## API
There will be a lot of cases where you'll want to integrate OneOps with other components in the build/deploy pipeline or simple script oft repeated operations like deployments. For this, OneOps provides a [RESTful API](http://oneops.github.io/developer/references/#oneops-api-documentation). We'll go into more detail about OneOp API usage in another post, but suffice it to say that as your usage of OneOps increases, you'll find yourself increasingly relying on this feature to integrate OneOps into your pipeline. OneOps also provides a [Ruby CLI](http://oneops.github.io/admin/key-concepts/#cli) to the API, which you can install. 

## Conclusion
### The good
OneOps is a powerful cloud management tool that you can experiment with today. Right off the shelf it provides a nice end to end solution for configuring and managing a range of cloud solutions. Standing up VM clusters with simple preset configurations is easy and viewing and maintaining VM health can be done with just a few clicks.
### The not as good
The operations executed by OneOps are often complex and debugging failures can be difficult. [The OneOps team](https://oneops.slack.com/) is incredibly responsive, but at times it can feel like there is a little black magic going on behind the scenes. The version control scheme for components and configurations and be opaque.  There are often times when you'd like to just use versioned files from Github or the like and while it's possible, it's not always obvious how to do it.  
### The future
I'm glad that now that OneOps is open source, the response to my complaints will be "File a PR!". I think community involvement will make an already powerful tool even more useful and user friendly.
