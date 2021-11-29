# Playbook Summary
This playbook contains a series of scripts used to automate the instillation and startup of Docker, Ansible Pip3, Filebeat, and Metricbeat. It also contains scripts for the configuration of Docker, Filebeat, Metricbeat, and Ansible

### Docker and Pip 3 Install
- This is the first install done.
- Docker is a container which is lighter than a vm because it does not have an OS. This is what we will enable  
 ansible on. After Ansible is configured then you will install Filebeat and Metricbeat onto Ansible.
- Pip3 is the official Python 3 package manager.

### hosts
- This is the host file where you need to add your virtual machines in order to configure them with ansible.

### Filebeat and Metricbeat Install and Launch
- These scripts install and launch Filebeat and Metricbeat 
- They will allow you to start pulling data from the webvms and send it to Kibana once they are configured in the   next step

### Filebeat and Metricbeat Configs
- Now that Filebeat and Metricbeat are installed they must be configured to your IP address.
- Once this is complete Kibana should show that it is recieving data from the Elk Server which inturn is recieving 
 data from the Web Virtual Machines
