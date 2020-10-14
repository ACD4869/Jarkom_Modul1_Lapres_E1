# Jarkom_Modul1_Lapres_E1

**Intan Kusuma R  (05111840000020)**

**Julius          (05111840000082)**

A.	Display Filter
1.	Sebutkan webserver yang digunakan pada "testing.mekanis.me"!
* Cari IP dari domain testing.mekanis.me
* frame contains "testing.mekanis.me"<br>
![1a](https://user-images.githubusercontent.com/61036923/96029460-eaa3b000-0e84-11eb-912d-a00668dabc2e.png)
* find response from website, karena tidak bisa pakai nama websitenya, gunakan IP dari website yang sudah diketahui dari hasil wireshark diatas
* ip.src_host == "157.245.50.224" and http.response<br>
![1b](https://user-images.githubusercontent.com/61036923/96029410-d65fb300-0e84-11eb-86c8-a1a96a74db91.png)
* Hasil ada di field server dari HTTP header
* nginx/1.14.0 (Ubuntu)


2.	Simpan gambar "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"!
* frame contains "Sukabumi141436"<br>
![2a](https://user-images.githubusercontent.com/61036923/96029560-07d87e80-0e85-11eb-8cc4-a80afb6848d1.png)
* export http<br>
![2b](https://user-images.githubusercontent.com/61036923/96029645-23dc2000-0e85-11eb-87c3-43fda15fd058.png)
* Search nama filenya<br>
![2c](https://user-images.githubusercontent.com/61036923/96029717-3eae9480-0e85-11eb-9edb-b0bf39fe40b4.png)
* export<br>
![2d](https://user-images.githubusercontent.com/61036923/96030396-2428eb00-0e86-11eb-820b-70a2b83b215d.jpg)

3.	Cari username dan password ketika login di "ppid.dpr.go.id"!
* http.host == "ppid.dpr.go.id" and http.request.method == "POST"<br>
![3a](https://user-images.githubusercontent.com/61036923/96029783-5259fb00-0e85-11eb-9a5f-f5c74eea7db4.png)
* user: 10pemuda
* password: guncangdunia

4.	Temukan paket dari web-web yang menggunakan basic authentication method!
* http.authbasic<br>
![4a](https://user-images.githubusercontent.com/61036923/96029873-73bae700-0e85-11eb-9d98-7d1321c3bba3.png)
*  follow http stream untuk check web nya<br>
![4b](https://user-images.githubusercontent.com/61036923/96029940-87fee400-0e85-11eb-8d33-765a2787696e.png)
* webiste testing.mekanis.me

5.	Ikuti perintah di aku.pengen.pw! Username dan password bisa didapatkan dari file .pcapng!
* http.host == "aku.pengen.pw"<br>
![5a](https://user-images.githubusercontent.com/61036923/96029995-9fd66800-0e85-11eb-8b8d-1d3236a3b3c0.png)
![5b](https://user-images.githubusercontent.com/61036923/96030052-b2e93800-0e85-11eb-8934-9244821ea6b9.png)
* user: kakakgamtenk
* pass: hartatahtabermuda<br>
![5c](https://user-images.githubusercontent.com/61036923/96030094-c7c5cb80-0e85-11eb-9ef4-40a8e126feff.png)<br>
    1. Putih - Oranye
    2. Oranye
    3. Putih - Hijau
    4. Biru
    5. Putih - Biru
    6. Hijau
    7. Putih - Coklat
    8. Coklat

6.	Seseorang menyimpan file zip melalui FTP dengan nama "Answer.zip". Simpan dan Buka file "Open This.pdf" di Answer.zip. Untuk mendapatkan password zipnya, temukan dalam file zipkey.txt (passwordnya adalah isi dari file txt tersebut).
* ftp-data and ftp-data.command contains "Answer.zip"<br>
![6a](https://user-images.githubusercontent.com/61036923/96030162-dad89b80-0e85-11eb-8ba8-e3913128f611.png)
* follow tcp stream, raw, save as Answer.zip<br>
![6b](https://user-images.githubusercontent.com/61036923/96030208-e9bf4e00-0e85-11eb-8499-cec69fad4b89.png)
**Finding password**
* ftp-data and ftp-data.command contains "txt"<br>
![6c](https://user-images.githubusercontent.com/61036923/96030525-4c184e80-0e86-11eb-93fb-1c08b4fe1cff.png)
* zipkey.txt
* hey997400323051<br>
![6d](https://user-images.githubusercontent.com/61036923/96030546-53d7f300-0e86-11eb-9948-c3335e86cf72.png)
![6e](https://user-images.githubusercontent.com/61036923/96030569-5a666a80-0e86-11eb-89cf-d813268b7cc2.png)

7.	Ada 500 file zip yang disimpan ke FTP Server dengan nama 1.zip, 2.zip, ..., 500.zip. Salah satunya berisi pdf yang berisi puisi. Simpan dan Buka file pdf tersebut.
Your Super Mega Ultra Rare Hint = nama pdf-nya "Yes.pdf"
* ftp-data and frame contains "Yes.pdf"<br>
![7a](https://user-images.githubusercontent.com/61036923/96030664-7bc75680-0e86-11eb-8395-531981e79d95.png)
* follow tcp stream, as raw, save as namaFile.zip<br>
![7b](https://user-images.githubusercontent.com/61036923/96030677-808c0a80-0e86-11eb-9232-ab7fdc2ad39a.png)
![7c](https://user-images.githubusercontent.com/61036923/96031843-16746500-0e88-11eb-9025-b3ef48a40fa4.png)

8.	Cari objek apa saja yang didownload (RETR) dari koneksi FTP dengan Microsoft FTP Service!
* ftp.request.command == "RETR"<br>
![8a](https://user-images.githubusercontent.com/61036923/96030726-94d00780-0e86-11eb-8920-101117405847.png)
* Host yang mana yang microsoft?
* Gunakan follow ftp stream<br>
![8b](https://user-images.githubusercontent.com/61036923/96030941-e082b100-0e86-11eb-94d2-606e3426ae63.png)
* atau cari ip.addr ke sumber, pasti host diberitahu di awal
* ip.addr == 198.246.117.106<br>
![8c](https://user-images.githubusercontent.com/61036923/96030951-e4aece80-0e86-11eb-882b-920427e02365.png)

9.	Cari username dan password ketika login FTP pada localhost!
* ftp.request.command contains "USER" or ftp.request.command contains "PASS"<br>
![9a](https://user-images.githubusercontent.com/61036923/96030964-ea0c1900-0e86-11eb-9fdf-6bab5abc9cd4.png)

10.	Cari file .pdf di wireshark lalu download dan buka file tersebut!
clue: "25 50 44 46" 
* frame contains "pdf"<br>
![10a](https://user-images.githubusercontent.com/61036923/96030984-f001fa00-0e86-11eb-87b6-b6323b144589.png)
![10b](https://user-images.githubusercontent.com/61036923/96032285-a74b4080-0e88-11eb-83a3-b87115647e57.png)
* follow tcp stream, raw, save as test.pdf<br>
![10c](https://user-images.githubusercontent.com/61036923/96031012-f8f2cb80-0e86-11eb-8b01-f63021b1fb8d.png)
![10d](https://user-images.githubusercontent.com/61036923/96031119-23448900-0e87-11eb-8484-8045ebcfee44.png)

B. Capture Filter
1.	Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!
* port 21<br>
![11](https://user-images.githubusercontent.com/61036923/96033601-7b30bf00-0e8a-11eb-8de8-25a5ccf2d614.png)

2.	Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80!
* src port 80<br>
![12](https://user-images.githubusercontent.com/61036923/96033636-8a177180-0e8a-11eb-9928-c2d882336319.png)

3.	Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!
* dst port 443<br>
![13](https://user-images.githubusercontent.com/61036923/96033664-956a9d00-0e8a-11eb-93d3-72cdadcd97c9.png)

4.	Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!
* src host 192.168.1.4<br>
![14](https://user-images.githubusercontent.com/61036923/96033687-9d2a4180-0e8a-11eb-8b7f-966fe5506465.png)

5.	Filter sehingga wireshark hanya mengambil paket yang tujuannya ke monta.if.its.ac.id!
* host monta.if.its.ac.id<br>
![15](https://user-images.githubusercontent.com/61036923/96033710-a5827c80-0e8a-11eb-8fed-93ccb41f106f.png)

