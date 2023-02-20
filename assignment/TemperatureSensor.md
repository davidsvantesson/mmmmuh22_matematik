# Räkna ut temperatur för Arduinos temperatursensor

Arduinos temperatursensor heter TMP36. Vi kan hitta datablad här:
[https://www.arduino.cc/en/uploads/Main/TemperatureSensor.pdf?_gl=1*1ah833y*_ga*MTI2NzY2NjgyNS4xNjU4NTY3NTY1*_ga_NEXN8H46L5*MTY2OTExOTQ1Ny4xMTcuMS4xNjY5MTI3OTMwLjAuMC4w
](https://www.arduino.cc/en/uploads/Main/TemperatureSensor.pdf?_gl=1*1ah833y*_ga*MTI2NzY2NjgyNS4xNjU4NTY3NTY1*_ga_NEXN8H46L5*MTY2OTExOTQ1Ny4xMTcuMS4xNjY5MTI3OTMwLjAuMC4w)

Vi behöver omvanlda från ADC värde (10 bitar) till Spänning.


1.
Från ADC till spänning: 
10 bitar: 0-1023. Motsvarar spänning 0-5V
1023 / 5V ger oss ADC-värde per spänning. 
float spänning_in = (float) indata * 5/1023 (V)

2. 
Vad är referensspänningen / referenstemperatur? 
(Se TMP36 Output Voltage, TA = 25°C, ger 750mV ut)
Dra bort denna spänning, då kan vi räkna ut temperatur från referenstemperaturen
referens_spänning = spänning_in - 0.750;

3.
Vad är Scale factor (mV/C)?
1mV = 0.001V
10mV = 0.01V. 
10mV / C
Dela med denna så omvandlar vi från volt till celcius
relativ_temperatur = referens_spänning (V) / 0.01 (mV/C)   // Ger C


4.
Lägg på (addera) referenstemperaturen (25C)
Nu har vi omvandlat från ADC till temperatur!
absolut_temperatur = relativ_temperatur + 25




Lägg ihop allt:
Man kan göra beräkningen i fyra steg (fyra kod-instruktioner).
Snyggare är att göra det i en beräkning.
Ännu bättre: Förenkla! Det går att räkna ut som
temp = temp * A - B
Där A och B är två tal.