# Snap7 Penetration Testing

## Lab Info

192.168.1.14 = Kali<br />
192.168.1.15 = Ubuntu Server<br />
00:1C:06 = MAC Address Ubuntu Server

## Lab Testing

### Ubuntu Server

``conpot -f --template default``

<img width="915" alt="Screenshot 2023-04-10 at 9 27 46 AM" src="https://user-images.githubusercontent.com/96379191/230808053-fc8110cc-7f76-469c-8995-8243fcbd3d7c.png">

### Kali

``snmp-check 10.168.1.15   ``

![Screenshot 2023-04-10 at 9 26 36 AM](https://user-images.githubusercontent.com/96379191/230808072-b9e2e3d4-bff8-4703-8634-38e2ee77f30c.png)


``sudo nmap 192.168.1.15 -Pn -p 1-65535``

![Screenshot 2023-04-10 at 9 26 41 AM](https://user-images.githubusercontent.com/96379191/230808065-d855af5d-63f3-4c32-96b3-83bc15352359.png)


``snmp-check --port 16100 192.168.1.15``

![Screenshot 2023-04-10 at 9 26 47 AM](https://user-images.githubusercontent.com/96379191/230808059-9f1afd52-34b8-4b62-acfa-c9f867fc743c.png)

