## Introducción:
Antes de sumergirnos en las diferencias entre ~/.profile y ~/.zshrc, es importante comprender para qué sirven estos archivos. Ambos son scripts de configuración de shell que se ejecutan cuando se inicia una nueva sesión de shell en sistemas Unix o Unix-like. Estos archivos contienen comandos y configuraciones personalizadas que definen el entorno del usuario, como variable de entorno, alias, funciones y otras configuraciones del sistema.
## Historia y compatibilidad:
### ~/.profile
El archivo ~/.profile ha existido desde los primeros días de UNIX y es un script de configuración que se utiliza principalmente con el shell Bourne (sh) y shells compartibles como Bash (bash). Dado que ha estado en el ecosistema UNIX desde hace mucho tiempo, es muy probable que sea compatible con la mayoría de los sistemas UNIX o Unix-like.
### ~/.zshrc
Por otro lado, ~/.zshrc es específico para el shell Zsh (zsh), que se lanzó en 1990. Zsh es un shell muy extensible y ofrece muchas características que no están disponibles en otros shells. MacOS cambió a Zsh como su shell predeterminado a partir de macOS Catalina en 2019.
## Diferencias clave:
**1. Compatibilidad de Shell:** ~/.profile es generalmente compatible con sh y shells compatibles como bash. ~/.zshrc es específico para Zsh.
**2. Ejecución de inicio:**
- ~/.profile se ejecuta para sesiones de inicio de sesión. Esto puede incluir el inicio de sesión desde la interfaz gráfica o mediante SSH.
- ~/.zshrc se ejecuta para cada nueva ventana o pestaña de terminal que utilice Zsh.
**3. Prioridad de carga:**
- En sistemas que usan Bash como el shell predeterminado, si tanto ~/.bash_profile como ~/.profile existen, sólo ~/.bash_profile se ejecutará.
- ~/.zshrc tiene prioridad en entornos donde Zsh es el shell predeterminado.
## ¿Cómo saber si el sistema utiliza uno u otro?
Para saber qué shell estás usando, puedes ejecutar el siguiente comando:
`-> echo $SHELL`
Si devuelve algo como /bin/zsh o /usr/bin/zsh, entonces estás usando Zsh y deberías considerar usar ~/.zshrc. Si devuelve /bin/bash o /bin/sh, entonces puedes usar ~/.profile (o ~/.bash_profile si estás en Bash).
## Resumen: ¿Cuándo usar qué archivo?
- Usa ~/.profile para configuraciones que son comunes a varios shells y para sesiones de inicio de sesión.
- Usa ~/.zshrc para configuraciones que son específicas de Zsh y que quieres que se apliquen en cada nueva ventana o pestaña de terminal que abras.