Linux
======

change default application
  - open file browser, such as **pcmanfm**, right click the file and select **open with**.
  - choose the program or shell command, then select some checkbox with label "always open this kind of file .."

zathura clipboard
  1. in viewer, :code:``set selection-clipboard clipboard``
  #. in ``~/.config/zathura/zathurarc`` or ``/etc/zathurarc`` add the above command


find
  1. `link https://wangchujiang.com/linux-command/c/find.html`_
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


