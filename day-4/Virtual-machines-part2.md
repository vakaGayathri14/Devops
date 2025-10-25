Virtual Machines Part-2:

This is typically “Virtual Machines Part Two.” In the previous day, we talked about virtual machines — the evolution of virtual machines, what is a server, what is a physical server, how a physical server is different from a virtual machine, what is the concept that allows you to create virtual machines — and we also looked at how data centers are getting extinct. Previously, even a startup used to have their own data center, but now people are relying on platforms like OpenStack, AWS, or Azure.

Let’s say your organization has not shifted to the cloud and they’re still using their own data center or their own servers — we’ll also discuss how to create a virtual machine on those. These are the different things that we would cover today.

So what we would do is make a request with one of these cloud providers — let’s say we are only talking about AWS and Azure. As an end user, from your personal laptop, you log in and make a request. Let’s say this is your personal laptop and you are someone sitting in front of this laptop searching for a virtual machine.

What you do is you log into something called the AWS Console. By logging into the AWS Console, you make a request to AWS asking for a virtual machine. In AWS terminology, it is called an EC2 instance.

For theoretical understanding, what happens is — there is a developer or a person called Mr. X. What Mr. X would do, sitting in front of his laptop, is open his favorite browser and search for the AWS Console. Once he goes to the AWS Console, he can make a request through the UI to create a virtual machine or EC2 instance.

What AWS would do is, in response, it would send you back something like an IP address and all the specifications related to the virtual machine that you have requested.

This is the overall thing that happens if you are trying to create a virtual machine from the UI. The same thing happens with Microsoft Azure as well — whether it is Microsoft Azure or AWS, the process is the same.

Again, there is a person sitting in front of his laptop — let’s call him Mr. X. Instead of AWS, on his favorite browser, he opens the Microsoft Azure Portal (the Azure Portal). Once he opens it, he does the same thing — he asks Azure to create a virtual machine. In Azure terminology, we call it a virtual machine only, and Azure would send him the same response — the IP address and all the specifications required to log in.

Importance of Automation

So this is the process. But the important thing to understand is — for creating one virtual machine, everything is fine. You can log in, go through the UI, and create a virtual machine. But as a DevOps engineer, always remember from Class 1 — we have to focus on efficiency.

Let’s say you get a hundred such requests. In your organization, you might have thousands of people, and you get hundreds of similar requests every day. People ask you to create virtual machines. Would you go to your AWS portal 100 times and create them manually? You can do that, but that does not add efficiency.

In DevOps, every day we talk about the same thing — efficiency. As a DevOps engineer, you should always target improving the efficiency of your routine tasks. So what you do is look for automation.

AWS provides support for this automation. Since you’re talking to AWS, it must develop features that allow you to automate tasks. This is done through something called the AWS API.

In this case, we are talking about EC2, so it’s called the AWS EC2 API. What is it called? AWS EC2 API — because we are talking about EC2. Similarly, if you want to create storage, AWS provides the AWS S3 API. If you want to work with volumes, there’s AWS EBS API.

For now, understand that AWS developers have built something called the AWS EC2 API. Using this API, the end user or DevOps engineer can automate EC2 instance creation.

Instead of directly accessing the AWS Console from a browser, the user can write a script. Using that script, they make a call to the AWS EC2 API.

In this script, they can specify “I want to create 10 EC2 instances,” or even just automate the creation of one. Every time a user asks for an EC2 instance, they can run the script, and it returns one instance.

Even if you automate just one instance creation, and it saves even one minute of your regular time — that’s still called automation. Because there’s no manual intervention, it means no manual errors. Automation avoids errors and saves time.

Script

Now, coming to the script — it can be done in multiple ways. AWS allows you to automate things in different ways. The process is the same for Microsoft Azure as well, which is why I’m not repeating both.

The process is the same for any cloud provider — AWS, Azure, Google Cloud Platform, DigitalOcean, or any other. What they do is: for each service they provide (like EC2 or storage), they create an API.

At Amazon, developers have written hundreds of services. Today we’re dealing with the EC2 service. In the future, we’ll talk about other services. For the EC2 service, a team of developers has exposed the EC2 API.

This API receives requests. If the request comes in the expected format, as a response, it sends you an EC2 instance.

