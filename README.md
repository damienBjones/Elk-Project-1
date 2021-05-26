## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

!https://github.com/damienBjones/Elk-Project-1/blob/main/Virtual%20Network.JPG

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the roles folder may be used to install only certain pieces of it, such as Filebeat.

  - /etc/ansible/roles/filebeat-playbook.yml

### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly secure, in addition to restricting access to the network.
-  Load balancers protects the system from DDoS attacks by shifting attack traffic
-  The advantage of a jump box is to give access to the user from a single node that can be secured and monitored.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the network and system logs.
-  Filebeat collects data about the file system.
- Metricbeat collects machine metrics  from the operating system and from services running on the server

The configuration details of each machine may be found below.

| Name        | Function   | IP Address | Operating System |
|-------------|------------|------------|------------------|
| Jumpbox     | Gateway    | 10.0.0.4   | Linux            |
| redteamWeb1 | Web Server | 10.0.0.5   | Linux            |
| redteamWeb2 | Web Server | 10.0.0.6   | Linux            |
| ElkVM1      | Elk Server | 10.1.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Elk VM machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- 70.133.217.87

Machines within the network can only be accessed by jumpbox.
- Jump-Box-Provisioner. 10.0.0.4_

A summary of the access policies in place can be found in the table below.

| Name        | Publicly Accessible | Allowed IP Address |
|-------------|---------------------|--------------------|
| Jumpbox     | Yes                 | 52.255.191.196     |
| redteamWeb1 | No                  | 10.0.0.5           |
| redteamWeb2 | No                  | 10.0.0.6           |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because you can setup OpenSSH without installing anything on the servers.

The playbook implements the following tasks:
- install docker
- install Python3-pip
- 

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

https://github.com/damienBjones/Elk-Project-1/blob/171eb56bd96db2af00caf4bd882f5fb6e2ce3ef8/Capture.PNG

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_

We have installed the following Beats on these machines:
- filebeat
- metricbeat

These Beats allow us to collect the following information from each machine:
-Filebeat collects log files from web servers.
Metericbeat periodically collect metrics from the operating system and from services running on the server

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the filebeat-playbook.yml file to /etc/ansible/roles
- Update the host file to include the ip address of your Elk machine
- Run the playbook, and navigate to Kibana GUI. to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?


