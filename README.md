# OpenVPN-on-GNS3
# How to install OpenVPN (Virtual Private Network) in Ubuntu Desktop Guest 20.4 as OpenVPN server and Client



:pushpin: in this topology I'll show you how to install OpenVpn in different instruments and how to create the connection between them in the different networks.

##
![image](images/1.1.PNG)


 # Step 1: Setting Up OpenVPN Server on Ubuntu
 ##
 :pushpin: first we are going to receive all update packets using :~$ sudo apt get update command:
 
 ##
 ![image](images/1.PNG)
 
 :pushpin: we will be using a script that lets you set up your own secure OpenVPN server in a matter of seconds. 
 ##
 :pushpin: so we are going to download the installer script using the curl command-line tool, then make it executable using the chmod command as follows.
 
 :~$ curl -O https://raw.githubusercontent.com/angristan/openvpn-install/master/openvpn-install.sh
##

##
![image](images/2.PNG)
 
 :~$ chmod +x openvpn-install.sh 
 
##
 ![image](images/3.PNG)
 
##

##
:pushpin: Next, run the executable installer script as shown.
##

When executed for the first time, the script will ask you some questions, read them carefully, and provide answers according to your preferences, to set up your OpenVPN server.

##
![image](images/4.PNG) 
 
## 

![image](images/5.PNG)
 
##

![image](images/6.PNG)
 
##

![image](images/7.PNG)

##

![image](images/8.PNG)

##
Once the VPN installation process is complete, a client configuration file will be written under the current working directory. This is the file you will use to configure your OpenVPN client as described in the next section.

##
![image](images/9.PNG)
 
##

Next, confirm that the OpenVPN service is up and running by checking its status using the following:
 
##

:~$ sudo systemctl status openvpn

##
![image](images/10.PNG)

##
Then check if the OpenVPN interface exists and has got the IP address: 

##
![image](images/11.PNG)
##

Also, confirm that the OpenVPN daemon is listening on the port you instructed the script to use, using the ss command as shown.

:~$ sudo ss -tupln | grep openvpn

##

##
![image](images/12.2.PNG)

##
 
:pushpin: 1- La commande TRACERT
 
 :pushpin: 2- Firewalld. D'abord je vous explique comment installer firewalld sur votre serveur,et comment le configurer. Et après, le configurer d'une manière que seulement une           spécifique address IP ait l'autorité de le conneceter. À la suite, vous utilisez SSH et l'address IP de l'interface de votre OpenVPN pour vous connecter à votre serveur.
 


 :star: D'abord en utilisant les commmandes suivantes on va recevoire les derniers mis à jours.
 
 :~$ sudo apt-get update
 
 :~$ sudo apt-get upgrade
 
 ![image](images/22.PNG)
 
