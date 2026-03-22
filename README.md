# Ubuntu VM Security Hardening

## 1. Update and Upgrade Software:
   - Open Terminal
     
     *`sudo apt update && sudo apt upgrade -y`*

## 2. Configuring Firewall For SSH:
   - In Terminal

     *`sudo ufw enable`*
     
     *`sudo ufw default deny incoming`*
     
     *`sudo ufw allow ssh`*

## 3. Secure SSH Configuration:
   - Generate **Public and Privite Key** Pair:

      *`ssh-keygen -t ed25519`*
        - Choose a file name or use the default
        - Optional: Choose a passphrase
        - Key pair will be generated in two files with the specified file name with .pub extension being the public key
    
   - **Save Public key to SSH server:**

      *`ssh-copy-id -i <path to key pair file>.pub user@<ip address>`*
        - Type in user's password
        - The public key will be added

   - Copy and Edit **sshd_config** file:

     *`sudo cp /etc/ssh/sshd_config /etc/ssh/sshd_config.local`*

     *`sudo nano /etc/ssh/sshd_config`*

   - Set ***PermitRootLogin no*** and ***PasswordAuthentication no*** in */etc/ssh/sshd_config* file:
     
     - Also set ***PublicKeyAuthenication yes*** (*if not set by default*)


## 4. Install Fail2ban:

   - *`sudo apt install fail2ban`*
   - *`sudo systemctl enable fail2ban`*

**Test:** ***Attempt root login from a client terminal -- Should fail. Check `/var/log/auth.log`***
