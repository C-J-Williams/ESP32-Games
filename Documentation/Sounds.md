# Creating New Sounds

## 1. Find or Create Your Sound

Find or create the sound effects you want to use in your game.

You can download existing sound effects or create your own. The audio files can be in WAV or MP3 format.

Once you have your sound, we need to convert it into a format that can be stored directly in the ESP32's program memory.

## 2. Create a New Tab in Arduino IDE

Open your Arduino project and create a new tab for the sound effect.

Give the tab a name that describes the sound, for example:

`coin.h`

Use the name of the sound effect as the filename. This will make it easier to keep track of your sounds.

## 3. Convert Your Sound Using Audacity

We first need to convert the sound into a RAW audio file.

Download and open **[Audacity](https://www.audacityteam.org/)** (available for free).

1. Open Audacity.
2. Select **File → Open** and locate your sound file (WAV or MP3).
3. Once the sound is loaded, select **File → Export**.
4. Use the following export settings:

| Setting | Value |
|---|---|
| Type | Export full project audio |
| Filename | A suitable name, e.g. `coin` |
| Folder | Choose where you want to save the file |
| Format | Other uncompressed files |
| Channels | Mono |
| Sample Rate | 16000 Hz |
| Header | RAW (header-less) |
| Encoding | Signed 16-bit PCM |

5. Click **Export** to save your file.

You should now have a `.raw` audio file.

### Convert the RAW File to HEX

We now need to convert the RAW file into HEX data that can be added to our Arduino program.

Go to the following website:

[Tomeko – File to HEX Converter](https://tomeko.net/online_tools/file_to_hex.php)

1. Upload the `.raw` file you created in Audacity.
2. Click **COPY OUTPUT TO CLIPBOARD**.

Your converted sound data is now ready to paste into Arduino IDE.

## 4. Paste the Sound Data into Arduino IDE

Return to the new tab you created in Arduino IDE.

Paste the following template into the tab:

```cpp
#pragma once

#include <stdint.h>

const uint8_t newsound_raw[] PROGMEM = {

// Paste raw data here

};

const size_t newsound_raw_length = sizeof(newsound_raw);
```

You now need to replace `newsound` with the name of your sound effect.

For example, if your sound is called `coin`, the first line should become:

```cpp
const uint8_t coin_raw[] PROGMEM = {
```

And the final line should become:

```cpp
const size_t coin_raw_length = sizeof(coin_raw);
```

Paste the HEX data you copied from the Tomeko website between the curly brackets.

**Important – Understanding File and Variable Names**

There is a difference between the filename and the variable names used in the code.

For example, if your sound effect is called `coin`:

- The Arduino tab (filename) must be called `coin.h`.
- The variable name must be called `coin_raw`.
- The length variable must be called `coin_raw_length`.

**Do not include `.h` in the variable names.** The `.h` extension is only used for the filename.

Make sure you use the same name consistently throughout the template and when playing the sound.

## 5. Include the Sound in AudioAssets.h

Open the `AudioAssets.h` tab in Arduino IDE.

Add an include statement for your new sound file underneath the other sound files that are already included.

For example:

```cpp
#include "win.h"

#include "newsound.h"
```

Replace `newsound.h` with the actual filename of your sound.

**Important:** The filename, including capital letters and the `.h` extension, must match the Arduino tab exactly.

## 6. Play Your Sound

Your sound is now ready to use in your game!

To play it, use the following command:

```cpp
playPCM(newsound_raw, newsound_raw_length);
```

Make sure `newsound_raw` and `newsound_raw_length` match the variable names you used in your sound file.

For example, to play the sound called `coin`, use:

```cpp
playPCM(coin_raw, coin_raw_length);
```

That's it! Your sound effect is now stored in the ESP32's program memory and can be played directly by your game without needing an SD card.
