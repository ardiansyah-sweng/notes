# Membaca File Teks
## Materi: Dasar-Dasar Pemrograman Modern
* Tingkat: Menengah
* Prasyarat: `array`, `loop`

## Konsep
File merupakan salah satu objek yang sering digunakan dalam pemrograman. File biasanya akan memuat data, sehingga sering juga disebut dengan data dalam bentuk teks.

## Mengapa membaca file teks?
Karena file teks menjadi salah satu format file yang bisa menyimpan rangkaian data, baik data `string` maupun `angka`. Kadangkala data teks juga merupakan hasil output dari sistem lain, misalnya hasil eksperimen atau sensor berbasis IoT.

## Bagaimana membaca file teks?
Ada sebuah file teks [`hasil_mpso_sinusoidal.txt`](https://github.com/ardiansyah-sweng/ucwpso/blob/main/hasil_mpso_sinusoidal.txt). Kita akan mencoba membaca file tersebut

### `PHP`
Dalam `PHP` tinggal memanggil fungsi `file($nama_file)`. Hasil outputnya berupa `array`. Contoh: <br>
```php
print_r(file('hasil_mpso_sinusoidal.txt'));
```
#### Output
> Array ( [0] => 7970,6518.22 [1] => 7962,6567.13 [2] => 7935,6570.01 [3] => 7805,6524.64 [4] => 7758,6524.97 [5] => 7643,6486.70 [6] => 7532,6546.78 [7] => 7451,6492.45 [8] => 7449,6492.38 [9] => 7427,6491.76 [10] => 7406,6494.39 [11] => 7365,6475.72 [12] => 7350,6470.80 [13] => 7303,6442.85 [14] => 7252,6427.63 [15] => 7245,6421.44 [16] => 7166,6370.10 [17] => 7119,6359.01 [18] => 7111,6367.73 [19] => 7044,6328.96 [20] => 7040,6316.53 [21] => 7028,6301.39 [22] => 6942,6263.58 [23] => 6814,6178.35 [24] => 6809,6166.16 [25] => 6802,6176.16 [26] => 6787,6149.87 [27] => 6764,6146.36 [28] => 6761,6149.46 [29] => 6725,6102.41 [30] => 6690,6075.20 [31] => 6600,5997.88 [32] => 6474,5894.58 [33] => 6433,5832.75 [34] => 6416,5842.02 [35] => 6412,5812.75 [36] => 6400,5819.22 [37] => 6360,5790.23 [38] => 6337,5733.33 [39] => 6240,5654.51 [40] => 6232,5632.47 [41] => 6173,5596.09 [42] => 6160,5581.17 [43] => 6117,5514.76 [44] => 6062,427.72 [45] => 6051,5415.12 [46] => 6048,5423.48 [47] => 6035,5383.61 [48] => 6024,5359.30 [49] => 6023,5364.71 [50] => 5993,5323.01 [51] => 5985,5332.92 [52] => 5971,5293.87 [53] => 5962,5324.18 [54] => 5944,5309.91 [55] => 5940,5294.66 [56] => 5927,5249.87 [57] => 5885,5185.66 [58] => 5882,5164.73 [59] => 5880,5182.22 [60] => 5880,5156.78 [61] => 5876,5155.64 [62] => 5873,5177.67 [63] => 5865,5150.67 [64] => 5863,5149.62 [65] => 5856,5129.00 [66] => 5800,5005.77 [67] => 5791,5009.67 [68] => 5782,4975.97 [69] => 5778,4979.80 [70] => 5775,4983.05 )
