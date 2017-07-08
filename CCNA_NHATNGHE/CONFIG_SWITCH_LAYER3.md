-------------------------- START CONFIG SWITCH L3  ------------------------------
enable
config t
hostname SWL3
enable secret darkness
service password-encryption 
line con 0
password hntu
logging synchronous
login
exit
line vty 0 4
password hntu
logging synchronous
login
exit
int range fa0/1-24
shutdown
exit
int range gi0/1-2
shutdown
exit
vtp mode server
vtp domain motherfucker.com
vtp password fucker

vlan 10
name VLAN10
exit
vlan 20
name VLAN20
exit
vlan 30
name VLAN30
exit
vlan 40
name VLAN40
exit
vlan 50
name VLAN50
exit
vlan 60
name VLAN60
exit
int range fa0/1-5
switchport trunk encapsulation dot1q 
switchport mode trunk
no shutdown
exit
int vlan 10
ip add 192.168.10.1 255.255.255.0
no shutdown
exit
int vlan 20
ip add 192.168.20.1 255.255.255.0
no shutdown
exit
int vlan 30
ip add 192.168.30.1 255.255.255.0
no shutdown
exit
int vlan 40
ip add 192.168.40.1 255.255.255.0
no shutdown
exit
int vlan 50
ip add 192.168.50.1 255.255.255.0
no shutdown
exit
int vlan 60
ip add 192.168.60.1 255.255.255.0
no shutdown
exit

int range fa0/10-11
no shutdown
switchport mode access
switchport access vlan 60
exit

int fa0/1
no switchport
ip add 172.16.1.1 255.255.255.252
no shutdown
exit

ip routing

int vlan 10
ip helper-address 192.168.60.100
exit
int vlan 20
ip helper-address 192.168.60.100
exit
int vlan 30
ip helper-address 192.168.60.100
exit
int vlan 40
ip helper-address 192.168.60.100
exit
int vlan 50
ip helper-address 192.168.60.100

exit
router ospf 100
network 192.168.10.0 0.0.0.255 area 0
network 192.168.20.0 0.0.0.255 area 0
network 192.168.30.0 0.0.0.255 area 0
network 192.168.40.0 0.0.0.255 area 0
network 192.168.50.0 0.0.0.255 area 0
network 192.168.50.0 0.0.0.255 area 0
network 172.16.1.0 0.0.0.3 area 0
-------------------- END CONFIG SWITCH LAYER 3 ----------------------------------------
