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
 
 [Putty Download Link `putty`][putty] 

 [Putty Download Link `soft98`][softputty]
 
 [XSHELL Download Link `soft98`][softxshell]
 
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
 یک پسورد دلخواه دلخواه به عنوان مثال (@MyPa5s54s3HwXoZs)
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
 یک پورت دلخواه دلخواه به عنوان مثال(10391)
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
 
 > نکته یک: قبل از ساختن یوزر حتما ورژن رو از قسمتی که با فلش آبی مشخص شده به `1.6.0` تغییر دهید
 >  نکته دو: از منو شماره ۳ میتونید تنظیمات مربوط به `رمز` و `پورت` ادمین رو تغییر بدهید
 
 ![Screenshot4](images/CShot%2020221018_015855.png)
 <br>
 
 > **برای `ساخت یوزر` وارد منو شماره دو بشوید**
 > **از طریق دکمه‌ای که با فلش قرمز مشخص شده اقدام به اضافه کردن یوزر میکنیم**
 
 <br>

 ![Screenshot5](images/CShot%2020221018_122337.png)
 <br>
 
 > **در این قسمت طبق جدول زیر اطلاعات خواسته شده رو پر کنید**
 
 <br>

 ![Screenshot6](images/CShot%2020221018_124748.png)
 
 |   x   |    توضیح     |                         اطلاعات ورودی                          |
 | :---: | :----------: | :------------------------------------------------------------: |
 |   1   |   یوزرنیم    |                      یوزرنیم مورد نظرتون                       |
 |   2   |    پروتکل    |                             vmess                              |
 |   3   |  پورت یوزر   |    میتونید پورت دلخواه وارد کنید یا از پیشفرض استفاده کنید     |
 |   4   | محدودیت حجم  | میتونید محدودیت دلخواه تنظیم کنید، مقدار صفر یعنی بدون محدودیت |
 |   5   | تاریخ انقضا  |  میتونید تاریخ دلخواه تنظیم کنید، بدون مقدار یعنی انقضا ندارد  |
 |   6   |     UUID     |                   به مقدار پیشفرض دست نزنید                    |
 |   7   | Transmission |                               ws                               |
 |   8   |   Sniffing   |                              OFF                               |
 
 **الان شما اولین یوزر خودتون رو ساختین**



 ## مرحله هشت: استفاده از کانفیگ‌ها

 لیستی از نرم افزارهای کلاینت برای سیستم عامل‌های مختلف

 اپ های زیر رو دانلود کنید و نصب داشته باشید
 [ روی لینک کلیک کنید، ممکنه فیلتر باشن ]

 ### **[ iOS ]**
 [ 1: NapsterNetV iOS ][NapsterNetV]

 [ 2: ShadowLink iOS ][ShadowLink]

 [ 3: Fair VPN iOS ][Fair VPN]

 [ 4: Shadowrocket iOS ][Shadowrocket]

 ### **[ Android ]**
 [ 1: V2RayNG Android ][v2rayNG]

 [ 2: XRAY VPN Android ][XRAY]

 [ 3: Matsuri Android ][Matsuri]

 [ 4: AnXray Android ][AnXray]

### **[ MacOS ]**
 [ 1: qv2ray MacOS ][qv2ray Mac]

 [ 2: V2RayX MacOS ][V2RayX]

 ### **[ Windows ]**
 [ 1: v2rayN Windows ][v2rayN]

 [ 2: nekoray Windows ][nekoray]

 [ 3: qv2ray Windows ][qv2ray Windows]


[putty]: https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html
[softputty]: https://dl2.soft98.ir/soft/p-q/PuTTY.0.77.rar?1
[softxshell]: https://dl2.soft98.ir/soft/x-y-z/Xshell.5.0.0835.rar?1
[NapsterNetV]: https://apps.apple.com/us/app/napsternetv/id1629465476
[ShadowLink]: https://apps.apple.com/us/app/shadowlink-shadowsocks-vpn/id1439686518
[Fair VPN]: https://apps.apple.com/us/app/fair-vpn/id1533873488
[Shadowrocket]: https://apps.apple.com/us/app/shadowrocket/id932747118
[v2rayNG]: https://play.google.com/store/apps/details?id=com.v2ray.ang
[XRAY]: https://play.google.com/store/apps/details?id=vpn.v2ray.xray
[Matsuri]: https://play.google.com/store/apps/details?id=moe.matsuri.lite
[AnXray]: https://f-droid.org/repo/io.nekohasekai.anXray_175.apk
[qv2ray Mac]: https://qv2ray.net/getting-started/step2.html#download-v2ray-core-files
[V2RayX]: https://github.com/Cenmrev/V2RayX/releases/download/v1.5.1/V2RayX.app.zip
[v2rayN]: https://github.com/2dust/v2rayN/releases
[nekoray]: https://github.com/MatsuriDayo/nekoray/releases
[qv2ray Windows]: https://github.com/v2fly/v2ray-core/releases