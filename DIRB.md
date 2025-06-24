### Fuzzing a una URL y con una wordlist por default:
$ dirb {URL}
### Fuzzing a una URL y usando una wordlist definida:
$ dirb {URL} -w {WORDLIST}
### Fuzzing a una URL, usando una wordlist definida y guardar el resultado en un archivo:
$ dirb {URL} -w {WORDLIST} -o {FILENAME}
### Fuzzing a una URL, usando una wordlist definida e ignorando la respuesta del código 404 HTTP:
$ dirb {URL} -w {WORDLIST} -N 404
### Buscando por las extensiones PHP y txt:
$ dirb {URL} -w {WORDLIST} -X ".php,.txt"
### Buscando desde un listado de extensiones:
$ dirb {URL} -w {WORDLIST} -x {ExtsFile}
### Fuzzing a una URL y usar Recursividad en los directorios encontrados:
$ dirb {URL} -w {WORDLIST} -R
### Fuzzing a una URL y especificando un User-Agent:
$ dirb {URL} -w {WORDLIST} -a {AgentString}
### Fuzzing a una URL y usar un proxy:
$ dirb {URL} -p `{URL-Proxy[:port]}`
### Fuzzing a una URL, usando una Cookie:
$ dirb {URL} -c {COOKIE-STRING}
### Fuzzing a una URL y usando Autenticación HTTP:
$ dirb {URL} -w {WORDLIST} -u {USERNAME:PASSWORD}
### Fuzzing a una URL y usar un encabezado personalizado:
$ dirb {URL} -H {Header-String}