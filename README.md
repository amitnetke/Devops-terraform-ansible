CentOS 7 (x86_64) - with Updates HVM

installation of jenkins :

sudo -i

-- https://www.jenkins.io/download/
-- Download Jenkins 2.375.1 LTS for:  centos

---https://pkg.jenkins.io/redhat-stable/


[root@ip-172-31-95-236 ~]# history

    1  sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo

2  yum install wget -y

3  sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo

4  sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key

5  yum install fontconfig java-11-openjdk

6  yum install jenkins

7  clear

8  systemctl status jenkins

9  systemctl start jenkins

10  systemctl status jenkins

11  cat /var/lib/jenkins/secrets/initialAdminPassword


-----------------------------------------------
change jenkins permissions to perform 
systemctl status jenkins
   24  vi /usr/lib/systemd/system/jenkins.service


# $JENKINS_HOME, $JENKINS_LOG, and (if you have already run Jenkins)
# $JENKINS_WEBROOT.
User=root
Group=root


   25  systemctl daemon-reload
   26  systemctl restart jenkins
   27  cd /home/centos/

---------------------------------------

Terraform installation
https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli






 Terraform github ansible pipeline :


--- yum install git on centos node

--- install terraform on centos host machine

give an admin role to centos host machine as it will give failure for aws configure whle building

--- install ansible on centos host machine 

sudo yum install epel-release

sudo yum install ansible


-- vi /etc/ansible/ansible.cfg
   uncomment host_key_checking=FALSE


--- create a keypair on centos hostmachine to import a keypair named raman-import on aws ohio region to authenticate :
ssh-keygen -t rsa
-- import the public key to ohio in creation raman-import key

sripts for jenkins :


 terraform init
 terraform apply -auto-approve
 sleep 30
 ansible-playbook -i /tmp/inv -u ec2-user -b --become-method sudo web.yaml



poll the pipeleine
*****

