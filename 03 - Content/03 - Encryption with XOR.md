---
creation date: August 15th 2023
last modified date: August 15th 2023
aliases: []
tags: #📖
---

Primary Categories: [[02 - GFACT]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Encryption with XOR]]  

XOR is a crucial concept in encrypting data and one of the most simple forms of encryption/decryption. It is used in many real world implementations, though often as a stage of the process. With XOR you iterate through text using XOR bit by bit to produce the new result, this is the encrypted text. For example in python3:

First we define a function to XOR two strings. We will cover the code much later in the class, just trust it works for now!

```python
def sxor(s1,s2):
  return ''.join(chr(ord(a) ^ ord(b)) for a,b in zip(s1,s2))
```

Now we will use this to populate plaintext, key and then encrypt.

```python
plaintext="Hey how goes?"

key="adhnawdagjswb" # Note the key is equal in length to the plaintext.

ciphertext=sxor(plaintext,key)
```

If we print each of these as binary values:

```python
bin(int.from_bytes(plaintext.encode(),'big'))

bin(int.from_bytes(key.encode(),'big'))

bin(int.from_bytes(ciphertext.encode(),'big'))
```

Producing (in order):

```binary 
0b100100001100101011110010010000001101000011011111
11001000000110011101101111011001010111001100111111
```

```binary
0b110000101100100011010000110111001100001011101110
11001000110000101100111011010100111001101110111011
00010
```

```binary
0b0101001000000010001000101001110000010010001 10000001001101000001000000000000010100010110000001
0001011101
```

If you take the very first values after the 0b (denoting binary) they are 1 from plaintext and 1 from the key. XOR 1 and 1 produces a 0 as the values are identical, so as expected the third sequence shows a 1 straight after the 0b. Continue down the sequence and you will find they are simply XOR transformations.

**Note:** If you try running the Python above the ciphertext may give you 

```
0b1010010000000100010001010011100000100100011000 
00010011010000010000000000000101000101100000010001011101
```

instead. This is actually one bit shorter than it should be because a preceding `0` is optional in Python and not displayed. If you didn't try it yourself don't worry about it for now.

The resulting data?

```python
>>> ciphertext 
')\x01\x11N\t\x18\x13A\x00\x05\x16\x04]'
```

That data looks pretty darn unreadable, and it is!

You can XOR plaintext with the key and you get the ciphertext. This is encryption. You can XOR the ciphertext with the key and get the plaintext. This is decryption. You can XOR the plaintext with the ciphertext and get the key, which might be re-used elsewhere and enable further decryption. This is key recovery.



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: August 15th 2023 (09:15 pm) 
Last Modified Date: August 15th 2023 (09:15 pm)
