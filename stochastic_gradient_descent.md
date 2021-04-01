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
### Objek data ke-1 
`X = 0.89731563298296`, `Y = 0.88198757763975`. Kita akan mencoba memprediksi nilai `Y'` hingga mencapai nilai paling terdekat. Percobaan prediksi ini kita lakukan secara iterasi dengan mengoptimasi nilai `intercept` dan `slope`.<p> 

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
Iterasi ke- | Error) 
------------ | ------------- 
0 |  -0.068782894616399
1 |  -0.056366376063128
<p>
  
**Iterasi ke-2** <br>
Langkah 1. Nilai bobot iterasi ke-0 `a = 0.070398549685359`, dan `b = 0.8529861098971` <br>
Langkah 2. Nilai prediksi `Y'`.<br>
`Y' = 0.070398549685359 + 0.8529861098971 * 0.89731563298296 = 0.83579632081334` <br>
Langkah 3. Hitung `error` prediksi.<br>
`error = 0.83579632081334 - 0.88198757763975 = -0.04619125682641`. <br>
Langkah 4. Update bobot `a` (_intercept_) dan `b` (_slope_)<br>
`a(t+1) = a(t) - r * error`<br>
`a(t+1) = 0.070398549685359 - 0.01 * (-0.04619125682641) = 0.070398549685359`<br>
`b(t+1) = b(t) - r * error`<br>
`b(t+1) = 0.8529861098971 - 0.01 * (-0.04619125682641) = 0.8529861098971`<br>
Sehingga `a` dan `b` baru sekarang adalah **`0.075017675368`** dan **`0.85713092358284`**.<br>
Perubahan error:<br>
Iterasi ke- | Error 
------------ | -------------
0 |  -0.068782894616399
1 |  -0.056366376063128
2 | -0.04619125682641
<p>
  
