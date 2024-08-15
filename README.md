
## Hex to base 64 
```
import base64
#hex strings
s = "49276d206b696c6c696e6720796f757220627261696e206c696b65206120706f69736f6e6f7573206d757368726f6f6d"

# convert hex to bytes and then to base64
bas64 = base64.b64encode(bytes.fromhex(s)).decode()

#convert base64 to bytes and then to hex
s2 = base64.b64decode(bas64.encode()).hex()
# .encode() function pass to b64encode() to convert the string into bytes form and bytes.hex() function convert it to base64

print (bas64}
print(s2)
```

## Basic RSA
> example from [DeconstruCTF 2021 solved by cl2y7on1c](https://c12yptonic.github.io/ctf-writeups/ctfs/deconstructf21#rsa-1-)
```
from Crypto.Util.number import long_to_bytes

n = 23519325203263800569051788832344215043304346715918641803 # public modulus create by p*q
e = 71                                                       # public encryption exponent used to encrypt a plaintext message
c = 10400286653072418349777706076384847966640064725838262071 # encrypted message c = pow(m, e, N)

# find in the http://www.factordb.com
p = 4655885807254867892895911581
q = 5051525354555657585960616263

#calculate Euler's totient function
phi_n = (p-1)*(q-1)

# calculate private key,d (inverse mod)
d = pow(e, -1, phi_n)

#Decryption
m = pow(c,d,n)

print (long_to_bytes(m).decode())
```

