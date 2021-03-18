# Standardized Accuracy (SA)
## Materi: Metodologi Penelitian Software Engineering
* Tingkat: Menengah
* Prasyarat: 

## Formula
![equation](https://latex.codecogs.com/gif.latex?SA=1-\frac{MAR}{MAR_P_0}*100) <br>
dengan `MAR` = rerata error absolut dari prediktor.

## Improved SA
Diusulkan oleh [2], karena perhitungan sebelumnya bersifat stokastik dan bias. Perhitungannya menjadi: <br>
![equation](https://latex.codecogs.com/gif.latex?MAR_P_0=\frac{2}{n^2}\sum_{i=1}^{n}\sum_{j=1}^{j<i}|y_i-y_j|)

## Referensi
[2] Langdon, W. B. et al. (2016) ‘[Exact Mean Absolute Error of Baseline Predictor, MARP0’, Information and Software Technology. Elsevier B.V., 73, pp. 16–18. doi: 10.1016/j.infsof.2016.01.003.](https://linkinghub.elsevier.com/retrieve/pii/S0950584916000057)
