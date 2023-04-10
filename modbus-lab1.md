# Modbus Lab 1

## Lab Info

192.168.1.14 = Kali<br/>
192.168.1.17 = Ubuntu Server<br />
00:00:54 = MAC Address Ubuntu Server

## Lab Testing

### Ubuntu Server

``conpot -f --template default``


### Kali

``sudo netdiscover -r 192.168.1.0/24 ``

![Screenshot 2023-04-10 at 12 12 12 PM](https://user-images.githubusercontent.com/96379191/230824471-65ed0e2c-dedd-47bb-9570-3c00c3b02379.png)

``sudo nmap -Pn 192.168.1.17 -p 1-65535``

![Screenshot 2023-04-10 at 12 14 51 PM](https://user-images.githubusercontent.com/96379191/230824622-ff5d7825-93ec-40cb-913c-4a3a25a3030e.png)

``sudo msfconsole``

![Screenshot 2023-04-10 at 12 21 11 PM](https://user-images.githubusercontent.com/96379191/230825356-e87aeeb5-3ff8-450c-91e4-d38b60396d3f.png)

Password has been detected as illustrated below.

![Screenshot 2023-04-10 at 12 21 25 PM](https://user-images.githubusercontent.com/96379191/230825379-8be7e28f-aa36-4787-8102-1f6d02c198c2.png)

The function is not support by this honeypot

![Screenshot 2023-04-10 at 12 21 57 PM](https://user-images.githubusercontent.com/96379191/230825389-5d120b9c-32e7-44b9-92a8-f30403d52c71.png)

This module find more than one ID, and usually it should find just one.

![Screenshot 2023-04-10 at 12 22 11 PM](https://user-images.githubusercontent.com/96379191/230825400-84d99d05-eb26-4fb6-bb6d-37aa5c20c37e.png)
