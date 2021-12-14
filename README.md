## Automated ELK Stack Deployment
The files in this repository were used to configure the network depicted below.

![ScreenShot](Ansible/Elk Stack Diagram.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the playbook.yml file may be used to install only certain pieces of it, such as Filebeat.
  - [Playbook file](Ansible/Filebeat-playbook.yml.txt)
  
This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build
### Description of the Topology
The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.
Load balancing ensures that the application will be highly avaiable, in addition to restricting access to the network.
- Load balancers defends against DDoS It shifts attacks from one server to another server. Jump Boxes allows admins to connect to a secure computer(SSH), and connect to other machinces (servers, workstations).
Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logs and system metrics.
- Filebeat monitors the log files or locations that toy specify. After it collects the data, it forwards them to Elasticsearch.
- Metricbeat helps monitors servers by collecting metrics from the ssystem and services running on the server. It also takes the info output them in Elasticsearch. 
The configuration details of each machine may be found below.

|   Name    |  Function   | IP Address | Operation System |
|:---------:|:-----------:|:----------:|:----------------:|
| Jump box  | Gateway     | 10.0.0.4   | Linux            |
| Web-1     | Web Machine | 10.0.0.5   | Linux            |
| Web-2     | Web Machine | 10.0.0.6   | Linux            |
| ElkServer | Server      | 10.1.0.4   | Linux            |
### Access Policies
The machines on the internal network are not exposed to the public Internet. 
Only the jump box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted 107.221.85.110
Machines within the network can only be accessed by SSH. 
- The machince that I allow access to my Elk vm is the jump box. The IP address is ElkServer-ip
A summary of the access policies in place can be found in the table below.

| Name       | Publicly Accessible | Allowed IP Address |
|------------|---------------------|--------------------|
| Jump Box   | Yes                 | 10.0.0.5 10.0.0.6  |
| Web-1      | No                  | 10.0.0.4           |
| Web-2      | No                  | 10.0.0.6           |
| ElkServer  | No                  | 10.1.0.4           |
### Elk Configuration
Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- The main advantage of automating configuration with Ansible is, it helps with the representation of Infrastructure as Code (IAC). Provisioning and management is involved. 
The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ...Install docker python
- ... Install memory to max
- ... Launch the docker for the Elk container

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.
![ScreenShot](https://github.com/Hrespeto/ElkProject/blob/main/Ansible/Docker_ps_ouput.PNG)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- The IP address of the machines I am monitoring are 10.0.0.5 and 10.0.0.6
We have installed the following Beats on these machines:
- The beats that were successfully installed were the Filebeat and the Mectric Beat
These Beats allow us to collect the following information from each machine: 
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._ Filebeat collects log data and log events and forwards them to Elasticsearch. Metric beats 
### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 
SSH into the control node and follow the steps below:
- Copy the ansible.cfg file to /etc/ansible.
- Update the install-elk.yml and filebeat-playbook file to include the IP addresses of the machines that will be used on playbook 
- Run the playbook, and navigate to Kibana to check that the installation worked as expected.
_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it? The filebeat-playbook should be copied to /etc/ansible
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running? (kibana link)
_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
