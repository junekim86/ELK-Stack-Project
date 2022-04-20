# ELK-Stack-Project
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.
ELK-Stack-Project/ELK diagram.png
             

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. 

 Ansible/metricbeat_playbook.yml

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly efficient, in addition to restricting congestion to the network.  Load balancing plays an important security role as computing moves evermore to the cloud.  The off-loading function of a load balancer defends an organization against distributed denial-of-service (DDoS) attacks.  A jump box is a secure computer that all admins first connect to before launching any administrative task or use as an origination point to connect to other servers or untrusted environments.


Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the data and system logs.
Filebeat monitors the log files or locations that you specify, collect log events, and forwards them either to Elasticsearch or Logstash for indexing.
Metricbeat takes the metrics and statistics that it collects and ships them to the output that you specify, such as Elasticsearch or Logstash. Metricbeat helps you monitor your servers by collecting metrics from there system and services running on the server, such as Apache.

The configuration details of each machine may be found below.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.1   | Linux            |
| Web-1    | Container| 10.0.0.12  | Linux            |
| Web-2    | Container| 10.0.0.10  | Linux            |
| ELK      | Container| 10.1.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
108.236.42.161

Machines within the network can only be accessed by Jump box. You are able to access the ELK VM through the Jump box: 10.0.0.4


A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | No                  |  108.236.42.161      |
| Web-1    | No                  |  20.231.32.213       |
| Web-2    | No                  |  20.231.32.213       |
| ELK      | No                  |  20.25.75.19         |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because automation helps considerably with the representation of Infrastructure as Code (IAC).  IAC involves provisioning and management of computing infrastructure and related configuration through machine-processable definition files.




The playbook implements the following tasks:
Step 1: Install Dependencies, Install Java, Install Nginx
Step 2: Add Elastic Repository
Step 3: Install Elasticsearch
Step 4: Install Kibana
Step 5: Install Filebeat

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

ELK-Stack-Project/Ansible

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
Web-1 10.0.0.12
Web-2 10.0.0.10

We have installed the following Beats on these machines:
- Filebeat & Metricbeat
Filebeat is "A lightweight shipper for forwarding and centralizing log data". It helps you keep the simple things simple by offering a lightweight way to forward and centralize logs and files. On the other hand, Metricbeat is detailed as "A Lightweight Shipper for Metrics".
