# k-Medoids
## Materi: Machine Learning
* Tingkat: menengah
* Prasyarat: [`clustering`](https://github.com/ardiansyah-sweng/notes/blob/main/clustering.md), `loop`, `array`

# Bisecting k-Medoids
## Formula yang digunakan
`Persamaan (1)` <br>
![equation](https://latex.codecogs.com/png.latex?variance=\frac{1}{n}\sum_{j=1,y_j\in_C_i}^{n}\big\|\big\|x_j-v_i\big\|\big\|^2) <br>
dengan:<br>
`||.||` = jarak dalam _euclidean_. <br>
_x_<sub>j</sub> = objek data ke-_j_ <br>
_v_<sub>i</sub> = pusat _cluster_ ke-_i_ (_C_<sub>i</sub>)

## Mengapa `bisecting k-Medoids`?
Pada algoritma _clustering_ `k-means` dan `k-medoids`, kita diminta untuk menentukan jumlah _cluster_ di awal. Penentuan jumlah _cluster_ dilakukan secara acak/menebak atau menggunakan indeks validitas _clustering_. Kedua teknik tersebut tidak selalu menghasilkan jumlah _cluster_ yang optimal. Untuk mengatasi masalah tersebut, maka digunakanlah prosedur `bisecting` pada `k-medoids`. Pada gambar berikut ditunjukkan ilustrasi bagaimana pembentukan _cluster_ pada algoritma _bisecting_ `k-medoids`.<p>
![Bisecting k-Medoids](https://github.com/ardiansyah-sweng/notes/blob/main/method-comparison-ilustrasi-bisecting-kmedoids.svg)

## Kapan menggunakan `bisecting ke-Medoids`?

## Bagaimana menerapkan k-Medoids?
1. Hitung _variance_ _cluster_ induk (C) menggunakan `Persamaan (1)`
2. Tentukan _centroid<sub>1</sub>_ (c<sub>1</sub>), dan _centroid<sub>2</sub>_ (c<sub>2</sub>)

## Pseudocode
![Bisecting k-Medoids](https://github.com/ardiansyah-sweng/notes/blob/main/bisecting_kmedoids_pseudocode.svg)

## Dataset
Silakan unduh [`dataset_silhavy.txt`](https://github.com/ardiansyah-sweng/ucwpso/blob/main/silhavy_dataset.txt)
