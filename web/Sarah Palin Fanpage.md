# Sarah Palin Fanpage

## SOAL
![sarah palin fanpage](https://user-images.githubusercontent.com/26424136/83002846-bc3d4980-a037-11ea-8c6e-1ce4558b807c.PNG)
![Screenshot (375)](https://user-images.githubusercontent.com/26424136/82979190-a2d4d700-a010-11ea-9d07-272b608f204e.png)

## Penyelesaian
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

## Flag
Flag: <b>tjctf{wkDd2Pi4rxiRaM5lOcLo979rru8MFqVHKdTqPBm4k3iQd8n0sWbBkOfuq9vDTGN9suZgYlH3jq6QTp3tG3EYapzsTHL7ycqRTP5Qf6rQSB33DcQaaqwQhpbuqPBm4k3iQd8n0sWbBkOf}</b>.
