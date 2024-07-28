## IAM Project Proof of Concept Setup
*Identity Management POC* will have three virtual machines to simulate the production deployment. One *Keycloak server* as the IAM solution for login management, it will be using *Ubuntu 22.04 Server* . A End-user machine, running the *Cyber-Range* operating system of *Ubuntu 22.04*, with the graphical interface. The end-user machine will be simulating a *Cyber-Range* desktop. For the last Virtual Machine there will be *Windows Server 2019* running *Active Directory Domain Services*  

### **General Overview** 
VM Hypervisor - *VMware*

VM1 (Keycloak) - *Ubuntu 22.04 Server*  

VM2 (End-user) - *Ubuntu 22.04* w/ graphical interface

VM3 (AD Domain Services) - *Windows Server 2019*  w/ graphical interface

## Keycloak Server (VMware Setup)
1. This virtual machine will be using *Ubuntu 22.04* CLI. The ISO can be downloaded from the [Ubuntu website](https://releases.ubuntu.com/jammy/)

   <img src="Images/C1.PNG" width=750>

2. Once installation is complete you can create a new virtual machine on VMware by selecting *Player* and then *New Virtual Machine*

   <img src="Images/A1.PNG" width=750>

3. Choose *Installer disc image file (iso)* and find path of *Ubuntu Server* ISO

   <img src="Images/C2.PNG" width=750>

4. Create username, full name and password

   <img src="Images/C3.PNG" width=750>

5. Name VM to Keycloak-Server, and pick a file location that has room for 20GB

   <img src="Images/C4.PNG" width=750>

6. Make sure its at least 20GB's for the maximum disk size

   <img src="Images/C5.PNG" width=750>

7. Select Finish and boot up the machine

   <img src="Images/C6.PNG" width=750>

## Keycloak Server (Keycloak Setup) 
1. Installing Keycloak server
* Update packages
   ```sh
   sudo apt update 
   ```
* Install openJDK 21 
   ```sh
   sudo apt install openjdk-21-jdk
   ```
* Copy raw link (.tar.gz) of the most current version of Keycloak on their [Github Repo](https://github.com/keycloak/keycloak/releases).

    <img src="Images/C7.PNG" width=750>

* Do a wget command for the rawlink you copied in order to get the keycloak.tar file
   ```sh
   wget https://github.com/keycloak/keycloak/releases/download/25.0.2/keycloak-25.0.2.tar.gz
   ```
* Using the tar command unzip the file using the flags -xvzf (extracts, lists out, decompresses and gets filenames)
   ```sh
   tar -xvzf keycloak-25.0.2.tar.gz
   ```
* Before you can access the dashboard you will have to setup the admin account by exporting environmental variables
  ```sh
  export KEYCLOAK_ADMIN=<choose a username>
  export KEYCLOAK_ADMIN_PASSWORD=<something secure>
  ```
* Start the server in development mode in the background using the Keycloak shell command and &
  ```sh
  <file-path/bin/kc.sh start-dev &
  ```
* You can access the dashboard using port 8080 and the host machines IP address, http://keycloak-server-ip:8080

  ## Keycloak Server (Keycloak Configuration)

