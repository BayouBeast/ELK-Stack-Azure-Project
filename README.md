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
- Load Balancers protect the availability aspect of security. They dispense traffic across servers in-order to ensure each of them is processing an evenly distributed load. Thus, reducing the likelihood of overwhelming the network by too much activity on a single server.

-  Jump Boxes are what administrators connect to for doing tasks, connecting to servers, or accessing environments that are not trusted. When configured right a jump box increases the security of a network. The most secure  version of which is know a secure admin workstation (SAW). A SAW is a computer that an admin must use in order to carry out administrative tasks or connecting to a server or network. Jump Boxes are ONLY used for administrative tasks and are NEVER used for any other activity. In summation, Jump Boxes allow for tighter security because of their single point of access and single use purpose to using administrative privilege's on a network.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the data and system logs.
- Filebeat watches for irregularities in files by "harvesting" them. Harvesters read the content within a file adn sends the content to an output of events which can be further analyzed.

- Metricbeat records metrics from data running on and through services services and gives it an output in a gui.

#### Machine Configuration Table

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.1   | Linux            |
| Web-1    |          |            |                  |
| Web-2    |          |            |                  |
| Web-3    |          |            |                  |


### Access Policies

The machines on the internal network are not exposed to the public Internet.

The Jumpbox is the ONLY machine that can accept connections from the Internet. Access to this machine is only allowed from your host IP address which can be found by typing; "What is my IP Address?" into a search engine.

Machines within the network can only be accessed by the ansible container running on the jumpbox via the ssh protocol running on port 22.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_

#### Access Policy Table.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | 10.0.0.1 10.0.0.2    |
| Web-1    | No                  |                      |
| Web-2    | No                  |                      |
| Web-3    | No                  |                      |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of Elk. Automation is advantageous because it saves time and ensures consistancy of installs.

The playbook implements the following tasks:
- Step 1: Install Docker using script [Docker and Pip3 Install](https://github.com/BayouBeast/ELK-Stack-Azure-Project/blob/main/Playbook/Docker_pip3_Download_Install.yml) and enable ansible by running sudo su | docker start (container name) | docker attach (container name). After Ansible is running configure it to the IP addresses necessary in the hosts file with nano which is located in /etc/ansible.
- Step 2: Download the Configuration files [Filebeat Configuration](https://github.com/BayouBeast/ELK-Stack-Azure-Project/blob/main/Playbook/Filebeat_Configuration.yml) and [Metricbeat Configuration](https://github.com/BayouBeast/ELK-Stack-Azure-Project/blob/main/Playbook/MetricbeatConfigExample.yml) to the ansible directory. Nano into the file and change the IP addresses to that of your JumpBox Provisioner in both files.
- After Configuration you are ready to install the [Filebeat Instillation](https://github.com/BayouBeast/ELK-Stack-Azure-Project/blob/main/Playbook/Filebeat_Install_Launch.yml) and [Metricbeat Instillation](https://github.com/BayouBeast/ELK-Stack-Azure-Project/blob/main/Playbook/Metricbeat_Install_Launch.yml)

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
- Copy the ConfigureELK_vm_used_Docker.yml file to /etc/ansible/.
- Update the hosts file to include the IP address of the Elk Virtual Machine
- Run the playbook, and navigate to the kibana site on port 5601 to check that the installation worked as expected.

- YAML files are the playbooks used which get copied into the ansible folder.
- The host file must be updated with the IP addresses for Ansible to run on a specific machine. The Filebeat Configuration file is where you specify the location for you to install it. When you SSH into the VM you want to install elk on you are able to do so through the CLI.
- https://20.124.33.252:5601/app/kibana (IP of Elk Machine) navigating here will confirm its running properly.


