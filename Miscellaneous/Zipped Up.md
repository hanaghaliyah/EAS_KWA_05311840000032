# Zipped Up

## SOAL
![Zipped Up](https://user-images.githubusercontent.com/26424136/83015646-f106cc00-a04a-11ea-8c98-5ad7fb929279.PNG)
[zip file](https://static.tjctf.org/663d7cda5bde67bd38a8de1f07fb9fab9dd8dd0b75607bb459c899acb0ace980_0.zip)
____________________________________
## Penyelesaian
Disini saya menggunakan <b>OS Ubuntu</b> <br />
1. Lakukan pengunduhan terhadap **_zip file_** melalui terminal ubuntu dengan menggunakan ```wget``` 
	```html
	wget "https://static.tjctf.org/663d7cda5bde67bd38a8de1f07fb9fab9dd8dd0b75607bb459c899acb0ace980_0.zip"
	```
	![01](https://user-images.githubusercontent.com/49342639/82989639-357f7100-a025-11ea-94fd-d626ef482362.PNG)
<br> **_zip file_** telah berhasil diunduh pada _Archive Manager_ dari Ubuntu
![02](https://user-images.githubusercontent.com/49342639/82990061-c8b8a680-a025-11ea-9c13-6fe8888a00ae.PNG)

2. Lakukan pengekstrakan manual dari **_zip file_** yang telah diunduh
![03](https://user-images.githubusercontent.com/49342639/82990232-0f0e0580-a026-11ea-9d18-841d01df1802.PNG)

3. Untuk mempermudah metode selanjutnya, maka lakukan penggantian nama _(rename)_ pada file hasil pengekstrakan dengan nama ```ZippedUp```
![04](https://user-images.githubusercontent.com/49342639/82990451-6e6c1580-a026-11ea-99a6-e07f0de5796a.PNG)
<br> Kita buka terlebih dahulu si dari folder hasil pengekstrakan **_zip file_** dengan menggunakan ```ls``` pada folder tersebut
![05 00](https://user-images.githubusercontent.com/49342639/82991157-79737580-a027-11ea-90e7-12e7b54f92fb.PNG)
<br>Dapat kita lihat bahwa ada file ```1.tar.bz2``` .  Ini artinya kita harus melakukan pengekstrakan terhadap file tersebut.

4. Kita akan menggunakan sebuah **_python script_** dengan nama ```UnzippedUp``` untuk melakukan pengekstrakan __semua file__ yang ada di dalam folder ```ZippedUp```
![06](https://user-images.githubusercontent.com/49342639/82991971-ac6a3900-a028-11ea-9a1b-d47aa7301645.PNG)

5. Jalankan **_python script_** tersebut melalui terminal Ubuntu
	```html
	python3 UnzippedUp.py
	```
	![07](https://user-images.githubusercontent.com/49342639/82992451-65c90e80-a029-11ea-94b4-6f3e980f0a4b.PNG)
<br>Pengekstrakan telah berhasil dilakukan dan dapat kita mendapatkan semua isi dari **_zip file_** berjumlah __1000 folder__
![08](https://user-images.githubusercontent.com/49342639/82992736-c5271e80-a029-11ea-9d09-c8d95454e1d3.PNG)

6. Kita tinjau ke dalam salah satu folder yakni pada folder ```1``` terdapat sebuah file bereksistensi ```txt``` yang berisi ```flag``` yang __bukan flag__ dengan menggunakan ```cat 1.txt```
![09 00](https://user-images.githubusercontent.com/49342639/82993310-93628780-a02a-11ea-87d2-7950ab23c16c.PNG)

7. Dikarenakan ada 1000 folder yang hanya akan ada 1 folder saja yang berisi file berekstensi ```txt``` yang mengandung ```flag sebenarnya```, maka kita gunakan ```grep``` 
	```html
	grep -v -r "tjctf{n0t_th3_fl4g}" /home/akmu/Documents/ZippedUp/0
	```
	![09 00 (1)](https://user-images.githubusercontent.com/49342639/82993876-7d08fb80-a02b-11ea-8369-e1e028179c01.PNG)
	<br>Lakukan __scroll__ hingga ditemukan sebuah ```flag sebenarnya```
	![10](https://user-images.githubusercontent.com/49342639/82994015-b04b8a80-a02b-11ea-903e-a74edb2106d8.PNG)
<br>Nah, sebuah ```flag``` terlihat dan kita berhasil mendapatkannya
![11](https://user-images.githubusercontent.com/49342639/82994110-d709c100-a02b-11ea-91df-5bb1d2f153a6.PNG)

____________________________________
## Flag
Flag: <b>tjctf{p3sky_z1p_f1L35}</b>
