
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
