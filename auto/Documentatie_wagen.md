# Documentatie Robotwagen
### Brian Van Campen
### 2ITIOT

# Probleemstelling

Ontwerp van een schakelingen om een robotwagentje aan te sturen. Dit is opgedeeld in twee schakelingen. Een stuurschakeling PCB met een ESP32 en een trackermodule PCB met een ATMega en sensoren om de sturing te kunnen realiseren.


# As-Is situatie

### MotorWagen: 

![image](https://user-images.githubusercontent.com/91600019/165828954-e81f2889-8426-4b7b-abec-2da97f2bf552.png)


### Specificaties:

- Voltage Regulator LM7805 through hole
- Motor driver SN754410 through hole + 2x 2 motor pins: 1A, 1B, 2A, 2B
- 4x LED's: 1x rood, 2x geel, 1x groen
- LCD scherm module, I²C pins op PCB: GND, SDA, SCL, 3V3
- Ultrasoon module aansluiting: 5V, TRIG, ECHO, GND
- 3 voeding pins: 3V3, 5V, GND
- 2 pin aansluiting: 3V3, PQ_L
- 2x 2 GPIO spare pins


# To-Be situatie

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
  <li>SMD Motor driver, vb. TC78H621FNG(O,EL)</li>
  <li>Polariteitsbeveiliging</li>
  <li>ESP32 WROVER</li>
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


# Hardware Analyse

## blokschema

![image](https://user-images.githubusercontent.com/91600019/165936682-b576b309-730a-43de-adba-fa8ccc5e27eb.png)


### Sturingschakeling:

**Microcontroller:**

**ESP32-WROVER:**
- ESP32 WROVER

Winkel : https://www.bol.com/be/nl/p/esp-wroom-32-ontwikkelbord/9200000114634593/?Referrer=ADVNLGOO002013-G-137016892532-S-1080766724149-9200000114634593&gclid=CjwKCAjwoduRBhA4EiwACL5RP3gmvcCjgniShMIKJF6Tj-c8ILHCnZigB3Wc8GkKKFBQUkc2TnLEZBoC6nkQAvD_BwE

**Sturing**

**TC78H621FNG(O,EL)**


Winkel: https://be.farnell.com/toshiba/tc78h621fng-o-el/motor-driver-ic-h-bridge-tssop/dp/3869999?st=motordriver

**Display**

**Seeed Studio Grove OLED Display**

- 0.96" OLED Display 128x64
- Vcc = 3.3 - 5 V
- Icc = 9 - 15 mA
- Controller: SSD1315
- Comm protocol: I²C
- Connector: JST 4P
- Eenheidsprijs: €4,60 - €7,00

Winkel: https://www.tinytronics.nl/shop/nl/displays/oled/0.96-inch-oled-display-128*64-pixels-wit

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

- ATmega328p 

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

## Elektrisch schema

**ESP32**

![image](https://user-images.githubusercontent.com/91600019/165834512-cccccd1c-e59d-42e8-957e-40d403bd0062.png)

**ATmega328**

![image](https://user-images.githubusercontent.com/91600019/165836377-3e437a59-0724-4ad9-a4ea-843643a98a9a.png)


## PCB ontwerp

**ESP32**

![image](https://user-images.githubusercontent.com/91600019/165935490-a91bb53d-2611-4c0b-9848-46969a8f6130.png)


**ATmega328**

![image](https://user-images.githubusercontent.com/91600019/166685380-d3eef0ae-c65c-43bf-a2cf-0a45c3396451.png)



## Software Analyse

### Data I/O

### stuurschakeling

|Component|Input|Output|
|---------|-----|------|
|ESP-Wrover|config data motor aansturing wifi-sensordata|return data motor|
|motor driver|Motor aansturing PWM|-|
|OLED Display|return data I²C|-|

### Sensorschakeling

|Component|Input|Output|
|---------|-----|------|
|ATMega| Line Tracker data D1-D8 Ultrasoon sensor echo IR-afstandssensor afstand als analoge spanning. |Sensordata I²C Line Tracker IR aan/uit Ultrasoon sensor trigger |
|Line Tracker|IR aan/uit|Data van 8x IR sensoren D1-D8.|
|Ultrasoon sensor|Trigger|Echo|
|IR-afstandssensor|-|afstand analoge spanning|

### State diagram /flowchart

**manueel**

![image](https://user-images.githubusercontent.com/91600019/165838316-70b6748c-1aca-4553-8da2-9e5d61a11ae8.png)

![image](https://user-images.githubusercontent.com/91600019/174058207-b8526711-b13f-4172-a294-bca070d36284.png)


**automatisch**

![image](https://user-images.githubusercontent.com/91600019/165838830-11321749-1f95-4515-b68c-e34e35ae918e.png)


**patroon**

![image](https://user-images.githubusercontent.com/91600019/165839465-ea7a9d60-4b92-49a7-be43-a56b4c27d8b3.png)

![image](https://user-images.githubusercontent.com/91600019/174058926-b8665421-69ea-4248-9bc0-40dfa6a8f0d0.png)


## web interactie

### Node-RED

![image](https://user-images.githubusercontent.com/91600019/174067684-b87f60a8-f7c7-40ac-8dc8-87defbadbd68.png)

### Flow

![image](https://user-images.githubusercontent.com/91600019/174067670-8e435f90-a538-40ed-ad32-c99d51eb7184.png)


## Plan

### Epics

1. Analyse
2. PCB ontwerp
3. Software ontwikkeling
4. Hardware samenstelling
5. Software implementatie
6. Test

## Stories

### 1. Analyse

**Analyse maken**


**Acceptance Criteria:**

- Probleemstelling in 2 tot 5 lijnen
- Mindmap
- Hardware analyse
- Hardware blokdiaram
- Specificatie tabel
- Argumentatie en alternatieven tabel
- Software analyse
- Data In -en Outputs
- State diagram
- Flowchart
- Release plan

### 2.PCB ontwerp

**Sturingsschakeling**


**Acceptance Criteria:**

- 2x UART connectoren
- 3x I²C connectoren
- Voltage regulator 5V & 3.3V
- Polariteitsbeveiliging
- SMD Motor driver
- OLED-scherm met I²C-sturing op PCB
- Batterij aansluiting (GND, VCC)
- Drill holes voor bevestiging van de PCB op het wagentje.

**Sensor schakeling**

**Acceptance Criteria:**

- Ultrasoon
- IR afstandssensoren
- 8 channel IR Line tracker

### 3.Software ontwikkeling

- Manuele bediening
- Automatisch rijden
- Patroon volgen

### 4.Hardware samenstelling

- Sturings PCB solderen
- Sensor PCB solderen
- Robotwagen samenstellen

### 5.Software implementatie

- ESP32 programmeren
- ATmega328 programmeren

### 6.Test

- Componenten
- Data in & out
- Modussen 

### Sprints
- Analyse 
- PCB ontwerp
- Afwezig internationaal week Brugge
- Software ontwikkeling
- Hardware samenstelling & Software implementatie & Test
