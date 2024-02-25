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

Daftar Isi

1. Pendahuluan.
1. Soal.

Apa itu Sistem Operasi?

Sistem Operasi (OS) adalah perangkat lunak sistem yang bertugas untuk melakukan kontrol dan manajemen terhadap perangkat keras dan operasi-operasi dasar sistem, termasuk menjalankan perangkat lunak aplikasi seperti program-program pengolah kata dan peramban web.

<br>Soal<br>
Sebutkan dan jelaskan proses booting!

1. Power On

   Saat tombol power atau tombol *reset* dihidupkan, sumber daya listrik akan mengalir ke komputer. Kemudian, perangkat keras akan menerima daya untuk dinyalakan.

1. Power-On Self Test (POST)

   Setelah dinyalakan, komputer akan melakukan *Power-On Self-Test* atau POST, yang merupakan serangkaian tes perangkat keras untuk memastikan bahwa semuanya berfungsi dengan baik. POST akan memeriksa RAM, prosesor, kartu grafis, dan perangkat keras lainnya. Jika ada masalah dengan perangkat keras, komputer akan memberikan pesan kesalahan yang sesuai.

1. Inisialisasi Perangkat Keras

   Setelah POST selesai, komputer akan menginisialisasi perangkat keras seperti *hard drive, keyboard, mouse*, dan perangkat lainnya. Proses ini melibatkan tahap mengenali perangkat keras, memuat *driver* yang diperlukan, dan menyiapkan perangkat untuk digunakan.

1. Membaca Sektor Boot

   Selanjutnya, komputer akan mencari sektor *boot* di *hard drive* atau perangkat penyimpanan lainnya. Sektor *boot* adalah area khusus yang berisi instruksi awal untuk memuat sistem operasi.

1. Memuat Sistem Operasi

   Setelah sektor *boot* ditemukan, komputer akan memuat sistem operasi ke dalam memori utama (RAM). Kemudian, sistem operasi akan mengambil alih kendali dan mulai menjalankan program-program yang diperlukan untuk mengoperasikan komputer.

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

   ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.016.jpeg)

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.017.jpeg) Input nama host, lalu klik lanjutkan

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.018.jpeg) Kosongkan nama domain dan klik lanjutkan

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.019.jpeg) Input kata sandi root, lalu klik lanjutkan

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.020.jpeg) Input Nama akun, lalu klik lanjutkan

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.021.jpeg) Input nama pengguna, disarankan huruf kecil semua, lalu klik lanjutkan

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.022.jpeg) Input Password pengguna, lalu klik lanjutkan

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.023.jpeg) Atur waktu tempat anda berada, lalu klik lanjutkan

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.024.jpeg) Pilih ‘manual’ pada halaman metode pemartisian, lalu klik lanjutkan

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.025.jpeg) Pilih opsi ‘ya’ pada halaman pembuat partisi baru

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.026.jpeg) Pilih ‘SCSI2’ pada halaman pemilihan partisi hard disk, lalu klik lanjutkan

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.027.jpeg) Pilih ‘ruang kosong’ yang pertama, lalu klik lanjutkan

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.028.jpeg) Pilih ‘buat partisi baru’ lalu klik lanjutkan

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.029.jpeg) Input 20 GB untuk ukuran partisi pertama, lalu klik lanjutkan

1. ![ref1] Pilih ‘primer’ pada halaman jenis partisi, lalu klik lanjutkan

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.031.jpeg) Pilih ‘awal’ pada lokasi partisi, lalu klik lanjutkan

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.032.jpeg) Double click pada’penanda bisa boot’

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.033.jpeg) Hasilnya akan seperti ini, lalu double klik ‘selesai menyusun partisi’

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.034.jpeg) Pilih ‘ruang kosong’ yang kedua, lalu klik lanjutkan

1. ![ref2] Pilih ‘buat partisi baru’ lalu klik lanjutkan

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.036.jpeg) Input 5 GB untuk ukuran partisi kedua, lalu klik lanjutkan

1. ![ref1] Pilih ‘primer’ pada halaman jenis partisi, lalu klik lanjutkan

1. ![ref3] Pilih ‘awal’ pada lokasi partisi, lalu klik lanjutkan

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.038.jpeg) Double click pada’titik kait’

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.039.jpeg) Ganti ‘/home’ menjadi ‘/storage’, lalu klik lanjutkan

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.040.jpeg) Hasilnya akan seperti ini, lalu double klik ‘selesai menyusun partisi’

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.041.jpeg) Pilih ‘ruang kosong’ yang ketiga, lalu klik lanjutkan

1. ![ref2] Pilih ‘buat partisi baru’ lalu klik lanjutkan

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.042.jpeg) Input 1.5 GB untuk ukuran partisi ketiga, lalu klik lanjutkan

1. ![ref1] Pilih ‘primer’ pada halaman jenis partisi, lalu klik lanjutkan

1. ![ref3] Pilih ‘awal’ pada lokasi partisi, lalu klik lanjutkan

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.043.jpeg) Double click pada’gunakan sebagai’

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.044.jpeg) Pilih ‘ruang swap’ lalu klik lanjutkan

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.045.jpeg) Double click pada’penanda bisa-boot’

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.046.jpeg) Hasilnya akan seperti ini, lalu klik lanjutkan

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.047.jpeg) Pilih ‘selesai mempartisi’ lalu klik lanjutkan

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.048.jpeg) Pilih ‘ya’ pada halaman konfirmasi perubahan

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.049.jpeg) Pada opsi instalasi tambahan pilih ‘tidak’ lalu klik lanjutkan

   ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.050.jpeg)

1. ` `Pada halaman cermin arsip pilih ‘Indonesia’ lalu klik lanjutkan

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.051.jpeg) Pada halaman cermin arsip Debian pilih ‘kebo-pens.ac.id’ lalu klik lanjutkan

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.052.jpeg) Pada halaman proxy kosongkan inputan jika tidak ada, lalu klik lanjutkan

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.053.jpeg) Klik ‘ya’ pada halaman survey penggunaan, lalu klik lanjutkan

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.054.jpeg) Centang seperti di gambar lalu klik lanjutkan

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.055.jpeg) Pilih ‘ya’ pada halaman pasang boot loader lalu klik lanjutkan

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.056.jpeg)Pada halaman pemasangan boot loader pilih ‘/dev/sda….’ Lalu klik lanjutkan

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.057.jpeg) Klik kanjutkan jika instalasi sudah selesai

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.058.jpeg) Pilih ‘debian gnu/linux’ lalu tekan enter

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.059.jpeg)Akan muncul tampilan seperti ini jika selesai

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.060.jpeg) Inputkan password lalu tekan enter

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.061.jpeg)Pilih Bahasa lalu klik selanjutnya

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.062.jpeg)Pada halaman tata letak keyboard pilih sesuai negara anda, lalu klik selanjutnya

1. ![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.063.jpeg)Setelah selesai klik ‘memulai memakai Debian GNU/linux’

1. Tampilan Debian akan seperti ini

![](Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.064.jpeg)

[ref1]: Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.030.jpeg
[ref2]: Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.035.jpeg
[ref3]: Aspose.Words.08797166-63bf-4b2a-8196-cfd0b10822da.037.jpeg

</p>

</div>
