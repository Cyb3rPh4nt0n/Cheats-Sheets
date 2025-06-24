### Revisar si un sitio web es vulnerable a LFI:
`$ dotdotpwn -m http-url -d 10 -f /etc/passwd -u "http://test.com?lang=TRAVERSAL" -b -k "root:"`
### Revisar si un sitio web es vulnerable a LFI y guardarlo en un archivo:
`$ dotdotpwn -m http-url -d 10 -f /etc/passwd -u "http://test.com?lang=TRAVERSAL" -b -k "root:" -r {OUTPUT.txt}