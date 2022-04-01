# serialize

- Generates a storable representation of a value.
- Useful for storing or passing PHP values around without losing their type and structure.
- Doesnt store methods or static properties.
- Output should generally be stored in a BLOB field in a database, rather than a CHAR or TEXT field.

```php
$obj = new stdClass;
$obj->a = null;
$output = serialize(["Green", 50.02, $obj]);

// var_dump
// string(67) "a:3:{i:0;s:5:"Green";i:1;d:50.02;i:2;O:8:"stdClass":1:{s:1:"a";N;}}"
```

Documentation: https://www.php.net/manual/en/function.serialize.php

# unserialize
```php
unserialize('a:3:{i:0;s:5:"Green";i:1;d:50.02;i:2;O:8:"stdClass":1:{s:1:"a";N;}}');

// var_dump
// array(3) { [0]=> string(5) "Green" [1]=> float(50.02) [2]=> object(stdClass)#2 (1) { ["a"]=> NULL } }
```
Documentation: https://www.php.net/manual/en/function.unserialize.php

[<< Back](../README.md)