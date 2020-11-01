---
isChild: true
anchor:  mac_setup
---

## نصب روی مک {#mac_setup_title}

سیستم عامل مک پچپ را به صورت پیش‌فرض نصب دارد ولی معمولاً نسخه‌ای که ارائه می‌دهد کمی قدیمی است. چندین راه برای نصب آخرین نسخه‌ی پچپ روی مک وجود دارد.

### نصب با Homebrew

[Homebrew] یک مدیر پکیج برای مک است که کمک می‌کند پچپ و افزونه‌های آن را به راحتی نصب کنید.
ریپازیتوری اصلی Homebrew یک سری «فرمول» برای پچپ 5.6، 7.0، 7.1، 7.2، 7.3 و 7.4 دارد. با این دستور آخرین نسخه را نصب کنید:

{% highlight console %}
> brew install php@7.4
{% endhighlight %}

می‌توانید با تغییر متغیر `PATH` بین نسخه‌های پچپ جابجا شوید. همچنین می‌توانید از [brew-php-switcher][brew-php-switcher] استفاده کنید تا به صورت خودکار از نسخه‌های گوناگون پچپ استفاده کنید.

### نصب با MacPorts

پروژه‌ی [MacPorts] یک پروژه‌ی متن‌باز است که سیستم ساده‌ای طراحی کرده برای کامپایل کردن، نصب و ارتقای کامندلاین، X11 یا نرم‌افزارهای متن‌باز مبتنی بر Aqua روی سیستم عامل مک.

MacPorts از باینری‌های از پیش کامپایل شده پشتیبانی می‌کند؛ بنابراین لازم نیست هر دفعه پکیج‌ها را از سورس tarballشان کامپایل کنید.
اگر هیچ پکیجی روی کامپیوترتان نصب نیست MacPorts زندگی‌تان را نجات می‌دهد.

در حال حاضر می‌توانید `php54`، `php55`، `php56`، `php70`، `php71`، `php72`، `php73` یا `php74` را با استفاده از دستور `port install` نصب کنید. برای مثال:

{% highlight console %}
> sudo port install php56
> sudo port install php74
{% endhighlight %}

و می‌توانید با دستور `select` بین این نسخه‌ها جابجا شوید:

{% highlight console %}
> sudo port select --set php php74
{% endhighlight %}

### نصب با phpbrew

[phpbrew] ابزاری است برای نصب و مدیریت چندین نسخه‌ی پچپ. اگر دو یا چند پروژه دارید که به نسخه‌های مختلفی از پچپ نیاز دارند و از ماشین‌های مجازی هم استفاده نمی‌کنید این ابزار می‌تواند خیلی کمک‌تان کند.

### نصب با نصب‌کننده‌ی باینری Liip

یک گزینه‌ی محبوب دیگر [php-osx.liip.ch] است که با یک خط دستور می‌تواند نسخه‌های 5.3 تا 7.3 پچپ را برایتان نصب کند.
اگر قبلا پچپ را نصب کرده‌اید، این ابزار آنها را جایگزین نمی‌کند بلکه در محل جدیدی (`/usr/lib/php5`) قرار می‌گیرد.

### کامپایل کردن کد

گزینه‌ی دیگر که به شما کمک می‌کند نسخه‌ی پچپ مورد نظرتان را نصب کنید، [کامپایل کردن کد][mac-compile] است.
اگر از این روش استفاده می‌کنید حتما [Xcode][xcode-gcc-substitution] یا جایگزین اپلی‌اش ["Command Line Tools for XCode] را نصب کنید.

### نصب همه‌چی

روش‌های بالا بیشتر روی خود پچپ تمرکز دارند و چیزهایی مثل [Apache][apache] یا [Nginx][nginx] یا سرور SQL را نصب نمی‌کنند.
روش‌های نصب همه‌چی مثل [MAMP][mamp-downloads] و [XAMPP][xampp] این نرم‌افزارها را هم برایتان نصب می‌کنند. ولی حواستان باشد که سادگی نصب می‌تواند منعطف بودن‌تان را کم کند.

[Homebrew]: https://brew.sh/
[Homebrew PHP]: https://github.com/Homebrew/homebrew-php#installation
[MacPorts]: https://www.macports.org/install.php
[phpbrew]: https://github.com/phpbrew/phpbrew
[php-osx.liip.ch]: https://php-osx.liip.ch/
[mac-compile]: https://secure.php.net/install.macosx.compile
[xcode-gcc-substitution]: https://github.com/kennethreitz/osx-gcc-installer
["Command Line Tools for XCode"]: https://developer.apple.com/downloads
[apache]: https://httpd.apache.org/
[nginx]: https://www.nginx.com/
[mamp-downloads]: https://www.mamp.info/en/downloads/
[xampp]: https://www.apachefriends.org/index.html
[brew-php-switcher]: https://github.com/philcook/brew-php-switcher
