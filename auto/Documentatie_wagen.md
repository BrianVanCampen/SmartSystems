# Documentatie Robotwagen
### Brian Van Campen
### 2ITIOT

## Probleemstelling

Ontwerp van een schakelingen om een robotwagentje aan te sturen. Dit is opgedeeld in twee schakelingen. Een stuurschakeling PCB met een ESP32 en een trackermodule PCB met een ATMega en sensoren om de sturing te kunnen realiseren.


## As-Is situatie
### MotorWagen: 
temp
### Specificaties:

- Voltage Regulator LM7805 through hole
- Motor driver SN754410 through hole + 2x 2 motor pins: 1A, 1B, 2A, 2B
- 4x LED's: 1x rood, 2x geel, 1x groen
- LCD scherm module, I²C pins op PCB: GND, SDA, SCL, 3V3
- Ultrasoon module aansluiting: 5V, TRIG, ECHO, GND
- 3 voeding pins: 3V3, 5V, GND
- 2 pin aansluiting: 3V3, PQ_L
- 2x 2 GPIO spare pins


## To-Be situatie

### Goals:
- Sensoren toepassen in een praktische schakeling.
- Voldoende materiaal genereren voor gebruik in het eerste jaar.
- Besturing voorzien.





## Schakelingen voor robotwagen
### Stuurschakeling: 
<ul>
  <li>2x UART connectoren</li>
  <li>3x I²C connectoren</li>
  <li>Voltage regulator LDL1117 SMD</li>
  <ul>
      <li>5V</li>
      <li>3V3</li> 
    
  </ul>
  <li>OLED-scherm met I²C-sturing op PCB</li>
  <li>2x SMD Motor driver, vb. LA6583MC-AH</li>
  <li>Polariteitsbeveiliging</li>
  <li>ESP32 WROOM DevKit module</li>
  <li>Batterij aansluiting (GND, VCC)</li>
  <li>Mounting drill holes, voor bevestiging op wagentje</li>
</ul>

### Sensorschakeling: 

<ul>
      <li>Ultrasoon + IR afstandssensoren</li>
      <li>8 channel IR Linetracker</li>
  </ul>
  
### Sturing
<ul>
 <li>Manueel of automatisch rijden</li>
 <li>Hindernissen herkennen en vermijden</li>
</ul>

## Mindmap
![image](https://user-images.githubusercontent.com/91600019/157880859-9cdfd92e-9ed3-454a-b55d-052e98593a98.png)


## Hardware Analyse

### blokschema

### Sturingschakeling:

**Microcontroller:**

**ESP32-WROOM-32 Dev. Board:**
- ESP32 WROOM DevKit module
- Core: ESP32-D0WD
- SPI flash: 4 MB, 32 Mbits, 3.3 V
- Crystal: 40 MHz
- Vcc = 3.0 - 3.6 V
- Ioperating = 80 mA
- Imin delivered by power supply = 500 mA
- Module interfaces: SD card, UART, SPI, SDIO, I2C, LED PWM, Motor PWM, I2S, IR, pulse counter, GPIO, capacitive, touch sensor, ADC, DAC, TWAI.
- On-chip sensor: Hall sensor
- Operating temperature: -40°C ~ +85°C
- Eenheidsprijs: €11,98
- Lead time: 10 weken (op voorraad)

Winkel : https://www.bol.com/be/nl/p/esp-wroom-32-ontwikkelbord/9200000114634593/?Referrer=ADVNLGOO002013-G-137016892532-S-1080766724149-9200000114634593&gclid=CjwKCAjwoduRBhA4EiwACL5RP3gmvcCjgniShMIKJF6Tj-c8ILHCnZigB3Wc8GkKKFBQUkc2TnLEZBoC6nkQAvD_BwE

**Sturing**

**LA6583MC-AH**
- Motor driver
- Single Phase Driver With Hall Sensor Method (no Speed Control)
- SMD IC
- Output Configuration: Half Bridge, 2 outputs
- Vcc = 2.8 - 14 V
- Vcc max = 15 V
- Icc drive = 4 - 6 - 9 mA
- IOUT max = 800 mA
- Eenheidsprijs: 0,526€
- Lead time: onbekend (op voorraad)

Winkel: https://be.farnell.com/on-semiconductor/la6583mc-ah/mtr-drvr-sngl-phase-fan-motor/dp/2728202?st=LA6583MC-AH

**Display**

**Seeed Studio Grove OLED Display**

- 0.96" OLED Display 128x64
- Vcc = 3.3 - 5 V
- Icc = 9 - 15 mA
- Controller: SSD1315
- Comm protocol: I²C
- Connector: JST 4P
- Eenheidsprijs: €4,60 - €7,00

Winkel: https://www.tinytronics.nl/shop/nl/displays/oled/0.96-inch-oled-display-128*64-pixels-wit-i2c

**Voeding**

**Sensorschakeling**

microcontroller:
Sensoren

### Elektrisch schema

## Software Analyse

### Data I/O

### stuurschakeling

### Sensorschakeling

### State diagram /flowchart

**manueel**
**automatisch**
**patroon**

## Plan

### Epics

1. Analyse
2. PCB ontwerp
3. Software ontwikkeling
4. Hardware samenstelling
5. Software implementatie
6. Test

### Sprints
- Analyse 
- PCB ontwwerp
- Afwezig internationaal week Brugge
- Software ontwikkeling
- Hardware samenstelling & Software implementatie & Test
