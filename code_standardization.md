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
`addToCart()`, `saveToStore()`, `getMinimumPayment()`, `countAllRegisteredUser()`, `isBirthday()`

## Penamaan Variabel
Variabel harus memiliki makna yang sesuai dengan data yang disimpan beserta tipe datanya <br>
Jika terdiri dari lebih dua kata, maka di awal kata gunakan huruf kecil dengan `camelCase` <br>
Format: `<something>variabel` atau `variabel<something>`<br>

### Variabel tunggal yang pasti bernilai integer
Contoh: `$studentAge`, `$yearOfEntrance`<br>
#### Menunjukkan jumlah atau frekuensi <br>
`<numberOf>something`. Contoh: `$numberOfRegisteredUser`, atau <br>
`<something>Count`. Contoh: `$studentCount`, atau <br>
`times<something>`. Contoh: `$timesViewed`, `$timesVisited`
