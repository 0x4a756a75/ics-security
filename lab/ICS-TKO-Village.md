# ICS TKO Lab

## Table of contents
 * [Logo](#Logo)
 * [ICS TKO Village](#ICSTKOVillageMap)
 * [Raspberry Pi](#RaspberryPi)
 * [Breadboard](#Breadboard)

## Logo

![2](https://github.com/0x4a756a75/ics-security/assets/96379191/a73eb905-9d5a-41fe-9f7f-78eb0284d09d)
![3](https://github.com/0x4a756a75/ics-security/assets/96379191/84354cc4-c53b-4142-b3aa-c5c5e9e05f77)

## ICS TKO Village Map

![District 1](https://github.com/0x4a756a75/ics-security/assets/96379191/4779647e-6d3e-4d69-ac69-33007156fd12)


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



## Raspberry Pi

### Configuration

- RPI Purple - OpenPLC = District 1 + District 2 + District 3 (Japanese Restaurant + Ice Cream)
- RPI Orange - OpenPLC = District 3 (7/11 + McDo) + Electric Tower (+ D1-PB)


### GPIO

![Raspberry-Pi-GPIO-pinouts-1024x703](https://github.com/0x4a756a75/ics-security/assets/96379191/991123bf-4c29-4009-8d4d-31b34fa13233)


## Breadboard

| GPIO  | RPI Pin  | RPI Purple | RPI Orange | Components | Light Color | Resis. (Ohms) | Cable #  |
| ------------- |  ------------- |------------- |------------- |------------- |------------- |------------- |------- |
| GPIO 4 | 7  | D1-TL  |   |  | | |Green |
| GPIO 5  | 29  | D1-TL |   || | |Yellow |
| GPIO 6 | 31 | D1-TL |   | | | | Red|
| GPIO 12  | 32  | D1-RL |   | | | | Red|
| GPIO 13 | 33| D1-PL |   | | | | Blue|
| GPIO 16 | 36  | D2-TL |   | | | | Green|
| GPIO 17 | 11 | D2-TL  |   | | | | Yellow|
| GPIO 18  | 12 | D2-TL |   | | | | Red|
| GPIO 19 | 35 | D2-RL |   | | | | Red |
| GPIO 20 | 38 | D2-PB |   | | | |Blue |
| GPIO 21 | 40  | D2-PB |   | | | | Red|
| GPIO 22 | 15  | |   | | | | |
| GPIO 23 | 16 |  |   | | | | |
| GPIO 24 | 18 |  |   | | | | |
| GPIO 25 | 22 |  |   | | | | |
| GPIO 26 | 37 |  |   | | | | |
| GPIO 27 | 13 |  |   | | | | Black |

GND Pin - 9, 25, 39, 14, 20, 30 and 34





