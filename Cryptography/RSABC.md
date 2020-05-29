# RSABC

## SOAL
![rsabcc](https://user-images.githubusercontent.com/26424136/82997703-ec351e80-a030-11ea-9a2f-45f5d0a21cbf.PNG)
![rsabccc](https://user-images.githubusercontent.com/26424136/83002151-e6423c00-a036-11ea-958e-9c77c94cb085.PNG)

____________________________________
## Penyelesaian
Disini saya mencari flag menggunakan OS ubuntu dan Bahasa ruby
- Membuat file bernama solve.rb yang berisi source code RSA dengan perintah `nano solve.rb`
![rsabc](https://user-images.githubusercontent.com/26424136/82997747-fce59480-a030-11ea-807a-baeebdd07248.PNG)
- `Nilai p dan q` diambil dari faktorisasi `nilai n`, disini saya memfaktorkan menggunakan [factordb](http://factordb.com/)<br /> 
![rsabc 3](https://user-images.githubusercontent.com/26424136/83001087-7089a080-a035-11ea-95bf-3caacc000c1d.PNG)
- Berikut source code RSA pada <b>solve.rb</b>
  ```
#!/usr/bin/env ruby
require 'openssl'

# From challenge
n = 57772961349879658023983283615621490728299498090674385733830087914838280699121
e = 65537
c = 36913885366666102438288732953977798352561146298725524881805840497762448828130

# Factorised by factordb.com
p = 202049603951664548551555274464815496697
q = 285934543893985722871321330457714807993

raise "wrong factors" unless p*q == n

# Helper methods
"""
def extended_gcd(a, b)
  last_remainder, remainder = a.abs, b.abs
  x, last_x, y, last_y = 0, 1, 1, 0
  while remainder != 0
    last_remainder, (quotient, remainder) = remainder, last_remainder.divmod(remainder)
    x, last_x = last_x - quotient*x, x
    y, last_y = last_y - quotient*y, y
  end
 
  return last_remainder, last_x * (a < 0 ? -1 : 1)
end
 
def invmod(e, et)
  g, x = extended_gcd(e, et)
  if g != 1
    raise 'The maths are broken!'
  end
  x % et
end
"""

def invmod(e, et)
  e.to_bn.mod_inverse(et)
end

def powmod(x, e, n)
  x.to_bn.mod_exp(e, n)
end

def hex2ascii(text)
  [text].pack('H*')
end

# Decrypt
phi = (p-1)*(q-1)
d = invmod(e,phi)

plaintext = powmod(c, d, n)
plaintext = plaintext.to_s(16)
plaintext = hex2ascii(plaintext)
puts plaintext
  ```
- Jalankan program tersebut dengan perintah `ruby solve.py`
![rsabc 2](https://user-images.githubusercontent.com/26424136/82997745-fbb46780-a030-11ea-8131-7cf01bf4cb7b.PNG)
- Flag telah ditemukan <br />
____________________________________
## Flag

Flag: <b>tjctf{BOLm1QMWi3c}</b>
