# Gas Station

## Lab Info

192.168.1.14 = Kali<br/>
192.168.1.16 = Ubuntu Server

## Lab Testing

### Ubuntu Server

``conpot -f --template default``


### Kali


``sudo netdiscover -r 192.168.1.0/24 ``

![Screenshot 2023-04-10 at 11 54 15 AM](https://user-images.githubusercontent.com/96379191/230822501-f439fab8-20fd-468b-bcbe-c2d7d4f7608e.png)

``sudo nmap 192.168.1.16 -p 1-65535``

![Screenshot 2023-04-10 at 11 55 27 AM](https://user-images.githubusercontent.com/96379191/230822677-d81f65d2-0cbf-43f9-8df4-947f39b8cf63.png)

``sudo nmap 192.168.1.16 -p 10001 --script atg-info.nse``

![Screenshot 2023-04-10 at 11 56 22 AM](https://user-images.githubusercontent.com/96379191/230822713-aa4b3e1c-a1c2-47e6-8dfd-20645279b054.png)

https://www.ericzhang.me/gas-station-atgs-exposed-to-public/
