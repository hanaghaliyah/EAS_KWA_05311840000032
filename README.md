# EAS_KWA_05311840000032
[TJCTF 2020](http://tjctf.org/)<br />
Nama : Hana Ghaliyah Azhar <br />
NRP  : 05311840000032

## Table of Contents
- Miscellaneous
- Web
- Cryptography
- Reversing
- Forensics

## A First Step
![A first step](https://user-images.githubusercontent.com/26424136/82996609-6a90c100-a02f-11ea-8c3c-8759698a0ac3.PNG)

## Discord
![Discord](https://user-images.githubusercontent.com/26424136/82996615-6c5a8480-a02f-11ea-8bdf-2505f652e7ea.PNG)

## Broken Button
![Broken Button](https://user-images.githubusercontent.com/26424136/82996612-6bc1ee00-a02f-11ea-9c3f-954ca915c976.PNG)

#### Penyelesaian
Pada web tersebut dapat dilihat ada button yang tidak bisa diklik. Untuk mendapatkan flagnya yaitu klik F12 atau ke inspect element. Pada <body> tag terdapat button yang mengarah ke "find_the_flag!.html". Kemudian salin link tersebut ke url diatas sehingga hasilnya adalah "https://broken_button.tjctf.org/find_the_flag!.html" Dan flag ditemukan.
Flag: <b>tjctf{wHa1_A_Gr8_1nsp3ct0r!}</b>


## Circles
![circles](https://user-images.githubusercontent.com/26424136/83008699-c9f6cd00-a03f-11ea-9560-830c53fb5e56.PNG)
Tampilan gambar [Circles.png](https://static.tjctf.org/f5e809c4c49f2c7d607d77c99f07bbd8e9b46dfbe61779201f5b185ed6642de3_Circles.png)
![Circlesflag](https://user-images.githubusercontent.com/26424136/83008707-ce22ea80-a03f-11ea-88db-9e01dacf3a1f.png)

#### Penyelesaian
# Circles

**Soal**

Some typefaces are mysterious, like this one - its origins are an enigma wrapped within a riddle, indeed. 

[circles.png](link gambar)

____________________________________

**Penyelesaian**

Di dalam gambar tesebut, tedapat sebuah simbol yang merupakan petunjuk untuk menemukan flag tersebut. Apabila dilihat dari polanya, simbol tersebut akan berisi tjctf{_isi dari flag_}. Jika dilihat dari motif simbol, terlihat bahwa simbol tersebut berupa sebuah _font_. Untuk mengetahui font tersebut kita dapat menggunakan sebuah tool brtupa _font identifier_

Setelah kita telah menemukan _font_ apa yang digunakan untuk menulis kalimat tersebut, kita dapat mencari arti dari simbol terebut berdasarkan _font_ yang telah ditemukan

____________________________________

**Flag**

flag = tjctf{B3auT1ful_f0Nt}



## Login Sequel
![Login sequel](https://user-images.githubusercontent.com/26424136/83002844-bb0c1c80-a037-11ea-972d-124236c9f3ef.PNG)
Tampilan Halaman Login
![login sequel 1](https://user-images.githubusercontent.com/26424136/82976688-f09a1100-a009-11ea-8ce7-222763d7b14c.PNG)
#### Penyelesaian
- Masalah injeksi SQL.
- Kita dapat memeriksa kueri dengan melihat sumbernya.
```
def get_user(username, password):
    database = connect_database()
    cursor = database.cursor()
    try:
        cursor.execute('SELECT username, password FROM `userandpassword` WHERE username=\'%s\' AND password=\'%s\'' % (username, hashlib.md5(password.encode())))
    except:
        return render_template("failure.html")
    row = cursor.fetchone()
    database.commit()
    database.close()
    if row is None: return None
    return (row[0],row[1])
```
- Periksa nilai yang difilter
```
admin' || 1=1 #
```
- Saat dicoba memang gagal, tapi hal tersebut tidak menunjukkan kesalahan, jadi itu adalah time based injection dan saya mencoba melakukan _benchmarking_ dan _sleep_. <br />

- Saya memberikan `/ * * /` pada source code tersebut, disini kata sandi dilewati karena sedang diproses <b>md5</b>.
```
username: admin' /*
```
![login sequel 2](https://user-images.githubusercontent.com/26424136/82976691-f1cb3e00-a009-11ea-867e-50549e12ae64.PNG) <br />
<b>Flag: tjctf{W0w_wHa1_a_SqL1_exPeRt!}</b> 

## Forwarding
![forwarding 2](https://user-images.githubusercontent.com/26424136/83002840-b9daef80-a037-11ea-8b78-5b71abe8137e.PNG)

#### Penyelesaian
- Klik _forwarding_ (Ketika diklik forwarding auto download)
- Buka file forwarding yang telah terdownload melalui notepad
![forwarding](https://user-images.githubusercontent.com/26424136/82977424-fc86d280-a00b-11ea-8e98-b0ddf1018b1b.PNG)
- Flag telah ditemukan <br />
<b>Flag: tjctf{just_g3tt1n9_st4rt3d} </b>

## Sarah Palin Fanpage
![sarah palin fanpage](https://user-images.githubusercontent.com/26424136/83002846-bc3d4980-a037-11ea-8c6e-1ce4558b807c.PNG)
![Screenshot (375)](https://user-images.githubusercontent.com/26424136/82979190-a2d4d700-a010-11ea-9d07-272b608f204e.png)

#### Penyelesaian
- Inspect Element website tersebut, buka cookies pada application
![Screenshot (376)](https://user-images.githubusercontent.com/26424136/82979192-a5373100-a010-11ea-9d7c-e6369123f290.png)
- Decode value pada name data  menggunakan base64 <br />
1. Input
```
eyIxIjpmYWxzZSwiMiI6ZmFsc2UsIjMiOmZhbHNlLCI0IjpmYWxzZSwiNSI6ZmFsc2UsIjYiOmZhbHNlLCI3IjpmYWxzZSwiOCI6ZmFsc2UsIjkiOmZhbHNlLCIxMCI6ZmFsc2V9
```
2. Hasil Decode
```
{"1":false,"2":false,"3":false,"4":false,"5":false,"6":false,"7":false,"8":false,"9":false,"10":false}
```
![Screenshot (377)](https://user-images.githubusercontent.com/26424136/82979194-a5cfc780-a010-11ea-893c-2124dcb44d15.png)
- Ganti false menjadi true, Kemudian encode menggunakan base64 
```
{"1":true,"2":true,"3":true,"4":true,"5":true,"6":true,"7":true,"8":true,"9":true,"10":true}
```
![Screenshot (379)](https://user-images.githubusercontent.com/26424136/82979195-a6685e00-a010-11ea-9512-b33844cb76a3.png)
- Masukan hasil encode pada value data
```
eyIxIjp0cnVlLCIyIjp0cnVlLCIzIjp0cnVlLCI0Ijp0cnVlLCI1Ijp0cnVlLCI2Ijp0cnVlLCI3Ijp0cnVlLCI4Ijp0cnVlLCI5Ijp0cnVlLCIxMCI6dHJ1ZX0=
```
![Screenshot (380)](https://user-images.githubusercontent.com/26424136/82979196-a700f480-a010-11ea-9733-ba38a2678729.png)
- Kemudian refresh dan tutup inspect element
- Buka tab <b>VIP area</b> pada website sarah palin fanpage
![Screenshot (381)](https://user-images.githubusercontent.com/26424136/82979197-a8322180-a010-11ea-9b38-32b7cc7eb63a.png)
- Flag telah ditemukan <br />
Flag: <b>tjctf{wkDd2Pi4rxiRaM5lOcLo979rru8MFqVHKdTqPBm4k3iQd8n0sWbBkOfuq9vDTGN9suZgYlH3jq6QTp3tG3EYapzsTHL7ycqRTP5Qf6rQSB33DcQaaqwQhpbuqPBm4k3iQd8n0sWbBkOf}</b>.


## Hexillology
![Hexillology](https://user-images.githubusercontent.com/26424136/83003350-64531280-a038-11ea-867f-84896a6d9237.PNG)
Gambar pada [flag](https://static.tjctf.org/af83861c918131864a4e3df24c49d9bad766ae701f02387ee0698593b44f3390_Hexillology.png) hexillology
![Hexi flag](https://user-images.githubusercontent.com/26424136/83003542-a7ad8100-a038-11ea-841c-c58f11ce63b4.png)

#### Penyelesaian
- Buka Tool online [Image Color Picker](https://imagecolorpicker.com/en/) untuk mengetahui hex code color pada gambar tersebut
- Upload image hexillology pada Image Color Picker <br />
Dalam gambar terdapat 7 color, copy hex code per color pada gambar tersebut
![image color picker](https://user-images.githubusercontent.com/26424136/83004675-28b94800-a03a-11ea-9fe9-887880db2423.PNG)
- Convert hex to ascii menggunakan [Hex to ASCII Text Converter](https://www.rapidtables.com/convert/number/hex-to-ascii.html) <br />
Input : `#746a63#74667b#70594a#726651#4b3064#626154#50477d`
![Hexillology 2](https://user-images.githubusercontent.com/26424136/83006300-38399080-a03c-11ea-8f20-9b8cce81ba32.PNG)
- Flag telah ditemukan <br />
Flag: <b>tjctf{pYJrfQK0dbaTPG}</b>


## RSABC 
![rsabcc](https://user-images.githubusercontent.com/26424136/82997703-ec351e80-a030-11ea-9a2f-45f5d0a21cbf.PNG)
![rsabccc](https://user-images.githubusercontent.com/26424136/83002151-e6423c00-a036-11ea-958e-9c77c94cb085.PNG)

#### Penyelesaian
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
Flag: <b>tjctf{BOLm1QMWi3c}</b>
