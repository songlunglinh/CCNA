//CONFIG R2
enable
config t
hostname R2
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
int s0/0/0
ip add 172.16.1.6 255.255.255.252
no shutdown
bandwidth 64
clokc rate 64000
