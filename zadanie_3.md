## Zadanie 3

## Charakterystyka rozwiązania:
* Uruchomione i skonfigurowane usługi: DHCP, NAT oraz DNS, aby spełnić wymagania

* Adres sieci: 172.16.0.0/22

## Użyte oprogramowanie i technologie:
* Program do obsługi maszyny wirtualnej: VirtualBox
* System operacyjny: Alpine Linux
* DHCP: dhcpd
* DNS: dnsmasq
* NAT: iptables

## Konfiguracja NAT:
* net.ipv4.ip_forward = 1
* iptables:  Chain POSTROUTING (policy ACCEPT) MASQUERADE all -- anywhere anywhere

## Konfiguracja DHCP:
* subnet 172.16.0.0 
* netmask 255.255.252.0 
* { range 172.16.0.100 172.16.3.254; option routers  172.16.0.1; 
* option domain-name-server 172.16.0.0,8.8.8.8 }
* host drukarka { hardware ethernet 0:c0:c3:88:2d:81; } 
## DNS hosts:
* 172.16.0.1 erp.mojaorganizacja.pl,
* 172.16.0.1 router.mojaorganizacja.pl
* 172.16.0.10 drukarka.mojaorganizacja.pl
## Interfejsy sieciowe:
* serwer DHCP: 
* auto eth0 
* iface eth0 inet dhcp 
* auto eth1 
* iface eth1 inet static 
* address * 172.16.0.1 
* netmask: 255.255.252.0
* drukarka sieciowa: auto eth0 
* iface eth0 inet static 
* address 172.16.0.10
* netmask: 255.255.252.0
Inne urządzenia w sieci: 
* auto eth0 
* iface eth0 inet dhcp