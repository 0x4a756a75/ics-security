# ICS TKO Lab

## Table of contents
 * [Logo](#Logo)
 * [ICS TKO Village](#ICSTKOVillageMap)
 * [Raspberry Pi](#RaspberryPi)
 * [Breadboard](#Breadboard)

## ICS TKO Village 

## Logo

![2](https://github.com/0x4a756a75/ics-security/assets/96379191/a73eb905-9d5a-41fe-9f7f-78eb0284d09d)
![3](https://github.com/0x4a756a75/ics-security/assets/96379191/84354cc4-c53b-4142-b3aa-c5c5e9e05f77)

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

| GPIO  | RPI Pin  | RPI Purple | Cable Color  | Light Color | Conf. | Resis. (Ohms) | 
| ------------- |  ------------- |------------- |------------- |------------- |------------- |------------- |
| GPIO 4 | 7  | D1-TL  |   Green | Green | 1 - | 220 
| GPIO 5  | 29  | D1-TL |  Yellow | Yellow |1 - | 220 
| GPIO 6 | 31 | D1-TL |   Red|Red|1 - | 220 
| GPIO 12  | 32  | D1-RL | Red| White | 2 = | 100 
| GPIO 13 | 33| D1-PL |   Blue| Blue |1 - |220
| GPIO 16 | 36  | D2-TL |    Green|Green |1 - | 220 
| GPIO 17 | 11 | D2-TL  |  Yellow|Yellow |1 - | 220 
| GPIO 18  | 12 | D2-TL |    Red| Red|1 - | 220 
| GPIO 19 | 35 | D2-RL |    Red |White |2 = |75  
| GPIO 20 | 38 | D2-PB |   Blue | n.a |n.a | n.a |
| GPIO 21 | 40  | D2-PB |  Red| n.a |n.a | n.a |
| GPIO 22 | 15  |D3-JE |  Orange | Red | 2 // | 200
| GPIO 23 | 16 |  D3-JG | Purple | White |1 - | 220
| GPIO 24 | 18 | D3-JU | Yellow  | White |1 - | 220
| GPIO 25 | 22 | D3-ICE | Orange  | White |2 = |200 
| GPIO 26 | 37 | D3-ICG |   Purple | White |1 - | 220
| GPIO 27 | 13 |  |   Black | n.a |n.a | n.a |

- Pb GND Pin = 10k Ohms

- GND Pin - 9, 25, 39, 14, 20, 30 and 34
- =: Serie
//: Parallel 
-: Unique 

### RPI Orange 

| GPIO  | RPI Pin  | RPI Orange | Cable #  | Light Color | Conf. | Resis. (Ohms) | 
| ------------- |  ------------- |------------- |------------- |------------- |------------- |------------- |
| GPIO 4 | 7  | D1-ET | Red   | Red   | 2 // | 200 
| GPIO 5  | 29  | D1-ET|   Green| Green | 2 // | 200
| GPIO 6 | 31 |D2-ET | Red  |Red   | 2 // | 200
| GPIO 12  | 32  |D2-ET  | Green| Green | 2 // | 200
| GPIO 13 | 33|D3-ET |  Red |Red   |  2 // | 200
| GPIO 16 | 36  | D3-ET  | Green   | Green | 2 // |200
| GPIO 17 | 11 | D1-PB| Blue | n.a |n.a | n.a |
| GPIO 18  | 12 | D3-711E |  Orange  | White | 2 // | 200
| GPIO 19 | 35 | D3-711G |   Purple | White |1 - | 220
| GPIO 20 | 38 | D3-711U |   Yellow | Yellow & Green |2 // |200
| GPIO 21 | 40  | D3-MDG | Purple | White |1 - | 200
| GPIO 22 | 15  | D3-MDU|  Yellow | White |1 - | 200
| GPIO 23 | 16 |   |  |
| GPIO 24 | 18 |  |   |
| GPIO 25 | 22 | |   |
| GPIO 26 | 37 |  |    |
| GPIO 27 | 13 |  |   Black |n.a |n.a | n.a |

### Tinkercad Resistance Testing

![Screenshot 2024-04-09 at 12 20 31 PM](https://github.com/0x4a756a75/ics-security/assets/96379191/d06cfb51-75bf-4362-b5b6-2e0eaf02a518)

### Breadboard Configuration

![Screenshot 2024-04-09 at 2 01 03 PM](https://github.com/0x4a756a75/ics-security/assets/96379191/1f4e8485-bd66-45cc-8183-1364f8e01f96)

#### BreadboardRPI Orange

![Screenshot 2024-04-09 at 1 47 58 PM](https://github.com/0x4a756a75/ics-security/assets/96379191/12ad3744-b915-4b82-a202-037079152258)

#### BreadboardRPI Purple

![Screenshot 2024-04-09 at 1 48 04 PM](https://github.com/0x4a756a75/ics-security/assets/96379191/488f842a-b5c4-42a7-a63c-531072e2845d)



