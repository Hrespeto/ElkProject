## Automated ELK Stack Deployment
The files in this repository were used to configure the network depicted below.
![Elk stack project diagram](./Red Team network.drawio)
These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.
  - _TODO: Enter the playbook file._
This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build
### Description of the Topology
The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.
Load balancing ensures that the application will be highly avaiable, in addition to restricting access to the network.
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?_ Load balancers defends against DDoS It shifts attacks from one server to another server. Jump Boxes allows admins to connect to a secure computer(SSH), and connect to other machinces (servers, workstations).
Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logs and system metrics.
- _TODO: What does Filebeat watch for?_ Filebeat monitors the log files or locations that toy specify. After it collects the data, it forwards them to Elasticsearch.
- _TODO: What does Metricbeat record?_ Metricbeat helps monitors servers by collecting metrics from the ssystem and services running on the server. It also takes the info output them in Elasticsearch. 
The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.
|   Name    |  Function | IP Address | Operation System |
|:---------:|:---------:|:----------:|:----------------:|
| Jump box  | Gateway   | 10.0.0.4   | Linux            |
| Web-1     | Web server| 10.0.0.5   | Linux            |
| Web-2     | Web server| 10.0.0.6   | Linux            |
| ElkServer | Server    | 10.1.0.4   | Linux            |
### Access Policies
The machines on the internal network are not exposed to the public Internet. 
Only the jump box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted 10.0.0.4
Machines within the network can only be accessed by .
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_ The machinces that I allow acces to my Elk vm were Web-1 and Web-2. 10.0.0.5 and 10.0.0.6
A summary of the access policies in place can be found in the table below.
| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes/No              | 10.0.0.5 10.0.0.6    |
| Web-1    | No                  | 10.0.0.5             |
| Web-2    | No                  | 10.0.0.6             |
| ElkServer| No                  | 10.1.0.4             |
### Elk Configuration
Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_ It helps with the representation of Infrastructure as Code (IAC). Provisioning and management is involved. 
The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ...Install docker python
- ... Install memeory to max
- ... Launch the docker for the Elk container
The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.
![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)
### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_ The IP address 10.0.0.5 and 10.0.0.6
We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_ The beats that were successfully installed were the Filebeat and the Mectric Beat
These Beats allow us to collect the following information from each machine: 
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._
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
