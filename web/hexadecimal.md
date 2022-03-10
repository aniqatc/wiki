## [🪴 View in the Comfort of My Digital Garden: Language of Computers: Hexadecimal](https://www.aniqa.io/wiki/web/hexadecimal)

The basics to understanding the hexadecimal system and its many uses in computer programming.

---

Computers find it easier to convert [binary](/wiki/web/binary) numbers to hexadecimal numbers and vice versa.

In the **hexadecimal system**, **each digit represents a power of 16**. Therefore, the hexadecimal system is a **base-16 system** with 16 digits; *whereas the decimal system is a **base-10 system** with only 10 digits*.

Hexadecimal Digits include 16 digits that represent the decimal equivalent of 0 through 15:
- The first 10 digits: 0 - 9 digits are used as is (`0, 1, 2, 3, 4, 5, 6, 7, 8, 9`)
- The remaining 6 digits: 10-15 are not used, instead the letters A-F represent 10-15 (`A, B, C, D, E, F`)

+ **1 individual hexadecimal digit = 4-bit [binary sequence](/wiki/web/binary)**

### Hexadecimal vs. [Decimal vs. Binary](/wiki/web/binary)
<br/>
<center>
<div class="table" style="width:450px;" id="hex-table">

| Decimal | Hex  | Binary  |
| :----: | :---: | :---:   |
| 0      | 0     | 0000    |
| 1      | 1     | 0001    |
| 2      | 2     | 0010    |
| 3      | 3     | 0011    |
| 4      | 4     | 0100    |
| 5      | 5     | 0101    |
| 6      | 6     | 0110    |
| 7      | 7     | 0111    |
| 8      | 8     | 1000    |
| 9      | 9     | 1001    |
| 10     | A     | 1010    |
| 11     | B     | 1011    |
| 12     | C     | 1100    |
| 13     | D     | 1101    |
| 14     | E     | 1110    |
| 15     | F     | 1111    |

</div>
<br/>
</center>

### Convert Hex to Decimal

Example: `0xC0DE`

- The prefix `0x` means the code is a hexadecimal value
- Identify the hex values which include anything after the prefix: `C0DE`
- Identify the digit positions: 
    - `C = 3`, `0 = 2`, `D = 1`, `E = 0`
- Convert the individual hex values to its decimal equivalent:
    - `C = 12`, `0 = 0`, `D = 13`, `E = 14`
- Multiply the decimal values to 16 with an exponent number that represents the digit places:
   - C = `12 x 16^3 = 49,152`
   - 0 = `0 x 16^2 = 0`
   - D = `13 x 16^1 = 208`
   - E = `14 x 16^0 = 14`
- The sum of all of the products = decimal equivalent of hexadecimal code, `49374`


### Hex Identifiers

Hexadecimal values are used in a variety of different ways ranging from color codes to individual character codes and more. To identify if a code represents a hexadecimal value and its specific use-case, there are **hex identifiers** that *usually* prefix a hex-value:
<center>
<div class="table">


| Prefix | Example | Meaning |
| :---:  | :---:   | :----:  |
|   0x   | `0x6400`  | Used in UNIX & C-Based Programming Languages | 
|   #    | `#F7FF7F` | [Color reference codes](/wiki/web/color-models) |
|   %    | 	`%3A` | <a href="https://www.obkb.com/dcljr/chars.html" target="_blank">Character code that represents all standard keyboard character</a> |
|  \x    |  `\x1B` | <a href="https://www.eso.org/~ndelmott/ascii.html" target="_blank">Represents character codes used for keyboard control</a> |
| &#x    | `&#x3A9` | <a href="https://www.toptal.com/designers/htmlarrows/symbols/" target="_blank">Code for unicode characters in HTML, XML & XHTML</a>  |
| 0h     | `0h5E`    | Prefix used by programmable graphic calculators |
| $      | `$6AD`    | Used in assembly languages |
| U+     | `U+0061`  | [Unicode character code](/wiki/web/character-encoding) points use hexadecimals |
|  -- | -- | [ASCII Equivalents](https://flaviocopes.com/printable-ascii-characters/) |

</div>
</center>


---

#### [Color Models Including Hex Color Values](/wiki/web/color-models)
#### [Unicode (Utilizes Hexadecimal-System) & ASCII](/wiki/web/character-encoding)


