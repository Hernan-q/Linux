# Montar Discos y LVM

## RAID (mdadm)

```bash
# Instalar
apt install mdadm

# Crear RAID
mdadm --create --v /dev/md0 --level=10 --raid-devices=3 /dev/sdb1 /dev/sdc1 /dev/sdd1

# Agregar dispositivo
mdadm --manage /dev/[nombre] --add /dev/[dispositivo]

# Detener RAID
mdadm --stop /dev/[nombre]

# Eliminar superblock
mdadm --zero-superblock [ruta]
```

## LVM - Volúmenes Lógicos

### Physical Volumes (PV)

```bash
# Crear volumen físico
pvcreate /dev/sdf /dev/sdg

# Mostrar atributos
pvdisplay

# Información
pvs

# Eliminar volumen
pvremove /dev/sdg
```

### Volume Groups (VG)

```bash
# Crear grupo
vgcreate cursoadm /dev/sdf /dev/sdg

# Mostrar atributos
vgdisplay cursoadm

# Extender grupo
vgextend cursoadm /dev/sdh

# Reducir grupo
vgremove /dev/sdh

# Renombrar
vgrename cursoadm cursoadmnuevo
```

### Logical Volumes (LV)

```bash
# Crear volumen lógico (por tamaño)
lvcreate --name operador --size 300M cursoadm
lvcreate --name admin --size 500M cursoadm

# Crear volumen lógico (usar todo el espacio libre)
lvcreate --name redes --extents 100%FREE cursoadm

# Mostrar
lvdisplay
lvs cursoadm/operador

# Renombrar
lvrename cursoadm admin nivelador

# Eliminar
lvremove cursoadm/nivelador
```
