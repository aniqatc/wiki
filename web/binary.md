## [🪴 View In My Digital Garden: Language of Computers: Binary - Bits & Bytes](https://www.aniqa.io/wiki/web/binary)

Understanding what the binary system is and how bits and bytes allow computers to interpret all types of written and visual data.

---

*Computers do not understand our human languages or images or sounds the way we do. Instead computers work off electrical signals. These **electrical signals follow binary data**; binary data is processed by computers because it is simple and can be interpreted through electrical signals that go **on** or **off**.*

**Everything that we see, and even hear, can be broken into binary data**, whether it's [individual letters in the alphabet](/wiki/web/character-encoding) or high-resolution photos or animated gifs or videos with sound or [colors](/wiki/web/color-models).

## Decimal System
For reference: **decimal** system uses digits between 0 - 9. Each position of number is assigned a **place value**. For example, the number **`646,108,004.4652`** includes the following place values:

<center>
<div class="table" style="width:320px;">


| Place Value | Number |
| :----:      | :---:  |
| Hundred-Millions | 6 | 
| Ten-Millions     | 4 | 
| Millions         | 6 |
| Hundred-Thousands| 1 | 
| Ten-Thousands    | 0 | 
| Thousands        | 8 | 
| Hundreds         | 0 | 
| Tens             | 0 |
| Ones             | 4 | 
| **.**            | . | 
| Tenths           | 4 | 
| Hundredths       | 6 | 
| Thousands        | 5 | 
| Ten-Thousandths  | 2 | 


</div>
</center>

## Binary System: Bits
**Binary system** is made up of only two numbers: **0** and **1**

- The two numbers (**0** and **1**) are known as a **bit** = *the smallest & most basic unit of data that a computer can store, process, input and output*
- Using only 1s and 0s, you can count up to any number
- A single _bit_ can represent **two** different values
    - `ON` or `OFF`
    - `YES` or `NO`
    - `TRUE` or `FALSE`
    - `ENABLE` or `DISABLE`
    - `AM` or `PM`

<small>Note: Anything can be represented with two-values; for e.g. a wire can hold electrical signals that represent <code>[on]</code> and <code>[off]</code> which would be enough for it to operate - it would be known as a <b>1-bit wire</b>.</small>

Physical storage of **bits**: computers use electromechanical transistors which can map electrical signals to either `0` or `1` bit state

## Binary System: Bytes
- **8 bits** [of 0s and 1s] = **1 byte**
- **1 byte** ➜ can have 256 different values between 0 to 255
- 1 byte [can hold about 1 character (alphabetic, numeric or symbol)](/wiki/web/character-encoding)
- A single byte of information looks like: **10101001**
- A single [hexadecimal digit](/wiki/web/hexadecimal) represents a [4-bit binary sequence](/wiki/web/hexadecimal#hex-table)


 ##### Storage Measurements in Bytes

<center>
<div class="table" style="width:450px;">

| Size | Value  | Abbrev. |
| :----: | :---: | :---:   |
| 1 bit   | 0 or 1  | `(b)`   |
| 8 bits  | 1 byte   |  `(B)`   |
| 1 thousand bytes  | kilobyte | `(KB)` |
| 1 million bytes  | megabyte  | `(MB)` |
| 1 billion bytes | gigabyte  | `(GB)`  |
| 1 trillion bytes  | terabyte | `(TB)`  |

</div>
</center>

##### Patterns
Equation = `n` number of bits is used  exponent to `2^n` *(2 to the nth power)*

<center>
<div class="table" style="width:600px;">

| Bit/Byte | Patterns  | Example |
| :----: | :---: | :---:   |
| 1 bit | 2  | (`0`, `1`) |
| 2 bits | 4  | (`00`, `01`, `11`, `10`) |
| 3 bits | 8  | (`010`, `100`, `110`, etc) |
| 4 bits | 16  | (`0001`, `0011`, `0111`, etc) |
| 5 bits | 32 | (`00001`, `00011`, etc) |
| 6 bits | 64 | (`000111`, `111000`, etc) |
| 7 bits | 128 | (`1110001`, `0001110`, etc) |
| 8 bits/1 byte | 256  | (`11001100`, etc) |

</div>
</center>

##### Sequences
- 2-bit Sequence - `2 x 2` = 0-4 distinct values (`00`, `01`, `11`, `10`)
- 3-bit Sequence - `2 x 2 x 2` = 0-8 distinct values (`000`, `001`, `010`, `011`, `111`, `110`, `100`, `101`)


##### Unique Patterns
- If byte ends in 1 *(in the ones place)* ➜ decimal number will be **odd**
- If bit(s) equal 1 in every value place ➜ decimal number can be found using the following equation: `2 ^ (# of bits) - 1`

<center>
<div style="width:200px;">

| Binary | Decimal   | 
| :----: | :----: | 
| 1 | 1 |
| 11 | 3 |
| 111 | 7 |
| 1111 | 15 |
| 11111 | 31 |

</div>
</center>


#### Why 8 Bits Equal A Byte?
Modern computers smallest addressable unit of memory is a **byte**; *byte-addressable memory cannot store individual pieces of data that are smaller than a byte*.

A **byte sequence** can represent simple to complex data; from a pixel to alphabetic character, an instruction, or a sound waveform. 

**Context is important** = the byte ` 1000011` *could be* the letter `C` or the number `67`


### Graphics & Sound Using Bits & Bytes
- [Letters = Assigned Numbers](https://www.phys.uconn.edu/~rozman/Courses/P2200_14F/downloads/ascii.pdf)
- Photos/Graphics = Made up of thousands of individual pixel colors that each have a [specific color value](/wiki/web/color-models) which can be translated to binary; more specifically, [color codes](/wiki/web/color-models) are usually represented by a **[hexadecimal value](/wiki/web/hexadecimal)** that is easily converted to binary
- Sounds = made up of vibrations represented graphically through waveforms *(every point on the waveform can be represented by a number which can be translated to binary)*
    - *Why 32-bit audio > 8-bit audio? More bits means more range of numbers meaning higher quality sound*
