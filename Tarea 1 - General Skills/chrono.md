## Descripción
```
How to automate tasks to run at intervals on linux servers?

Additional details will be available after launching your challenge instance.

```
## Solución
```
porti_04@DESKTOP-8HT902T:~$  ssh picoplayer@saturn.picoctf.net -p 58598
picoplayer@saturn.picoctf.net's password:
Welcome to Ubuntu 20.04.5 LTS (GNU/Linux 6.5.0-1023-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.
Last login: Wed Sep 18 05:14:25 2024 from 177.232.7.227
picoplayer@challenge:~$ ls
picoplayer@challenge:~$ cd /etc/
picoplayer@challenge:/etc$ ls
adduser.conf            default       init.d         mailcap.order        rc0.d        subgid
alternatives            deluser.conf  inputrc        mime.types           rc1.d        subgid-
apt                     dhcp          issue          mke2fs.conf          rc2.d        subuid
bash.bashrc             dpkg          issue.net      modules-load.d       rc3.d        subuid-
bindresvport.blacklist  e2scrub.conf  kernel         mtab                 rc4.d        sudoers
binfmt.d                environment   ld.so.cache    networkd-dispatcher  rc5.d        sudoers.d
ca-certificates         fstab         ld.so.conf     networks             rc6.d        sysctl.conf
ca-certificates.conf    gai.conf      ld.so.conf.d   nsswitch.conf        rcS.d        sysctl.d
cloud                   group         legal          opt                  resolv.conf  systemd
cron.d                  group-        libaudit.conf  os-release           rmt          terminfo
cron.daily              gshadow       localtime      pam.conf             security     timezone
cron.hourly             gshadow-      login.defs     pam.d                selinux      tmpfiles.d
cron.monthly            gss           logrotate.d    passwd               shadow       ucf.conf
cron.weekly             host.conf     lsb-release    passwd-              shadow-      ufw
crontab                 hostname      machine-id     profile              shells       update-motd.d
dbus-1                  hosts         magic          profile.d            skel         wgetrc
debconf.conf            hosts.allow   magic.mime     python3              ssh          xattr.conf
debian_version          hosts.deny    mailcap        python3.8            ssl          xdg
picoplayer@challenge:/etc$ cat /etc/crontab
# picoCTF{Sch3DUL7NG_T45K3_L1NUX_d83baed1}
picoplayer@challenge:/etc$ Connection to saturn.picoctf.net closed by remote host.
Connection to saturn.picoctf.net closed.
porti_04@DESKTOP-8HT902T:~$
```

## Notas 
```
Primero me conecte al servidor mediante ssh y despues busque la carpeta /etc/ y dentro de ella busque el archivo cron, que se llamaba crontab y le hice un cat.
```

## Referencias
````

```