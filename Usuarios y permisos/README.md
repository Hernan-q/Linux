# Usuarios y Permisos

## Ver información de usuarios

```bash
getent passwd ...
id ...
```

## Crear usuarios

```bash
sudo useradd [usuario]
sudo adduser
sudo passwd [usuario]
```

## Grupos

```bash
groupadd [nombre]
groupdel [nombre]
```

## Modificar usuario

```bash
usermod -aG [grupo] [usuario]   # Agregar a grupo (sin reemplazar)
usermod -G [grupo] [usuario]    # Reemplazar grupos
usermod -g [grupo] [usuario]    # Grupo primario
```

## Propietario

```bash
chown usuario:grupo archivo
chgrp grupo archivo
```

## Permisos

```bash
chmod [750] archivo
# Dueño: 7 (rwx) = 4+2+1
# Grupo: 5 (r-x) = 4+1
# Otros: 0 (---)

# Notación simbólica:
chmod u+rwx,g+rx,o-rwx archivo
# u=user, g=group, o=others, a=all
# r=read, w=write, x=execute
```

## Permisos Especiales

| Tipo | Comando | Descripción |
|------|---------|-------------|
| SUID | `chmod 4755 archivo` | Ejecutar como dueño |
| SGID | `chmod 2755 archivo` | Mantener grupo en subdirectorios |
| Sticky | `chmod 1755 archivo` | Solo dueño puede borrar |

```bash
# Agregar
chmod u+s archivo
chmod g+s archivo
chmod +t directorio

# Quitar
chmod u-s archivo
chmod g-s archivo
chmod -t directorio
```

## Atributos de filesystem

```bash
# Ver atributos
lsattr archivo

# Agregar inmutabilidad (no se puede modificar ni borrar)
chattr +i archivo

# Quitar inmutabilidad
chattr -i archivo
```
