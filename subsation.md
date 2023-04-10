# Infrastructure Subsation

## Lab Info

192.168.1.14 = Kali<br/>
192.168.1.19 = Ubuntu Server
Ubuntu Server MAC Address = 00:1D:59

## Lab Testing

### Ubuntu Server

``nano .local/lib/python3.10/site-packages/conpot/templates/IEC104/snmp/snmp.xml``

We need to change the port number from 161 to 16100

<img width="398" alt="Screenshot 2023-04-10 at 2 33 28 PM" src="https://user-images.githubusercontent.com/96379191/230842284-9b888a44-7ceb-4d82-abd6-bbb1b34d1a6f.png">

``conpot -f --template IEC104``

### Kali

#### Recon and Fingerprinting


``sudo netdiscover -r 192.168.1.0/24 ``

![Screenshot 2023-04-10 at 2 36 38 PM](https://user-images.githubusercontent.com/96379191/230842268-ffba8f40-1b3d-4a5d-bb9c-9a904bfa16e5.png)

``sudo nmap -Pn 192.168.1.19 -p 1-65535``

![Screenshot 2023-04-10 at 2 42 18 PM](https://user-images.githubusercontent.com/96379191/230843092-bd47a55a-a4a4-4fe1-8dd5-431219b85e1b.png)

``find /usr/share/nmap -name iec*.nse ``

![Screenshot 2023-04-10 at 2 44 36 PM](https://user-images.githubusercontent.com/96379191/230843444-a7cc7a4f-566c-4b60-8c9f-e7596f0ca343.png)

``sudo nmap 192.168.1.19 -p 2404 --script iec-identify.nse``

![Screenshot 2023-04-10 at 2 44 42 PM](https://user-images.githubusercontent.com/96379191/230843471-af370d89-13e3-4b22-981f-6153932cfbf9.png)

#### Enumeration

#### Triggering the Shutdown





