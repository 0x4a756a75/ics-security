# Gas Station

## Lab Info

192.168.1.14 = Kali<br/>
192.168.1.16 = Ubuntu Server

## Lab Testing

### Ubuntu Server

``conpot -f --template guardian_ast``


### Kali


``sudo netdiscover -r 192.168.1.0/24 ``

![Screenshot 2023-04-10 at 11 54 15 AM](https://user-images.githubusercontent.com/96379191/230822501-f439fab8-20fd-468b-bcbe-c2d7d4f7608e.png)

``sudo nmap 192.168.1.16 -p 1-65535``

![Screenshot 2023-04-10 at 11 55 27 AM](https://user-images.githubusercontent.com/96379191/230822677-d81f65d2-0cbf-43f9-8df4-947f39b8cf63.png)

``sudo nmap 192.168.1.16 -p 10001 --script atg-info.nse``

![Screenshot 2023-04-10 at 12 04 56 PM](https://user-images.githubusercontent.com/96379191/230823584-70291f82-211b-44fa-800e-f3b3e2d90af6.png)

https://www.ericzhang.me/gas-station-atgs-exposed-to-public/

``telnet 192.168.1.16 10001``

![Screenshot 2023-04-10 at 12 03 34 PM](https://user-images.githubusercontent.com/96379191/230823487-10211f02-009e-46ba-977d-ed71df82528d.png)

![Screenshot 2023-04-10 at 12 04 28 PM](https://user-images.githubusercontent.com/96379191/230823541-4a3e3c06-6749-4e41-9228-be62ea0113b1.png)

