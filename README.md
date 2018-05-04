# Yii2 Telegram API #


Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
php composer.phar require mirkhamidov/yii2-bot-telegram "*"
```

or add

```
"mirkhamidov/yii2-bot-telegram": "*"
```

to the require section of your `composer.json` file.

Usage
-----
first add to config.php
```php
<?php
'components' => [
	'telegram' => [
        'class' => 'mirkhamidov\telegramBot\TelegramBot',
        'botToken' => 'TOKEN HERE',
    ]
]
?>
```
Once the extension is installed, simply use it in your code by  :
```php
<?php Yii::$app->telegram->sendMessage('Message'); ?>
```
send message width inline keyboard by:
```php
<?php Yii::$app->telegram->sendMessage('Message with inline keyboard', $chatId, [
        'reply_markup' => json_encode([
            'inline_keyboard'=>[
                [
                    ['text'=>"refresh",'callback_data'=> time()]
                ]
            ]
        ]),
    ] ?>
```

send photo by :
```php
<?php Yii::$app->telegram->sendPhoto('/app/pattern2.jpg', $chatId, [
    'caption' => 'some text',
]); ?>
```




## TODO

* Logging




PS: Inspired by aki/yii2-bot-telegram