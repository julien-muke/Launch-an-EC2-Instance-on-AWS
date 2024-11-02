<div align="center">
  <br />
    <a href="https://youtu.be/HcqDrF-k7bc?si=vc-ViXgOG4B7IOEl?feature=shared" target="_blank">
      <img src="https://github.com/user-attachments/assets/024577c7-30a4-46e3-bfc9-4932270a01ed" alt="Project Banner">
    </a>
  <br />

<h3 align="center">How to Launch an EC2 Instance on AWS: Complete Step-by-Step Guide for Beginners</h3>

   <div align="center">
     Build this hands-on demo step by step with my detailed tutorial on <a href="http://www.youtube.com/@julienmuke/videos" target="_blank"><b>Julien Muke</b></a> YouTube. Feel free to subscribe 🔔!
    </div>
</div>

## 📋 <a name="table">Table of Contents</a>

1. 🤖 [Introduction](#introduction)
2. ⚙️ [Tech Stack](#tech-stack)
3. 🔋 [Steps](#features)
4. 🤸 [Quick Start](#quick-start)
5. 🕸️ [Snippets (Code to Copy)](#snippets)
6. 🔗 [Assets](#links)
7. 🚀 [More](#more)

## 🚨 Tutorial

This repository contains the steps corresponding to an in-depth tutorial available on our YouTube
channel, <a href="http://www.youtube.com/@julienmuke/videos" target="_blank"><b>Julien Muke</b></a>.

If you prefer visual learning, this is the perfect resource for you. Follow my tutorial to learn how to build projects
like these step-by-step in a beginner-friendly manner!

<a href="https://youtu.be/HcqDrF-k7bc?si=vc-ViXgOG4B7IOEl?feature=shared" target="_blank"><img src="https://github.com/sujatagunale/EasyRead/assets/151519281/1736fca5-a031-4854-8c09-bc110e3bc16d" /></a>

## <a name="introduction">🤖 Introduction</a>

In this beginner-friendly tutorial, we'll walk you through the process of launching your very first EC2 instance on AWS. Whether you're new to cloud computing or looking to sharpen your AWS skills, this step-by-step guide covers the complete step-by-step guide. By the end of this video, you'll be ready to deploy and manage virtual servers with ease!

## <a name="tech-stack">⚙️ Tech Stack</a>

- Amazon Web Services
- Amazon EC2

## <a name="features">🚩 Steps</a>

👉 **Step 1**: Launch an instance

👉 **Step 2**: Connect to your instance

👉 **Step 3**: Clean up your instance

## <a name="quick-start">🤸 Quick Start</a>

Follow these steps to set up your first EC2 instance on Amazon Web Services.

**Prerequisites**

Make sure you have the following:

- [Create an AWS account](https://aws.amazon.com/)
- Install OpenSSH on [Window](https://learn.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse?tabs=gui&pivots=windows-server-2025) or [Ubuntu](https://hostman.com/tutorials/how-to-install-and-configure-ssh-on-ubuntu-22-04/)

## Step 1: Launch an instance

You can launch an EC2 instance using the AWS Management Console as described in the following procedure. This tutorial is intended to help you quickly launch your first instance, so it doesn't cover all possible options.

To launch an instance:

1. Open the Amazon EC2 console at https://console.aws.amazon.com/ec2/.
2. From the EC2 console dashboard, in the Launch instance pane, choose Launch instance.

![2](https://github.com/user-attachments/assets/71299dde-cb7c-4b5a-9919-d515770e0ed0)

3. Under Name and tags, for Name, enter a descriptive name for your instance, i will name it `MyFisrtInstance`.

![3](https://github.com/user-attachments/assets/0af5a012-104f-4edd-984e-7837a2ab4cf3)

4. Under Application and OS Images (Amazon Machine Image), do the following:
<br> a. Choose Quick Start, and then choose the operating system (OS) for your instance. For your first Linux instance, we recommend that you choose Amazon Linux.
<br> b. From Amazon Machine Image (AMI), select an AMI that is marked Free Tier eligible.

![4](https://github.com/user-attachments/assets/2fe9f406-e821-4185-bda7-3e2db1b0759c)

5. Under Instance type, for Instance type, choose t2.micro, which is eligible for the Free Tier. In Regions where t2.micro is not available, t3.micro is eligible for the Free Tier.

![5](https://github.com/user-attachments/assets/7127433f-46c6-4def-9a29-f8cc8578b2c1)

6. Under Key pair (login), for Key pair name, choose an existing key pair or choose Create new key pair to create your first key pair.

![6](https://github.com/user-attachments/assets/870eb2ed-c072-499e-a8de-4a9ab1494415)

⚠️ Warning: If you choose Proceed without a key pair (Not recommended), you won't be able to connect to your instance using the methods described in this tutorial.


