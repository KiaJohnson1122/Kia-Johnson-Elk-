Automated Elk Stack Deployment 

The files in repository were used to configure the network below. 

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above.
Docker

Filebeat

Elk

Metricbeat

Host and Config file


This document contains the following details:

Description of the Topologu

Access Policies

ELK Configuration
Beats in Use
Machines Being Monitored

How to Use the Ansible Build

----------------------------------------------------------------------------------------------------------------------------------------------
Description of the Topology
The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.
Load balancing ensures that the application will be highly secure, in addition to restricting access to the network.

What aspect of security do load balancers protect?
Load balances protect against DDos attacks. It does this by shifting attack traffic to the cloud. 
What is the advantage of a jump box?
- Ajumpbox is good becasue you can manage devices in seperate security zones. This allows logging and monitoring on a single box. 

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the date and system logs.

 What does Filebeat watch for?
 - Filebeat collects logs and monitor them. 
What does Metricbeat record?
-Metricbeat takes metrics and statistics from the system and service running. 

| Name     | Function   | IP Address             | Operating System |
|----------|------------|------------------------|------------------|
| Jump Box | Gateway    | 10.0.0.4/20.28.183.254 | Linux            |
| Web 1    | Webserver  | 10.1.0.5/20.58.184.145 | Linux            |
| Web 2    | Webserver  | 10.1.0.6/20.58.184.145 | Linux            |
| Elk      | Elk Server | 10.3.0.4               | Linux            |

----------------------------------------------------------------------------------------------------------------------------------------------
Access Policy 

The machines on the internal network are not exposed to the public Internet.

Only the JUMPBOX machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses: 

$HOST_IP

Machines within the network can only be accessed by DOCKER.

We go into our Jumpbox and start docker container from there we would get into the ELK WM and IP 10.3.0.4. 

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses       |
|----------|---------------------|----------------------------|
| Jump Box | No                  | 10.1.0.5/10.1.0.6/10.3.0.4 |

------------------------------------------------------------------------------------------------
Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...






The playbook implements the following tasks:

Install Docker.io

Install Python-pip

Increase virtual memory









The following screenshot displays the result of running docker ps after successfully configuring the ELK instance.


-----------------------------------------------------------------------------------------------

Target Machines & Beats


This ELK server is configured to monitor the following machines:


 Web-1: 10.1.0.5
 
 Web-2: 10.1.0.6
 
 ELK-VM: 10.3.4
 
 
 
We have installed the following Beats on these machines:

 Filebeat Installation
 
 Metricbeat Installation
 
 These Beats allow us to collect the following information from each machine:
 
  
  Metricbeat monitors the statistics on virtual machines. Filebeat us to collect log files from certain files and web servers. 
  
  ----------------------------------------------------------------------------------------------
  
  Using the Playbook
  
  In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:
  
SSH into the control node and follow the steps below:

Copy the yml file to ansible folder.

Update the hosts and configuration file to include the remote users and ports

Run the playbook, and navigate to [PUBLICIP of Elk-VM]:5601/app/kibana to check that the installation worked as expected.
    
 
 
 
 