So the AWS EC2 API is responsible for receiving the request, and once it’s valid, authenticated, and authorized, it creates the resource.

Great! Here’s your next chunk cleaned, structured, and formatted for clarity while keeping all the content intact:

---

What I am talking about are three things:

1. **The request should be valid** — valid means it follows all the standards that the EC2 API is expecting.
2. **It should be authenticated** — the user making the request should have access to AWS.
3. **It should be authorized** — sometimes, as a user, you might have access to AWS, but you are not authorized to create an EC2 instance.

All three criteria have to be matched. Once these are done, as a DevOps engineer, you can write a script.

**What the script does:**
Your script has to make an API call to AWS with a request that is valid, authenticated, and authorized. As output, the script will return an EC2 instance.

**Types of scripts:**

* **CLI (Command Line Interface):** You can automate the creation of your virtual machines or EC2 instances using AWS CLI.
* **AWS API directly:** If you are familiar with REST API and a programming language, you can make direct calls to the AWS API. For example, Python supports the `boto3` module, which allows you to make API requests directly to AWS services. Even if you don’t know Python or Java, you can still use AWS CLI to automate the process.

AWS also allows writing custom scripts using open-source libraries or modules. For example, using Python and `boto3`, you can call AWS services like EC2 or S3.

* **CloudFormation Templates (CFT):** AWS supports CloudFormation Templates — a templating language with a defined structure. You provide this template to AWS, and AWS will return the requested number of virtual machines.
* **Terraform:** A popular competitor tool for automation. Terraform is cloud-agnostic — it can automate infrastructure across AWS, Azure, Google Cloud, and more.

So essentially, all these approaches (CLI, API, CFT, Terraform) are talking to the **AWS API**. Developers at Amazon expose EC2 instances through APIs, and as a DevOps engineer, you use one of these tools to automate processes in your organization.

* **Manual approach:** You can still create instances manually, but if you receive 100 requests, you would have to log in 100 times — inefficient and against the DevOps principle of efficiency.

**Interview perspective:**
If asked how to create 10 virtual machines at once or what automation is used for infrastructure, the answer depends on your organization:

* Popular tool: **Terraform** (cloud-agnostic)
* AWS-focused: **AWS CLI, API, CFT, or CDK (Cloud Development Kit)**
* Azure-focused: **Azure Resource Manager**

**AWS CDK** — recently introduced, provides advanced benefits over Terraform for AWS-specific use. CDK gives early access to new AWS services because it’s proprietary to AWS, whereas Terraform is open-source (maintained by HashiCorp and community members).

**When to use Terraform:**
Organizations using **hybrid cloud models** — different cloud platforms for different resources (e.g., AI/ML on Google Cloud, RDS on AWS). Terraform is ideal for automating infrastructure across multiple clouds.

* Single-cloud organizations: Stick with CLI, API, CFT, or CDK.
* Multi-cloud/hybrid organizations: Terraform is a better fit.

**Next steps:**
Now let’s get practical.

