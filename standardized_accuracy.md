# Standardized Accuracy (SA)
## Materi: Metodologi Penelitian Software Engineering
* Tingkat: Menengah
* Prasyarat: `absolute error`, `mean`, `kuadrat`
## Deskripsi
`MMRE` atau _Mean Magnitude Relative Error_ merupakan metrik yang sering digunakan dalam mengevaluasi performa estimasi dalam riset _software engineering_. Akan tetapi, penelitian [1] menemukan bahwa `MMRE` ternyata memiliki bias. Oleh karena itu [1] mengusulkan sebuah metrik pengganti yaitu `Standardized Accuracy (SA)`. `SA` terbukti mampu memberikan hasil yang lebih _meaningful_.

## Formula
![equation](https://latex.codecogs.com/gif.latex?SA=1-\frac{MAR}{MAR_P_0}*100) <br>
dengan `MAR` = rerata error absolut dari prediktor.

## Improved SA
Karena perhitungan ![equation](https://latex.codecogs.com/gif.latex?{MAR_P_0}) sebelumnya bersifat stokastik dan bias, maka [2] mengusulkan perbaikan perhitungan ![equation](https://latex.codecogs.com/gif.latex?{MAR_P_0}). Sehingga, perhitungannya menjadi: <br>
![equation](https://latex.codecogs.com/png.latex?MAR_P_0=\frac{2}{n^2}\sum_{i=1}^{n}\sum_{j=1}^{j<i}|y_i-y_j|)

## Referensi
[1] Shepperd, M. and MacDonell, S. (2012) ‘[Evaluating prediction systems in software project estimation’, Information and Software Technology, 54(8), pp. 820–827. doi: 10.1016/j.infsof.2011.12.008.](https://www.sciencedirect.com/science/article/pii/S095058491200002X) <br>
[2] Langdon, W. B. et al. (2016) ‘[Exact Mean Absolute Error of Baseline Predictor, MARP0’, Information and Software Technology. Elsevier B.V., 73, pp. 16–18. doi: 10.1016/j.infsof.2016.01.003.](https://linkinghub.elsevier.com/retrieve/pii/S0950584916000057)
