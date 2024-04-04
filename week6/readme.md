<div align="center">
  <h1 style="text-align: center;font-weight: bold">Praktikum 4B<br>Sistem Operasi</h1>
  <h4 style="text-align: center;">Dosen Pengampu : Dr. Ferry Astika Saputra, S.T., M.Sc.</h4>
</div>
<br />
<div align="center">
  <img src="https://upload.wikimedia.org/wikipedia/id/4/44/Logo_PENS.png" alt="Logo PENS">
  <h3 style="text-align: center;">Disusun Oleh : </h3>
  <p style="text-align: center;">
    <strong>Fauzan Abderrasheed (3123500020) </strong><br>
    <strong>Muhammad Rafi Dhiyaulhaq (3123500004) </strong><br>
    <strong>Arva Zaki Fanadzan (3123500014)</strong>
  </p>
<h3 style="text-align: center;line-height: 1.5">Politeknik Elektronika Negeri Surabaya<br>Departemen Teknik Informatika Dan Komputer<br>Program Studi Teknik Informatika<br>2023/2024</h3>
  <hr><hr>
</div>

<h1 style="text-align: center;font-weight: bold">Proses dan Manajemen Proses</h1>


### Percobaan 5 : Menghentikan dan Memulai Kembali Job

1. Instruksi `yes > /dev/null`

    ![App Screenshot](img/pcb5/yes-dev-null-z.png)

    Analisa : 
    Cara lain meletakkan job pada background dengan memulai job secara normal (pada foreground), stop job dan memulai lagi pada background. Gunakan perintah `yes > /dev/null` untuk memulai job baru. Hentikan sementara job (suspend), bukan menghentikannya (terminate), tetapi menghentikan sementara job sampai di restart. Untuk menghentikan sementara job gunakan *Ctrl + Z*

2. Instruksi `fg`

    ![App Screenshot](img/pcb5/fg.png)

    Analisa : 
    Perintah `fg` disini digunakan untuk me-restart job pada *foreground*.

3. Instruksi `bg`

    ![App Screenshot](img/pcb5/bg.png)

    Analisa : 
    Setelah instruksi `fg`, Shell akan menampilkan nama perintah yang diletakkan di *foreground*. Stop job lagi dengan *Ctrl + Z*. Kemudian gunakan perintah `bg` untuk meletakkan job pada *background*. 
     
    Instruksi `fg`

    ![App Screenshot](img/pcb5/fg-2.png)

    Analisa : 
    Job tidak bisa dihentikan dengan *Ctrl + Z* karena job berada pada *background*. Untuk menghentikannya, letakkan job pada *foreground* dengan `fg` dan kemudian hentikan sementara dengan *Ctrl + Z*.

4. Instruksi `yes &`

    ![App Screenshot](img/pcb5/yes-&.png)

    Analisa : 
    Job pada *background* dapat digunakan untuk menampilkan teks pada terminal, dimana dapat diabaikan jika mencoba mengerjakan job lain seperti perintah di atas. Untuk menghentikannya tidak dapat menggunakan *Ctrl + C*. Job harus dipindah ke *foreground* baru diberhentikan dengan cara tekan `fg` dan tekan enter, Kemudian lanjutkan dengan *Ctrl + Z* untuk menghentikan sementara

5. Instruksi `fg %2`, `bg %2` atau `%2`

    ![App Screenshot](img/pcb5/fg-bg-2.png)

    Analisa : 
    Perintah di atas digumakan apabila ingin menjalankan banyak job dalam satu waktu, letakkan job pada *foreground* atau *background* dengan memberikan job ID. 

6. Instruksi `fg`

    ![App Screenshot](img/pcb5/fg-3.png)

    Analisa : 
    tekan `fg` dan tekan *Enter*, kemudian dilanjutkan dengan *Ctrl-Z* untuk menghentikan sementara

