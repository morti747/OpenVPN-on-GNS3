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
 
 ##
 ``
 :~$ curl -O https://raw.githubusercontent.com/angristan/openvpn-install/master/openvpn-install.sh
``
##

##
![image](images/2.PNG)

##
``
 :~$ chmod +x openvpn-install.sh 
`` 
##

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

##
``
:~$ sudo systemctl status openvpn
``
##

##

![image](images/10.PNG)

##
 If you check your network interfaces, a new interface has been created for a VPN tunnel, you can confirm this by using IP command.
 
##

##
``
:~$ IP addr
``

##
##
![image](images/11.PNG)
##

Also, confirm that the OpenVPN daemon is listening on the port you instructed the script to use, using the ss command as shown.


##
``
:~$ sudo ss -tupln | grep openvpn
``
##

##
![image](images/12.2.PNG)

##
 
 
# Step 2: Setup OpenVPN Clients in Ubuntu 
 
:pushpin: Now its time to set up your OpenVPN client and connect it to the VPN server. First, install the OpenVPN package in the client machine as follows.
 
##
``
sudo apt install openvpn
``

##
![image](images/13.PNG)

## 
 
##
On a desktop system, you also need to install the network-manager-openvpn package to make VPN settings from the graphical interface.

##

##

``
sudo apt-get install network-manager-openvpn
``
##
##
![image](images/14.PNG)

## 
 
After installing the above packages, start the OpenVPN service, for now, enable it to automatically start at system boot and check its status to confirm that it’s up and running.

``
sudo systemctl start openvpn 
``
##
``
sudo systemctl enable openvpn
``
##
``
sudo systemctl status openvpn
``

##

![image](images/15.PNG)
##
 
 
:pushpin: Check if you can reach the server from the client using ping and ssh commands: 

## 
![image](images/16.PNG)

## 
##

If you need to install SSH on your instruments, you can use the following command: 

##
``
sudo apt-get install ssh
``
##

![image](images/17.PNG) 
 
##

and the check its status: 

``
sudo systemctl status ssh
``
##

![image](images/18.PNG) 
 
##

##

Now check if you can reach your server using ssh, and use ip addr command to see its interfaces: 


##

![image](images/19.PNG) 

##

##

![image](images/20.PNG) 

##

##

![image](images/21.PNG) 

##

Now you need to import the OpenVPN client settings from the OpenVPN server. Open a terminal window and use the SCP command to grab the file as shown:

##
``
scp osboxes@10.8.0.1:/home/osboxes/morty.ovpn .
``
##

##
![image](images/22.PNG) 
##

##
Open system Settings, then go to Networks. Under VPN, click the add button to get the necessary options.
##


##
![image](images/23.1.PNG) 

##

##
![image](images/23.2.PNG) 

##

##
![image](images/24.PNG) 

##
After importing the file, the VPN settings should be added as shown in the following screenshot. Then click Add.


##
![image](images/25.1.PNG) 

##

Your VPN client settings should be added successfully. You can connect to the OpenVPN server by turning on the VPN as highlighted in the following screenshot.

##
![image](images/27.PNG) 
##

If you check your network interface connections using the IP add command, there should now exist a VPN tunnel interface as highlighted in the following screenshot.

##
![image](images/30.PNG) 
##









