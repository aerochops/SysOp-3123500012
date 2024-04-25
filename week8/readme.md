<div align="center">
  <h1 style="text-align: center;font-weight: bold">Praktikum 8<br>Praktek Sistem Operasi</h1>
  <h4 style="text-align: center;">Dosen Pengampu : Dr. Ferry Astika Saputra, S.T., M.Sc.</h4>
</div>
<br />
<div align="center">
  <img src="https://upload.wikimedia.org/wikipedia/id/4/44/Logo_PENS.png" alt="Logo PENS">
  <h3 style="text-align: center;">Disusun Oleh : </h3>
  <p style="text-align: center;">
    <strong>Fikri Athanabil Effendi (3123500012) </strong><br>
    <strong>Danur Isa Prabutama (3123500023) </strong><br>
    <strong>Achmad Risel Araby (3123500025)</strong>
  </p>
<h3 style="text-align: center;line-height: 1.5">Politeknik Elektronika Negeri Surabaya<br>Departemen Teknik Informatika Dan Komputer<br>Program Studi Teknik Informatika<br>2023/2024</h3>
  <hr><hr>
</div>

## Bash Programming 

### Apa itu bash?

Bash, kependekan dari Bourne Again Shell, adalah open source command line interpreter dan scripting language. Ini menafsirkan perintah yang dimasukkan pengguna, baik secara interaktif atau dari file skrip.

Ini berfungsi sebagai interface untuk memanggil perintah, memungkinkan system function calls.

Ada 2 tipe dari mode bash

- **Interactive Mode**
    Juga disebut sebagai command intepreter, memungkinkan eksekusi perintah di terminal. Ini mengeksekusi perintah secara berurutan jika ada beberapa perintah.

- **Non-interactive Mode**
    Ini merujuk pada scrpts, memungkinkan Anda menulis Bash syntax yang berisi rangkaian beberapa perintah untuk eksekusi skrip.

### Apa Perbedaan dari Bash dan Shell

Shell, an alias for Bourne Shell, adalah command-line interpreter untuk OS Unix dan Linux. Bash, alias Bourne Again Shell, adalah versi yang disempurnakan.

### Untuk apa skrip bash digunakan?

Skrip Bash memiliki banyak kasus penggunaan, termasuk:
- Menulis skrip untuk mengotomatiskan tugas pemrograman
- Menyinkronkan tugas untuk menyalin file
- Menjalankan tugas cron untuk penjadwalan

### Bagaimana cara menulis kode di bash?

Untuk menulis kode dalam skrip Bash, ikuti langkah-langkah berikut:
- Di terminal, buat file menggunakan `vi test.sh`.
- Tambahkan `#!/bin/bash` di bagian atas file.
- Tambahkan beberapa cuplikan kode shell.
- Simpan file shell dengan `.sh` ekstensi.
- Jalankan skrip shell menggunakan `./test.sh` perintah di terminal.

### Apakah bash termasuk bahasa pengkodean?

Bash menjalankan perintah dari terminal atau file. Ini adalah bahasa pemrograman yang beroperasi pada sistem operasi kernel Unix/Linux, berisi semua fitur untuk menulis kode lengkap.

Bash adalah tipe shell khusus yang menerima masukan dari perintah, menjalankan kode, dan memproses masukan, serta mengembalikan hasilnya.

### Jenis Shell

Ada berbagai jenis shell di OS Unix.

<table>
<thead>
<tr>
  <th style="background-color: blue; color: white">Tipe Cangkang</th>
  <th style="background-color: blue; color: white">Alias</th>
  <th style="background-color: blue; color: white">Garis Pertama</th>
<tr>
</thead>
<tbody>
  <tr>
  <td>SH</td>
  <td>Bourne Shell</td>
  <td>#!/bin/sh</td>
  </tr>
   <tr>
  <td>bash</td>
  <td>Bourne Again Shell</td>
  <td>#!/bin/bash</td>
  </tr>
   <tr>
  <td>cshell</td>
  <td>C shel</td>
  <td>#!/bin/csh</td>
  </tr>
