### Enumerar lo que comparte un Host:
$ smbclient -L //{IP} -N
### Enumerar lo que comparte un Host en un puerto diferente:
$ smbclient -L //{IP} -N -p {PORT}
### Enumerar lo que comparte un Host usando el Nombre de grupo, usuario vacío y sin password:
$ smbclient -L {Group-Name} -I {IP} -N -U ""
### Verificar si es vulnerable a Null Sessions:
$ smbclient //{IP}/IPC$ -N
$ smbclient //{IP}/C$ -N
### Acceder y ver los archivos de una carpeta compartida (llamada WorkSharing):
$ smbclient \\\\{IP}\\WorkSharing -N
### Acceder y ver los archivos de una carpeta compartida (llamada secret) proporcionando un usuario y en un puerto diferente:
$ smbclient \\\\{IP}\\secret -U '{USER}' -p {PORT}
### Acceder a directorio usando un Hash NTLM:
$ smbclient \\\\{IP}\\WorkSharing -U '{USER}' --pw-nt-hash '{NTLM-HASH}'
### Acceder a directorio usando un Hash NTLM:
$ smbclient //{IP}/Users -U '{USER}' --password='{NTLM-HASH}' --pw-nt-hash
### Listar carpetas compartidas colocando un protocolo:
$ smbclient -L {IP} -N --option 'client min protocol = NT1'