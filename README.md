ansible-minecraft-nukkit
============
This role installs the minecraft nukkit version on Raspberry Pi 3+ and allows to connect for LAN network at home. 

Hardware requirements
------------
[x] Raspberry Pi 3 B+ Motherboard
[x] 32GB Micro SD. 
[x] High Performance Cat6 RJ45 Ethernet
[x] USB Charger for your Raspberry.

Software requirements:
---------------------
[x] [Raspbian Stretch Lite](https://www.raspberrypi.org/downloads/raspbian/)
[x] [BalenaEtcher](https://www.balena.io/etcher/) to install your Raspbian on your SD card.

Role Variables
--------------
All the below variables allow to customize Minecraft's properties. The ```minecraft_server_ip``` needs to be changed based on your raspberry-pi api, the ```minecraft_server_port``` can be changed but is not required.

```minecraft_max_players``` is set to 3 by default but it can be set to 10 or even 20 ( I did not test this high value)

The ```minecraft_view_distance``` is set to 5 by default for performance reasons but it can be changed to a higher value like 10.

```minecraft_motd``` is the server name that will appears on your list when it is added.

**Putting all together**:

```yaml
minecraft_level_name: world
minecraft_max_players: 3
minecraft_view_distance: 5
minecraft_motd: "Vennon Server"
minecraft_server_ip: 192.168.0.13
minecraft_server_port: 19132
```

Example Playbook
----------------

Using variables.

```
- hosts: servers
  vars:
    minecraft_level_name: world
    minecraft_max_players: 10
    minecraft_view_distance: 10
    minecraft_motd: "Vennon Server"
  roles:
      - { role: robedevops.ansible_minecraft_nukkit }
```

License
-------

BSD

Author Information
------------------

Roberto Cardenas Isla - email: rcardenas20@gmail.com