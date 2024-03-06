<div align="center">
    <h1 style="text-align: center;font-weight: bold">Praktikum 2<br>SysOp</h1>
    <h4 style="text-align: center;">Dosen Pengampu : Dr. Ferry Astika Saputra, S.T., M.Sc.</h4>
</div>
<br />
<div align="center">
    <img src="Logo_PENS.png" alt="Logo PENS">
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
3. [Perbedaan Legacy&UEFI](#Perbedaan-Legacy-&-UEFI)
4. [Referensi](#Referensi)

# Pendahuluan
Motherboard adalah papan sirkuit utama yang terdapat di dalam sebuah komputer. Motherboard adalah komponen yang memiliki tugas utama untuk mendistribusikan listrik dan memfasilitasi komunikasi antar perangkat komputer ataupun perangkat periferal. Motherboard menjadi tulang punggung utama proses komunikasi antar perangkat CPU (Central Processing Unit), RAM (Random Access Memory), memori penyimpanan, dan seluruh komponen lain dari perangkat keras komputer. Motherboard dapat ditemukan di hampir semua komputer, terutama desktop PC dan laptop. Komponen komputer yang terhubung di Motherboard antara lain, seperti CPU, memori, GPU, Ethernet Card, dan Audio Card.

Unified Extensible Firmware Interface (UEFI) adalah proses booting pada komputer modern dengan kemampuan lebih canggih dibanding sistem Legacy. UEFI menggunakan firmware URFI untuk menyimpan EFI Service Partitions saat proses booting berlangsung. 
Sementara, Legacy adalah proses booting komputer dengan firmware BIOS yang lebih lama dan tradisional. 

# Komposisi Motherboard
1. *Socket CPU*: Ada ZIF (Zero Insertion Force), LIF (Low Insertion Force), dan AMD Socket A.
<img src="socket CPU.jpeg">

2. *BIOS (Basic Input-Output System)*: Program dasar yang menghubungkan motherboard dengan sistem operasi.
<img src="BIOS.jpg">

3. *North Bridge Controller*: Menghubungkan slot RAM, AGP, dan socket CPU.
<img src="nourth south.PNG">

4. *South Bridge Controller*: Mengatur peripheral seperti USB, keyboard, IDE controller, dll.
<img src="nourth south.PNG">

5. *Konektor Power Supply Unit*: Menyambungkan motherboard dengan power supply, AT atau ATX.
<img src="konektor powersupply.jpeg">

6. *Slot RAM*: Tempat meletakkan RAM, saat ini menggunakan tipe DDR3.
<img src="slot RAM.jpeg">

7. *Slot PCI*: Tempat untuk Add-on Card seperti LAN, sound, dan TV Tuner.
<img src="slot PCI.jpeg">

8. *Slot AGP (Accelerated Graphics Port)*: Untuk AGP Card yang menampilkan grafis.
<img src="slot AGP.jpeg">

9. *Slot IDE dan SATA*: IDE untuk harddisk atau floppy disk, SATA untuk serial ATA.
<img src="IDE SATA.jpeg">

10. *CMOS (Complementary Metal Oxide Semiconductor)*: Baterai yang memberi daya pada memori untuk pengaturan
konfigurasi.
<img src="CMOS.jpeg">

# Perbedaan Legacy&UEFI

<img src="UEFI-vs-Legacy.png">

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
  
[Legacy & UEFI](https://kumparan.com/how-to-tekno/perbedaan-uefi-dan-legacy-simak-penjelasannya-di-sini-20b8sBrgRs4/3)
  
[Foto Legacy & UEFI](https://qwords.com/blog/apa-itu-uefi-dan-legacy/)

