### Fuzzing a sitio web usando una lista de palabras:
`$ dirsearch -u http://target -w {Wordlist}`
### Búsqueda de extensiones por default:
`$ dirsearch -u http://target -E -w {Wordlist}`
### Búsqueda de extensiones colocadas por el usuario:
`$ dirsearch -u http://target -e html,php,txt -w {Wordlist}`
### Fuzzing a sitio web, excluyendo código de error 404 y 403, con 500 hilos, y guardar el resultado en un reporte simple:
`$ dirsearch -u http://target -w {Wordlist} -t 500 -x 404,403 --simple-report={OutFile}`
### Búsqueda de forma recursiva en los directorios encontrados:
`$ dirsearch -u http://target -w {wordlist} -e php -x 403,301,302 -r`
### Búsqueda de forma recursiva en los directorios encontrados con una profundidad de nivel 3:
`$ dirsearch -u http://target -w {Wordlist} -e php -x 403,301,302 -r -R 3`
### Fuzzing a sitio web usando un User-Agent random:
`$ dirsearch -u http://target -e {Wordlist} --random-agent`