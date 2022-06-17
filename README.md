# Ubuntu 20.04 Vagrantfile

Simple ubuntu vagrant file based on bento/ubuntu-20.04,  with public network. Used ONLY for tests purposes.

To improve SSH connection facility, the vagrant file also copy ssh public keys from current user to authorize_keys in user's vagrant and root. 

## RUN

    1 - Clone repo

    $git clone https://github.com/onovaes/ubuntu2004_vagrant.git
    
    2 - Enter in directory and run vagrant up
    
    cd /ubuntu2004_vagrant/
    $vagrant up