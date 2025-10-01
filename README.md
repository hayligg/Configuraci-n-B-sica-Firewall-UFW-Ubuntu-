# Configuración-Básica-Firewall-UFW-Ubuntu
# Proyecto: Configuración básica de firewall con UFW en Ubuntu
## 👤 Autor
- **Carlos Saldaña**                                                          
- **Correo**: [c.a.saldana20@gmail.com](mailto:c.a.sadlana20@gmail.com)
- **LinkedIn**: [linkedin.com/in/carlos-saldana](www.linkedin.com/in/carlossalca)

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
Permitir servicios esenciales:
  ```bash
  sudo ufw allow 22/tcp
  sudo ufw allow 80/tcp
  sudo ufw allow 443/tcp
  ```

3. Editar reglas para bloquear ICMP (ping):
  ```bash
  sudo nano /etc/ufw/before.rules
  ```

  3.1 Se comentó la línea:
  ```bash
   -A ufw-before-input -p icmp --icmp-type echo-request -j ACCEPT
  ```

4. Reiniciar UFW:
  ```bash
 sudo ufw disable
 sudo ufw enable
  ```
## Evidencias

ufw status numbered mostrando reglas activas.

ping a 8.8.8.8 bloqueado.

curl https://example.com funcionando.

nc -zv 127.0.0.1 21 mostrando puerto 21 denegado.

## Resultados

Navegación web funciona (HTTP/HTTPS permitido).

SSH sigue siendo accesible.

ICMP (ping) bloqueado → mayor seguridad contra escaneos.

Servicios no utilizados (FTP) cerrados.

Importancia en seguridad

Esta configuración demuestra el principio de mínimo privilegio en redes:

Solo los servicios necesarios están abiertos.

Se bloquea un método común de reconocimiento (ping).

Puertos innecesarios están protegidos.