AWS
okay perfect so now I'm sharing my AWS console screen right let's say you don't have access or you are very new to cloud and you want to create an account with AWS it's a very simple uh practice what you have to do is you have to come here okay go for sign in dot aws.com okay or you can simply click on uh AWS console uh just go to your browser and say AWS console it will redirect you to this page if you have already have an account with AWS you can proceed with your sign in provide your user mail ID or if you don't have what you can do is you can come down and you can click on create a new AWS account once you click on create a new AWS account it would just ask you for some questions okay and you will be proceeded with creating an AWS account so there are no uh ifs and buts there like you know you can directly follow the step-by-step approach and finally you will be asked with the card details and once you provide the card details it will deduct uh if you are in India it will direct two rupees INR from your account just to validate that you are a authentic user and providing a valid card details and once you are done with that your AWS account will be created now don't worry that AWS will not charge you for any virtual machines that you are created if you are using a free instance I'll also show you how to use a free instance don't worry about it now let me just stop sharing for a moment so that I can hide my user details
stop share
and let me log in
okay coming here
so I have provided my user id uh sorry for not sharing the screen but I have to enter my password and uh my password details are entered now let me see let me go back and share my screen
perfect
AWS Services
so I hope you are looking at the right screen again perfect so now what you do is once you are done with it come here and search for the services so AWS provides you a bunch of services okay and you have to Choose Wisely what the service that you want to use so in my case I am sure that I want to use a AWS ec2 service so you can click on the ec2 service and what you will do is you look at the instances or the services that are available here what you do is you would come to the AWS ec2 global view and perfect let me just go back here and what I'll do is I would go to the instances and what I'll do is I'll click on the launch instance okay so click on the launch instance and provide these details okay now what you are doing you are talking to the AWS uh CL sorry UI directly you are not doing any API calls or this is not a process of automation what you are doing everything is a manual process okay so what do you do here you would provide the details here let's say test okay let me call my AWS instance name as test and then you have to choose over the wide range of operating systems that AWS provides you you can use Amazon Linux you can choose Ubuntu Windows red hat for a first comer or if you are just learning about uh devops and everything I would prefer Ubuntu and I would recommend you to use Ubuntu because Ubuntu is widely used in the devops community but you can go with any other options as well and after that see this is very important choose free tire eligible okay because we want to try out things and we are not going to pay any amount uh to the AWS for the instances that we're using so always choose the free tire available what is the difference between free tire and the paid ones so in free tire you get very uh restricted amount of resources so here if you see I'm only dealing with one CPU and 1GB memory but if I am going to go to the subscription model or if I'm going to pay AWS then I can choose larger virtual machines here if you see T2 large I'm going I'm getting two CPUs and 8GB memory but I am going to be charged well if you are using the free tire available or free time eligible options you'll not be charged by AWS then
after that for the very first time you have to create your key value pair with AWS what is key value pair so key value pair is something that would allow you to login to your ec2 instance okay once you create your AWS ec2 instance you would get the IP address but there has to be a password kind of thing to log into your virtual machine right so that's why click on create new key value pair okay let me call it as test key value pair or let me say test one one one and now go with the defaults choose RSA you don't have to know about uh you know Ed for now this is a different uh you know RSA is a kind of thing and Erie is a different uh encrypted public and private key methodology but for now just go with RSA that is default and pem pem should be fine for the private key file format
now click on create key value pair that would be saved it would be downloaded and saved in your local this would be very useful to login once your key value pair is gone then it is almost impossible to log into your ec2 instance so make sure you save your key value pair
then you know we are not going to talk about any of these things at this point of time I am not going to explain you what is a security group what are the vpcs and all at this point of time because today we are just learning about installing a virtual machine and uh for the beginners who are watching our videos I don't want to confuse them by explaining about the advanced concepts of a virtual machine or compute instances and then click on launch instance that's it now once you click on the launch instance your virtual machine is created you don't have to do anything else just wait for a couple of minutes go back to the instant screen your ec2 instance is available here okay it would take a couple of minutes now while we wait for this I would also parallely show you how to create instances on Microsoft azure you don't have to do anything new or anything fancy apart from uh the things that we are doing on AWS what you do is click on portal.azure.com okay on your browser go for portal.azure.com it would ask you for sign up and one good thing about Microsoft Azure is they have inbuilt integration with GitHub okay so if you are a user for GitHub user on GitHub you already have a GitHub account like like I do what I've done is I have signed up with GitHub if you see here this is a GitHub icon that I'm showing here so using GitHub I have logged in it would take less than couple of minutes for you to log in once you are done with it see here I don't I'm not holding any paid account with Microsoft Azure one difference between Azure and AWS here is if you're a new player or if you are just learning devops you know AWS provides you close to one year uh free membership on AWS whereas Azure only provides you some 30 to 45 days I'm not exactly I don't remember exactly but AWS provides you longevity so that you can play around and try AWS for more time Azure you have to buy uh after this one month or let's say no I want to create a virtual machine with Azure which I'm sure you I have to pay money so click on create resource okay or there is an option directly for virtual machines so I personally feel that the Azure user interface or user experience is slightly better than AWS like click on create virtual machine and provide the same details that you're going to provide for nav I don't hold a free account so if you if you have a free account then you just follow the same steps click on start I mean I'm not going to go with the pay and use I would go for start free but I'm already done with my free membership so if you if you have a free membership then you provide the same details that you have done with AWS and your virtual machine would be created on Azure as well so whether it's AWS or Azure the process is the same now if you see here our AWS ec2 instance is up and running okay once this AWS ec2 instance is up and running you can either log in from the UI or using the key value pair you can also log in using the terminal
