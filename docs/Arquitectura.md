# Arquitectura de la infraestructura

## Visión general

La infraestructura está desplegada sobre la plataforma Clouding y utiliza una red privada virtual (VPC) para la comunicación entre servidores.

Cada máquina virtual dispone de dos interfaces de red:

- **WAN**: interfaz conectada a Internet con dirección IP pública.
- **LAN (VPC)**: interfaz conectada a la red privada `10.20.10.0/24`.

Esta arquitectura permite separar el tráfico público del tráfico interno, manteniendo una red privada para la comunicación entre servicios y la administración de la plataforma.

---

# Componentes principales

La infraestructura está formada por los siguientes elementos:

- Firewall pfSense
- Servidores Linux
- Servidores Windows
- Servicios Docker
- VPN Site-to-Site
- Red privada VPC

---

# Red pública

Cada servidor dispone de una dirección IP pública asignada por Clouding.

Esta interfaz permite:

- Publicación de servicios.
- Acceso SSH/RDP.
- Actualizaciones del sistema.
- Acceso a Internet.

No todos los servicios publicados utilizan necesariamente la VPC como puerta de salida.

---

# Red privada (VPC)

La red privada utiliza el rango:

```
10.20.10.0/24
```

Esta red se emplea para:

- Comunicación entre servidores.
- Administración interna.
- Acceso a bases de datos.
- Tráfico entre servicios.
- Acceso a través de VPN.

---

# Firewall pfSense

El firewall pfSense dispone de dos interfaces:

| Interfaz | Función |
|----------|---------|
| WAN | Conectividad pública |
| LAN | Red privada VPC |

Entre sus funciones principales se encuentran:

- VPN Site-to-Site.
- Filtrado de tráfico.
- Control de acceso.
- Enrutamiento entre redes.
- Servicios de red (DNS, si aplica).

---

# VPN

La infraestructura dispone de una VPN Site-to-Site que conecta la VPC con la red remota.

Todo el tráfico destinado a la red remota es encaminado a través de pfSense.

---

# Diagramas

Los diagramas de la infraestructura se encuentran en:

```
docs/drawio/
```

Las versiones exportadas se almacenan en:

```
docs/drawio/exports/
```

---

# Estado de la documentación

Este documento describe la arquitectura general.

La configuración detallada de cada servidor, servicio y componente de red se documenta en sus correspondientes secciones.
