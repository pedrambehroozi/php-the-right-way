---
title: راهنمای استایل کد
anchor: code_style_guide
---

# راهنمای استایل کد {#code_style_guide_title}

جامعه پچپ‌کاران بزرگ و متنوع است و از بی‌شمار کتابخانه، فریم‌ورک و کامپوننت تشکیل شده است. خیلی رایج است که برنامه‌نویس‌ها از چندتایی از آنها در پروژه‌شان استفاده کنند. برای این که برنامه‌نویس‌ها بتوانند از آنها در کد خودشان استفاده کنند لازم است که کد (تا جایی که ممکن است) از یک استایل که مورد قبول همه است پیروی کند.

[Framework Interop Group][fig] چندتایی پیشنهاد در این باره داده است. البته همه‌شان به استایل کد ربطی ندارد، فقط [PSR-1][psr1] و [PSR-12][psr12] و [PSR-4][psr4] برای این کار هستند که شامل چند تایی قانون برای طریقه‌ی نوشتن کد می‌شوند. پروژه‌های معروفی مثل Drupal، Zend، Symphony، Laravel، CakePHP، phpBB، AWS SDK، FuelPHP، Lithium و غیره از آنها پیروی می‌کنند. می‌توانید شما هم در کدتان از این استانداردها یا استاندارد شخصی خودتان استفاده کنید.

در شرایط ایده‌آل باید کدی بنویسید که از یکی از استانداردهای شناخته‌شده پیروی می‌کند. حالا یا ترکیبی از PSRها یا استانداردهایی که PEAR یا ZEND طراحی کرده‌اند. این‌طوری برنامه‌نویس‌های دیگر می‌توانند به راحتی کدتان را بخوانند و رویش کار کنند و همچنین برنامه‌هایی که از این استانداردها پیروی می‌کنند حتی اگر از هزاران قطعه کد دیگران استفاده کنند باز یکپارچه و ترتمیز هستند.

* [درباره PSR-1 بخوانید][psr1]
* [درباره PSR-12 بخوانید][psr12]
* [درباره PSR-4 بخوانید][psr4]
* [درباره استانداردهای کد PEAR بخوانید][pear-cs]
* [درباره استانداردهای کد Symphony بخوانید][symfony-cs]

می‌توانید از [PHP_CodeSniffer][phpcs] برای چک کردن کدتان استفاده کنید و پلاگین‌هایی نصب کنید روی ویرایشگرها مثل [Sublime Text][st-cs] که در لحظه بهتان فیدبک بدهند.

می‌توانید از ابزارهای زیر استفاده کنید که به صورت خودکار استایل کدتان را درست می‌کنند:

- یکی [PHP Coding Standards Fixer][phpcsfixer] است که کد حسابی تست‌شده‌ی درست و حسابی دارد.
- یکی دیگر [PHP Code Beautifier and Fixer][phpcbf] است که همراه PHP_CodeSniffer عرضه می‌شود و کدتان را تر و تمیز می‌کند.

می‌توانید phpcs را دستی هم اجرا کنید:

{% highlight console %}
> phpcs -sw --standard=PSR1 file.php
{% endhighlight %}

اگر کدتان مشکلی داشته باشد ارور می‌دهد و می‌گوید که چطوری می‌توانید درستش کنید.
حتی می‌توانید این دستور را داخل یک git hook قرار دهید. این‌طوری تا وقتی مشکل برنچ‌ها حل نشده باشد نمی‌توانید آنها را روی ریپازیتوری پوش کنید.

اگر PHP_CodeSniffer دارید می‌توانید مشکلات کد را به صورت خودکار با استفاده از [PHP Code Beautifier and Fixer][phpcbf] برطرف کنید:

{% highlight console %}
> phpcbf -w --standard=PSR1 file.php
{% endhighlight %}

گزینه‌ی دیگر استفاده از [PHP Coding Standards Fixer][phpcsfixer] است.
قبل از این که کد را درست کند بهتان نشان می‌دهد چه مشکلی وجود داشته است.

{% highlight console %}
> php-cs-fixer fix -v --rules=@PSR1 file.php
{% endhighlight %}

برای اسم‌ها و تمام قسمت‌های کد از زبان انگلیسی استفاده کنید. کامنت‌ها می‌توانند به هر زبانی که توسط تمام اعضای فعلی و آینده‌ی پروژه بلدند نوشته شود.

در نهایت منبع تکمیلی دیگری هم برای کد پچپ تمیز وجود دارد. [Clean Code PHP][cleancode]

[fig]: https://www.php-fig.org/
[psr1]: https://www.php-fig.org/psr/psr-1/
[psr12]: https://www.php-fig.org/psr/psr-12/
[psr4]: https://www.php-fig.org/psr/psr-4/
[pear-cs]: https://pear.php.net/manual/en/standards.php
[symfony-cs]: https://symfony.com/doc/current/contributing/code/standards.html
[phpcs]: https://pear.php.net/package/PHP_CodeSniffer/
[phpcbf]: https://github.com/squizlabs/PHP_CodeSniffer/wiki/Fixing-Errors-Automatically
[st-cs]: https://github.com/benmatselby/sublime-phpcs
[phpcsfixer]: https://cs.sensiolabs.org/
[cleancode]: https://github.com/jupeter/clean-code-php
