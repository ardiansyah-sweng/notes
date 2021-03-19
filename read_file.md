# Membaca File
## Materi: Dasar-Dasar Pemrograman Modern
* Tingkat: Menengah
* Prasyarat: `variabel`, `array`, `loop`

## Konsep
File merupakan salah satu objek yang sering digunakan dalam pemrograman. Ada beberapa ekstensi file yang sering dioleh misalnya `.txt`, `csv`, dan `xlsx`.

## Mengapa membaca file teks?
Karena file menjadi salah satu format penyimpanan data, baik data `string` maupun `alfanumerik`. Kadangkala data teks juga merupakan hasil output dari sistem lain, misalnya hasil eksperimen atau sensor berbasis IoT.

## Membaca file **teks**?
Ada sebuah file teks [`hasil_mpso_sinusoidal.txt`](https://github.com/ardiansyah-sweng/ucwpso/blob/main/hasil_mpso_sinusoidal.txt). Kita akan mencoba membaca file tersebut

### `PHP`
Dalam `PHP` tinggal memanggil fungsi `file($nama_file)`. Hasil outputnya berupa `array` 1-dimensi. Contoh: <br>
```php
print_r(file('hasil_mpso_sinusoidal.txt'));
```
#### Output
> Array ( [0] => 7970,6518.22 [1] => 7962,6567.13 [2] => 7935,6570.01 [3] => 7805,6524.64 [4] => 7758,6524.97 [5] => 7643,6486.70 [6] => 7532,6546.78 [7] => 7451,6492.45 [8] => 7449,6492.38 [9] => 7427,6491.76 [10] => 7406,6494.39 [11] => 7365,6475.72 [12] => 7350,6470.80 [13] => 7303,6442.85 [14] => 7252,6427.63 [15] => 7245,6421.44 [16] => 7166,6370.10 [17] => 7119,6359.01 [18] => 7111,6367.73 [19] => 7044,6328.96 [20] => 7040,6316.53 [21] => 7028,6301.39 [22] => 6942,6263.58 [23] => 6814,6178.35 [24] => 6809,6166.16 [25] => 6802,6176.16 [26] => 6787,6149.87 [27] => 6764,6146.36 [28] => 6761,6149.46 [29] => 6725,6102.41 [30] => 6690,6075.20 [31] => 6600,5997.88 [32] => 6474,5894.58 [33] => 6433,5832.75 [34] => 6416,5842.02 [35] => 6412,5812.75 [36] => 6400,5819.22 [37] => 6360,5790.23 [38] => 6337,5733.33 [39] => 6240,5654.51 [40] => 6232,5632.47 [41] => 6173,5596.09 [42] => 6160,5581.17 [43] => 6117,5514.76 [44] => 6062,427.72 [45] => 6051,5415.12 [46] => 6048,5423.48 [47] => 6035,5383.61 [48] => 6024,5359.30 [49] => 6023,5364.71 [50] => 5993,5323.01 [51] => 5985,5332.92 [52] => 5971,5293.87 [53] => 5962,5324.18 [54] => 5944,5309.91 [55] => 5940,5294.66 [56] => 5927,5249.87 [57] => 5885,5185.66 [58] => 5882,5164.73 [59] => 5880,5182.22 [60] => 5880,5156.78 [61] => 5876,5155.64 [62] => 5873,5177.67 [63] => 5865,5150.67 [64] => 5863,5149.62 [65] => 5856,5129.00 [66] => 5800,5005.77 [67] => 5791,5009.67 [68] => 5782,4975.97 [69] => 5778,4979.80 [70] => 5775,4983.05 )

Perhatikan nilai setiap elemen dalam output `array` di atas contohnya `[17] => 7119,6359.01`. Bisa kita simpulkan bahwa nilai elemen bertipe `string`. Setiap elemen mengandung tanda koma `,`, dan titik `.`. Dalam pemrograman, tanda koma adalah karakter biasa. Sedangkan titik merupakan pecahan desimal. Artinya tanda koma tersebut merupakan pemisah antara dua nilai. Berarti, dalam sebuah elemen `array` sebenarnya mengandung dua nilai. Dengan demikian sebenarnya data `array` tersebut terdiri dari dua kolom. Karena output sebelumnya masih satu kolom atau 1-dimensi, maka harus kita ubah menjadi 2-kolom atau multi-dimensi terlebih dahulu.<br>
Karena pemisah antarnilai berupa tanda koma, maka tanda tersebut menjadi penandanya. Dalam `PHP` kita menggunakan fungsi `explode(penanda,string)` dengan output berupa `array`. Karena ada 71 elemen, maka kita akan memisahkan sebanyak 71 elemen.<br>
```php
$file_name = 'hasil_mpso_sinusoidal.txt';
foreach (file($file_name) as $val) {
    $dataset[] = explode(",", $val);
 }
 print_r($dataset);
```
#### Output
> Array ( [0] => Array ( [0] => 7970 [1] => 6518.22 ) [1] => Array ( [0] => 7962 [1] => 6567.13 ) [2] => Array ( [0] => 7935 [1] => 6570.01 ) [3] => Array ( [0] => 7805 [1] => 6524.64 ) [4] => Array ( [0] => 7758 [1] => 6524.97 ) [5] => Array ( [0] => 7643 [1] => 6486.70 ) [6] => Array ( [0] => 7532 [1] => 6546.78 ) [7] => Array ( [0] => 7451 [1] => 6492.45 ) [8] => Array ( [0] => 7449 [1] => 6492.38 ) [9] => Array ( [0] => 7427 [1] => 6491.76 ) [10] => Array ( [0] => 7406 [1] => 6494.39 ) [11] => Array ( [0] => 7365 [1] => 6475.72 ) [12] => Array ( [0] => 7350 [1] => 6470.80 ) [13] => Array ( [0] => 7303 [1] => 6442.85 ) [14] => Array ( [0] => 7252 [1] => 6427.63 ) [15] => Array ( [0] => 7245 [1] => 6421.44 ) [16] => Array ( [0] => 7166 [1] => 6370.10 ) [17] => Array ( [0] => 7119 [1] => 6359.01 ) [18] => Array ( [0] => 7111 [1] => 6367.73 ) [19] => Array ( [0] => 7044 [1] => 6328.96 ) [20] => Array ( [0] => 7040 [1] => 6316.53 ) [21] => Array ( [0] => 7028 [1] => 6301.39 ) [22] => Array ( [0] => 6942 [1] => 6263.58 ) [23] => Array ( [0] => 6814 [1] => 6178.35 ) [24] => Array ( [0] => 6809 [1] => 6166.16 ) [25] => Array ( [0] => 6802 [1] => 6176.16 ) [26] => Array ( [0] => 6787 [1] => 6149.87 ) [27] => Array ( [0] => 6764 [1] => 6146.36 ) [28] => Array ( [0] => 6761 [1] => 6149.46 ) [29] => Array ( [0] => 6725 [1] => 6102.41 ) [30] => Array ( [0] => 6690 [1] => 6075.20 ) [31] => Array ( [0] => 6600 [1] => 5997.88 ) [32] => Array ( [0] => 6474 [1] => 5894.58 ) [33] => Array ( [0] => 6433 [1] => 5832.75 ) [34] => Array ( [0] => 6416 [1] => 5842.02 ) [35] => Array ( [0] => 6412 [1] => 5812.75 ) [36] => Array ( [0] => 6400 [1] => 5819.22 ) [37] => Array ( [0] => 6360 [1] => 5790.23 ) [38] => Array ( [0] => 6337 [1] => 5733.33 ) [39] => Array ( [0] => 6240 [1] => 5654.51 ) [40] => Array ( [0] => 6232 [1] => 5632.47 ) [41] => Array ( [0] => 6173 [1] => 5596.09 ) [42] => Array ( [0] => 6160 [1] => 5581.17 ) [43] => Array ( [0] => 6117 [1] => 5514.76 ) [44] => Array ( [0] => 6062 [1] => 427.72 ) [45] => Array ( [0] => 6051 [1] => 5415.12 ) [46] => Array ( [0] => 6048 [1] => 5423.48 ) [47] => Array ( [0] => 6035 [1] => 5383.61 ) [48] => Array ( [0] => 6024 [1] => 5359.30 ) [49] => Array ( [0] => 6023 [1] => 5364.71 ) [50] => Array ( [0] => 5993 [1] => 5323.01 ) [51] => Array ( [0] => 5985 [1] => 5332.92 ) [52] => Array ( [0] => 5971 [1] => 5293.87 ) [53] => Array ( [0] => 5962 [1] => 5324.18 ) [54] => Array ( [0] => 5944 [1] => 5309.91 ) [55] => Array ( [0] => 5940 [1] => 5294.66 ) [56] => Array ( [0] => 5927 [1] => 5249.87 ) [57] => Array ( [0] => 5885 [1] => 5185.66 ) [58] => Array ( [0] => 5882 [1] => 5164.73 ) [59] => Array ( [0] => 5880 [1] => 5182.22 ) [60] => Array ( [0] => 5880 [1] => 5156.78 ) [61] => Array ( [0] => 5876 [1] => 5155.64 ) [62] => Array ( [0] => 5873 [1] => 5177.67 ) [63] => Array ( [0] => 5865 [1] => 5150.67 ) [64] => Array ( [0] => 5863 [1] => 5149.62 ) [65] => Array ( [0] => 5856 [1] => 5129.00 ) [66] => Array ( [0] => 5800 [1] => 5005.77 ) [67] => Array ( [0] => 5791 [1] => 5009.67 ) [68] => Array ( [0] => 5782 [1] => 4975.97 ) [69] => Array ( [0] => 5778 [1] => 4979.80 ) [70] => Array ( [0] => 5775 [1] => 4983.05 ) )

### Catatan
Pastikan bahwa file yang akan dibaca berada pada direktori yang sesuai.
