# openvpn3

# vpn autoload

```
$ mkdir -m700 -p $HOME/.openvpn3/autoload

# copy client.ovpn inside autoload director

# create a file client.autload (should same name client and client)

# inside client.autoload

 $ cat client.autoload 
{
    "autostart": true,
    "user-auth": {
        "autologin": true,
        "username": "",
        "password": ""
    }
}

openvpn3-autoload --directory $HOME/.openvpn3/autoload

also

sudo sh -c 'echo "nameserver 10.0.0.2" >> /etc/resolv.conf.head'

```

# /etc/resolv.conf was getting changed

so 

```
sudo sh -c 'echo "nameserver 10.0.0.2" >> /etc/resolv.conf.head'

also remove it when disconnected

nslookup google.com  will show which dns server its using
```

# how to view log vpn
```
openvpn3 log --log-level 6 --session-path /net/openvpn/v3/sessions/21cac29cs6ae5s4637sab69s4cd790c08fc6

openvpn3 session-manage --session-path /net/openvpn/v3/sessions/21cac29cs6ae5s4637sab69s4cd790c08fc6 --restart
```

# how to disconnect

```
openvpn3 session-manage --session-path /net/openvpn/v3/sessions/21cac29cs6ae5s4637sab69s4cd790c08fc6 --disconnect

also remove /etc/resolv.conf.head
```

