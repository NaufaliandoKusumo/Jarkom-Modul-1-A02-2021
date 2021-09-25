# Jarkom-Modul-1-A02-2021

#### 1. Sebutkan webserver yang digunakan pada "ichimarumaru.tech"! 
- Masukkan command `http contains "ichimarumaru.tech"` pada display filtering\
  ![](https://i.postimg.cc/xCLPwnnk/image.png)
- Pilih salah satu paket, lalu Follow TCP Stream\
  ![](https://i.postimg.cc/nhQ9RTHr/image.png)
- Didapatkan webserver pada "ichimarumaru.tech" adalah `nginx`\
  ![](https://i.postimg.cc/LX4XpVMz/image.png)

#### 2. Temukan paket dari web-web yang menggunakan basic authentication method!
- Gunakan command http.authbasic pada display filtering\
  ![](https://i.postimg.cc/GhdYq6tp/image.png)\
  Setelah filtering, terlihat ada tiga paket
  
#### 3. Ikuti perintah di basic.ichimarumaru.tech! Username dan password bisa didapatkan dari file .pcapng!
- Memasukkan command filtering `http.host contains "basic.ichimarumaru.tech"`\
  ![](https://i.postimg.cc/pVFbq173/image.png)
- Username dan password ada di Credentials, yaitu:\
  ![](https://i.postimg.cc/rwqByymL/image.png)\
  Username = kuncimenujulautan\
  Password = tQKEJFbgNGC1NCZlWAOjhyCOm6o3xEbPkJhTciZN
- Perintah yang muncul, beserta jawabannya dalam kolom
  ![](https://i.postimg.cc/Pqx0Z6Y3/image.png)

#### 4. Temukan paket mysql yang mengandung perintah query select!
- Memasukkan filter menggunakan `mysql contains SELECT`\
  ![](https://i.postimg.cc/nLBBdx4C/image.png)
- Pilih salah satu paket, lalu Follow TCP Stream\
  ![](https://i.postimg.cc/wjGYW8q8/image.png)
- Bisa dilihat paket mysql mengandung perintah query select\
  ![](https://i.postimg.cc/0jcBbDrR/image.png)

#### 5. Login ke portal.ichimarumaru.tech kemudian ikuti perintahnya! Username dan password bisa didapat dari query insert pada table users dari file .pcap!
- Masukkan filter `mysql` untuk memfilter query-query mysql

![](https://i.postimg.cc/J7HxGzKk/image.png)

didapatkan username berupa `akakanomi` dan password `pemnbelah4lautan`



#### 6. Cari username dan password ketika melakukan login ke FTP Server!
- Masukkan command `ftp` pada display filtering\
  ![](https://i.postimg.cc/QNygxfdN/image.png)
- Pilih salah satu paket, lalu Follow TCP Stream\
  ![](https://i.postimg.cc/fbDmgFBC/image.png)
- Bisa dilihat username dan passwordnya\
  ![](https://i.postimg.cc/2ybZZfSk/image.png)\
  Username = secretuser\
  Password = aku.pengen.pw.aja

#### 7. Ada 500 file zip yang disimpan ke FTP Server dengan nama 0.zip, 1.zip, 2.zip, ..., 499.zip. Simpan dan Buka file pdf tersebut. (Hint = nama pdf-nya "Real.pdf")
- Untuk filtering dengan nama "Real.pdf" masukkan command tcp contains “Real.pdf”\
  ![](https://i.postimg.cc/pTgQWBD1/image.png)
- Lalu Follow TCP Stream\
  ![](https://i.postimg.cc/1zXDDdBj/image.png)
- Untuk mensave file, sebelumnya pilih Show data as Raw\
  ![](https://i.postimg.cc/BZHH5H54/image.png)
- Lalu save as\
  ![](https://i.postimg.cc/hGX7XdPF/image.png)
- Setelah diunzip muncul pdf dengan nama "Real"\
  ![](https://i.postimg.cc/1Xr8k0MF/image.png)
- Isi dari Real.pdf\
  ![](https://i.postimg.cc/L8bJF8kx/image.png)

#### 8. Cari paket yang menunjukan pengambilan file dari FTP tersebut!
- Memasukkan command `ftp-data.command contains "RETR"` pada display filtering, dengan `RETR` untuk mengunduhan gambar\
  ![](https://i.postimg.cc/HstS2f0Y/image.png)\
  Tidak ditemukan adanya paket
- Mengecek apakah ada command `RETR` dengan cara filtering dengan `ftp.request.command`\
  ![](https://i.postimg.cc/FHRxx1sp/image.png)\
  Setelah dilihat tidak ada command `RETR`
  
#### 9. Dari paket-paket yang menuju FTP terdapat inidkasi penyimpanan beberapa file. Salah satunya adalah sebuah file berisi data rahasia dengan nama "secret.zip". Simpan dan buka file tersebut!
- Memasukkan command `ftp-data.command contains "secret.zip"` pada display filtering\
  ![](https://i.postimg.cc/L5WjC3sV/image.png)
- Pada salah satu paket, lakukan Follow TCP Stream\
  ![](https://i.postimg.cc/nhBq27fv/image.png)
- Sebelum mensave file, pilih Show data as Raw\
  ![](https://i.postimg.cc/t4QxsTn7/image.png)
- Memasukkan nama file untuk disave\
  ![](https://i.postimg.cc/SKV21fTz/image.png)
- Akan diminta untuk memasukkan kata sandi\
  ![](https://i.postimg.cc/kDrBR14L/image.png)

#### 10. Selain itu terdapat "history.txt" yang kemungkinan berisi history bash server tersebut! Gunakan isi dari "history.txt" untuk menemukan password untuk membuka file rahasia yang ada di "secret.zip"!
- Untuk melihat history bash server dalam "history.txt", masukkan command `ftp-data.command contains "history.txt"`\
![](https://i.postimg.cc/7Z8Kqqxn/image.png)
- Pada key terdapat file `bukanapaapa.txt`\
![](https://i.postimg.cc/yddPLdPs/image.png)
- Untuk melihat isi file `bukanapaapa.txt`, masukkan command `ftp-data.command contains "bukanapaapa.txt"`\
![](https://i.postimg.cc/NF2xwzSn/image.png)\
  Ada text "d1b1langbukanapaapajugagapercaya" yang merupakan kata sandi untuk membuka file "secret.zip"
- Isi dari file rahasia yang bernama Wanted.pdf\
![](https://i.postimg.cc/259p1dZd/image.png)

#### 11. Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80! 
- Gunakan command `src port 80`

![] 

#### 12. Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!
#### 13. Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!
#### 14. Filter sehingga wireshark hanya mengambil paket yang tujuannya ke kemenag.go.id!
- Gunakan command `dst host kemenag.go.id`

![](https://i.postimg.cc/C529CPXs/image.png)

#### 15. Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!

