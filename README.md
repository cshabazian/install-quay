# Ansible playbooks to install either Red Hat Quay or Project Quay

## Instructions:
### Clone this repository
`git clone https://github.com/cshabazian/install-quay.git`

### Install ansible
`sudo dnf -y install ansible-core`

### Install ansible-galaxy requirements
`ansible-galaxy install -r files/requirements.yml`

---

### To install Red Hat Quay, you will need to pass credentials, or store them in ~/.ansible/quay.vars
**Optional use of ssl - Define:**  
SSL_CERT:  
SSL_KEY:  
and change USE_SSL: from false to true  
These may also be included in your local vars  
and simply run:  
`ansible-playbook install_quay.yml`  
If not using a local vars file, pass credentials to the playbook  
`ansible-playbook install_quay.yml -e REGISTRY_USER="<registry_username>" -e REGISTRY_PASS="<registry_pasword>"`

--- 

### To install upstream project quay
**Optional use of ssl:**  

add ssl.cert and ssl.key to the files directory and change USE_SSL: from false to true  
`ansible-playbook install_project_quay.yml`  
or
`ansible-playbook install_project_quay.yml -e USE_SSL="true"`  


`ansible-playbook install_project_quay.yml`  
or  
`ansible-playbook install_project_quay.yml -e USE_SSL="true"`  
---
*There are many variables in the playbooks that you can change. **PLEASE** at least change the passwords*