7. Instruksi `ps -fae`

    ![App Screenshot](img/pcb5/ps-fae.png)

    ![App Screenshot](img/pcb5/kill-9-PID.png)

    ![App Screenshot](img/pcb5/killed-9-PID.png)

    Analisa : 
    Lihat job dengan perintah `ps -fae` dan tekan Enter. Kemudian hentikan proses dengan perintah kill. Pada proses di atas proses yang dihentikan adalah proses dengan PID 6142, yaitu proses `yes > /dev/null`

8. Logout dan tekan Alt+F7 untuk kembali ke mode grafis

### Percobaan 6 : Percobaan dengan Penjadwalan Prioritas

1. Login sebagai root

2. Buka 3 terminal, tampilkan pada screen yang sama. 

    ![App Screenshot](img/pcb6/login-root.png)

3. Pada setiap terminal, ketik `PS1 = ” \w:”` diikuti Enter. `\w` menampilkan path pada direktori home.

    ![App Screenshot](img/pcb6/ps1-w.png)

4. Karena login sebagai root, maka akan ditampilkan `~:` pada setiap terminal. Untuk setiap terminal ketik `pwd` dan tekan *Enter* untuk melihat bahwa Anda sedang berada pada direktori `/root`.

    ![App Screenshot](img/pcb6/pwd.png)

5. Buka terminal lagi (keempat), atur posisi sehingga keempat terminal terlihat pada screen

    ![App Screenshot](img/pcb6/4-terminal.png)

6. Pada terminal keempat, ketik `top` dan tekan *Enter*. Maka program `top` akan muncul. Ketik `i`. Top akan menampilkan proses yang aktif. Ketik `lmt`. `Top` tidak lagi menampilkan informasi pada bagian atas dari screen. Pada percobaan ini, terminal ke empat sebagai jendela `Top`.

    ![App Screenshot](img/pcb6/top.png)

    ![App Screenshot](img/pcb6/top-i.png)

    ![App Screenshot](img/pcb6/top-lmt.png)

7. Pada terminal 1, bukalah program executable C++ dengan mengetik program `yes` dan tekan *Enter*.

    ![App Screenshot](img/pcb6/terminal-1-yes.png)

8. Ulangi langkah 7 untuk terminal 2

    ![App Screenshot](img/pcb6/terminal-2-yes.png)  

9. Jendela Top akan menampilkan dua program `yes` sebagai proses yang berjalan. Nilai `%CPU` sama pada keduanya. Hal ini berarti kedua proses mengkonsumsi waktu proses yang sama dan berjalan sama cepat. *PID* dari kedua proses akan berbeda, misalnya pada contoh di bawah adalah 2835 dan 2837. Kemudian gunakan terminal 3 (yang tidak menjalankan primes maupun Jendela Top) dan ketik *renice 19 2835* dan diikuti Enter. Hal ini berarti mengganti penjadwalan prioritas dari proses ke 19.

    ![App Screenshot](img/pcb6/terminal-4-2yes.png)  

    ![App Screenshot](img/pcb6/terminal-3-renice.png)  

10. Tunggu beberapa saat sampai program top berubah dan terlihat pada jendela `Top`. Pada kolom `STAT` memperlihatkan `N` untuk proses 2835. Hal ini berarti bahwa penjadwalan prioritas untuk proses 2835 lebih besar (lebih lambat) dari 0. Proses 2837 berjalan lebih cepat.

    ![App Screenshot](img/pcb6/terminal-4-after-renice.png)  

11. Program *top* juga mempunyai fungsi yang sama dengan program `renice`. Pilih Jendela *Top* dan tekan `r`. Program top terdapat prompt PID to renice: tekan 2835 dan tekan Enter. Program top memberikan prompt Renice PID 3148 to value: tekan -19 dan tekan Enter.

    ![App Screenshot](img/pcb6/terminal-4-r.png)  

    ![App Screenshot](img/pcb6/terminal-4-19.png)  

12. Tunggu beberapa saat sampai top berubah dan lihat nilai %CPU pada kedua proses. Sekarang proses 2835 lebih cepat dari proses 2837. Kolom status menunjukkan < pada proses 3148 yang menunjukkan penjadwalan prioritas lebih rendah (lebih cepat) dari nilai 0

    ![App Screenshot](img/pcb6/terminal-4-19-after.png)  

