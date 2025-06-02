# Problems
  ۱. **اسکایپ در ابونتوی ۲۲ گزینه ی share screen ندارد. چرا؟**
 
 این به دلیل عوض شدن نسخه ی ابونتو هست و باید موقع login کردن، در گوشه پایین سمت راست، گزینه ی ubuntu on Xorg زو بزنیم. یکبار که اینکار رو بکنیم کافیه و نیازی به تغییر مجدد نیست. با اینکار همه چی درست میشه.
  
  
  ۲. **صفحه کلیدم کاراکترهای جابجا رو چاپ میکنه مثلا به جای u عدد ۴ و به جای p کاراکتر * رو چاپ میکنه و برای بعضی دیگه از کلیدهام این جابجایی رو داره. دلیل 
  چیه؟ سیستم عاملم لینوکسه**

این ممکنه به چند تا دلیل باشه. یکی از دلیلاش فعال بودن کلید num lk هست. من در صفحه کلیدم باید fn و num lk رو با هم بزنیم تا این گزینه فعال بشه و برای درست 
شدنش هم باید این دو تا کلید رو با هم بزنم تا درست بشه.

لینک های کمکی

[مربوط به کلید num lk ](https://answers.microsoft.com/en-us/windows/forum/all/strange-keyboard-problem-strange-2eyb6ard-r6b3e0/16ebe691-0182-4f84-9cdc-b5de4a1ac126)


۳. **در هنگام پوش کردن به گیت لب  که فیلتر هست به ارور  `fatal: unable to access 'https://gitlab.com/*****/project-dic.git/': The requested URL returned error: 403` برخوردم.**

برای حلش طبق راهنمایی [این](https://roocket.ir/discuss/%D8%A7%D8%B1%D9%88%D8%B1-%D9%87%D9%86%DA%AF%D8%A7%D9%85-push-%DA%A9%D8%B1%D8%AF%D9%86-%D8%A8%D9%87-%DA%AF%DB%8C%D8%AA-%D9%84%D8%A8#subject-52405) سایت پیش رفتم:

دستورهای زیر رو وارد کردم:

‍‍‍‍```
git config --global http.proxy fodev.org:8118
و git config --global https.proxy fodev.org:8118```

درست شد . اما برای گیت لب خود شرکت که فیلتر نبود اومدم دستور پوش رو زدم و به ارور زیر خوردم:


‍‍git push fatal: unable to access 'https://gitlab.abriment.com/chatbot_apis/chatbot.git/': Received HTTP code 403 from proxy after CONNECT


برای حلش باید تغییراتی که برای پروکسی انجام داده بودم رو برمیگردوندم

با دستور زیر همه ی چیزهایی که توی git config بود رو می تونستم ببینم:

```
git config --global --list
```

حالا باید پراکسی رو حذف کننم پس از دستور زیر استفاده می کنم:

```
git config --global --edit
```
خط های اضافه رو پاک می کنم  و بعدش با کنترل اس ذخیره می کنم و با کنترل ایکس میام بیرون.



۴ . **د
ر مک وقتی ضرب در بالای صفحه در فایرفاکس رو میزنیم، دوباره که فایرفاکس رو باز می کنیم تمام تب هامون رفته و با تنظیم کردن فایرفاکس هم این درست نمیشه**

وقتی در مک از فایرفاکس استفاده می کنیم و میخوایم اون رو با استفاده از ضرب در قرمز فایرفاکس ببندیم بسته نیمشه انگار و وقتی بازش می کنیم تمام تب ها پریدن. هر چی هم تنظیمات رو توی فایرفاکس چک کردم که تب ها را نبنده و تاریخچه را نگه داره درست نشد. دلیل این هست که با ضرب در بالای فایرفاکس در مک این برنامه بسته نمیشه. باید در کنار گزینه ی اپل، روی فایرفاکس بزنیم و کوییت را انتخاب کنیم. 


  ۵. **مایکروسافت پاورپوینت در مک یه سری از گزینه‌هایی که در ویندوز داره رو نداره. برای مثال در بهش home بخشی به نام editing برای هماهنگ کردن همه فونت‌ها نداره. چیگار کنیم؟**

  
  برای اینکه در تمام اسلایدها ما از یک فونت خاص استفاده کنیم باید در قسمت home بخش editing را بزنیم و گزینه replace font را بزنیم. ولی در مک همچین گزینه‌ای نمیبینیم. برای دسترسی به این امکان باید در نوار ابزای بالای مارک اپل در پاورپوینت گزینه 

  Edit => Find => Replace fonts

  را بزنیم و فونت پیش فرض اسلاید را با فونتی که دوست داریم عوض کنیم.اینطوری دیگه نیاز به تنظیم دستی توی هر اسلاید نیست.


۵ . **د
ر مک بعضی وقتا فایرفاکس دچار مشکل میشه. برای مثال وقتی اکانت جیمیلم رو باز میکنم و میخوام اسکجول کنم برای یه تایم دیگه ای این دکمه کلیک میشه ولی هیچ اتفاقی نمی افته یا چیزهای دیگر گه وقتی در کروم امتحان میکنم مشکلی نداره.**

برای این کار من اومدم این مشکل رو سرچ کردم. متوجه شدم که مشکل ممکنه از یه سری از اکستنشن ها باشه. برای این کار طبق سایت زیر پیش رفتم:
https://support.mozilla.org/en-US/kb/use-troubleshooting-information-page-fix-firefox

اول tune up کردم ولی مشکل حل نشد. دقت شه وقتی این کار رو میکنیم تمام تب ها بسته میشه و فونت فایرفاگس به تنظیمات پیش فرضش در میاد که در مک کوچیک میشه در واقع. دیدم با این کار مشکل هنوز حل نشده. پس اومدم روش دوم یعنی trouble shoot mode رو امتحان کردم. در این حالت فایرفاکس میاد یه دور ری استارت میشه و در safe mode قرار میگیره یعنی extention ها رو موقتا disabled میکنه تا ببینه مشکل از چیه. با این کار مشکل من کامل حل شد ولی هیچ کدم از extention ها فعال نبود و کارشون داشتم. چندبار extention ها رو install و uninstall کردم به روش آزمون و خطا تا متوجه شدم یه سری از اکستنشن ها مشکل دارن. اومدم همه ی disabled شده ها را uninstall کردم و اونایی که اوکی بودن رو دوباره نصب کردم. فعلا اوکی شده.



۶ . **چطوری در فایرفاکس فونت تولبار رو افزایش بدیم؟**

بر اساس این سایت عمل کنیم:
https://support.mozilla.org/gl/questions/1349800
۷. **چطوری anydesk  رو در ubuntu نصب کنیم؟**

برای نصب anydesk باید طبق دستورات زیر پیش بریم. اول طبق روش دوم در این سایت پیش میریم : https://www.geeksforgeeks.org/how-to-install-anydesk-on-ubuntu/
بعدش طبق زیر پیش میریم:
‍‍‍
```
ls /usr/share/applications/anydesk.desktop # Check for the AnyDesk .desktop file
sudo update-desktop-database
gedit ~/.local/share/applications/anydesk.desktop

```
After that paste the following value in the popup editor:

```
[Desktop Entry]
Name=AnyDesk
Comment=Remote Desktop Application
Exec=anydesk
Icon=anydesk
Terminal=false
Type=Application
Categories=Network;RemoteAccess;
```

Save the file and make it executable by:
```
chmod +x ~/.local/share/applications/anydesk.desktop
```
Then you can see the anydesk icon in your application list. The next step is to log out your system. In the log in page, you should select `ubuntu on xrog` , otherwise you will get error when you are trying to connet to your ubuntu system using other systems. That's it. Enjoy learning!
‍‍‍
