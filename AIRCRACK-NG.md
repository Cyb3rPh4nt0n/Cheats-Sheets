### Cracking password dando un nombre de BSSID:
$ aircrack-ng -b {BSSID} {File.cap}
### Cracking password dando un nombre ESSID:
$ aircrack-ng -e {ESSID} {File.cap}
### Cracking password para WPA/WPA2 usando una Wordlist:
$ aircrack-ng -w {Wordlist} {File.cap}
### Cracking password para WEP dando un nombre de ESSID y almacenando en un archivo:
$ aircrack-ng -a 1 -e {ESSID} -l {output-File} {File.cap}
### Crear archivo Hashcat (HCCAP):
$ aircrack-ng -J {Name-Hashcat} {File.cap}
### Crear archivo Hashcat v3.6+ (HCCAP):
$ aircrack-ng -j {Name-Hashcat} {File.cap}