13. Pilih terminal 3 (yang sedang tidak menjalankan yes atau program top) dan ketik nice –n -10 yes dan tekan Enter. Tunggu beberapa saat agar program top berubah dan akan terlihat proses primes ketiga. Misalnya PID nya 2845. Opsi -10 berada pada kolom NI (penjadwalan prioritas).

    ![App Screenshot](img/pcb6/terminal-3-nice-10-yes.png)  

14. Jangan menggunakan mouse dan keyboard selama 10 detik. Program top menampilkan proses yang aktif selain program yes. Maka akan terlihat proses top terdaftar tetapi %CPU kecil (dibawah 1.0) dan konsisten. Juga terlihat proses berhubungan dengan dekstop grafis seperti X, panel dll.

    ![App Screenshot](img/pcb6/terminal-4-proses-top.png)  

15. Pindahkan mouse sehingga kursor berubah pada screen dan lihat apa yang terjadi dengan tampilan top. Proses tambahan akan muncul dan nilai %CPU berubah sebagai bagian grafis yang bekerja. Satu alasan adalah bahwa proses 2834 berjalan pada penjadwalan prioritas tinggi. Pilih jendela Top, ketik `r`. `PID to renice :` muncul prompt. Ketik 2834 dan tekan Enter. `Renice PID 2834 to value:` muncul prompt. Ketik 0 dan tekan Enter. Sekarang pindahkan mouse ke sekeliling screen. Lihat perubahannya

    ![App Screenshot](img/pcb6/terminal-4-top-r.png)  

    ![App Screenshot](img/pcb6/terminal-4-top-r-0.png)  

    ![App Screenshot](img/pcb6/terminal-4-last.png)  

16. Tutup semua terminal window.

17. Logout dan login kembali sebagai user.

### Latihan 

1. Masuk ke tty2 dengan *Ctrl+Alt+F2*. Ketik `ps –au` dan tekan Enter. Kemudian perhatikan keluaran sebagai berikut :

    ![App Screenshot](img/latihan/ps-au.png)

    - Sebutkan nama-nama proses yang bukan root
        - Semua proses kecuali `/bin/login -p--` adalah bukan root 

    - Tulis PID dan COMMAND dari proses yang paling banyak menggunakan CPU time
        - PID : 2653
        - COMMAND : -bash

    - Sebutkan buyut proses dan PID dari proses tersebut
        - `/usr/libexec/gdm-wayland-session` dengan PID 1166

    - Sebutkan beberapa proses daemon
        - Pada beberapa proses yang tampil pada gambar di atas, tidak ada proses daemon.

    - Pada prompt login lakukan hal- hal sebagai berikut :
        `$ csh`
        `$ who`
        `$ bash`
        `$ ls`
        `$ sh`
        `$ ps`

        ![App Screenshot](img/latihan/1-e-prompt.png)

        perintah `$ csh` adalah sebuah shell interaktif yang menawarkan lebih banyak sintaks dibandingkan dengan Bourne Shell. 
        perintah `$ bash` digunakan untuk mengkonversi instruksi yang dimasukkan ke dalam bahasa biner yang dapat dimengerti oleh kernel Linux. 
        perintah `$ ls` digunakan untuk menunjukkan semua file yang terletak dalam direktori aktif.
        perintah `$ sh` adalah singkatan dari Bourne Shell, yang bertindak sebagai interpreter perintah atau shell standar di unix.
        perintah `$ ps` digunakan untuk menampilkan daftar proses yang sedang berlangsung dalam sistem. Tampilan dari perintah ps mencakup empat kolom utama: PID, TTY, TIME, dan CMD.
        Perintah `$ who`digunakan untuk menampilkan daftar pengguna yang saat ini login ke sistem. Ini menampilkan informasi seperti nama pengguna, terminal yang mereka gunakan, waktu login, dan sebagainya. Perintah ini sering digunakan untuk memeriksa siapa yang sedang menggunakan sistem atau untuk melihat apakah ada pengguna yang login secara tidak sah.

    - Sebutkan PID yang paling besar dan kemudian buat urut-urutan proses sampai ke PPID = 1.

        ![App Screenshot](img/latihan/1-f.png)

        1) PID = 2682 -> ps
        2) PID = 2681 -> sh
        3) PID = 2678 -> bash
        4) PID = 2676 -> csh
        5) PID = 2583 -> bash
        6) PID = 2064 -> bash

