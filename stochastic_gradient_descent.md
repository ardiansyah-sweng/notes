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
No | Sizel (X) | Effort Aktual (Y) 
------------ | ------------- | -------------
1 |  320.5 | 3684
2 |  135.6 | 1980
3 |  354.0 | 3950
4 |  106.2 | 1925 
5 |  134.6 | 2175
6 |  143.1 | 2226
7 |  195.0 | 2640
8 |  160.8 | 2568
9 |  272.2 | 3042
10 | 106.4 | 1696

![image](https://user-images.githubusercontent.com/71623245/111888856-f9355b00-8a12-11eb-8426-d5888de43462.png)

### Proses
Data dinormalisasi terlebih dahulu, sehingga menjadi:<br>
No | Size (X) | Effort Aktual (Y) 
------------ | ------------- | -------------
1 |  0.89731563298296 | 0.88198757763975
2 |  0.12274383349386 | 0.12599822537711
3 |  1.00 | 1.0
4 |  0.0 | 0.10159716060337
5 |  0.11876544243896 | 0.21251109139308
6 |  0.15444532853135 | 0.23513753327418
7 |  0.37187486913187 | 0.41881100266193
8 |  0.22856903555425 | 0.3868677905945 
9 |  0.69496210059048 | 0.59716060337178
10 |  0.00054441140751292 | 0.00

Karena ada 10 objek data, maka kita akan mengoptimasi objek data tersebut satu per satu.<br>
Objek data ke-1. `X = 0.89731563298296`, `Y = 0.88198757763975`. Kita akan mencoba memprediksi nilai `Y'` hingga mencapai nilai paling terdekat. Percobaan prediksi ini kita lakukan secara iterasi dengan mengoptimasi nilai `intercept` dan `slope`.<p> 

**Iterasi ke-0** <br>
Langkah 1. Nilai awal bobot `a = 0.057883622617407`, dan `b = 0.84175627019338` yang diperoleh secara acak [0,1] <br>
Langkah 2. Nilai prediksi `Y'`.<br>
`Y' = 0.057883622617407 + 0.84175627019338 * 0.89731563298296 = 0.81320468302335` <br>
Langkah 3. Hitung `error` prediksi.<br>
`error = 0,813204683023356 - 0,88198757763975 = -0.068782894616399`. <br>
Langkah 4. Update bobot `a` (_intercept_) dan `b` (_slope_)<br>
`a(t+1) = a(t) - r * error`<br>
`a(t+1) = 0.057883622617407 - 0.01 * (-0.06878289461639) = 0.064761912079046`<br>
`b(t+1) = b(t) - r * error`<br>
`b(t+1) = 0.84175627019338 - 0.01 * (-0.06878289461639) = 0.84792826685549`<br>
Sehingga `a` dan `b` baru sekarang adalah **`0.064761912079046`** dan **`0.84792826685549`**
<p>
  
**Iterasi ke-1** <br>
Langkah 1. Nilai bobot iterasi ke-0 `a = 0.064761912079046`, dan `b = 0.84792826685549` <br>
Langkah 2. Nilai prediksi `Y'`.<br>
`Y' = 0.064761912079046 + 0.84792826685549 * 0.89731563298296 = 0.82562120157662` <br>
Langkah 3. Hitung `error` prediksi.<br>
`error = 0.82562120157662 - 0.88198757763975 = -0.056366376063128`. <br>
Langkah 4. Update bobot `a` (_intercept_) dan `b` (_slope_)<br>
`a(t+1) = a(t) - r * error`<br>
`a(t+1) = 0.064761912079046 - 0.01 * (-0.056366376063128) = 0.070398549685359`<br>
`b(t+1) = b(t) - r * error`<br>
`b(t+1) = 0.84792826685549 - 0.01 * (-0.056366376063128) = 0.8529861098971`<br>
Sehingga `a` dan `b` baru sekarang adalah **`0.070398549685359`** dan **`0.8529861098971`**.<br>
Perubahan error:<br>
Iterasi ke- | Error) | Perubahan (%) 
------------ | ------------- | -------------
0 |  -0.068782894616399 | 0
1 |  -0.056366376063128 | 0
<p>
**Iterasi ke-2** <br>
Langkah 1. Nilai bobot iterasi ke-0 `a = 0.064761912079046`, dan `b = 0.84792826685549` <br>
Langkah 2. Nilai prediksi `Y'`.<br>
`Y' = 0.064761912079046 + 0.84792826685549 * 0.89731563298296 = 0.82562120157662` <br>
Langkah 3. Hitung `error` prediksi.<br>
`error = 0.82562120157662 - 0.88198757763975 = -0.056366376063128`. <br>
Langkah 4. Update bobot `a` (_intercept_) dan `b` (_slope_)<br>
`a(t+1) = a(t) - r * error`<br>
`a(t+1) = 0.064761912079046 - 0.01 * (-0.056366376063128) = 0.070398549685359`<br>
`b(t+1) = b(t) - r * error`<br>
`b(t+1) = 0.84792826685549 - 0.01 * (-0.056366376063128) = 0.8529861098971`<br>
Sehingga `a` dan `b` baru sekarang adalah **`0.070398549685359`** dan **`0.8529861098971`**.<br>
Perubahan error:<br>
Iterasi ke- | Error) | Perubahan (%) 
------------ | ------------- | -------------
0 |  -0.068782894616399 | 0
1 |  -0.056366376063128 | 0


Langkah 4. Ulangi Langkah 2-4 dengan menggunakan `a` dan `b` terbaru sebanyak 20 kali iterasi.
  
## Unduh dataset
[Dalam bentuk `txt`](https://drive.google.com/file/d/1c_JTnycE15Ij33C0rwHOOKduj9RrRuqY/view?usp=sharing)

## Referensi
[1] Ningrum, P. A. and Sholiq (2015) ‘[Penentuan Nilai Effort Rate (ER) Pada Metode Use Case Point (UCP) untuk Estimasi Effort Proyek Pengembangan Perangkat Lunak di Bidang Bisnis’, Teknik Pomits](http://digilib.its.ac.id/public/ITS-paper-34646-5209100001-Paper.pdf)
