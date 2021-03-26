# k-Medoids
## Materi: Machine Learning
* Tingkat: menengah
* Prasyarat: `clustering`, `k-Medoids`, `loop`, `array`

# Bisecting k-Medoids
## Formula yang digunakan
Persamaan (1)<br>
![equation](https://latex.codecogs.com/png.latex?variance=\frac{1}{n}\sum_{j=1,y_j\in_C_i}^{n}\big\|\big\|x_j-v_i\big\|\big\|^2) <br>
dengan:<br>
`||.||` = jarak dalam _euclidean_. <br>
_x_<sub>j</sub> = objek data ke-_j_ <br>
_v_<sub>i</sub> = pusat _cluster_ ke-_i_ (_C_<sub>i</sub>)

## Mengapa k-Medoids?
Pada algoritma _clustering_ `k-means` dan `k-medoids`, kita diminta untuk menentukan jumlah _cluster_ di awal. Penentuan jumlah _cluster_ dilakukan secara acak/menebak atau menggunakan indeks validitas _clustering_. Kedua teknik tersebut tidak selalu menghasilkan jumlah _cluster_ yang optimal. Untuk mengatasi masalah tersebut, maka digunakanlah prosedur `bisecting` pada `k-medoids`. Pada gambar berikut ditunjukkan ilustrasi bagaimana pembentukan _cluster_ pada algoritma _bisecting_ `k-medoids`.<p>
![Bisecting k-Medoids](https://github.com/ardiansyah-sweng/notes/blob/main/method-comparison-ilustrasi-bisecting-kmedoids.svg)
## Bagaimana menerapkan k-Medoids?
## Pseudocode
Input: Dataset X<br>
Output: Himpunan _N_ cluster _S_ = {C<sub>1</sub>, C<sub>2</sub>, C<sub>3</sub>, C<sub>4</sub>,...,C<sub>N</sub>}<br>
Inisialisasi: V=X, S={}, NextLevel={}<br>
Repeat while size(V) > 0<br>
&nbsp;&nbsp; foreach Cluster C in V<br>
&nbsp;&nbsp; Comp &#8592; variance(C)<br>
&nbsp;&nbsp;&nbsp;&nbsp; [C<sub>1</sub>,C<sub>2</sub>] &#8592; k-Medoids(C,2)<br>
&nbsp;&nbsp;&nbsp;&nbsp; Comp<sub>1</sub> &#8592; variance(C<sub>1</sub>)<br>
&nbsp;&nbsp;&nbsp;&nbsp; Comp2 &#8592; variance(C<sub>2</sub>)<br>
&nbsp;&nbsp; if (max(Comp<sub>1</sub>, Comp<sub>2</sub>) < Comp<br>
&nbsp;&nbsp;&nbsp;&nbsp; NextLevel &#8592; NextLevel &#8746; {C<sub>1</sub>,C<sub>2</sub>}<br>
&nbsp;&nbsp; else<br>
&nbsp;&nbsp;&nbsp;&nbsp; S &#8592; S &#8746; {C}<br>
&nbsp;&nbsp; end<br>
&nbsp;&nbsp;&nbsp;&nbsp; V &#8592; NextLevel<br>
&nbsp;&nbsp;&nbsp;&nbsp; NextLevel &#8592; {}<br>
end

## Dataset
Silakan unduh [`dataset_silhavy.txt`](https://github.com/ardiansyah-sweng/ucwpso/blob/main/silhavy_dataset.txt)
