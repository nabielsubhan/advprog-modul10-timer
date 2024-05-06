## Nama   : Muhammad Nabiel Subhan
## NPM    : 2206081553
## Kelas  : AdPro B

### 1.2. Understanding how it works.

<p align="center">
  <img src="images\hey.png" />
</p>

Dapat dilihat bahwa baris `Nabiel's komputer: hey hey` dieksekusi terlebih dahulu daripada `Nabiel's Komputer: howdy!` dan `Nabiel's Komputer: done!`. Hal tersebut dapat terjadi karena pada function main, `spawner` menambahkan task asinkronus baru. Tugas asinkronus tersebut menunggu `executor` untuk mulai menjalankannya, sedangkan thread utama terus berjalan mengeksekusi line berikutnya hingga sampai dan mengeksekusi baris `Nabiel's komputer: hey hey` terlebih dahulu. Ini berarti, baris `Nabiel's komputer: hey hey` dieksekusi terlebih dahulu sebelum `executor` mulai menjalankan task asinkronus yang nantinya akan mencetak baris `Nabiel's Komputer: howdy!` dan `Nabiel's Komputer: done!`.

###  1.3. Multiple Spawn and removing drop

<p align="center">
  <img src="images\withoutdrop1.png" />
</p>
<p align="center">
  <img src="images\withoutdrop2.png" />
</p>
<p align="center">
  <img src="images\withdrop.png" />
</p>

Dari ketiga gambar di atas, dapat dilihat perbedaan pada dua gambar pertama dengan gambar ketiga, yaitu dua gambar pertama menunjukkan bahwa program masih terus berjalan setelah semua task sudah dijalankan, sedangkan gambar ketiga menunjukkan bahwa program selesai selepas menjalankan semua task yang ada. Hal tersebut diakibatkan oleh baris `drop(spawner);` yang dihilangkan pada kasus dua gambar pertama yang membuat `spawner` terus menunggu adanya task baru untuk dijalankan sehingga program tidak dapat selesai, sedangkan pada gambar ketiga, dengan adanya baris `drop(spawner);` akan membuat `spawner` berhenti menerima task baru. Selain itu, dapat dilihat bahwa urutan eksekusi baris yang dicetak dapat berbeda-beda tiap kali program dijalankan. Hal tersebut terjadi karena program berjalan secara konkuren sehingga urutan eksekusi dapat bervariasi dan hal tersebut adalah hal yang normal terjadi pada lingkungan konkurensi.