### Encontrar parámetros de consulta de una URL:
$ arjun -u {URL}
### Especificando un método HTTP (GET/POST/JSON/XML):
$ arjun -u {URL} -m POST
### Encontrar parámetros de consulta desde un archivo que contiene listado de objetivos:
$ arjun -i {URLS_FILE}
### Guardar los resultados en un archivo:
$ arjun -u {URL} -oJ result.json
-oJ result.json : archivo JSON
-oT result.txt : archivo de texto
-oB result.127.0.0.1:8080 : exportar a BurpSuite
### Encontrar parámetros de consulta de una URL y usar hilos:
$ arjun -u {URL} -t 10
### Encontrar parámetros de consulta de una URL y usar un Delay entre cada petición:
$ arjun -u {URL} -d 2
### Encontrar parámetros de consulta de una URL y deshabilitar el redirect:
$ arjun -u {URL} -disable-redirects
### Encontrar parámetros de consulta de una URL y usar una cabecera HTTP personalizada:
$ arjun -u {URL} --headers "Accept-Language: en-US\nCookie: null"
### Búsqueda pasiva de parámetros:
$ arjun -u {URL} -oT {OUTPUT.txt} -t 10 --rate-limit 10 --passive -m GET,POST --headers "User-Agent: Mozilla/5.0"
### Búsqueda activa de parámetros:
$ arjun -u {URL} -oT {OUTPUT.txt} -t 10 -m GET,POST -w {WORDLIST} -t 10 --rate-limit 10 --headers "User-Agent: Mozilla/5.0"