</tbody>
</table>

| tcsh | TENEX C shell | #!/bin/tcsh | | | | ksh | Korn shell | #!/bin/ksh |

### Perbedaan dari Command Line dan Script di bash

Mari kita lihat perbedaan antara baris perintah dan skrip

Opsi baris perintah

- Baris perintah memiliki prompt yang menerima masukan dari pengguna
- Perintah tidak disimpan ke file.
- Ini hanya mendukung satu perintah pada satu waktu.

File skrip

- Mendukung banyak perintah dalam satu file
- Prompt masih dapat ditulis dalam file skrip
- Hanya satu baris dalam sebuah file yang dijalankan secara berurutan

## Bash - Variables

**Deklarasi Variable**: Untuk membuat variable, maka harus memberikan nilai padanya

``` 
variableName=VariableValue
```

Keterangan: 

- variableName: dapat berisi kombinasi huruf apa saja, angka, dan garis bawah
- variableValue: adalah nilai yang disimpan dalam variabel, dan dapat berupa angka, string atau boolean. Simbol `=` digunakan untuk memberikan nilai pada suatu variabel.

Misalnya

```
AGE=25
```

### Cara mengakses variabel di bash

![App Screenshot](img/variable/var-access.png)

Pertama adalah mendeklarasikan variable *AGE* dengan memberikan nilai 25. Kemudian menggunakan `echo` untuk menampilkan outputnya. Simbol dollar `$` sebelum nama variable sangat penting untuk mengakses nilainya.

![App Screenshot](img/variable/var-access-output.png)

### Bash Shell readonly variables

![App Screenshot](img/variable/var.png)

Setelah variabel diberi nilai, kita dapat mengubahnya ke nilai baru menggunakan operator penugasan =

![App Screenshot](img/variable/var-output.png)

**Membuat Variable tidak dapat diperbarui**

![App Screenshot](img/variable/var-readonly.png)

keyword `readonly` mencegah variable untuk diperbarui, secara efektif mengubahnya menjadi `constant`.

![App Screenshot](img/variable/var-readonly-output.png)

### Bash Unset Variable

Keyword `unset` membantu menghilangkan nilai dari variable yang ditentukan. Variable tetap dapat diakses tetapi mencetak nilai kosong.

![App Screenshot](img/variable/var-unset.png)

Output:

![App Screenshot](img/variable/var-unset-output.png.png)

### Variables Scope

Setiap variabel yang dideklarasikan harus memiliki ruang lingkup, yang menentukan di mana variabel tersebut dapat digunakan dalam program.

Misalnya, jika suatu variabel dideklarasikan di dalam suatu fungsi, maka variabel tersebut hanya tersedia di dalam fungsi tersebut dan tidak dapat diakses di luar fungsi tersebut.

Cakupan variabel di Bash dapat didefinisikan dengan dua cara

- Variabel global
- Variabel lokal

### Variable Global Bash

### Bash Local Bash

### Variables Typing

### Display Environment 

### Variable nameing covention

### Shell variables

## Bash - Loop File

Terkadang kita ingin membaca konten file menggunakan bash programming. 
Ada berbagai macam cara yang dapat kita lakukan

### Bagaimana cara membaca file demi baris di bash Shell?
- menggunakan perulangan while

![App Screenshot](img/loop-file/loop-sh.png)

Output

![App Screenshot](img/loop-file/loop-sh-output.png)

Output diatas merupakan isi dari file `filename.txt` 

![App Screenshot](img/loop-file/loop-txt.png)

## Bash - Comments

Posting ini menjelaskan cara menulis komentar dalam skrip bash shell, dengan contoh yang menyertainya.

