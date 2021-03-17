# Constructor
### Materi: OOP
* Tingkat: Dasar
* Prasyarat: `function`, `class`, `object`

## Dasar `constructor`
```php
<?php

/**
 * SignUp
 * @Input parameter: email, password
 * @Output: validation messages or redirect to dashboard page
 */
class SignUp
{
    function __construct()
    {
        echo 'Tes constructor';
    }
}

$tes = new SignUp;
```
### Output
>Tes constructor

## Class dengan `constructor`

```php
<?php

/**
 * SignUp
 * @Input parameter: email, password
 * @Output: validation messages or redirect to dashboard page
 */
class SignUp
{
    protected $email;
    protected $password;

    function __construct($email, $password)
    {
        $this->email = $email;
        $this->password = $password;
    }

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
        
        session_start();
        $_SESSION['username'] = $this->email;
        header("location: dashboard.php");
    }
}

$tes = new SignUp("","");
echo $tes->inputValidation();
```

### Output
> Username or password is empty!

## Class tanpa `constructor`
```php
<?php

/**
 * SignUp
 * @Input parameter: email, password
 * @Output: validation messages or redirect to dashboard page
 */
class SignUp
{
    function inputValidation($email, $password)
    {
        if (empty($email) || empty($password)) {
            return 'Username or password is empty!';
        }
        if (!filter_var($email, FILTER_VALIDATE_EMAIL)) {
            return "Invalid email format!";
        }
        if (strlen($password) < 6) {
            return "Your Password Must Contain At Least 6 Characters!";
        }
        if (!preg_match("#[0-9]+#", $password) && !preg_match("#[A-Z]+#", $password)) {
            return "Your Password Must Contain At Least 1 Number or capital letter! ";
        }
        
        session_start();
        $_SESSION['username'] = $email;
        header("location: dashboard.php");
    }
}

echo SignUp::inputValidation("","");
```
### Output
> Username or password is empty!
