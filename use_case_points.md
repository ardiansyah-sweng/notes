# Use Case Points

## Apa itu Use Case Points?
## Mengapa menggunakan Use Case Points?

## Bagaimana menggunakan Use Case Points?
###  Pembobotan _Actor_
<a href="https://www.codecogs.com/eqnedit.php?latex=UAW=\sum_{i=1}^{3}W_i*A_i" target="_blank"><img src="https://latex.codecogs.com/svg.latex?UAW=\sum_{i=1}^{3}W_i*A_i" title="UAW=\sum_{i=1}^{3}W_i*A_i" /></a>
<p>
dengan:<br>
  W<sub>i</sub> = bobot aktor. Simple = 1, Average = 2, Complex = 3 <br>
A<sub>i</sub> = jumlah aktor pada diagram use case

### Unadjusted Use Case Weighting (UUCW)
<a href="https://www.codecogs.com/eqnedit.php?latex=UUCW=\sum_{i=1}^{3}W_i*UC_i" target="_blank"><img src="https://latex.codecogs.com/svg.latex?UUCW=\sum_{i=1}^{3}W_i*UC_i" title="UUCW=\sum_{i=1}^{3}W_i*UC_i" /></a>
<p>
  dengan: <br>
  W<sub>i</sub> = bobot use case. Simple = 5, Average = 10, Complex = 15 <br>
  UC<sub>i</sub> = jumlah transaksi berdasarkan diagram spesifikasi use case

### Unadjusted Use Case Points (UUCP)
<a href="https://www.codecogs.com/eqnedit.php?latex=UUCP=UAW&plus;UUCW" target="_blank"><img src="https://latex.codecogs.com/svg.latex?UUCP=UAW&plus;UUCW" title="UUCP=UAW+UUCW" /></a>

### Technical Complexity Factors (TCF)
<a href="https://www.codecogs.com/eqnedit.php?latex=TCF=0.6&plus;\left&space;(&space;0.01*\sum_{i=1}^{13}W_i*G_i&space;\right&space;)" target="_blank"><img src="https://latex.codecogs.com/svg.latex?TCF=0.6&plus;\left&space;(&space;0.01*\sum_{i=1}^{13}W_i*G_i&space;\right&space;)" title="TCF=0.6+\left ( 0.01*\sum_{i=1}^{13}W_i*G_i \right )" /></a>
<p>
  dengan: <br>
  W<sub>i</sub> = Bobot instrumen ke-_i_<br>
  G<sub>i</sub> = Nilai instrumen ke-_i_

### Environmental Complexity Factors (ECF)
<a href="https://www.codecogs.com/eqnedit.php?latex=ECF=1.4&plus;\left&space;(-0.03*\sum_{i=1}^{8}W_i*G_i&space;\right&space;)" target="_blank"><img src="https://latex.codecogs.com/svg.latex?ECF=1.4&plus;\left&space;(-0.03*\sum_{i=1}^{8}W_i*G_i&space;\right&space;)" title="ECF=1.4+\left (-0.03*\sum_{i=1}^{8}W_i*G_i \right )" /></a>
<p>
  dengan:<br>
  W<sub>i</sub> = Bobot instrumen ke-_i_<br>
  G<sub>i</sub> = Nilai instrumen ke-_i_
  
### UCP  
<a href="https://www.codecogs.com/eqnedit.php?latex=UCP=UUCP*TCF*ECF" target="_blank"><img src="https://latex.codecogs.com/svg.latex?UCP=UUCP*TCF*ECF" title="UCP=UUCP*TCF*ECF" /></a>

### Estimasi Effort
<a href="https://www.codecogs.com/eqnedit.php?latex=Effort=UCP*PF" target="_blank"><img src="https://latex.codecogs.com/svg.latex?Effort=UCP*PF" title="Effort=UCP*PF" /></a>
<p>
Satuan estimasi effort adalah _person/hours_ untuk setiap 1 UCP. Productivity factor (PF) bisa ditentukan dengan berbagai macam cara:<br>
  1. Menggunakan PF standar Karner yaitu 20
  2. 8.2 person-hours/UCP [2]
  3. Memproses _learning productivity ratio_ sendiri terlebih dahulu seperti yang dilakukan [1]
Sebagai saran, gunakan PF 20 jika kita belum memiliki data histori proyek, atau data histori masih sedikit (1-3)

## Referensi
[1] Azzeh, M. and Nassif, A. B. (2018) ‘Project productivity evaluation in early software effort estimation’, Journal of Software: Evolution and Process, 30(12), pp. 1–12. doi: 10.1002/smr.2110.
[2] Subriadi, Pribadi, A. and Ningrum, P. A. (2014) ‘Critical Review of the Effort Rate Value in Use Case Point Method for Estimating Software Development Effort’, 59(3), pp. 735–744.
