# Zadanie 1

Organizacja planuje rozpoczęcie działalności w 3 budynkach, w każdym z nich przewiduje do 1000 urządzeń IP

1. Zaprojektuj oraz udokumentuj prototyp rozwiązania z wykorzystaniem oprogramowania ``CISCO Packet Tracer``, ``VirtualBox`` lub podobnego. 

## Schemat

![zadanie 1](stage-01.svg)

## Zawartość

 ## Adresy poszczególnych sieci IP
 
 * LAN 1 192.107.0.0/22 : dostępne adresy: od 192.107.0.1 do 192.107.3.254
 * LAN 2 192.108.0.0/22 : dostępne adresy: od 192.108.0.1 do 192.108.3.254
 * LAN 3 192.109.0.0/22 : dostępne adresy: od 192.109.0.1 do 192.109.3.254
 
 ## Adresacja linków pomiędzy routerami
 
 * LAN1 <=> LAN2 192.207.4.1 <=> 192.207.0.2
 * LAN1 <=> LAN3 192.207.0.1 <=> 192.207.0.3
 * LAN2 <=> LAN3 192.207.4.2 <=> 192.207.4.3
 
 
 ## Tablice routingów na poszczególnych routerach
 
 * Router 1: 
 
192.108.0.0/22 via 192.207.0.2 \
192.109.0.0/22 via 192.207.0.3 

 * Router 2: 
 
192.107.0.0/22 via 192.207.4.1 \
192.109.0.0/22 via 192.207.4.3

 * Router 3: 
 
192.107.0.0/22 via 192.207.0.1 \
192.108.0.0/22 via 192.207.4.2
 
