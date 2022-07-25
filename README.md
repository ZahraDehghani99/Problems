# Problems
  ۱. **اسکایپ در ابونتوی ۲۲ گزینه ی share screen ندارد. چرا؟**
 
 این به دلیل عوض شدن نسخه ی ابونتو هست و باید موقع login کردن، در گوشه پایین سمت راست، گزینه ی ubuntu on Xorg زو بزنیم. یکبار که اینکار رو بکنیم کافیه و نیازی به تغییر مجدد نیست. با اینکار همه چی درست میشه.
  
  
  ۲. **صفحه کلیدم کاراکترهای جابجا رو چاپ میکنه مثلا به جای u عدد ۴ و به جای p کاراکتر * رو چاپ میکنه و برای بعضی دیگه از کلیدهام این جابجایی رو داره. دلیل 
  چیه؟ سیستم عاملم لینوکسه**

این ممکنه به چند تا دلیل باشه. یکی از دلیلاش فعال بودن کلید num lk هست. من در صفحه کلیدم باید fn و num lk رو با هم بزنیم تا این گزینه فعال بشه و برای درست 
شدنش هم باید این دو تا کلید رو با هم بزنم تا درست بشه.

لینک های کمکی

[مربوط به کلید num lk ](https://answers.microsoft.com/en-us/windows/forum/all/strange-keyboard-problem-strange-2eyb6ard-r6b3e0/16ebe691-0182-4f84-9cdc-b5de4a1ac126)


۲. **در هنگام پوش کردن به گیت لب  که فیلتر هست به ارور  `fatal: unable to access 'https://gitlab.com/*****/project-dic.git/': The requested URL returned error: 403` برخوردم.**

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