`Comments` adalah pernyataan kode yang berisi teks yang dapat dibaca pengguna yang dilewati shell selama eksekusi. Setiap bahasa pemrograman menyertakan fitur komentar, yang memberikan deskripsi baris kode atau pernyataan.

Komentar sebaris dalam kode membantu pengembang dalam mengedit dan memahami kode dengan lebih baik.

Bahasa script bash memungkinkan anda menggunakan jenis komentar berikut.

- **Komentar tunggal**
- **Komentar multi-baris**

Komentar berguna bagi manusia, kode ditulis untuk scripting

### Komentar satu baris di bash shell 

Komentar satu baris dalam skrip shell dilambangkan dengan `#` simbol di awal setiap baris.

Komentar ini mencakup string yang memberikan informasi tentang baris kode terkait dalam skrip shell.

Penting untuk menempatkan komentar satu baris pada baris terpisah untuk kejelasan.

Untuk komentar sebaris, gunakan simbol `#` di awal komentar. Komentar satu baris selalu dimulai dengan `#` simbol.

**Syntax:**

```
# Single-line comments
```

Spasi kosong setelah `#` simbol tidak diperlukan. Berikut ini adalah contoh komentar satu baris dalam skrip shell.

![App Screenshot](img/comment/comment-single.png)

Output

![App Screenshot](img/comment/comment-single-output.png)

### Komentar multi-baris dalam skrip shell

Komentar multi-baris melibatkan penggunaan lebih dari satu baris untuk komentar.

Cara pertama untuk membuat komentar multi-baris adalah dengan memanfaatkan komentar satu baris yang setiap barisnya dimulai dengan simbol komentar satu baris.

Syntax: 

![App Screenshot](img/comment/comment-multi-1.png)

Cara kedua untuk membuat komentar multi-baris adalah dengan mengapit beberapa baris di dalam (`:`) dan (`'`).

Sintaks ini melibatkan:

- Komentar dimulai dengan titik dua (`:`) diikuti dengan `'`.
- Ini diikuti oleh beberapa baris komentar.
- Komentar diakhiri dengan `'`. Berikut sintaksnya:

![App Screenshot](img/comment/comment-multi-2.png)

Output:

![App Screenshot](img/comment/comment-multi-output.png)

Hal ini berguna untuk memasukkan lebih banyak teks yang mencakup beberapa baris, juga melayani tujuan dokumentasi.

### Kesimpulan
Singkatnya, kita telah mempelajari cara menambahkan komentar tunggal dan multi-baris dalam pemrograman skrip shell.

## Bash - Arrays

Array di shells adalah variable untuk menyimpan lebih dari satu nilai/data.
Misal ketika memiliki data daftar bilangan integer 1-100, dan ingin menyimpan bilangan-bilangan ini di shell script, tanpa array kita harus mendeklarasikannya satu persatu / baris per baris menggunakan `let number1=1` dst. Jadi, anda bisa menggunakan array yang merujuk ke satu variabel dan menyimpannya.

### Bagaimana cara mendeklarasikan dan membuat array?

Ada 2 jenis array yang dapat kita buat
- array yang diindeks: elemen array disimpan dengan indeks mulai dari nol
- array terkait: array disimpan dengan pasangan nilai kunci

**Deklarasi sebuah array**

Untuk membuat array, kita perlu mendeklarasikan array.
```
declares -a array; # indexed array
declare -A array; # associative array
```
Sebuah array dideklarasikan dengan kata kunci declaredengan opsi `-a` atau `A`

**Menetapkan nilai tanpa mendeklarasikan Array**

```
arrayvariable[index]=value
```
Artinya, `arrayvariable[indeks]` array dideklarasikan dan diberi nilai.

Array diindeks nol berdasarkan nol pada panjang array -1 indeks=0 - mengembalikan elemen pertama indeks=-1 mengembalikan elemen terakhir

Array bisa berisi angka, string, dan campurannya. Mari kita buat contoh array.

### Akses nilai Array

