# Guion de demostración (hasta 10 min)

**0:00–0:35** Presentación, matrícula 2025-2174, fecha/hora visible y topología GNS3, hablar frente a cámara según consigna.

**0:35–1:40** Router `show ip interface brief`, `show ip dhcp binding`: red LAN y FortiGate.

**1:40–2:35** SSH con PuTTY al Router `10.21.74.1` y Switch `10.21.74.2` (sin revelar contraseñas).

**2:35–3:50** Windows NPS: usuarios autorizados y evento 6272; evento 6273 denegado (sin generar bloqueos inesperados).

**3:50–4:50** Zabbix: mostrar hosts de Router/Switch en estado disponible SNMP.

**4:50–6:40** FortiGate GUI mostrar `VPN-CISCO-2174` y Cisco `show crypto isakmp sa`; `ping 10.21.75.1 source 10.21.74.1 repeat 5`; `show crypto ipsec sa` y contadores.

**6:40–8:10** Router y Switch: SSH v2, `show logging`, VTY timeout, HTTP deshabilitado; `show port-security` y `gi0/3`.

**8:10–9:20** Explicar límites: DES en demo, SNMPv2c, Router SSH local vs Switch NPS, credenciales censuradas. Mostrar README Github.

**9:20–9:45** Cierre con validaciones y repositorio. Duración < 10 min.
