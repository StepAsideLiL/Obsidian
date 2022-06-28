# `include` and `require`
- Both expressions **work the same** and produce **the same result**.
- Copy all the content or code into the place of `include` in the file.

##### `include`
```php
// a-file.php
echo 'Hello from a-file.php';
```

```php
// index.php
include 'a-file.php';
echo 'Hello from index.php';
```

```
Output:
Hello from a-file.php
Hello from index.php
```

##### `require`
```php
// a-file.php
echo 'Hello from a-file.php';
```

```php
// index.php
require 'a-file.php';
echo 'Hello from index.php';
```

```
Output:
Hello from a-file.php
Hello from index.php
```

**The code above is same as this**
```php
echo 'Hello from a-file.php'
echo 'Hello from index.php';
```

```
Output:
Hello from a-file.php
Hello from index.php
```

<br>
# `include` vs `require`
#### If `a-file.php` does not exist,
|    **`include`**     | **`require`**            |
|:--------------------:| ------------------------ |
| Show **warning** message | Show **fatal error** message |

<br>
# `require` vs `require_once`
| **`require`**                                                                          | **`require_once`**                                                                                                          |
| -------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| include a PHP file into another file whether the file is included before or not. | first check whether a file is already included or not and if it is already included then it will not include it again.|
| include a certain code again and again                                           | include a certain code just once.                                                                                     |
| Use **`require`** to load template-like files.                                         | Use **`require_once`** to load dependencies ( classes, functions, constants).                                               |
| **`require`** function will execute every time it is called.                           | **`require_once`** function will not execute every time it is called                                                        |


### More info
- [PHP: include - Manual](https://www.php.net/manual/en/function.include.php)
- [PHP: require - Manual](https://www.php.net/manual/en/function.require.php)
- [Describe PHP Include and Require - GeeksforGeeks](https://www.geeksforgeeks.org/describe-php-include-and-require/)
- [Describe PHP Include and Require - GeeksforGeeks](https://www.geeksforgeeks.org/describe-php-include-and-require/)
