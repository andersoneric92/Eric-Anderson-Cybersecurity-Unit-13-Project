## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![alt text](https://github.com/andersoneric92/Eric-Anderson-Cybersecurity-Unit-13-Project/blob/main/Diagrams/Azure_Diagram.png "Azure Diagram")

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  - install-elk.yml

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly _____, in addition to restricting _____ to the network.
- protected from DDoS attacks by shifting traffic, Restricting access to the network to a single secured and monitored node

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _____ and system _____.
- log files
- metrics

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function         | IP Address | Operating System |
|----------|------------------|------------|------------------|
| Jump Box | Ansible          | 10.0.0.4   | Linux            |
| VM1      | Docker container | 10.0.0.5   | Linux            |
| VM2      | Docker container | 10.0.0.6   | Linux            |
| VM3      | Docker container | 10.0.0.7   | Linux            |
| ELKVM    | Elk container    | 10.1.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- 98.36.243.49

Machines within the network can only be accessed by _____.
- Jump Box VM ip address 10.0.0.4

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses  |
|----------|---------------------|-----------------------|
| Jump Box | Yes                 | 98.36.243.49          |
| VM1      | No                  | 10.0.0.4              |
| VM2      | No                  | 10.0.0.4              |
| VM3      | No                  | 10.0.0.4              |
| ELKVM    | No                  | 10.0.0.4              |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- This reduces the potential for human error and simplifies the process of configuring multiple machines indentically

The playbook implements the following tasks:
- Install docker.io
- Install python3-pip
- Install Docker module
- Use more memory on the VM
- Download and launch a docker elk container
- Enable Docker Service on start

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![alt text](https://github.com/andersoneric92/Eric-Anderson-Cybersecurity-Unit-13-Project/blob/main/Ansible/docker_ps_output.png "Docker ps Screenshot")

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- 10.0.0.5
- 10.0.0.6
- 10.0.0.7

We have installed the following Beats on these machines:
- Filebeats
- Metricbeats

These Beats allow us to collect the following information from each machine:
- Filebeats collects information from logfiles
- Metricbeats collects informations from the system metrics

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- filebeat-configuration.yml, /etc/ansible/file/
-  /etc/ansible/host, under webservers add elkservers and add the Elk server ip address to it
- www.(public ip of elk server):5601/app/kibana

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
