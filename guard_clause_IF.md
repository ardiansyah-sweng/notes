# Guard Clause

### Materi: Dasar Algoritma dan Pemrograman Modern
* Tingkat: Advanced
* Prasyarat Utama: `conditional`
* Prasyarat Tambahan: -

## Prinsip conditional `IF` dengan Guard Clause
* Me-`return` suatu nilai secepat mungkin.
* Proritaskan me-`return` kondisi yang tidak normal/tidak diinginkan
* Kondisi yang diharapkan di-`return` terakhir
* Usahakan dikemas dalam sebuah `function`

## Contoh guard clause dalam `function`
```php
    function inputValidation()
    {
        if (empty($this->email) || empty($this->password)) {
            return 'Username or password is empty!';
        }
        if (!filter_var($this->email, FILTER_VALIDATE_EMAIL)) {
            return "Invalid email format!";
        }
        if (strlen($this->password) < 6) {
            return "Your Password Must Contain At Least 6 Characters!";
        }
        if (!preg_match("#[0-9]+#", $this->password) && !preg_match("#[A-Z]+#", $this->password)) {
            return "Your Password Must Contain At Least 1 Number or capital letter! ";
        }
        return 'Welcome, ' . $email;
    }
```
### Output
> Welcome <email>

## Contoh guard clause jika tidak dalam sebuah `function`
Note: baru dicoba dalam `PHP`
```php
...
if (empty($this->email) || empty($this->password)) {
    echo 'Username or password is empty!';
    exit();
}
if (!filter_var($this->email, FILTER_VALIDATE_EMAIL)) {
    echo "Invalid email format!";
    exit();
}
if (strlen($this->password) < 6) {
    echo "Your Password Must Contain At Least 6 Characters!";
    exit();
}
if (!preg_match("#[0-9]+#", $this->password) && !preg_match("#[A-Z]+#", $this->password)) {
    echo "Your Password Must Contain At Least 1 Number or capital letter! ";
    exit();
}
echo 'Welcome, ' . $email;
...
```
### Output
> Welcome, [email]
