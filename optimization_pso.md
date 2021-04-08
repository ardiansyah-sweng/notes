# Particle Swarm Optimization
Tulisan ini membahas secara lengkap salah satu algoritma optimasi metaheuristik yaitu Particle Swarm Optimization (PSO). 

## Apa itu PSO?
PSO itu sama saja seperti kita mengerahkan satu tim untuk menemukan anak/benda yang hilang. Anak/benda tersebut tidak diketahui posisi/lokasi persisnya, kita cuma tahu perkiraan lokasinya. Tim diberikan batas waktu dalam melakukan pencarian. Di akhir waktu, salah satu anggota tim yang paling dekat dengan target yang dicari dinyatakan sebagai orang yang menemukan objek tersebut. <br>
Begitulah kira-kira analogi utama cara kerja PSO. Sedangkan secara ilmiah, PSO sendiri ditemukan oleh [3] yang terinspirasi dari segerombolan hewan yang bergerak menemukan makanan seperti ikan dan burung. Bisa Anda baca lengkap di sana.

## Mengapa PSO?
## Bagaimana menggunakan PSO?

Tahap **eksplorasi** dilakukan pada tahap awal pencarian, kemudian secara bertahap/perlahan melakukan tahap **eksploitasi** terhadap solusi terbaik yang ditemukan. Baik eksplorasi maupun eksploitasi harus dilakukan secara seimbang.

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
[3] Kennedy, J. and Eberhart, R. (1995) ‘Particle swarm optimization’, in Proceedings of ICNN’95 - International Conference on Neural Networks. IEEE, pp. 1942–1948. doi: 10.1109/ICNN.1995.488968.
