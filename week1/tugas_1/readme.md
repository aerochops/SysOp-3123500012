<div style="text-align:center">
    <h1>Tugas 1<br>Sistem Informasi</h1>

<p>Dosen Pengampu : Dr. Ferry Astika, S.T., M.Sc.</p>

![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/Logo_PENS.png?raw=true)

</div>

<div style="text-align:center">

<p>
Disusun oleh :

Achmad Risel Araby (3123500025)<br>
Danur Isa Prabutama (3123500023)<br>
Fikri Athanabil Efendi (31235000)<br>

Politeknik Elektronika Negeri Surabaya<br>
Departemen Teknik Informatika dan Komputer<br>
Program Studi Teknik Informatika<br>
2023/2024

</p>

</div>

<div>

<p>

### Pengertian Sistem Operasi?

Sistem operasi adalah salah satu perangkat lunak paling kompleks, didalamnya terdapat Kernel yang mengabstraksi fitur-fitur yang disediakan oleh perangkat keras komputer.Peran Sistem Operasi menjadikan fitur-fitur tersebut lebih aman dan nyaman untuk digunakan.

istilah "sistem operasi" biasanya mengacu pada perangkat lunak yang menyediakan antarmuka antara pengguna dan perangkat keras sistem komputer.Sebagai antarmuka antara pengguna dan perangkat keras, sistem operasi harus dirancang dengan mempertimbangkan kebutuhan pengguna serta kendala dan peluang teknologi.

### Soal

#### Sebutkan dan jelaskan proses booting Komputer!

## Apa itu Proses Booting?

Apa itu booting di OS? Di bagian ini, kita akan mendefinisikan booting di sistem operasi. Saat kita menyalakan komputer, perangkat menerima daya dan diinisialisasi. Pada tahap ini, memori utama, atau RAM, kosong. Untuk memulai sistem, sekumpulan kecil instruksi yang disimpan dalam memori read-only (ROM) dikirim ke unit pemrosesan pusat (CPU) untuk dieksekusi. Petunjuk ini membantu memeriksa komponen perangkat keras dan mengidentifikasi potensi masalah. Jika ada masalah perangkat keras, bunyi bip atau notifikasi di layar mengingatkan kita.

Setelah pemeriksaan perangkat keras selesai, proses booting sistem operasi dimulai. Sistem operasi dimuat, memungkinkan komputer berfungsi dengan baik dan menerima perintah pengguna.Proses booting di OS sangat penting untuk pengoperasian komputer yang memadai dan pelaksanaan berbagai aplikasi perangkat lunak.
booting pada komputer

## Jenis Proses Booting

### 1. Cold Booting

<img src="./media/cold.jpg"
style="width:300px; object-fit: cover;"/>

Menyalakan komputer untuk pertama kalinya atau setelah komputer dimatikan sepenuhnya. Saat kita menekan tombol daya untuk memulai cold boot, komputer membaca instruksi Basic Input/Output System (BIOS) yang disimpan di ROM. Instruksi ini memandu sistem dalam memuat sistem operasi ke dalam memori utama. Dibandingkan dengan Warm booting, booting dingin membutuhkan waktu lebih lama karena melibatkan startup sistem yang lengkap.

### 2. Warm Booting

<img src="./media/warm.png"
style="width:200px; object-fit: cover; padding: 50px; background-color: white;"/>

Warm boot, atau reboot, terjadi saat komputer dihidupkan ulang saat dihidupkan. Jenis booting ini biasanya dilakukan ketika sistem hang atau menjadi tidak responsif. Warm booting dapat dimulai melalui perangkat keras, seperti menekan tombol reset, atau perintah perangkat lunak, seperti Ctrl+Alt+Del. Seringkali perlu melakukan boot hangat setelah menginstal perangkat lunak atau perangkat keras baru untuk menerapkan perubahan konfigurasi dan memastikan fungsionalitas sistem yang tepat.

#### \* Untuk langkah langkah dari proses booting sistem operasi bisa di lihat di bawah ini:

### 1. Memuat BIOS

<img src="./media/step1.png"
style="width:5.48945in;height:2.54825in"/>
<img src="./media/step1.2.png"
style="width:5.48945in;height:2.54825in"/>

Saat kita menyalakan power, langkah pertama dalam proses booting adalah memuat BIOS. Power supply menyediakan listrik ke komponen penting, termasuk prosesor dan BIOS.

### 2. Power-On Self Test (POST)

<img src="./media/step2.png"
style="width:5.48945in;height:2.54825in"/>

