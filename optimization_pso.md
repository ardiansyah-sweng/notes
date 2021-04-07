# Particle Swarm Optimization

Tahap **eksplorasi** dilakukan pada tahap awal pencarian, kemudian secara bertahap/perlahan melakukan tahap **eksploitasi** terhadap solusi terbaik yang ditemukan. Baik eksplorasi maupun eksploitasi harus dilakukan secara seimbang.

## Kelemahan PSO
Premature convergence adalah salah satu kelemahan dari PSO. Premature convergence adalah situasi di mana partikel menganggap dirinya sudah menemukan solusi optimum, padahal tidak. Atau partikel-partikel sudah mengumpul pada titik yang dianggap optimal. Dengan kata lain terjebak dalam **optimum lokal**. Penyebab konvergen prematur adalah _loss of diversity_. Oleh karena itu solusinya adalah dengan meningkatkan _diversity_ partikel.<br>
Diversity adalah ukuran atau tingkat dispersi (sebaran) partikel dalam _swarm_ [1]. Sebaran ini bisa ditentukan di sekitar titik pusat, atau tidak. Dispersi jug abisa ditentukan berdasarkan **posisi** atau _velocity_ partikel. 

# Referensi
[1] Olorunda, O. and Engelbrecht, A. P. (2008) ‘Measuring exploration/exploitation in particle swarms using swarm diversity’, 2008 IEEE Congress on Evolutionary Computation, CEC 2008, pp. 1128–1134. doi: 10.1109/CEC.2008.4630938.
