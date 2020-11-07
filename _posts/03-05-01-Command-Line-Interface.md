---
title: اینترفیس کامندلاین
isChild: true
anchor:  command_line_interface
---

## اینترفیس کامندلاین {#command_line_interface_title}

پچپ طراحی شده است تا با آن اپلیکیشن وب بنویسید، اما برای برنامه‌های کامندلاینی (CLI) هم به درد می‌خورد.
برنامه‌های کامندلاینی پچپ می‌توانند کارهای روتین مثل تست کردن، دیپلوی کردن و مدیریت اپلیکیشن را انجام دهند.

برنامه‌های کامندلاینی پچپ قدرمند هستند چون می‌توانید از همان کدی که در اپلیکیشن استفاده کرده‌اید کمک بگیرید و نگران ساختن
و امن کردن GUI برایش نباشید. فقط کد اپلیکیشن کامندلاینی پچپ‌تان را در شاخه‌ی عمومی و اصلی اپلیکیشن وب **نگذارید**!

پچپ را در کامندلاین اجرا کنید:

{% highlight console %}
> php -i
{% endhighlight %}

گزینه `-i` تنظیمات پچپ را مثل وقتی که از متد [`phpinfo()`][phpinfo] استفاده می‌کنید نشان می‌دهد.

گزینه `-a` یک محیط تعاملی برایتان باز می‌کند، مثل IRB در روبی یا محیط تعاملی پایتون. کلی گزینه‌ی به‌دردبخور دیگر هم
در [گزینه‌های کامندلاینی پچپ][cli-options] وجود دارد.

بیایید یک برنامه کامندلاینی ساده به صورت "Hello, $name" بنویسیم. فایلی با نام `hello.php` بسازید و این کد را داخلش
بگذارید:

{% highlight php %}
<?php

if ($argc !== 2) {
    echo "Usage: php hello.php <name>.\n";
    exit(1);
}

$name = $argv[1];
echo "Hello, $name\n";
{% endhighlight %}

پچپ با توجه به آرگومان‌هایی که اپلیکیشن‌تان با آنها کار می‌کند دو تا متغیر می‌سازد. [`$argc`][argc] یک متغیر عددی است
که *تعداد* آرگومان‌ها در آن ذخیره می‌شود. [`$argv`][argv] یک آرایه است شامل *مقادیر* هر آرگومان. اولین آرگومان همیشه
اسم فایل پچپ است. در این مورد `hello.php`.

`exit()` با یک ورودی عددی بزرگتر از صفر صدا زده می‌شود که به شِل بگوید دستور خطا داشته است. کدهای خروج رایج را می‌توانید از [اینجا][exit-codes] ببینید.

برای اجرا کردن اسکریپت دستور زیر را اجرا کنید:

{% highlight console %}
> php hello.php
Usage: php hello.php <name>
> php hello.php world
Hello, world
{% endhighlight %}


 * [درباره اجرای پچپ در کامندلاین بیشتر بخوانید][php-cli]

[phpinfo]: https://secure.php.net/function.phpinfo
[cli-options]: https://secure.php.net/features.commandline.options
[argc]: https://secure.php.net/reserved.variables.argc
[argv]: https://secure.php.net/reserved.variables.argv
[exit-codes]: https://www.gsp.com/cgi-bin/man.cgi?section=3&amp;topic=sysexits
[php-cli]: https://secure.php.net/features.commandline.options
