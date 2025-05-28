### Scan types:
-sS: Escaneo SYN "Half-open"
-sT: Escaneo TCP
-sU: Escaneo UDP
-sA: Escaneo ACK
-sW: Escaneo a equipos Windows
-sM: Escaneo TCP Maimon
-sR: Escaneo RPC
-sX: Escaneo XMAS
-sN: Escaneo NULL de TCP
-sF: Escaneo TCP FIN
-sI: Escaneo IDLE/IPID Header (Zommbie Scan)
-sY: Escaneo SCTP INIT
-sZ: Escaneo SCTP COOKIE ECHO
-so: Escaeno protocolo IP
-Pn: Deshabilitar descubrimientos de host. Solamente escaneo de puertos
### Host Discovery:
-sP: Escaeneo con Ping
-sL: No escanear. Listar solamente objetivos
-sn: Deshabilitar Escaneo de puertos (ping sweep)
-PS: Escaneo TCP SYN ping
-PA: Escaeno TCP ACK ping
-PU: Escaneo UDP ping
-PR: Escaneo ARP ping
-PE: Escaneo ICMP ECHO ping
-PE {IP-Range}: Escaneo ICMP ECHO ping sweep
-PP: Escaneo ICMP timestamp ping.
-PM: Escaneo ICMP address mask ping
-PO: Escaneo IP Protocol ping
-PY: Escaneo SCPT ping
-PN: No hacer ping
-n: No resolución DNS
### Scan options:
-p{Port-Range}: Rango de puertos
-p-: Escaneo de todos los puertos
-pU:53,U:110,T:20-445: Escaneo mixto TCP y UDP
--top-ports {number}: Escaneo del top de puertos especificados
--open: Escaneo de puertos abiertos
-F: Escaneo rápido (Escanea los 100 puertos más populares)
--spoof-mac {MAC}: Envía tramas ethernet a la dirección MAC especificada
-e {interface}: Define Interfaz
--interactive: Modo interactivo
-r: No aleatorio
### Service/Version Detection:
-sV: Información de Servicio/Versión
-sV --version-all: Información de Servicio/Versión cuando correo en un puerto no estándar, más lento
-sV --version-intensity 9: Información de Servicio/Versión cuando correo en un puerto no estándar
-sV --version-light: Información de Servicio/Versión, más rápido
### Input options:
-iL {filename}: Escaneo de objetivos desde un archivo
-iR {num-hosts}: Escaneo aleatorio de hosts
--exclude {host1{host2}...}: Excluir escaneo de hosts
--exclude {filename}: Excluir del escaneo desde un archivo con listado de hosts
### Output options:
-oN: Formato estándar de NMAP
-oX: Formato XML
-oG: Formato grepeable
-oS: Formato Script Kiddies
-oA: Salida en 3 formatos (Normal, XML y Grepeable)
-v: Aumente el nivel de verbosidad
-vvv: Verbosidad a más detalle
### OS detection:
-A: Detección de SO, version, script de escaneo y traceroute
-sV -O: Detección de SO
-sV -O --osscan-guess: Detección de OS manera agresiva
-sV -O --osscan-limit: Limitar la detección del OS
-sV -O --max-os-tries: Establece el número máximo x intentos de detección contra el objetivo
### Timing:
-T0: Paranoico
-T1: Sigiloso
-T2: Sofisticado
-T3: Normal
-T4: Agresivo
-T5: Loco
--max-rate {number}: Envía paquetes no más rápido que 'cantidad' por segundo
--min-rate {number}; Envía paquetes no más lentos que 'cantidad' por segundo
--max-retries {tries}: Especifique el número máximo de retransmisiones de la sonda de escaneo de puertos
### Misc:
-V: Imprime la versión de NMAP
-N: Resolución DNS
-R: Reverse Lookup
-6: Habilitar IPv6
--scan-delay {time}ms: Agrega un retraso entre los paquetes enviados
--badsum: Genera una suma de comprobación no válida para paquetes
-h: Panel de Ayuda
### NSE scripts:
-sC: Escanear con scripts NSE por default
--script default: Escanear con scripts NSE por default
--script {Script-Name}: Escanear con un script en particular
--script {NSE-Categories}: Escanear con algunas categorías de NSE
--script-args {Script-Name}.{Argument}: Si algún script requiere algun argumento
--script-help {script-name}: Mostrar la ayuda del script a usar
--script-updatedb: Actualizar la base de datos de scripts
### Firewall/IDS Evasion:
-f: Fragmentación de paquetes
-g {Port-Number}: Manipulación del puerto origen
--mtu {Number}: Fragmentación más controlada de paquetes
-D: Escaneo de señuelos
-S: Falsear dirección de origen
RND:{Number}: Genera direcciones IP aleatorias y no reservadas
--data {Hexadecimal}: Para enviar los datos binarios (0's y 1's) como cargas útiles en los paquetes enviados
--data-length {Number}: Agrega datos aleatorios a los paquetes enviados
--data-string {String}: Para enviar una cadena regular como cargas útiles en los paquetes enviados a la máquina de destino
--randomize-host: Para escanear la cantidad de hosts en la red de destino en orden aleatorio
--badsum: Para enviar los paquetes con sumas se comprobación TCP/UDP erróneas o falsas al objetivo previsto para enviar ciertos conjuntos de reglas de firewall
### Script Categories:
locate .nse | xargs grep "categories" | grep -oP '".?"' | sort -u: Listar las categorías de NSE
/usr/share/nmap/scripts: Directorio donde están almacenados los scripts en Linux
nmap --script-help {script.nse}: Muestra información detallada del uso del script NSE
safe: Ejecuta scripts que no son intrusivos
intrusive: Utiliza scripts que son considerados intrusivos para la víctima o objetivo
vuln: Descubre las vulnerabilidades más conocidas
exploit: Intento de aprovechar una vulnerabilidad
auth: Ejecutar todos sus scripts disponibles para autentificación
brute: Intento de usar la fuerza bruta de las credenciales para ejecutar servicios
discovery: Intente consultar los servicios en ejecución para obtener más información sobre la red (por ejemplo, consultar un servidor SNMP)
external: Script para utilizar recursos externos
default: Ejecuta los scripts básicos por defecto de la herramienta
malware: Revisa si hay conexiones abiertas por códigos maliciosos o backdoors (puertas traseras)
all: Ejecuta absolutamente todos los scripts con extensión NSE disponibles
### Ports Status:
Puerto filtrado: Un firewall (cortafuegos) bloquea el acceso al puerto
Puerto cerrado: El puerto no está bloqueado pero no hay ninguna aplicación escuchando en él
Puerto abierto: El puerto no está bloqueado y hay una aplicación escuchando en él
### Escaneo agresivo:
$ nmap -sS -n -Pn -p- --max-rtt-timeout 100ms --min-parallelism 1000 {IP}
### Escaneo para evadir Firewall:
$ nmap -sS -T1 --max-rate 50 --scan-delay 5s -f -n -PN {IP}
### Escaneo rápido para descubrir puertos abiertos:
$ nmap -sS -p- --open --min-rate 5000 -vvv -n -Pn {IP}