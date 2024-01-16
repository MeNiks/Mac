```
On ubuntu firewall is by default installed
but if uninstalled can be installed using

>sudo apt install ufw

>sudo ufw allow ssh

22 is the port that the SSH daemon listens on by default
>sudo ufw allow 22

Specific Port Ranges
>sudo ufw allow 6000:6007/tcp
>sudo ufw allow 6000:6007/udp

Specific IP Addresses
>sudo ufw allow from 203.0.113.4

Specific IP Addresses Specific Port
>sudo ufw allow from 203.0.113.4 to any port 22

Enabling UFW (Enable firewall this will deny incoming connection for the rules you have set)
>sudo ufw enable

To check status
>ufw status verbose

Check local ports
>netstat -an | grep tcp | grep LIST
```

## SSH
```
Login to remote system
> ssh niks@google.com
niks - username
google.com - is server domain it can also be ip address

Port forwarding (https://www.youtube.com/watch?v=x1yQF1789cE)
> ssh -N -L localhost:8888:localhost:80 root@159.223.180.93

-N - Do not enter in ssh machine
-L - Local port fordwarding

```
