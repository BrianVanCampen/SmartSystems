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
