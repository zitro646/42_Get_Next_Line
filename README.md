
# Get Next Line

## Descripción

La función `get_next_line` es una implementación que lee líneas de un archivo o de la entrada estándar (stdin) utilizando un descriptor de archivo. Repetidos llamados a esta función permiten leer el archivo línea por línea.

- La función debe devolver una línea leída desde el descriptor de archivo especificado.
- Si no hay más líneas para leer o si ocurrió un error, debe devolver `NULL`.
- La línea devuelta debe incluir el carácter de nueva línea (`\n`), a menos que el final del archivo no termine con un `\n`.

## Prototipo

```c
char *get_next_line(int fd);
```

## Parámetros

- **fd**: El descriptor de archivo desde el cual se va a leer. Puede ser cualquier archivo abierto o `STDIN` (entrada estándar).

## Valor de retorno

- **Línea leída**: Si se lee una línea con éxito, se devuelve una cadena con la línea leída (incluyendo el carácter de nueva línea, si aplica).
- **NULL**: Si no hay más datos para leer o si ocurre un error.

## Funciones externas utilizadas

- **read**: Para leer datos desde el descriptor de archivo.
- **malloc**: Para la asignación dinámica de memoria.
- **free**: Para liberar la memoria previamente asignada.


## Descripción detallada

La función `get_next_line` debe ser capaz de leer líneas de un archivo, devolviendo una línea a la vez. Si el final del archivo es alcanzado o si ocurre algún error, la función debe devolver `NULL`.

### Características clave:

- **Líneas completas**: La función debe devolver una línea completa, incluyendo el carácter de nueva línea (`\n`), a menos que el archivo termine sin una nueva línea al final.
- **Manejo de archivos y `stdin`**: La función debe funcionar tanto para archivos abiertos como para la entrada estándar (usando el descriptor de archivo `STDIN`).
- **Lecturas repetidas**: La función debe permitir leer el archivo línea por línea a través de llamadas repetidas a `get_next_line()`.
- **Gestión de memoria**: La memoria debe ser gestionada adecuadamente utilizando `malloc` para asignar espacio para las líneas leídas y `free` cuando sea necesario.
- **Tamaño del búfer (`BUFFER_SIZE`)**: El tamaño del búfer utilizado en la función `read()` debe definirse mediante la opción `-D BUFFER_SIZE=n` en la compilación. Este valor de tamaño de búfer será modificado durante las evaluaciones del proyecto, y tu código debe manejar adecuadamente diferentes tamaños de búfer. El valor de `BUFFER_SIZE` debe ser capaz de ser modificado sin necesidad de recompilar el código, y el comportamiento del código debe ser correcto tanto con un tamaño de búfer fijo como cuando se cambia.


## Compilacion
```bash
cc -std=c99 -Wall -Wextra -Werror -D BUFFER_SIZE=42 get_next_line.c get_next_line_utils.c main.c -o test
```

