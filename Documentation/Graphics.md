# Creating New Graphics and Sprites

## 1. Find or Create Your Graphics

Find or create the sprites, backgrounds or other graphics you want to use in your game.

The maximum screen size is **320 × 240 pixels** (landscape orientation).

Most of the sprites used in the games are **16 × 16 pixels**. This gives us a grid of 20 cells horizontally and 15 cells vertically across the screen.

You can create or resize your graphics using [GIMP](https://www.gimp.org/), which is available as a free download.

Once your graphics are ready, export them as **PNG files**.

## 2. Create a New Tab in Arduino IDE

Open your Arduino project and create a new tab for the graphic.

Give the tab a name that describes the graphic, for example:

`newsprite.h`

**Tip:** Use the name you intend to give the graphic when creating the tab. This will make it easier to keep track of your files.

## 3. Convert Your Image

We need to convert the PNG image into a format that can be used by the ESP32.

Go to the following website:

[Rinky-Dink Electronics – Image Converter](http://www.rinkydinkelectronics.com/t_imageconverter565.php)

Follow these steps:

1. If the correct page hasn't opened, click **UTFT – Image Converter** on the left-hand side.
2. Click the **CHOOSE FILE** button and select your PNG image.
3. Select the **.c** radio button.
4. Click **MAKE FILE**.

The website will take a few moments to convert your image.

Once it has finished, you will see your graphic displayed with a link underneath saying **"Click here to download your file"**.

Click this link to download the converted file.

**Important:** Your browser may display a download warning. You must select the option to **Keep** the file, otherwise it may not download.

## 4. Add the Converted Graphic to Arduino IDE

Open the `.c` file you have downloaded.

Find the line beginning with:

`const unsigned short`

Copy everything from this line right down to the final closing `};` at the end of the file.

Return to the new tab you created in Arduino IDE and paste the copied code into it.

**Make sure you copy the entire section.** Some graphics may contain hundreds or even thousands of lines of data.

### Understanding the Sprite Name

The first line of the pasted code contains the name of the graphic. For example:

```cpp
const unsigned short games_title[76800] PROGMEM={
```

The name `games_title` is the name we will use when displaying the graphic in our program.

If you want to change the name, change `games_title` in this line to your preferred name.

**Important:** The sprite name is not the same as the filename. The filename includes the `.h` extension, but the sprite name does not.

For example:

- Arduino tab (filename): `games_title.h`
- Sprite name in the code: `games_title`

Keep these names consistent throughout your project.

## 5. Include the New Graphic in Sprites.h

Open the `Sprites.h` tab in Arduino IDE.

Add an include statement for the new `.h` file underneath the other graphics that are already included.

For example:

```cpp
#include "snakeHead.h"
#include "games_title.h"
```

**Important:** Make sure the filename, including capital letters, matches the name of your tab exactly.

## 6. Display Your Graphic

You can now display the graphic on the screen using the following command:

```cpp
tft.drawRGBBitmap(x, y, spriteName, width, height);
```

The command uses four parameters:

- **x:** The horizontal position where the graphic will appear.
- **y:** The vertical position where the graphic will appear.
- **spriteName:** The name of the graphic from the first line of your `.h` file.
- **width and height:** The dimensions of the graphic in pixels.

For example, to display the `games_title` graphic across the entire screen:

```cpp
tft.drawRGBBitmap(0, 0, games_title, 320, 240);
```

This will display the graphic starting at the top-left corner of the screen.

### Example: Displaying a Small Sprite

To display a 16 × 16 pixel brick sprite called `bricks1`, use:

```cpp
tft.drawRGBBitmap(10, 30, bricks1, 16, 16);
```

This will display the `bricks1` image:

- 10 pixels from the left edge of the screen.
- 30 pixels from the top of the screen.
- At its original size of 16 × 16 pixels.

You can change the x and y values to position the sprite wherever you need it on the screen.
