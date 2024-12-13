# LIST OF ALL DEVICES ON THE NETWORK
- 2811 Router
- 2x Switch 2960-24TT (Switch4 -> 168.90.0.0; Switch5 -> 210.3.14.0)
- 5x PC-PT (PC3 -> 168.90.0.4; PC4 -> 168.90.0.5; PC5 -> 210.3.14.3; PC0 -> 168.90.0.6; PC1 -> 210.3.14.5)
- Laptop-PT (Laptop1 -> 168.90.0.3)
- 3x Server-PT (Server6 -> 168.90.0.2; Server7 -> 210.3.14.4; Server8 -> 210.3.14.2)

# COMMANDS USED FOR SETUP
1. `en`
2. `config t`
3. `hostname dhcp-server` name of the router
4. `int f0/0` interface of fast ethernet 0/0
5. `ip add 168.90.0.1 255.255.0.0` assigning ip to interface and subnet mask
6. `no sh` no shutdown

1. `int f0/1` interface of fast ethernet 0/1
2. `ip add 210.3.14.1 255.255.255.0` assigning ip to interface and subnet mask
3. `no sh` no shutdown

1. `ip dhcp excluded-address 168.90.0.1` excluding the addresses that are assigned to interface
2. `ip dhcp excluded-address 210.3.14.1`

1. `ip dhcp pool 168.90.0.1` creating a pool with a name
2. `network 168.90.0.0 255.255.0.0` ip addresses that are assigned to nodes will start from x.x.x.<b>2</b>
3. `default-router 168.90.0.1` setting default gateway
4. `exit`


1. `ip dhcp pool 210.3.14.1` creating a pool with a name
2. `network 210.3.14.0 255.255.255.0` ip addresses that are assigned to nodes will start from x.x.x.<b>2</b>
3. `default-router 210.3.14.1` setting default gateway
4. `exit`