2. Cobalah format tampilan ps dengan opsi berikut dan perhatikan hasil tampilannya :
    - `-f` daftar penuh

        ![App Screenshot](img/latihan/ps-f.png)  

    - `-j` format job

        ![App Screenshot](img/latihan/ps-j.png)  

    - `j` format job control

        ![App Screenshot](img/latihan/ps_j.png)  

    - `l` daftar memanjang

        ![App Screenshot](img/latihan/ps_l.png) 

    - `s` format sinyal

        ![App Screenshot](img/latihan/ps_s.png)

    - `v` format virtual memory

        ![App Screenshot](img/latihan/ps_v.png)

    - `X` format register i386

        ![App Screenshot](img/latihan/ps_X.png)

3. Lakukan urutan pekerjaan berikut :

    - Gunakan perintah `find` ke seluruh direktory pada sistem, belokkan output sehingga daftar direktori dialihkan ke file `directories.txt` dan daftar pesan error dialihkan ke file `errors.txt`

        ![App Screenshot](img/latihan/2-a.png)

    - Gunakan perintah `sleep 5`. Apa yang terjadi dengan perintah ini ?

        ![App Screenshot](img/latihan/2-b.png)

    - Jalankan perintah pada background menggunakan `&`

        ![App Screenshot](img/latihan/2-c.png)

    - Jalankan `sleep 15` pada foreground, hentikan sementara dengan Ctrl-Z dan kemudian letakkan pada background dengan `bg`. Ketikkan `jobs`. Ketikkan `ps`. Kembalikan job ke foreground dengan perintah `fg`.

        ![App Screenshot](img/latihan/2-d.png)

    - Jalankan `sleep 15` pada background menggunakan `&` dan kemudian gunakan perintah `kill` untuk menghentikan proses diikuti job number.

        ![App Screenshot](img/latihan/2-e.png)

    - Jalankan `sleep 15` pada background menggunakan `&` dan kemudian gunakan `kill` untuk menghentikan sementara proses. Gunakan `bg` untuk melanjutkan menjalankan proses.

        ![App Screenshot](img/latihan/2-f.png)

    - Jalankan `sleep 60` pada background 5 kali dan terminasi semua pada dengan menggunakan perintah `killall`.

        ![App Screenshot](img/latihan/2-g.png)

    - Gunakan perintah `ps`, `w` dan `top` untuk menunjukkan semua proses yang sedang dieksekusi.

        ![App Screenshot](img/latihan/2-h-ps-w.png)

        ![App Screenshot](img/latihan/2-h-top.png)

    - Gunakan perintah `ps –aeH` untuk menampilkan hierarki proses. Carilah init proses. Apakah Anda bisa identifikasi sistem daemon yang penting ? Dapatkan Anda identifikasi shell dan subproses ?

        ![App Screenshot](img/latihan/2-i.png)

        ![App Screenshot](img/latihan/2-i-bash-ps.png)

        ![App Screenshot](img/latihan/2-i-systemd.png)

    - Kombinasikan `ps –fae` dan grep, apa yang Anda lihat ?

        ![App Screenshot](img/latihan/2-j.png)

    - Jalankan proses `sleep 300` pada background. Log off komputer dan log in kembali. Lihat daftar semua proses yang berjalan. Apa yang terjadi pada proses sleep ?

        ![App Screenshot](img/latihan/2-k-sleep.png)

        ![App Screenshot](img/latihan/2-k-ps.png)