Array berisi indeks untuk mendapatkan elemen. Elemen array dapat diakses menggunakan sintaks di bawah ini.

```
${array_name[index]}
```

### Deklarasi Array angka dan Loop

Array dapat berisi angka Contoh ini berisi array angka dan loop for untuk dicetak

![App Screenshot](img/array/numbers-loop-through.png)

Output:

![App Screenshot](img/array/numbers-loop-through-output.png)

### Deklarasi Array string dan Loop

Array dapat berisi angka Contoh ini berisi array angka dan loop for untuk dicetak

![App Screenshot](img/array/strings-loop-through.png)

Output:

![App Screenshot](img/array/strings-loop-through-output.png)

### Akses elemen pertama array

Dalam elemen Array, indeks elemen Pertama adalah nol, dan array[0] mengembalikan elemen pertama

![App Screenshot](img/array/first-element.png)

Output:

![App Screenshot](img/array/first-element-output.png)

### Dapatkan element terakhir dalam sebuah array

Dalam skrip bash, Anda dapat menggunakan indeks=-1 untuk mendapatkan elemen array terakhir.

![App Screenshot](img/array/last-element-1.png)

Dengan versi bash 4.0 terbaru, Anda dapat menggunakan sintaks di bawah ini untuk membaca elemen terakhir.

![App Screenshot](img/array/last-element-2.png)

Output:

![App Screenshot](img/array/last-element-output.png)

### Iterate atau Loop element array

For loop digunakan untuk mengulangi elemen.

Berikut adalah contoh contoh loop array untuk mencetak semua elemen

![App Screenshot](img/array/iterate-loop.png)

Output:

![App Screenshot](img/array/iterate-loop-output.png)

Cara lain untuk mencetak indeks dan elemen array menggunakan for loop.

![App Screenshot](img/array/iterate-loop-2.png)

Output:

![App Screenshot](img/array/iterate-loop-2-output.png)

### Cetak semua elemen array

Gunakan [@] atau [*] untuk mencetak semua elemen array.

![App Screenshot](img/array/print-all.png)

Output:

![App Screenshot](img/array/print-all-output.png)

### Hapus elemen dari array

Anda dapat menghapus elemen dari array menggunakan `unset` indeks tertentu.

![App Screenshot](img/array/remove-element.png)

Output:

![App Screenshot](img/array/remove-element-output.png)

### Menambahkan elemen ke array

Anda dapat menambahkan elemen di posisi indeks mana pun menggunakan sintaksis di bawah ini.

```
array[index]=value
```

Contoh penambahan elemen awal dan akhir serta tengah

![App Screenshot](img/array/add-element.png)

Output:

![App Screenshot](img/array/add-element-output.png)

### Panjang sebuah array

Dalam hal ini, Temukan jumlah semua elemen dalam array.

Script Shell menyediakan `#`

![App Screenshot](img/array/length-of-array.png)

Output:

![App Screenshot](img/array/length-of-array-output.png)

### Array cheat sheet

<table>
<thead>
<tr>
  <th style="background-color: blue; color: white">Example</th>
  <th style="background-color: blue; color: white">Description</th>
