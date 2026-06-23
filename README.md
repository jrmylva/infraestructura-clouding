# Infraestructura Clouding

Repositorio de documentación de la infraestructura desplegada en Clouding.

## Objetivos

- Documentar la arquitectura de la plataforma.
- Mantener un inventario actualizado de servidores y servicios.
- Documentar la red, VPN y firewall.
- Centralizar la información técnica de la infraestructura.
- Facilitar el mantenimiento y la incorporación de nuevos administradores.

## Infraestructura

La plataforma está desplegada sobre Clouding y utiliza una VPC privada (`10.20.10.0/24`).

Cada servidor dispone de:

- Una interfaz WAN con IP pública.
- Una interfaz LAN conectada a la VPC.

El firewall pfSense proporciona:

- Acceso VPN Site-to-Site.
- Segmentación de la red privada.
- Control de acceso entre redes.

## Documentación

```
docs/
```

Contiene toda la documentación técnica de la infraestructura.

## Diagramas

Los diagramas de red están desarrollados con Draw.io y se encuentran en:

```
docs/drawio/
```

Las versiones exportadas (PNG/SVG) se almacenan en:

```
docs/drawio/exports/
```

## Estado

🚧 Documentación en desarrollo.
