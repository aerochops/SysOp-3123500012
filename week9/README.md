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

## PRODUCER & CONSUMER

### Semaphore
#### Kode: 
    #include<stdio.h>
    #include<stdlib.h>
 
    int mutex=1,full=0,empty=3,x=0;
 
    int main()
    {
        int n;
          void producer();
          void consumer();
          int wait(int);
          int signal(int);
          printf("\n1.Producer\n2.Consumer\n3.Exit");
          while(1)
        {
        printf("\nEnter your choice:");
        scanf("%d",&n);
        switch(n)
        {
          case 1:	if((mutex==1)&&(empty!=0))
                producer();
              else
                printf("Buffer is full!!");
              break;
          case 2:	if((mutex==1)&&(full!=0))
                consumer();
              else
                printf("Buffer is empty!!");
              break;
          case 3:
              exit(0);
              break;
        }
      }
      
      return 0;
    }
 
    int wait(int s)
    {
	  return (--s);
    }
 
    int signal(int s)
    {
	  return(++s);
    }
 
    void producer()
    {
      mutex=wait(mutex);
      full=signal(full);
      empty=wait(empty);
      x++;
      printf("\nProducer produces the item %d",x);
      mutex=signal(mutex);
    }
 
    void consumer()
    {
      mutex=wait(mutex);
      full=wait(full);
      empty=signal(empty);
      printf("\nConsumer consumes item %d",x);
      x--;
      mutex=signal(mutex);
    }
