# Optimasi Regresi Linear Sederhana menggunakan Stochastic Gradient Descent (SGD)

## Materi: Optimasi
* Tingkat: Menengah
* Prasyarat: `turunan`, `regresi linear`, [`normalisasi data`](https://github.com/ardiansyah-sweng/notes/blob/main/normalisasi_data.md)

## Prinsip utama Stochastic Gradient Descent
Tugas utama Stochastic Gradient Descent (SGD) adalah menemukan nilai `intercept` dan `slope` yang **optimal** sehingga **error** antara nilai estimasi/prediksi dengan nilai aktual sekecil mungkin. `Slope` dan `intercept` juga sering disebut sebagai `bobot` atau `weight (w)`

## Formula yang digunakan
### Regresi linear
`Y' = a + b * X` <br>
Dengan `Y' = nilai prediksi`, `a = intercept` dan `b = slope`
### Nilai residual
Ada beberapa nilai residual atau error yang bisa digunakan, antara lain:
#### Sum Square Error (SSE)
`SSE = 0.5 * (Y - Y')^2` atau `0.5 * (Y - (a + b * X))^2`<br>
Dengan `SSE` = Sum Squared Error, `Y` = nilai aktual, dan `Y'` = nilai prediksi
#### Absolute Error (AE) atau Absolute Residual (AR)
`AE = absolute(Y - Y')` <br>
### Gradient Error
`∂SSE/∂a = -(Y-Y')`<br>
`∂SSE/∂b = -(Y-Y') * X`<br>
### Update bobot
`w(t+1) = w(t) - r * ∂SSE/∂w(t)`<br>
dengan: <br> 
`w(t+1)` = bobot baru <br>
`w(t)` = bobot saat ini <br>
`r` = laju belajar (_learning rate_) <br>
`∂SSE/∂w` = gradient error  

## Studi Kasus 1
Dataset yang digunakan diambil dari publikasi [1] <br>
`Y` = Effort Aktual, dan `X` = size atau UCP, dan laju belajar `r = 0.01 `
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

![image](https://user-images.githubusercontent.com/71623245/111888856-f9355b00-8a12-11eb-8426-d5888de43462.png)

### Proses
Data dinormalisasi terlebih dahulu, sehingga menjadi:<br>
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

Karena ada 10 objek data, maka kita akan mengoptimasi objek data tersebut satu per satu.<br>
Objek data ke-1. `X = 0.9`, `Y = 0.88`. Kita akan mencoba memprediksi nilai `Y'` hingga mencapai nilai paling terdekat. Percobaan prediksi ini kita lakukan secara iterasi dengan mengoptimasi nilai `intercept` dan `slope`.<p> 

Langkah 1. Nilai awal bobot `a = 0.2`, dan `b = 0.64` yang diperoleh secara acak [0,1] <br>
Langkah 2. Nilai prediksi `Y'`.<br>
`Y' = 0.2 + 0.64 * 0.9 = 0.776` <br>
Langkah 3. Hitung `error` prediksi.<br>
`error = 0.776 - 0.88 = -0.104`. <br>
Langkah 4. Update bobot `a` (_intercept_) dan `b` (_slope_)<br>
`a(t+1) = a(t) - r * ∂SSE/∂a(t)`<br>
`a(t+1) = 0.2 - 0.01 * 0.949065314`<br>
`a(t+1) = 0.18101869372`<p>
`b(t+1) = b(t) - r * ∂SSE/∂b(t)`<br>
`b(t+1) = 0.64 - 0.01 * 0.334281702`<br>
`b(t+1) = 0.954281702`<p>
Sehingga `a` dan `b` baru sekarang adalah **`0.18101869372`** dan **`0.954281702`**
<p>
Langkah 4. Ulangi Langkah 2 dengan menggunakan `a` dan `b` terbaru
  
## Unduh dataset
[Dalam bentuk `txt`](https://drive.google.com/file/d/1c_JTnycE15Ij33C0rwHOOKduj9RrRuqY/view?usp=sharing)

## Referensi
[1] Ningrum, P. A. and Sholiq (2015) ‘[Penentuan Nilai Effort Rate (ER) Pada Metode Use Case Point (UCP) untuk Estimasi Effort Proyek Pengembangan Perangkat Lunak di Bidang Bisnis’, Teknik Pomits](http://digilib.its.ac.id/public/ITS-paper-34646-5209100001-Paper.pdf)
