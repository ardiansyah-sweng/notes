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
`SSE = 0.5 * (Y - Y')^2` <br>
Dengan `SSE = Sum Squared Error`, `Y = nilai aktual`, dan `Y' = nilai prediksi`

## Langkah-Langkah
Langkah 1. Inisialisasi nilai acak antara [0,1] untuk `intercept (a)`, dan `slope (b)` <br>
Langkah 2. Hitung nilai prediksi dengan memasukkan ada persamaan **`regresi linear`** <br>
Langkah 3. Hitung `SSE`
