# Particle Swarm Optimization
Prasyarat: `optimasi`, `array`, `loop`,  `vektor` <p>

Tulisan ini membahas secara lengkap salah satu algoritma optimasi metaheuristik yaitu Particle Swarm Optimization (PSO). Perlu diingat kembali, bahwa sebagai optimasi metaheuristik, PSO tidak menjanjikan hasil yang deterministik/pasti/_exact_, melainkan perkiraan hasil yang terbaik mendekati.

## Apa itu PSO?
Sebagai analogi, PSO itu sama saja seperti kita mengerahkan satu tim untuk menemukan anak/benda yang hilang. Anak/benda tersebut tidak diketahui posisi/lokasi persisnya, kita cuma tahu perkiraan lokasinya. Setiap anggota memiliki peluang/kesempatan yang sama untuk menemukan target. Tim diberikan batas waktu dalam melakukan pencarian. Di akhir waktu, salah satu anggota tim yang paling dekat dengan target yang dicari dinyatakan sebagai anggota terbaik yang menemukan objek tersebut. <br>
Seperti halnya di dunia nyata, pencarian tentu saja menuntut para pencari untuk bergerak atau berpindah dari posisi yang berbeda-beda. Setiap anggota/partikel dibekali informasi terkait posisi terkini masing-masing temannya. Sehingga bisa diketahui mana posisi teman yang paling dekat dengan target. Begitu pula, setiap anggota memiliki histori informasi posisi di setiap perpindahannya selama ini. <br>
Begitulah kira-kira analogi utama cara kerja PSO. Sedangkan secara ilmiah, PSO sendiri ditemukan oleh [3] yang terinspirasi dari segerombolan hewan yang bergerak menemukan makanan seperti ikan dan burung. Bisa Anda baca lengkap di sana. 

## Cara kerja PSO
Cara kerja PSO sebenarnya sederhana, setiap partikel akan bergerak menuju ke target pencarian. Karena bergerak, maka terjadi perpindahan dari posisi lama ke posisi baru. Perpindahan tersebut juga karena kecepatan (_velocity_). Sehingga formulanya seperti `Persamaan 1` berikut: <p>
<a href="https://www.codecogs.com/eqnedit.php?latex=v(t&plus;1)&space;=&space;\omega&space;v(t)&plus;C_1R_1(Pbest_i-x_i)&plus;C_2R_2(Gbest_i-x_i)" target="_blank"><img src="https://latex.codecogs.com/svg.latex?v(t&plus;1)&space;=&space;\omega&space;v(t)&plus;C_1R_1(Pbest_i-x_i)&plus;C_2R_2(Gbest_i-x_i)" title="v(t+1) = \omega v(t)+C_1R_1(Pbest_i-x_i)+C_2R_2(Gbest_i-x_i)" /></a>

dengan: <br>
v<sub>i</sub>(t+1) = velocity baru partikel ke-_i_ <br>
v<sub>i</sub> = velocity saat ini. Ketika v<sub>0</sub>, nilainya diambil acak antara [0,1] <br>
&omega; = bobot inersia <br>
C<sub>1</sub> = Faktor pembelajaran kognitif <br>
C<sub>2</sub> = Faktor pembelajaran sosial <br>
Pbest<sub>i</sub> = Posisi terbaik yang pernah diperoleh setiap partikel <br>
x<sub>i</sub> = Posisi partikel saat ini <br>
R<sub>1</sub> dan R<sub>2</sub> = nilai acak antara [0,1] <br>
Gbest<sub>i</sub> = Posisi terbaik dari seluruh partikel
<p>
Bobot inersia ditentukan pada `Persamaan 2` berikut: <p>
<a href="https://www.codecogs.com/eqnedit.php?latex=\omega(t)&space;=&space;\omega_{max}&plus;\frac{(\omega_{max}-\omega_{min}).t}{T_{max}}" target="_blank"><img src="https://latex.codecogs.com/svg.latex?\omega(t)&space;=&space;\omega_{max}&plus;\frac{(\omega_{max}-\omega_{min}).t}{T_{max}}" title="\omega(t) = \omega_{max}-\frac{(\omega_{max}-\omega_{min}).t}{T_{max}}" /></a>

