## [🪴 View in the Comfort of My Digital Garden: Language of Computers: Binary - Color Models](https://www.aniqa.io/wiki/web/color-models)

The basics to understanding how different color models represent millions of different colors with varying degrees of saturation and brightness.

---

### [Hexadecimal](/wiki/web/hexadecimal) Color Codes

The [hexadecimal system](/wiki/web/hexadecimal) is used to represent over 16 million colors using a 6-digit, 24-[bit](/wiki/web/binary) hexadecimal format that represents **Red**, **Green** and **Blue** with a `#` prefix (`#123456`). 

Each character of the 6-digit hexadecimal code has a specific value (with lowest intensity at `00` and highest intensity at `FF`).

For Hex-Value `#123456`:
- First two digits `12` represent the intensity of **Red** 
    - `#FF0000` has only red
- Middle two digits `34` represent the intensity of **Green**
    - `#00FF00` has only green
- Last two digits `56` represent the intensity of **Blue**
    - `#0000FF` has only blue


<i><code>#FFFFFF</code> represents white & highest intensity of color, whereas, <code>#000000</code> represents black & lowest intensity of color.</i>


###  HTML & RGB

- HTML supports the use of [**140 Color Names**](https://www.w3schools.com/tags/ref_colornames.asp)
    - `tomato`
    - `green`
    - `crimson`
    - `plum`
    - `red`


- **RGB (Red, Green, Blue)** color values use three numbers that represent a number between `0` to `255` for each primary color. The value represents the intensity for each individual color (with lowest intensity at `0` and highest intensity at `255`).
    - `rgb(255,255,255)` = White
    - `rgb(255,0,0)` = Red
    - `rgb(0,255,0)` = Green
    - `rgb(0,0,255)` = Blue
    - `rgb(114, 245, 66)` = Lime Green

### HSL & HSV

While RGB and Hex color code formats are known to be machine-friendly, HSL and HSV are more human-friendly.

For both HSL and HSV color models, (1) **Hue** defines the first letter of both acronyms and (2) **Saturation** represents the second letter of both acronyms. *Whereas, the L is Lightness and the V is Value.*


**Hue is pure color** portion of the model, identified by a number between 0 to 360 degrees:
<center>
<div class="table" style="width:300px;max-width:100%;">

| Color | Degree |
| :---: | :---: |
| Red | 0-60 |
| Yellow | 61-120 |
|  Green | 121-180 |
| Cyan | 181-240 | 
|  Blue | 241-300 |
| Magenta | 301-360 | 

</div>
</center>

**Saturation describes whether a color leans more grayscale or more vibrant and full color**, identified by a percentage between 0 and 100 percent:
- `0%` = Greyscale and Faded
- `100%` = Full Color and Vibrant

**Lightness describes how light or dark a color is**, identified by a number between 0 and 100 percent:
- `0%` = Dark / Black *(Color with Least Light)*
- `100%` = Light / White *(Color with Most Light)*

**Value or Brightness describes the intensity or brightness of a color**, identified by a number between 0 and 100 percent:
- `0%` = Dark (completely black)
- `100%` = Brightest (reveals the most color)

---

#### HSL
HSL (Hue, Saturation, Lightness) color values provide a human-friendly format of defining colors.
- `hsl(136°, 0%, 0%)` = Black
- `hsl(0°, 100%, 50%)` = Pure Red
- `hsl(145, 25%, 50%)` = Muted green
- `hsl(244°, 89%, 72%)` = Blue-Leaning Lavender

#### HSV
**HSV** (Hue, Saturation, Value) color model is similar to **HSL** but replaces *Lightness* for **Value** instead. 
- `hsv(136°, 0%, 0%)` = Black
- `hsv(0°, 100%, 100%)` = Pure Red
- `hsv(145°, 40%, 62%)` = Muted Green
- `hsv(244°, 51%, 97%)` = Blue-Leaning Lavender

### CMYK

- **CMYK (Cyan, Magenta, Yellow, Key-Black)** is a four-color system that is primarily used for print materials (in contrast to computer screens that usually display colors using RGB). Each of the four values are percentages between `0%` and `100%` and represent `[C]` Cyan, `[M]` Magenta, `[Y]` Yellow, and `[K]` Key-Black in order.
    - `cmyk(0%, 0%, 0%, 100%)` = Pure Black = *black value is used*
    - `cmyk(50%, 10%, 75%, 50%)` = Dark Green = *all colors values used*
    - `cmyk(0%, 100%, 100%, 0%)` = Pure Red = *magenta, yellow used*

---
