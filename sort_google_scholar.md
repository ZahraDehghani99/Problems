وقتی در گوگل اسکولار عنوانی را سرچ می کنیم گزینه ای وجود ندارد که نتایج را بر حسب تعداد سایتیشن مرتب کنیم برای اینکار یک ریپوزیتوری در گیت هاب را کلون می کنیم و با زدن یک کامند در ترمینال می توانیم بازه ی سال مورد نظر را مشخص کنیم همچنین می توانیم نحوه ی مرتب سازی مقالات را مشخص کنیم. در حالت عادی این کد مقالات را برحسب تعداد سایتیشن مرتب می کند اما می توانیم بر حسب تعداد سایتیشن در هر سال نیز مرتب کنیم. مراحل کار به صورت زیر است:

```
git clone https://github.com/WittmannF/sort-google-scholar.git
```
بعد از این دستور به مسیر اصلی فولدر می رویم و در ترمینال در همان مسیر دستور زیر را می زنیم. در داخل دابل کوتیشن باید عبارتی را که می خواهیم جستجو کنیم بنویسیم.


```
python sortgs.py --kw 'your keyword' --startyear 2018 --sortby "cit/year"
```

حال یک فایل سی اس وی به نام عبارتی که جستجو کردیم در مسیر اصلی ایجاد می شود.