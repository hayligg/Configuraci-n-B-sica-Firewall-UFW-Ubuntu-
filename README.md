# Configuración-Básica-Firewall-UFW-Ubuntu
# Proyecto: Configuración básica de firewall con UFW en Ubuntu

## Descripción
Este proyecto demuestra cómo configurar **UFW (Uncomplicated Firewall)** en Ubuntu Server para:
- Permitir tráfico HTTP/HTTPS.
- Permitir SSH para administración remota.
- Bloquear ICMP (ping) para evitar reconocimiento de red.
- Denegar puertos no utilizados (ejemplo: FTP).

## Entorno
- **Sistema operativo:** Ubuntu Server 22.04 (VM en VirtualBox).
- **Modo de red:** Adaptador puente (Bridge Adapter).
- **Herramienta de firewall:** UFW.

## Pasos realizados
1. Habilitar UFW:
   ```bash
   sudo ufw enable
