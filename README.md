# consulSample

## Preinstall
- Vagrant Installed
- Vagrant up

## Step
NOTE - 

### Server
```
consul agent -server -bootstrap-expect=1 -data-dir=/tmp/consul -node=server -bind=80.20.20.10 -enable-script-checks=true -config-dir=/etc/consul.d -client 0.0.0.0 -ui
```
### Client1
```
consul agent -data-dir=/tmp/consul -node=client1 -bind=80.20.20.11 -enable-script-checks=true -config-dir=/etc/consul.d
```
### Client2
```
consul agent -data-dir=/tmp/consul -node=client2 -bind=80.20.20.12 -enable-script-checks=true -config-dir=/etc/consul.d
```

### Server
```
CMD - join cmd
consul join 80.20.20.11
consul join 80.20.20.12


consul members
dig @server -p 8600 client1.node.consul
dig @server -p 8600 client2.node.consul
```
