# IOT project

![image](https://user-images.githubusercontent.com/91600019/173873760-71ceed04-5d37-45b9-beb5-00eb2bc54d6a.png)

## beschrijving van het project

Dit project is de 5de iteratie van Farmlab, de bedoeling is om basilicum te groeien en alles er van te automatiseren. Hiervoor moeten aantal onderdelen ontworpen of verbeterd worden. Vervolgens worden er steeds nieuwe iteraties gemaakt met steeds deze verbeteringen.

## Wat is het doel van het project?

Als een team samenwerken aan deelprojecten om zo stap voor stap een volledig project kunnen te verwezenlijken.

Deze iteratie heeft ook als doel de 4de iteratie te fine tunen:

- Herwerken van PCBs
- XY-systeem
- automatisering
- Documentatie

# Pomp controller

### Beschrijving pompcontroller

De pompcontroller moet in staat zijn om het water op het gepaste moment rond te pompen. Hierdoor kunnen er geen algen of andere planten in het water groeien doordat het water te lang heeft stil gestaan. Dit proces moet automatisch gebeuren zodat de gebruiker niet om de zoveel tijd manueel de pomp moet aanzetten. Daarnaast is er nog een tweede pomp om de voedingsstoffen toe te voegen aan het water zodat de planten optimaal kunnen groeien. Ook deze wordt geautomatiseerd en remote aanpasbaar zodat de hoeveelheden voedingstoffen kunnen worden aangepast indien nodig. Tot nu toe werd er gewerkt met een pomp die manueel werd aangestuurd en zitten ze in het proces om te kijken of al de buizen waterdicht zijn. Basilicum heeft verschillende voedingsstoffen nodig om te kunnen groeien. Kalium en calcium zijn twee voedingswaarden waar basilicum voldoende van moet krijgen. Deze moeten op een 1:1 basis worden gegeven. Daarnaast spelen magnesium en stikstof nog een significante rol. Het magnesium gehalte zou 50 ppm moeten zijn. Aan de hand van de electric conductivity (EC) kan er worden gekeken of de basilicum genoeg voedingsstoffen kan opnemen. De EC is het zoutgehalte in het voedingswater en wordt uitgedrukt in μS/cm. De EC zou een waarde tussen 1.6 en 2.2 μS/cm moeten hebben. (Miller, 2020; Smith, 2021; Deepak, 2020; Sandy, 2021)

# Blokdiagram

![image](https://user-images.githubusercontent.com/91600019/165539456-4badd72a-6aa0-4e98-a140-ba2f3281fa0a.png)

<div style="page-break-after: always"></div>

# Elecktrisch Schema

### Microcontroller

![image](https://user-images.githubusercontent.com/91600019/165540538-81c22187-6720-4f9c-b0bf-3acebd8dc536.png)

<div style="page-break-after: always"></div>

### Microcontroller Peripherals

![image](https://user-images.githubusercontent.com/91600019/165540701-a9571016-1667-478b-a546-4da77ca12471.png)
<div style="page-break-after: always"></div>

### Pomp Aansturing

![image](https://user-images.githubusercontent.com/91600019/165540865-9b0e7b98-c11d-4a54-8501-4e307dd046b4.png)

<div style="page-break-after: always"></div>

### Spannings Regelaar 

![image](https://user-images.githubusercontent.com/91600019/165541373-ffcd6622-a634-476a-a338-1bc812f74609.png)

### Voeding & Montage gaten

![image](https://user-images.githubusercontent.com/91600019/165542133-74cd2027-c0d5-486e-992c-df419a1c8eac.png)
<div style="page-break-after: always"></div>

# PCB ontwerp

### Voorkant

KiCad: 

![image](https://user-images.githubusercontent.com/91600019/165544898-ac918bb3-d51f-4f5d-ab53-38924f0e7675.png)

![image](https://user-images.githubusercontent.com/91600019/165542330-8508beab-56f0-4ed9-92a2-73c7dabfee2c.png)




### Achterkant

![image](https://user-images.githubusercontent.com/91600019/165542382-c488735b-913c-4839-8997-d51b20a19b3a.png)

### 3D ontwerp

![image](https://user-images.githubusercontent.com/91600019/166697643-f6117e52-276a-4865-8d4c-58d1a359b8a6.png)

![image](https://user-images.githubusercontent.com/91600019/166701357-500b2369-b82d-4c3d-ab02-1e3eaf8055e9.png)

<div style="page-break-after: always"></div>

# Componenten


|Pomp|Naam|Spanning|Stroom|Vermogen|Link|
|--------|--------|--------|--------|--------|--------|
|![image](https://user-images.githubusercontent.com/91600019/165543210-dbb0adce-757f-4d2a-ae17-64f63fa3d84e.png)|Barwig Typ 04 0444 Laagspanning dompelpomp 600 l/h 6 m|12V|1.7A|20W|<ul>https://www.conrad.be/nl/p/barwig-typ-04-0444-laagspanning-dompelpomp-600-l-h-6-m-539090.html</ul>|






|Component|Soort|Naam|Link|
|--------|--------|--------|--------|
|![image](https://user-images.githubusercontent.com/91600019/165543411-e09bc5d5-a62d-436f-a4a4-63edf3d23ddb.png)|Microcontroller|ESP32-wrover|<ul> https://www.tinytronics.nl/shop/nl/communicatie-en-signalen/draadloos/wi-fi/modules/esp32-wrover-wifi-module-pcb-antenne-aansluiting </ul> <ul>https://www.tinytronics.nl/shop/index.php?route=product/product/get_file&file=1719/esp32-wrover_datasheet_en.pdf</ul>|
|![image](https://user-images.githubusercontent.com/91600019/165543737-006d015a-3ed4-48f4-98cd-d8b8ef467183.png)|Power mosfet|SI2312BDS-T1-E3|<ul> https://be.farnell.com/vishay/si2312bds-t1-e3/mosfet-n-ch-20v-3-9a-sot-23-3/dp/2396085 </ul> <ul>https://www.farnell.com/datasheets/2045689.pdf</ul>|
|![image](https://user-images.githubusercontent.com/91600019/165544066-c5331e54-d0bc-4ff1-91a6-5afd2911dabf.png)|Spannings regelaar|AP7361-33E-13|<ul>https://be.farnell.com/diodes-inc/ap7361-33e-13/ldo-fixed-3-3v-1a-40-to-85deg/dp/3482976</ul>|



<div style="page-break-after: always"></div>

# Din Rail Enclosure

RS PRO Modular Enclosure Enclosure Type, 70.0 x 90.0 x 65.0mm, ABS DIN Rail Enclosure

![image](https://user-images.githubusercontent.com/91600019/165544375-e25acbfb-de92-45d4-8fa2-6ef38c2f1d3f.png)

**Gegevens:**

Category Enclosures Modular for DIN rail
Type Full
Material ABS V0
Variant Without gasket
Height 65.0 mm
Width 90.0 mm
Length 70.0 mm
Color Lightgray (J)
Standards Met RoHS Compliant
Accessories Black hook: 1.0 pcs
Certificate number CE/032/18 Dashed line shows outline of the mounting boss under PCB board

**Afmetingen**

![image](https://user-images.githubusercontent.com/91600019/165544557-c7aaa88f-f07e-4351-b811-2b7809cf69ca.png)

Recommended mounting holes diameter ø3,5mm

**Links**

https://benl.rs-online.com/web/p/din-rail-enclosures/1862295


# Software Analyse

## Data

Data wordt grotendeels verstuurd tussen de centrale ESP32 (broker MQTT en Node-RED) en de ESP32's aanwezig op de PCB's.
Alle data die tussen deze 2 uitgestuurd worden zullen van het type String zijn.

**PompController:**

<ol>

  <ul>
    <li>Node-RED -> Centrale RaspberryPi -> ESP32 op pompcontroller:</li>
    <ul>
      <li>Topics: Pump/water OF Pump/nutrients</li>
      <li>String "on" => Pomp gaat aan</li>
      <li>String "off" => Pomp gaan uit</li>
    </ul>
</ol>
    

| HTTP        |MQTT   |
| ----------- | ----------- |
| Vrij zwaar protocol: de header van een package is al groter dan 1 bericht van MQTT
(min +- 26 bytes header vs enkele bytes MQTT message) | Weinig data → meer keuzes op fysieke laag, trage links worden mogelijk |
| Software stack / Software stack / Library Library is vrij zwaar heeft een zeer kleine footprint | Lightweight → protocol last ook in kleine devices, sensors.. met weinig geheugen & cpu power. |
| Geen ingebouwde Standaard enkele QoS mogelijkheden| Standardisatie, compatibilieit → elk device kan hetzelfde protocol gebruiken → MQTT bouwt verder op de TCP/IP stack|
| | Vereenvoudiging → bij complexe configuraties (zie principe MQTT) |

=>MQTT omdat dit protocol gemaakt is om kleinere bytes aan data door te sturen en dit makkelijk te implementeren is in de opstelling.

<div style="page-break-after: always"></div>

### IOT Dashboard/Platform

**Er is een platform/server nodig om:**

- Verzamelde data weer te geven
- Controle opdrachten te sturen
- Automatisatie programma's te beheren

|Node-RED|Thingsboard|Freeboard.io|
| ----------- | ----------- | ----------- |
| Open-source | Open-source+ professional(betalend) | Open-source |
| Flows | Entities |  |
| no API | API |  |
| Supports MQTT out of the box | Supports MQTT out of the box | Does not support MQTT out of the box (Not actively developed Plugin available) |
| Makkelijk om snel data te kunnen verwerken naar een dashboard aan de hand van flows | Eerder gemaakt voor professionele klanten, werkt met verschillende entities voor apparaten en klanten. |  |

=>Node-RED gebruiken omdat dit ingebouwde MQTT support heeft (Wat Freeboard.io niet heeft) en omdat dit op maat is van het project (Thingsboard zou te uitgebreid zijn).

(De Gendt et al., 2021)

<div style="page-break-after: always"></div>

## Beschrijving van de mogelijke interfaces

Deze kast maakt gebruik van Node-RED die gaat communniceren met een centrale RaspberryPi. Hieruit worden de verschillende controller/sensor ESP32’s aangestuurd.


![image](https://user-images.githubusercontent.com/91600019/173879215-64e4fd66-bb5f-45b5-990f-fdcb946a1600.png)


## Handleiding Web Interactie

Dit is de handleiding om te starten met Node-RED:

1. je surft naar https://nodered.org/
2. je scrollt tot aan Get Started 
![image](https://user-images.githubusercontent.com/91600019/173856720-546ec266-002b-4d37-b8f8-440766e076b4.png)
3. volg deze stappen: https://nodered.org/docs/getting-started/local
4. Je typt in de console

       $ node-red

6. je gaat naar deze link
![image](https://user-images.githubusercontent.com/91600019/173860103-977e0776-5aac-4d56-8cdd-93d900304497.png)
6. Hier kan je de Flow van het project aanmaken
![image](https://user-images.githubusercontent.com/91600019/173860481-4481ca81-cfea-4074-85e7-046a2ac4e456.png)
7. Voor de pomp controller kan je het bestand importeren boven aan rechts of CTRL+I 
![image](https://user-images.githubusercontent.com/91600019/173861188-8d6f1d11-af6c-4de9-aa65-3989a1abe84f.png)
8. zorg er ook voor dat je in Node-RED de plugin Node-red-dashboard installeert door bovenaan rechts manage pallete te kiezen 
9. vervolgens zoek je Node-red-dashboard in de install tab
![image](https://user-images.githubusercontent.com/91600019/173862159-83b7e537-2add-4789-9cc7-1186018d7cdd.png)

10. klik op dashboard bovenaan rechts
![image](https://user-images.githubusercontent.com/91600019/173865857-e49763fd-dbe3-4b9e-a35d-ddac99b32a12.png)

11. hier kan je van alles aanpassen
12. Om de UI te openen klik je op het vierkantje bovenaan rechts
![image](https://user-images.githubusercontent.com/91600019/173864979-6ebb3724-bc87-42da-8f91-b7f8c05d3ab4.png)
![image](https://user-images.githubusercontent.com/91600019/173865114-ac08e7da-b212-4ddf-b465-8797c852b685.png)


### zip van flow
[flows.zip](https://github.com/BrianVanCampen/Farmlab/files/8910688/flows.zip)

### Arduino code

[PompController Arduino Code.zip](https://github.com/BrianVanCampen/Farmlab/files/8911117/PompController.Arduino.Code.zip)

<div style="page-break-after: always"></div>  
  
# Tijdelijke Problemen

![image](https://user-images.githubusercontent.com/91600019/173864206-1f95dce7-247d-451b-9906-92af991ca766.png)


## Testen van PCB

### SpanningsRegelaar

Foute footprint bij spanningsregelaar 5V output in plaats van 3V3 (zie foto)
![image](https://user-images.githubusercontent.com/91600019/173863423-bda24eab-996c-40e8-9d0a-559c63ca2e81.png)

Max waarde ESP32: 

![image](https://user-images.githubusercontent.com/91600019/173866000-3f70db04-26b7-4de7-b629-4c7d9ea35834.png)

De ESP32 kan maar 3.9V max aan 

### Power MOSFET

Geen gepaste MOSFET gebruikt(Through-hole vs SMD) ,IRF9530N inplaats van SI2312BDS-T1-E3


![image](https://user-images.githubusercontent.com/91600019/173863764-473ebb0b-bef5-4efc-9a93-e91127ea9c06.png)

![image](https://user-images.githubusercontent.com/91600019/173863755-8312c63e-c276-41d7-865a-5b5e14d27e15.png)

## Mogelijke uitbreidingen 

- Verkleinen van pcb
- Sensoren toevoegen



