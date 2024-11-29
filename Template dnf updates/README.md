# Zabbix CentOS/Redhat dnf updates monitoring
Monitoring of available CentOS/Redhat updates via ´dnf update-check´ with Zabbix.  

## Description
Shows number of available dnf updates on host as a warning.  
YUM package manager update template also available: [Template dnf updates](https://github.com/emodii/zabbix-templates/edit/main/Template%20yum%20updates)  
Tested with:  
* Zabbix Server 7
* zabbix-agent2 (on CentOS server)

## Getting Started
### Dependencies
* Zabbix Server
* Host with zabbix-agent2 installed

### Installing
#### On Zabbix frontend server:  
* Download and import the template `template-dnf-updates.yaml`  
* Assign the `Template DNF Updates` to the docker host(s) you want to monitor  

#### On all hosts you want to monitor:
* Install and configure package zabbix-agent2 (if not installed):  
     ```sh
     apt-get install zabbix-agent2
     ```
* add file "yum.conf" to /etc/zabbix/zabbix_agent2.d/
     ```sh
     curl -L https://raw.githubusercontent.com/emodii/zabbix-templates/refs/heads/main/Template%dnf%20updates/dnf.conf -o /etc/zabbix/zabbix_agent2.d/dockcheck.conf
     ```  
* restart zabbix-agent2
     ```sh
     systemctl restart zabbix-agent2
     ```
     
## Version History
* 0.1
    * Initial Release