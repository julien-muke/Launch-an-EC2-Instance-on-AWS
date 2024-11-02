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

7. Under Network settings, notice that we selected your default VPC, selected the option to use the default subnet in an Availability Zone that we choose for you, and configured a security group with a rule that allows connections to your instance from anywhere. For your first instance, we recommend that you use the default settings. Otherwise, you can update your network settings as follows:

* (Optional) To use a specific default subnet, choose Edit and then choose a subnet.

* (Optional) To use a different VPC, choose Edit and then choose an existing VPC. If the VPC isn't configured for public internet access, you won't be able to connect to your instance.

* (Optional) To restrict inbound connection traffic to a specific network, choose Custom instead of Anywhere, and enter the CIDR block for your network.

* (Optional) To use a different security group, choose Select existing security group and choose an existing security group. If the security group does not have a rule that allows connection traffic from your network, you won't be able to connect to your instance. For a Linux instance, you must allow SSH traffic. For a Windows instance, you must allow RDP traffic.

![8](https://github.com/user-attachments/assets/84fbd825-bad8-4892-a4f2-c675e414c939)

8. Under Configure storage, notice that we configured a root volume but no data volumes. This is sufficient for test purposes.

![9](https://github.com/user-attachments/assets/ffd242ec-90d6-4b8a-a31b-fe9060e967e4)

9. Review a summary of your instance configuration in the Summary panel, and when you're ready, choose Launch instance.

![10](https://github.com/user-attachments/assets/7848c8d8-747f-4470-af98-9c57d22a2a86)

10. Select the check box for the instance. The initial instance state is `pending`. After the instance starts, its state changes to `running`. Choose the Status and alarms tab. After your instance passes its status checks, it is ready to receive connection requests.

![Screenshot 2024-11-02 142606](https://github.com/user-attachments/assets/44733bb2-14b7-4ed2-ab65-223b39d970ca)

## Step 2: Connect to your instance

The procedure that you use depends on the operating system of the instance. If you can't connect to your instance, see [Troubleshoot issues connecting to your Amazon EC2 Linux instance](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/TroubleshootingInstancesConnecting.html) for assistance.

## Connect using the Amazon EC2 console

You can connect to an instance using EC2 Instance Connect through the Amazon EC2 console. EC2 Instance Connect handles the permissions.

**Requirement:** To connect using the Amazon EC2 console, the instance must have a public IPv4 or public IPv6 address. If the instance has only a private IPv4 address, you can connect using the [ec2-instance-connect AWS CLI commands](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-connect-methods.html#connect-linux-inst-eic-cli-ssh).


To connect to your instance using the Amazon EC2 console:

1. Open the Amazon EC2 console at https://console.aws.amazon.com/ec2/.
2. In the navigation pane, choose Instances.
3. Select the instance `MyFirstInstance` and choose Connect.

![11](https://github.com/user-attachments/assets/70172c4c-95e1-4fa8-a624-ba9747720c1d)

4. Choose the EC2 Instance Connect tab.
5. For Connection type, choose Connect using EC2 Instance Connect.
6. If there is a choice, select the IP address to connect to. Otherwise, the IP address is selected automatically.
7. For Username, verify the username.

![12](https://github.com/user-attachments/assets/2e51b13c-a219-47cb-80cc-8d6785533a92)

8. Choose Connect to open a terminal window.

![13](https://github.com/user-attachments/assets/d04a67b7-67fe-4b4a-b64c-56285aa472f9)


## Connect using your own key and SSH client

You can use your own SSH key and connect to your instance from the SSH client of your choice while using the EC2 Instance Connect API. This enables you to benefit from the EC2 Instance Connect capability to push a public key to the instance. This connection method works for instances with public and private IP addresses.

To connect to your instance using your own key and any SSH client:

1. Open the Amazon EC2 console at https://console.aws.amazon.com/ec2/.
2. In the navigation pane, choose Instances.
3. Select the instance and then choose Connect.
4. On the Connect to instance page, choose the SSH client tab.
5. (Optional) If you created a key pair when you launched the instance and downloaded the private key (.pem file) to a computer running Linux or macOS, run the example chmod command to set the permissions for your private key.

![14](https://github.com/user-attachments/assets/9742133b-042f-4d5f-abc9-8a29c52ca134)

6. Copy the example SSH command. The following is an example, where `key-pair-name.pem` is the name of your private key file, `ec2-user` is the username associated with the image, and the string after the @ symbol is the public DNS name of the instance.

```bash
ssh -i key-pair-name.pem ec2-user@YOUR-PUBLIC-DNS-NAME
```

7. In a terminal window on your computer, run the ssh command that you saved in the previous step. If the private key file is not in the current directory, in my case it's in the Download folder, you must specify the fully-qualified path to the key file in this command:

* `cd Downloads`
* Run `chmod 400 "EC2ConnectKey.pem"`
* Run `ssh -i key-pair-name.pem ec2-user@YOUR-PUBLIC-DNS-NAME`
* To verify that the fingerprint in the security alert matches the instance fingerprint contained in the console output when you first start an instance, enter `yes`

![15](https://github.com/user-attachments/assets/53862ab3-f9e6-42c4-8dd0-4c2a4ce45ac4)







