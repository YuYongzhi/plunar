Plunar
======
一个PHP版中国阴历转换工具，用于将阳历日期转换为中国阴历日期。

安装
----
使用 Composer 安装：

```
composer require guojikai/plunar
```
在入口文件引入 Composer 启动脚本： (eg. index.php)

```php
require 'vendor/autoload.php';
```

使用
----
```php
<?php

use Plunar\Plunar;
use Plunar\PlunarException;

try {
	$lunar_array = Plunar::solarToLunar(1984, 9, 22);
} catch (PlunarException $e) {
	echo $e->getMessage();
	exit;
}

var_dump($lunar_array);

?>
```

输出：

```php
array:7 [
  0 => "一九八四" //阴历年
  1 => "八月" //阴历月
  2 => "廿七" //阴历日
  3 => "甲子" //天干地支
  4 => "鼠" //生肖
  5 => "闰十月" //闰月
  6 => array:3 [ //阴历日期对应数字
    0 => 1984
    1 => 8
    2 => 27
  ]
]
```
