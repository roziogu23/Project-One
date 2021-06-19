# Project-One
https://docs.google.com/document/d/16SexDpvc7MrW17IevZPwtHD-7E9aTa0L_NFSW9EkLJM/edit?usp=sharing 

This repository highlights work from the first half of Cybersecurity Bootcamp training.
Elk-Stack-Project

The files in this repository were used to configure the network depicted below.

NetwElk Diagram.png


These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the config file may be used to install only certain pieces of it, such as Filebeat.

  filebeat-playbook.yml.txt, metricbeat-playbook.yml.txt

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly accessible, in addition to restricting traffic to the network.
What aspect of security do load balancers protect? Availability  
What is the advantage of a jump box?  The advantage of a jump box is to give access to the user from a single node that can be secured and monitored.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the jumpbox and system network.
What does Filebeat watch for? Filebeat monitors the log files or locations that you specify, collects log events, and forwards them either to Elasticsearch or Logstash for indexing.

What does Metricbeat record? Metricbeat periodically collects metrics from the operating system and from services running on the server.

The configuration details of each machine may be found below.




Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Load Balancer machine can accept connections from the Internet. 
Access to this machine is only allowed from the following IP addresses:
Home IP Address

Machines within the network can only be accessed by .
Which machine did you allow to access your ELK VM? Jump Box Provisioner & Workstation
What was its IP address? 10.0.0.4 and Home IP Address

A summary of the access policies in place can be found in the table below.



Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...services running can be limited, system installation and update can be streamlined, and processes become more replicable.

What is the main advantage of automating configuration with Ansible?  Ansible is designed to be very simple, reliable, and consistent for configuration management.

The playbook implements the following tasks:
- 1. Connect to ansible container
- 2. Create Playbook
- 3. Run Playbook

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

From GitBash>SSH to Jump Box > Start Container/attach to Container > SSH to ELK Server > Run command “sudo docker ps”



Target Machines & Beats
This ELK server is configured to monitor the following machines:


We have installed the following Beats on these machines:
Filebeat and Metricbeat

These Beats allow us to collect the following information from each machine:
In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._
Filebeat monitors the log files or locations that you specify, collects log events, and forwards them either to Elasticsearch or Logstash for indexing.

Metricbeat takes the metrics and statistics that it collects and ships them to the output that you specify, such as collecting and shipping arbitrary HTTP endpoint server metrics and statistics to Logstash or Elasticsearch.



Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the script file to your notepad.
- Update the playbook file to include the script.
- Run the playbook, and navigate to localhost/setup.php to check that the installation worked as expected.

Answer the following questions to fill in the blanks:_
Which file is the playbook? Filebeat-playbook.yml 
Where do you copy it? /etc/ansible
Which file do you update to make Ansible run the playbook on a specific machine? Hosts file
How do I specify which machine to install the ELK server on versus which to install Filebeat on?
To specify which machine to install the ELK server you use filebeat-config.yml and to specify which machine to install Filebeat on you use filebeat-playbook.yml.

Which URL do you navigate to in order to check that the ELK server is running? http://[your.VM.IP]:5601/app/kibana
