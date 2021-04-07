# Particle Swarm Optimization

Tahap **eksplorasi** dilakukan pada tahap awal pencarian, kemudian secara bertahap/perlahan melakukan tahap **eksploitasi** terhadap solusi terbaik yang ditemukan. Baik eksplorasi maupun eksploitasi harus dilakukan secara seimbang.

## Kelemahan PSO
Premature convergence adalah salah satu kelemahan dari PSO. Premature convergence adalah situasi di mana partikel menganggap dirinya sudah menemukan solusi optimum, padahal tidak. Atau partikel-partikel sudah mengumpul pada titik yang dianggap optimal. Dengan kata lain terjebak dalam **optimum lokal**. Penyebab konvergen prematur adalah _loss of diversity_. Oleh karena itu solusinya adalah dengan meningkatkan _diversity_ partikel.

