# Optimasi Regresi Linear menggunakan Gradient Descent

## Materi: Optimasi
* Tingkat: Menengah
* Prasyarat: `turunan`, `regresi linear`

## Prinsip utama Gradient Descent
Tugas utama Gradient Descent (GD) adalah menemukan nilai `intercept` dan `slope` yang **optimal** sehingga **error** antara nilai estimasi/prediksi dengan nilai aktual sekecil mungkin. `Slope` dan `intercept` juga sering disebut sebagai `bobot` atau `weight (w)`

## Formula yang digunakan
### Regresi linear
`Y' = a + b * X` <br>
Dengan `Y' = nilai prediksi`, `a = intercept` dan `b = slope`
### Sum Square Error (SSE)
`SSE = 0.5 * (Y - Y')^2` atau `0.5 * (Y - (a + b * X))^2`<br>
Dengan `SSE` = Sum Squared Error, `Y` = nilai aktual, dan `Y'` = nilai prediksi
### Gradient Error
`∂SSE/∂a = -(Y-Y')`<br>
`∂SSE/∂b = -(Y-Y') * X`<br>
### Update bobot
`w(t+1) = w(t) - r * ∂SSE/∂w`<br>
dengan `w(t+1)` = bobot baru, `r` = laju belajar (learning rate), dan `∂SSE/∂w` = gradient error  
### Standarisasi data
`Standardized data [X] = X[i] - MIN(X) / (MAX[X] - MIN[X])` <br>
dengan `standardize data [X] antara [0,1]`, `X` = data dalam satu kolom, `X[i]` = data ke-i, `MIN(X)` = nilai minimum dalam suatu kolom, `MAX(X) = nilai maksimum dalam suatu kolom

## Langkah-Langkah
Inisialisasi parameter: `r = 0.01` <br>
Langkah 1. Inisialisasi nilai acak antara [0,1] untuk `intercept (a)`, dan `slope (b)` <br>
Langkah 2. Hitung nilai prediksi dengan memasukkan nilai `a` dan `b` pada persamaan **`regresi linear`** <br>
Langkah 3. Hitung `SSE` <br>
Langkah 4. Hitung `gradient` <br>
Langkah 5. Hitung total `SSE`, `∂SSE/∂a`, dan `∂SSE/∂b` <br>
Langkah 6. Update bobot `a` dan `b` dengan `gradient` hingga diperoleh `SSE` minimum <br>
Langkah 7. Ulangi Langkah 2 s.d langkah 6 hingga `sse` sudah tidak lagi berkurang secara signifikan

## Studi Kasus 1
Dataset yang digunakan diambil dari publikasi [1] <br>
`Y` = Effort Aktual, dan `X` = size atau UCP
### Dataset
No | Effort Aktual (Y) | Size (X) 
------------ | ------------- | -------------
1 |  3684 | 320.5
2 |  1980 | 135.6
3 |  3950 | 354.0
4 |  1925 | 106.2
5 |  2175 | 134.6
6 |  2226 | 143.1
7 |  2640 | 195.0
8 |  2568 | 160.8
9 |  3042 | 272.2
10 |  1696 | 106.4

### Proses
Data distandarkan terlebih dahulu.<br>
`MIN(Y) = 1696`, `MAX(Y) = 3950`, `MIN(X) = 106,24`, dan `MAX(Y) = 345,03` <br>
Hasil standarisasi data <br>
No | Effort Aktual (Y) | Size (X) 
------------ | ------------- | -------------
1 |  0.88 | 0.9
2 |  0.13 | 0.12
3 |  1.00 | 1.0
4 |  0.10 | 0.0
5 |  0.21 | 0.12
6 |  0.24 | 0.15
7 |  0.42 | 0.37
8 |  0.39 | 0.23
9 |  0.60 | 0.69
10 |  0.00 | 0.00

Langkah 1. Nilai awal `a = 0.16`, dan `b = 0.64` <br>
Langkah 2. Nilai prediksi


## Referensi
[1] Ningrum, P. A. and Sholiq (2015) ‘[Penentuan Nilai Effort Rate (ER) Pada Metode Use Case Point (UCP) untuk Estimasi Effort Proyek Pengembangan Perangkat Lunak di Bidang Bisnis’, Teknik Pomits](http://digilib.its.ac.id/public/ITS-paper-34646-5209100001-Paper.pdf)
