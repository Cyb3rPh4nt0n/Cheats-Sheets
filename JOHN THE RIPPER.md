### Mostrar los tipos de contraseñas que John puede descifrar con la velocidad del crack (crack/segundo):
$ john --test
## Modos de Cracking:
### Para usar una lista de palabras:
$ john --wordlist={WORDLIST} {PASSWORD_FILE}
### Modo incremental (Brute Force):
$ john --incremental {HASH_FILE}
### Usar una wordlist y una regla:
$ john --wordlist={WORDLIST} {PASSWORD_FILE} --rules={RULES_NAME}
### Mostrar el listado de formatos que se pueden usar:
$ john --list=formats
### Forzar hash a un tipo de formato (Ejemplo formato NT):
$ john --format=NT {HASH_FILE}
### Mostrar resultados después de ejecutar John:
$ john --show {HASH_FILE}
## Sesión y Restauración:
### Restaurar una sesión de John interrumpida:
$ john --restore:{NAME}
## Reglas:
### Tipos de reglas ya definidas:
$ john --rules=Single
$ john --rules=Wordlist
$ john --rules=Extra
$ john --rules=Jumbo
$ john --rules=KoreLogic
$ john --rules=All
### Crear una regla:
List.Rules:Tryout
l
u
c
l r
l Az"2015"
d
l A0"2015"
A0"#"Az"#"
### Regla/Descripción:
l -> Convertir a minúsculas
u -> Convertir a mayúsculas
c -> Primera letra en mayúsculas
r -> Palabra al revés
d -> Duplicar
#Nota Editar el archivo 