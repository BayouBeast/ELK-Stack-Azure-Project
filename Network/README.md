# Network Diagrams

### Host Workstation
- Is configured to access the internet via http protocol which runs on port 80.
- Allows connection to and from the Jump Box Provisioner.

### Internet
- Facilitates http traffic to the Jump Box Provisioner.
- 
### Load Balancer
- Distributes the traffic evenly between the three Virtual Machines. This configuration helps to prevent a single server from overworking or becoming overwhelmed by traffic

### Jump Box Provisioner
- Private IP: 10.0.0.4
- Allows admin level access to all other machines on the network
- Is configured to only allow traffic from the designated host machine
- Allows SSH into the Web Virtual Machines 1-3
- Allows SSH into Elk Server

### Elk Server
-


