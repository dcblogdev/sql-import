# php Import SQL

[![Latest Version on Packagist](https://img.shields.io/packagist/v/dcblogdev/sql-import.svg?style=flat-square)](https://packagist.org/packages/dcblogdev/sql-import)
[![Total Downloads](https://img.shields.io/packagist/dt/dcblogdev/sql-import.svg?style=flat-square)](https://packagist.org/packages/dcblogdev/sql-import)

![Logo](https://repository-images.githubusercontent.com/142712626/d110ff80-49c1-11eb-8153-e43e3960caca)

PDO import sql from a .sql file

## Install
Using composer include the repository by typing the following into a terminal

```
composer require dcblogdev/sql-import
```

## Usage

Include the composer autoloader, import the Import namespace.

Define your database file path and credentials, the option dropTables, when set to true, will delete all the tables in the database before the sql file gets imported.

The option forceDropTables is optional and not recommended. When enabled together with dropTables, the deletion of tables will be executed with disabled foreign key checks. Only use this method if you are sure that the integrity of the existing data in the database does not matter.

```php
use Dcblogdev\SqlImport\Import;

$filename = 'database.sql';
$username = 'root';
$password = '';
$database = 'sampleproject';
$host = 'dev';
$dropTables = true;
$forceDropTables = false;

new Import($filename, $username, $password, $database, $host, $dropTables, $forceDropTables);
```
