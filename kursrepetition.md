
Kursens innehåll (kan komma på tentan):

- Talsystem som binära, oktala och hexadecimala tal
- Representation av tal och aritmetik i datorer
- Boolesk algebra, logik och funktioner
- Algebra inklusive matriser
   - Formler vid mätning och omvandling.
   - --> Kunna hantera fysiska formler
- Grundläggande sannolikhet och statistik
- Trigonometri
   - Beräkna vinklar
   - Enhetscirkeln
   - Sinus och cosinus funktion och grafer


Flesta uppgifter har helt påhittade värden.
En VG uppgift ska man räkna ut något i verkligheten. Värdena är ändrade lite, så det ni får när ni räknar ut stämmer inte exakt med vad ni kan hitta på t.ex. Wikipedia.




## Sannolikhet

$$
P(A) = \frac{g}{m}
$$

Säg att man kastar två tärningar (6-sidiga). Vad är sannolikheten att man får minst 12 i summa?

Ett enda fall: 6 + 6.  $g = 1$<br>
Antal möjliga utfall? 36

Sannolikheten att få (minst) 12 är $1/36=2.78\%$

Sannolikheten att jag får 13 i summa? 0%

Sannolikheten att få max 12 i summa (12 eller mindre): 100%

Sannolikhet att få mindre än 12 i summa? $P(\neg sum \geq12)=1-1/36=35/36=97.22\%$ 

### Två händelser oberoende
Vi ska kasta två tärningar. Vad är sannolikheten att vi får minst 8 i summa?

Sannolikheten att få summa 8 är $5/36$.

Sannolikheten att få minst summa 8 (summa 8 elle högre): Summa 8 eller 9 eller 10 eller 12 --> $15/36$

### Betingad sannolikhet
Du ska kasta två tärningar. Du kastar den första och får 4. Du ska sen kasta den andra tärningen. Vad är sannolikheten att vi får minst 8 i summa på båda tärningarna?

$$
P(sum\geq8|T_1=4)
$$

$$
sum = T_1+T_2\geq8
$$

$$
T_2 \geq 8-T_1 = 4
$$

Vad är sannolikheten att $T_2\geq4$

Utfall för T2: 1, 2, 3, 4, 5, 6

$$
P(T_2\geq4) = 3/6 = 1/2 = 0.5 = 50\%
$$

### Kortlek
52 kort.

Du drar Hjärter Dam.
Vad är sannolikheten att få ytterliggare en hjärter?

#### Fråga 1:
Total utfallsrymd? 51 kort <br>
Hur många hjärter? 12 hjärter kvar<br>

Sannolikheten är $12/51$

#### Fråga 2
Vad är sannolikheten att få ytterliggare en damer?

$P=3/51$

#### Fråga 3
Vad är sannolikheten att få ytterligare tre damer?

P = 

### Kortlek - fyra damer
En kortlek - 52 kort. Dra kort  en och en.

$P(dam)\cdot P(dam efter dam)\cdot P(dam efter två damer)\cdot P(dam efter tre damer)$

$P(4\  damer)=\frac{4}{52}\cdot\frac{3}{51}\cdot\frac{2}{50}\cdot\frac{1}{49} =$

#### Alternativ
Ta ett kort. Stoppa tillbaks och dra ett nytt

$P(dam)^4$

$P(4\  damer)=\frac{4}{52}\cdot\frac{4}{52}\cdot\frac{4}{52}\cdot\frac{4}{52}$

### Sannolikhet - Eller

Vad är sannolikheten att slå en 1 eller 6a?

$$
P(1\mathrm{or}6) = \frac{2}{6} = 1/3
$$

$$
P(1\mathrm{or}6) = P(1) + P(6) = \frac{1}{6} + \frac{1}{6} = \frac{1}{3}
$$

## Statistik

- Olika sortera diagram
- Lägesmått
- Standardavvikelse / normalfördelning

### Lägesmått:

- Minsta
- Största
- Medeltal / average: 

$$
\mu = \frac{1}{N}\sum x_i
$$

- Median. Talet i mitten. 50% av mätvärdena är lägre, 50% är högre. Samma som andra kvartil
- Första kvartil = 25 percentil. Värdet där 1/4=25% av alla är lägre, 75% är högre
- Tredje kvartil = 75 percentil.
- Percentil: Hur många som har lägre värde
- Typvärde: Värdet som förkommer oftast.

#### Standardavvikelse

Vi har 10000 personer. Medellängd är 172 cm Standardavvikelsen är 12 cm.

Ungefär hur många personer är mellan 160 och 184 cm?

