# Implementación y servicios

## Plataforma
GNS3 sobre GNS3 VM / VMware, Cisco IOS 15.2, switch IOSvL2, FortiGate VM64-KVM FortiOS 7.0.9, Windows Server 2019 con Active Directory y NPS, Ubuntu Server con Zabbix.

## DHCP y conectividad
Router Fa0/0 `10.21.74.1/24`; Switch VLAN1 `10.21.74.2/24`; Zabbix `10.21.74.100`; Windows Server NPS `10.21.74.10`. DHCP pool LAN-2174 en `10.21.74.0/24`, rango utilizable tras exclusiones `.100–.200`; pool FortiGate `10.21.76.0/30` con `10.21.76.2` arrendada.

## Acceso administrativo
La PC usa VMnet1 `10.21.74.3/24` sin gateway; ruta a `10.21.76.0/30` vía `10.21.74.1`. FortiGate recibió una ruta de host `10.21.74.3/32` vía `10.21.76.1` para conservar administración al habilitar ruta IPsec hacia `10.21.74.0/24`.

## AAA / NPS
Windows NPS registra eventos 6272 y 6273. Switch usa `RADIUS-2174` y servidor NPS-2174 `10.21.74.10`, con método local alternativo. Router emplea SSH local.

## IPsec
Enlace Cisco `10.21.76.1/30` a FortiGate `10.21.76.2/30`. Redes protegidas LAN Cisco `10.21.74.0/24`, LAN FortiGate `10.21.75.0/24`; FortiGate `port2` `10.21.75.1`. Fase 1 IKEv1 DES/SHA1 DH14 28800; fase 2 ESP-DES/SHA1 PFS14 3600.

## Monitoreo
SNMPv2c de lectura en Router y Switch, monitoreados en servidor Zabbix. SNMPv2c no cifra comunidades; no se publican valores de comunidad ni claves.
