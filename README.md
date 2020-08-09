# C5
C5 is short for Counter Conventional Caesar Cipher Contraption

**Full Disclosure :** 

C5 is **not** intended for any commercial or serious security purposes. It is loosely based on the Vigenère Cipher and the Caesar Cipher, and remains, a shift cipher at its core. It's intended for making puzzle-ciphers and for the purposes of throwing off casual snooping. A challenge to break C5 is posted [here](https://puzzling.stackexchange.com/questions/100920/can-you-crack-this-multiple-shift-cipher) , and while not yet cracked, it is only a matter of time. It is not immune to being treated as multiple caesar ciphers, where it may be broken by frequency analysis, as long as the message is long enough. 

**Algorithm/Steps:**

C5 cipher involves maximum 8 different shifts applied mostly unevenly across the message, resulting in ciphertext that is not easy to casually crack.
It is not necessary that all 8 shifts are used, nor that 8 shifts have unique values, nor even that all 8 shifts have non-zero values -- all this depends on the pin and the length of the message.

Hence, a number can be ecnrypted as itself, and the ciphertext can prima facie be very random looking in most cases.

- Encryption :

1. Pin is taken. Pin has 8 digits. These digits are stored individually in an array.These digits are used as the 8 possible shifts.
2. A Message is taken from the user, stored into a char array msg[]
4. Each character in msg[] is changed depending on its position value. The position number is matched with 6 mathematical number series. Depending on which it matches with, a digit from the pin is used as a shift on that char. If it is a part of none of these series, the position value is checked for being odd or even. The shifted value is stored as an int.(ASCII value of char x is used for the shift operations)
5. Each int is stored in an int array en[]. Then, all these ints are printed in hex , with a space separating these , and the last number is always -de  (hex for -222)
- Decryption :

1. Pin is taken and digits are stored to array. 
2. Ciphertext is taken from user.
3. Every entered int d is stored as int d and the same rules as in encrypt are applied and reversed according to the entered pin and stored to char array msg[].
4. Char array msg[] is printed, and if pin was correct, it makes sense and is the same as the original message. 

- **Example :**

Message = "hello"

PIN = "12345678"

Ciphertext =  63 68 6f 67 70 -de 
