# ICS TKO Lab

## Table of contents
 * [Logo](#Logo)
 * [ICS TKO Village](#ICSTKOVillageMap)
 * [Raspberry Pi](#RaspberryPi)
 * [Breadboard](#Breadboard)

## ICS TKO Village 

## Logo

![2](https://github.com/0x4a756a75/ics-security/assets/96379191/a73eb905-9d5a-41fe-9f7f-78eb0284d09d)
![ICS Cyber Ninja](https://github.com/0x4a756a75/ics-security/assets/96379191/6b2c19c3-6620-4fe7-a782-13c01541f0ff)


## Map

![District 1](https://github.com/0x4a756a75/ics-security/assets/96379191/4779647e-6d3e-4d69-ac69-33007156fd12)
![2](https://github.com/0x4a756a75/ics-security/assets/96379191/708d7d16-0e61-4270-9bac-08f1244bbd33)
![1](https://github.com/0x4a756a75/ics-security/assets/96379191/2068715b-6fae-4126-820d-f44c6d00098e)


| Components | Type | District 1 | District 2 | District 3 | 
| ------------- | ------------- |  :---:  |  :---:  |  :---:  |
| Traffic Light  | Light  |  X (D1-TL)  | X (D2-TL) |    |
| Road Light   | Light  | X (D1-RL) | X (D2-RL) |   |
| Pedestrian Light   | Light | X (D1-PL) |    |    |
| Pedestrian Button  | Button  |    | X (D2-PB) |    |
| SIS  | Button |  X (D1-PB)  |   |  |
| Electricity Tower (ET)   | Light  | X (D1-ET) | X (D2-ET) | X (D3-ET) |
| Japanese Restaurant   | Light  |    |    | X (D3-JE)(D3-JG)(D3-JU)  |
| 7/11   | Light  |   |    |  X (D3-711E)(D3-711G)(D3-711U) |   
| Ice Cream  | Light  |  |  |  X (D3-ICE)(D3-ICG) |    
| McDo  | Light  |   | |  X (D3-MDG)(D3-MDU) |    



| District| Components | Type | Red | Black | Blue | Yellow (U)| Green  | Orange (E) | Purple (G)| 
| ------------- | ------------- | ------------- | :---: | :---: | :---: |:---: |:---: |:---:| :---: |
| D1 | D1-TL | Light  | X | X | | X |X || |
| D2 | D2-TL   | Light | X | X | | X |X || |
| D1 | D1-RL  | Light | X | X | |   |  || |
| D2 | D2-RL  | Light  | X | X | |   |  || |
| D1 | D1-PL | Light  |   | X | X|   |  || |
| D2 | D2-PB  | Button  | X | X | X|   |  || |
| D1 | D1-PB  | Button  | X | X | X|   |  || |
| D1 | D1-ET | Light  | X | X |  |   | X || |
| D2 | D2-ET | Light  | X | X |  |   | X || | 
| D3 | D3-ET  | Light  | X | X |  |   | X || |
| D3 | D3-JE | Light |   | X1 |  |   |   |X| | 
| D3 | D3-JG  | Light  |   | X1  |  |   |   || X|  
| D3 | D3-JU | Light |   | X1  |  | X  |   ||  |   
| D3 | D3-711E | Light |   | X2 |  |   |   |X| |  
| D3 | D3-711G | Light |   | X2  |  |   |   || X|   
| D3 | D3-711U | Light |   | X2  |  | X  |   ||  |   
| D3 | D3-ICE | Light |   | X3  |  |   |   |X| |  
| D3 | D3-ICG | Light |   |X3  |  |   |   || X|   
| D3 | D3-MDG | Light |   | X4 |  |   |   || X|  
| D3 | D3-MDU | Light |   | X4 |  | X  |   ||  |   



## Technical Setup

### RPI Usage Configuration

- RPI Purple - OpenPLC = District 1 + District 2 + District 3 (Japanese Restaurant + Ice Cream)
- RPI Orange - OpenPLC = District 3 (7/11 + McDo) + Electric Tower (+ D1-PB)


### RPI GPIO 

![Raspberry-Pi-GPIO-pinouts-1024x703](https://github.com/0x4a756a75/ics-security/assets/96379191/991123bf-4c29-4009-8d4d-31b34fa13233)

### RPI Purple 

| GPIO  | RPI Pin  | RPI Purple | Cable Color  | Light Color | Conf. | Resis. (Ohms) | Info. | 
| ------------- |  ------------- |------------- |------------- |------------- |------------- |------------- |------------- |
| GPIO O8  |   | D1-TL  |   Green | Green | 1 - | 220 
| GPIO O10 |   | D1-TL |  Yellow | Yellow |1 - | 220 
| GPIO I16 |  | D1-TL |   Red|Red|1 - | 220 
| GPIO O18 |   | D1-RL | Red| White | 2 = | 100 
| GPIO O22 | | D1-PL |   Blue| Blue |1 - |220
| GPIO O24 |   | D2-TL |    Green|Green |1 - | 220 
| GPIO O26 |  | D2-TL  |  Yellow|Yellow |1 - | 220 
| GPIO O32 |  | D2-TL |    Red| Red|1 - | 220 
| GPIO O36 |  | D2-RL |    Red |White |2 = |100  
| GPIO I5 |  | D2-PB |   Blue | n.a |n.a | n.a | Pedestrians Ligh |
| GPIO I3 |   | D2-PB |  Red| n.a |n.a | n.a | Pedestrians Ligh |
| GPIO O38 |  | D3-ICE | Orange  | White |2 = |100 
| GPIO O38 |   | D3-MDG | Purple | White |1 - | 220
| GPIO O40|   | D3-MDU|  Yellow | White |1 - | 220
| GPIO O40 |  | D3-ICG |   Purple | White |1 - | 220
|   |  | |    |  | | 
| GPIO  |  |  |   Black | n.a |n.a | n.a |

- Pb GND Pin = 10k Ohms

- GND Pin - 9, 25, 39, 14, 20, 30 and 34
- =: Serie
//: Parallel 
-: Unique 

### RPI Orange 

| GPIO  | RPI Pin  | RPI Orange | Cable #  | Light Color | Conf. | Resis. (Ohms) | Info. | 
| ------------- |  ------------- |------------- |------------- |------------- |------------- |------------- |------------- |
| GPIO O8 |   | D1-ET | Red   | Red   | 2 // | 200 
| GPIO 010  |   | D1-ET|   Green| Green | 2 // | 200
| GPIO O16 |  |D2-ET | Red  |Red   | 2 // | 200
| GPIO O18  |   |D2-ET  | Green| Green | 2 // | 200
| GPIO O22 | |D3-ET |  Red |Red   |  2 // | 200
| GPIO O24 |   | D3-ET  | Green   | Green | 2 // |200
| -  |  | |  |  | |  | D1-PB (Blue) SIS |
| -  |  | |  |  | |  |D1-PB (Red) SIS |
| GPIO  O26 |  | D3-711U |   Yellow | Yellow & Green |2 // |200
| GPIO O26 |  | D3-711E |  Orange  | White | 2 // | 200
| GPIO O26 |  | D3-711G |   Purple | White |1 - | 220 
| GPIO O32 |   | D3-JE |  Orange | Red | 2 // | 200 
| GPIO O32 |   | D3-JU | Yellow  | White |1 - | 220 
| GPIO O32 |   |D3-JE |  Orange | Red | 2 // | 200 
| -  |  |    |  |  | |   
| - |    |  |   |  | |  
| GPIO  |  |  |   Black |n.a |n.a | n.a |


### Tinkercad Resistance Testing

![Screenshot 2024-04-09 at 8 07 05 PM](https://github.com/0x4a756a75/ics-security/assets/96379191/b5248213-d3dd-434b-8341-916cb852e94e)


### Breadboard Configuration

![Screenshot 2024-04-17 at 1 45 11 PM](https://github.com/0x4a756a75/ics-security/assets/96379191/15f2ee18-d135-40b1-8818-2c0389e8ea14)


### Open PLC & RPI Addressing
![wfwefewfew](https://github.com/0x4a756a75/ics-security/assets/96379191/2187f962-b548-4700-a5ea-1a1443fa8879)


### Cable Connectivity

![Screenshot 2024-04-16 at 10 41 00 AM](https://github.com/0x4a756a75/ics-security/assets/96379191/6dd10da5-412b-4c69-bd83-a05fb21bfb8b)




| #  | Outputs (1-20) |  OpenPLC # | - | # |Outputs (1-20) |OpenPLC # |
| ------------- |  ------------- |------------- |------------- |------------- |------------- |------------- |
| 1 |  || - | 21 |D2 Ground| 
| 2 |  ||- | 22 ||
| 3 |  ||- | 23 |D1 Ground| 
| 4 |  ||- | 24 ||
| 5 |  ||- | 25 |D3 Ground| 
| 6 | D2-TL - Green  |Breadboard RPI P O24 |- | 26 |D1-TL Green| Breadboard RPI P O8
| 7 | D3-711U |Breadboard RPI O O26 |- | 27 |D3-ICE| Breadboard RPI P O40
| 8 | D2-TL Yellow | Breadboard RPI P O26  |- | 28 |D1-TL Yellow| Breadboard RPI P O10
| 9 |D3-711E   |Breadboard RPI O O26|- | 29 |D3-MDG| Breadboard RPI O O32
| 10 |D2-TL Red  |Breadboard RPI P O32 |- | 30|D1-TL Red | Breadboard RPI P O16  
| 11 | D3-711G |Breadboard RPI O O26 |- | 31 |D3-MDU| Breadboard RPI O O32
| 12 |D2-RL  | Breadboard RPI P O18 |- | 32 |D1-RL|Breadboard RPI O O10
| 13 |D3-JG  |Breadboard RPI P O38 |- | 33 |D3-ICG| Breadboard RPI P O40
| 14 |D2-ET Green |Breadboard RPI P  O18 |- | 34 |D1-PL| Breadboard RPI O O8
| 15 | D3-JU |Breadboard RPI P O38|- | 35 |D3-ET Green|Breadboard RPI O O24
| 16 |D2-PB (Red) |Breadboard RPI P I03 |- | 36 |D1-ET Green | Breadboard RPI P O18 
| 17 |D3-JE  |Breadboard RPI P O38|- | 37 |D3-ET Red| Breadboard RPI O O22
| 18 | D2-ET Red|Breadboard RPI P O36|- | 38 |D1-ET Red| Breadboard RPI P O22
| 19 |  ||- | 39 ||
| 20 | D2-PB (Blue) |Breadboard RPI P I05|- | 40 ||


## Hacking

``sudo netdiscover -r 192.168.1.0/24 ``

![Screenshot 2024-11-15 at 3 54 29 PM](https://github.com/user-attachments/assets/c8ebf600-d787-4503-85bc-1730af3276b9)

``sudo nmap 192.168.1.14 -p 1-65535 ``

![Screenshot 2024-11-15 at 4 15 30 PM](https://github.com/user-attachments/assets/c69257d4-fefa-4f30-9469-c63587878c25)

![Screenshot 2024-11-15 at 5 36 34 PM](https://github.com/user-attachments/assets/de0a4ba7-d37a-441e-acab-8c3828281e3b)
