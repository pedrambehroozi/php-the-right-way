---
title:   Composer و Packagist
isChild: true
anchor:  composer_and_packagist
---

## Composer و Packagist {#composer_and_packagist_title}

کامپوزر ابزار پیشنهادی مدیریت بسته‌ها در پچپ است. تمام وابستگی‌های پروژه‌تان را در فایلی به نام `composer.json` می‌نویسید
و یکی دو تا دستور ساده می‌زنید. کامپوزر به صورت خودکار همه‌ی وابستگی‌ها را دانلود می‌کند و اتولودینگ را برایتان راه می‌اندازد.
کامپوزر شبیه NPM در نود و Bundler در روبی است.

تعداد بیشماری کتابخانه با کامپوزر سازگارند و آماده‌اند تا به پروژه‌تان اضافه شوند. این «پکیج‌ها» در [Packagist] که مخزن
رسمی کتابخانه‌های کامپوزر است، لیست شده‌اند.

### نصب کامپوزر

راحت‌ترین راه برای دانلود کامپوزر [دنبال کردن مستندات در سایت رسمی‌اش است](https://getcomposer.org/download).
با این کار مطمئن می‌شوید که چیزی خراب نیست و دانلود به درستی انجام شده است.
بعد از نصب یک فایل باینری به نام `composer.phar` در _دایرکتوری‌ای که در آن هستید_ ایجاد می‌شود.

پیشنهاد ما این است که کامپوزر را به صورت *عمومی* نصب کنید (یعنی مثلا یک کپی از فایل phar در مسیر `/usr/local/bin` بسازید).
برای این کار دستورات زیر را بزنید:

{% highlight console %}
mv composer.phar /usr/local/bin/composer
{% endhighlight %}

**توجه** اگر دستور بالا خطای دسترسی داد قبلش یک `sudo` بگذارید.

برای اجرای کامپوزر که عمومی نیست، از دستور `php composer.phar` و در حالت عمومی از `composer` استفاده می‌کنید.

#### نصب روی ویندوز

برای کاربران ویندوز آسان‌ترین راه استفاده از [ComposerSetup] است که کامپوزر را به صورت عمومی نصب می‌کند و `$PATH` را ویرایش می‌کند
تا بتوانید با دستور `composer` کار کنید.

### چگونه وابستگی‌ها را تعریف و نصب کنیم

کامپوزر تمام وابستگی‌های پروژه را از یک فایل به نام `composer.json` می‌خواند. می‌توانید آن را دستی ویرایش کنید یا از خود 
کامپوزر استفاده کنید. دستور `composer require` یک وابستگی به پروژه اضافه می‌کند و اگر فایل `composer.json` وجود نداشته باشد
آن را می‌سازد. مثال زیر [Twig] را به عنوان وابستگی به پروژه‌تان اضافه می‌کند.

{% highlight console %}
composer require twig/twig:^2.0
{% endhighlight %}

دستور `composer init` را هم می‌توانید بزنید که مرحله به مرحله یک فایل `composer.json` برای پروژه می‌سازد. به‌هرحال 
وقتی `composer.json` ساخته شد می‌توانید به کامپوزر بگویید وابستگی‌ها را دانلود و نصب کند و در دایرکتوری `vendor/` قرار دهد. 
اگر پروژه‌ای دانلود کرده‌اید که فایل `composer.json` داخلش هست باز هم این دستور کار می‌کند:

{% highlight console %}
composer install
{% endhighlight %}

بعد این خط را در فایل پچپ اصلی پروژه بگذارید؛ این دستور به پچپ می‌گوید که از اتولودر کامپوزر برای بارگذاری وابستگی‌ها
استفاده کند.

{% highlight php %}
<?php
require 'vendor/autoload.php';
{% endhighlight %}

حالا می‌توانید از وابستگی‌ها استفاده کنید و آنها هر لحظه که بخواهید در دسترس‌تان هستند.

### بروزرسانی وابستگی‌ها

کامپوزر یک فایل به نام `composer.lock` می‌سازد که در آن مشخص می‌کند چه نسخه‌ای از هر پکیج با دستور `composer install` نصب شده است. 
اگر پروژه‌تان را با دیگران به اشتراک می‌گذارید حتما فایل `composer.lock` را هم برایشان بفرستید تا وقتی `composer install` را
اجرا می‌کنند همان نسخه‌ها برایشان نصب شود. برای بروز کردن وابستگی‌ها دستور `composer update` را اجرا کنید. وقتی روی پروداکشن
هستید از این دستور استفاده نکنید، فقط `composer install` را بزنید. وگرنه ممکن است نسخه‌هایی متفاوت با نسخه‌ی لوکال روی پروژه
نصب شود.

اگر نسخه‌ی وابستگی‌ها را در فایل `composer.json` منعطف تعریف کرده باشید دستور آپدیت بسیار کاربردی می‌شود. مثلا `~1.8` یعنی 
«هر چیزی جدیدتر از `1.8.0` و قدیمی‌تر از `2.0.x-dev`». می‌توانید از `*` هم استفاده کنید: `1.8.*`
حالا دستور `composer update` تمام وابستگی‌ها را به جدیدترین نسخه‌ای که تعریف کرده‌اید بروز می‌کند.

### نوتیفیکیشن برای آپدیت‌ها

برای دریافت نوتیفیکیشن در صورت وجود یک نسخه‌ی جدید در [libraries.io] یک اکانت بسازید. این سایت یک سرویس است که
وابستگی‌ها را مانیتور می‌کند و اگر آپدیتی داشتند خبرتان می‌کند.

### ایرادهای امنیتی وابستگی‌ها

یک سرویس تحت وب به نام [Security Advisories Checker] وجود دارد که به صورت کامندلاین هم قابل استفاده است. این سرویس
فایل `composer.lock` را بررسی می‌کنند و اگر وابستگی‌ها مشکل امنیتی داشتند بهتان اطلاع می‌دهند.

### مدیریت وابستگی‌های عمومی

کامپوزر می‌تواند وابستگی‌هایی تعریف کند که عمومی هستند. خیلی ساده می‌توانید از دستور `composer global require xxx` استفاده کنید.
برای مثال فرض کنید می‌خواهید PHPUnit را نصب کنید و از آن به صورت عمومی در تمام پروژه‌ها استفاده کنید. این دستور را باید بزنید:

{% highlight console %}
composer global require phpunit/phpunit
{% endhighlight %}

این دستور یک دایرکتوری در مسیر `~/.composer` می‌سازد و وابستگی عمومی را در آن ذخیره می‌کند. برای این که باینری این وابستگی همه‌جا
در دسترس باشد باید مسیر `~/.composer/vendor/bin` را در `$PATH` اضافه کنید.

* [راجع به کامپوزر بخوانید][Learn about Composer]

[Packagist]: https://packagist.org/
[Twig]: https://twig.symfony.com/
[libraries.io]: https://libraries.io/
[Security Advisories Checker]: https://security.symfony.com/
[Learn about Composer]: https://getcomposer.org/doc/00-intro.md
[ComposerSetup]: https://getcomposer.org/Composer-Setup.exe
