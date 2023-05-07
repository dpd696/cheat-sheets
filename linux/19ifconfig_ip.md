# Getting info about the network interfaces (ifconfig, ip, route)

## displaying information about enabled interfaces

```
ifconfig
```

## displaying information about all interfaces (enabled and disabled)

```
ifconfig -a
ip address show
```

## displaying info about a specific interface

```
ifconfig enp0s3
ip addr show dev enp0s3
```

## showing only IPv4 info

```
ip -4 address
```

## showing only IPv4 info

```
ip -6 address
```

## displaying L2 info (including the MAC address)

```
ip link show
ip link show dev enp0s3
```

## displaying the default gateway

```
route 
route -n    # numerical addresses
ip route show
```

## displaying the DNS servers

```
systemd-resolve --status
```


# Setting the network interfaces (ifconfig, ip, route)

## disabling an interface

```
ifconfig enp0s3 down
ip link set enp0s3 down
```

## activating an interface

```
ifconfig enp0s3 up
ip link set enp0s3 up
```

## checking its status

```
ifconfig -a
ip link show dev enp0s3
```

## setting an ip address on an interface

```
ifconfig enp0s3 192.168.0.222/24 up
ip address del 192.168.0.111/24 dev enp0s3
ip address add 192.168.0.112/24 dev enp0s3
```


## setting a secondary ip address on sub-interface

```
ifconfig enp0s3:1 10.0.0.1/24
```

## deleting and setting a new default gateway

```
route del default gw 192.168.0.1
route add default gw 192.168.0.2
```

## deleting and setting a new default gateway

```
ip route del default
ip route add default via 192.168.0.1
```

## changing the MAC address

```
ifconfig enp0s3 down
ifconfig enp0s3 hw ether 08:00:27:51:05:a1
ifconfig enp0s3 up
```

## changing the MAC address

```
ip link set dev enp0s3 address 08:00:27:51:05:a3
```