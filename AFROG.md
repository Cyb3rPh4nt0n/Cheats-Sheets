### Escaneo de vulnerabilidades a un sitio web:
$ afrog -t {URL}
### Escaneo de vulnerabilidades a múltiples URLs:
$ afrog -T urls.txt
### Escaneo de vulnerabilidades a un sitio web solo mostrando vulnerabilidades altas y críticas (pueden ser info, low, medium, high y critical):
$ afrog -t {URL} -S high,critical
### Escaneo de vulnerabilidades a un sitio web y guardar el resultado en un archivo HTML:
$ afrog -t {URL} -o {OUTPUT}