# Gym

### Persoalan
![Gymm](https://user-images.githubusercontent.com/26424136/83095838-6a93ce00-a0ce-11ea-99bf-f41cbaff9a85.PNG)
___________________________________
### Penyelesaian
- Pertama kita harus mendownload file [create a plan](bed9d7b7327958dab4d07b06772a032f3e97455e310956558579e8838762b5e2_gym) yang diberikan pada persoalan. 
- Jalankan command `nc p1.tjctf.org 8008` pada terminal
![gym 1](https://user-images.githubusercontent.com/26424136/83095833-68317400-a0ce-11ea-807b-07b2464168ea.PNG)
- Jadi pada soal ini diminta untuk menurunkan berat badan. Berat badan sekarang yaitu 211 dan targetnya yaitu 180. Per harinya diberi 4 pilihan, dimana di tiap pilihan tersebut dapat mengurangi berat badan dengan nilai tertentu. 
- Untuk mengetahui nilai disetiap pilihan tersebut, kita perlu download aplikasi decompiler. Saya menggunakan aplikasi ghidra, program gym yang telah didownload tadi di decompile disini. <br />
Berikut list pilihan beserta nilainya
  1. eat_healthy = -4
  2. do_pushup = -1
  3. go_run = -2 + -3
  4. go_sleep = -3
- Cari cara biar 211 jadi 180 dalam 7 hari. <br />
211 - 180 = 31, jadi dalam 7 hari kita perlu menurunkan sebanyak 31. <br /> 
Jadi selama 7 hari kita perlu memilih pilihan sebagai berikut: <br />
  - Day 1 : Pilihan 3 = -2 + -3
  - Day 2 : Pilihan 3 = -2 + -3
  - Day 3 : Pilihan 3 = -2 + -3 
  - Day 4 : Pilihan 1 = -4
  - Day 5 : Pilihan 1 = -4
  - Day 6 : Pilihan 1 = -4
  - Day 7 : Pilihan 1 = -4 <br />
                      = - 31
![gym 2](https://user-images.githubusercontent.com/26424136/83095837-69fb3780-a0ce-11ea-9d24-d838ca66fa42.PNG)
- Flag telah ditemukan
____________________________________
## Flag
Flag dari persoalan ini adalah `tjctf{w3iGht_l055_i5_d1ff1CuLt}`.

