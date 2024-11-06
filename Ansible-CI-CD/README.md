**SetUp & Installation of Ansible**
1. Create 4 ubuntu EC2 instances and Name them as Controller, DevServer, QAServer and ProdServer
2. Establish passwordless ssh from Controller to DevServer, QAServer, and ProdServer
3. Connect to Controller using gitbash
4. Generate the ssh keys **ssh-keygen**
5. goto **cd .ssh** folder and do **ls**
6. copy the public_key
7. Connect to DevServer using gitbash
8. go to **cd.ssh** folder and do **ls**
9. Open the **authrosized_key** and paste the **public_key** of controller
10. Restart the **service sudo service ssh restart**
11. Repeat the steps 7 to 10 for the remaining servers

**Installing Ansible**
1. Update the apt repository
     **sudo apt-get update**
2. Install software-properties-common
     **sudo apt-get install -y software-properties-common**
3. Add the latest version of Ansible to apt repository
     **sudo apt-add-repository ppa:ansible/ansible**
4. Update the apt repository
     **sudo apt-get update**
5. Install ansible
     **sudo apt-get install -y ansible**
6. To check the verision of ansible
     **ansible --version**
Ansible stores all the remote servers info in a file called as inventory file We should open this file and store the ipaddress of all the managed nodes here
**sudo vim /etc/ansible/hosts**
Here copy and paste the ipaddresses of the managed nodes

![Screenshot (101)](https://github.com/user-attachments/assets/87ebddb2-b9f3-4cd8-8c16-adfcca21bf14)
![Screenshot (98)](https://github.com/user-attachments/assets/d1e65574-dc6d-403f-ae79-90d0f2055424)
![Screenshot (99)](https://github.com/user-attachments/assets/b0fcb1db-4b4c-4a88-b48e-e023ecd935a5)
![Screenshot (100)](https://github.com/user-attachments/assets/38ec0cb3-0ada-4d41-88b0-56c12a7bd9c5)



