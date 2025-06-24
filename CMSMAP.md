### Escaneo a un sitio de CMS:
$ cmsmap {URL}
### Escaneo full a un sitio de WordPress y enumerando plugins:
$ cmsmap {URL} -f W -F --noedb -d
### Escaneo a multiples sitios a través de un listado en un archivo y guardar el resultado en un archivo:
$ cmsmap {URL} -i {FILE} -o {OUTPUT}
### Ataque de fuerza bruta para adivinar la contraseña de un usuario en particular usando una Wordlist:
$ cmsmap {URL} -u {USER} -p {WORDLIST}
### Crackear un archivo de hashes:
$ cmsmap -k {HASHSE-FILE} -w {WORDLIST}