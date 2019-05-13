# aws-ansible-practice
### NOTE: For zoo-kafka-standalone use t2.large
### NOTE: For nifi-standalone (in Security Groups) Add TCP rule for inbound access to port 8080 from "My IP" 

1. Follow instructions for **aws-ansible-ctrl dev environment (tested on Windows 10 )**
  ===>  https://github.com/spenfraz/vagrant-dev-envs/tree/ansible_local  

2. (while still at the "[vagrant@ansible-dev ~]$ " prompt...) $ cd /home/vagrant/
3. $ git clone https://github.com/spenfraz/aws-ansible-practice.git
4. $ cd aws-ansible-practice
5. $ ansible-playbook nifi-standalone.yml  **OR**   $ ansible-playbook zoo-kafka-standalone.yml
6. (Once control of the terminal returns) To test nifi-standalone go to https://\<public-ip-of-ec2>:8080/nifi  **OR**  To test zoo-kafka-standalone, ssh into EC2 instance from [vagrant@ansible-dev ~] with   $ ssh -i ~/.ssh/<filename>.pem ec2-user@\<public-ip-of-ec2>
7. (After ssh'ing into ec2 instance)  $ netstat -ant | grep -E ':2181|:9092'   ( kafka server runs on port 9092 and zookeeper on port 2181 )
