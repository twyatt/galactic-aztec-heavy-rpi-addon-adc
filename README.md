# About
[![OSHPark PCB Top Thumbnail](artwork/thumb_top.png?raw=true)](artwork/top.png?raw=true)
[![OSHPark PCB Bottom Thumbnail](artwork/thumb_bottom.png?raw=true)](artwork/bottom.png?raw=true)

Custom Raspberry Pi Add-on ADC board (based on the [Galactic Aztec Raspberry Pi Add-on: Pressure Transducer Interface] board) used to read pressures on the [Galactic Aztec Heavy] rocket. The board has a molex connector for power input (Supply Voltage) and 6 ethernet ports for interfacing with custom [pressure transducer connector boards].

Custom EagleCAD parts on this board can be found in the [SDSU Rocket Eagle Libraries].

## Specifications
| Input | IC      |
|:-----:|:-------:|
| A0    | ADS1114 |
| A1    | ADS1114 |
| A2    | ADS1114 |
| A3    | ADS1114 |
| A4    | ADS1100 |
| A5    | ADS1100 |

### ADS1114
16-bit, 860 SPS ADC

| PGA | Resolution (V) | Maximum Input (V) |
|:---:|:---------------|:-----------------:|
| 2/3 | 0.0001875      | 5.3               |
| 1   | 0.000125       | 4.096             |
| 2   | 0.0000625      | 2.048             |
| 4   | 0.00003125     | 1.024             |
| 8   | 0.000015625    | 0.512             |
| 16  | 0.0000078125   | 0.256             |

### ADS1100
| Bits | Resolution (V) | Sample Rate (SPS) |
|-----:|:---------------|:-----------------:|
| 16   | 0.000152587891 | 8                 |
| 15   | 0.000305175782 | 16                |
| 14   | 0.000610351563 | 32                |
| 12   | 0.00244140625  | 128               |

_Resolution values listed with PGA=1_

## Wiring
The ethernet ports adhere to the following [T-568B] wiring configuration:

| Pin | Color        | Function       |
|:---:|:------------:|:--------------:|
| 1   | Orange/White | Signal         |
| 2   | Orange       | Signal         |
| 3   | Green/White  |                |
| 4   | Blue         | Supply Voltage |
| 5   | Blue/White   | Supply Voltage |
| 6   | Green        |                |
| 7   | Brown/White  | Ground         |
| 8   | Brown        | Ground         |

# Bill of Materials
| Qty | Name  | Description                                    | Notes               | Part Number        | Vendor   |
|:---:|:-----:|------------------------------------------------|---------------------|--------------------|----------|
| 1   | H0    | Header Stacking 2x20 Tall 23mm                 |                     | [1979]             | Adafruit |
| 1   | P0    | Molex Mini Fit Jr. 4-pos Right Angle           |                     | [WM1352-ND]        | DigiKey  |
| 6   | JP0-5 | Jack RJ45 CAT5/CAT5e                           |                     | [380-1046-ND]      | DigiKey  |
| 1   | IC6   | ISO1541 Low-Power Bidirectional I²C Isolator   |                     | [296-34872-1-ND]   | DigiKey  |
| 4   | IC0-3 | ADS1114 16-Bit I²C Analog-to-Digital Converter | Addresses A0-A3     | [296-24932-1-ND]   | DigiKey  |
| 1   | IC4   | ADS1100 16-Bit I²C Analog-to-Digital Converter | Address A4 (100)    | [296-14301-1-ND]   | DigiKey  |
| 1   | IC5   | ADS1100 16-Bit I²C Analog-to-Digital Converter | Address A5 (101)    | [296-14302-1-ND]   | DigiKey  |
| 2   | R0,1  | Resistor 1.8kΩ 1/10W ±1% 0603                  | I²C Pull-up         | [311-1.80KHRCT-ND] | DigiKey  |
| 8   | C0-7  | Capacitor Ceramic 0.1µF ±10% 25V 0603          | Bypass Capacitors   | [490-1524-1-ND]    | DigiKey  |
| 1   | D0    | LED Red Vf=1.8V If=2mA 0603                    | 5V Power Indicator  | [475-1195-2-ND]    | DigiKey  |
| 1   | R2    | Resistor 1.8kΩ 1/4W ±1% 0603                   |                     | [P1.8KBYCT-ND]     | DigiKey  |
| 1   | D1    | LED Yellow Vf=1.8V If=2mA 0603                 | VIN Power Indicator | [475-1196-1-ND]    | DigiKey  |
| 1   | R3    | Resistor 15kΩ 1/4W ±1% 0603                    |                     | [RHM15.0KADCT-ND]  | DigiKey  |


[Galactic Aztec Raspberry Pi Add-on: Pressure Transducer Interface]: https://github.com/twyatt/galactic-aztec-rpi-addon-pressure
[Galactic Aztec Heavy]: http://rocket.sdsu.edu/rockets#galactic-aztec-heavy
[pressure transducer connector boards]: https://github.com/twyatt/galactic-aztec-pressure-transducer-connector
[SDSU Rocket Eagle Libraries]: https://github.com/twyatt/SDSURocket-Eagle-Libraries
[T-568B]: https://en.wikipedia.org/wiki/TIA/EIA-568#Wiring
[1979]: https://www.adafruit.com/product/1979
[WM1352-ND]: http://www.digikey.com/product-detail/en/0039301040/WM1352-ND/561079
[380-1046-ND]: http://www.digikey.com/product-detail/en/SS-7188-NF/380-1046-ND/388308
[296-34872-1-ND]: http://www.digikey.com/product-detail/en/texas-instruments/ISO1541DR/296-34872-1-ND/3587215
[296-24932-1-ND]: http://www.digikey.com/product-detail/en/texas-instruments/ADS1114IDGST/296-24932-1-ND/2123296
[296-14301-1-ND]: http://www.digikey.com/product-detail/en/texas-instruments/ADS1100A4IDBVT/296-14301-1-ND/528555
[296-14302-1-ND]: http://www.digikey.com/product-detail/en/texas-instruments/ADS1100A5IDBVT/296-14302-1-ND/528553
[311-1.80KHRCT-ND]: http://www.digikey.com/product-detail/en/yageo/RC0603FR-071K8L/311-1.80KHRCT-ND/729821
[490-1524-1-ND]: http://www.digikey.com/product-detail/en/murata-electronics-north-america/GRM188R71E104KA01D/490-1524-1-ND/587865
[475-1195-2-ND]: http://www.digikey.com/product-detail/en/LS%20L29K-H1J2-1-Z/475-1195-1-ND/810356
[P1.8KBYCT-ND]: http://www.digikey.com/product-detail/en/ERJ-PA3F1801V/P1.8KBYCT-ND/5036145
[475-1196-1-ND]: http://www.digikey.com/product-detail/en/LY%20L29K-H1K2-26-Z/475-1196-1-ND/810357
[RHM15.0KADCT-ND]: http://www.digikey.com/product-detail/en/rohm-semiconductor/ESR03EZPF1502/RHM15.0KADCT-ND/1983758
