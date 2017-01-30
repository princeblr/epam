Task 2  for ubuntu 16.10 (used as server):

1. Install git (apt-get install -y git)
2. Install vagrant (apt-get install vagrant)
3. Install virtualbox (apt-get install virtualbox)
NP, all the above steps can also be automated when triggering via Vagrantfile ansible provisioner.
4. Install ansible using the below steps on the server box
   #sudo apt-get -y install software-properties-common 
   #sudo apt-add-repository ppa:ansible/ansible 
   #sudo apt-get update & sudo apt-get -y install ansible

5. I have used bento boxes for Vagrant VMs, so please follow the below process :

   Install new Vagrant Ubuntu VM from hashicorp bento url
   https://atlas.hashicorp.com/bento/boxes/ubuntu-16.10
   
   #vagrant init bento/ubuntu-16.10; vagrant up --provider virtualbox 

6. Its very important to set critical vagrant paths on your machine for your vagrant boxes like 
   (this is used fpr optimum use of disk space)
    EXPORT VAGRANT_HOME=/opt/vagrant
    EXPORT VAGRANT_DOTFILES_PATH=/opt/vagrant/.vagrant.d

7. For xml element changes, i have used the 3rd party module like : xml element changes : https://github.com/cmprescott/ansible-xml
   This can be downloaded and saved to any modules location like i have used for my scripts, my playbook will take care
   of the dependency pkgs. 
   [library        = /opt/ansible/test_modules/library/] . it could be anything, can be changed too if the playbook fails.

8. I have downloaded the war at /opt/app/guestbookapp. (usually this is taken care by playbook)

9. Also added JNDI info for configuring the correct data source but looked like there were some application issues on the jsp page.

10. There are many changes that went inside the playbooks and documenting README.md for each is a tedious task and will require more time.

11. Usually playbooks are self-explanatory in nature and all tasks are named to define explicity what each one does.
