# Redes

## Ver IP

```bash
ifconfig | grep eth0 | grep inet
ip addr show
```

## Puertos y conexiones

```bash
netstat -tulpn          # Puertos abiertos
ss -tulpn              # Similar a netstat
```

## Firewall

```bash
iptables                # Configurar firewall
ufw allow 80            # Abrir puerto 80
```

## Información del sistema

```bash
neofetch               # Información del sistema
history                # Historial de comandos
![numero]              # Ejecutar comando del historial
```