Langkah 4. Ulangi Langkah 2-4 dengan menggunakan `a` dan `b` terbaru sebanyak 25 kali iterasi, hingga diperoleh hasil lengkap pada tabel berikut:<br>
Iterasi ke- | a | b | Y Normalized | Y' Normalized | Y Original | Error original | Error normalized
------------ | -------------| -------------| -------------| -------------| -------------| -------------| -------------
0 | 0.057883622617407 | 0.84175627019338 | 0.88198757763975 | 0.81320468302335 | 3460.5077136964 | 223.49228630365 | -0.068782894616399
1 | 0.064761912079046 | 0.84792826685549 | 0.88198757763975 | 0.82562120157662 | 3500.851990204 | 183.14800979597 | -0.056366376063128
2 | 0.070398549685359 | 0.8529861098971 | 0.88198757763975 | 0.83579632081334 | 3533.9134173846 | 150.08658261544 | -0.04619125682641
3 | 0.075017675368 | 0.85713092358284 | 0.88198757763975 | 0.84413465261201 | 3561.0066772428 | 122.99332275724 | -0.037852925027746
4 | 0.078802967870775 | 0.860527525721 | 0.88198757763975 | 0.85096776931237 | 3583.2091286293 | 100.79087137073 | -0.031019808327384
5 | 0.081904948703513 | 0.86331098161543 | 0.88198757763975 | 0.8565673886329 | 3601.4036482312 | 82.596351768808 | -0.025420189006855
6 | 0.084446967604199 | 0.86559197491435 | 0.88198757763975 | 0.86115617847944 | 3616.3137380128 | 67.686261987193 | -0.020831399160317
7 | 0.08653010752023 | 0.8674612089267 | 0.88198757763975 | 0.86491661129645 | 3628.5322951476 | 55.46770485242 | -0.017070966343303
8 | 0.088237204154561 | 0.86899301342369 | 0.88198757763975 | 0.86799822005261 | 3638.545188473 | 45.454811527002 | -0.013989357587144
9 | 0.089636139913275 | 0.87024830034953 | 0.88198757763975 | 0.87052354439375 | 3646.7505789819 | 37.249421018097 | -0.011464033246
10 | 0.090782543237875 | 0.87127698597439 | 0.88198757763975 | 0.87259300341097 | 3653.4747526264 | 30.525247373629 | -0.0093945742287819
11 | 0.091722000660753 | 0.87211997580646 | 0.88198757763975 | 0.87428888878861 | 3658.9850950229 | 25.014904977142 | -0.0076986888511412
12 | 0.092491869545867 | 0.87281079119242 | 0.88198757763975 | 0.87567863711905 | 3663.5007239956 | 20.499276004427 | -0.0063089405207
13 | 0.093122763597937 | 0.8733769022881 | 0.88198757763975 | 0.87681751150728 | 3667.2012027593 | 16.798797240672 | -0.0051700661324726
14 | 0.093639770211185 | 0.87384082040452 | 0.88198757763975 | 0.87775079909882 | 3670.2336802201 | 13.766319779892 | -0.0042367785409356
15 | 0.094063448065278 | 0.87422099316635 | 0.88198757763975 | 0.87851561191533 | 3672.7187423262 | 11.281257673818 | -0.0034719657244205
16 | 0.09441064463772 | 0.87453253807852 | 0.88198757763975 | 0.87914236260784 | 3674.7552071477 | 9.2447928522606 | -0.0028452150319118
17 | 0.094695166140912 | 0.87478784367125 | 0.88198757763975 | 0.87965597381058 | 3676.4240543606 | 7.5759456394262 | -0.0023316038291731
18 | 0.094928326523829 | 0.87499706212784 | 0.88198757763975 | 0.8800768691853 | 3677.7916453891 | 6.2083546109429 | -0.0019107084544544
19 | 0.095119397369274 | 0.87516851298446 | 0.88198757763975 | 0.88042178556468 | 3678.9123622568 | 5.0876377431523 | -0.0015657920750706
20 | 0.095275976576781 | 0.87530901395516 | 0.88198757763975 | 0.88070443848964 | 3679.8307700788 | 4.16922992123 | -0.0012831391501086
21 | 0.095404290491792 | 0.87542415203703 | 0.88198757763975 | 0.88093606760547 | 3680.583389185 | 3.4166108150043 | -0.0010515100342855
22 | 0.095509441495221 | 0.87551850567623 | 0.88198757763975 | 0.88112588360438 | 3681.2001473457 | 2.7998526542665 | -0.00086169403537362
23 | 0.095595610898758 | 0.87559582682911 | 0.88198757763975 | 0.88128143448715 | 3681.7055698439 | 2.2944301561006 | -0.00070614315259787
24 | 0.095666225214018 | 0.8756591901581 | 0.88198757763975 | 0.88140890570808 | 3682.1197547188 | 1.8802452811938 | -0.00057867193167294
25 | 0.095724092407185 | 0.87571111529517 | 0.88198757763975 | 0.88151336613848 | 3682.4591719613 | 1.540828038741 | -0.0004742115012718

Dapat kita lihat bahwa pada iterasi ke-25, `Y' = 0.88151336613848` dengan error = `-0.0004742115012718`, atau setelah kita denormalisasi (dikembalikan ke nilai asli) maka `Y' = 3682.4591719613` dengan selisih atau error = `1.540828038741`. <br>
Perhatikan penurunan tingkat `error` yang semakin mengecil di setiap iterasinya, menunjukkan semakin dekat antara nilai `Y aktual` dengan `Y prediksi`.

### Objek data ke-2 s.d 10
Ulangi prosesnya sama persis seperti pada proses estimasi/prediksi untuk **Objek data ke-1**

## Unduh dataset
[Dalam bentuk `txt`](https://drive.google.com/file/d/1c_JTnycE15Ij33C0rwHOOKduj9RrRuqY/view?usp=sharing)

## Referensi
[1] Ningrum, P. A. and Sholiq (2015) ‘[Penentuan Nilai Effort Rate (ER) Pada Metode Use Case Point (UCP) untuk Estimasi Effort Proyek Pengembangan Perangkat Lunak di Bidang Bisnis’, Teknik Pomits](http://digilib.its.ac.id/public/ITS-paper-34646-5209100001-Paper.pdf)
