# k-Medoids
## Materi: Machine Learning
* Tingkat: menengah
* Prasyarat: [`clustering`](https://github.com/ardiansyah-sweng/notes/blob/main/clustering.md), `loop`, `array`

# Bisecting k-Medoids
## Formula yang digunakan
`Persamaan (1)` <br>
<a href="https://www.codecogs.com/eqnedit.php?latex=variance&space;=&space;\frac{1}{n}&space;\sum_{j=1,y_j\in&space;C_i}^{n}{\left&space;|&space;\right&space;|x_j-v_i\left&space;|&space;\right&space;|^2}{}" target="_blank"><img src="https://latex.codecogs.com/svg.latex?variance&space;=&space;\frac{1}{n}&space;\sum_{j=1,y_j\in&space;C_i}^{n}{\left&space;|&space;\right&space;|x_j-v_i\left&space;|&space;\right&space;|^2}{}" title="variance = \frac{1}{n} \sum_{j=1,y_j\in C_i}^{n}{\left | \right |x_j-v_i\left | \right |^2}{}" /></a>

dengan:<br>
`||.||` = jarak dalam _euclidean_. <br>
_x_<sub>j</sub> = objek data ke-_j_ <br>
_v_<sub>i</sub> = pusat _cluster_ ke-_i_ (_C_<sub>i</sub>) <br>
_n_ = jumlah data

## Mengapa `bisecting k-Medoids`?
Pada algoritma _clustering_ `k-means` dan `k-medoids`, kita diminta untuk menentukan jumlah _cluster_ di awal. Penentuan jumlah _cluster_ dilakukan secara acak/menebak atau menggunakan indeks validitas _clustering_. Kedua teknik tersebut tidak selalu menghasilkan jumlah _cluster_ yang optimal. Untuk mengatasi masalah tersebut, maka digunakanlah prosedur `bisecting` pada `k-medoids`. Pada gambar berikut ditunjukkan ilustrasi bagaimana pembentukan _cluster_ pada algoritma _bisecting_ `k-medoids`.<p>
![Bisecting k-Medoids](https://github.com/ardiansyah-sweng/notes/blob/main/images/bisecting_kmedoids_pseudocode.svg)

## Kapan menggunakan `bisecting ke-Medoids`?

## Bagaimana menerapkan k-Medoids?
1. Hitung _variance_ _cluster_ induk (C) menggunakan `Persamaan (1)`
2. Tentukan _centroid<sub>1</sub>_ (c<sub>1</sub>), dan _centroid<sub>2</sub>_ (c<sub>2</sub>)

## Pseudocode
![Bisecting k-Medoids](https://github.com/ardiansyah-sweng/notes/blob/main/images/bisecting_kmedoids_pseudocode.svg)

## Dataset
Silakan unduh [`dataset_silhavy.txt`](https://github.com/ardiansyah-sweng/ucwpso/blob/main/silhavy_dataset.txt)
