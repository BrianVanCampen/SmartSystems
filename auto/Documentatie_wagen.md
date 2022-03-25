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

**Conrad Energy LiPo accupack**

- Vnomonaal = 7.4 V
- Inominaal = 1200 mAh
- Aantal cellen: 2
- Belastbaarheid: 20 C
- Aansluiting: XT60, XH-balancer
- Afmetingen: 112 x 35 x 19 mm
-Eenheidsprijs: €16,49




Winkel : https://www.conrad.be/nl/p/conrad-energy-lipo-accupack-7-4-v-2400-mah-aantal-cellen-2-20-c-softcase-xt60-1344133.html?t=1&utm_source=google&utm_medium=surfaces&utm_term=1344133&utm_content=free-google-shopping-clicks&utm_campaign=shopping-feed&vat=true&gclid=CjwKCAjwxOCRBhA8EiwA0X8hi6Dpvaew0u-kTnIyrUmKE2RRHzkksSaw41QoJ36AmjOCY1n-dP7VnRoC240QAvD_BwE&gclsrc=aw.ds&tid=13894944235_122657379817_pla-301443522443_pla-1344133&WT.srch=1


**Voltage regulator**

**LDL1117S50R**

- Voltage Regulator 5 V
- Package: SOT223 SMD
- Voutput = 5 V
- Vinput = 2.5 - 18 V
- Ioutput = 1.2 A
- Eenheidsprijs: €0,56

**Polarriteit beveiliging**

**DMG3414U**

- N-channel MOSFET
- Package: SOT-23 SMD
- Vds = 20 V
- Id = 4.2 A
- Rds(on) = 0.019 ohm
- Vgs(th) = 500 mV
- Pd = 780 mW
- Eenheidsprijs: 0,72€

reden: 	De DMG3414U heeft een lage threshold spanning zodat deze ook geleid bij een lage spanning, en een Vds en Id die hoog genoeg zijn zodat de MOSFET niet stuk gaat in een schakeling met een 7.2 V batterij. 

Winkel :https://nl.farnell.com/diodes-inc/dmg3414u/mosfet-n-ch-w-diode-20v-4-2a-sot23/dp/2061404?st=mosfet%20n%20smd

**Sensorschakeling**

microcontroller:

- ATmega328p of arduino Nano

reden: sensoren moeten op een apart bordje komen zodat de line tracker dicht tegen de grond zit. eenvoudiger om een extra Microcontroller hiervoor te gebruiken door teveel verbindingen --> 1 I²C verbinding nodig tussen de 2 bordjes 



**Sensoren**

**MJKDZ MIR-3.0Y**

- 8x IR Line Tracking Module
- Vcc = 3 - 5 V
- Bereik (max. bij 5V) = 40 mm
- Afmetingen LxB: 17 x 67 mm
- Eenheidsprijs: €6,00

Winkel :https://www.tinytronics.nl/shop/nl/sensoren/optisch/infrarood/8x-ir-lijn-tracking-module-40mm-bereik


**Sharp GP2Y0A21YK0F**

- IR-afstandssensor
- Vcc = 4.5 - 5.5 V
- Ityp = 30 mA
- Bereik: 50 - 800 mm
- Afmetingen: 29.5 x 13 x 13.5 mm
- Eenheidsprijs: €5,50 - 12,06

winkel: https://www.tinytronics.nl/shop/nl/sensoren/afstand/sharp-optische-afstandsensor-gp2y0a21yk0f

**HC-SR04**

- Ultrasoon afstandssensor
- Vcc = 5 V
- Icc = <2 - 15 mA
- Bereik: 20 - 4500 mm
- Resolutie: 3 mm
- Sensor hoek: <15°
- Ultrasone freq.: 40 kHz
- Eenheidsprijs: €3,00 - 7,21

winkel:https://www.tinytronics.nl/shop/nl/sensoren/afstand/ultrasonische-sensor-hc-sr04

### Elektrisch schema

## Software Analyse

### Data I/O

### stuurschakeling
|Component|Input|Output|
------
||||||||

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
