# robotron EC1834 Floppy Disk Controller Schema

Der Robotron EC1834 ist ein 8086 basierter PC.

Hier ist die digitale Version des Schaltplans des Floppy Disk Controllers von 1988, inkl. Platinen-Layout.
Die Platine wurde aktuell noch nicht geroutet.

Falls sich das jemand antun möchte, halte ich ihn nicht davon ab... ;-)

https://www.robotrontechnik.de/index.htm?/html/computer/ec1834.htm
                       
## Anschlüsse
### DIP Switches

#### S1 Konfiguration
S1:1   - Abfrage /RDYL vom Laufwerk (1=EIN)
S1:2-7 - AUS
S1:8   - EIN bei U8272 D C04 (4 MHz Variante)
S1:8   - AUS bei U8272 D C08 (8 MHz Variante)
		 auch bei NEC D765A (8Mhz)

#### S2 Prüfschalter	 
ohne nähere Erläuterung
S2:1   - AUS
S2:2   - EIN

### Pin Header / Bus Connector

* X1 1 DIN41612 ISA SLOT
* X2 Anschluss externes Floppy
* X3 Floppy 1-2
* X4 Floppy 3-4
* X5 Prüfstecker 1
* X6 Prüfstecker 2
* X7 Prüfstecker 3


### Prüfstecker 


X5
    X5:1 - PLL Frequenz 2000kHz ± 2kHz (via R19)
    X5:2 - DATA WINDOW (mit X5:4)
    X5:3 - Unknown
    X5:4 - READ DATA (mit X5:2)
    X5:5 - N/V

                             ┌─┐                ┌─┐               ┌─┐        
     RDD X5:4          ──────┘ └────────────────┘ └───────────────┘ └─────── 
                                                                             
                          ┌────────┐        ┌────────┐         ┌────────┐    
                       ───┘        └────────┘        └─────────┘        └─── 
     DATA WINDOW                                                             
         X5:2          ───┐        ┌────────┐        ┌─────────┐        ┌────
                          ├────────┤        └────────┤         └────────┘    
                          │<------>│<--------------->│                       
                            1 us           2 us                              
 

X6
    X6:1 - CLK 8000kHz
    X6:2 - TA8 Disable (Signal auf GND)
    X6:3 - WRCLK
    
X7
    X7:1 - ?
    X7:2 - TA8
    X7:3 - /TA4
    X7:4 - TA3
    X7:5 - /TA2

