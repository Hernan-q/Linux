# Hacking

## Escaneo de puertos

```bash
nmap -p [puerto] [TARGET_IP]
```

## Conexión remota

```bash
telnet [TARGET_IP]
```

## Permisos sudo

```bash
usermod -aG sudo [usuario]
```

## Crear sistema de archivos

```bash
mkfs [sistema_de_ficheros]
# Crea archivos que se deben montar
# Se montan con: mount
# Se desmontan con: umount
```
