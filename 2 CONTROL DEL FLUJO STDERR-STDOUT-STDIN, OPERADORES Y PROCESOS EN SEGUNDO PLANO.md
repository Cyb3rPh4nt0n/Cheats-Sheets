# Flujos estándares en Linux: STDIN, STDOUT y STDERR

En Linux, todo comando tiene disponibles los siguientes 3 descriptores: STDIN, STDOUT y STDERR.
# Consideraciones generales de STDIN, STDOUT y STDERR

* Estos flujos también tienen un número asociado: STDIN es 0, STDOUT es 1 y STDEER es 2.
* Cuando no se especifica ninguno, se considera que se trata de STDOUT.
# STDOUT (Standard Output)

La salida estándar es hacia donde el comando envía su salida. Este flujo de datos se imprime en la consola y se envía al STDIN de un comando que lo consuma.

Ejemplo: en un directorio tenemos 2 archivos y el comando de 1 de ellos es "Contenido del archivo"

Si buscamos "Contenido" dentro de ellos obtenemos:

	$ grep Contenido *
	file1.txt:Contenido del archivo

La salida del comando se envió al STDOUT, en este caso, la consola.
# STDIN (Standard Input)

La entrada estándar proviene del teclado o de la salida de otro comando.

Ejemplo: Si listamos solamente los primeros 4 directorios o archivos del directorio raíz:

	$ ls / | head -n4
	bin
	boot
	cdrom
	dev

La salida STDOUT del comando ls se convierte en la STDIN del comando head y lo que vemos en la consola es el STDOUT del comando HEAD.
# STDERR (Standard Error)

La salida estándar de error es hacia donde el comando envía datos de error al momento de realizar su tarea. Este flujo de datos también se imprime se imprime en la consola pero NO se envía al STDIN de un comando que lo consuma.

Ejemplo: En un directorio tenemos 4 archivos cuyo contenido es "Contenido del archivo" y sobre 2 de ellos no tenemos permiso de lectura.

a) Si buscamos "Contenido" dentro de todos ellos obtenemos:

	$ grep Contenido *
	file1.txt:Contenido del archivo
	file2.txt:Contenido del archivo
	grep: file3.txt: Permiso denegado
	grep: file4.txt: Permiso denegado

Las primeras 2 líneas correspondientes a lo que se envió a STDOUT y las otras 2, a STDERR. En este caso, todo se imprime en la consola.

b) Si buscamos "Contenido" dentro de todos ellos y generamos un archivo con los que hayamos encontrado:

	$ grep Contenido * | cat > encontrados.txt
	grep: file3.txt: Permiso denegado
	grep: file4.txt: Permiso denegado

Del comando grep, solo veremos en la consola lo que se envió al STDERR dado que el STDOUT se utilizó como STDIN del comando cat.

	$ cat encontrados.txt
	file1.txt:Contenido del archivo
	file2.txt:Contenido del archivo

Viendo el contenido del archivo 'encontrados.txt' podemos notar que solamente contiene la salida STDOUT del comando grep.