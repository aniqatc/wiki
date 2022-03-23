## [🪴 View In My Digital Garden: Character-Encoding: ASCII and Unicode](https://www.aniqa.io/wiki/web/character-encoding)

Understanding the importance of ASCII and Unicode character-encoding methodologies, as well as, the key differences between UTF Character Sets.

---

> What is a **Compiler**? Program responsible for translating computer code that has been written in one programming language into a different kind of language (from source language to target language)

## ASCII Code
**ASCII or US-ASCII = American Standard Code for Information Interchange**: a method of character encoding used for computerized, electronic communications

> Internet Assigned Numbers Authority (IANA) is a not-for-profit organization that looks over the allocation of IP addresses, management of the Domain Name System (DNS), and other TCP/IP related work.

- **IANA** prefers the name `US-ASCII` for the ASCII character encoding.

**ASCII Primary Goal**: to provide a common language across all computers *around the world*

Most common character-encoding rooted in ASCII = **UTF-8 & ISO-8859-1**

English alphabet, numbers, common symbols are encoded in **ASCII**'s table of characters. These characters are stored as [binary bits [1s and 0s]](/wiki/web/binary). For e.g. `01000001` = Letter `A`

---

**Basic ASCII: 128 slots in an 7-bit code** with 95 including alphabet, lower & uppercase, digits 0-9, punctuation

**Extended ASCII: 256 slots in an 8-bit code** = 8-bit is an early software program with ability to transfer 8 bits of data simultaneously. *(For reference = nowadays, computer processors run on 64-bit architecture)*

Extended ASCII table includes *(links may include [hex-values](/wiki/web/hexadecimal))*:
- [**Non-Printable**](https://web.itu.edu.tr/sgunduz/courses/mikroisl/ascii.html) = system codes between `0` and `31`
     - **Control Characters** used for commands: [space], [line break], [end-transmission], [acknowledge], [cancel], [substitute], and [**more**](https://flaviocopes.com/non-printable-ascii-characters/)
- [**Lower ASCII**](https://flaviocopes.com/printable-ascii-characters/) = system codes between `32` and `127` (standard characters for english speakers)
- **Higher ASCII** = programmable system codes between `128` and `255` - *custom portion*

### Issues with ASCII 
For Higher ASCII codes between `128` and `255` that are meant to be **programmable**, different entities came up with their *own character sets*:
- IBM-PC had their own character set *(OEM character set)* that allowed for **accented characters to fit European languages** and other symbols. 
- Computers in **different countries would create their own character sets as well to fit their language needs**. 

*The **issue** with the higher ASCII characters being so vastly different between regions and computer types*: when information would be shared, there would be issues understanding certain words because the accented letters wouldn't show up accented in some places, it **could show up as a different character depending on the character set in the receiving computer**. 
* For example, *PCs in America* could have their character code `158` as `ñ` but someone in *Russia* might have their `158` character set as `Ю`. (So, if I send my character code `158` to someone in Russia, they won't receive `ñ`, they'll receive their `Ю` and it would be placed out of context).

> Character codes below 128 were known as the **standard** for all computers but everything beyond that was basically **custom** based on region or different PC types. 

#### ASCII was used until 2007 - UTF-8 took over:
## Unicode
#### Unicode = Universal

**Expanded ASCII** original 128 characters and built up on it using characters and symbols in English AND other languages **across the globe**.

[**As of 2020, Unicode has 143,859 characters and is still growing!**](https://home.unicode.org/) There is no limit to how many characters can be added to the Unicode system. They assign [hexadecimals](/wiki/web/hexadecimal) to each **code point**.

- **Code Point** = `U+1F643`: the `U+` **represents "unicode" and the numbers after represent a [hexadecimal](/wiki/web/hexadecimal)**

Every letter in every alphabet, including upper-case and lower-case, numbers, symbols, and more recently, [emojis](https://unicode.org/emoji/charts/full-emoji-list.html) are assigned to a **Unicode number (a code point)**.

Unicode was created in order to provide a **universal character set to work across the globe**. 

*Several* `U+HEX#` *code points can be used to write out words and full sentences; using a [unicode character search tool](https://unicode-table.com/), here's an example:*

```:title=Aniqa
A = U+0041
n = U+006E
i = U+0069
q = U+0071
a = U+0061
```

**Unicode standards are implemented by UTF-8, UTF-16, UTF-32**. The main difference: how many [bytes](/wiki/web/binary) it requires to represent a character in memory

### UTF-8 [Default Choice]

<div class="table">

| UTF-8 |
| ----  |
| Backward-compatible with ASCII Character-Encoding |
| Backtrack and can match with ASCII |
| Provides over 65,000 code points |
| Known as standard for websites |
| Large library of scripts without overloading programs with unnecessary rendering |
| Flexibility to handle large-byte transfer scenarios |
| Quick enough to handle single [bytes](/wiki/web/binary) |
| Not overwhelmed with unnecessary byte weight |
| 8-bit / 1 byte = each character |

</div>


- Every code point between 0-127 is stored = **1 byte**
- Code points above 128 are stored = **2 to 6 bytes**

### UTF-16

> ISO 10646 defined encoding form that ran on **32-bits called UCS-4**

- *The code points started at* `0` to `0x7FFFFFFF`
- **UTF-18**: the limited version of **UCS-4**

| UTF-16 |
| -----  |
| Character-mapping did **not** match ASCII |
| **Not** backward-compatible with ASCII |
| Cannot process ASCII encodings |
| Slower render time |
| More characters |
| Less efficiency |
| 16-bit / 2 bytes = each character |

Designed as variable-width encoding: codes of differing length to encode a character set (using multi-byte encoding, varying number of [bytes](/wiki/web/binary), octets)

### UTF-32

**Similar to UTF-16**: takes more time to transfer 32-bits + more space to store it
- Each character is composed of 4 bytes (32-bits) 
- Fixed-width code for every character

---

## HTML: Define Character Set

The following tag is inserted within the `<head>` of an HTML document **to specify which character encoding the website will support**:

```html:title=Character-Encoding
<meta charset="utf-8">
```

- `<meta>` = an *HTML tag* that contains **metadata** about the website *(the attribute that follows it will describe what particular piece of data is being defined)*
- `<charset>` = an *HTML attribute* that is used to define the *character encoding that the browser will use* to display website text, symbols, numbers and other applicable content 
- `utf-8` = the specific character encoding *(like a language of its own)*

**Note**: It's important to identify the necessary character encoding so that **browsers can understand how to interpret the content and how to display it**, otherwise, there might be issues rendering it *(for e.g. different languages have different writing systems of their own, or symbols of their own)*.

## Evolution of Web Character Encoding
1. ASCII
2. ISO-8859-1: Default in HTML4
3. ANSI
4. **UTF-8: Default in HTML5**

HTML5 specification encourages the use of **UTF-8 as the standard character-encoding** as it *covers almost all the characters and symbols that are used in modern-day websites*.

In HTML5, **UTF-8 is the default character-encoding**, so it doesn't need to be declared, as long as the `<!DOCTYPE HTML>` **is included at the start of the HTML file**.
- *Still good practice to use* `<meta charset="utf-8">` *in your HTML documents to allow **support for older browsers that may not have adopted HTML5 as a default** yet.*
