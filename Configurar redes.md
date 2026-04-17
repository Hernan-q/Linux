# Configurar Redes

## Comandos de Red

```bash
# Ver configuración de interfaces de red
ip addr show
ifconfig

# Configurar dirección IP estática
sudo ip addr add 192.168.1.100/24 dev eth0

# Activar/desactivar interfaz de red
sudo ip link set eth0 up
sudo ip link set eth0 down

# Configurar puerta de enlace (gateway)
sudo ip route add default via 192.168.1.1

# Ver tabla de rutas
ip route show

# Configurar DNS
sudo nano /etc/resolv.conf
# Agregar: nameserver 8.8.8.8

# Reiniciar servicio de red
sudo systemctl restart networking

# Ver estado de conexión
ip link show
ping 8.8.8.8

# Configurar DHCP
sudo dhclient eth0

# Ver configuración actual
ip addr
ip route
```

## Archivos de Configuración

### 1. Resolución de nombres (DNS)

**`/etc/resolv.conf`**
```
nameserver 8.8.8.8
nameserver 8.8.4.4
```

### 2. Configuración de interfaces (Debian/Ubuntu)

**`/etc/network/interfaces`**
```
auto eth0
iface eth0 inet static
  address 192.168.1.100
  netmask 255.255.255.0
  gateway 192.168.1.1
```

### 3. Netplan (Ubuntu 18.04+)

**`/etc/netplan/01-netcfg.yaml`**
```yaml
network:
  version: 2
  ethernets:
    eth0:
      dhcp4: no
      addresses: [192.168.1.100/24]
      gateway4: 192.168.1.1
      nameservers:
        addresses: [8.8.8.8, 8.8.4.4]
```

### 4. Red Hat/CentOS

**`/etc/sysconfig/network-scripts/ifcfg-eth0`**
```
DEVICE=eth0
BOOTPROTO=static
ONBOOT=yes
IPADDR=192.168.1.100
NETMASK=255.255.255.0
GATEWAY=192.168.1.1
```

### 5. Otros archivos

| Archivo | Descripción |
|---------|-------------|
| `/etc/hostname` | Nombre del equipo |
| `/etc/hosts` | Resolución local de nombres |
| `/etc/systemd/network/` | Configuración systemd |
| `/etc/dhcp/dhclient.conf` | Configuración DHCP |

## Servidor DHCP

### Instalación

```bash
# Debian/Ubuntu
sudo apt install isc-dhcp-server

# Red Hat/CentOS
sudo yum install dhcp
```

### Configuración

**`/etc/dhcp/dhcpd.conf`**
```dhcp
authoritative;
default-lease-time 600;
max-lease-time 7200;

subnet 192.168.1.0 netmask 255.255.255.0 {
  range 192.168.1.100 192.168.1.200;
  option routers 192.168.1.1;
  option subnet-mask 255.255.255.0;
  option domain-name-servers 8.8.8.8, 8.8.4.4;
  option domain-name "midominio.local";
}

# IP fija para cliente
host cliente1 {
  hardware ethernet 00:11:22:33:44:55;
  fixed-address 192.168.1.50;
}
```

### Interfaz de escucha

**`/etc/default/isc-dhcp-server`**
```
INTERFACES="eth0"
```

### Iniciar servicio

```bash
sudo systemctl start isc-dhcp-server
sudo systemctl enable isc-dhcp-server
sudo systemctl status isc-dhcp-server
```
