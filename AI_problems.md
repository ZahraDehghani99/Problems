**`SyntaxError: cannot assign to operator` in Python**

ممکنه در پایتون در اسم متغیر که دو بخشی است از dash استفاده کنید. این باعث می شود این ارور رو دریافت کنید چون پایتون dash را با علامت منها اشتباه می گیره. حتما توجه شود که اگر اسم متغیر بیشتر از یک بخش بود از underline استفاده کنیم.



 **در هنگام استفاده از پایتورچ باید برای استفاده از gpu دیوایس رو مشخص کنیم. برای کراس چطوری؟**
 
 
 در کراس اگر ما gpu رو فعال داشته باشیم به صورت اوتوماتیک و پیش فرض از gpuاستفاده میشه و نیازی به تعریف device نیست.

## Mount google drive in colab

```
from google.colab import drive
drive.mount('/content/drive')
```

## Unmount google drive in colab

```
from google.colab import drive
drive.flush_and_unmount()
```

## login to huggingface hub
```
from huggingface_hub import notebook_login
notebook_login()
```
وقتی این دستور را زدیم باید بریم توی اکانتمون در hugging face در قسمت settings در قسمت access token کپی می‌کنیم توکن را.
این دستوری که در بالا گفته شد برای کار با google colaboratory یا jupyter notebook است. اگر بخواهیم از vscode notebook استفاده کنیم باید در ترمینال دستور زیر را بزنیم و اینطوری لاگین کنیم:

‍‍‍
```
huggingface-cli login
```

## Upload dataset to the hugging face using python
https://huggingface.co/docs/datasets/upload_dataset#upload-with-python
