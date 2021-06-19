# Standarisasi Kode Program
Dokumen ini berisi konvensi standarisasi penulisan kode program yang digunakan pada proyek perangkat lunak atau perkuliahan terkait software engineering.

## Penamaan `Class`
Gunakan **kata benda** <br>
Jika terdiri dari lebih dua kata, maka setiap huruf pertama di awal kata, gunakan huruf besar <br>
Format: `KataBenda`<br>
Contoh:<br> 
`Employee`, `BestEmployee`, `SwarmOptimizer`, `RegisteredMember`

## Penamaan `Method` atau `Function`
Minimal mengandung satu **kata kerja** <br>
Jika terdiri dari lebih dua kata, maka di awal kata gunakan huruf kecil dengan `camelCase` <br>
Format: `<something>kataBenda` atau `kataBenda<something>`<br>
Contoh:<br> 
`addToCart()`<br>
`saveToStore()`<br>
`getMinimumPayment()`<br>
`countAllRegisteredUser()`<br>
`isBirthday()`

## Penamaan Variabel
Variabel harus memiliki makna yang sesuai dengan data yang disimpan beserta tipe datanya <br>
Jika terdiri dari lebih dua kata, maka di awal kata gunakan huruf kecil dengan `camelCase` <br>
Format: `<something>variabel` atau `variabel<something>`<br>

### Variabel yang pasti bernilai integer
Contoh: `$studentAge`, `$yearOfEntrance`<br>
#### Menunjukkan jumlah atau frekuensi <br>
Format: `<numberOf>something`<br>
Contoh: `$numberOfRegisteredUser`, atau <p>
  
Format: `<something>Count`. <br>
Contoh: `$studentCount`, atau <p>
  
Format: `times<something>`. <br>
Contoh: `$timesViewed`, `$timesVisited`

### Variabel selain integer
Usahakan di bagian akhir menunjukkan satuannya <br>
Format: `<something>InMilisecond`.<br>
Contoh: `$cpuSpeedInMilisecond`<p>
  
Format: `<something>In<currency code>`.<br>
Contoh: `$totalCostInIDR`<p>
  
Format: `<something>inCentimeter`. <br>
Contoh: `$squareLengthInCentimeter` <p> 
  
Format: `<something>inDecimal` <br>
Contoh: `$absoluteErrorInDecimal`, `$discountInDecimal`

### Variabel `array`
Harus dalam bentuk jamak
Jika terdiri dari lebih dua kata, maka di awal kata gunakan huruf kecil dengan `camelCase` <br>

#### Array 1-Dimensi
Contoh: <br>
`$studentsAge = []` <br>
`$yearsOfEntrance = []` <br>
`$numberOfRegisteredUsers = []` <br>
`$fruitsName = []` <br>
`$cpuSpeedsInMilisecond = []` <br>
`$pricesInIDR = []` <br>
`$squareLengthsInCentimeter = []` <br>
`$absoluteErrorsInDecimal = []` <br>
`$temperatureInCelcius = []` <br>
 
#### Array Multidimensi