Setelah memuat BIOS, ia melakukan Power on Self-Test (POST). Tes ini memeriksa memori utama komputer, drive disk, perangkat input/output, dan komponen perangkat keras lainnya. Jika kesalahan terdeteksi selama pengujian, sistem akan mengeluarkan bunyi bip atau menampilkan notifikasi di layar untuk mengingatkan pengguna.

### 3. Memuat Sistem Operasi

<img src="./media/step3.png"
style="width:5.48945in;height:2.54825in"/>

Setelah POST berhasil diselesaikan, BIOS membaca urutan bootable yang disimpan dalam CMOS (Common Metal Oxide Semiconductor). Berdasarkan urutan bootable, BIOS mencari Master Boot Record (MBR) pada perangkat yang dapat di-boot seperti floppy disk, CD-ROM, dan hard disk.
Jika MBR tidak ditemukan pada perangkat yang dapat di-boot, sistem akan menampilkan pesan yang mengatakan "Tidak Ada Perangkat Booting Ditemukan" dan crash. Namun, jika MBR ditemukan, BIOS meluncurkan boot loader, perangkat lunak aplikasi khusus yang memuat sistem operasi.

### 4. Konfigurasi Sistem

<img src="./media/step4.png"
style="width:5.48945in;height:2.54825in"/>

Setelah sistem operasi dimuat, driver perangkat dimuat ke dalam memori untuk memastikan pengoperasian komponen perangkat keras komputer dengan benar. Driver perangkat ini bertindak sebagai perantara antara sistem operasi dan perangkat keras, memungkinkan keduanya berkomunikasi secara efektif.

### 5. Memuat Utilitas Sistem

<img src="./media/step5.jpg"
style="width:5.48945in;height:2.54825in"/>

Pada langkah ini, proses booting dalam sistem operasi melibatkan pemuatan utilitas sistem ke dalam memori. Utilitas sistem, seperti perangkat lunak antivirus dan kontrol volume, merupakan alat penting yang meningkatkan fungsionalitas dan keamanan sistem operasi.

### 6. Autentikasi Pengguna

<img src="./media/step6.png"
style="width:5.48945in;height:2.54825in"/>

Jika ada otentikasi pengguna yang dikonfigurasi, sistem akan meminta pengguna untuk memasukkan kredensial mereka. Setelah sistem menerima kredensial yang valid, sistem biasanya meluncurkan shell antarmuka pengguna grafis (GUI) atau shell antarmuka baris perintah (CLI), yang memberikan akses pengguna ke sumber daya dan aplikasi sistem.

Enam langkah ini memastikan sistem operasi komputer dimuat dengan benar dan siap digunakan. Dengan memahami proses booting, kita mendapatkan wawasan tentang rangkaian kejadian rumit di balik layar saat kita menghidupkan komputer.

### Referensi

    - Richard R. Muntz. 1974 June, Operating Systems. https://ieeexplore.ieee.org/document/6323579

    - James Mickens. 2021, Operating Systems. https://read.seas.harvard.edu/cs161/2021/

    - Vibha Gupta. 2003 September 6, Booting in Operating  System (OS): Types, Steps and Process.
      https://www.almabetter.com/bytes/articles/booting-in-operating-system

    - Sunbul. 2023 December 7, Computing System. https://www.redswitches.com/blog/uefi-vs-bios/#what-is-bios

    - geeksforgeeks.org. 2023 July 26, What is a Motherboard?. https://www.geeksforgeeks.org/what-is-a-motherboard/

</p>

<p>

<br>Bagaimana cara install Linux Debian di Virtual Box?

1. Download Virtual Box di <https://bit.ly/49DpHxO>, pilih sesuai system operasi yang kalian gunakan.

   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/Download%20virtual%20box.png?raw=true)

1. Download Debian di https://bit.ly/48sH03m

   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/Download%20Debian.png?raw=true)

1. Buka Virtual Box, lalu klik tombol New

   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/Tampilan%20awal%20virtual%20box.png?raw=true)

1. Masukkan nama virtual machine, tentukan folder penyimpanan untuk virtual machine, dan pilih file iso Debian yang telah kita download. Kemudian klik tombol next.

   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/Screenshot%202024-02-22%20150942.png?raw=true)

1. Tentukan base memory (RAM) dan jumlah core CPU yang ingin anda gunakan, dan centang tulisan _Enable EFI,_ lalu klik tombol next.

   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/1.%20Virtual%20Machine%20Name.png?raw=true)

1. Tentukan Virtual Hard Disk yang akan digunakan, lalu klik tombol next.

   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/2.%20Virtual%20Hard%20Disk.png?raw=true)

1. Lalu akan moncul gambar seperti berikut, lalu klik tombol finish.

   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/3.%20Summary.png?raw=true)

1. Pilih virtual machine yang telah kita buat tadi, lalu klik tombol start di kanan atas.
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/4.%20Menu%20Virtual%20Box.png?raw=true)

