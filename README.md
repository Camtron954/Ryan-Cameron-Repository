# Cyber Security Bootcamp, Project 1 - Ryan Cameron

Automated ELK Stack Deployment
The files in this repository were used to configure the network depicted below.

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the : ( etc/ansible/filebeat-playbook.yml )  file may be used to install only certain pieces of it, such as Filebeat.


This document contains the following details:

Description of the Topology
Access Policies
ELK Configuration

Beats in Use
Machines Being Monitored


How to Use the Ansible Build


Description of the Topology
The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.
Load balancing ensures that the application will be highly :  safe from DDos attacks by changing the flow of web traffic  , in addition to restricting :  outside access, we can use a remote Virtual Machine to safely log in  to the network.


Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the : data in the files, for when they may have been changed and system :  metrics & stats, for when you are ready to send them to an output .


The configuration details of each machine may be found below.
Note: Use the Markdown Table Generator to add/remove values from the table.



Name
Function
IP Address
Operating System




Jump Box
Gateway
10.0.0.9
Linux


Web1
Server
10.0.0.6
Linux





Web2
Server
10.0.0.7
Linux





ELK-VM
Server
10.1.0.4
Linux







Access Policies
The machines on the internal network are not exposed to the public Internet.
Only the :  5601 Kibana Port  machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:


Machines within the network can only be accessed by :  my IP 73.54.240.243  .


A summary of the access policies in place can be found in the table below.



Name
Publicly Accessible
Allowed IP Addresses




JumpBox
Yes/No
73.54.240.243






Web1
No
10.0.0.6 / 40.88.139.89





Web2
No
10.0.0.7 / 40.88.139.89





ELK-Vnet
No
10.1.0.0/16  /  40.88.139.89

Elk Configuration
Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
:  you can put commands into multiple servers from a single playbook 

The playbook implements the following tasks:

... Install Docker, then update/upgrade
... Install pip 3 / and Python
... Attach Image, for your container
... Run the Docker container with ELK

The following screenshot displays the result of running docker ps after successfully configuring the ELK instance.


Target Machines & Beats
This ELK server is configured to monitor the following machines:
:  Web1, 10.0.0.6 / Web2, 10.0.0.7 

We have installed the following Beats on these machines:
:  Microbeats 


These Beats allow us to collect the following information from each machine:

:  Filebeat monitors the log files, collects events, then sends them to be indexed, Elasticsearch or Logstash. 
:  Metricbeat monitors collected metrics/stats then sends them to an output, Elasticsearch or Logstash. 


Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:
SSH into the control node and follow the steps below:

Copy the _____ file to _____.
Update the _____ file to include...
Run the playbook, and navigate to ____ to check that the installation worked as expected.


Which file is the playbook? Where do you copy it? 
:  (/etc/ansible/filebeat-config.yml)
Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?
: the /etc/ansible/host file,  then include the Web/ELK server IP's 
Which URL do you navigate to in order to check that the ELK server is running?
: http://20.94.254.87:5601 Kibana
