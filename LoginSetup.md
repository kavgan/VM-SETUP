
## 0. Enable RSA 

Check to ensure key authentication enabled.

    sudo nano /etc/ssh/sshd_config

## 1. Generate Keys
Go to your local terminal
  
    ssh-keygen -t rsa -b 4096

Specify location for saving:

    ~/.ssh/vm_key
    
Change mode    

    chmod 600 ~/.ssh/vm_key

## 2. Copy Key to VM

Copy the public key to server.

    cat ~/.ssh/vm_key.pub

Log in to server using pwd

    ssh user@ipaddress

Create a file

    vim vm_key.pub

Paste public key from local machine and save.

    echo vm_key.pub >> ~/.ssh/authorized_keys
 
    mv vm_key.pub ~/.ssh/

    chmod 600 vm_key.pub

    chmod 600 authorized_keys

## 3. Login
  
    ssh usern@ip -i ~/.ssh/vm_key


## Create Jupyter Tunnel
  ssh  -i /home/kavgan/.ssh/id_rsa -N -L 3333:localhost:3333 user@123.456.789.10
