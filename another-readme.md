# How to use obfs4proxy as a general tcp stream obfuscator

## server side:
```
env TOR_PT_MANAGED_TRANSPORT_VER=1 TOR_PT_SERVER_TRANSPORTS=obfs4 TOR_PT_STATE_LOCATION= TOR_PT_SERVER_BINDADDR=obfs4-0.0.0.0:5678 TOR_PT_ORPORT=127.0.0.1:80./obfs4proxy
```

## client side:
```
env TOR_PT_CERT=Q7WCH8qb7XxmFeXkopekoLDuS0Lw94bOLu7ml8kPb0J4kpopQwhcUJPGxxI8IGOv/gtzMA TOR_PT_MANAGED_TRANSPORT_VER=1 TOR_PT_STATE_LOCATION=/tmp/pt TOR_PT_CLIENT_TRANSPORTS=obfs4 ./obfs4proxy --logLevel DEBUG --enableLogging true
```

## foxyproxy:
```
socks5 proxy url: It can be found in the output of client side command line.
socks5 user & pass: 
	username: cert=Q7WCH8qb7XxmFeXkopekoLDuS0Lw94bOLu7ml8kPb0J4kpopQwhcUJPGxxI8IGOv/gtzMA
	password: ;iat-mode=0
```

## firefox:
```
http://server-ip:5678
```

## note:
When used as a tcp protocol obfuscation tool, It need some modification.
