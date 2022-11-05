# Cryptography

Cryptography, or cryptology, is the practice and study of techniques for secure communication in the presence of adversarial behavior. More generally, cryptography is about constructing and analyzing protocols that prevent third parties or the public from reading private messages.

### **Encryption, decryption, and cracking**

One of the earliest encryption techniques is the Caesar Cipher, invented by Julius Caesar more than two thousand years ago to communicate messages to his allies.

The Caesar Cipher is a great introduction to encryption, decryption, and code cracking, thanks to its simplicity.

**Encrypting a message**

Imagine Caesar wants to send this message:

>SECRET MEETING AT THE PALACE

Here's what that might look like encrypted:

>YKIXKZ SKKZOTM GZ ZNK VGRGIK

That looks an awfully lot like gobbledygook at first, but this encrypted message is actually very related to the original text.

The Caesar Cipher is a simple substitution cipher which replaces each original letter with a different letter in the alphabet by shifting the alphabet by a certain amount.

In the previous example it is shifting each letter by 6 letters:

>A	B	C	D	E	F	G	H	I	J	K	L	M	N	O	P	Q	R	S	T	U	V	W	X	Y	Z

>G	H	I	J	K	L	M	N	O	P	Q	R	S	T	U	V	W	X	Y	Z	A	B	C	D	E	F

S shifts 6 letters over to Y, E shifts 6 letters over to K, etc. Here's the first word and its shifts:

>S	E	C	R	E	T

>Y	K	I	X	K	Z

**Decrypting a message**

With Caeser Cipher it is the act of unshifting the letters by the certain amount of letter of the encrypting.

**Cracking the cipher**

There are three main techniques he could use: frequency analysis, known plaintext, and brute force.

1. **Frequency analysis**

    Human languages tend to use some letters more than others. For example, "E" is the most popular letter in the English language. We can analyze the frequency of the characters in the message and identify the most likely "E" and narrow down the possible shift amounts based on that.

2. **Known plaintext**

    Another term for the original unencrypted message is plaintext. If the enemy already knew some part of the plaintext, it will be easier for them to crack the rest of the encrypted version.

    For example, messages tend to start with similar beginnings. In WWII, encrypted German messages always started with a weather forecast, which ultimately made them easier for British mathematician Alan Turing to crack.

3. **Brute force**

    There are only 25 possible shifts (not 26 — why not?). The enemy could take some time to try out each of them and find one that yielded a sensible message. They wouldn't even need to try the shifts on the entire message, just the first word or two.

## Things I want to know more about

- Generating random numbers in computers
- Diffie-Hellman Key Exchange
- Hashing passwords

## References

[1] <https://www.khanacademy.org/computing/computers-and-internet/xcae6f4a7ff015e7d:online-data-security/xcae6f4a7ff015e7d:data-encryption-techniques/a/encryption-decryption-and-code-cracking>

[2] <https://en.wikipedia.org/wiki/Caesar_cipher>

[3] <https://www.youtube.com/watch?v=jhXCTbFnK8o>
