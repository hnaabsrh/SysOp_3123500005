<div align="center">
    <h1 style="text-align: center;font-weight: bold">Praktikum 2<br>SysOp</h1>
    <h4 style="text-align: center;">Dosen Pengampu : Dr. Ferry Astika Saputra, S.T., M.Sc.</h4>
</div>
<br />
<div align="center">
    <img src="Assets/Logo_PENS.png" alt="Logo PENS">
    <h3 style="text-align: center;">Disusun Oleh : </h3>
    <p style="text-align: center;">
        <strong>Roihanah Inayati Bashiroh (3123500005)</strong><br>
        <strong>Dio Ramadhan Widya Pamungkas (3123500011)</strong><br>
        <strong>Ragil Ridho Saputra (3122500016)</strong>
    </p>

<h3>Politeknik Elektronika Negeri Surabaya<br>Departemen Teknik
Informatika Dan Komputer<br>Program Studi Teknik Informatika<br>2023/2024</h3>
    <hr>
    <hr>
</div>

## Daftar Isi
1. [Pendahuluan](#Pendahuluan)
2. [Komposisi Motherboard](#Komposisi-Motherboard)
3. [Perbedaan Legacy UEFI](#Perbedaan-Legacy-UEFI)
4. [Referensi](#Referensi)

# Pendahuluan
Motherboard adalah papan sirkuit utama yang terdapat di dalam sebuah komputer. Motherboard adalah komponen yang memiliki tugas utama untuk mendistribusikan listrik dan memfasilitasi komunikasi antar perangkat komputer ataupun perangkat periferal. Motherboard menjadi tulang punggung utama proses komunikasi antar perangkat CPU (Central Processing Unit), RAM (Random Access Memory), memori penyimpanan, dan seluruh komponen lain dari perangkat keras komputer. Motherboard dapat ditemukan di hampir semua komputer, terutama desktop PC dan laptop. Komponen komputer yang terhubung di Motherboard antara lain, seperti CPU, memori, GPU, Ethernet Card, dan Audio Card.

Unified Extensible Firmware Interface (UEFI) adalah proses booting pada komputer modern dengan kemampuan lebih canggih dibanding sistem Legacy. UEFI menggunakan firmware URFI untuk menyimpan EFI Service Partitions saat proses booting berlangsung. 
Sementara, Legacy adalah proses booting komputer dengan firmware BIOS yang lebih lama dan tradisional. 

# Komposisi Motherboard
Motherboard adalah wadah dari berbagai komponen elektronik yang saling terjalin untuk membuat perangkat PC bekerja. Pada motherboard terdapat chip BIOS atau program penggerak dan konektor yang digunakan untuk menghubungkan setiap perangkat. Motherboard memiliki fungsi utama sebagai pusat penghubung antar perangkat yang terpasang pada sebuah PC. Antara motherboard dan bagian-bagiannya dapat menghubungkan kode-kode yang akan difungsikan menjadi sebuah kinerja pada perangkat komputer.

Motherboard memiliki beberapa bagian sebagai berikut:
1. *Socket CPU*: Ada ZIF (Zero Insertion Force), LIF (Low Insertion Force), dan AMD Socket A.
<img src="Assets/socket CPU.jpeg">

2. *BIOS (Basic Input-Output System)*: Program dasar yang menghubungkan motherboard dengan sistem operasi.
<img src="Assets/BIOS.jpg">

3. *North Bridge Controller*: Menghubungkan slot RAM, AGP, dan socket CPU.
<img src="Assets/nourth south.PNG">

4. *South Bridge Controller*: Mengatur peripheral seperti USB, keyboard, IDE controller, dll.
<img src="Assets/nourth south.PNG">

5. *Konektor Power Supply Unit*: Menyambungkan motherboard dengan power supply, AT atau ATX.
<img src="Assets/konektor powersupply.jpeg">

6. *Slot RAM*: Tempat meletakkan RAM, saat ini menggunakan tipe DDR3.
<img src="Assets/slot RAM.jpeg">

7. *Slot PCI*: Tempat untuk Add-on Card seperti LAN, sound, dan TV Tuner.
<img src="Assets/slot PCI.jpeg">

8. *Slot AGP (Accelerated Graphics Port)*: Untuk AGP Card yang menampilkan grafis.
<img src="Assets/slot AGP.jpeg">

9. *Slot IDE dan SATA*: IDE untuk harddisk atau floppy disk, SATA untuk serial ATA.
<img src="Assets/IDE SATA.jpeg">

10. *CMOS (Complementary Metal Oxide Semiconductor)*: Baterai yang memberi daya pada memori untuk pengaturan
konfigurasi.
<img src="Assets/CMOS.jpeg">

# Perbedaan Legacy UEFI

<img src="Assets/UEFI-vs-Legacy.png"><br>
<img src="Assets/uefidanlegacy.png">


Dalam hal proses booting, perbedaan signifikan antara BIOS Legacy dan UEFI terletak pada cara mereka memulai sistem. Berikut adalah perbedaan utama dalam proses booting keduanya:

1. **BIOS Legacy:**
   - Proses booting dimulai dengan POST (Power-On Self Test), yang menguji perangkat keras sistem untuk memastikan semuanya berfungsi dengan baik.
   - Setelah itu, BIOS akan mencari perangkat boot yang diprioritaskan dalam urutan yang telah ditentukan (biasanya hard drive atau CD-ROM) dan mencoba untuk mem-boot dari perangkat tersebut.
   - BIOS Legacy menggunakan MBR (Master Boot Record) sebagai metode partisi dasar, yang memiliki batasan dalam ukuran partisi dan jumlah partisi yang bisa didukung.

2. **UEFI:**
   - Proses booting dimulai dengan inisialisasi firmware UEFI, yang menyediakan antarmuka grafis dan lebih banyak opsi konfigurasi.
   - UEFI memuat driver dan aplikasi yang diperlukan langsung dari sistem file yang terdapat dalam partisi EFI (Extensible Firmware Interface).
   - UEFI mendukung partisi GPT (GUID Partition Table), yang memungkinkan lebih banyak partisi dan ukuran partisi yang lebih besar daripada MBR.
   - UEFI dapat memanfaatkan Secure Boot untuk memverifikasi keaslian firmware dan perangkat lunak yang di-boot, meningkatkan keamanan sistem.

Dengan demikian, perbedaan signifikan dalam proses booting antara BIOS Legacy dan UEFI terletak pada cara mereka menginisialisasi sistem dan memuat sistem operasi, dengan UEFI menawarkan antarmuka yang lebih modern dan fleksibel serta kemampuan untuk bekerja dengan partisi yang lebih besar dan lebih banyak.

Dan berikut adalah perbedaan utama Legacy dan UEFI :

1. Definisi
Unified Extensible Firmware Interface (UEFI) adalah proses booting pada komputer modern dengan kemampuan lebih canggih
dibanding sistem Legacy. UEFI menggunakan firmware URFI untuk menyimpan EFI Service Partitions saat proses booting
berlangsung.
Sementara, Legacy adalah proses booting komputer dengan firmware BIOS yang lebih lama dan tradisional.
2. Waktu yang Dibutuhkan
UEFI membutuhkan waktu booting yang lebih cepat. Sedangkan, Legacy lebih lama.
3. Dukungan untuk Penyimpanan
UEFI sudah menggunakan partisi GUID Partition Table (GTP), sehingga dapat mendukung perangkat penyimpanan hingga 9
zettabytes.
Legacy yang masih menggunakan dukungan Master Boot Record (MBR) dapat mendukung perangkat penyimpanan komputer hanya 2
TB.
4. Keamanan
UEFI dapat mencegah pemuatan aplikasi yang tak sah atau dicurigai. Selain itu juga dapat menghambat adanya kerja dua
boot karena UEFI menganggap sistem operasi adalah aplikasi.
ADVERTISEMENT
Namun, pada Legacy, tak ada keamanan yang disediakan saat booting berlangsung, sehingga ada kemungkinan aplikasi tak sah
dimuat serta terjadi dual-boot.

# Referensi
[Motherboard](https://tekno.kompas.com/read/2023/11/12/17150087/pengertian-motherboard-lengkap-dengan-fungsi-komponen-cara-kerja-dan-jenisnya?page=all#google_vignette)

[Komposisi Motherboard](https://www.baktikominfo.id/id/informasi/pengetahuan/fungsi_motherboard_beserta_bagian-bagiannya_untuk_memaksimalkan_kinerja_komputer-751)
  
[Legacy & UEFI](https://kumparan.com/how-to-tekno/perbedaan-uefi-dan-legacy-simak-penjelasannya-di-sini-20b8sBrgRs4/3)
  
[Foto Legacy & UEFI](https://qwords.com/blog/apa-itu-uefi-dan-legacy/)

