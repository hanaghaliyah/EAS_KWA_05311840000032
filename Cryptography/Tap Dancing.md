# Tap Dancing

## SOAL
![Tap Dancing](https://user-images.githubusercontent.com/26424136/83102869-bf8c1000-a0df-11ea-9735-a2ca95230a30.PNG)
[dance moves](https://static.tjctf.org/518d6851c71c5482dbd5bbe812b678684238c8f4e9e9b3d95a188f7db83a0870_cipher.txt)

## Penyelesaian
Ini merupakan list dance move `1101111102120222020120111110101222022221022202022211`
<br> Kode diatas harus kita terjemahkan menjadi kode morse terlebih dahulu dengan ketentuan seperti dibawah ini :
<br> 0 = spasi (" ")
<br> 1 = minus (-)
<br> 2 = titik (.)
<br> Hasil kode morse dari list dance move yang sudah ditentukan :
<br> `-- ----- .-. ... . -. ----- - -... ....- `
<br> Setelah menghasilkan kode morse, kita melakukan konversi dari kode morse menjadi text menggunakan [translator online](https://morsify.net/), sehingga akan menemukan flagnya.

## FLAG
Flag: <b>tjctf{M0RSEN0TB4SE3}</b>
