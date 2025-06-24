### Enumerar los DNS de un dominio:
$ dnsenum --enum {Domain}
### Enumerar los DNS de un dominio y guardar el resultado en un archivo XML:
$ dnsenum --enum {Domain} --output {FIle}
### Enumerar dominios usando Bruteforce desde una lista de un archivo:
$ dnsenum -f {FileSubdomain} -r {Domain}
### Guardar todos los subdominios validos en un archivo:
$ dnsenum {Domain} --subfile {File}