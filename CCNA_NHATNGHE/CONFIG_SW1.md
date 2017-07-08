-------------------------- START CONFIG SWITCH1  ------------------------------
enable
config t
hostname SWL1
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

vtp mode client
vtp domain motherfucker.com
vtp password fucker

int range fa0/1-5
switchport mode trunk
no shutdown
exit

int range fa0/10-15
no shutdown
switchport mode access
switchport access vlan 10
exit

int range fa0/16-20
no shutdown
switchport mode access 
switchport access vlan 20
exit

-------------------- END CONFIG SWITCH LAYER 3 ----------------------------------------
