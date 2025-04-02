# Cisco Packet Tracer

## Project Overview

This project outlines the network configuration and operations for the College of Art, Technology, and Science (CATS). The goal is to ensure proper setup, security, and efficient management of the network infrastructure within multiple buildings of the college, facilitating seamless connectivity for students, staff, and general users.

### Network Configuration and Technologies

- Cisco Packet Tracer
- VLAN Configuration
- Port Security
- Trunking (802.1Q)
- Spanning Tree Protocol (STP)
- Switch Configuration and Management
- Routing and Subnetting
- Wireless Access Points (WAPs)
- DHCP Configuration
- Switch and Network Device Management
- IOS Configuration and Version Control

### Hobart Campus - LAN

| VLAN Name | VLAN # | Subnet Address | Subnet Mask | CIDR | # of Hosts | Usable Range | Broadcast Address |
| -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- |
| HBT_Staff | <div align="center">10</div> | <div align="center">10.9.0.0/24</div> | <div align="center">255.255.255.0</div> | <div align="center">/24</div> | <div align="center">254</div> | <div align="center">10.9.0.1 - 10.9.0.254</div> | <div align="center">10.9.0.255</div> |
| HBT_Students | <div align="center">20</div> | <div align="center">10.9.2.0/23</div> | <div align="center">255.255.254.0</div> | <div align="center">/23</div> | <div align="center">510</div> | <div align="center">10.9.2.1 - 10.9.3.254</div> | <div align="center">10.9.3.255</div> |
| HBT_General | <div align="center">30</div>| <div align="center">10.9.4.0/24</div> | <div align="center">255.255.255.0</div> | <div align="center">/24</div> | <div align="center">254</div> | <div align="center">10.9.4.1 - 10.9.4.254</div> | <div align="center">10.9.4.255</div> |

### Launceston Campus - LAN

| VLAN Name | VLAN # | Subnet Address | Subnet Mask | CIDR | # of Hosts | Usable Range | Broadcast Address |
| -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- |
| LAU_Staff | <div align="center">40</div> | <div align="center">10.9.6.0/24</div> | <div align="center">255.255.255.0</div> | <div align="center">/24</div> | <div align="center">254</div> | <div align="center">10.9.6.1 - 10.9.6.254</div> | <div align="center">10.9.6.255</div> |
| LAU_Students | <div align="center">50</div> | <div align="center">10.9.8.0/23</div> | <div align="center">255.255.254.0</div> | <div align="center">/23</div> | <div align="center">510</div> | <div align="center">10.9.8.1 - 10.9.9.254</div> | <div align="center">10.9.9.255</div> |
| LAU_General | <div align="center">60</div> | <div align="center">10.9.10.0/24</div> | <div align="center">255.255.255.0</div> | <div align="center">/24</div> | <div align="center">254</div> | <div align="center">10.9.10.1 - 10.9.10.254</div> | <div align="center">10.9.10.255</div> |

### Burnie Campus - LAN

| VLAN Name | VLAN # | Subnet Address | Subnet Mask | CIDR | # of Hosts | Usable Range | Broadcast Address |
| -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- |
| BUR_Staff | <div align="center">70</div> | <div align="center">10.9.12.0/24</div> | <div align="center">255.255.255.0</div> | <div align="center">/24</div> | <div align="center">254</div> | <div align="center">10.9.12.1 - 10.9.12.254</div> | <div align="center"> 10.9.12.255</div> |
| BUR_Students | <div align="center">80</div> | <div align="center">10.9.14.0/23</div> | <div align="center">255.255.254.0</div> | <div align="center">/23</div> | <div align="center">510</div> | <div align="center">10.9.14.1 - 10.9.14.254</div> | <div align="center">10.9.14.255</div> |
| BUR_General | <div align="center">90</div> | <div align="center">10.9.16.0/24</div> | <div align="center">255.255.255.0</div> | <div align="center">/24</div> | <div align="center">254</div> | <div align="center">10.9.16.1 - 10.9.16.254</div> | <div align="center">10.9.16.255</div> |


### Enter Privileged Exec Mode

1. Access Privileged Mode:

```terminal
Main_Switch>enable
```

2. Note the change in the prompt from > to #

```terminal
Main_Switch#
```

3. Exit and return to User Mode:

```terminal
Main_Switch#disa
Main_Switch#disable
Main_Switch>
```

I partially typed a command and then hit the “Tab” key, which completes the command for me.

### Set the Hostname

1. Enter Global Configuration Mode:

```terminal
Main_Switch#configure terminal
```

2. Set the Hostname:

```terminal
Main_Switch(config)#hostname testing
```

3. Confirm the Changes (note the hostname has changed to testing):

```terminal
testing(config)#
```

### Set the Banner

1. Enter Global Configuration Mode:

```terminal
Main_Switch#configure terminal
```

2. Set the Banner:

```terminal
Main_Switch(config)#banner motd +
```

3. Enter the banner along with the delimiter:

```terminal
Enter TEXT message.  End with the character '+'.
Main_Switch says Hello World!+
```

4. Confirm the Changes:

```terminal
Press RETURN to get started!

Main_Switch says Hello World!
```

### Set the Enable Password

1. Enter Global Configuration Mode:

```terminal
Main_Switch#configure terminal
```

2. Set the Enable Password:

```terminal
Main_Switch(config)#enable secret <password>
```

### Set the Console Password

1. Enter Global Configuration Mode:

```terminal
Main_Switch#configure terminal
```

2. Enter Console Line Configuration:

```terminal
Main_Switch#configure terminal
```

3. Set the Password:

```terminal
Main_Switch(config-line)#password <password>

Main_Switch(config-line)#login
```

4. Set the Service Password Encryption (Optional but Recommended):

```terminal
Main_Switch(config-line)#exit

Main_Switch(config)#service password-encryption

```

### Creating VLANs

1. Enter Global Configuration Mode:

```terminal
BUR_Main_SW#configure terminal
```

2. Create a VLAN:

```terminal
BUR_Main_SW(config)#vlan 100
```

3. Name the VLAN:

```terminal
BUR_Main_SW(config-vlan)#name WIFI
```

4. Assign Ports to the VLAN:

```terminal
BUR_SW_1#configure terminal
BUR_SW_1(config)#interface FastEthernet0/15
BUR_SW_1(config)#switchport mode access
BUR_SW_1(config)#switchport access vlan 100
BUR_SW_1(config)#exit
```

5. Verify VLAN Configuration:

```terminal
BUR_SW_1#show vlan brief
```
