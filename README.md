# Ubuntu VM Security Hardening

## 1. Update and Upgrade Software:
   - Open Terminal
     
     *`sudo apt update && sudo apt upgrade -y`*

## 2. Configuring Firewall For SSH:
   - Terminal

     *`sudo ufw enable`*
     
     *`sudo ufw default deny incoming`*
     
     *`sudo ufw allow ssh`*

## 3. Secure SSH Configuration:
   - Edit **sshd_config** file:

     *`
     
