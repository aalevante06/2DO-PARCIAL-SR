# Matriz de validación funcional

| Requisito | Comando o ubicación | Resultado comprobado |
|---|---|---|
| Direccionamiento Router | `show ip interface brief` | `10.21.74.1`, `10.21.76.1` UP/UP |
| DHCP Router | `show ip dhcp binding` | `10.21.74.100` activa y FortiGate `10.21.76.2` observado |
| SSH v2 Router/Switch | `show ip ssh` | SSH version 2.0 en ambos |
| AAA/RADIUS Switch | Visor de eventos Windows, NPS | evento 6272 y evento 6273 |
| SNMP/Zabbix | Hosts Router y Switch desde GUI Zabbix | monitoreo SNMP comprobado en la práctica |
| Port Security | `show port-security interface gi0/3` | Secure-up, máximo 2 MAC |
| IKE | `show crypto isakmp sa` | QM_IDLE ACTIVE |
| ESP | `show crypto ipsec sa` | inbound y outbound ACTIVE(ACTIVE) |
| Ping VPN | `ping 10.21.75.1 source 10.21.74.1 repeat 5` | 5/5 (100 %) |
| Paquetes cifrados | `show crypto ipsec sa` | encaps 5 / decaps 5, 0 errores |
| Hardening | `show run ...`, `show logging` | SSH, logging, timeout 10 min, sin HTTP/HTTPS IOS |

Importante: confirmar en la grabación los resultados en vivo y no mostrar comandos con PSK ni claves. No se adjunta una captura inventada del ping VPN final.
