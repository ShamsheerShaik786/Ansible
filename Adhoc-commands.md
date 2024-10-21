# Ahoc Command Syntax
# Command Module

# Ansible command to see the memory info of all managed nodes
  ansible all -i /etc/ansible/hosts -m command -a 'free -m'

  Note: /etc/ansible/hosts is the deafult inventory file and when working on it we need not specify the -i option
  ansible all -m command -a 'free -m'

  Note: command module is the default module of Ansible and when working on it we need not specify the -m option
  ansible all -a 'free -m'

# Shell Module

# Ansible command to install docker on all managed nodes

  ansible all -m shell -a 'curl -fsSL https://get.docker.com -o get-docker.sh'
  ansible all -m shell -a 'sh get-docker.sh' 

# Ansible command to store the memory info of all managed nodes in file1
  ansible all -m shell -a 'free -m > file1'

# User Module

# Ansible command to create a user and assign a password
  ansible all -m user -a 'name=sai password=intelliqit' -b
  Note: -b represents "become" it is used to giving higher previlages on the remote managed nodes

# User module can also assign home dirs ,default working shell ,uid etc
  ansible all -m user -a 'name=Shamsheer password=Shamsheer uid=3421 home=/home/ubuntu/Shamsheer shell=/bin/bash comment="A normal user"' -b

# file Module

# Ansible command to create a file on all managed nodes
  ansible all -m file -a 'name=/tmp/file14 state=touch'

  Note: state= touch   is for creating files
  state=directory is for creating directories
  state=absent is for deleting file/directories

# Ansible command to create a file and also change the premissions ownership and groupship
ansible all -m file -a 'name=/home/ubuntu/file56 state=touch owner=Shamsheer group=Shamsheer mode=770' -b

# apt Module

# Ansible command to install tree on all managed nodes
  ansible all -m apt -a 'name=tree state=present' -b

  Note: state=present for installing
  state=absent for uninstalling
  state=latest for upgrading to the latest version

# Ansible command to uninstall git from all managed nodes
  ansible all -m apt -a 'state=absent name=git ' -b

# To update the apt repository we use
  update_cache=yes

# Ansible comamnd to install tomcat9 after updating the apt repository
  ansible all -m apt -a 'update_cache=yes name=tomcat10 state=present ' -b
  
# Service Module

# Ansible command to restart ssh service
  ansible all -m service -a 'name=ssh state=restarted' -b

  Note: state=restarted for restarting services
  state=started for starting services
  state=stopped for stopping services

# Install tomcat10 ,copy tomcat-users.xml file and restart tomcat

# 1 Install tomcat10
  ansible all -m apt -a 'name=tomcat10 state=present' -b

# 2 Create tomcat-users.xml file
  vim tomcat-users.xml
  <tomcat-users>
         <user username="tomcat" password="tomcat" roles="manager-script"/>
  </tomcat-users>

# 3 Copy the tomcat-users.xmlf file the required location
  ansible all -m copy -a 'src=tomcat-users.xml dest=/etc/tomcat9' -b

# 4 Restart tomcat9
  ansible all -m service -a 'name=tomcat9 state=restarted' -b

# get_url Module

# Ansible command to downlaod jenkins.war into all managed nodes
  ansible all -m get_url -a 'url=http://mirrors.jenkins.io/war-stable/2.235.3/jenkins.war dest=/tmp'

# Replace Module

# Ansible command to change  port of tomcat9 from 8080 to 9090 and restart tomcat10
  ansible all -m replace -a 'regexp=8080 replace=9090 path=/etc/tomcat10/server.xml' -b
  ansible all -m service -a 'name=tomcat9 state=restarted' -b

# git module

# Ansible command to download from a remote git repository
  ansible all -m git -a 'repo= git_repo_url dest=/tmp/mygit' -b

# uri module

# Ansible command to check if google.com is reachable from all managed nodes
  ansible all -m uri -a 'url=http://google.com status_code=200'
  
