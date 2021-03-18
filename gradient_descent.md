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

## Langkah-Langkah
Inisialisasi parameter: `r = 0.01` <br>
Langkah 1. Inisialisasi nilai acak antara [0,1] untuk `intercept (a)`, dan `slope (b)` <br>
Langkah 2. Hitung nilai prediksi dengan memasukkan nilai `a` dan `b` pada persamaan **`regresi linear`** <br>
Langkah 3. Hitung `SSE` <br>
Langkah 4. Hitung `gradient` <br>
Langkah 5. Hitung total `SSE`, `∂SSE/∂a`, dan `∂SSE/∂b` <br>
Langkah 6. Update bobot `a` dan `b` dengan `gradient` hingga diperoleh `SSE` minimum <br>
Langkah 7. Ulangi Langkah 2 s.d langkah 6 hingga `sse` sudah tidak berkurang secara signifikan
