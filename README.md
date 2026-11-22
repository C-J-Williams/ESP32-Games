# ESP32 Game Machine

A custom-built handheld game machine powered by an ESP32, designed and built from the ground up as a complete hardware and software project.

The project combines a custom electronics design with a 320 × 240 colour TFT display, joystick and physical controls, audio output, and a custom 3D-printed enclosure. The goal was to make the machine as easy to assemble and as cheap to make as possible using mostly off the shelf components. The ESP32 provides enough processing power and memory to run colourful games with animated graphics, sprites, sound effects and responsive controls.

The machine is designed to be a flexible platform for developing and experimenting with different games. Graphics and other game assets can be stored directly in the ESP32's flash memory, allowing games to load their own backgrounds, sprites and animations without the need for an SD card.

This project was originally designed to work with a N16R2 it uses the custom partition map included in the Arduino folder, this however requires the module to be removed from the Development Board and be replaced. If you have a hot air station this is easily done. This project will work with a standard N4xx but will be limited in the number of games and sound effects that can be loaded. It is also very important that when using a N4xx you delete the partition.csv file from the folder. If you don't everything will compile and upload perfectly but the board will never boot.

The hardware has been designed specifically for the project while the software is structured so that new games and features can be added as the project develops.

### Requirements to Build
- ESP32 WR-32 Development Board
- ESP32-WROOM-32E Series Modules N16R2 `if wanted, needs to replace the N4XX module`
- 2.0 inch TFT screen SPI 240x320 ST7789
- MAX98357 Audio amplifier
- PSP-1000 joystick
- Custom PCB
- Various components `see the BOM`


The project was developed as a teaching tool for primary aged students. It will continue to evolve as new games, hardware features and software capabilities are developed.
