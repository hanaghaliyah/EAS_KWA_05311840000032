# Titanic

## SOAL
![Titanic](https://user-images.githubusercontent.com/26424136/83098919-0c6ae900-a0d6-11ea-83bb-33ce3cab335e.PNG)

## Penyelesaian
Yang kita ketahui adalah hash MD5 tersebut berasal dari script film "Titanic". Setiap katanya dibuat lowercase dan di tambahi dengan tjctf{}. 
Langkah pertama adalah mengkopi script film Titanic terlebih dahulu di [sini](http://sites.inka.de/humpty/titanic/script.html). Kemudian dengan bantuan visual studio code, ubah semua menjadi lowercase, hapus `.` `,` `:` `/` , ubah spasi menjadi enter dan tambahkan tjctf{} di setiap barisnya.
Setelah itu gunakan hashcat pada terminal dengan command sebagai berikut :

    hashcat -m 0 -a 0 9326ea0931baf5786cde7f280f965ebb titanic.txt --force --show

Titanic.txt adalah script dari film "Titanic" yang sudah diubah. Tekan enter dan hasil akan langsung muncul. <br />
Cocokkan dengan MD5 hash `9326ea0931baf5786cde7f280f965ebb` pada [MD5 Hash Generator](https://passwordsgenerator.net/md5-hash-generator/) seperti gambar diatas. Flag telah ditemukan. <br />
![titanic](https://user-images.githubusercontent.com/26424136/83210293-adb07880-a184-11ea-8f29-c92419bb0c02.PNG) <br />

____________________________________
## Flag

Flag: <b>tjctf{marlborough's}</b>
