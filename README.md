# Jarkom-Modul-1-E01-2021

- Clarence 05111940000104
- Nur Putra Khanafi 05111940000020
- Husnan 05111940007002

### List
1. [Soal 1](https://github.com/theodorusclarence/Jarkom-Modul-1-E01-2021#1)
2. [Soal 2](https://github.com/theodorusclarence/Jarkom-Modul-1-E01-2021#2)
3. [Soal 3](https://github.com/theodorusclarence/Jarkom-Modul-1-E01-2021#3)
4. [Soal 4](https://github.com/theodorusclarence/Jarkom-Modul-1-E01-2021#4)
5. [Soal 5](https://github.com/theodorusclarence/Jarkom-Modul-1-E01-2021#5)
6. [Soal 6](https://github.com/theodorusclarence/Jarkom-Modul-1-E01-2021#6)
7. [Soal 7](https://github.com/theodorusclarence/Jarkom-Modul-1-E01-2021#7)
8. [Soal 8](https://github.com/theodorusclarence/Jarkom-Modul-1-E01-2021#8)
9. [Soal 9](https://github.com/theodorusclarence/Jarkom-Modul-1-E01-2021#9)
10. [Soal 10](https://github.com/theodorusclarence/Jarkom-Modul-1-E01-2021#10)
11. [Soal 11](https://github.com/theodorusclarence/Jarkom-Modul-1-E01-2021#11)
12. [Soal 12](https://github.com/theodorusclarence/Jarkom-Modul-1-E01-2021#12)
13. [Soal 13](https://github.com/theodorusclarence/Jarkom-Modul-1-E01-2021#13)
14. [Soal 14](https://github.com/theodorusclarence/Jarkom-Modul-1-E01-2021#14)
15. [Soal 15](https://github.com/theodorusclarence/Jarkom-Modul-1-E01-2021#15)


## 1 
> Sebutkan webserver yang digunakan pada "ichimarumaru.tech"! 

Pertama, cari dengan mengetikkan pada filter `tcp contains ichimarumaru.tech`.

![Picture1](https://user-images.githubusercontent.com/65794806/134769729-5cf4b26a-eea0-4c51-b4e5-e108534809d2.png)

Setelah itu klik kanan pada salah satu paket dan pilih `Follow > TCP Stream`

![Picture1s2](https://user-images.githubusercontent.com/65794806/134769796-f6a47bbb-e834-4fa2-991d-7ea52258bb0b.png)

Akan muncul beberapa informasi, informasi web server dapat dilihat pada tulisan server yang mana webserver yang digunakan adalah **nginx/1.18.0 (Ubuntu)**

## 2 
> Temukan paket dari web-web yang menggunakan basic authentication method! 

Filter dilakukan dengan *syntax* `http.authbasic`

![Picture2](https://user-images.githubusercontent.com/65794806/134769893-5a6703ad-7aa7-4e11-801d-f1128285c0e0.png)

## 3 
> Ikuti perintah di basic.ichimarumaru.tech! Username dan password bisa didapatkan dari file .pcapng!

Melihat HTTP Auth Header dengan `http.authbasic` di display filter

![Picture3](https://user-images.githubusercontent.com/65794806/134770121-9b77cf07-69a9-4f58-b2d3-46952debc80e.png)

Setelah itu lihat isi dari Hypertext yang mana didalamnya ada **Authorization**. Kemudian pilih **Credentials** yaitu format dari username:password.

**Credentials: kuncimenujulautan:tQKEJFbgNGC1NCZlWAOjhyCOm6o3xEbPkJhTciZN**

Setelah itu masuk ke basic.ichimarumaru.tech dengan username **kuncimenujulautan** dan password **tQKEJFbgNGC1NCZlWAOjhyCOm6o3xEbPkJhTciZN** yang nantinya akan ada soal tambahan mengenai konfigurasi pengkabelan.

![Picture3s2](https://user-images.githubusercontent.com/65794806/134770132-6618d373-ae85-4948-b6d8-067daf4004c7.png)

## 4 
> Temukan paket mysql yang mengandung perintah query select!

Menggunakan display filter `mysql contains SELECT || mysql contains select`

![Picture4](https://user-images.githubusercontent.com/65794806/134770216-bb21c232-74eb-47d9-aca5-0722a8668589.png)

## 5 
> Login ke portal.ichimarumaru.tech kemudian ikuti perintahnya! Username dan password bisa didapat dari query insert pada table users dari file .pcap!

Pertama, mencari query insert dengan `mysql contains INSERT || mysql contains insert`

![Picture5](https://user-images.githubusercontent.com/65794806/134770312-a1de6d29-f5cc-491e-8207-c2180012d345.png)

Setelah itu akan muncul sebuah command INSERT yang dapat dilihat langsung pada display bawah maupun pada Request Command Query > Statement. Command INSERT tersebut memasukkan data username dan password.

**Username: akakanomi**
**Password: pemisah4lautan**

Setelah itu masuk ke portal.ichimarumaru.tech dengan username **akakanomi** dan password **pemisah4lautan** yang nantinya akan ada soal tambahan mengenai konfigurasi pengkabelan.

![Picture5s2](https://user-images.githubusercontent.com/65794806/134770682-9bef96f3-b144-4982-9cf8-402bfd3d4378.png)


## 6 
> Cari username dan password ketika melakukan login ke FTP Server!

Sesuai dengan referensi, default port FTP server adalah port 21

![image](https://user-images.githubusercontent.com/55318172/134176792-8c99257d-e8f7-4016-b6c8-fb7f0c3af975.png)

Maka, kami menggunakan `ftp && tcp.port == 21` pada Display Filter. Kemudian kami mengecek paket yang memiliki informasi user

![image](https://user-images.githubusercontent.com/55318172/134177389-a2d53bc5-d6b4-4076-b012-e3fac24e9832.png)

Ketika dicek, didapatkan user: **secretuser** pada FTP Request arg

Kemudian kami juga mengecek password, 

![image](https://user-images.githubusercontent.com/55318172/134177590-685128e1-9418-4881-abbf-8d2f8bdb4362.png)

Ketika dicek, didapatkan password: **aku.pengen.pw.aja** pada FTP Request arg

Maka, username:password = **secretuser:aku.pengen.pw.aja**

## 7 
> Ada 500 file zip yang disimpan ke FTP Server dengan nama 0.zip, 1.zip, 2.zip, ..., 499.zip. Simpan dan Buka file pdf tersebut. (Hint = nama pdf-nya "Real.pdf")

Pertama, karena ingin mencari file yang bernama Real.pdf pada FTP Server, maka kami menggunakan display filter yaitu `ftp-data contains "Real.pdf`. Kemudian kami `Follow > TCP Stream`

![image](https://user-images.githubusercontent.com/55318172/134177771-e4103a9b-27b2-4c60-8a45-32902b7f2887.png)

Dari Follow TCP Stream tersebut kita dapat menyimpan file as **Raw**, dan dinamakan dengan ekstensi `.zip`

![image](https://user-images.githubusercontent.com/55318172/134177908-2d72ea41-a623-4604-9f5b-c7a48a7dfc6f.png)

Kemudian, file tersebut bisa langsung diunzip dan ketika dibuka tampilannya sebagai berikut

![image](https://user-images.githubusercontent.com/55318172/134177984-cc17aef8-9c15-45d2-8996-b136f265323c.png)

## 8 
> Cari paket yang menunjukan pengambilan file dari FTP tersebut!

Karena pengambilan data dari FTP, maka kita bisa menggunakan command yang mirip dengan nomor 7, dengan mencari pengambilan file yaitu `RETR`, maka pada Display Filter dapat dicari `ftp-data.command contains RETR`.

![image](https://user-images.githubusercontent.com/55318172/134178149-fde8c90d-4260-4559-83a3-2c60051d5dc4.png)

## 9 
> Dari paket-paket yang menuju FTP terdapat inidkasi penyimpanan beberapa file. Salah satunya adalah sebuah file berisi data rahasia dengan nama "secret.zip". Simpan dan buka file tersebut!

Pada nomor 9, kami menggunakan `ftp-data.command contains secret.zip` untuk mencari file, kemudian menyimpan menggunakan `Follow > TCP Stream`, save as raw.

![image](https://user-images.githubusercontent.com/55318172/134178365-6e3eafaf-e075-4770-8b3b-93190697aec6.png)

Ketika kami buka file `.zip` tersebut di lock, maka kami mencari ke nomor 10, dan mendapatkan password: **d1b1langbukanapaapajugagapercaya**, dan mengunzip file dengan password tersebut.

![image](https://user-images.githubusercontent.com/55318172/134178613-14e85f1d-9382-4827-9253-b6661cbd82a7.png)

Kemudian kami setelah berhasil di unzip, terdapat pdf sebagai berikut

![image](https://user-images.githubusercontent.com/55318172/134178669-7a6a5573-499a-47fe-98fc-63f54a9cd257.png)


## 10
>  Selain itu terdapat "history.txt" yang kemungkinan berisi history bash server tersebut! Gunakan isi dari "history.txt" untuk menemukan password untuk membuka file rahasia yang ada di "secret.zip"!

Karena kita ingin mencari "history.txt" pada FTP, maka kita bisa menambahkan `ftp-data.command contains history.txt` pada Display Filter

![image](https://user-images.githubusercontent.com/55318172/134178799-8e82f498-2cef-44fd-b9d7-457342a855b4.png)

Setelah di `Follow > TCP Stream` maka didapat history bash script yang pada line 289 berarti menyimpan baris terakhir dari `bukanapaapa.txt` dan digunakan untuk membuka zip nomor 9.

Maka, kami mencari file `bukanapaapa.txt` dengan Display Filter `ftp-data.command contains bukanapapa.txt`

![image](https://user-images.githubusercontent.com/55318172/134179324-082685d1-465f-4ee9-9a42-deade35ecb37.png)

Dari `Follow > TCP Stream`, atau menjalankan bash script line 289,

![image](https://user-images.githubusercontent.com/55318172/134179389-0652ea32-4bbc-49b3-8fa8-98c88163320b.png)

Didapat password yaitu **d1b1langbukanapaapajugagapercaya**

## 11
>  Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80!

Menggunakan `src port 80` di Capture Filter

![11](https://user-images.githubusercontent.com/57633103/134199342-44c1c847-4397-405f-8b53-6433bec4b78e.png)

Untuk memunculkan paket, kita bisa mencoba membuka basic.ichimarumaru.tech

## 12
>  Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!

Menggunakan `port 21` di capture filter

![12](https://user-images.githubusercontent.com/57633103/134199397-550a28b2-d80e-462e-81c4-24a5b2e052c3.png)

### Revisi

Untuk mengambil paket-nya dapat melakukan connect dengan server filezilla  terlebih dahulu. Dapat dengan membuat server dari XAMPP dan melakukan connect dengan filezilla client. Setelah itu membuka wireshark dan melakukan filter dengan `port 21` pada koneksi *Adapter for loopback traffic capture* yang didalamnya terdapat paket dari FTP.

![Soal12FTPa](https://user-images.githubusercontent.com/65794806/134770732-70c36042-b269-4d28-b875-0713545da368.png)

Hasil filter sebagai berikut.

![Soal12FTP](https://user-images.githubusercontent.com/65794806/134770761-cf8ef39e-8aa2-410f-a3e6-49a10be0904f.png)

## 13
>  Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!

Menggunakan `dst port 443` pada capture filter

![13](https://user-images.githubusercontent.com/57633103/134199419-5ed9739d-85c1-401e-8614-56e0d8ea1b01.png)

## 14
>  Filter sehingga wireshark hanya mengambil paket yang tujuannya ke kemenag.go.id!

Menggunakan `dst host kemenag.go.id` pada capture filter

![14](https://user-images.githubusercontent.com/57633103/134199446-9e6d41b9-8c5f-460f-8245-f7cf54595347.png)

Untuk memunculkan paket, kita bisa mencoba membuka kemenag.go.id

## 15
>  Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!

Mengecek IP dengan settingan di macbook

![15 1](https://user-images.githubusercontent.com/57633103/134199467-b6c73038-c730-4aa8-84f5-83774a51bd7b.png)

Kemudian dapat menggunakan `ip src 192.168.100.11` pada Display Filter

![15 2](https://user-images.githubusercontent.com/57633103/134199498-69e2e4cf-980a-43b5-bd0d-36a6eaaee963.png)

Pada windows, ip dapat dicek pada comand prompt dengan mengetikkan ipconfig

![15 3](https://user-images.githubusercontent.com/57633103/134199531-39ab1ee0-a19d-4f41-88c6-2719a740539b.png)

Setelah itu scroll informasi untuk mendapatkan melihat ipv4 pada Wi-Fi

![15 4](https://user-images.githubusercontent.com/57633103/134199550-42551f64-26ab-4f17-952b-cfe6a8b4657d.png)

Setelah itu dapat memasukkan sintaks yang sama pada filter.
