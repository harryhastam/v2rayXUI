 # v2rayXUI
 Setup v2ray VPN Server on Linux and Config Clients.

 # راه اندازی VPN v2ray در سرور لینوکس :ninja:
 
 ## مرحله یک: آماده سازی
 
 برای اینکار در ابتدا نیاز به سرور `لینوکس` داریم، که میتونید از سایت‌های مختلفی اون رو تهیه کنید
 (بعضی سایت‌ها پرداخت به صورت ساعتی دارن)
 
 ### نکات مربوط به تهیه سرور:
 
 
 1. از ابر!آرو*ان نگیرید
 2. اکثر مواقع یه سرور به کمترین میزان رم و سی پی یو کافیه
 3. ترجیحا از کشورهایی مثل هلند، آلمان، فرانسه، ترکیه سرور تهیه بکنید بهتره(در صورتی که پیدا نکردین خیلی فرقی نمیکنه کجا)
 4. سروری که تهیه میکنید باید از داخل ایران پینگ داشته باشه
 5. میتونید از سیستم عامل‌های `Ubuntu` ,`CentOS` یا هرچیزی استفاده کنید ولی پیشنهاد میشه از `Ubuntu ورژن 18 یا 20` استفاده کنید
 6. داشتن دسترسی `root` در سرور الزامی است
 
 
 ----------



 ## مرحله دو: اتصال به سرور
 
 #### در ویندوز
 **راه اول**
 اگر از ویندوز ۱۰ یا ۱۱ استفاده میکنید احتمال خیلی زیاد با استفاده از کامند پرامپت میتونید دستور زیر رو وارد و به سرور وصل بشید
 
 ```bash
 ssh [Server Username]@[Server IP]
 ```
 نمونه:
 ```bash
 ssh root@123.34.387.13
 ```
 
 **راه دوم**
 دانلود و استفاده از یکی از نرم افزارهای زیر
 (پیشنهاد میکنم از Putty استفاده کنید)

 [Putty Download Link `soft98`](https://dl2.soft98.ir/soft/p-q/PuTTY.0.77.rar?1)
 
 [XSHELL Download Link `soft98`](https://dl2.soft98.ir/soft/x-y-z/Xshell.5.0.0835.rar?1)
 
 #### در مک و لینوکس
 در مک و لینوکس کافیه با استفاده از نرم افزار ترمینال با کامند زیر وارد سرور بشوید
 
 ```bash
 ssh [Server Username]@[Server IP]
 ```
 نمونه:
 ```bash
 ssh root@123.34.387.13
 ```
 
 > نکته: در اولین اتصال ازتون یه سوال میپرسه، کافیه بنویسید `yes` و اینتر رو بزنید
 
 ## مرحله سه: آپدیت سرور
 
 بعد از وصل شدن به سرور اولین کاری که باید بکنید آپدیت سرور است
 
 > **نکته:** درصورتی که یوزر روت `#` نیستید اول دستور زیر را وارد کنید
 ```bash
 sudo su -
 ```
 
 دستور اول
 ```bash
 apt update
 ```
 
 دستور دوم
 ```bash
 apt upgrade -y
 ```
 
 اگه جایی سوال پرسید فقط دکمه اینتر رو بزنید
 
 ## مرحله چهار: نصب پیش نیازها
 ```bash
 apt install curl socat -y
 ```
 
 ## مرحله پنج: نصب اسکریپت اصلی
 
 دستور زیر را وارد کنید
 ```bash
 bash <(curl -Ls https://raw.githubusercontent.com/vaxilu/x-ui/master/install.sh)
 ```
 
 بعد از اجرای دستور زیر و گذشت کمی زمان چندتا سوال ازتون میپرسه که به زبان چینی نوشته شده
 
 سوال اول

 ```
 确认是否继续?
 (میگه مطمئنی که میخوای ادامه بدی؟)
 ```
 جواب:

 ```bash
 y
 ```
 
 سوال دوم

 ```
 请设置您的账户名:
 (یوزرنیم اکانت ادمین)
 ```
 فراموش نکنید و ترجیحا یادداشت کنید
 
 جواب:

 ```
 یک یوزرنیم دلخواه به عنوان مثال(Hero398)
 ```
 سوال سوم

 ```
 请设置您的账户密码:
 (پسورد اکانت ادمین)
 ```
 فراموش نکنید و ترجیحا یادداشت کنید
 
 جواب:

 ```
 یک پسورد دلخواه دلخواه به عنوان مثال(@MyPa5s54s3HwXoZs)
 ```
 سوال چهارم

 ```
 请设置面板访问端口:
 (پورت اتصال به پنل ادمین)
 ```
 فراموش نکنید و ترجیحا یادداشت کنید
 > نکته: پورت میتونه عددی بین 1 تا 65535 باشه
 
 جواب:

 ```
 یک پسورد دلخواه دلخواه به عنوان مثال(10391)
 ```
 بعد از جواب دادن به سوالات بالا پیام تاییدی شبیه به این متن میبینید
 
 set username and password success
 set port xxxx success


 ![Screenshot1](images/Screen%20Shot%202022-10-18%20at%2001.19.08.png)

 ## مرحله شش: ورود به پنل ادمین

 در این مرحله مرورگر خودتون رو باز میکنید و `آیپی سرور` + `پورتی` که در مرحله قبل انتخاب کردید رو وارد میکنید


 ![Screenshot2](images/Screen%20Shot%202022-10-18%20at%2001.03.06.png)
 
 <blockquote>
 نکته: زبان محیط پنل ادمین هم چینیه و برای استفاده از ترجمه خودکار حتما از مرورگر `کروم` استفاده کنید
 (کافیه کلیک راست کنید و گزینه Translate to English رو بزنید)
 </blockquote>

 ```bash
 [IP Server]:[Port]
 ```
 مثال

 ```bash
 123.34.387.13:10391
 ```
 بعد از وارد شدن به پنل ادمین `یوزرنیم` و `پسوردی` که در مرحله پنج ثبت کردید رو وارد کنید


 ![Screenshot3](images/Screen%20Shot%202022-10-18%20at%2001.44.21.png)


 ## مرحله هفت: ساخت یوزر
 
 > نکته یک: قبل از ساختن یوزر حتما ورژن رو از قسمتی که با فلش آبی مشخص شده به فلان تغییر دهید
 >  نکته دو: از منو شماره ۳ میتونید تنظیمات مربوط به `رمز` و `پورت` ادمین رو تغییر بدهید
 
 ![Screenshot4](images/CShot%2020221018_015855.png)
 
 
 مرحله هشت: استفاده از کانفیگ‌ها

 https://qrcode-decoder.com/