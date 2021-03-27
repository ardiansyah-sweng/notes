# Clustering
## Prasyarat: `array`, `loop`
## Apa itu Clustering?
Clustering adalah proses pengelompokan sebuah himpunan objek ke beberapa cluster, sedemikian sehingga objek-objek di dalam cluster yang sama memiliki kemiripan (_similarity_) satu sama lain, namun memiliki ketidakmiripan (_dissimilarity_) dengan objek-objek di cluster yang berbeda/lainnya. <br>

## Model-Model Clustering
1. Connectivity. contoh: `hierarchical clustering`
2. Centroid. contoh: `k-means`, `k-medoids`, `k-medians`, `fuzzy c-means`
3. Distribution. contoh: `expectation-maximization (EM)`
4. Density: contoh: Density-based spatial clustering of applications with noise (`DBSCAN`), Ordering points to identify the clustering structure (`OPTICS`)
5. Subspace. Contoh: `biclustering`
6. Graph. Contoh:
7. Signed graph. Contoh:
8. Neural. Contoh: 

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
