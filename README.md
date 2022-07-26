# ESP32 IO IHM

Kit de desenvolvimento para aplicação em aulas de eletrônica: 
* Instalação de componentes com tecnologias de montagem PTH(*Pin Through Hole*) e SMD(Surface Mounted Device).
* Validação de montagem e manutenção se necessário.
* Programação em linguagem C.
* Interface com periféricos:
	* Display de cristal líquido (LCD);
	* Teclado matricial 4x4;
	* Entradas digitais (12Vdc);
	* Saídas digitais (Relé e Tiristor e Transistor (open-collector);
	* Conector para módulo de acionamento de motor de passo (DRV8825);
	* Expansão de Entradas e Saídas por registrador de deslocamento;
	* Módulo ESP32:
		* WiFi
		* Bluetooth
* [Firmware](https://github.com/JoseWRPereira/esp32_io-ihm-prototipo) de teste de protótipo parcial em placa padrão.

## Hardware

| Figura 1: Vista 3D da placa de desenvolvimento |
|:----------------------------------------------:|
|![ESP32 IO Top 3D](https://github.com/JoseWRPereira/esp32_io_ihm/blob/main/img/esp32_IO-top3D.PNG)|
| Fonte: Próprio autor |



| Figura 2: Camada de serigrafia |
|:------------------------------:|
|![ESP32 IO Top Silkscreen](https://github.com/JoseWRPereira/esp32_io_ihm/blob/main/img/esp32_IO-topsilk.PNG)|
| Fonte: Próprio autor |


| Figura 3: Camada superior      |
|:------------------------------:|
|![ESP32 IO Top Layer](https://github.com/JoseWRPereira/esp32_io_ihm/blob/main/img/esp32_IO-toplayer.PNG)|
| Fonte: Próprio autor |


| Figura 4: Camada inferior      |
|:------------------------------:|
|![ESP32 IO Botton layer](https://github.com/JoseWRPereira/esp32_io_ihm/blob/main/img/esp32_IO-botlayer.PNG)|
| Fonte: Próprio autor |




# Montagem

<!-- "26"	"0R"	"R55,R56,R57,R59"	"5" // Não Montar - Drive de motor de passo -->
<!-- "17"	"10K"	"R6"	"1" Potenciometro -->
<!-- "16"	"9k1"	"R5"	"1" // divisor de tensão do LCD --> 
<!-- "18"	"760R"	"R7"	"1" // divisor de tensão do LCD -->
<!-- "2"	"47uF"	"C1,C3,C5,C7,C9,C10"	"6" *** PAD pequeno 100uF -->


| nº  | Componente | Valor | Quantidade | Referência |
|:---:|:----------:|:-----:|:----------:|:----------:|
| 1   | Resistor   | 10K   | 19         | R1,R2,R3,R4,R34,R35,R36,R37,R42,R43,R44,R45,R54,R10,R16,R22,R27,R13,R21 |
| 2   | Resistor   | 1K    | 1          | R48        | 
| 3   | Resistor   | 330R  | 5          | R49,R51,R50,R24,R29 | 
| 4   | Resistor   | 150R  | 2          | R52,R53 | 
| 5   | Resistor   | 100R  | 8          | R8,R14,R19,R25,R11,R17,R23,R28 |
| 6   | Resistor   | 180R  | 6          | R9,R12,R15,R18,R20,R26 |
| 7   | Resistor   | 470R  | 8          | R30,R31,R32,R33,R38,R40,R41,R39 |
| 8   | Resistor   | 0R    | 1          | R58 |
| 9   | Resistor   | 27R   | 2          | R46,R47 |
| 10  | Capacitor  | 470nF | 4 | C2,C4,C6,C8 |
| 11  | Diodo Zener| ZMM55-C5V1| 8 | D4,D5,D6,D7,D8,D9,D10,D11 |
| 12  | Diodo      | LS4148    | 6 | D2,D3,D_L1,D_L2,D_L3,D_L4 |
| 13  | LED        | LED-0805_Y| 2 | LED21,LED22 |
| 14  | LED        | LED-0805_R| 9 | LED17,LED1,LED2,LED3,LED4,LED5,LED6,LED7,LED8 |
| 15  | LED        | LED-0805_G| 11 | LED9,LED10,LED11,LED12,LED13,LED14,LED15,LED16,LED18,LED19,LED20 |
| 16  | CI         | SN74HC595DR    | 4  | U1,U3,U21,U40 |
| 17  | CI         | CD74HC165M     | 3  | U2,U33,U41 |
| 18  | Chave Táctil | K4-6×6_SMD   | 16 | S1,S2,S3,S4,S5,S6,S7,S8,S9,S10,S11,S13,S14,S15,S16,S12 |
| 19  | Regulador de Tensão | AMS1117-3.3 | 1 | U37 |
| 20  | Capacitor Eletrolítico | 47uF | 6 | C1,C3,C5,C7,C9,C10 |
| 21  | Diodo  | 1N4007 | 1 | D1 |
| 22  | Opto-acoplador | PC817 |14 | U7,U9,U10,U13,U15,U18,U22,U23,U24,U25,U26,U27,U28,U29 |
| 23  | Transistor | BC337 | 6 | T1,T2,T3,T4,T5,T6 |
| 24  | Opto-tiristor | MOC3061M | 2 | U17,U20 |
| 25  | Tiristor | BT136 | 2 | Q1,Q2 |

<!-- "1"	"R_3296W_US"	"RP1"	"1" -->
<!-- "37"	"LM7805T"	"U35,U36"	"2" -->
<!-- "44"	"USB_B"	"X1"	"1"  -->



ID	Name	Designator	Quantity
"7"	"KH-2.54PH180-1X19P-L11.5"	"H1,H2"	"2"
"8"	"KH-2.54PH180-1X4P-L11.5"	"H3"	"1"
"9"	"KH-2.54PH180-1X15P-L11.5"	"H4,H5"	"2"
"10"	"KH-2.54PH180-1X6P-L11.5"	"H6"	"1"
"11"	"KH-2.54PH180-1X8P-L11.5"	"H7,H8"	"2"
"12"	"Header-Female-2.54_1x9"	"H9,H10"	"2"
"13"	"IDC_14P_M"	"H11"	"1"

"14"	"Relay PCB 5V"	"K1,K2"	"2"


"32"	"200014-1"	"U4,U5,U6"	"3"
"34"	"KF301-5.0-3P"	"U8,U11,U12,U14,U30,U31,U32"	"7"
"35"	"KF301-5.0-2P"	"U16,U19,U34"	"3"
"39"	"KH-2.54FH-1X4P-H8.5"	"U38,U39"	"2"
"40"	"KH-2.54PH180-1X16P-L11.5"	"LCD1"	"1"
"41"	"LMB162ADC"	"LCD2"	"1"

cz gnd
vd D+
br D-
vm 5v


<!-- 
PI3

* Framework web
* Aplicativo Móvel
* Banco de dados
* Script Web (Java script)
* Nuvem
* Acessibilidade
* Controle de versão
* Integração Contínua
* Testes
* API (Consumo e fornecimento)
* Análise de Dados
* IoT 
-->