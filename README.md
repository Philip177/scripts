# scripts
Linux Scripts and Ansible Scripts from my CyberClass
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](Images/diagram_filename.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: Enter the playbook file._
  -13-Elk-Stack-Project_Resources_README/README/CyberClass/Scripts/Ansible/Filebeat/filebeat-playbook.yml

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting traffic to the network.
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?
It distributes user requests among multiple servers. The jumpbox is the only ip that is public.
Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the data and system logs.
- _TODO: What does Filebeat watch for?
Filebeat monitors the log files or locations that you specify.
- _TODO: What does Metricbeat record?
Metricbeat records the metrics and statistics from the operation system and from services running on the server.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
|JumpBoxPro | Gateway | 10.0.0.4   | Linux            |
| Web-1     |Webserver| 10.0.0.7   | Linux            |
| Web-2     |Webserver| 10.0.0.8   | Linux            |
| Web-3     |Webserver| 10.0.0.9   | Linux            |


### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted IP addresses
108.6.30.196

Machines within the network can only be accessed by the Jump Box virtual machine.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_
The Jump Box VM has access to the ELK VM. The IP address of the Jump Box VM is 10.0.0.4

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
|JumpBoxPro|     No              |    108.6.30.196      |
|Web-1     |     No              |       10.0.0.7       |
|Web-2     |     No              |       10.0.0.8       |
|Web-3     |     No              |       10.0.0.9       |
|ELK-NET   |     No              |       10.1.0.4       |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?
Ansible allows IT administrators to automate their daily tasks and save a lot of time. That frees them to focus on efforts that help deliver more value to the business by spending time on more important tasks.

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc.
.Install Docker
.Install python3-pip
.Install Docker python module
.Set the vm.max_map_count to 262144
.Download and launch a docker elk container

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring
Web-1, 10.0.0.7
Web-2, 10.0.0.8
Web-3, 10.0.0.9

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed
Filebeat
Metricbeat

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc.
Filebeat monitors the log files or locations that you specify, which we use to see what changes or messages the log files have received such as kill commands. Metricbeat records the metrics and statistics from the operation system and from services running on the server, which we could use to look at how much RAM or CPU usage was being used on the webservers at certain time.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
Copy the ansible.cfg file to /etc/ansible
add the machine, its IP, and ansible_python_interpreter=/usr/bin/python3 to the hosts in the ansible.cfg as shown below:

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?
nano ansible.cfg
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
