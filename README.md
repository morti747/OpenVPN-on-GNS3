# OpenVPN-on-GNS3
# How to install OpenVPN (Virtual Private Network) in Ubuntu Desktop Guest 20.4 as OpenVPN server and Client



:pushpin: in this topology I'll show you how to install OpenVpn in different instruments and how to create the connection between them in the different networks.

![image](images/1.1.PNG)

 
 :pushpin: À la fin, je vais vous montrer comment vous assurer que vous êtes connecté à votre serveur à partir de votre OpenVPN en utilisant:
 
 :pushpin: 1- La commande TRACERT
 
 :pushpin: 2- Firewalld. D'abord je vous explique comment installer firewalld sur votre serveur,et comment le configurer. Et après, le configurer d'une manière que seulement une           spécifique address IP ait l'autorité de le conneceter. À la suite, vous utilisez SSH et l'address IP de l'interface de votre OpenVPN pour vous connecter à votre serveur.
 


 :star: D'abord en utilisant les commmandes suivantes on va recevoire les derniers mis à jours.
 
 :~$ sudo apt-get update
 
 :~$ sudo apt-get upgrade
 
 ![image](images/22.PNG)
 
