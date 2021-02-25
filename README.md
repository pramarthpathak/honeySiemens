# honeySiemens
low interaction honeypot that simulates a Siemens Simatic S7-300 PLC 

# Requirements 
- An operating system (tested on ubuntu 18.04)
- Honeyd 
- Python 2.5+
- Farpd to make honeyd receive the network traffic 

# How to install?
1. Install [Honeyd](https://github.com/DataSoft/Honeyd) and all its dependencies.
2. Install farpd

`sudo apt-get install farpd`

3. Clone this repository 
4. Fix the script paths  in [honeyd.conf](./honeyd.conf) so they match the absolute path in your file system
5. Replace IP in [honeyd.conf](./honeyd.conf) with the address you've chosen: the IP address
has to be on the same network as the host interface where honeyd will listen.
6. From inside the repository, run: 

`sudo honeyd -d -p nmap-os-db -i INTERFACE -l Honeyd.log -f Honeyd.conf IP –disable-webserver`

where IP is the same IP address of Honeydconfiguration file and INTERFACE is the interface of the host machine occupied by the honeypot

7. Run:

`sudo farpd -d -i INTERFACE <IP>`

in order to make the host machine intercept the network traffic addressed to the honeypot

8. honeySiemens is up and running!

For more information take a look at the [report](./report/honeySiemens.pdf)
