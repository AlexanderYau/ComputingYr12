# AQA CS AS Notes

## 3.5 Fundamentals of data representation

### 3.5.1 Number systems
<img src="http://scimathmn.org/stemtc/sites/default/files/images/frameworks/math/8.1.1A/image131.jpg"></img>

+ natural numbers

**definition**: those are numbers used for counting (non-negative numbers).

**examples**: 0,1,2,3,4
``` 
Counting uses natural number
A set of natural number can expressed as:
N={0,1,2,3...}
```

+ integer numbers

**definition**: those are whole numbers.

**examples**: -2,-1,0,1,2
```
Fractions, surds and pi are not integers.
```

+ rational numbers

**definition**: those are numbers that can be expressed as a fraction (this includes integers as they can be written as n/n)

**examples**: 2/3, 19/328, 2/2
```
Surds, pi and imaginary/complex numbers are not rational numbers
```

+ irrational numbers

**definition**: numbers which can't be expressed as a fraction

**examples**: pi and surds

+ real numbers

**definition**: numbers which are not imaginary or complex (not the root of a negative number).

**examples**: pi, 2/3, surds, 3

+ ordinal numbers

**definition**: numbers used for positioning

**examples**: 1st, 2nd, 3rd

### 3.5.2 Number bases
+ base 2: those are binary numbers. example: 1010<sub>2</sub>. See [this site](https://bournetocode.com/projects/AQA_AS_Theory/pages/3-5.html) for more infomation
+ base 10: these are denary numbers. example: 14<sub>10</sub>.
+ base 16 these are hexidecimal numbers. example: 3F and DA.
+ conversion between denary, binary and hex

**Denary to Binary**
```
List the powers of 2 then subtract the highest power of 2 possible from your denary number and write a "1" under the power of 2, repeat until you are left with "0".

e.g.
102 to Binary
102-64=38
38-32=6
6-4=2
2-2=0
128|64|32|16|8|4|2|1
0	1  1  0  0 1 1 0
```
**Denary to Hexidecimal**
```
Convert the denary to binary then split the binary into nibbles then convert each nibble into Hexidecimal

e.g.
102 = 01100110
0110 0110
8|4|2|1
0 1 1 0

0110=6

Since both nibbles are the same

102 in denary = 66 in hex
```

### 3.5.3 Units of information
+ bit and bytes
A bit is a single digit in base 2
A byte is 8 bits
+ units of kilo, kilbi etc
A kilobyte is 1000 bits (10^3)
A kibibyte is 1024 bits (2^10)
A megabyte is 1,000,000 bits (10^6)
A mebibyte is 1,048,576 bits (2^20) 

The naming format of units of kilbi are the first 2 letters of the equivalent in kilo then "bibyte" added onto the end e.g. gibibyte is the equivalent of gigibyte

### 3.5.4 Binary number system

#### unsigned binary
Unsigned binary is binary without a negative or positive symbol assigned to it. It can have a maximum value of 255 with 8 bits and can hold 256 unique values.
#### unsigned binary arithmetics
To add two bytes of unsigned binary together, whenever you have two 1's in the same column carry a 1 and set the bit in that column to be 0:
 10010101
+01011011
---------
 11110000
---------
   11111 
#### signed binary with two's complement
Signed binary uses one of it's bits to represent a negative or positive symbol.
With 8 bits it can have a maximum value of 127 and can have 128 unique numbers (not including negatives)
#### fixed point form binary representation of numbers with fractional parts

### 3.5.5 Information encoding system

#### Character form of a decimal digit
```
When writing a number in Unicode or ASCII: such as "6" in ASCII, which is 54 in denary or 0110110 (ASCII is 7 bits), it doesn't have a value of 6 since that symbol is just an image and doesn't hold the value of 6 but instead 0110110 so when you add "6" and "6" in ASCII together you don't get 12 but instead you get 66.
```

#### ASCII and Unicode
```
ASCII is made up of 7 bits and can hold 128 English characters, Extended ASCII is made up of 8 bits and can hold 256 characters which includes "control characters" such as "£" and "%".

Unicode has 3 forms: UTF8, UTF16 and UTF32 (Unicode text file and the numbers stand for the number of bits). UTF8 can hold all english characters, UTF16 can hold all latin characters and UTF32 can hold all characters including those from the Chinese and Japanese languages.
```
#### Error checking and correction
There are 4 main types of error checking and correcting:
+ Parity bits
```
This is the simplest way to check for any errors that occurred while transmitting data. When transmitting 8 bits of data the 1st bit (the MSB-most significant bit) is used to check if there were any errors while the other 7 is the actual data that is being checked for errors.
The way parity bits work is it checks the number of "1"s in the data and if there is an even amount it sets the parity bit/MIB as 0 and if there are an odd amount it changes the MIB to 1 to make the number of "1"s even.
The receiver does some parity checking and if the parity bit is the same at the sending end as it is at the receiving end then the data is classified as correct, if the parity bits are different an error was deemed to have occurred and the sent data is ignored and resent.

The problem with parity bits is that if instead of just 1 bit changing during transmission and causing the data to be wrong, if 2 bits got changed then the parity bit would be the same on the sending end as on the receiving end despite the data being different e.g. 01101111 could have changed to 01000111 and using parity bits the the data would have been deemed as correct without errors.
```
+ Majority voting
```
In majority voting each bit of data is sent 3 times and the bit that is sent the majority of the 3 times is deemed as the correct bit e.g. 01100111 could have been sent as 010 111 011 100 000 101 111 011 and this would have meant that the entire byte was correctly sent since the majority of each 3 sends is the correct bit in each case however if it was sent as 011 in the first bit instead of 010 then the bit would have been sent as a 1 instead of a 0 meaning that the data received would have been incorrect.
``` 
+ Checksums
```
The way that checksums works is that a mathmatical algorithm is applied to the data producing a checksum value which is sent along with the data and the mathmatical algorthm is repeated at the receiver and if the 2 checksums values are equivalent then no error is deemed to have occurred and if they aren't the data is ignored and resent.
One example of a checksum algorithm is:
Your data: 01100011
1.Split the byte into nibbles: 0110 0011
2.Find the value of each nibble in denary: 6, 3
3.Add the value of each nibble together: 6+3 = 9
```
+ Checkdigit

### 3.5.6 Representing images, sound and other data

#### Bit patterns, images,  sound  and other  data
#### Analogue and digital
#### Analogue and digital conversion
#### Bitmapped graphics
#### Digital representation of sound
#### Musical Instrument Digital Interface (MIDI)
#### Data compression
#### Encryption
