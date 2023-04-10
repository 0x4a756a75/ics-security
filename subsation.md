# Infrastructure Subsation

## Lab Info

192.168.1.14 = Kali<br/>
192.168.1.16 = Ubuntu Server
Ubuntu Server MAC Address = 00:1D:59

## Lab Testing

### Ubuntu Server

``nano .local/lib/python3.10/site-packages/conpot/templates/IEC104/snmp/snmp.xml``

``conpot -f --template IEC104``



<img width="398" alt="Screenshot 2023-04-10 at 2 33 28 PM" src="https://user-images.githubusercontent.com/96379191/230842284-9b888a44-7ceb-4d82-abd6-bbb1b34d1a6f.png">



### Kali


``sudo netdiscover -r 192.168.1.0/24 ``

![Screenshot 2023-04-10 at 2 36 38 PM](https://user-images.githubusercontent.com/96379191/230842268-ffba8f40-1b3d-4a5d-bb9c-9a904bfa16e5.png)


