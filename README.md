# laravel-crud-generator
crud for laravel &amp; lumen  


fork from <https://github.com/funson86/laravel-crud-generator>





## Installation
The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
php composer.phar require  gaoj87/laravel-crud-generator @dev
```

or add

```
"gaoj87/laravel-crud-generator": "@dev"
```

to the require section of your `composer.json` file.

## Basic usage

Usage:  `Command: crud-model {name} {--table=} {--prefix=}`

example:

```Shell
➜  php artisan crud-model  users
```


Then:

```php
<?php

namespace XXX;

use Illuminate\Database\Eloquent\Model;

/**
 * This is the model class for table "users".
 * @property integer $id
 * @property integer $mid
 * @property string $real_name
 * @property string $mobile
 * @property string $created_at
 * @property string $updated_at
 */
class Users extends Model
{
    /**
     * The database table used by the model.
     *
     * @var string
     */
    protected $table = 'users';

    /**
     * The primary key for the model.
     *
     * @var string
     */
    protected $primaryKey = 'id';

    /**
     * The name of the "created at" column.
     *
     * @var string
     */
    const CREATED_AT = 'created_at';

    /**
     * The name of the "updated at" column.
     *
     * @var string
     */
    const UPDATED_AT = 'updated_at';

    /**
     * Attributes that should be mass-assignable.
     *
     * @var array
     */
    protected $fillable = [
        'mid',
        'real_name',
        'mobile',
    ];


    /**
     * Returns the text label for the specified attribute or all attribute labels.
     * @param string $key the attribute name
     * @return array|string the attribute labels
     */
    public static function attributeLabels($key = null)
    {
        $data = [
            'id' => 'Id',
            'mid' => 'Mid',
            'real_name' => 'Real Name',
            'mobile' => 'Mobile',
            'created_at' => 'Created At',
            'updated_at' => 'Updated At',
        ];

        if ($key !== null) {
            return isset($data[$key]) ? $data[$key] : null;
        } else {
            return $data;
        }
    }

}

```



