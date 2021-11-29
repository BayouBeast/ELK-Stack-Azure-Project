# Automating an ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

 - [Virtual Network Diagrams](https://github.com/BayouBeast/ELK-Stack-Azure-Project/tree/main/Network)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the Playbook file may be used to install only certain pieces of it, such as Filebeat.

  - [Playbook of YAML Files](https://github.com/BayouBeast/ELK-Stack-Azure-Project/tree/main/Playbook)

# Contents:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting access to the network.
- Load Balancers protect the availability aspect of security. They dispense
 traffic across servers in-order to ensure each of them is processing an evenly distributed load. Thus, reducing the likelihood of overwhelming 
 the network by too much activity on a single server.

-  Jump Boxes are what administrators connect to before doing tasks, connect  
  to servers, or access environments that are not trusted. When configured right a jump box increases the security of a network. The most
  secure  version of which is know a secure admin workstation (SAW). A SAW is a computer that an admin must use in order to carry out 
  administrative tasks or connecting to a server or network. Jump Boxes are ONLY used for administrative tasks and are NEVER used for any 
  other activity. In summation, Jump Boxes allow for tighter security because of their single point of access and single use purpose to 
  using administrative privilege's on a network.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the data and system logs.
- Filebeat watches for irregularities in files by "harvesting" them. Harvesters read the content within a file adn sends the content to an output of events which can be further analyzed.

- Metricbeat records metrics from data running on and through services services and 

### Machine Configuration Table

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.1   | Linux            |
| Web-1    |          |            |                  |
| Web-2    |          |            |                  |
| Web-3    |          |            |                  |

### Access Policies

The machines on the internal network are not exposed to the public Internet.

Only the Jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from your host IP address which can be found by typing; "What is my IP Address?" into a search engine.

Machines within the network can only be accessed by ssh.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | 10.0.0.1 10.0.0.2    |
| Web-1    | No                  |                      |
| Web-2    | No                  |                      |
| Web-3    | No                  |                      |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ...
- ...

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

[Successful Configuration of Docker with Elk](https://github.com/BayouBeast/ELK-Stack-Azure-Project/blob/main/Screenshots/elk_deployment.PNG)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_

We have installed the following Beats on these machines:
- Metricbeats and Filebeats have been installed on the 

These Beats allow us to collect the following information from each machine:
- Filebeats allows one an easy way that is lightweight to forward and  
  centralize log files.
- Metricbeats  _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._

