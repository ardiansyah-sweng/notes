# Standardized Accuracy (SA)
* Prasyarat: `absolute error`, `mean`, `kuadrat`
## Apa itu Standardized Accuracy?
`MMRE` atau _Mean Magnitude Relative Error_ merupakan metrik yang sering digunakan dalam mengevaluasi performa estimasi dalam riset _software engineering_. Akan tetapi, penelitian [1] menemukan bahwa `MMRE` ternyata memiliki bias. Oleh karena itu [1] mengusulkan sebuah metrik pengganti yaitu `Standardized Accuracy (SA)`. `SA` terbukti mampu memberikan hasil yang lebih _meaningful_.
## Formula
<a href="https://www.codecogs.com/eqnedit.php?latex=SA=1-\frac{MAR}{MAR_P_0}*100" target="_blank"><img src="https://latex.codecogs.com/svg.latex?SA=1-\frac{MAR}{MAR_P_0}*100" title="SA=1-\frac{MAR}{MAR_P_0}*100" /></a><br>
dengan `MAR` = rerata error absolut dari prediktor.

### Improved SA
Karena perhitungan MAR<sub>P0</sub> sebelumnya bersifat stokastik dan bias, maka [2] mengusulkan perbaikan perhitungan MAR<sub>P0</sub>. Sehingga, perhitungannya menjadi: <p>
![](mar_p0.svg)
  
## Mengapa menggunakan Standardized Accuracy?
## Bagaimana menghitung Standardized Accuracy?


## Referensi
[1] Shepperd, M. and MacDonell, S. (2012) ‘[Evaluating prediction systems in software project estimation’, Information and Software Technology, 54(8), pp. 820–827. doi: 10.1016/j.infsof.2011.12.008.](https://www.sciencedirect.com/science/article/pii/S095058491200002X) <br>
[2] Langdon, W. B. et al. (2016) ‘[Exact Mean Absolute Error of Baseline Predictor, MARP0’, Information and Software Technology. Elsevier B.V., 73, pp. 16–18. doi: 10.1016/j.infsof.2016.01.003.](https://linkinghub.elsevier.com/retrieve/pii/S0950584916000057)
