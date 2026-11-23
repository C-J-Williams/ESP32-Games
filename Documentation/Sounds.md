# Creating Audio Files for the Games Machine

This guide explains how to create and add new sound effects to the ESP32 Games Machine firmware.

## 1. Find or Create Your Sound Effects

First, find or create the sound effects you want to use in your Games Machine.

You can use existing WAV or MP3 files or create your own.

## 2. Convert the Audio Using Audacity

Download and install [Audacity](https://www.audacityteam.org/), which is available free of charge.

1. Open Audacity.
2. Open your WAV or MP3 file using **File → Open**.
3. Go to **File → Export**.
4. In the export dialogue box, make the following settings:

   | Setting | Value |
   |---|---|
   | Type | Export full project audio |
   | File Name | A useful name for the file (e.g. coin) |
   | Folder | Choose a folder where you can easily find the exported audio |
   | Format | Other uncompressed files |
   | Channels | Mono |
   | Sample Rate | 16000 Hz |
   | Header | RAW (header-less) |
   | Encoding | Signed 16-bit PCM |

5. Press **Export**.

This will create a `.raw` audio file.

## 3. Convert the RAW File into HEX Data

Go to the following website:

[Tomeko – File to HEX Converter](https://tomeko.net/online_tools/file_to_hex.php)

1. Click **Upload a file**.
2. Select the `.raw` file you created in Audacity.
3. Click **COPY OUTPUT TO CLIPBOARD**.

The converted audio data is now ready to be added to your Arduino project.

## 4. Create a New Arduino IDE Tab

In the Arduino IDE, create a new tab and give it a name matching your sound effect.

For example:

`newsound.h`

Copy the following template into the new tab:

```cpp
#pragma once

#include <stdint.h>

const uint8_t newsound_raw[] PROGMEM = {

// Paste raw data here

};

const size_t newsound_raw_length = sizeof(newsound_raw);
```

Replace `newsound` with a meaningful name for your sound effect, such as:

- `coin`
- `hit`
- `win`

**Important:** Every sound effect must have a unique name. It must not be the same as any other sound already in your project.

Now paste the HEX data copied from the Tomeko website into the area marked `// Paste raw data here`.

Make sure all the variable names match. The name used in the array declaration must also be used in the length declaration.

For example, if your sound is called `coin`, the declarations should become:

```cpp
const uint8_t coin_raw[] PROGMEM = {

// Paste raw data here

};

const size_t coin_raw_length = sizeof(coin_raw);
```

**Important – Understanding File and Variable Names**

There is a difference between the filename and the variable name used in the code.

For example, if your sound effect is called `coin`:

- The Arduino tab (filename) must be called `coin.h`.
- The variable name in the code must be `coin_raw`.
- The length variable must be called `coin_raw_length`.

**Do not include `.h` in the variable names.** The `.h` extension is only used for the filename.

Make sure you use the same name consistently throughout the template and when calling the sound in your program.

## 5. Add the New Sound to AudioAssets.h

Open the `AudioAssets.h` tab in the Arduino IDE.

Add an include statement for the new sound file underneath the other includes.

For example:

```cpp
#include "win.h"

#include "newsound.h"
```

Use the exact filename of the tab you created in Step 4.

**Important:** Capitalisation is extremely important. The filename and include statement must match exactly.

Also make sure the filename is not already being used by another sound file.

## 6. Playing Your New Sound Effect

Your new sound effect can now be played from within the Games Machine program using the following command:

```cpp
playPCM(newsound_raw, newsound_raw_length);
```

Replace `newsound` with the name you assigned to your sound effect.

For example, to play the coin sound:

```cpp
playPCM(coin_raw, coin_raw_length);
```

That's it! Your new sound effect is now included in the Games Machine firmware and can be played whenever required.

---

**Tip:** Give your sound files descriptive names and keep them organised. This makes it much easier to identify and manage audio assets as you add more games and sound effects to the project.
