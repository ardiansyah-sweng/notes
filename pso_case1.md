# Optimasi Use Case Weighting pada Estimasi Effort Perangkat Lunak UCP
Studi kasus ini akan melakukan optimasi pada parameter bobot use case untuk estimasi effort perangkat lunak Use Case Points. <br>

## Tahapan Optimasi
### Setting Parameter
C<sub>1</sub> = 2 <br>
C<sub>2</sub> = 2 <br>
R<sub>1</sub> = nilai acak [0,1] <br>
R<sub>2</sub> = nilai acak [0,1] <br>
Iterasi maksimum = 40 <br>
Jumlah partikel = 70 <br>
Nilai fitness = 200 <br>
Productivity = 20 <br>
Inersia maksimum = 0.9 <br>
Inersia minimum = 0.4

### Bangkitkan populasi awal

#### Buat fungsi menghitung size atau UCP
Lihat materi [Use Case Points](https://github.com/ardiansyah-sweng/notes/blob/main/use_case_points.md) di `Persamaan (6)`

```php
function size($xSimple, $simpleUC, $xAverage, $averageUC, $xComplex, $complexUC, $uaw, $tcf, $ecf)
{
  $ucSimple = $xSimple * $simpleUC;
  $ucAverage = $xAverage * $averageUC;
  $ucComplex = $xComplex * $complexUC;

  $UUCW = $ucSimple + $ucAverage + $ucComplex;
  $UUCP = $uaw + $UUCW;
  return $UUCP * $tcf * $ecf;
}
```
#### Buat fungsi mengambil nilai acak bobot use case Simple

```php
/**
* Generate random Simple Use Case Complexity weight parameter
* Min = 5,     
* Max = 7.49
*/
function randomSimpleUCWeight()
{
  $MIN = 5;
  $MAX = 7.49;
  return mt_rand($MIN * 100, $MAX * 100) / 100;
}
```

#### Buat fungsi mengambil nilai acak bobot use case Average

```php
/**
* Generate random Average Use Case Complexity weight parameter
* Min = 7.5     
* Max = 12.49
*/
function randomAverageUCWeight()
{
  $MIN = 7.5;
  $MAX = 12.49;
  return mt_rand($MIN * 100, $MAX * 100) / 100;
}
```

#### Buat fungsi mengambil nilai acak bobot use case Complex

```php
/**
* Generate random Complex Use Case Complexity weight parameter
* Min = 12.5     
* Max = 15
*/
function randomComplexUCWeight()
{
  $MIN = 12.5;
  $MAX = 15;
  return mt_rand($MIN * 100, $MAX * 100) / 100;
}
```

```php
## Generate population
for ($i = 0; $i <= $this->swarm_size - 1; $i++) {
  $xSimple = $this->randomSimpleUCWeight();
  $xAverage = $this->randomAverageUCWeight();
  $xComplex = $this->randomComplexUCWeight();

  $UCP = $this->size($xSimple, $project['simpleUC'], $xAverage, $project['averageUC'], $xComplex, $project['complexUC'], $project['uaw'], $project['tcf'], $project['ecf']);
  $esimated_effort = $UCP * $this->productivity_factor;
  $initial_particles[$i]['estimatedEffort'] = $esimated_effort;
  $initial_particles[$i]['ucp'] = $UCP;
  $initial_particles[$i]['ae'] = abs($esimated_effort - $project['actualEffort']);
  $initial_particles[$i]['xSimple'] = $xSimple;
  $initial_particles[$i]['xAverage'] = $xAverage;
  $initial_particles[$i]['xComplex'] = $xComplex;
} ## End Generate Population
```


## Dataset
Silakan unduh [datasetnya di sini](https://github.com/ardiansyah-sweng/ucwpso/blob/main/silhavy_dataset.txt) 
