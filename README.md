![PHPMailer](https://raw.github.com/PHPMailer/PHPMailer/master/examples/images/phpmailer.png)

## 用PHPMailer替换CodeInigiter的Email类

>本项目用PHPMailer完成CodeInigiter框架下的一个简易的用户注册，找回密码邮件发送功能，目的为了解决阿里云平台上邮件无法发送的问题。

在阿里云平台上怎么都无法用smtp发送邮件，各种google都无法解决，遂尝试了PHPMailer，结果成功了。
可能是CodeInigiter的默认设置的是25端口？(不过我改成465了还是不行)。

## 调用Mailer
在控制器中调用

```php
public function __construct() {
    parent::__construct();
    $this->load->library('Mailer');
}

$this->Mailer->sendMail();
```
---

>要注意的是，在Linux下，Mailer.php文件名首字母必须为大写，而以上代码中$this->Mailer->sendMail()的Mailer可能要为小写才能成功调用。
