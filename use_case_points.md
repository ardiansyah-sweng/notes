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
## Referensi
