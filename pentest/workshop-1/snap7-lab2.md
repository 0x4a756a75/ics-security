# Snap7 Penetration Testing

## Lab Info

192.168.1.14 = Kali<br/>
192.168.1.15 = Ubuntu Server<br />
00:1C:06 = MAC Address Ubuntu Server

## Lab Testing

### Ubuntu Server

``conpot -f --template default``

<img width="915" alt="Screenshot 2023-04-10 at 9 27 46 AM" src="https://user-images.githubusercontent.com/96379191/230808053-fc8110cc-7f76-469c-8995-8243fcbd3d7c.png">

### Kali

``sudo netdiscover -r 192.168.1.0/24 ``


``sudo nmap 192.168.1.15 -Pn -p 1-65535 ``

![Screenshot 2023-04-10 at 9 45 09 AM](https://user-images.githubusercontent.com/96379191/230809266-f1028907-1bab-4ccb-b33e-7a99d9b1bb7c.png)


Trying to find the list of script for the snap7 imported prevriously from https://github.com/digitalbond/Redpoint

``find /usr/share/nmap -name s7*.nse ``

![Screenshot 2023-04-10 at 9 53 44 AM](https://user-images.githubusercontent.com/96379191/230810010-9fbb79bd-0c71-49c4-a577-23341573073c.png)

``sudo nmap 192.168.1.15 -Pn -p 102 --script s7-info.mse ``

![Screenshot 2023-04-10 at 10 01 02 AM](https://user-images.githubusercontent.com/96379191/230810703-90ce7f89-c14a-4ece-8387-74ad726f1979.png)

``cd plcscan ``<br/>
``sudo python2 plcsan.py 102.168.1.15 ``

![Screenshot 2023-04-10 at 10 12 09 AM](https://user-images.githubusercontent.com/96379191/230811623-4909855c-7c63-4ab7-b812-93f537dd878b.png)

``sudo msfconsole `` <br/>
``searchsploit Siemens ``

![Screenshot 2023-04-10 at 10 13 14 AM](https://user-images.githubusercontent.com/96379191/230811705-04fdf515-b084-4312-bc97-f7c38120acfe.png)

Copy the file 38964.rb from /usr/share/exploitdb/exploits/hardware/remote to /usr/share/metasploit-framework/modules/exploits/hardware/remote (hardware/remote new folders created)

![Screenshot 2023-04-10 at 10 29 29 AM](https://user-images.githubusercontent.com/96379191/230813568-532aa2dc-4bbe-4de9-9c05-2f2404ce4ac0.png)

Nothing has changed in the Snap7 status, on Ubuntu Server, so it means the Snap7 is not vulnerable to this exploit

<img width="588" alt="Screenshot 2023-04-10 at 10 29 50 AM" src="https://user-images.githubusercontent.com/96379191/230813693-ae93feb5-c723-45a1-84e4-586b7207bdd1.png">




