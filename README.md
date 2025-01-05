Basic Device Configuration: SWITCH
at the terminal:
Enter GLOBAL CONFIGURATION mode
Switch# configure terminal
Switch(config)#

Name the switch “Sw-Floor-1”
Switch(config)# hostname SW-Floor-1

Secure user EXEC mode access by entering line console 0, assign the password cisco, enable login, and return to the global configuration mode using exit.
Sw-Floor-1(config)# line console 0
Sw-Floor-1(config-line)# password cisco
Sw-Floor-1(config-line)# login
Sw-Floor-1(config-line)# exit

Secure privileged EXEC mode access using the password class
Sw-Floor-1(config)# enable secret class

Secure the VTY lines 0 through 15, assign the password cisco, enable login, and return to the global configuration mode using exit.
Sw-Floor-1(config)# line vty 0 15
Sw-Floor-1(config-line)# password cisco
Sw-Floor-1(config-line)# login
Sw-Floor-1(config-line)# exit

Encrypt all plaintext passwords.
Sw-Floor-1(config)# service password-encryption

Create a banner message using the “#” symbol as the delimiter. The banner should display exactly: Warning! Authorized access only!
Sw-Floor-1(config)# banner motd #Warning! Authorized access only!#
You successfully completed the basic requirements to access and secure a device.

Configure a Switch Virtual Interface
Enter interface configuration mode for VLAN 1.
Switch(config)# interface vlan 1
Configure the IPv4 address as 192.168.1.20 and the subnet mask as 255.255.255.0.
Switch(config-if)# ip address 192.168.1.20 255.255.255.0
Enable the interface.
Switch(config-if)# no shutdown
Switch(config-if)# exit
Switch(config)# ip default-gateway 192.168.1.1

You have successfully configured the switch virtual interface for VLAN 1.
 
Basic Device Configuration: ROUTER
at the terminal:
Enter global configuration mode to configure the name of the router as “R1”.
Router> enable
Router# configure terminal
Router(config)# hostname R1

Configure 'class' as the secret password.
R1(config)#enable secret class

Configure 'cisco' as the console line password, require users to login, and return to global configuration mode.
R1(config)# line console 0
R1(config)# password cisco
R1(config)# login
R1(config)# exit

For vty lines 0 through 4, configure 'cisco' as the password, require users to login, enable SSH and Telnet access, and return to global configuration mode.
R1(config)# vty line 0 4
R1(config-line)# transport input ssh telnet
R1(config-line)# password cisco
R1(config-line)# login
R1(config-line)# exit
R1(config)# ip domain name PEPXL.be
R1(config)# crypto key generate rsa (1024)
Encrypt all clear text passwords.
R1(config)#service password-encryption
Enter the banner 'Authorized Access Only!' and use # as the delimiting character.
R1(config)#banner motd #Authorized Access Only!#
Exit global configuration mode.
R1(config)#exit
R1#
You have successfully configured the initial settings on router R1.

Configure a Router Interface
Enter interface configuration mode for TYPE – and - NUMBER.
R1(config)# interface type number (interface gigabitEthernet 0/0/0)
R1(config-if)# description description-text (description Link to Lan)
R1(config-if)# ip address ipv4 address subnet mask 
(ip address 209.165.200.225 255.255.255.252)
R1(config-if)# ip address ipv6 address /prefix length) (ipv6 address 2001:db8:feed:224::1/64)
R1(config)# no shutdown
R1(config-if)# exit
You have successfully configured the switch virtual interface for VLAN 1. 
Verification Commands:
at the terminal:
R1#  show ip interface brief (verkort: sh ip int)
R1#  show ipv6 interface brief
PING (kijken als de verbinding goed is, als er connectie is)
R1#  ping 192.168.10.1

WINDOWS PC CONFIG
at the command prompt:
C:\> ipconfig
C:\> ping 192.168.10.2
You successfully displayed the IP configuration on a Windows PC.









