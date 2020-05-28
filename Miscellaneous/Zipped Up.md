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
	![a](https://user-images.githubusercontent.com/26424136/83170899-766ba880-a13f-11ea-9a5d-64712ff85e1c.PNG)
	<br> **_zip file_** telah berhasil diunduh pada _Archive Manager_ dari Ubuntu
	![b](https://user-images.githubusercontent.com/26424136/83170905-78356c00-a13f-11ea-9ec8-2f87e8bfe807.PNG)

2. Lakukan pengekstrakan manual dari **_zip file_** yang telah diunduh
![c](https://user-images.githubusercontent.com/26424136/83170907-79ff2f80-a13f-11ea-98dc-746fe1a3211c.PNG)

3. Untuk mempermudah metode selanjutnya, maka lakukan penggantian nama _(rename)_ pada file hasil pengekstrakan dengan nama ```ZippedUp```
![d](https://user-images.githubusercontent.com/26424136/83170910-7a97c600-a13f-11ea-8e1b-7ab739867992.PNG)
<br> Kita buka terlebih dahulu si dari folder hasil pengekstrakan **_zip file_** dengan menggunakan ```ls``` pada folder tersebut
![e](https://user-images.githubusercontent.com/26424136/83170912-7bc8f300-a13f-11ea-98e9-a50759fe4115.PNG)
<br>Dapat kita lihat bahwa ada file ```1.tar.bz2``` .  Ini artinya kita harus melakukan pengekstrakan terhadap file tersebut.

4. Kita akan menggunakan sebuah **_python script_** dengan nama ```UnzippedUp``` untuk melakukan pengekstrakan __semua file__ yang ada di dalam folder ```ZippedUp```
![f](https://user-images.githubusercontent.com/26424136/83170914-7c618980-a13f-11ea-961c-0be69b408ac4.PNG)

5. Jalankan **_python script_** tersebut melalui terminal Ubuntu
	```html
	python3 UnzippedUp.py
	```

<br>Pengekstrakan telah berhasil dilakukan dan dapat kita mendapatkan semua isi dari **_zip file_** berjumlah __1000 folder__
![g](https://user-images.githubusercontent.com/26424136/83172313-9b611b00-a141-11ea-9878-a6e63f76c3a6.png)

6. Kita tinjau ke dalam salah satu folder yakni pada folder ```1``` terdapat sebuah file bereksistensi ```txt``` yang berisi ```flag``` yang __bukan flag__ dengan menggunakan ```cat 1.txt```
<br />
```html
cd 1
cat 1.txt
```
<b>1.txt</b> berisi <b>bukan flag</b> yaitu _tjctf{n0t_th3_fl4g}_
![h2](https://user-images.githubusercontent.com/26424136/83172309-9a2fee00-a141-11ea-94ed-20e6f755a2a3.png)

7. Dikarenakan ada 1000 folder dan hanya ada 1 folder saja yang berisi file berekstensi ```txt``` yang mengandung ```flag sebenarnya```, maka kita gunakan ```grep``` 
	```html
	grep -v -r "tjctf{n0t_th3_fl4g}" /home/hanaghaliyah/ZippedUp/0
	```
	<br>Lakukan __scroll__ hingga ditemukan sebuah ```flag sebenarnya```
	![i](https://user-images.githubusercontent.com/26424136/83172316-9bf9b180-a141-11ea-9519-5259e3b3ab65.png)
<br>Nah, sebuah ```flag``` terlihat dan flag telah ditemukan
![j](https://user-images.githubusercontent.com/26424136/83172318-9c924800-a141-11ea-8a91-05547297cfb2.PNG)

____________________________________
## Flag
Flag: <b>tjctf{p3sky_z1p_f1L35}</b>