1. Pilih Graphical Install, lalu klik enter.

   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/5.%20tampilanawaldebian.jpg?raw=true)

1. ` `Pilih Bahasa yang ingin kita gunakan, lalu klik tombol continue.
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/6.%20Pilih%20lokasi.jpeg?raw=true)
1. ` `Pilih lokasi kalian, sebagai contoh saya pilih other, kemudian Asia, dan pilih Indonesia. Lalu klik continue.

   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/7.%20Pilih%20bahasa.jpeg?raw=true)

1. ` `Pilih konfigurasi lokasi, lalu klik continue.

   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/7.%20Pilih%20bahasa.jpeg?raw=true)

1. ` `Pilih konfigurasi keyboard, lalu klik continue.

   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/8.%20Pengaturan%20keyboard.jpeg?raw=true)

1. ` `Tunggu proses loading hingga selesai.

   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/proses%20loading.png?raw=true)

1. Input nama host, lalu klik lanjutkan
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/9.%20Input%20nama%20host.jpeg?raw=true)

1. Kosongkan nama domain dan klik lanjutkan
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/10.%20Input%20domain.jpeg?raw=true)

1. Input kata sandi root, lalu klik lanjutkan
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/11.%20Kata%20sandi%20root.jpeg?raw=true)

1. Input Nama akun, lalu klik lanjutkan
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/12.%20Nama%20akun.jpeg?raw=true)

1. Input nama pengguna, disarankan huruf kecil semua, lalu klik lanjutkan
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/13.%20Nama%20pengguna.jpeg?raw=true)

1. Input Password pengguna, lalu klik lanjutkan
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/14.%20Password%20pengguna.jpeg?raw=true)

1. Atur waktu tempat anda berada, lalu klik lanjutkan
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/15.%20Mengatur%20waktu.jpeg?raw=true)

1. Pilih ‘manual’ pada halaman metode pemartisian, lalu klik lanjutkan
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/16.%20Metode%20pemartisian.jpeg?raw=true)

1. Pilih opsi ‘ya’ pada halaman pembuat partisi baru
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/17.%20Opsi%20buat%20partisi%20baru.jpeg?raw=true)

1. Pilih ‘SCSI2’ pada halaman pemilihan partisi hard disk, lalu klik lanjutkan
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/18.%20Pemilihan%20partisi.jpeg?raw=true)

1. Pilih ‘ruang kosong’ yang pertama, lalu klik lanjutkan
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/19.%20Pemilihan%20partisi%20HD_1.jpeg?raw=true)

1. Pilih ‘buat partisi baru’ lalu klik lanjutkan
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/20.%20Pembuatan%20partisi%20HD_1.jpeg?raw=true)

1. Input 20 GB untuk ukuran partisi pertama, lalu klik lanjutkan
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/21.%20Ukuran%20partisi%20HD_1.jpeg?raw=true)

1. Pilih ‘primer’ pada halaman jenis partisi, lalu klik lanjutkan
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/22.%20Jenis%20partisi%20HD_1.jpeg?raw=true)

1. Pilih ‘awal’ pada lokasi partisi, lalu klik lanjutkan
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/23.%20Lokasi%20partisi%20HD_1.jpeg?raw=true)

1. Double click pada’penanda bisa boot’
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/24.%20Penyusunan%20partisi%20HD_1%20II.jpeg?raw=true)

1. Hasilnya akan seperti ini, lalu double klik ‘selesai menyusun partisi’
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/25.%20Penyusunan%20partisi%20HD_1%20III.jpeg?raw=true)

1. Pilih ‘ruang kosong’ yang kedua, lalu klik lanjutkan
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/26.%20Pemilihan%20partisi%20HD_2.jpeg?raw=true)

1. Pilih ‘buat partisi baru’ lalu klik lanjutkan
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/27.%20Pembuatan%20partisi%20HD_2.jpeg?raw=true)

1. Input 5 GB untuk ukuran partisi kedua, lalu klik lanjutkan
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/28.%20Ukuran%20partisi%20HD_2.jpeg?raw=true)

1. Pilih ‘primer’ pada halaman jenis partisi, lalu klik lanjutkan
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/29.%20Jenis%20partisi%20HD_2.jpeg?raw=true)

1. Pilih ‘awal’ pada lokasi partisi, lalu klik lanjutkan
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/30.%20Lokasi%20partisi%20HD_2.jpeg?raw=true)

1. Double click pada’titik kait’
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/31.%20Penyusunan%20partisi%20HD_2%20I.jpeg?raw=true)

