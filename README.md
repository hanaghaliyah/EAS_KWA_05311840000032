# EAS_KWA_05311840000032
[TJCTF 2020] <br />
Nama : Hana Ghaliyah Azhar <br />
NRP  : 05311840000032

## Login Sequel
`<b>Login</b> as admin you must. This time, the client is of no use :(. What to do?` <br />
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
It can't be that hard... right? <br />
_forwarding_ <br />

#### Penyelesaian
- Klik _forwarding_ (Ketika diklik forwarding auto download)
- Buka file forwarding yang telah terdownload melalui notepad
![forwarding](https://user-images.githubusercontent.com/26424136/82977424-fc86d280-a00b-11ea-8e98-b0ddf1018b1b.PNG)
- Flag telah ditemukan <br />
<b>Flag: tjctf{just_g3tt1n9_st4rt3d} </b>

## Sarah Palin Fanpage
Are you a true fan of Alaska's most famous governor? Visit the _Sarah Palin fanpage_.
![Screenshot (375)](https://user-images.githubusercontent.com/26424136/82979190-a2d4d700-a010-11ea-9d07-272b608f204e.png)

#### Penyelesaian
- Inspect Element website tersebut, buka cookies pada application
![Screenshot (376)](https://user-images.githubusercontent.com/26424136/82979192-a5373100-a010-11ea-9d7c-e6369123f290.png)
- Decode value pada name data  menggunakan base64 <br />
Input
```
eyIxIjpmYWxzZSwiMiI6ZmFsc2UsIjMiOmZhbHNlLCI0IjpmYWxzZSwiNSI6ZmFsc2UsIjYiOmZhbHNlLCI3IjpmYWxzZSwiOCI6ZmFsc2UsIjkiOmZhbHNlLCIxMCI6ZmFsc2V9
```
Hasil Decode
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
