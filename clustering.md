# Clustering
## Prasyarat: `array`, `loop`, `jarak`, `similarity`
## Apa itu Clustering?
Clustering adalah proses pengelompokan sebuah himpunan objek ke beberapa cluster, sedemikian sehingga objek-objek di dalam cluster yang sama memiliki kemiripan satu sama lain, namun memiliki ketidakmiripan dengan objek-objek di cluster yang berbeda/lainnya. <br>

## Model atau Jenis Clustering
1. Connectivity. contoh: `hierarchical clustering`
2. Centroid/Partition. contoh: `k-means`, `k-medoids`, `k-medians`, `fuzzy c-means`.<br>
   - Cluster berbasis _centroid_ memiliki keunggulan dari sisi efisiensi, namun kelemahannya tidak cocok untuk data _non-convex_, mudah terjebak pada optimum lokal, jumlah _cluster_ harus di _preset_, sensitif pada penentuan kondisi awal (jumlah _cluster_) dan pencilan (_outlier_).
   - Apa itu `centroid`? Centroid adalah titik pusat dari sebuah _cluster_  
3. Distribution. contoh: `expectation-maximization (EM)`
4. Density: contoh: Density-based spatial clustering of applications with noise (`DBSCAN`), Ordering points to identify the clustering structure (`OPTICS`)
5. Subspace. Contoh: `biclustering`
6. Graph. Contoh:
7. Signed graph. Contoh:
8. Neural. Contoh: 

### Jarak (_dissimilarity_)
Jarak (_dissimilarity_) dan _similarity_ merupakan konstruksi dasar pembentuk _clustering_. Jika data bertipe **kuantitatif**, maka gunakan fungsi jarak untuk mengetahui hubungan antardata. Sedangkan jika data bertipe **kualitatif**, maka gunakan fungsi _similarity_.<br>
Fungsi-Fungsi Jarak
1. Minkowski
2. Standardized Euclidean
3. Cosine
4. Pearson correlation
5. Mahalanobis

Fungsi-Fungsi _similarity_
1. Jaccard
2. Hamming

## Mengapa Clustering?
## Bagaimana melakukan Clustering berbasis _centroid_?
1. Tentukan jumlah _cluster_ yang akan dibentuk
2. Tentukan _centroid_ (c<sub>i</sub>) masing-masing _cluster_ (C<sub>i</sub>). <br> Penentuan _centroid_ dilakukan secara acak.
3. Definisikan kemiripan antarobjek
4. Masukkan setiap objek ke dalam _cluster_ yang sesuai 

## Evaluasi Clustering
### Evaluasi Internal
1. Davies–Bouldin index
2. Dunn index
3. Silhouette coefficient
### Evaluasi Eksternal
1. Purity
2. Rand index
3. F-measure
4. Jaccard index
5. Dice index
6. Fowlkes–Mallows index
7. Mutual information
8. Confusion matrix
### Tendensi _Cluster_
Hopkins statistic

## Referensi
[1] Xu, D. and Tian, Y. (2015) [‘A Comprehensive Survey of Clustering Algorithms’, Annals of Data Science. Springer Berlin Heidelberg, 2(2), pp. 165–193. doi: 10.1007/s40745-015-0040-1.](https://link.springer.com/article/10.1007/s40745-015-0040-1)