1. Ganti ‘/home’ menjadi ‘/storage’, lalu klik lanjutkan
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/32.%20Penyusunan%20partisi%20HD_2%20II.jpeg?raw=true)

1. Hasilnya akan seperti ini, lalu double klik ‘selesai menyusun partisi’
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/33.%20Penyusunan%20partisi%20HD_2%20III.jpeg?raw=true)

1. Pilih ‘ruang kosong’ yang ketiga, lalu klik lanjutkan
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/34.%20Pemilihan%20partisi%20HD_3.jpeg?raw=true)

1. Pilih ‘buat partisi baru’ lalu klik lanjutkan
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/35.%20Pembuatan%20partisi%20HD_3.jpeg?raw=true)

1. Input 1.5 GB untuk ukuran partisi ketiga, lalu klik lanjutkan
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/36.%20Ukuran%20partisi%20HD_3.jpeg?raw=true)

1. Pilih ‘primer’ pada halaman jenis partisi, lalu klik lanjutkan
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/37.%20Jenis%20partisi%20HD_3.jpeg?raw=true)

1. Pilih ‘awal’ pada lokasi partisi, lalu klik lanjutkan
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/38.%20Lokasi%20partisi%20HD_3.jpeg?raw=true)

1. Double click pada’gunakan sebagai’
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/39.%20Penyusunan%20partisi%20HD_3%20I.jpeg?raw=true)

1. Pilih ‘ruang swap’ lalu klik lanjutkan
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/40.%20Penyusunan%20partisi%20HD_3%20II.jpeg?raw=true)

1. Double click pada’penanda bisa-boot’
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/41.%20Penyusunan%20partisi%20HD_3%20III.jpeg?raw=true)

1. Hasilnya akan seperti ini, lalu klik lanjutkan
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/42.%20Penyusunan%20partisi%20HD_3%20IV.jpeg?raw=true)

1. Pilih ‘selesai mempartisi’ lalu klik lanjutkan
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/43.%20Selesai%20mempartisi.jpeg?raw=true)

1. Pilih ‘ya’ pada halaman konfirmasi perubahan
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/44.%20Konfirmasi%20perubahan.jpeg?raw=true)

1. Pada opsi instalasi tambahan pilih ‘tidak’ lalu klik lanjutkan
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/45.%20opsi%20instlasi%20tambahan.jpeg?raw=true)

1. Pada halaman cermin arsip pilih ‘Indonesia’ lalu klik lanjutkan
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/46.%20Opsi%20cermin%20arsip.jpeg?raw=true)

1. Pada halaman cermin arsip Debian pilih ‘kebo-pens.ac.id’ lalu klik lanjutkan
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/47.%20Cermin%20arsip%20debian.jpeg?raw=true)

1. Pada halaman proxy kosongkan inputan jika tidak ada, lalu klik lanjutkan
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/48.%20Alamat%20proxy.jpeg?raw=true)

1. Klik ‘ya’ pada halaman survey penggunaan, lalu klik lanjutkan
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/49.%20Opsi%20survey.jpeg?raw=true)

1. Centang seperti di gambar lalu klik lanjutkan
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/50.%20Opsi%20pemilihan%20perangkat.jpeg?raw=true)

1. Pilih ‘ya’ pada halaman pasang boot loader lalu klik lanjutkan
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/51.%20Opsi%20pasang%20boot%20loader.jpeg?raw=true)

1. Pada halaman pemasangan boot loader pilih ‘/dev/sda….’ Lalu klik lanjutkan
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/52.%20Opsi%20piranti%20pemasangan%20boot%20loader.jpeg?raw=true)

1. Klik kanjutkan jika instalasi sudah selesai
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/53.%20Boot%20ulang.jpeg?raw=true)

1. Pilih ‘debian gnu/linux’ lalu tekan enter
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/54.%20Opsi%20running.jpeg?raw=true)

1. Akan muncul tampilan seperti ini jika selesai
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/55.%20Foto.jpeg?raw=true)

1. Inputkan password lalu tekan enter
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/56.%20Tampilan%20awal%20debian.jpeg?raw=true)

1. Pilih Bahasa lalu klik selanjutnya
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/58.%20Pilih%20bahasa.jpeg?raw=true)

1. Pada halaman tata letak keyboard pilih sesuai negara anda, lalu klik selanjutnya
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/59.%20opsi%20tata%20letak%20keyboard.jpeg?raw=true)

1. Setelah selesai klik ‘memulai memakai Debian GNU/linux’
   ![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/62.%20konfirmasi.jpeg?raw=true)

1. Tampilan Debian akan seperti ini

![App Screenshot](https://github.com/aerochops/Tugas_1/blob/main/Img/63.%20Tampilan%20debian.jpeg?raw=true)

</p>

</div>