dengan: <br>
&omega;(_t_) = bobot inersia iterasi ke-_t_ <br>
&omega;<sub>_max_</sub> = inersia maksimum yaitu 0.9<br>
&omega;<sub>_min_</sub> = inersia minimum yaitu 0.4<br>
_t_ = iterasi saat ini<br>
_T<sub>max</sub>_ = Iterasi maksimum <p>
   
Setelah diperoleh _velocity_ baru, maka partikel bisa memperbarui posisinya dengan `Persamaan 3` berikut: <p>
<a href="https://www.codecogs.com/eqnedit.php?latex=x(t&plus;1)&space;=&space;x_t&plus;v(t&plus;1)" target="_blank"><img src="https://latex.codecogs.com/svg.latex?x(t&plus;1)&space;=&space;x_t&plus;v(t&plus;1)" title="x(t+1) = x_t+v(t+1)" /></a>

dengan: <br>
x(_t_+1) = posisi terbaru partikel <br>
x(_t_) = posisi partikel saat ini <br>
v(_t_+1) = velocity terbaru <br>
_t_ = iterasi saat ini 

## Mengapa PSO?
## Kapan menggunakan PSO?
## Bagaimana menggunakan PSO?
Sebelum terjun melakukan pencarian, maka perlu dilakukan berbagai persiapan atau istilahnya _setting_ parameter.<br>
1. Ukuran populasi<br>
   Populasi sama saja dengan tim pencari yang terdiri dari banyak orang seperti analogi di bagian **Apa itu PSO?**. Sedangkan populasi berisi banyak partikel. Untuk itu perlu terlebih dahulu menentukan berapa ukuran populasinya. Anda bisa memilih antara 20-500 partikel [4] atau menentukan sendiri berdasarkan hasil eksperimen awal seperti yang dilakukan [5]. 
2. Iterasi maksimal <br>
   Iterasi sama saja dengan berapa lama pencarian dilakukan. Dalam prakteknya, iterasi ini adalah berapa kali terjadi perubahan posisi dari setiap partikel dalam rangka menuju ke target yang dituju. Anda bisa memilih iterasi di atas 20, atau menentukan sendiri berdasarkan eksperimen awal seperti yang dilakukan [5].
3. Faktor pembelajaran (_learning factors_) <br>
   Sebagaimana manusia, kita akan belajar atas keberhasilan di masa lampau, dan juga belajar dari keberhasilan orang lain di masa lalu. Begitu pula pada PSO, ada dua faktor pembelajaran yaitu faktor pembelajaran kognitif (C<sub>1</sub>) dan faktor pembelajaran sosial (C<sub>2</sub>). Nilai C<sub>1</sub> dan C<sub>2</sub> berupa konstan yaitu 2 (C<sub>1</sub>=C<sub>2</sub>=2).

Setelah _setting_ parameter disiapkan, maka perjuangan pencarian target bisa mulai dilaksanakan. <br>
Langkah pertama adalah menerjunkan tim atau partikel ke area pencarian. Sebagaimana halnya operasi pencarian, maka setiap anggota akan diterjunkan ke aera/wilayah yang dianggap merupakan tempat target bersembunyi/terletak. Karena di awal pencarian belum ada gambaran di mana target tersembunyi maka seluruh anggota akan berpencar ke titik-titik lokasi awal yang berbeda-beda. Perlu diingat bahwa semakin berbeda titik lokasi penempatan antaranggota satu dengan yang lain maka akan semakin baik. Karena hal ini bisa semakin memperbesar peluang menemukan target. Coba bayangkan saja jika satu tim diterjunkan pada titik lokasi yang hampir sama/berdekatan, tentu peluang untuk menemukan target menjadi kecil, karena bisa saja target berada jauh dari titik penerjunan tersebut. Tahap awal pencarian ini disebut sebagai tahap eksplorasi. <p>
   


Tahap **eksplorasi** dilakukan pada tahap awal pencarian, kemudian secara bertahap/perlahan melakukan tahap **eksploitasi** terhadap solusi terbaik yang ditemukan. Baik eksplorasi maupun eksploitasi harus dilakukan secara seimbang. Setelah beberapa kali melakukan perpindahan posisi, maka semua tim akan berpindah menuju pada titik yang sama yaitu ke arah target pencarian. Pergerakan menuju ke titik yang sama ini disebut **konvergen**.

