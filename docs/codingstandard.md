### PSR-1 Basic Coding Standard
#### 1. [Overview](./PSR-1-basic-coding-standard.md#1-overview)
#### 2. [Files]
[Files]: ./PSR-1-basic-coding-standard.md#2-files
#### 3. [Namespace and Class Names]
[Namespace and Class Names]: ./PSR-1-basic-coding-standard.md#3-namespace-and-class-names
#### 4. [Classes, Properties, and Methods]
[Classes, Properties, and Methods]: ./PSR-1-basic-coding-standard.md#4-class-constants-properties-and-methods


### PSR-2 Coding Style Guide
#### 1. [Overview](./PSR-2-coding-style-guide.md#1-overview)
#### 2. [General]
[General]: ./PSR-2-coding-style-guide.md#2-general
#### 3. [Namespace and Use Declarations]
[Namespace and Use Declarations]: ./PSR-2-coding-style-guide.md#3-namespace-and-use-declarations
#### 4. [Classes, Properties, and Methods]
[Classes, Properties, and Methods]: ./PSR-2-coding-style-guide.md#4-classes-properties-and-methods
#### 5. [Control Structures]
[Control Structures]: ./PSR-2-coding-style-guide.md#5-control-structures
#### 6. [Closures]
[Closures]: ./PSR-2-coding-style-guide.md#6-closures
#### 7. [Conclusion]
[Conclusion]: ./PSR-2-coding-style-guide.md#7-conclusion
***
### Addition
#### 1. PHP tag
You must use `<?php` instead of short tag `<?` in file PHP and do not use close tag `?>`

#### 2. Comment
* Class comment
```php
/**
 * Class description.
 */
```
* Method comment
```php
/**
 * Method description.
 * @params type paramName description
 * @return type description
 */
```
* Command comment: use `//` above command

#### 3. Class, method and variable naming rule
* Class's name should be written in CamelCase.
```php
<?php

class ClassName extends ParentClass
{
    // Constants, properties, methods
}
```

* Method, Variable or Function's name should be written in camelBack.

```php
<?php

class ClassName extends ParentClass
{
    public $userProfile = null;
    private $userPassword = null;

    public function getList($arg1, &$arg2, $arg3 = [])
    {
        // Method body
    }
}
```

* Option names and parameter names should be written in snake_case;

* Private property and function name SHOULD NOT be started with `_`.

#### 4. Constants
Constants may contain both alphanumeric characters and underscores.
All letters used in a constant name must be capitalized.
```php
const YEARS_PER_CENTURY = 100;
```

#### 5. String
Use single quote `'` for normal string, double quotes `"` for string which contain php variable.
```php
$str = 'This is a string';
echo "This is a string: $str";
```

#### 6. Array
* Use `[]` to define an array.
* Please add a comma after the last item.
```php
$myArray =  [
    'key1'  => 'val1',
    'key2'  => 'val2',
    'key3'  => 'val3',
];
```
