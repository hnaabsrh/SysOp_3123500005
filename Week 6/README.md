<div align="center">
  <h1 class="text-align: center;font-weight: bold">Praktikum 4B<br>Praktek System Operasi</h1>
  <h3 class="text-align: center;">Dosen Pengampu : Dr. Ferry Astika Saputra, S.T., M.Sc.</h3>
</div>
<br />
<div align="center">
  <img src="https://upload.wikimedia.org/wikipedia/id/4/44/Logo_PENS.png" alt="Logo PENS">
  <h3 style="text-align: center;">Disusun Oleh : </h3>
  <p style="text-align: center;">
    <strong>Dewangga Wahyu Putera Wangsa (3123500007)</strong><br>
    <strong>Hawa Kharisma Zahara (3123500010)</strong><br>
    <strong>Bayu Ariyo Vonda Wicaksono (3122500017)</strong>
  </p>

<h3 style="text-align: center;line-height: 1.5">Politeknik Elektronika Negeri Surabaya<br>Departemen Teknik Informatika Dan Komputer<br>Program Studi Teknik Informatika<br>2023/2024</h3>
  <hr><hr>
</div>

## Daftar Isi

1. [Laporan Hasil Percobaan 5](#percobaan-5--menghentikan-dan-memulai-kembali-job)
2. [Laporan Hasil Percobaan 6](#percobaan-6--percobaan-dengan-penjadwalan-prioritas)
3. [Laporan Hasil Latihan](#latihan)

### Percobaan 5 : Menghentikan dan Memulai Kembali Job

1. Perintah `yes > /dev/null`

   ![App Screenshot](assets/img/p5_1.png)

   Analisa : Cara lain meletakkan job pada background dengan memulai job secara normal (pada foreground), stop job dan memulai lagi pada background. Gunakan perintah yes > /dev/null untuk memulai job baru. Hentikan sementara job (suspend), bukan menghentikannya (terminate), tetapi menghentikan sementara job sampai di restart. Untuk menghentikan sementara job gunakan Ctrl + Z

2. Perintah `fg`

   ![App Screenshot](assets/img/p5_2.png)

   Analisa: Perintah `fg` disini digunakan untuk me-restart job pada foreground.

3. Perintah `bg`

   ![App Screenshot](assets/img/p5_3.png)

   Analisa : Setelah instruksi fg, Shell akan menampilkan nama perintah yang diletakkan di foreground. Stop job lagi dengan Ctrl + Z. Kemudian gunakan perintah bg untuk meletakkan job pada background.

   Perintah `fg`

   ![App Screenshot](assets/img/p5_4.png)

   Analisa : Job tidak bisa dihentikan dengan Ctrl + Z karena job berada pada background. Untuk menghentikannya, letakkan job pada foreground dengan fg dan kemudian hentikan sementara dengan Ctrl + Z.

4. Perintah `yes &`

   ![App Screenshot](assets/img/p5_5.png)

   Analisa : Job pada background dapat digunakan untuk menampilkan teks pada terminal, dimana dapat diabaikan jika mencoba mengerjakan job lain seperti perintah di atas. Untuk menghentikannya tidak dapat menggunakan Ctrl + C. Job harus dipindah ke foreground baru diberhentikan dengan cara tekan fg dan tekan enter, Kemudian lanjutkan dengan Ctrl + Z untuk menghentikan sementara

5. Perintah `fg %2`, `bg %2`, atau `%2`

   ![App screenshot](assets/img/p5_6.png)
   ![App Screenshot](assets/img/p5_7.png)

   Analisa : Perintah di atas digumakan apabila ingin menjalankan banyak job dalam satu waktu, letakkan job pada foreground atau background dengan memberikan job ID.

6. Perintah `fg`

   ![App Screenshot](assets/img/p5_8.png)

   Analisa : tekan fg dan tekan Enter, kemudian dilanjutkan dengan Ctrl-Z untuk menghentikan sementara

7. Perintah `ps -fae`

   ![App Screenshot](assets/img/p5_9.png)

   ![App Screenshot](assets/img/p5_10.png)

   ![App Screenshot](assets/img/p5_11.png)

   ![App Screenshot](assets/img/p5_12.png)

   Analisa : Lihat job dengan perintah ps -fae dan tekan Enter. Kemudian hentikan proses dengan perintah kill. Pada proses di atas proses yang dihentikan adalah proses dengan PID 6142, yaitu proses yes > /dev/null

8. Logout dan tekan Alt+F7 untuk kembali ke mode grafis

### Percobaan 6 : Percobaan dengan Penjadwalan Prioritas

1. Login sebagai root.
2. Buka 3 terminal, tampilkan pada screen yang sama.

   ![App Screenshot](assets/img/p6_1.png)

3. Pada setiap terminal, ketik `PS1="\w;"` diikuti Enter. `\w` menampilkan path pada direktori home.

   ![App Screenshot](assets/img/p6_2.png)

4. Karena login sebagai root, maka akan ditampilkan `~;` pada setiap terminal. Untuk setiap terminal ketik `pwd` dan tekan Enter untuk melihat bahwa Anda sedang berada pada direktori /root.

   ![App Screenshot](assets/img/p6_3.png)

5. Buka terminal lagi (keempat), atur posisi sehingga keempat terminal terlihat pada screen.

   ![App Screenshot](assets/img/p6_4.png)

6. Pada terminal keempat, ketik `top` dan tekan Enter. Maka program `top` akan muncul. Ketik i. `Top` akan menampilkan proses yang aktif. Ketik `lmt`. `Top` tidak lagi menampilkan informasi pada bagian atas dari screen. Pada percobaan ini, terminal ke empat sebagai jendela `Top`.

   ![App Screenshot](assets/img/p6_5.png)

   Ketik `lmt`

   ![App Screenshot](assets/img/p6_7.png)

7. Pada terminal 1, bukalah program executable C++ dengan mengeti program `yes` dan tekan Enter.
8. Ulangi langkah 7 untuk terminal 2.

   ![App Screenshot](assets/img/p6_8.png)

9. Jendela Top akan menampilkan dua program `yes` sebagai proses yang berjalan. Nilai %CPU sama pada keduanya. Hal ini berarti kedua proses mengkonsumsi waktu proses yang sama dan berjalan sama cepat. PID dari kedua proses akan berbeda, misalnya 2713 dan 2715. Kemudiani gunakan terminal 3 (yang tidak menjalankan primes maupun Jendela Top) dan ketik `renice 19 <PID terminal 1>` (contoh: `renice 19 2713`) dan diikuti Enter. Hal ini berarti mengganti penjadwalan prioritas dari proses ke 19.

   ![App Screenshot](assets/img/p6_9.png)

10. Tunggu beberapa saat sampai program top berubah dan terlihat pada jendela Top. Pada kolom STAT memperlihatkan N untuk proses 2713. Hal ini berarti bahwa penjadwalan prioritas untuk proses 2713 lebih besar (lebih lambat) dari 0. Proses 2715 berjalan lebih cepat.

    ![App Screenshot](assets/img/p6_9.png)

11. Program top juga mempunyai fungsi yang sama dengan program `renice`. Pilih jendela Top dan tekan `r`. Program top terdapat prompt PID to renice: tekan 2713 (ingat bahwa Anda harus mengganti 2713 dengan PID Anda sendiri) dan tekan Enter. Program top memberikan prompt `Renice` PID 2713 to value: tekan -19 dan tekan Enter.

    ![App Screenshot](assets/img/p6_10.png)

    ![App Screenshot](assets/img/p6_11.png)

12. Tunggu beberapa saat sampai top berubah dan lihat nilai %CPU pada kedua proses. Sekarang proses 2713 lebih cepat dari proses 2715. Kolom status menunjukkan penjadwalan prioritas lebih rendah (lebih cepat) dari nilai 0.

    ![App Screenshot](assets/img/p6_12.png)

13. Pilih terminal 3 (yang sedang tidak menjalankan `yes` atau program top) dan ketik `nice -n -10 yes` dan Tekan Enter. Tunggu beberapa saat agar program top berubah dan akan terlihat proses primes ketiga. Misalnya PID nya 2714. Opsi -10 berada pada kolom NI (penjadwalan prioritas).

    ![App Screenshot](assets/img/p6_13.png)

    ![App Screenshot](assets/img/p6_14.png)

14. Jangan menggunakan mouse dan keyboard selama 10 detik. Program top menampilkan proses yang aktif selain program yes. Maka akan terlihat proses top terdaftar tetapi %CPU kecil (dibawah 1.0) dan konsisten. Juga terlihat proses berhubungan dengan dekstop grafis seperti X, panel dll.

    ![App Screenshot](assets/img/p6_15.png)

15. Pindahkan mouse sehingga kursor berubah pada screen dan lihat apa yang terjadi dengan tampilan top. Proses tambahan akan muncul dan nilai %CPU berubah sebagai bagian grafis yang bekerja. Satu alasan adalah bahwa proses 2714 berjalan pada penjadwalan prioritas tinggi. Pilih jendela Top ketik `r`. PID to reniceL muncul prompt. Ketik 2714 (ubahlah 2714 dengan PID Anda) dan tekan Enter. Renice PID 2714 to value: muncul prompt. Ketik 0 dan tekan Enter. Sekarang pindahkan mouse ke sekeliling screen. Lihat perubahannya.

    ![App Screenshot](assets/img/p6_16.png)

    ![App Screenshot](assets/img/p6_17.png)

    ![App Screenshot](assets/img/p6_18.png)

    ![App Screenshot](assets/img/p6_19.png)

16. Tutup semua terminal window.
17. Logout dan login kembali sebagai user.

### Latihan

1. Masuk ke tty2 dengan Ctrl+Alt+F2. Ketik ps –au dan tekan Enter. Kemudian perhatikan keluaran sebagai berikut :

   ![App Screenshot](assets/img/l1_1.png)

   - Sebutkan nama-nama proses yang bukan root

     - Semua proses kecuali `/bin/login -p--` adalah bukan root

   - Tulis PID dan COMMAND dari proses yang paling banyak menggunakan CPU time

     - PID : 4470
     - COMMAND : -bash

   - Sebutkan buyut proses dan PID dari proses tersebut

     - `/usr/libexec/gdm-wayland-session` dengan PID 3059

   - Sebutkan beberapa proses daemon

     - Pada beberapa proses yang tampil pada gambar di atas, tidak ada proses daemon.

   - Pada prompt login lakukan hal- hal sebagai berikut : `$ csh` `$ who` `$ bash` `$ ls` `$ sh` `$ ps`

     ![App Screenshot](assets/img/l1_2.png)

     Analisa :
     Perintah `$ bash` digunakan untuk mengkonversi instruksi yang dimasukkan ke dalam bahasa biner yang dapat di mengerti oleh kernel Linux, perintah `$ ls` digunakan untuk menunjukkan semua file yang ada dalam direktori aktif, dan perintah `$ csh` adalah sebuah shell interaktif yang memiliki lebih banyak sintaks dibandingkan dengan Bourne Shell. PID, TTY, TIME, dan CMD membentuk empat kolom utama tampilan perintah ps, yang menampilkan daftar proses yang sedang berlangsung dalam sistem. Perintah `$ who` menampilkan daftar pengguna yang saat ini masuk ke sistem. Ini menunjukkan nama pengguna, terminal yang mereka gunakan, waktu login, dan informasi lainnya. Perintah ini digunakan dengan sering untuk mengetahui siapa yang sedang menggunakan sistem atau

   - Sebutkan PID yang paling besar dan kemudian buat urut-urutan proses sampai ke PPID = 1.

     ![App Screenshot](assets/img/l1_23.png)

     - PID = 5204 (ps)
     - PID = 5203 (sh)
     - PID = 5200 (bash)
     - PID = 5198 (csh)
     - PID = 4752 (bash)

2. Cobalah format tampilan ps dengan opsi berikut dan perhatikan hasil tampilannya :

   - `-f` daftar penuh

   ![App Screenshot](assets/img/l2_1.png)

   - `-j` format job

   ![App Screenshot](assets/img/l2_2.png)

   - `j` format job control

   ![App Screenshot](assets/img/l2_3.png)

   - `l` daftar memanjang

   ![App Screenshot](assets/img/l2_4.png)

   - `s` format sinyal

   ![App Screenshot](assets/img/l2_5.png)

   - `v` format virtual memory

   ![App Screenshot](assets/img/l2_6.png)

   - `X` format register i386

   ![App Screenshot](assets/img/l2_7.png)

3. Lakukan urutan pekerjaan berikut :

   - Gunakan perintah `find` ke seluruh direktory pada sistem, belokkan output sehingga daftar direktori dialihkan ke file directories.txt dan daftar pesan error dialihkan ke file errors.txt

   ![App Screenshot](assets/img/l3_1.png)

   - Gunakan perintah sleep 5. Apa yang terjadi dengan perintah ini ?

   ![App Screenshot](assets/img/l3_2.png)

   - Jalankan perintah pada background menggunakan &

   ![App Screenshot](assets/img/l3_3.png)

   - Jalankan sleep 15 pada foreground, hentikan sementara dengan Ctrl-Z dan kemudian letakkan pada background dengan bg. Ketikkan jobs. Ketikkan ps. Kembalikan job ke foreground dengan perintah fg.

   ![App Screenshot](assets/img/l3_4.png)

   - Jalankan sleep 15 pada background menggunakan & dan kemudian gunakan perintah kill untuk menghentikan proses diikuti job number.

   ![App Screenshot](assets/img/l3_6.png)

   - Jalankan sleep 15 pada background menggunakan & dan kemudian gunakan kill untuk menghentikan sementara proses. Gunakan bg untuk melanjutkan menjalankan proses.

   ![App Screenshot](assets/img/l3_7.png)

   - Jalankan sleep 60 pada background 5 kali dan terminasi semua pada dengan menggunakan perintah killall.

   ![App Screenshot](assets/img/l3_8.png)

   - Gunakan perintah ps, w dan top untuk menunjukkan semua proses yang sedang dieksekusi.

   ![App Screenshot](assets/img/l3_9.png)

   ![App Screenshot](assets/img/l3_11.png)

   - Gunakan perintah ps –aeH untuk menampilkan hierarki proses. Carilah init proses. Apakah Anda bisa identifikasi sistem daemon yang penting ? Dapatkan Anda identifikasi shell dan subproses ?

   ![App Screenshot](assets/img/l3_12.png)

   ![App Screenshot](assets/img/l3_13.png)

   ![App Screenshot](assets/img/l3_15.png)

   - Kombinasikan ps –fae dan grep, apa yang Anda lihat ?

   ![App Screenshot](assets/img/l3_16.png)

   - Jalankan proses sleep 300 pada background. Log off komputer dan log in kembali. Lihat daftar semua proses yang berjalan. Apa yang terjadi pada proses sleep ?

   ![App Screenshot](assets/img/l3_17.png)

   ![App Screenshot](assets/img/l3_18.png)