## Kelemahan PSO
Premature convergence adalah salah satu kelemahan dari PSO. Premature convergence adalah situasi di mana partikel menganggap dirinya sudah menemukan solusi optimum, padahal tidak. Atau partikel-partikel sudah mengumpul pada titik yang dianggap optimal. Dengan kata lain terjebak dalam **optimum lokal**. Penyebab konvergen prematur adalah _loss of diversity_. Oleh karena itu solusinya adalah dengan meningkatkan _diversity_ partikel.<br>
Diversity adalah ukuran atau tingkat dispersi (sebaran) partikel dalam _swarm_ [1]. Sebaran ini bisa ditentukan di sekitar titik pusat, atau tidak. Dispersi jug abisa ditentukan berdasarkan **posisi** atau _velocity_ partikel. Diversity berperan penting, karena agar bisa memastikan partikel eksplorasi dan eksploitasi dengan baik. Diversity partikel yang rendah mengakibatkan partikel akan fokus pencarian solusi pada area yang sempit. 

## Ukuran Diversity
Ukuran Diversity pertama kali diusulkan oleh [2]. Jarak ke rerata titik <br>
<a href="https://www.codecogs.com/eqnedit.php?latex=diversity(S)=\frac{1}{\left&space;|&space;S&space;\right&space;|}.\sum_{i=1}^{\left&space;|&space;S&space;\right&space;|}{\sqrt{\sum_{j=1}^{N}(p_i_j-\bar{p}_j)^2&space;}}" target="_blank"><img src="https://latex.codecogs.com/svg.latex?diversity(S)=\frac{1}{\left&space;|&space;S&space;\right&space;|}.\sum_{i=1}^{\left&space;|&space;S&space;\right&space;|}{\sqrt{\sum_{j=1}^{N}(p_i_j-\bar{p}_j)^2&space;}}" title="diversity(S)=\frac{1}{\left | S \right |}.\sum_{i=1}^{\left | S \right |}{\sqrt{\sum_{j=1}^{N}(p_i_j-\bar{p}_j)^2 }}" /></a>

dengan:<br>
S = populasi <br>
|S| = ukuran _swarm_ <br>
N = ukuran dimensi masalah <br>
p<sub>ij</sub> = nilai ke-_j_ dari partikel ke-_i_ <br>
<a href="https://www.codecogs.com/eqnedit.php?latex=\bar{p}_j" target="_blank"><img src="https://latex.codecogs.com/svg.latex?\bar{p}_j" title="\bar{p}_j" /></a> = rerata dimensi ke-_j_

# Referensi
[1] Olorunda, O. and Engelbrecht, A. P. (2008) ‘Measuring exploration/exploitation in particle swarms using swarm diversity’, 2008 IEEE Congress on Evolutionary Computation, CEC 2008, pp. 1128–1134. doi: 10.1109/CEC.2008.4630938. <br>
[2] Krink, T., Vesterstrom, J. S. and Riget, J. (2002) ‘Particle swarm optimisation with spatial particle extension’, Proceedings of the 2002 Congress on Evolutionary Computation, CEC 2002, 2, pp. 1474–1479. doi: 10.1109/CEC.2002.1004460. <br>
[3] Kennedy, J. and Eberhart, R. (1995) ‘Particle swarm optimization’, in Proceedings of ICNN’95 - International Conference on Neural Networks. IEEE, pp. 1942–1948. doi: 10.1109/ICNN.1995.488968. <br>
[4] Piotrowski, A. P., Napiorkowski, J. J. and Piotrowska, A. E. (2020) ‘Population size in Particle Swarm Optimization’, Swarm and Evolutionary Computation. Elsevier Ltd, 58(May), p. 100718. doi: 10.1016/j.swevo.2020.100718. <br>
[5] Tharwat, A. et al. (2019) ‘Intelligent Bézier curve-based path planning model using Chaotic Particle Swarm Optimization algorithm’, Cluster Computing. Springer US, 22(S2), pp. 4745–4766. doi: 10.1007/s10586-018-2360-3.
