# SMS4Jawaly for Lumen

مكتبة لإرسال الرسائل النصية القصيرة عبر خدمة SMS4Jawaly في إطار عمل Lumen.

## المتطلبات

- PHP: ^7.0|^8.0
- guzzlehttp/guzzle: ^6.0|^7.0
- illuminate/support: ^7.0|^8.0|^9.0|^10.0

## التثبيت

يمكنك تثبيت المكتبة باستخدام Composer:

```bash
composer require sms4jawaly/lumen
```

## الإعداد

1. قم بإضافة مزود الخدمة في ملف `bootstrap/app.php`:

```php
$app->register(Sms4jawaly\Lumen\Sms4jawalyServiceProvider::class);
```

2. قم بإضافة المتغيرات البيئية التالية في ملف `.env`:

```env
SMS4JAWALY_USERNAME=your_username
SMS4JAWALY_PASSWORD=your_password
```

## الاستخدام

```php
use Sms4jawaly\Lumen\Gateway;

// إنشاء كائن جديد
$sms = new Gateway();

// إرسال رسالة
$response = $sms->sendSMS([
    'messages' => [
        [
            'text' => 'مرحباً بك!',
            'numbers' => ['966500000000'],
            'sender' => '4jawaly'
        ]
    ]
]);

// الحصول على الرصيد
$balance = $sms->getBalance();

// الحصول على أسماء المرسلين
$senders = $sms->getSenderNames();
```

## المساهمة

نرحب بمساهماتكم! يرجى إرسال pull request إذا كان لديكم أي تحسينات أو إصلاحات.

## الترخيص

هذه المكتبة مرخصة تحت [MIT License](LICENSE).
