# php Import SQL
PDO import sql from a .sql file

### Install

Using composer include the repository by typing the following into a terminal

```
composer require daveismyname/sql-import
```

### Usage

Include the composer autoloader, import the Import namespace.

Define your database file path and credentials, the option `dropTables`, when set to _true_, will __delete all__ the tables in the database before the sql file gets imported.

The option `forceDropTables` is optional and __not recommended__. When enabled together with `dropTables`, the deletion of tables will be executed with disabled foreign key checks. Only use this method if you are sure that the integrity of the existing data in the database does not matter.

```php
<?php
require('vendor/autoload.php');

use Daveismyname\SqlImport\Import;

$filename = 'database.sql';
$username = 'root';
$password = '';
$database = 'sampleproject';
$host = 'localhost';
$dropTables = true;
$forceDropTables = false;
new Import($filename, $username, $password, $database, $host, $dropTables, $forceDropTables);
```