<tr>
</thead>
<tbody>
    <tr>
        <td>Sdeclare -a array	</td>
        <td>Declare an Indexed array</td>
    </tr>
    <tr>
        <td>declare -A array	</td>
        <td>Declare an Associative array</td>
    </tr>
    <tr>
        <td>declare -a array=()	</td>
        <td>Declare an indexed array with empty array</td>
    </tr>
    <tr>
        <td>array=()</td>
        <td>create an empty array with declaring is valid</td>
    </tr>
    <tr>
        <td>array=(1 6 3)</td>
        <td>Initialize array with numbers</td>
    </tr>
    <tr>
        <td>array=(one two three)</td>
        <td>Initialize the array with string</td>
    </tr>
    <tr>
        <td>array=(one two 1)</td>
        <td>Initialize the array with mixed data</td>
    </tr>
    <tr>
        <td>${array[0]}</td>
        <td>Get first element</td>
    </tr>
    <tr>
        <td>${array[1]}</td>
        <td>Get second element</td>
    </tr>
    <tr>
        <td>${array[-1]}</td>
        <td>Get last element</td>
    </tr>
    <tr>
        <td>${array[@]}</td>
        <td>Get All element</td>
    </tr>
    <tr>
        <td>${array[*]}</td>
        <td>Get All element</td>
    </tr>
    <tr>
        <td>${!array[!]}</td>
        <td>Get All indexes</td>
    </tr>
    <tr>
        <td>${#array[!]}</td>
        <td>Array length</td>
    </tr>
    <tr>
        <td>array[0]=12</td>
        <td>Add element to array at first position.i.e index=0</td>
    </tr>
    <tr>
        <td>array[-1]=22</td>
        <td>Add element to array at last position.</td>
    </tr>
    <tr>
        <td>array+=(11)</td>
        <td>Append value to an array</td>
    </tr>
    <tr>
        <td>${array[@]:k:i}</td>
        <td>Get index=1 element starting from index=k</td>
    </tr>
</tbody>
</table>

## Bash - Expansion

Tutorial ini menjelaskan cara menulis skrip batch dalam skrip shell dan menjalankannya.

perintah dimasukkan ke OS untuk membuat panggilan sistem dan melakukan tindakan. perintah masukan pengguna di terminal untuk melakukan operasi seperti ls, cd, mkdir dll.

Cara lain, Beberapa perintah dapat ditempatkan dalam satu file, juru bahasa bash membaca perintah dan menjalankannya

Cara menulis skrip shell di bash

- Pilih Editor atau editor teks
- Buat file dengan ekstensi .sh atau .bash
- Tulis perintah dalam file
- Simpan file sebagai `hello.sh`

![App Screenshot](img/expansion/expansion.png)

Output:

![App Screenshot](img/expansion/execute.png)

## Bash - Conditional Expression

Ekspresi kondisional dievaluasi pada waktu eksekusi skrip, berdasarkan hasil, Ia mengeksekusi blok perintah tertentu.

ini

Ada berbagai jenis ekspresi konisional di Bash

- Operator Perbandingan String
- Operator Perbandingan Numerik
- Operator File
- Operator Logis

### Operator File
Bash menyediakan operator logika pada FIle dan direktori untuk menguji ekspresi kondisional. Ini memungkinkan Anda untuk memeriksa berbagai operasi seperti keberadaan, dan izin, ukuran. Ini digunakan ekspresi kondisional dalam pernyataan kondisional seperti if else dan case.

Syntax:

![App Screenshot](img/conditional-expression/code.png)

Output:

![App Screenshot](img/conditional-expression/output.png)

conditional_expressions berisi opsi, dan jalur file, yang selalu mengembalikan nilai benar atau salah.

berikut adalah opsi yang disediakan

<table>
<thead>
<tr>
  <th style="background-color: blue; color: white">Example</th>
  <th style="background-color: blue; color: white">Description</th>
<tr>
</thead>
<tbody>
    <tr>
        <td>-e file</td>
        <td>Returns true if given file exists, file can be normal file or directory</td>
    </tr>
    <tr>
        <td>-f file</td>
        <td>Returns true if given file exists and a file(not directory)<td>
    </tr>
    <tr>
        <td>-d file</td>
        <td>Returns true if file is an directory</td>
    </tr>
    <tr>
        <td>-r file</td>
        <td>Returns true if file exists and has readable permission</td>
    </tr>
    <tr>
        <td>-w file</td>
        <td>Returns true if given file exists, file can be normal file or directory</td>
    </tr>
    <tr>
        <td>-x file</td>
        <td>Returns true if file exists and has writable permission</td>
    </tr>
    <tr>
        <td>-s file</td>
        <td>Returns true if file exists and size is not empty</td>
    </tr>
    <tr>
        <td>-G file</td>
        <td>Returns true if file exists and isowned by a Group ID that matches</td>
    </tr>
    <tr>
        <td>-O file</td>
        <td>Returns true if file exists and owned by a user ID that matches</td>
    </tr>
    <tr>
        <td>-N file</td>
        <td>Returns true if file exists and modified by last read date</td>
    </tr>
    <tr>
        <td>-L file</td>
        <td>Returns true if file exists and and is an symbolic Link</td>
    </tr>
    <tr>
        <td>file1 -ot file2</td>
        <td>Returns true if file1 is older than file2 or file2 exists, file1 does not exist</td>
    </tr>
    <tr>
        <td>file1 -ne file2</td>
        <td>Returns true if file1 is newer than file2,file1 exists, file2 does not exists</td>
    </tr>
    <tr>
        <td>file1 -ef file2</td>
        <td>Returns true if file1 and file2 pointed to same device and inode</td>
    </tr>
</tbody>
</table>

## Bash - Case Statements

pernyataan case mirip dengan switch case dalam bahasa pemrograman lain.

Ini digunakan untuk membandingkan masukan yang diberikan dengan beberapa pola, dan perintah di dalam pola yang cocok dijalankan.

Syntax:

```
case expression in

pattern1)
  ## Commands
  ;;
pattern1)
  ## Commands
  ;;
*)
  ## Default case to execute if none of the pattern is matched
  ;;
```

- expression adalah variabel atau expression yang valid untuk dievaluasi
- Ini berisi pola defiend di dalam case yang dievaluasi dengan membandingkan expression, mencocokkan case fuound, mengeksekusi perintah di dalamnya.
- case default ( `*)`) untuk dijalankan jika tidak ada pola yang cocok
- Setiap blok pola diakhiri dengan `;;`
`case` adalah kata awal dan `esac` merupakan kata yang mengakhiri pernyataan kasus

Contohnya sebagai berikut:

![App Screenshot](img/case-statements/code.png)

Output:

![App Screenshot](img/case-statements/output.png)

## Bash - Special Characters

## Bash - if elif else

### Conditional Statement Bash Shell

Terkadang, Anda mungkin perlu mengeksekusi beragam blok kode bergantung pada berbagai keputusan berdasarkan kondisi tertentu.

Skrip Bash memfasilitasi hal ini melalui pernyataan kondisional

```
  if condition; then
     # true code
  elif another_condition; then
     # condition is false, and another_condition is true
  else
     # none of the above conditions are true
  fi
```

- Pernyataan tersebut `if` digunakan untuk mengeksekusi blok kode jika suatu kondisi benar, dengan syntax `if then fi`.
- Pernyataan ini `else` digunakan untuk mengeksekusi kode jika suatu kondisi salah, mengikuti syntax `if then else fi`.
- Pernyataan ini `if..elif..else` berguna ketika Anda perlu mengeksekusi kode jika tidak ada kondisi sebelumnya yang benar. Syntaxnya adalah sebagai berikut:

Catatan:

- Kondisi adalah ekspresi yang mengevaluasi `true` atau `false` dalam skrip shell.
- Spasi diperlukan sebelum dan sesudah [ dan ].
- Diperlukan titik koma sebelum itu.
- `if`, `else`, `then`, `elif`, `fi` adalah kata-kata khusus di Bash.
- Kondisi adalah ekspresi dengan perintah.
    - Perintah yang berisi sintaks tanda kurung tunggal, contoh sintaksis `[expression]` dan digunakan untuk operasi string file.
    - Sintaks tanda kurung ganda, contohnya adalah `[[expression]]`, yang digunakan untuk menggabungkan beberapa kondisi dan menangani pola regex.
    - Tanda kurung ganda, contoh sintaksnya adalah `((expression))`, digunakan untuk operasi aritmatika

### If Conditional Statements

Pernyataan `if` di Bash digunakan untuk mengeksekusi blok kode ketika kondisi tertentu adalah `true`.

```
if [ condition ]; then
   # Execute code block if the condition is true
fi
```

Dalam sintaks di atas:

- Ganti `[ condition ]` dengan ekspresi kondisional.
- Blok kode dalam pernyataan `if` dieksekusi hanya jika kondisi yang ditentukan bernilai benar.
- Setiap `if` pernyataan harus diakhiri dengan `fi`.

Contoh

![App Screenshot](img/if-elif-else/if-code.png)

Output:

![App Screenshot](img/if-elif-else/if-output.png)

### If-else Conditional Statements

Pernyataan `if-else` kondisional di Bash memungkinkan Anda untuk mengeksekusi blok kode yang berbeda tergantung pada apakah suatu kondisi `true` atau `false`.

```
if [ condition ]; then
   # Execute code block if the condition is true
else
   # Execute code block if the condition is false
fi
```

Dalam sintaks di atas:

- Ganti `[ condition ]` dengan ekspresi yang akan diuji.
- Blok kode dalam `if` pernyataan dijalankan jika kondisi yang ditentukan adalah `true`.
- Blok kode dalam `else` pernyataan dijalankan jika kondisinya adalah `false`.
- Setiap pernyataan `if-else` harus diakhiri dengan `fi`.

![App Screenshot](img/if-elif-else/if-else-code.png)

Output:

![App Screenshot](img/if-elif-else/if-else-output.png)

Dalam contoh ini, jika usianya lebih dari 60 tahun, maka akan dihasilkan “Warga Negara Lanjut Usia”; jika tidak, akan ditampilkan “Bukan Warga Negara Lanjut Usia”.

### If..elif..else Statements

Gunakan `if..elif..else` pernyataan kondisional di Bash untuk mengeksekusi blok kode berbeda berdasarkan beberapa kondisi.

```
if [ condition1 ]; then
	# Execute code if condition1 is true
elif [ condition2 ]; then
	# Execute code if condition1 is false and condition2 is true
else
	# Execute code if both condition1 and condition2 are false
fi
```

- Blok kode dalam `if` pernyataan pertama dijalankan jika `condition1` is `true`.
- Blok kode dalam `elif` pernyataan pertama dijalankan jika `condition1` salah `false` dan `condition2` benar``.
- Blok `else` dijalankan jika keduanya `condition1` salah `condition2` salah.
- Setiap `if..elif..else` pernyataan harus diakhiri dengan `fi`.

Contoh:

![App Screenshot](img/if-elif-else/if-elif-else-code.png)

Output

![App Screenshot](img/if-elif-else/if-elif-else-output.png)

Dalam contoh ini, skrip memeriksa apakah usia lebih besar dari 60, kurang dari 14, atau tidak termasuk dalam kategori apa pun, dan menampilkan pesan yang sesuai.

## Bash - Loops

Loop digunakan untuk mengeksekusi blok kode beberapa kali.

Misalkan Anda ingin menjalankan perintah berulang kali atau mencetak array.for loop digunakan di Bash

Berbagai jenis loop

Bash Script menyediakan berbagai jenis loop

- for loop
- for index loop
- while loop
- until loop

### For loop

for loop digunakan untuk mengeksekusi kode beberapa kali berdasarkan suatu kondisi atau element

Syntax:

```
for element in [list]
do
 ## Code block
done
```

Contoh:

![App Screenshot](img/loops/for-loop.png)

Output:

![App Screenshot](img/loops/for-loop-output.png)

### for loop index

for loop index mirip dengan bahasa C for loop index. Ini mengeksekusi kode beberapa kali berdasarkan kondisi benar, Ini dimulai dengan nilai awal dan iterasi berisi nilai yang akan bertambah 1.

```
for (( assignment; condition; iteration )); do
  # code block
done
```

Contoh

![App Screenshot](img/loops/for-index.png)

Output:

![App Screenshot](img/loops/for-index-output.png)

Ini mencetak angka 0 sampai 5. 

### while loop in bash

Perulangan `while` di Bash memungkinkan eksekusi kode berulang selama kondisi yang ditentukan adalah `true`. Jika kondisinya menjadi `false`, perulangan akan keluar.

Struktur dari while loop adalah sebagai berikut:

```
while [ condition ]; do
  # code block
done
```

Contoh:

![App Screenshot](img/loops/while-loop.png)

Output:

![App Screenshot](img/loops/while-loop-output.png)

While loop diatas mencetak bilangan 0-100, program berjalan selama kondisi `[[ i -lt 100 ]]` benar. Variabel `i` akan terus mengincrement 1 dan mencetak nilainya. Jika kondisi salah (mencapai 100), maka program akan selesai.

### Until loop in bash

Kata `until` kunci di Bash digunakan untuk mengeksekusi kode berulang kali hingga kondisi tertentu menjadi `true`, di mana loop keluar.

Struktur dasar dari perulangan sampai adalah sebagai berikut.

```
until [ condition ]; do
  # code block
done
```

`until` kata kunci digunakan di Bash dan diakhiri dengan `done`.

Contoh

![App Screenshot](img/loops/until-loop.png)

Output:

![App Screenshot](img/loops/until-loop-output.png)

Program ini berjalan sama dengan program yang ada pada *while loop* hanya saja ini menggunakan *until loop*. Variable `i` akan mengincrement 1 sampai 99 dan mencetak nilainya. Program akan berjalan selama kondisi `[[ i -eq 100 ]]` benar. Jika kondisi salah (mencapai 100) maka program akan berhenti.

## Bash - Append String

### Bash Arthematic expressions
Arthematic expressions digunakan untuk melakukan operasi matematika

ekspresi adalah istilah yang digunakan dalam matematika untuk menunjukkan suatu operasi. Ini berisi operan dan operator untuk melakukan operasi matematika. `a<b`adalah sebuah ekspresi. Ini mungkin berisi operator biner atau unary

Di bash, Expressions dibuat menggunakan `(())` tanda kurung dengan operan dan operator sebagai argumen. `((a ))` adalah ekspresi bash. Expressions adalah operasi matematika, dapat berisi sub ekspresi yang dipisahkan dengan koma.

Contoh 

![App Screenshot](img/append-string/math-expression.png)

Output:

![App Screenshot](img/append-string/math-expression-output.png)

Arthematic expressions dibuat menggunakan operator dibawah ini 
- Operator Aritmatik
- Operator Perbandingan
- Operator Logis 
- Operator Bersyarat

Operator perbandingan digunakan untuk mengecek satu sama lain dengan membandingkan nilai operator (<, <=, >, >=, ==, !=)

Contoh:

![App Screenshot](img/append-string/math-comparison.png)

Output:

![App Screenshot](img/append-string/math-comparison-output.png)

### Bash Arithmetic Expansion

Expansion sama dengan Expression, yaitu digunakan untuk menghitung nilai expression dan hasilnya diganti dengan nilai dan selalu diawali dengan tanda dolar. 

```
$((expression))
``` 

Contoh menghitung nilai rata-rata menggunakan expansion. Setelah perhitungan dilakukan, output diganti dengan ekspresi.

![App Screenshot](img/append-string/athematic-expansion.png)

Output

![App Screenshot](img/append-string/athematic-expansion-output.png)

### Kapan Menggunakan Expression dan Expansion Aritmatik

[[]] digunakan untuk menguji ekspresi, mengembalikan nilai boolean (1 atau 0). Ini akan digunakan dalam kasus berikut

- Gunakan ekspresi artetik
    - Untuk melakukan operasi matematika dan perbandingan
- Gunakan ekspresi artetik [[]]
    - Perbandingan string dan angka
    - Periksa file atau direktori ada

