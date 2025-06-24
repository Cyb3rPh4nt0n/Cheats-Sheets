### Auditar CORS a un sitio web:
$ echo "{URL}" | corsme
### Auditar múltiples sitios web para CORS:
$ cat {FILE} | corsme
### Auditar CORS a un sitio web y marcar con '`*`' si encuentra el Acceess-Control-Allow-Origin:
$ echo "{URL}" | corsme -wildcard
### Auditar CORS a un sitio web y agregar un Encabezado si es necesario:
$ echo "{URL}" | corsme -header "Cookie: Session=12cvcx...."
### Auditar CORS a un sitio web y guardar el resultado en un archivo:
$ echo "{URL}" | corsme -output {FILE}
### Auditar CORS a un sitio web usando el método POST:
$ echo "{URL}" | corsme -wildcard -method "POST"