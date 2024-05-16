<div align="center">
  <h2 style="text-align: center;font-weight: bold">LAPORAN PRAKTIKUM * SISTEM OPERASI</br></h2>
  <h4 style="text-align: center;">Dosen Pengampu : Dr. Ferry Astika Saputra, S.T., M.Sc.</h4>
</div>
<br />
<div align="center">
  <img src="https://upload.wikimedia.org/wikipedia/id/4/44/Logo_PENS.png" alt="Logo PENS">
  <h3 style="text-align: center;">Disusun Oleh : <br>Danur Isa Prabutama</h3>

<h3 style="text-align: center;line-height: 1.5">Politeknik Elektronika Negeri Surabaya<br>Departemen Teknik Informatika Dan Komputer<br>Program Studi Teknik Informatika<br>2024/2025</h3>
  <hr><hr>
</div>

# Threads
- ## Apa itu threads
    Menurut Gabriel Ramuglia dalam artikelnya, "What are CPU threads? Cores Vs Threads Explained." Thread adalah urutan instruksi yang diberikan ke CPU, dan teknik threading seperti multithreading dan hyperthreading dapat meningkatkan kinerja. Dalam istilah sistem operasi, thread adalah unit eksekusi terkecil dalam sebuah proses, yang memungkinkan beberapa tugas dilakukan secara bersamaan oleh CPU.
    
    #### Analogi Threads
    Bayangkan Anda memiliki sebuah restoran. Restoran ini bisa dianggap sebagai proses. Di dalam restoran tersebut, ada beberapa pelayan yang bekerja untuk melayani pelanggan. Setiap pelayan adalah seperti sebuah thread. Mari kita lihat bagaimana analogi ini dapat menjelaskan konsep threads:

    - Berbagi Sumber Daya:
        Memori dan Sumber Daya Lain: Seperti pelayan yang bekerja di restoran yang sama dan berbagi peralatan dapur, meja, dan kursi, threads berbagi memori dan sumber daya lain dalam proses yang sama. Mereka dapat mengakses data yang sama dan menggunakan sumber daya yang sama.<br><br>

    - Eksekusi Mandiri:
        Tugas Terpisah: Setiap pelayan dapat melayani pelanggan berbeda pada waktu yang sama. Misalnya, satu pelayan mungkin mengambil pesanan dari satu meja, sementara yang lain menyajikan makanan ke meja lain. Demikian juga, threads dapat melakukan tugas yang berbeda secara simultan dalam satu proses.<br><br>

    - Konkurrensi:
        Bekerja Secara Bersamaan: Jika ada banyak pelanggan, memiliki beberapa pelayan (threads) memungkinkan restoran untuk melayani lebih banyak pelanggan secara lebih efisien. Dalam pemrograman, threads memungkinkan program untuk menangani banyak tugas secara bersamaan, seperti membaca data dari disk sambil memproses data lain di memori.<br><br>

    - Koordinasi dan Sinkronisasi:
        Koordinasi Tugas: Meskipun setiap pelayan bekerja secara mandiri, mereka harus berkoordinasi untuk memastikan pelayanan berjalan lancar dan tidak ada yang tertinggal. Demikian pula, threads dalam sebuah proses perlu disinkronisasi untuk menghindari konflik dan memastikan integritas data.

        

        #### Manfaat Threads

        Menurut IBM dalam artikelnya, "Benefits of threads." Program multithreaded dapat meningkatkan kinerja dibandingkan dengan program paralel tradisional yang menggunakan banyak proses. Peningkatan kinerja lebih lanjut dapat diperoleh pada sistem multiprosesor yang menggunakan threads.

    - Pengelolaan Threads

        Mengelola threads, yaitu membuat dan mengontrol eksekusinya, memerlukan lebih sedikit sumber daya sistem dibandingkan dengan mengelola proses. Membuat thread hanya memerlukan alokasi area data pribadi thread, biasanya 64 KB, dan dua panggilan sistem. Membuat proses jauh lebih mahal karena seluruh ruang alamat proses induk harus diduplikasi.

        API pustaka threads juga lebih mudah digunakan dibandingkan dengan pustaka untuk mengelola proses. Membuat thread hanya memerlukan subrutin pthread_create.<br><br>

    - Komunikasi Antar-Thread

        Komunikasi antar-thread jauh lebih efisien dan lebih mudah digunakan dibandingkan komunikasi antar-proses. Karena semua thread dalam satu proses berbagi ruang alamat yang sama, mereka tidak perlu menggunakan memori bersama. Lindungi data bersama dari akses bersamaan dengan menggunakan mutex atau alat sinkronisasi lainnya.

        Fasilitas sinkronisasi yang disediakan oleh pustaka threads memudahkan implementasi alat sinkronisasi yang fleksibel dan kuat. Alat ini dapat menggantikan fasilitas komunikasi antar-proses tradisional, seperti antrean pesan. Pipes dapat digunakan sebagai jalur komunikasi antar-thread.<br><br>

    - Sistem Multiprosesor

        Pada sistem multiprosesor, beberapa threads dapat berjalan secara bersamaan pada beberapa CPU. Oleh karena itu, program multithreaded dapat berjalan lebih cepat dibandingkan dengan sistem uniprosesor. Mereka juga bisa lebih cepat dibandingkan dengan program yang menggunakan banyak proses karena threads memerlukan sumber daya yang lebih sedikit dan menghasilkan overhead yang lebih kecil. Misalnya, pergantian threads dalam proses yang sama bisa lebih cepat, terutama dalam model perpustakaan M:N di mana pergantian konteks sering dapat dihindari. Keuntungan utama menggunakan threads adalah bahwa program multithreaded tunggal akan bekerja pada sistem uniprosesor, tetapi dapat secara alami memanfaatkan sistem multiprosesor tanpa perlu dikompilasi ulang.<br><br>
    
    - Keterbatasan

        Pemrograman multithreaded berguna untuk mengimplementasikan algoritma paralel menggunakan beberapa entitas independen. Namun, ada beberapa kasus di mana beberapa proses harus digunakan daripada beberapa threads.

        Banyak pengenal sistem operasi, sumber daya, status, atau keterbatasan ditentukan pada tingkat proses dan, dengan demikian, dibagikan oleh semua thread dalam proses. Misalnya, ID pengguna dan grup serta izin terkait ditangani pada tingkat proses. Program yang perlu menetapkan ID pengguna berbeda untuk entitas pemrogramannya perlu menggunakan beberapa proses, bukan proses multithreaded tunggal. Contoh lainnya termasuk atribut sistem file, seperti direktori kerja saat ini, dan status serta jumlah maksimum file terbuka. Program multithreaded mungkin tidak sesuai jika atribut ini lebih baik ditangani secara independen. Misalnya, program multi-proses dapat membiarkan setiap proses membuka sejumlah besar file tanpa gangguan dari proses lain.<br><br>


- ## Apa itu threads
        