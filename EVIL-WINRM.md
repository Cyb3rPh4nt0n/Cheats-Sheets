### Conexión usando usuario y contraseña:
$ evil-winrm -i {IP-TARGET} -u '{USER}' -p '{PASSWORD}'
### Conexión usando un NT Hash:
$ evil-winrm -i {IP-TARGET} -u '{USER}' -H '{NT-HASH}'
### Conexión por SSL y proporcionando llave pública y privada:
$ evil-winrm -i {IP-TARGET} -c {CERTIFICATE.pem} -k {PRIVATE-KEY.pem} -S

$ evil-winrm -i {IP-TARGET} -c {CERTIFICATE.pem} -k {PRIVATE-KEY.pem} -S -u '{USER}' -p '{PASSWORD}'
### Descargar un archivo dentro de sesión evil-winrm:
`Evil-WinRM> download C:\PATH\{FILE}`
### Cargar un archivo dentro de sesión evil-winrm:
`Evil-WinRM> upload {FILE}`