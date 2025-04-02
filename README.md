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

```console
Main_Switch>enable
```

2. Note the change in the prompt from > to #

```console
Main_Switch#
```

3. Exit and return to User Mode:

```console
Main_Switch#disa
Main_Switch#disable
Main_Switch>
```

I partially typed a command and then hit the “Tab” key, which completes the command for me.

### Set the Hostname

1. Enter Global Configuration Mode:

```console
Main_Switch#configure terminal
```

2. Set the Hostname:

```console
Main_Switch(config)#hostname testing
```

3. Confirm the Changes (note the hostname has changed to testing):

```console
testing(config)#
```

### Set the Banner

1. Enter Global Configuration Mode:

```console
Main_Switch#configure terminal
```

2. Set the Banner:

```console
Main_Switch(config)#banner motd +
```

3. Enter the banner along with the delimiter:

```console
Enter TEXT message.  End with the character '+'.
Main_Switch says Hello World!+
```

4. Confirm the Changes:

```console
Press RETURN to get started!

Main_Switch says Hello World!
```

### Set the Enable Password

1. Enter Global Configuration Mode:

```console
Main_Switch#configure terminal
```

2. Set the Enable Password:

```console
Main_Switch(config)#enable secret <password>
```

### Set the Console Password

1. Enter Global Configuration Mode:

```console
Main_Switch#configure terminal
```

2. Enter Console Line Configuration:

```console
Main_Switch#configure terminal
```

3. Set the Password:

```console
Main_Switch(config-line)#password <password>

Main_Switch(config-line)#login
```

4. Set the Service Password Encryption (Optional but Recommended):

```console
Main_Switch(config-line)#exit

Main_Switch(config)#service password-encryption

```
### Configuring Telnet

1. Enter Global Configuration Mode:

```console
BUR_Main_SW#configure terminal
```

2. Enable Telnet on the VTY Lines:

```console
Main_Switch(config)#line vty 0 4 
```

3. Enter the Password:

```console
Main_Switch(config-line)#password <password>
Main_Switch(config-line)#login
```
To access the switch via Telnet, open Command Prompt, and type telnet ```ip address```, replacing ```ip address``` with the switch's IP address. Enter the password when prompted to gain access.

### Saving the Configuration

1.	To save the current running configuration:

```console
Main_Switch#copy running-config startup-config
Destination filename [startup-config]?
Building configuration...
[OK]
Main_Switch#
```

2. Alternatively, use these commands:

```console
Main_Switch#copy run start
Destination filename [startup-config]?
Building configuration...
[OK]
Main_Switch#wr
Building configuration...
[OK]
```
3. If you are in configuration mode, you can use the do command to save without exiting:

```console
Main_Switch(config)#do copy running-config startup-config
Destination filename [startup-config]?
Building configuration...
[OK]
Main_Switch(config)#do wr
Building configuration...
[OK]
```

Always make sure you save your configurations after making changes to prevent loss of settings after a reboot.

### Adding another User for SSH Access

1. Enter Global Configuration Mode:

```console
BUR_Main_SW#configure terminal
```

2. Create a New User:

```console
Main_Switch(config)#username scott secret cisco
```

3. Replace ```scott``` and ```cisco``` with your chosen username and password.

5. Ensure that SSH is Enabled:

```console
Main_Switch(config)#ip ssh version 2
```

### Creating VLANs

1. Enter Global Configuration Mode:

```console
BUR_Main_SW#configure terminal
```

2. Create a VLAN:

```console
BUR_Main_SW(config)#vlan 100
```

3. Name the VLAN:

```console
BUR_Main_SW(config-vlan)#name WIFI
```

4. Assign Ports to the VLAN:

```console
BUR_SW_1#configure terminal
BUR_SW_1(config)#interface FastEthernet0/15
BUR_SW_1(config)#switchport mode access
BUR_SW_1(config)#switchport access vlan 100
BUR_SW_1(config)#exit
```

5. Verify VLAN Configuration:

```console
BUR_SW_1#show vlan brief
```
