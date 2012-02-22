Introduction
------------
Yii-Phpass is a simple wrapper for [Phpass 0.3](http://www.openwall.com/phpass/)
in the [Yii Framework](http://www.yiiframework.com/)

###Requirements

* Yii 1.0 or above
* PHP 5.3 or PHP with Suhosin Patch *strongly* recommended

###Installation

* Extract the release file under `protected/extensions/phpass`
* Add a line to your configurationf ile to import the extension:
~~~
[php]
'import'=>array(
    ...
    'application.extensions.phpass.*',
),
~~~
* Add to your main.php file within your Yii project, inside the component array:
~~~
[php]
'components'=>array(
    'hasher'=>array (
        'class'=>'Phpass',
        'hashPortable'=>true,
        'hashCostLog2'=>8,
    ),
),
~~~

###Usage

Access the Phpass object:
~~~
[php]
Yii::app()->hasher
~~~

For a New Password:
~~~
[php]
$theirHashToStore = Yii::app()->hasher->hashPassword($theirPassword);
~~~

Authenticate an Existing Password:
~~~
[php]
$isValid = Yii::app()->hasher->checkPassword($theirPassword, $theirStoredHash);
~~~

License
---------
Modified BSD License
[https://github.com/gtcode/Yii-Phpass](https://github.com/gtcode/Yii-Phpass)