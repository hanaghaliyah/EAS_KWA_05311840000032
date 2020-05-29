# Ling Ling

## SOAL
![Ling Ling](https://user-images.githubusercontent.com/26424136/83098764-af6f3300-a0d5-11ea-9dfa-8f87e22cb1ad.PNG)
Who made this [meme](https://static.tjctf.org/d25fe79e6276ed73a0f7009294e28c035437d7c7ffe2f46285e9eb5ac94b6bec_meme.png)?
![meme](https://user-images.githubusercontent.com/26424136/83098775-b4cc7d80-a0d5-11ea-9d64-5ac6c214cd05.png)
[I made this meme](https://www.reddit.com/r/lingling40hrs/comments/gam2if/this_popped_in_my_mind_as_i_was_playing_it_and_i/)! unless.....

-------------------------------------------------------------------------------
## Penyelesaian
Setelah mengunduh gambar, dapat dilihat gambar tersebut adalah meme dengan not balok Chopins Third Ballade. Dari soal dapat diketahui yang dicari adalah pembuat dari meme tersebut. Untuk mendapatkan data tersebut dapat menggunakan `exiftool` dan grep pada `terminal`. 

    $ exiftool meme.png | grep Artist
    
  
Setelah itu akan muncul langsung Artist/pembuat dari meme tersebut.
____________________________________
## Flag

Flag: <b>tjctf{ch0p1n_fl4gs}</b>
