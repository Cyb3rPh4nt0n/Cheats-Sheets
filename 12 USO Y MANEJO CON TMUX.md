## SESIONES:
### Iniciar una nueva sesión:
tmux
tmux new
tmux new-session
:new
### Empezar una nueva sesión con el nombre 'mysession':
tmux new -s mysession
:new -s mysession
### Matar/borrar la sesión mysession:
tmux kill-session -t mysession
### Matar/borrar todas las sesiones excepto la actual:
tmux kill-session -a
### Matar/borrar todas las sesiones menos 'mysession':
tmux kill-session -a -t mysession
### Renombrar todas las sesiones:
Ctrl + b $
### Desvincularse de la sesión:
Ctrl + b d
### Mostrar todas las sesiones:
tmux ls
Ctrl + b s
### Sincronizarse a la última sesión:
tmux a
tmux at
tmux attach
tmux attach-session
### Sincronizarse a la sesión con nombre 'mysession':
tmux a -t mysession
tmux attach-session -t mysession
### Moverse a la sesión anterior:
Ctrl + b (
### Moverse a la siguiente sesión:
Ctrl + b )
## VENTANAS:
### Empezar una nueva sesión con nombre 'mysession' y nombre de ventana 'mywindow':
tmux new -s mysession -n mywindow
### Crear una nueva ventana:
Ctrl + b c
### Renombrar la ventana actual:
Ctrl + b ,
### Redimensionar la altura del panel actual:
Ctrl + b + ↑ (↓)
### Redimensionar la anchura del panel actual:
Ctrl + b + → (←)
### Cerrar el panel actual:
Ctrl + b x
## MODO COPIA:
### Utilizar las teclas de vi en el buffer:
setw -g mode-keys vi
### Entrar en el modo copia:
Ctrl + b `[`
### Desplazarse una página hacia arriba:
Ctrl + b PgUp
### Modo salida:
q
### Ir a la línea superior:
g
### Ir a la línea inferior:
G
### Desplazarse hacia arriba:
↑
### Desplazarse hacia abajo:
↓
### Mover el cursor a la izquierda:
h
### Mover el cursor abajo:
j
### Mover el cursor arriba:
k
### Mover el cursor a la derecha:
l
### Mover el cursor hacia adelante una palabra a la vez:
w
### Mover el cursor hacia atrás una palabra a la vez
b
### Búsquedas hacia adelante:
/
### Búsqueda hacia atrás:
?
### Siguiente palabra clave:
n
### Cerrar la ventana actual:
Ctrl + b &
### Ventana anterior:
Ctrl + b p
### Ventana siguiente:
Ctrl + b n
### Alternar/seleccionar ventana por números:
Ctrl + b 0 ... 9
### Reordenar ventanas, intercambiar la ventana 2 (origen) por la 1 (destino):
swap-window -s 2 -t 1
### Mover la ventana actual a la izquierda en una posición:
swap-window -t -1
## PANELES:
### Conmutar el último panel activo:
Ctrl + b ;
### Dividir el panel verticalmente:
Ctrl + b %
### Dividir el panel horizontalmente:
Ctrl + b "
### Mueve el panel actual a la izquierda:
Ctrl + b {
### Mueve el panel actual a la derecha:
Ctrl + b }
### Intercambia el panel en la dirección indicada:
Ctrl + b ↑ (↓,→,←)
### Sincronizar paneles (enviar el comando indicado a todos los paneles):
setw synchronize-panes
### Alternar entre los diseños de los paneles:
Ctrl + b Spacebar
### Cambiarse al siguiente panel:
Ctrl + b o
### Mostrar los números de los paneles:
Ctrl + b q
### Alternar/seleccionar panel por número:
Ctrl + b q 0 ... 9
### Establecer zoom en el panel actual:
Ctrl + b z
### Convierte el panel en una ventana:
Ctrl + b !
### Ocurrencia de la palabra clave anterior:
N
### Iniciar selección:
Spacebar
### Limpiar selección:
Esc
### Copiar selección:
Enter
### Pegar contenido del buffer_0:
Ctrl + b ]
### Mostrar contenido del buffer_0:
show-buffer
### Copiar todo el contenido visible del panel a un buffer:
capture-pane
### Mostrar todos los buffers:
list-buffers
### Mostrar todos los buffers y pegar lo seleccionado:
choose-buffer
### Guardar el contenido del buffer en buf.txt:
save-buffer buf.txt
### Borrar buffer_1:
delete-buffer -b 1
## VARIOS:
### Entrar en modo comandos:
Ctrl + b :
### Establecer un OPTION para todas las sesiones:
set -g OPTION
### Establecer un OPTION para todas las ventanas:
setw -g OPTION
### Mostrar cada sesión, ventana, panel, etc.
tmux info
### Mostrar shortcuts:
Ctrl + b ?