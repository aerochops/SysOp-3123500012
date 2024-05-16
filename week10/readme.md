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

            Karena kelemahan-kelemahan ini, model many-to-one seringkali digantikan oleh model-model multithreading lainnya seperti one-to-one (satu thread pengguna untuk satu thread kernel) dan many-to-many (banyak thread pengguna untuk banyak thread kernel) yang menawarkan lebih banyak fleksibilitas dan kinerja yang lebih baik, terutama dalam lingkungan yang memerlukan skalabilitas dan responsifitas yang tinggi.<br><br>

            ![App Screenshot](https://github.com/aerochops/SysOp-3123500012/blob/main/week10/Media/Screenshot%202024-05-16%20101734.png?raw=true)<br><br>

            #### Analogi<hr>
            Dalam konteks multithreading, model Many-to-One mengacu pada skenario di mana banyak thread atau tugas berbagi satu proses tunggal atau satu thread yang menangani semua permintaan. Analogi yang mungkin adalah sebagai berikut:

            Bayangkan sebuah perusahaan yang memiliki banyak karyawan (thread) yang harus melakukan pekerjaan (tugas) untuk menyelesaikan proyek besar. Namun, hanya ada satu manajer (proses tunggal) yang mengatur dan mengkoordinasikan semua aktivitas. Para karyawan (thread) harus secara berurutan berbicara dengan manajer (proses tunggal) untuk mendapatkan arahan dan melaporkan kemajuan pekerjaan mereka.

            Dalam hal ini, banyak karyawan (thread) harus menunggu giliran untuk berbicara dengan manajer (proses tunggal), yang dapat menyebabkan penundaan dan efisiensi yang rendah karena ada bottleneck pada manajer (proses tunggal). Ini mencerminkan model Many-to-One di mana banyak thread harus berkomunikasi melalui satu proses tunggal untuk melakukan pekerjaan mereka.

        - ### one-to-one<hr>
            Model one-to-one dalam pemrograman multithreading adalah skema di mana setiap thread pengguna (user thread) dipetakan langsung ke dalam satu thread kernel (kernel thread). Dengan kata lain, untuk setiap thread pengguna yang dibuat dalam aplikasi, ada satu thread kernel yang sesuai yang dibuat dalam sistem operasi. Dalam model ini, thread-thread pengguna diimplementasikan di ruang pengguna (user space), sementara thread-thread kernel diimplementasikan di ruang kernel (kernel space).

            Kelebihan dari model one-to-one meliputi:

            **Skalabilitas yang Lebih Baik**: Karena setiap thread pengguna dipetakan langsung ke dalam thread kernel yang terpisah, model ini memungkinkan aplikasi untuk lebih baik memanfaatkan sumber daya multiprosesor. Thread-thread pengguna dapat didistribusikan di seluruh prosesor, meningkatkan kinerja aplikasi secara keseluruhan.

            **Responsifitas yang Lebih Baik**: Karena setiap thread pengguna memiliki thread kernel yang terpisah, operasi blocking pada satu thread pengguna tidak mempengaruhi thread-thread pengguna lainnya. Dengan demikian, aplikasi cenderung lebih responsif terhadap input dan memiliki waktu respons yang lebih baik.

            Namun, model one-to-one juga memiliki beberapa kelemahan:

            **Overhead Pembuatan dan Manajemen Thread**: Karena setiap thread pengguna dipetakan langsung ke dalam thread kernel yang terpisah, pembuatan dan manajemen thread memiliki overhead yang signifikan. Pembuatan thread-thread kernel memerlukan alokasi sumber daya yang lebih besar dari sistem operasi, yang dapat membatasi jumlah maksimum thread yang dapat dibuat oleh aplikasi.

            **Keterbatasan pada Beberapa Sistem Operasi**: Beberapa sistem operasi memiliki batasan pada jumlah thread-thread kernel yang dapat dibuat, yang dapat membatasi skalabilitas aplikasi dalam model one-to-one. Selain itu, mempertahankan jumlah thread-thread kernel yang besar dapat memakan banyak sumber daya sistem.

            Meskipun memiliki kelemahan-kelemahan ini, model one-to-one sering digunakan dalam lingkungan di mana skalabilitas dan responsifitas adalah faktor penting, terutama pada sistem multiprosesor dan pada aplikasi yang membutuhkan kinerja tinggi dan pemrosesan paralel.<br><br>

            ![App Screenshot](https://github.com/aerochops/SysOp-3123500012/blob/main/week10/Media/Screenshot%202024-05-16%20101843.png?raw=true)<br><br>

            #### Analogi<hr>
            Dalam model one-to-one dalam multithreading, setiap thread memiliki proses terpisah yang terkait dengannya. Analogi yang cocok untuk ini adalah sebuah tim proyek di mana setiap anggota tim memiliki manajer langsung yang bertanggung jawab atas koordinasi dan pengawasan pekerjaan mereka.

            Misalkan ada sebuah proyek konstruksi besar. Setiap pekerja (thread) memiliki mandor langsung (proses terpisah) yang memberikan arahan, memantau kemajuan, dan menangani masalah yang muncul. Dalam hal ini, setiap pekerja (thread) dapat bekerja secara independen tanpa harus menunggu atau bergantung pada orang lain. Mereka memiliki sumber daya dan otoritas langsung untuk melakukan tugas mereka dengan efisien.

            Analogi ini mencerminkan model one-to-one dalam multithreading, di mana setiap thread memiliki proses terpisah yang terkait dengannya, memungkinkan kinerja yang lebih mandiri dan efisien.<br><br>

        - ### Many-to-Many Model<hr>
            Model many-to-many dalam pemrograman multithreading adalah skema di mana banyak thread pengguna (user threads) dipetakan ke dalam banyak thread kernel (kernel threads). Dalam model ini, beberapa thread pengguna diimplementasikan di ruang pengguna (user space), dan thread-thread kernel diimplementasikan di ruang kernel (kernel space). Setiap thread pengguna dapat dipetakan ke satu atau lebih thread kernel, dan sebaliknya, beberapa thread kernel dapat melayani satu atau lebih thread pengguna.

            Kelebihan dari model many-to-many meliputi:

            **Skalabilitas yang Lebih Baik**: Karena beberapa thread pengguna dapat dipetakan ke dalam banyak thread kernel, model ini memungkinkan aplikasi untuk lebih baik memanfaatkan sumber daya multiprosesor. Thread-thread pengguna dapat didistribusikan di seluruh prosesor, meningkatkan kinerja aplikasi secara keseluruhan.

            **Responsifitas yang Lebih Baik**: Karena beberapa thread kernel dapat melayani beberapa thread pengguna, operasi blocking pada satu thread pengguna tidak akan mempengaruhi thread-thread pengguna lainnya. Ini memungkinkan aplikasi untuk tetap responsif terhadap input dan memiliki waktu respons yang lebih baik.

            **Kemampuan untuk Menangani Blocking Operations**: Dalam model many-to-many, jika satu thread pengguna mengalami operasi blocking, thread-thread kernel lain masih dapat menangani thread-thread pengguna lainnya, sehingga menghindari penghalangan (blocking) dari seluruh proses.

            Namun, model many-to-many juga memiliki beberapa kelemahan:

            **Kompleksitas Implementasi**: Implementasi model many-to-many seringkali lebih kompleks daripada model-model lainnya, seperti one-to-one atau many-to-one. Manajemen hubungan antara thread-thread pengguna dan thread-thread kernel memerlukan koordinasi yang cermat dan kompleksitas yang lebih besar dalam manajemen sumber daya.

            **Overhead Komunikasi**: Karena beberapa thread pengguna dapat dipetakan ke beberapa thread kernel, ada overhead tambahan dalam komunikasi antara thread-thread pengguna dan thread-thread kernel. Hal ini dapat mempengaruhi kinerja aplikasi, terutama pada skala besar atau pada sistem dengan banyak thread.

            Meskipun memiliki kelemahan-kelemahan ini, model many-to-many sering digunakan dalam lingkungan di mana fleksibilitas, skalabilitas, dan responsifitas adalah faktor penting, terutama pada aplikasi yang berjalan di atas sistem multiprosesor dan memerlukan kinerja tinggi serta pemrosesan paralel.<br><br>

            ![App Screenshot](https://github.com/aerochops/SysOp-3123500012/blob/main/week10/Media/Screenshot%202024-05-16%20101853.png?raw=true)<br><br>

            #### Analogi<hr>
            Bayangkan Anda memiliki sebuah proyek pembuatan film. Dalam proyek ini, Anda memiliki beberapa aktor dan beberapa kru. Aktor mungkin terlibat dalam beberapa film yang berbeda, dan kru mungkin bekerja di beberapa film dalam waktu yang bersamaan.

            Analogi ini menggambarkan model many-to-many dalam multithreading. Aktor adalah thread yang menjalankan tugas-tugas tertentu (misalnya, berakting dalam adegan tertentu), dan kru adalah sumber daya yang digunakan oleh thread (misalnya, kamera, pencahayaan, dll.).

            Dalam model many-to-many, beberapa thread (aktor) dapat dieksekusi pada beberapa sumber daya (kru) secara bersamaan. Sebaliknya, beberapa sumber daya (kru) dapat digunakan oleh beberapa thread (aktor) pada saat yang sama.

            Ini memungkinkan efisiensi yang lebih besar dalam pemanfaatan sumber daya, karena beberapa thread dapat menggunakan sumber daya yang sama pada waktu yang bersamaan, dan sumber daya yang sama dapat digunakan oleh beberapa thread.<br><br>

- ## Thread Libraries 
    Pustaka thread menyediakan API bagi programmer untuk membuat dan mengelola thread. Pustaka thread dapat diimplementasikan di ruang pengguna atau di ruang kernel. Yang pertama melibatkan fungsi API yang diimplementasikan semata-mata di dalam ruang pengguna, tanpa dukungan kernel. Yang terakhir melibatkan pemanggilan sistem, dan membutuhkan kernel dengan dukungan pustaka thread.<br><br>

    Ada tiga pustaka thread utama yang digunakan saat ini:<br>
    > POSIX Pthreads - dapat disediakan baik sebagai pustaka pengguna atau kernel, sebagai perluasan dari standar POSIX.<br><br>
    > Win32 threads - disediakan sebagai pustaka tingkat kernel pada sistem Windows.<br><br>
    > Thread Java - Karena Java umumnya berjalan pada Java Virtual Machine, implementasi thread didasarkan pada OS dan perangkat keras apa pun yang digunakan JVM, yaitu Pthreads atau Win32, tergantung pada sistem.<br><br>

    Bagian berikut ini akan mendemonstrasikan penggunaan thread di ketiga sistem untuk menghitung jumlah bilangan bulat dari 0 hingga N dalam thread terpisah, dan menyimpan hasilnya dalam variabel “jumlah”.

    - #### Pthreads<hr>
        Standar POSIX (IEEE 1003.1c) mendefinisikan spesifikasi untuk pThreads, bukan implementasinya.
        pThreads tersedia di Solaris, Linux, Mac OSX, Tru64, dan melalui shareware domain publik untuk Windows.
        Variabel global digunakan bersama di antara semua thread.
        Satu thread dapat menunggu thread lain untuk bergabung sebelum melanjutkan.
        pThreads memulai eksekusi pada fungsi yang ditentukan, dalam contoh ini adalah fungsi runner( ):<br><br>

        ![App Screenshot](https://github.com/aerochops/SysOp-3123500012/blob/main/week10/Media/4_09_PThreadsAPI.jpg?raw=true)<br><br>

        ![App Screenshot](https://github.com/aerochops/SysOp-3123500012/blob/main/week10/Media/4_10_JoiningPThreads.jpg?raw=true)

    - #### Windows Threads<hr>
        Mirip dengan pThreads. Periksa contoh kode untuk melihat perbedaannya, yang sebagian besar adalah sintaksis & nomenklatur:<br><br>
        ![App Screenshot](https://github.com/aerochops/SysOp-3123500012/blob/main/week10/Media/4_10_Win32API.jpg?raw=true)<br><br>

    - #### Java Threads<hr>
        SEMUA program Java menggunakan Thread - bahkan yang “umum” sekalipun.
        Pembuatan Thread baru membutuhkan Objek yang mengimplementasikan Antarmuka yang dapat dijalankan, yang berarti mengandung metode “public void run( )”. Setiap turunan dari kelas Thread secara alami akan mengandung metode seperti itu. (Dalam prakteknya metode run( ) harus ditimpa / disediakan agar thread memiliki fungsionalitas praktis. )<br>
        Membuat sebuah Object Thread tidak membuat thread berjalan - Untuk melakukan hal tersebut program harus memanggil metode “start( )” dari Thread. Start( ) mengalokasikan dan menginisialisasi memori untuk Thread, dan kemudian memanggil metode run( ). (Programmer tidak memanggil run( ) secara langsung. )
        Karena Java tidak mendukung variabel global, Thread harus memberikan referensi ke sebuah Object bersama untuk berbagi data, dalam contoh ini adalah Object “Jumlah”.<br>
        Perhatikan bahwa JVM berjalan di atas OS asli, dan bahwa spesifikasi JVM tidak menentukan model apa yang akan digunakan untuk memetakan thread Java ke thread kernel. Keputusan ini tergantung pada implementasi JVM, dan bisa jadi satu-ke-satu, banyak-ke-banyak, atau banyak-ke-satu ... (Pada sistem UNIX, JVM biasanya menggunakan PThreads dan pada sistem Windows, biasanya menggunakan windows threads. )<br><br>
        ![App Screenshot](https://github.com/aerochops/SysOp-3123500012/blob/main/week10/Media/4_11_JavaThreads.jpg?raw=true)<br><br>

#### Thread Implisit


Thread implisit merujuk pada teknik di mana pembuatan dan pengelolaan thread dilakukan oleh kompiler dan pustaka runtime, bukan oleh programmer secara eksplisit. Pendekatan ini bertujuan untuk menyederhanakan pemrograman paralel dengan mengurangi kompleksitas yang terkait dengan manajemen thread secara manual. Berikut adalah beberapa contoh metode yang menggunakan thread implisit:

#### 1. Thread Pools
- **Konsep**: Thread pool adalah kumpulan thread yang telah dibuat sebelumnya dan siap untuk menjalankan tugas. Ketika ada tugas baru yang harus dijalankan, tugas tersebut diambil oleh salah satu thread dalam pool, yang sudah siap bekerja.
- **Keuntungan**:
  - **Efisiensi**: Penggunaan kembali thread yang ada lebih efisien daripada membuat thread baru setiap kali ada tugas baru. Ini mengurangi overhead pembuatan dan penghancuran thread.
  - **Pengelolaan Beban Kerja**: Thread pool dapat mengatur jumlah maksimum thread yang berjalan secara bersamaan, yang membantu dalam pengelolaan sumber daya sistem dan pencegahan oversubscription.
- **Implementasi**: Banyak bahasa pemrograman dan pustaka menyediakan implementasi thread pool, seperti `java.util.concurrent.ExecutorService` di Java dan `ThreadPoolExecutor` di Python.

#### 2. OpenMP
- **Konsep**: OpenMP (Open Multi-Processing) adalah standar untuk pemrograman paralel di lingkungan memori bersama. OpenMP menggunakan kumpulan direktif kompiler, pustaka runtime, dan variabel lingkungan untuk mengelola eksekusi paralel.
- **Keuntungan**:
  - **Kemudahan Penggunaan**: Programmer dapat menambahkan direktif OpenMP ke kode sekuensial untuk menjadikannya paralel tanpa perlu mengubah struktur kode secara signifikan.
  - **Kontrol Granularitas**: OpenMP memungkinkan kontrol granularitas pada level loop dan bagian kode lainnya, mempermudah pembagian tugas dalam blok kode.
- **Implementasi**: OpenMP didukung oleh banyak kompiler utama, seperti GCC, Clang, dan Intel compilers. Contoh direktif OpenMP adalah `#pragma omp parallel for`, yang memparallelkan eksekusi loop.

#### 3. Grand Central Dispatch (GCD)
- **Konsep**: GCD adalah teknologi dari Apple yang digunakan pada macOS dan iOS untuk memudahkan identifikasi dan pengelolaan bagian kode yang dapat dijalankan secara paralel. GCD menggunakan konsep `dispatch queues` untuk mengelola eksekusi tugas.
- **Keuntungan**:
  - **Sederhana dan Efisien**: GCD menyederhanakan pemrograman paralel dengan mengabstraksi manajemen thread. Programmer hanya perlu menambahkan tugas ke antrian yang sesuai, dan GCD mengurus eksekusinya.
  - **Penskalaan Otomatis**: GCD secara otomatis menyesuaikan jumlah thread berdasarkan beban kerja dan sumber daya yang tersedia, sehingga optimal dalam penggunaan CPU.
- **Implementasi**: GCD menggunakan dua jenis antrian, yaitu **serial queues** dan **concurrent queues**. Tugas dapat ditambahkan ke antrian ini menggunakan fungsi seperti `dispatch_async` untuk eksekusi asinkron.



### Threading Issues

Dalam sistem operasi, pengelolaan thread memerlukan perhatian khusus terhadap beberapa isu utama, yang mencakup semantik dari panggilan sistem `fork()` dan `exec()`, penanganan sinyal, pembatalan thread, penyimpanan thread-lokal, dan aktivasi penjadwal. Berikut adalah penjelasan rinci mengenai setiap isu tersebut:

#### Semantics of `fork()` and `exec()` System Calls
- **`fork()`**: `fork()` adalah panggilan sistem yang digunakan untuk membuat proses baru dengan menggandakan proses yang memanggilnya. Dalam konteks multithreading:
  - **Menggandakan Satu Thread**: Hanya thread yang memanggil `fork()` yang digandakan dalam proses anak. Ini berarti thread lain di proses induk tidak ada di proses anak, yang bisa menyebabkan masalah jika thread lain memegang sumber daya penting atau mengelola data yang dibutuhkan proses anak.
  - **Menggandakan Semua Thread**: Semua thread dalam proses induk digandakan di proses anak. Pendekatan ini lebih rumit karena memastikan konsistensi dan sinkronisasi antara thread yang digandakan dapat menjadi tantangan besar.
- **`exec()`**: `exec()` menggantikan proses yang sedang berjalan dengan program baru. Ketika `exec()` dipanggil:
  - Semua thread dalam proses digantikan oleh program baru, yang dimulai dengan satu thread utama. Semua thread sebelumnya dihentikan, dan konteks eksekusi baru dimulai dari awal program yang dieksekusi.

#### Signal Handling
- **Sinyal**: Sinyal adalah metode yang digunakan oleh sistem operasi untuk mengirim pemberitahuan ke proses tentang kejadian tertentu (misalnya, pembagian dengan nol, permintaan penghentian).
- **Dalam Sistem Multithreaded**: Penanganan sinyal lebih rumit karena sinyal dapat ditujukan ke:
  - **Thread Tertentu**: Sinyal hanya diterima oleh thread yang spesifik.
  - **Semua Thread**: Sinyal dikirim ke semua thread dalam proses, meskipun hanya satu thread yang akan menangani sinyal tersebut.
  - **Thread-thread Tertentu**: Sinyal dikirim ke beberapa thread tertentu yang telah mengatur untuk menangani sinyal tersebut. Hal ini memerlukan mekanisme koordinasi untuk menentukan thread mana yang akan menangani sinyal.

#### Thread Cancellation
- **Pembatalan Thread**: Proses penghentian thread sebelum selesai menjalankan tugasnya. Ini bisa dilakukan untuk membebaskan sumber daya atau menghentikan eksekusi yang tidak lagi diperlukan.
- **Pendekatan Utama**:
  - **Pembatalan Asinkron**: Thread dapat dibatalkan kapan saja, tanpa pemberitahuan. Ini bisa menyebabkan masalah inkonsistensi data atau deadlock karena thread bisa dibatalkan saat sedang memegang sumber daya penting.
  - **Pembatalan Tertunda**: Thread memeriksa secara berkala apakah ada permintaan pembatalan dan membatalkan diri secara teratur pada titik-titik tertentu yang aman. Pendekatan ini lebih aman karena thread memiliki kesempatan untuk membersihkan sumber daya sebelum berhenti.

#### Thread-Local Storage (TLS)
- **Penyimpanan Lokal Thread**: Mekanisme yang memungkinkan setiap thread memiliki salinan data sendiri yang bersifat unik untuk thread tersebut.
- **Kegunaan**: TLS sangat berguna ketika data perlu bersifat thread-specific dan tidak aman untuk diakses oleh thread lain. Misalnya, variabel yang menyimpan informasi sesi untuk setiap thread klien di server web.

#### Scheduler Activations
- **Aktivasi Penjadwal**: Model komunikasi antara thread pengguna dan kernel untuk mengelola thread secara efisien dalam model Many-to-Many atau two-level.
- **Lightweight Process (LWP)**: Struktur data menengah yang digunakan untuk mengurangi overhead penjadwalan dan memungkinkan kernel dan perpustakaan thread berkomunikasi.
- **Mekanisme Aktivasi Penjadwal**: Ketika kernel memutuskan untuk menjadwalkan atau menghentikan thread pengguna, ia mengirim aktivasi penjadwal ke perpustakaan thread pengguna, yang kemudian dapat menyesuaikan peta thread pengguna ke thread kernel. Hal ini memungkinkan perpustakaan thread untuk menjaga sinkronisasi dan efisiensi dalam penggunaan thread kernel.

### Threading Issue
Semantics of fork() and exec() system calls
fork() membuat sebuah proses baru yang merupakan salinan dari proses yang dipanggil. Ini termasuk menyalin semua thread dalam sebuah program multi-threaded pada beberapa sistem UNIX. Ada dua versi fork() yang mengontrol berapa banyak thread yang disalin. fork dapat menduplikasi semua thread dari proses induk ke proses anak atau hanya thread yang dipanggil oleh proses induk.

exec() menggantikan seluruh proses dengan program baru yang ditentukan dalam argumen-argumennya.

Karena exec() menggantikan proses, maka tidak perlu melakukan fork() dan menyalin semua thread jika exec() dipanggil setelahnya. Dalam kasus ini, versi fork() yang hanya menyalin thread yang dipanggil akan lebih efisien.

Signal Handling
Sinyal adalah interupsi perangkat lunak yang dikirimkan ke suatu proses. Sistem operasi menggunakan sinyal untuk melaporkan situasi luar biasa ke program yang sedang dijalankan. Beberapa sinyal melaporkan kesalahan seperti referensi ke alamat memori yang tidak valid; yang lain melaporkan peristiwa yang tidak sinkron, seperti terputusnya saluran telepon.

Sebuah pengelola sinyal digunakan untuk memproses sinyal

Sinyal dihasilkan oleh suatu peristiwa tertentu
Sinyal dikirimkan ke sebuah proses
Sinyal ditangani oleh salah satu dari dua penangan sinyal:
default
ditentukan pengguna
Setiap sinyal memiliki penanganan default yang dijalankan kernel saat menangani sinyal

Penanganan sinyal yang ditentukan pengguna dapat menggantikan default
Untuk single-threaded, sinyal dikirim ke proses
Ke mana sinyal harus dikirimkan untuk multi-threaded?

Mengirimkan sinyal ke utas yang menggunakan sinyal tersebut
Mengirimkan sinyal ke setiap utas dalam proses
Mengirimkan sinyal ke utas tertentu dalam proses
Menetapkan thread tertentu untuk menerima semua sinyal untuk proses
Dalam program multithreaded, sinyal dapat menjadi rumit. Tidak seperti single-threaded apps di mana sinyal menuju ke seluruh proses, multithreading membuat target menjadi tidak jelas.

Ada dua jenis sinyal:

Synchronous: Dikirim ke thread yang menyebabkannya (seperti kesalahan program).
Asynchronous: Dapat datang secara tidak terduga dari luar program (seperti sinyal penghentian).
Sinyal Asynchronous merupakan tantangan dalam multithreading karena tidak jelas thread mana yang harus menerimanya. Pada sistem Unix, thread dapat menentukan sinyal mana yang mereka inginkan, tetapi OS pada akhirnya memutuskan pengirimannya.
Windows menggunakan Panggilan Prosedur Asinkron (APC) sebagai pengganti sinyal. Tidak seperti Unix di mana sebuah thread memilih sinyalnya, semua thread dalam proses Windows dapat menerima APC.
Thread Cancellation
Menghentikan thread sebelum selesai dikerjakan Thread yang akan dibatalkan adalah thread target Dua pendekatan umum:

Pembatalan asynchronous menghentikan thread target dengan segera
Deffered cancellation memungkinkan thread target untuk secara berkala memeriksa apakah harus dibatalkan
App Screenshot

Pembatalan utas memungkinkan Anda menghentikan thread sebelum menyelesaikan tugasnya. Ada dua jenis utama:

Asynchronous cancellation: Pembatalan secara tiba-tiba menghentikan thread target tanpa memperhatikan statusnya, yang dapat menyebabkan masalah seperti kebocoran sumber daya atau data yang rusak jika thread tersebut memperbarui informasi bersama.
Deffered cancellation: **Ini memberikan kesempatan kepada thread target untuk membersihkan diri dan keluar dengan tenang. Thread memeriksa bendera pembatalan secara berkala untuk melihat apakah thread tersebut harus berhenti. Titik pembatalan adalah saat-saat tertentu dalam kode thread di mana pembatalan aman karena thread tidak berada di tengah-tengah operasi yang kritis.
Thread-Local Storage
Thread Local Storage (TLS) adalah metode di mana setiap thread dalam proses multithreaded dapat mengalokasikan lokasi untuk menyimpan data spesifik thread. Data spesifik thread yang terikat secara dinamis (run-time) didukung melalui API TLS (TlsAlloc).

thread-local storage (TLS) memungkinkan setiap thread memiliki salinan datanya sendiri
Berguna ketika Anda tidak memiliki kendali atas proses pembuatan thread (misalnya, ketika menggunakan kumpulan thread)
Berbeda dengan variabel lokal
Variabel lokal hanya terlihat selama pemanggilan fungsi tunggal
TLS terlihat di seluruh pemanggilan fungsi
Mirip dengan data statis
TLS bersifat unik untuk setiap thread
Scheduler Activations
Baik model M:M dan two-level model memerlukan komunikasi untuk mempertahankan jumlah thread kernel yang sesuai yang dialokasikan ke aplikasi

Biasanya menggunakan struktur data perantara antara thread pengguna dan kernel - lightweight process (LWP)

Tampak sebagai prosesor virtual di mana proses dapat menjadwalkan thread pengguna untuk dijalankan
Setiap LWP dilampirkan ke thread kernel
Berapa banyak LWP yang harus dibuat?
Aktivasi penjadwal menyediakan upcalls - mekanisme komunikasi dari kernel ke upcall handler di pustaka thread

Komunikasi ini memungkinkan aplikasi untuk mempertahankan jumlah thread kernel yang benar

References
https://www.geeksforgeeks.org/threading-issues/
https://en.wikipedia.org/wiki/Thread-local_storage
https://learn.microsoft.com/en-us/cpp/parallel/thread-local-storage-tls?view=msvc-170
Windows Threads
Windows mengimplementasikan API Windows - primary API untuk Win 98, Win NT, Win 2000, Win XP, dan Win 7
Mengimplementasikan one-to-one mapping, tingkat kernel
Setiap threads berisi
Sebuah id thread
Set register yang mewakili status processor
Tumpukan pengguna dan kernel yang terpisah ketika thread berjalan dalam mode pengguna atau mode kernel
Area penyimpanan data pribadi yang digunakan oleh pustaka run-time dan pustaka tautan dinamis (DLL)
Kumpulan register, tumpukan, dan area penyimpanan pribadi dikenal sebagai konteks dari thread
Struktur data utama dari sebuah thread meliputi:
ETHREAD (blok thread eksekutif) - termasuk pointer ke proses yang mana thread tersebut berada dan ke KTHREAD, di ruang kernel
KTHREAD (blok thread kernel) - scheduling dan synchronization info, tumpukan kernel-mode, pointer ke TEB, dalam ruang kernel
TEB (blok lingkungan thread) - id thread, tumpukan mode-pengguna, penyimpanan thread-lokal, di ruang pengguna
No 1
Berikan tiga contoh pemrograman di mana multithreading memberikan kinerja yang lebih baik daripada solusi single-threaded.

Jawaban:

Sebuah server Web yang melayani setiap permintaan dalam thread yang berbeda.
Aplikasi yang diparalelkan seperti perkalian matriks di mana bagian-bagian yang berbeda dari matriks dapat dikerjakan secara paralel.
Sebuah program GUI interaktif seperti debugger di mana sebuah thread digunakan untuk memantau masukan pengguna, thread lain mewakili aplikasi yang berjalan, dan thread ketiga memantau kinerja.
Penjelasan
a. Web Server:

Dalam kasus web server, masing-masing permintaan dari klien (seperti mengambil halaman web atau data dari server) dapat dianggap sebagai tugas yang independen. Dengan menggunakan multithreading, server dapat menangani beberapa permintaan secara bersamaan. Sebagai contoh, ketika satu thread sedang menunggu respon dari database, thread lainnya dapat melayani permintaan dari klien lainnya. Ini dapat mengoptimalkan penggunaan sumber daya server dan meningkatkan responsivitas secara keseluruhan.

b. Parallelized Application (Aplikasi Paralel):

Dalam kasus seperti perkalian matriks, ada banyak operasi yang dapat dijalankan secara independen. Dengan menggunakan multithreading, bagian-bagian dari matriks dapat dikalikan secara bersamaan oleh thread yang berbeda. Ini memungkinkan untuk meningkatkan throughput secara signifikan karena beberapa operasi dapat dilakukan secara paralel tanpa harus menunggu selesainya operasi sebelumnya.

c. Interactive GUI Program (Program Antarmuka Pengguna Grafis yang Interaktif):

Dalam aplikasi seperti debugger, kita mungkin memiliki tugas-tugas yang berjalan secara bersamaan. Satu thread mungkin bertanggung jawab untuk menerima input dari pengguna, yang lain untuk menjalankan aplikasi yang sedang di-debug, dan yang lainnya mungkin untuk memantau kinerja aplikasi. Dengan menggunakan multithreading, aplikasi dapat tetap responsif terhadap input pengguna sementara masih dapat menjalankan tugas-tugas lain secara bersamaan tanpa mengganggu pengalaman pengguna. Ini memungkinkan debugger untuk tetap aktif sambil melakukan pemantauan kinerja dan menjalankan kode yang sedang di-debug secara bersamaan.

References
https://rdr11.it.student.pens.ac.id/Semester2/Sistem Operasi/Teori/TeoriOS7rev1_1D4TIB_2110191044.pdf
No 2
Apa dua perbedaan antara thread tingkat pengguna dan thread tingkat kernel? Dalam keadaan apa satu jenis lebih baik daripada yang lain?

Jawaban:

Thread tingkat pengguna tidak diketahui oleh kernel, sedangkan kernel mengetahui thread tingkat kernel.
Pada sistem yang menggunakan pemetaan M:1 atau M:N, thread pengguna diatur oleh pustaka thread dan kernel mengatur thread kernel.
Thread kernel tidak harus dikaitkan dengan proses sedangkan setiap thread pengguna milik proses. Thread kernel umumnya lebih mahal untuk dipertahankan daripada thread pengguna karena mereka harus diwakili dengan struktur data kernel.
Penjelasan
Perbedaan antara user-level threads dan kernel-level threads terletak pada tingkat di mana sistem operasi terlibat dan bagaimana proses penjadwalan dilakukan. User-level threads tidak dikenal oleh kernel, sementara kernel-level threads dikenal oleh kernel. Selain itu, pada sistem dengan pemetaan M:1 atau M:N, user-level threads dijadwalkan oleh perpustakaan thread, sedangkan kernel-level threads dijadwalkan oleh kernel.

Pilihan antara kedua jenis ini tergantung pada kebutuhan aplikasi. User-level threads memiliki overhead yang lebih rendah karena mereka dikelola sepenuhnya oleh program pengguna tanpa intervensi kernel. Namun, kernel-level threads dapat memberikan kinerja yang lebih baik dan lebih stabil karena mereka dapat dijadwalkan langsung oleh kernel dan memiliki kemampuan untuk menggunakan multiple core. Sebagai aturan umum, user-level threads lebih cocok untuk aplikasi yang membutuhkan manajemen yang sangat ringan, sementara kernel-level threads lebih cocok untuk aplikasi yang memerlukan kinerja dan skalabilitas yang tinggi.

References
https://www.geeksforgeeks.org/difference-between-user-level-thread-and-kernel-level-thread/
https://www.geeksforgeeks.org/thread-in-operating-system/
No 3
Jelaskan tindakan yang diambil oleh kernel untuk context switch antara kernel level threads.

Jawaban:

Peralihan konteks antara benang kernel biasanya memerlukan penyimpanan nilai dari register CPU dari thread yang sedang dipindahkan dan mengembalikan register CPU dari thread baru yang sedang dijadwalkan.

Penjelasan
Saat melakukan context-switch antara thread-thread di level kernel, kernel perlu menyimpan nilai-nilai register CPU dari thread yang akan diganti dan mengembalikan nilai-nilai register CPU dari thread baru yang akan dijadwalkan.

Apa itu Context Swicth
Context-switch adalah proses di mana CPU beralih dari eksekusi satu proses atau thread ke proses atau thread lainnya. Saat melakukan context-switch, sistem operasi menyimpan status (atau konteks) dari proses atau thread yang sedang berjalan saat ini, termasuk nilai-nilai register CPU, pointer instruksi, dan informasi lain yang diperlukan untuk melanjutkan eksekusi nanti. Kemudian, sistem operasi memuat konteks dari proses atau thread baru yang akan dieksekusi sehingga CPU dapat melanjutkan eksekusi dari titik terakhir di mana proses atau thread sebelumnya dihentikan. Context-switch memungkinkan sistem operasi untuk memberikan kesan bahwa banyak proses atau thread sedang berjalan secara bersamaan, meskipun CPU sebenarnya melakukan eksekusi secara bergantian di antara mereka.

References
https://www.geeksforgeeks.org/context-switch-in-operating-system/
No 4
Sumber daya apa saja yang digunakan ketika thread dibuat? Bagaimana perbedaannya dengan yang digunakan ketika proses dibuat?

Jawaban:

Karena thread lebih kecil daripada proses, pembuatan thread biasanya menggunakan sumber daya yang lebih sedikit dibandingkan dengan pembuatan proses. Membuat proses membutuhkan alokasi blok kontrol proses (PCB), struktur data yang cukup besar. PCB mencakup peta memori, daftar file yang dibuka, dan variabel lingkungan. Mengalokasikan dan mengelola peta memori biasanya merupakan aktivitas yang paling memakan waktu. Membuat thread pengguna atau kernel melibatkan alokasi struktur data kecil untuk menampung set register, tumpukan, dan prioritas.

Penjelasan
Ketika membuat sebuah thread, digunakan lebih sedikit sumber daya dibandingkan dengan membuat sebuah proses. Proses memerlukan alokasi blok kontrol proses (PCB), struktur data yang cukup besar, yang mencakup peta memori, daftar file terbuka, dan variabel lingkungan. Pembuatan PCB dan pengelolaan peta memori biasanya memakan waktu paling lama. Sedangkan, pembuatan sebuah thread melibatkan alokasi struktur data kecil untuk menampung set register, tumpukan, dan prioritas.

References
https://www.guru99.com/difference-between-process-and-thread.html?gpp&gpp_sid
No 5
Asumsikan bahwa sistem operasi memetakan thread tingkat pengguna ke kernel menggunakan model many-to-many dan bahwa pemetaan dilakukan melalui LWPs. Selain itu, sistem memungkinkan pengembang untuk membuat thread real-time untuk digunakan dalam sistem real-time. Apakah perlu mengikat thread real-time ke LWP? Jelaskan.

Jawaban:

Ya. Waktu sangat krusial untuk aplikasi real-time. Jika thread ditandai sebagai real-time tetapi tidak terikat ke LWP, thread mungkin harus menunggu untuk dihubungkan ke LWP sebelum berjalan. Pertimbangkan jika thread real-time sedang berjalan (terhubung ke LWP) dan kemudian melanjutkan untuk memblokir (mis. harus melakukan I/O, telah dipraemptif oleh thread real-time prioritas lebih tinggi, sedang menunggu kunci penguncian mutual, dll.) Sementara thread real-time diblokir, LWP yang sebelumnya terhubung telah ditugaskan ke thread lain. Ketika thread real-time telah dijadwalkan untuk berjalan lagi, ia harus menunggu untuk dihubungkan ke LWP. Dengan mengikat LWP ke thread real-time, Anda memastikan thread akan dapat berjalan dengan penundaan minimal setelah dijadwalkan.

Penjelasan
Tentu! Saat menggunakan thread real-time dalam sistem, penting untuk mengikatnya ke dalam unit pemrosesan yang disebut LWP. Tanpa ikatan ini, thread real-time mungkin harus menunggu sebelum bisa berjalan. Ini bisa menyebabkan penundaan yang tidak diinginkan dalam kinerja aplikasi yang membutuhkan waktu respons cepat. Dengan mengikat thread real-time ke LWP, kita memastikan bahwa thread tersebut bisa langsung berjalan begitu dijadwalkan tanpa penundaan tambahan.

Apa itu LWP?
LWP singkatan dari "Lightweight Process" atau Proses Ringan. Ini adalah unit pemrosesan kecil yang dikelola oleh sistem operasi untuk mengeksekusi thread. Dalam sistem operasi yang menggunakan model many-to-many untuk memetakan thread pengguna ke kernel, seperti Solaris dan beberapa versi UNIX lainnya, LWP berfungsi sebagai perantara antara thread pengguna dan kernel. Mereka membantu dalam penjadwalan dan pengelolaan sumber daya untuk thread, memungkinkan sistem operasi untuk mengelola thread secara efisien. Dalam konteks ini, mengikat thread real-time ke LWP berarti menghubungkan thread tersebut ke unit pemrosesan yang akan mengeksekusinya.

References
https://www.geeksforgeeks.org/thread-scheduling/
References
https://socs.binus.ac.id/2020/12/13/thread-unit-pemanfaatan-cpu/
https://rdr11.it.student.pens.ac.id/Semester2/Sistem Operasi/Teori/TeoriOS7rev1_1D4TIB_2110191044.pdf
https://www.geeksforgeeks.org/context-switch-in-operating-system/<br>
References https://www.cs.uic.edu/~jbell/CourseNotes/OperatingSystems/4_Threads.html

            

