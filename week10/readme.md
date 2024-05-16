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
        Koordinasi Tugas: Meskipun setiap pelayan bekerja secara mandiri, mereka harus berkoordinasi untuk memastikan pelayanan berjalan lancar dan tidak ada yang tertinggal. Demikian pula, threads dalam sebuah proses perlu disinkronisasi untuk menghindari konflik dan memastikan integritas data.<br><br>
        ![App Screenshot](https://github.com/aerochops/SysOp-3123500012/blob/main/week10/Media/Screenshot%202024-05-16%20084636.png?raw=true)



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


- ## Multicore Programming
    Menurut MathWorks dalam artikelnya, "Concepts in Multicore Programming." Sistem prosesor multicore adalah prosesor tunggal dengan beberapa inti eksekusi dalam satu chip. Sebaliknya, sistem multiprosesor memiliki beberapa prosesor pada motherboard atau chip. Sistem multiprosesor dapat mencakup Field-Programmable Gate Array (FPGA). FPGA adalah sirkuit terintegrasi yang berisi susunan blok logika yang dapat diprogram dan hierarki interkoneksi yang dapat dikonfigurasi ulang. Node pemrosesan memproses data input untuk menghasilkan output. Ini bisa berupa prosesor dalam sistem multicore atau multiprosesor, atau FPGA.

    - ### Jenis-jenis Paralelisme<hr>
        Konsep pemrograman multicore adalah memiliki beberapa tugas sistem yang dijalankan secara paralel. Jenis paralelisme meliputi:

            > Paralelisme data(Data Parallelism)

            > Paralelisme tugas(Task parallelism)

            > Pipelining(Pipelining)

        - ### Paralelisme data(Data Parallelism)
            Paralelisme data melibatkan pemrosesan beberapa bagian data secara independen secara paralel. Prosesor melakukan operasi yang sama pada setiap bagian data. Anda mencapai paralelisme dengan memasukkan data secara paralel.

            Gambar menunjukkan diagram waktu untuk paralelisme ini. Masukan dibagi menjadi empat bagian, A, B, C, dan D. Operasi yang sama F() diterapkan pada setiap bagian ini dan keluarannya adalah OA, OB, OC, dan OD secara berurutan. Keempat tugas tersebut identik, dan berjalan secara paralel.<br><br>
            ![App Screenshot](https://github.com/aerochops/SysOp-3123500012/blob/main/week10/Media/data_parallelism_schematic.png?raw=true)<br><br>
            ![App Screenshot](https://github.com/aerochops/SysOp-3123500012/blob/main/week10/Media/data_parallelism_timing.png?raw=true)<br><br>
            
            #### Analogi<hr>
            Paralelisme data dapat dianalogikan dengan pekerjaan mencuci piring di sebuah restoran besar. Bayangkan Anda memiliki empat pelayan (representasi dari inti prosesor) yang semuanya mencuci piring (melakukan operasi yang sama) secara bersamaan. Piring-piring yang kotor (data) dibagi menjadi empat tumpukan terpisah, satu untuk setiap pelayan.

            Setiap pelayan mencuci piring pada tumpukan mereka sendiri secara bersamaan dengan yang lain, sehingga semua piring bisa dicuci lebih cepat daripada jika hanya satu pelayan yang bekerja mencuci semua piring tersebut satu per satu. Meskipun mereka semua melakukan pekerjaan yang sama, yaitu mencuci piring, mereka melakukannya secara paralel dengan tumpukan piring yang berbeda, sehingga pekerjaan selesai lebih cepat.

            Dalam konteks pemrograman multicore, pelayan adalah inti prosesor, piring kotor adalah data, dan mencuci piring adalah operasi yang dilakukan pada data tersebut. Proses paralel ini memungkinkan penggunaan sumber daya yang lebih efisien dan mempercepat waktu penyelesaian tugas secara keseluruhan.<br><br>

         - ### Paralelisme tugas(Task parallelism)
            Berbeda dengan paralelisme data, paralelisme tugas tidak membagi data masukan. Sebaliknya, paralelisme ini mencapai paralelisme dengan membagi aplikasi menjadi beberapa tugas. Paralelisme tugas melibatkan pendistribusian tugas dalam aplikasi di beberapa node pemrosesan. Beberapa tugas dapat memiliki ketergantungan data pada tugas lain, sehingga semua tugas tidak berjalan pada waktu yang sama.

            Pertimbangkan sebuah sistem yang melibatkan empat fungsi. Fungsi F2a() dan F2b() adalah paralel, yaitu, mereka dapat berjalan secara bersamaan. Dalam paralelisme tugas, Anda dapat membagi komputasi Anda menjadi dua tugas. Fungsi F2b() berjalan pada simpul pemrosesan yang terpisah setelah mendapatkan data Out1 dari Tugas 1, dan mengeluarkannya kembali ke F3() pada Tugas 1.<br><br>
            ![App Screenshot](https://github.com/aerochops/SysOp-3123500012/blob/main/week10/Media/task_parallelism_schematic.png?raw=true)
            <br><br>
            ![App Screenshot](https://github.com/aerochops/SysOp-3123500012/blob/main/week10/Media/task_parallelism_timing.png?raw=true)<br><br>

            #### Analogi<hr>
            Paralelisme tugas dapat dianalogikan dengan persiapan makanan di sebuah dapur restoran. Bayangkan Anda memiliki beberapa koki (representasi dari inti prosesor), dan masing-masing koki memiliki tugas spesifik yang berbeda untuk menyiapkan satu hidangan.

            Misalnya, Anda ingin membuat burger. Berikut adalah tugas-tugas yang dibagi antara koki-koki tersebut:

                Koki A menyiapkan dan memanggang roti.
                Koki B memasak patty daging.
                Koki C memotong sayuran dan menyiapkan topping.
                Koki D merakit burger dengan menggabungkan roti, patty, dan topping.

            Semua koki bekerja secara bersamaan pada tugas-tugas mereka masing-masing, sehingga keseluruhan hidangan bisa disiapkan lebih cepat daripada jika satu koki harus melakukan semua tugas tersebut satu per satu.

            Dalam konteks pemrograman multicore, koki adalah inti prosesor, dan setiap tugas spesifik mereka adalah proses yang berbeda dalam program. Dengan menggunakan paralelisme tugas, berbagai bagian dari pekerjaan (tugas-tugas yang berbeda) diselesaikan secara bersamaan oleh inti-inti prosesor yang berbeda, sehingga meningkatkan efisiensi dan mempercepat waktu penyelesaian total.<br><br>

        - ### Pipelining(Pipelining)
            Gunakan eksekusi pipeline model, atau pipelining, untuk mengatasi masalah paralelisme tugas di mana utas(thread) tidak berjalan sepenuhnya secara paralel. Pendekatan ini melibatkan modifikasi model sistem Anda untuk memperkenalkan penundaan di antara tugas-tugas yang memiliki ketergantungan data.

            Pada gambar ini, sistem dibagi menjadi tiga tugas untuk dijalankan pada tiga node pemrosesan yang berbeda, dengan penundaan yang diperkenalkan di antara fungsi-fungsi. Pada setiap langkah waktu, setiap tugas mengambil nilai dari langkah waktu sebelumnya melalui penundaan.<br><br>
            ![App Screenshot](https://github.com/aerochops/SysOp-3123500012/blob/main/week10/Media/pipelining_schematic.png?raw=true)
            <br><br>
            ![App Screenshot](https://github.com/aerochops/SysOp-3123500012/blob/main/week10/Media/pipelining_timing.png?raw=true)<br><br>

            #### Analogi<hr>
            Model pipeline execution dapat dianalogikan dengan jalur perakitan di sebuah pabrik mobil. Bayangkan Anda memiliki beberapa stasiun kerja (representasi dari tahap-tahap dalam pipa) yang masing-masing melakukan bagian spesifik dari proses perakitan mobil.

            Misalnya, proses perakitan mobil terdiri dari beberapa langkah sebagai berikut:

                Stasiun A: Merakit rangka dasar mobil.
                Stasiun B: Memasang mesin.
                Stasiun C: Memasang bodi mobil.
                Stasiun D: Memasang interior dan sistem elektronik.
                Stasiun E: Melakukan pengecekan akhir dan uji kualitas.

            Mobil bergerak sepanjang jalur perakitan, berhenti di setiap stasiun untuk menyelesaikan bagian dari proses perakitan. Ketika mobil pertama berpindah dari Stasiun A ke Stasiun B, Stasiun A mulai bekerja pada mobil kedua, dan begitu seterusnya.

            Dengan cara ini, setiap stasiun bekerja secara paralel namun pada mobil yang berbeda. Jadi, alih-alih satu mobil diselesaikan sepenuhnya sebelum mobil berikutnya mulai dirakit, beberapa mobil sedang dalam proses perakitan pada berbagai tahap pada saat yang sama.

            Dalam konteks pemrograman multicore, jalur perakitan adalah pipa, stasiun kerja adalah tahap dalam pipa, dan mobil adalah data atau tugas yang diproses. Setiap tahap dalam pipa melakukan operasi tertentu pada data, dan data tersebut bergerak melalui pipa, sehingga beberapa data sedang diproses pada berbagai tahap dalam pipa pada waktu yang sama. Pipelining meningkatkan efisiensi dengan memastikan bahwa setiap bagian dari pipa selalu sibuk memproses data.<br><br>

    - ### Tantangan Pemrograman Sistem Multicore<hr>
        Tren menuju sistem multicore terus memberikan tekanan pada perancang sistem dan pemrogram aplikasi untuk memanfaatkan beberapa inti komputasi dengan lebih baik. Perancang sistem operasi harus menulis algoritme penjadwalan yang menggunakan beberapa inti pemrosesan untuk memungkinkan eksekusi paralel seperti yang ditunjukkan pada Gambar 

        Untuk pemrogram aplikasi, tantangannya adalah memodifikasi program yang sudah ada serta mendesain program baru yang bersifat multithread. Secara umum, ada lima area yang menjadi tantangan dalam pemrograman untuk sistem multicore:  
        1. **Mengidentifikasi tugas**. Hal ini melibatkan pemeriksaan aplikasi untuk menemukan area yang dapat dibagi menjadi tugas-tugas yang terpisah dan bersamaan. Idealnya, tugas-tugas tidak bergantung satu sama lain dan dengan demikian dapat berjalan secara paralel pada masing-masing core.

        2. **Keseimbangan**. Ketika mengidentifikasi tugas-tugas yang dapat berjalan secara paralel, programmer juga harus memastikan bahwa tugas-tugas tersebut melakukan pekerjaan yang sama dengan nilai yang sama. Dalam beberapa kasus, tugas tertentu mungkin tidak memberikan kontribusi nilai yang sama besar terhadap keseluruhan proses seperti tugas lainnya. Menggunakan inti eksekusi terpisah untuk menjalankan tugas tersebut mungkin tidak sepadan dengan biayanya.  

        3. **Pemisahan data**. Sama seperti aplikasi yang dibagi menjadi beberapa tugas terpisah, data yang diakses dan dimanipulasi oleh tugas-tugas tersebut harus dibagi agar dapat berjalan pada core yang terpisah.

        4. **Ketergantungan data**. Data yang diakses oleh tugas-tugas harus diperiksa untuk mengetahui ketergantungan antara dua atau lebih tugas. Ketika satu tugas bergantung pada data dari tugas lain, programmer harus memastikan bahwa eksekusi tugas-tugas tersebut disinkronkan untuk mengakomodasi ketergantungan data.

        5. **Pengujian dan debugging**. Ketika sebuah program berjalan secara paralel pada beberapa core, banyak jalur eksekusi yang berbeda yang dimungkinkan. Menguji dan men-debug program bersamaan seperti itu pada dasarnya lebih sulit daripada menguji dan men-debug aplikasi berulir tunggal.

        Karena tantangan ini, banyak pengembang perangkat lunak berpendapat bahwa munculnya sistem multicore akan membutuhkan pendekatan yang sama sekali baru untuk merancang sistem perangkat lunak di masa depan. (Demikian pula, banyak pendidik ilmu komputer percaya bahwa pengembangan perangkat lunak harus diajarkan dengan penekanan yang lebih besar pada pemrograman paralel).<br><br>

- ## Multithreading Models 
    Menurut javatpoint dalam artikelnya, "Multithreading Models in Operating system."
    Multithreading memungkinkan aplikasi untuk membagi tugasnya menjadi beberapa thread. Dalam multi-thread, proses atau tugas yang sama dapat dilakukan oleh sejumlah thread, atau dapat dikatakan bahwa ada lebih dari satu thread untuk melakukan tugas dalam multithreading. Dengan penggunaan multithreading, multitasking dapat dicapai.<br><br>

    - ### User Thread (Utas Pengguna)<hr>
        User thread adalah thread yang dikelola sepenuhnya oleh program yang berjalan di level pengguna (user level) dari sistem operasi.

        Bayangkan sebuah perpustakaan besar yang memiliki banyak pengguna (pengunjung) yang ingin membaca buku. Setiap pengguna ini adalah seperti "user thread". Mereka melakukan aktivitas membaca buku secara independen, tetapi mereka tidak bisa mengakses langsung semua fasilitas perpustakaan tanpa bantuan.

        **Pengelolaan**: User thread dikelola oleh pengguna atau aplikasi itu sendiri, bukan oleh sistem operasi. Ini seperti pengguna yang mengatur sendiri kapan mereka akan mengambil buku, membaca, dan mengembalikannya.

        **Efisiensi**: Karena dikelola sendiri oleh aplikasi, user thread biasanya lebih ringan dan lebih cepat untuk diciptakan dan dikelola. Ibaratnya, pengguna bisa bergerak dengan cepat tanpa harus melalui banyak prosedur.

        **Keterbatasan**: Namun, jika terjadi masalah (misalnya, perpustakaan sedang direnovasi dan akses dibatasi), pengguna mungkin tidak bisa melakukan apa-apa tanpa intervensi dari perpustakawan. Artinya, jika satu user thread mengalami blok (misalnya, menunggu I/O), seluruh proses bisa terhenti karena sistem operasi tidak sadar ada lebih dari satu thread yang berjalan di dalam proses tersebut.<br><br>

    - ### User Thread (Utas Pengguna)<hr>
        Kernel thread, di sisi lain, dikelola sepenuhnya oleh kernel sistem operasi.

        Sekarang bayangkan perpustakaan ini memiliki sejumlah perpustakawan yang bekerja di sana. Setiap perpustakawan adalah seperti "kernel thread". Mereka memiliki otoritas dan kemampuan lebih besar untuk mengelola semua aktivitas di perpustakaan.

        **Pengelolaan**: Kernel thread dikelola oleh sistem operasi. Seperti perpustakawan yang memiliki akses dan otoritas untuk mengatur semua aktivitas di perpustakaan, kernel thread dapat mengakses berbagai sumber daya sistem dan diatur oleh kernel sistem operasi.

        **Efisiensi Pengelolaan Sumber Daya**: Kernel thread dapat melakukan tugas yang lebih berat dan kompleks karena mereka memiliki akses penuh ke sumber daya sistem. Jika satu kernel thread mengalami blok, sistem operasi masih dapat menjalankan thread lain, sehingga tidak ada yang sepenuhnya berhenti.

        **Overhead**: Kernel thread cenderung lebih lambat dan lebih berat untuk diciptakan dan dikelola karena mereka memerlukan interaksi lebih banyak dengan kernel sistem operasi, seperti perpustakawan yang harus mengikuti prosedur tertentu untuk mengatur aktivitas.<br><br>

    - ### Multithreading Models<hr>
        - ### Many-to-One<hr>
            Model many-to-one dalam pemrograman multithreading adalah skema di mana banyak thread pengguna (user threads) dipetakan ke dalam satu thread kernel (kernel thread). Dalam model ini, setiap thread pengguna diimplementasikan sepenuhnya di ruang pengguna (user space), dan satu-satunya thread yang memiliki representasi di ruang kernel (kernel space) adalah thread kernel yang menangani eksekusi dari semua thread pengguna yang terkait.

            Kelebihan dari model many-to-one meliputi:

            **Ringan**: Karena tidak ada overhead yang terkait dengan penciptaan dan manajemen thread di ruang kernel, model many-to-one cenderung lebih ringan dalam hal alokasi sumber daya. Ini karena hanya satu thread kernel yang harus dikelola oleh kernel.

            **Kesederhanaan** Implementasi: Model many-to-one seringkali lebih mudah diimplementasikan karena hanya memerlukan manajemen satu thread kernel. Ini dapat membuatnya menjadi pilihan yang baik untuk lingkungan yang memerlukan penggunaan sumber daya yang efisien dan tidak memerlukan skala besar atau kinerja tinggi.

            Namun, model many-to-one juga memiliki beberapa kelemahan:

            **Keterbatasan pada Skalabilitas**: Salah satu kelemahan utama dari model many-to-one adalah keterbatasan dalam hal skalabilitas. Karena semua thread pengguna dipetakan ke satu thread kernel, jika salah satu thread pengguna mengalami blok, maka semua thread pengguna dalam proses tersebut akan terhenti. Ini dikenal sebagai masalah penghalangan (blocking problem). Sebagai contoh, jika salah satu thread pengguna melakukan operasi I/O yang membutuhkan waktu lama, semua thread pengguna dalam proses tersebut akan terblokir hingga operasi I/O selesai. Ini membuat model ini kurang cocok untuk aplikasi yang membutuhkan responsif tinggi atau memiliki beban kerja I/O yang berat.

            **Keterbatasan pada Sistem Multiprosesor**: Model many-to-one tidak efisien pada sistem multiprosesor karena hanya menggunakan satu thread kernel. Pada sistem multiprosesor, idealnya, thread-thread pengguna dapat didistribusikan di seluruh prosesor untuk meningkatkan kinerja, tetapi model ini tidak memungkinkan hal itu.

            Karena kelemahan-kelemahan ini, model many-to-one seringkali digantikan oleh model-model multithreading lainnya seperti one-to-one (satu thread pengguna untuk satu thread kernel) dan many-to-many (banyak thread pengguna untuk banyak thread kernel) yang menawarkan lebih banyak fleksibilitas dan kinerja yang lebih baik, terutama dalam lingkungan yang memerlukan skalabilitas dan responsifitas yang tinggi.

            


    




        