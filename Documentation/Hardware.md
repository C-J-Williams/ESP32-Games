# Hardware Components

The ESP32 Games Machine has been designed around readily available, off-the-shelf electronic components to make sourcing parts and assembling the project as straightforward as possible.

The custom PCB has been designed to accommodate these components, minimising the need for specialist parts and simplifying construction.

## Required Components

The following components were used in the development and construction of this project.

| Component | Description |
|---|---|
| PSP 1000 Joystick | Analogue joystick module used for game controls. |
| ESP32-WROOM-32 Development Board | Main microcontroller responsible for running the games and managing the hardware. |
| 2.0-inch TFT Display | SPI colour display, 240 × 320 resolution, using the ST7789 controller. |
| MAX98357 Audio Amplifier | I2S digital audio amplifier for sound output. |

## Component Suppliers

The components used during development were purchased from AliExpress. The links below are provided as a reference to the specific products used when designing and assembling the machine.

These are not exclusive suppliers. The components, or equivalent alternatives, are generally available from other electronics suppliers and online retailers. Buy from where ever you find it cheaper.

- **PSP 1000 Joystick** – [AliExpress](https://www.aliexpress.com/item/1005006347196648.html)
- **ESP32-WROOM-32 Development Board** – [AliExpress](https://www.aliexpress.com/item/1005006476877078.html)
- **2.0-inch TFT SPI Display (ST7789, 240 × 320)** – [AliExpress](https://www.aliexpress.com/item/1005006388926254.html)
- **MAX98357 I2S Audio Amplifier** – [AliExpress](https://www.aliexpress.com/item/1005007003802663.html)

*Product listings, availability and pricing may change over time. Always check the component specifications before purchasing.*

## Optional / Alternative Components

### ESP32-WROOM-32E Series Module (N16R2)

[AliExpress – ESP32-WROOM-32E N16R2](https://www.aliexpress.com/item/1005005466233411.html)

This is an alternative for users who wish to have larger storage for their Games Machine. You can use the ESP32-WROOM-32 and remove the module using a hot air station and replace the module with one of these.

**This component is NOT required when using the standard ESP32-WROOM-32 development board listed above.**

## Component Selection

The project is intended to be relatively accessible to hobbyists and makers.

Where possible, standard commercially available components have been selected to:
- Make parts easier to source.
- Keep assembly relatively simple.
- Avoid unnecessary specialist components.
- Allow users to substitute equivalent components where appropriate.

Please refer to the PCB folder for the Bill of Materials (BOM), Gerber manufacturing files and original PCB design file.
