### Fuerza bruta con diccionario y descomprimir el archivo:
$ fcrackzip -b -D -p {Wordlist} -u {FileZip}
### Fuerza bruta, con longitud de 3 caracteres, que solo contenga caracteres en minúsculas, $ y %:
$ fcrackzip -v -b -l 3 -c 'a:$%' {FileZip}
### Romper contraseñas numéricas con una longitud específica:
$ fcrackzip -b -c '1' -l 1-3 -u {FileZip}
### Romper contraseñas que sólo contenga dígitos, a partir de la contraseña '12345':
$ fcrackzip -b -l 5 -c '1' -p 12345 {FileZip}
### Proporcionar contraseña inicial:
$ fcrackzip -b -c 'a' -p hola -u {FileZip}
### Prueba de rendimiento:
$ fcrackzip -B
### Cambiar el método de romper la contraseña:
$ fcrackzip -b -c 'a' -m 1 -u {FileZip}