#### Output: 
![App Screenshot](https://github.com/aerochops/SysOp-3123500012/blob/main/week9/media/H_semaphore.png?raw=true)

#### Analisa: 
Pertimbangkan seorang produsen dan seorang konsumen yang berbagi buffer bersama. Produsen menghasilkan item dan menyimpannya di dalam buffer. Konsumen mengonsumsi item dari buffer. Jika buffer penuh, produsen harus menunggu. Jika buffer kosong, konsumen harus menunggu.

## Semafor

Dalam kode ini, mutex adalah semafor biner yang digunakan untuk melindungi buffer bersama dari akses bersamaan oleh produsen dan konsumen. Semafor mutex diinisialisasi menjadi 1, yang berarti tersedia untuk digunakan.

full dan empty adalah semafor hitungan yang menunjukkan jumlah item dalam buffer. Semafor full diinisialisasi menjadi 0, menunjukkan bahwa buffer awalnya kosong. Semafor empty diinisialisasi menjadi 3, menunjukkan bahwa buffer dapat menampung hingga 3 item.

## Fungsi Produsen

Fungsi produsen menghasilkan item dan menyimpannya di dalam buffer. Sebelum menghasilkan item, produsen memeriksa apakah semafor mutex tersedia dan semafor empty lebih besar dari 0. Jika kedua kondisi tersebut terpenuhi, produsen melanjutkan untuk menghasilkan item dan memperbarui nilai semafor secara sesuai.

## Fungsi Konsumen

Fungsi konsumen mengonsumsi item dari buffer. Sebelum mengonsumsi item, konsumen memeriksa apakah semafor mutex tersedia dan semafor full lebih besar dari 0. Jika kedua kondisi tersebut terpenuhi, konsumen melanjutkan untuk mengonsumsi item dan memperbarui nilai semafor secara sesuai.

## Fungsi Utama

Fungsi utama mengimplementasikan menu untuk pengguna memilih opsi. Pengguna dapat memilih untuk menambahkan item ke buffer (produsen), menghapus item dari buffer (konsumen), atau keluar dari program.

Sebelum menambahkan atau menghapus item, program memeriksa apakah semafor mutex tersedia dan semafor yang sesuai (full atau empty) lebih besar dari 0. Jika kedua kondisi tersebut terpenuhi, operasi dilakukan, dan pengguna kembali ke menu. Jika kondisinya tidak terpenuhi, pesan yang sesuai ditampilkan kepada pengguna.

## Keterbatasan Kode

Implementasi masalah produsen-konsumen ini memiliki beberapa keterbatasan. Pertama, kode ini mengasumsikan bahwa buffer dapat menampung jumlah item yang tetap (3 dalam hal ini). Kedua, program tidak mengimplementasikan thread terpisah untuk produsen dan konsumen, yang berarti produsen dan konsumen tidak dapat berjalan secara bersamaan. Terakhir, kode tidak termasuk mekanisme apa pun untuk menangani situasi di mana produsen menghasilkan item lebih cepat dari konsumen mengonsumsinya, yang mengakibatkan penumpukan item di dalam buffer. Untuk mengatasi keterbatasan ini, implementasi yang lebih kompleks menggunakan thread dan buffer terpisah akan diperlukan.

### Wake-Sleep thread
#### Kode: 
    #include<stdio.h>
    #include<stdlib.h>

    int mutex = 1, full = 0, empty = 3, x = 0;

    int wait(int);
    int signal(int);
    void producer();
    void consumer();

    int main() {
        int n;
        printf("\n1.Producer\n2.Consumer\n3.Exit");

        while (1) {
            printf("\nEnter your choice:");
            scanf("%d", &n);
            switch (n) {
                case 1:
                    if ((mutex == 1) && (empty != 0))
                        producer();
                    else
                        printf("Buffer is full!!");
                    break;
                case 2:
                    if ((mutex == 1) && (full != 0))
                        consumer();
                    else
                        printf("Buffer is empty!!");
                    break;
                case 3:
                    exit(0);
                    break;
            }
        }

        return 0;
    }

    int wait(int s) {
        return (--s);
    }

    int signal(int s) {
        return (++s);
    }

    void producer() {
        mutex = wait(mutex);
        full = signal(full);
        empty = wait(empty);
        x++;
        printf("\nProducer produces the item %d", x);
        mutex = signal(mutex);
    }

    void consumer() {
        mutex = wait(mutex);
        full = wait(full);
        empty = signal(empty);
        printf("\nConsumer consumes item %d", x);
        x--;
        mutex = signal(mutex);
    }


#### Output: 
![App Screenshot](https://github.com/aerochops/SysOp-3123500012/blob/main/week9/media/H_wake-sleep-thread.png?raw=true)

#### Analisa: 
Penjelasan Kode: Masalah Produsen-Konsumen dengan Pthreads

Kode ini mengimplementasikan masalah produsen-konsumen menggunakan POSIX threads (pthreads) dan condition variables. Masalah produsen-konsumen adalah masalah sinkronisasi klasik dalam ilmu komputer, di mana satu thread (produsen) menghasilkan item dan thread lainnya (konsumen) mengonsumsinya.
Variabel Global

Kode ini mendefinisikan beberapa variabel global:

    mutex: mutex (kependekan dari "mutual exclusion") yang melindungi bagian kritis kode tempat produsen dan konsumen mengakses sumber daya bersama.

    cond: condition variable yang memungkinkan thread menunggu kondisi tertentu terjadi.

    condition: flag boolean yang menunjukkan apakah suatu item telah diproduksi dan siap dikonsumsi.
    count: bilangan bulat yang melacak jumlah item yang diproduksi.

    NUM_TO_PRODUCE: konstanta yang menentukan jumlah item yang akan diproduksi.

## Fungsi Utama (Main Function)

Fungsi utama membuat dua thread: thread produsen dan thread konsumen. Ini menginisialisasi mutex dan condition variable menggunakan pthread_mutex_init dan pthread_cond_init, masing-masing. Kemudian, ia membuat thread produsen dan konsumen menggunakan pthread_create. Terakhir, ia menunggu kedua thread selesai menggunakan pthread_join.
Thread Produsen (Producer Thread)

Fungsi Produce adalah fungsi thread untuk thread produsen. Ini berjalan dalam loop tak terbatas hingga variabel count mencapai NUM_TO_PRODUCE. Berikut tindakan thread produsen:

    Mengunci mutex menggunakan pthread_mutex_lock untuk melindungi bagian kritis kode.

    Memeriksa apakah suatu item telah diproduksi dan belum dikonsumsi (yaitu, condition bernilai true). Jika demikian, ia menunggu pada condition variable menggunakan pthread_cond_wait hingga thread konsumen membangunkannya.

    Memproduksi item dengan menambah variabel count dan mencetak pesan ke konsol.

    Mengatur flag condition ke true untuk menunjukkan bahwa suatu item siap dikonsumsi.

    Memberi sinyal pada thread konsumen menggunakan pthread_cond_signal untuk membangunkannya.

    Membuka kunci mutex menggunakan pthread_mutex_unlock.

## Thread Konsumen (Consumer Thread)

Fungsi Consume adalah fungsi thread untuk thread konsumen. Ini berjalan dalam loop tak terbatas hingga variabel count mencapai NUM_TO_PRODUCE. Berikut tindakan thread konsumen:

    Mengunci mutex menggunakan pthread_mutex_lock untuk melindungi bagian kritis kode.

    Memeriksa apakah ada item yang tersedia untuk dikonsumsi (yaitu, condition bernilai true). Jika tidak, ia menunggu pada condition variable menggunakan pthread_cond_wait hingga thread produsen membangunkannya.

    Mengonsumsi item dengan mencetak pesan ke konsol.

    Mengatur flag condition ke false untuk menunjukkan bahwa item telah dikonsumsi.

    Memberi sinyal pada thread produsen menggunakan pthread_cond_signal untuk membangunkannya.

    Membuka kunci mutex menggunakan pthread_mutex_unlock.

## Sinkronisasi

Kunci dari implementasi ini adalah penggunaan mutex dan condition variable untuk mensinkronisasi akses ke sumber daya bersama. Mutex memastikan bahwa hanya satu thread yang dapat mengakses bagian kritis kode pada satu waktu, sementara condition variable memungkinkan thread untuk menunggu kondisi tertentu terjadi.
Keluaran (Output)

Program akan menampilkan urutan pesan "Diproduksi" dan "Dikonsumsi", yang menunjukkan bahwa thread produsen dan konsumen berjalan secara bersamaan dan disinkronkan dengan benar.  Output yang tepat dapat bervariasi tergantung pada penjadwalan thread oleh sistem operasi.
Batasan (Limitations)

Implementasi ini memiliki beberapa keterbatasan. Misalnya, diasumsikan bahwa thread produsen dan konsumen berjalan pada proses yang sama dan berbagi ruang memori yang sama. Ini juga mengasumsikan bahwa thread produsen dan konsumen adalah satu-satunya thread yang mengakses sumber daya bersama. Dalam skenario dunia nyata, mungkin ada thread lain yang mengakses sumber daya bersama, dan mekanisme sinkronisasi tambahan mungkin diperlukan.

 ### Referensi
 https://www.geeksforgeeks.org/producer-consumer-problem-in-c/

