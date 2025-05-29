### Comprobar si un host es propiedad de CloudFlare:
$ echo "{HOST}" | cf-check
### Comprobar si un host es propiedad de CloudFlare y solo mostrar el dominio en lugar de la dirección IP:
$ echo "{HOST}" | cf-check -d