# Normalisasi Data

## Formula
Persamaan (1) <br>
<a href="https://www.codecogs.com/eqnedit.php?latex=C_i_j={\frac{x_i_j-min(f_j)}{max(x_j)-min(x_j)}}" target="_blank"><img src="https://latex.codecogs.com/svg.latex?C_i_j={\frac{x_i_j-min(x_j)}{max(x_j)-min(x_j)}}" title="C_i_j={\frac{x_i_j-min(x_j)}{max(x_j)-min(x_j)}}" /></a> <br>
dengan:<br>
C<sub>ij</sub> = nilai data ke-_i_ pada kolom ke-_j_ yang sudah dinormalisasi<br>
x<sub>ij</sub> = nilai date ke-_i_ pada kolom ke-_j_ yang hendak dinormalisasi<br>
min(f<sub>j</sub>) = nilai **minimum** pada kolom ke-_j_<br>
max(f<sub>j</sub>) = nilai **maksimum** pada kolom ke-_j_<br>
## Apa itu Normalisasi data?
Proses mengubah skala nilai data ke dalam rentang antara 0 hingga 1.
## Mengapa Normalisasi data?
## Bagaimana melakukan Normalisasi data?
Langkah 1. Tentukan nilai **minimal** dan **maksimal** setiap kolom <br>
Langkah 2. Untuk setiap nilai dalam kolom lakukan normalisasi data seperti pada `Persamaan (1)`.

### Contoh normalisasi data
No | Y | X 
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

Langkah 1. Tentukan nilai `minimum` dan `maksimum` kedua kolom `X` dan `Y` tersebut. Sehingga diperoleh:<br>
Kolom | Minimum | Maksimum 
------------ | ------------- | -------------
Y |  1696 | 3950
X |  106.2 | 354.0

Langkah 2. Setiap nilai dalam kolom lakukan normalisasi seperti pada `Persamaan (1)`.<p>
Kolom `X`<br>
<a href="https://www.codecogs.com/eqnedit.php?latex=C_1_1={\frac{3684-1696}{3950-1696}}&space;=&space;0.88" target="_blank"><img src="https://latex.codecogs.com/svg.latex?C_1_1={\frac{3684-1696}{3950-1696}}&space;=&space;0.88" title="C_1_1={\frac{3684-1696}{3950-1696}} = 0.88" /></a> <br>
<a href="https://www.codecogs.com/eqnedit.php?latex=C_2_1={\frac{1980-1696}{3950-1696}}&space;=&space;0.13" target="_blank"><img src="https://latex.codecogs.com/svg.latex?C_2_1={\frac{1980-1696}{3950-1696}}&space;=&space;0.13" title="C_2_1={\frac{1980-1696}{3950-1696}} = 0.13" /></a> <br>
<a href="https://www.codecogs.com/eqnedit.php?latex=C_3_1={\frac{3950-1696}{3950-1696}}&space;=&space;1.00" target="_blank"><img src="https://latex.codecogs.com/svg.latex?C_3_1={\frac{3950-1696}{3950-1696}}&space;=&space;1.00" title="C_3_1={\frac{3950-1696}{3950-1696}} = 1.00" /></a> <br>
  ...dst hingga baris ke-10 kolom 1 atau C<sub>101</sub><p>
 
 Kolom `Y`<br>
 <a href="https://www.codecogs.com/eqnedit.php?latex=C_1_2={\frac{320.5-106.2}{354.0-106.2}}&space;=&space;0.9" target="_blank"><img src="https://latex.codecogs.com/svg.latex?C_1_2={\frac{320.5-106.2}{354.0-106.2}}&space;=&space;0.9" title="C_1_2={\frac{320.5-106.2}{354.0-106.2}} = 0.9" /></a> <br>
 <a href="https://www.codecogs.com/eqnedit.php?latex=C_2_2={\frac{135.6-106.2}{354.0-106.2}}&space;=&space;0.12" target="_blank"><img src="https://latex.codecogs.com/svg.latex?C_2_2={\frac{135.6-106.2}{354.0-106.2}}&space;=&space;0.12" title="C_2_2={\frac{135.6-106.2}{354.0-106.2}} = 0.12" /></a> <br>
 <a href="https://www.codecogs.com/eqnedit.php?latex=C_3_2={\frac{354.0-106.2}{354.0-106.2}}&space;=&space;1.0" target="_blank"><img src="https://latex.codecogs.com/svg.latex?C_3_2={\frac{354.0-106.2}{354.0-106.2}}&space;=&space;1.0" title="C_3_2={\frac{354.0-106.2}{354.0-106.2}} = 1.0" /></a> <br>
   ...dst hingga baris ke-10 kolom 2 atau C<sub>102</sub><p>
 
Hasil normalisasi data <br>
No | Y | X 
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
