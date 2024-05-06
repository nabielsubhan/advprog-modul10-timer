## Nama   : Muhammad Nabiel Subhan
## NPM    : 2206081553
## Kelas  : AdPro B

### 1.2. Understanding how it works.

<p align="center">
  <img src="images\hey.png" />
</p>

Dapat dilihat bahwa baris `Nabiel's komputer: hey hey` dieksekusi terlebih dahulu daripada `Nabiel's Komputer: howdy!` dan `Nabiel's Komputer: done!`. Hal tersebut dapat terjadi karena pada function main, `spawner` menambahkan task asinkronus baru. Tugas asinkronus tersebut menunggu `executor` untuk mulai menjalankannya, sedangkan thread utama terus berjalan mengeksekusi line berikutnya hingga sampai dan mengeksekusi baris `Nabiel's komputer: hey hey` terlebih dahulu. Ini berarti, baris `Nabiel's komputer: hey hey` dieksekusi terlebih dahulu sebelum `executor` mulai menjalankan task asinkronus yang nantinya akan mencetak baris `Nabiel's Komputer: howdy!` dan `Nabiel's Komputer: done!`.