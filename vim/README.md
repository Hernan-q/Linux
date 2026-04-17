# Vim Commands

## Navegación

| Comando | Descripción |
|---------|-------------|
| `h` | Mover a la izquierda |
| `j` | Mover abajo |
| `k` | Mover arriba |
| `l` | Mover a la derecha |
| `w` | Siguiente palabra |
| `b` | Palabra anterior |
| `0` | Inicio de línea |
| `$` | Fin de línea |
| `gg` | Inicio del archivo |
| `G` | Fin del archivo |
| `:n` | Ir a línea n |

## Edición

| Comando | Descripción |
|---------|-------------|
| `i` | Insertar antes del cursor |
| `a` | Insertar después del cursor |
| `o` | Nueva línea abajo |
| `O` | Nueva línea arriba |
| `x` | Eliminar carácter |
| `dd` | Eliminar línea |
| `d$` | Eliminar hasta fin de línea |
| `u` | Deshacer |
| `Ctrl+r` | Rehacer |

## Selección y Copia

| Comando | Descripción |
|---------|-------------|
| `v` | Modo visual (por caracteres) |
| `V` | Modo visual (por líneas) |
| `Ctrl+v` | Modo visual (bloque) |
| `y` | Copiar (yank) |
| `p` | Pegar después |
| `P` | Pegar antes |

## Buscar y Reemplazar

| Comando | Descripción |
|---------|-------------|
| `/patrón` | Buscar adelante |
| `?patrón` | Buscar atrás |
| `n` | Siguiente coincidencia |
| `N` | Coincidencia anterior |
| `:%s/old/new/g` | Reemplazar todo |

## Guardar y Salir

| Comando | Descripción |
|---------|-------------|
| `:w` | Guardar |
| `:q` | Salir |
| `:wq` | Guardar y salir |
| `:q!` | Salir sin guardar |

## Otros

```bash
:set number    " Mostrar números de línea
:set nonumber  " Ocultar números de línea
```
