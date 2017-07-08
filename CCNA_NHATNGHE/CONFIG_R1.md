------------------------START CONFIG R1 -----------------------------------
enable
config t
hostname R1
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
int fa0/1
no shutdown
ip add 172.16.1.2 255.255.255.252
exit

int s0/0/0
ip add 172.16.1.5 255.255.255.252
no shutdown
bandwidth 64

router ospf 100
network 172.16.1.0 0.0.0.3 area 0
default-information originate 

exit
int fa0/1
ip nat inside
exit
int s0/0/0
ip nat outside
exit
