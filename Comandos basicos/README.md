# Comandos Básicos de Linux

## Navegación

- `cd ..` - Cambiar al directorio padre
- `ls -l -a -h` - Listar archivos con detalles (incluyendo ocultos y tamaños legibles)
- `pwd` - Mostrar directorio actual
- `stat` - Información de los inodos

## Archivos

- `""` - Indica que lo que sigue no es una opción sino un nombre de archivo
- `ln [-s]` - Crear enlace simbólico (soft)
  - Hard links: enlaza inodos, hasta no borrar el enlace no se pierde el contenido
  - También copia los permisos

## Paquetes

- `apt install` - Instalar paquete
- `apt remove [--purge]` - Eliminar paquete (--purge borra configuraciones)

## Visualización

- `cat -n` - Ver contenido con números de línea
- `more` / `less` - Navegar contenido paginado
- `head -n1` - Ver primera línea
- `tail -f` - Monitorear cambios en tiempo real

## Discos

- `fdisk -l` - Ver información de discos y manipular tabla de particiones

## Comparación

- `cmp` - Comparar archivos
- `diff` - Mostrar diferencias entre archivos

## Directorios

- `mkdir` - Crear directorio
- `rmdir` - Eliminar directorio vacío
- `rm -r` - Eliminar directorio con contenido

## Copiar y Mover

- `cp archivo /ruta/` - Copiar archivo
- `mv archivo destino` - Mover o renombrar

## Información

- `whatis` - Descripción de comandos
- `which` - Ver ruta de un comando
- `where` - Ubicación de ejecutables
- `man` - Manual de comandos

## Descargas

- `wget` - Descargar archivos