~6800 personer bör falla inom den längden, om man antar någorlunda normalfördelat.

3000 person inte rimligt<br>
9000 person inte rimligt<br>
6000-7500 kan vara rimligt<br>

Mellan 160 till 172 cm. Endast nedanför medel

Mellan 148 till 172 cm. (två standardavvikelser __nedanför__ medel): ~47.5%

Mellan 148 och 196 cm (två standardavikelser från medel): ~95%

## Logiska grindar och boolesk algebra

- Logiska grindar och sanningstabeller
  - YES
  - NOT
  - AND
  - NAND
  - OR
  - NOR
  - XOR
  - XNOR

- Bitvis beräkningar

- Grindnät. 
  - Booleska ekvationer
  - Sanningstabell 
  - Förenkling (Generellt VG nivå)

## Talsystem

- Binärt --> Hexadecimalt
- Binärt --> Decimalt
- Decimalt --> Binärt
- Decimalt --> Hexadecimalt
- Hexadecimalt --> Binärt
- Hexadecimalt --> Decimalt

På tentan oftast något verkligt exempel på användning eller kod.

### Representation av tal och aritmetik
- Bitvis beräkningar
- Hur kan man få ut en del av ett tal / signal
- Göra beräkning i binär och hexadecimal form
- Lagring av tal i datorn. Visst antal bitar/byte.
- MSB/LSB och big endian / little endian

Kan vara fråga på VG nivå, beroende på svårighetsgrad

#### Bitvis beräkningar

```
uint32 A = 0x1234;
uint32 B = 0x00FF;
uint32 C = A & B;
uint32 D = A | B;
uint32 E = ~C;
uint32 F = ~D;
```

Vad är C?

A = 0b0001 0010 0011 0100<br>
B = 0b0000 0000 1111 1111<br>
C = 0b0000 0000 0011 0100<br>

Man kan också tänka att sista hex siffrorna i A filtreras ut: C = 0x0034

Vad är D?

D = 0b0001 0010 1111 1111<br>
D = 0x12FF

~0x0 = 0xF<br>
~0x1 = 0xE<br>
~0x2 = 0xD<br>
~0x3 = ~0b0011 = 0b1100 = 12 = 0xC<br>
~0x4 = ~0b0100 = 0b1011 = 11 = 0xB<br>

~0xH = 0xF - 0xH


E = 0xFFCB

F = 0xED00

##### Ett annat exempel
```
uint32 X = 0x1234 & 0x5678;
```

```
0x1&0x5 = 0001 & 0101 = 0001 = 0x1
0x2&0x6 = 0x2
0x3&0x7 = 0x3
0x4&0x8 = 0100 & 1000 = 0x0

X = 0x1230
```

#### Bit order

Skriv ner deciamala talet 173 i binär form (en byte) men LSB först.

173/16 = 10 = 0xA
173 mod 16 = 13 = 0xD

173 = 0xAD = 0b1010 1101 med MSB först 

LSB först: 0b10110101


#### Signaler

```
uint16 msg = 0x1234;
```

Hur kan jag dela upp denna i följande signaler

- signal1: bit 8-15
- signal2: bit 4-7
- signal3: bit 0-3

Vilket värde har signalerna?

msg: 0001001000110100b

- signal1: 00010010b = 0x12 = 18
- signal2: 0011b = 0x3 = 3
- signal3: 0100b = 0x4 = 4

Hur kan jag programmera för att få ut de?

```
int signal3 = msg & 0b0000000000001111 >> 0;


int signal3 = msg & 0x000F >> 0;
ing signal2 = msg & 0x00F0 >> 4;
int signal1 = msg & 0xFF00 >> 8;
```

Åt andra hållet. Om man ska lagra in siffor i en signal

```
msg = (signal1 << 8) | (signal2 << 4) | signal1;
```

#### Lagring och hantering av tal

Kom ihåg, antalet bitar är begränsat i en viss variabel.

Vi kan få olika runtime error, om CPUn stödjer det. Men ALUn ger alltid ett output.

Givet vi inte får runtime error, vad lagras i v?

```
uint16 v = 0xFFFF + 1  // 0xF + 1 = 0x10. Varje siffra får en minnessiffra. Resultat blir slutligen 0x10000. Det som lagras är 0x0.
```

```
uint16 w = 0xFFFF + 2  // 0xF + 2 = 0x11. Det vill säga 1 med en minnessiffra. 0xF + 1 = 0x10. Varje siffra får en minnessiffra. Resultat blir slutligen 0x10001. Det som lagras är 0x0001.
```

## Algebra och fysik

### Enhetsanalys. Hantering av enheter och prefix


## Trigonometri