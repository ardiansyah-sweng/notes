# Membaca File Teks
## Materi: Dasar-Dasar Pemrograman Modern
* Tingkat: Menengah
* Prasyarat: `array`, `loop`

## Mengapa membaca file teks?
Karena file teks menjadi salah satu format file yang bisa menyimpan rangkaian data, baik data `string` maupun `angka`. Kadangkala data teks juga merupakan hasil output dari sistem lain, misalnya hasil eksperimen atau sensor berbasis IoT.

## Konsep
File merupakan salah satu objek yang sering digunakan dalam pemrograman. File biasanya akan memuat data, sehingga sering juga disebut dengan data dalam bentuk teks.

## Bagaimana membaca file teks?
Ada sebuah file teks [`hasil_mpso_sinusoidal.txt`](https://github.com/ardiansyah-sweng/ucwpso/blob/main/hasil_mpso_sinusoidal.txt). Kita akan mencoba membaca file tersebut

### `PHP`
Dalam `PHP` tinggal memanggil fungsi `file($nama_file`. Hasil outputnya berupa `array`.
