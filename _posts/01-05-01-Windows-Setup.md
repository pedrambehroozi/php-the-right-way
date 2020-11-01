---
isChild: true
anchor:  windows_setup
---

## نصب روی ویندوز {#windows_setup_title}

می‌توانید باینری‌های پچپ را از [windows.php.net/download][php-downloads] بگیرید. بعد از این که آنها را اکسترکت کردید بهتر است [PATH][windows-path] را 
روی دایرکتوری پچپ تنظیم کنید (همان جایی که php.exe وجود دارد) تا بتوانید پچپ را از هر کجای سیستم اجرا کنید.

برای یاد گرفتن و کد زدن روی لوکال، می‌توانید از وب سرور داخلی پچپ 5.4 به بعد استفاده کنید و نگران تنظیم کردن وب سرور نباشید. اگر همه‌چی از جمله یک وب سرور کامل و MySql می‌خواهید ابزارهایی مثل [Web Platform Installer][wpi] و [XAMPP][xampp] و [EasyPHP][easyphp] و [OpenServer][openserver] و [WAMP][wamp] محیط ویندوز را خیلی سریع برای کد زدن آماده می‌کنند. اما بدانید که ابزارها روی محیط پروداکشن کمی متفاوت هستند. پس اگر روی ویندوز کد می‌زنید و روی لینوکس اجرا می‌کنید حواستان را جمع کنید.

اگر محیط پروداکشن‌تان هم روی ویندوز است، IIS7 انتخاب خوبی است. برای تنظیم و مدیریت آسان پچپ می‌توانید از [phpmanager][phpmanager] (یک پلاگین GUI برای IIS7) استفاده کنید. IIS7 درون خود FastCGI را دارد. فقط کافی است پچپ را به عنوان یک handler تنظیم کنید. اگر اطلاعات بیشتر می‌خواهید یک [صفحه اختصاصی برای پچپ در سایت iis.net][php-iis] وجود دارد.

کلاً اگر محیط کد زدن و پروداکشن‌تان فرق داشته باشد ممکن است به باگ‌های عجیب و غریب بخورید. اگر روی ویندوز کد می‌زنید و روی لینوکس (یا هر چیزی جز ویندوز) دیپلوی می‌کنید به خودتان لطف کنید و از یک [ماشین مجازی](#virtualization_title) استفاده کنید.

کریس تانکرسلی یک پست وبلاگ خیلی خوب دارد راجع به این که چطوری [روی ویندوز کد پچپ بزنید][windows-tools].

[easyphp]: http://www.easyphp.org/
[phpmanager]: http://phpmanager.codeplex.com/
[openserver]: http://open-server.ru/
[wamp]: http://www.wampserver.com/en/
[php-downloads]: http://windows.php.net/download/
[php-iis]: http://php.iis.net/
[windows-path]: http://www.windows-commandline.com/set-path-command-line/
[windows-tools]: http://ctankersley.com/2016/11/13/developing-on-windows-2016/
[wpi]: https://www.microsoft.com/web/downloads/platform.aspx
[xampp]: http://www.apachefriends.org/en/xampp.html
