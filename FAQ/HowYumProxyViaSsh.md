* add blew line to /etc/yum.conf to **A client**  
 `proxy=http://135.251.228.199:7777`

* excute blow command to **B server** 
 `/usr/bin/ssh -i /home/fabius8/.ssh/id_rsa -NfL 0.0.0.0:7777:135.245.48.34:8000 135.251.228.199`

