# نحوه نصب و کار با لاتک

برای کار با لاتک دو گزینه داریم : ۱) اجرای اون با استفاده از محیط آنلاینOverleafکه نیازی به نصب هیچ چیزی روی سیستم نداره. تنها مشکلی که این روش داره این هست که این سایت در حال حاضر در ایران فیلتر هست و اینکه مدت کامپایل شدن اون ممکنه خیلی طول بکشه. ولی از خوبیای این سایت این هست که می‌شه برای تیکه‌ای از متن کامنت بذازیم و یا اینکه ورژن کنترل داره و می‌شه برگشت به ورژن قبلی


۲) از طریق نصب ملزومات کامپایلر لاتک و نصب افزونه‌ی LaTeX Workshop در visual studio code. برای نصب طبق این [سایت](https://mathjiajia.github.io/vscode-and-latex/#step-2-download--install-visual-studio-code) پیش می‌رویم. فقط چیزی که باید تغییر دهیم در گام سوم این سایت هست که گفته یه سری دستورات رو در settings.json کپی کنیم. همه چیز رو طبق سایت پیش می‌رویم فقط قسمت دوم رو طبق زیر تغییر می‌دهیم:

‍‍

"latex-workshop.latex.recipes": [
{
"name": "xelatex ➞ bibtex ➞ xelatex`×2",
"tools": [
    "xelatex",
    "bibtex",
    "xelatex",
    "xelatex"
    ]
}




یعنی می‌زاریم فقط xelatex بمونه و برای اینکه رفرنس‌ها هم درست چاپ بشوند bibtex رو هم می‌زاریم باشه. این تغییرات را باید در فایل settings.json وارد کنیم. برای پیدا کردنش باید`command + shift + p` و این فایل را پیدا کنیم. مسیرش الان در لپ تاپ من اینه

`~/Library/Application Support/Code/User/settings.json‍‍`

الان دیگه به صورت دیفالت یه کامپایلر xelatex داریم که اجرا می‌شه و همه چیز اوکیه.

---------
# نکات خیلی مهم برای هر پروژه لاتک

۱) هنگام استفاده از هر پروژه لاتک باید حتما یک فایل .bib داشته باشیم که اسم این فایل باید با اسم داخل کروشه در این خط از کد یکی باشد:
```
\bibliography{references}
```


یعنی ما باید یک فایل به اسم `references.bib` داشته باشیم وگرنه به ارورهای زیر در هنگام اجرای پروژه میخوریم:

```
I found no \citation commands BibTex [Ln 1, Col 1]
I found no \bibdata command BibTex [Ln 1, Col 1]
```

توجه شود که فایل .bbl را خود برنامه ایجاد میکنه یعنی نیاز نیست ما دستی ایجادش کنیم.


۲)برای حاشیه گذاری اطراف صفحه پکیج `frame` مسئول این کاره بنابراین برای حذف این حاشیه ها باید این پکیج را از داکیومنت لاتکمون حذف کنیم کلا.

۳) پکیج xepersian باید آخرین پکیج در لیست پکیج های استفاده شده ی ما باشد در غیر اینصورت ارور میگیریم.

۴) برای اینکه فهرست، رفرنس ها و فوت نوت هامون حالت هایپرلینک داشته باشند باید از پکیج hyperref استفاده شود.

۵) برای اینکه فوت نوت ها در هر صفحه از شماره ۱ شروع شوند باید از دو دستور زیر با هم دیگه استفاده شود. توجه شود که نباید جداشون کنیم و باید بعد از پکیج xepersian استفاده شود:


```
\usepackage{perpage}
\MakePerPage[1]{footnote}
```
**آپدیت** : من این دو دستور را در پروپوزالم استفاده کردم و درست عمل می کرد، در حالیکه برای پایان نامه یک مشکلی داشت و آن هم این بود که فوت نوت صفحه اول پایان نامه از ۲ شروع می شد ولی برای بقیه صفحه ها درست بود. این مشکل شاید به دلیل ورژن لاتک یا استفاده از پکیج های جدیدی بود که در پایان نامه داشتم ولی در پروپوزال نداشتم بوده. برای حل این مشکل طبق این این [سایت](https://tex.stackexchange.com/a/361744/284551) از دو دستور زیر به جای دو دستور بالا استفاده کردم.
```
\usepackage{zref-perpage}
\zmakeperpage{footnote}
```


۶) برای اضافه کردن یک بخشی به فهرست از دستور زیر استفاده میشود. برای مثال مراجع جزو فصل های پایان نامه نیست ولی دوست داریم در فهرست نمایش داده بشه یا هر قسمت دیگه ای، بعد از تعریف اون قسمت بلافاصله دستور زیر باید نوشته شود:

```
\addcontentsline{toc}{chapter}{کتاب‌نامه}
```
به عبارت دیگر برای کتاب نامه باید کد بالا را در ادامه تعریف صفحه کتاب نامه بیاوریم که به صورت زیر میشه:

```
\begin{latin} 
\newpage
\bibliographystyle{unsrtnat}
\bibliography{references}
\end{latin}
\addcontentsline{toc}{chapter}{کتاب‌نامه}
```

۷) [این](https://www.overleaf.com/learn/latex/Sections_and_chapters) سایت در مورد section بندی و اینا خوب توضیح داده که هر levelای از section بندی چه دستوری دارد.

۸) اگر به این مشکل خوردید که در یک عکسی کپشن دادید و رفرنسی که در کپشن اومده از یک شروع شده باید از راه زیر رفت. به عبارت دیگر، اگر یک رفرنسی، رفرنس شماره ی ۸ شما باشه و یک عکسی رو به اون رفرنس بدید ولی شماره اون رفرنس توی عکس یه چیز دیگه باشه باید از پکیج `notoccite`‍ بعد از پکیج `xepersian` استفاده شود. برای اطلاعات بیشتر به [این](https://tex.stackexchange.com/questions/224984/when-citing-inside-caption-it-starts-at-number-one) سایت مراجعه شود.

-----------
# درست کردن واژه نامه فارسی به انگلیسی و واژه نامه انگلیسی به فارسی در لاتک
من در vscode کد و با افزونه‌ی latex workshop کدهای لاتک را اجرا می کنم. برای اینکه بتوانیم واژه نامه را به پایان نامه اضافه کنیم باید از پکیجی به نام glossary استفاده کنیم. این پکیج برای انگلیسی به فارسی درست کار میکنه ولی برای اینکه بتونیم واژه نامه فارسی به انگلیسی را هم درست داشته باشیم باید از پکیج xindy که برای اینکار و کار و مرتب کردن کلمات فارسی به کار میره استفاده کنیم.

برای اینکار ابتدا موارد مربوط به ایجاد واژه نامه را از [این](http://parsilatex.com/site/1401/08/create-a-glossary-in-xepersian/#!prettyPhoto) سایت مطالعه کردم و کدهای زیر را در فایل اصلی پایان نامه دقیقا قبل از begin{document} قرار دادم.
کدهای این قسمت برای ساخت استایل برای هر کدام از واژه نامه ها است. در سایت اشاره شده استایل رو طوری تعریف کرده که کلمات در واژه نامه بر اساس حرف اولشون گروه گروه می شوند و بین هر گروه یه فاصله ای ایجاد میشه. ما این ویژکی را نیاز نداریم پس خط مربوط به ایجاد هدینگ برای هر گروه را کامنت می کنیم و فاصله بین گروه ها را که در خط بالاش هست حذف می کنیم.

```
\newglossarystyle{myFaToEn}{%
	\setglossarystyle{list}
	\renewenvironment{theglossary}{}{}
	\renewcommand*{\glsgroupskip}{}
	% \renewcommand*{\glsgroupheading}[1]{\subsection*{\glsgetgrouptitle{##1}}}
	\renewcommand*{\glossentry}[2]{\noindent\glsentryname{##1}\dotfill\space \glsentrytext{##1}
		
	}
}

%% % تعریف استایل برای واژه نامه انگلیسی به فارسی، در این استایل واژه‌های فارسی در سمت راست و واژه‌های انگلیسی در سمت چپ خواهند آمد. از حالت گروه ‌بندی استفاده می‌کنیم، 
%% % یعنی واژه‌ها در گروه‌هایی به ترتیب حروف الفبا مرتب می‌شوند، مثلا:
%% % E
%%% Economy ............................... اقتصاد
%% % F
%% % Failure................................... اشکال
%% %N
%% % Network ................................. شبکه

\newglossarystyle{myEntoFa}{%
	%%% این دستور در حقیقت عملیات گروه‌بندی را انجام می‌دهد. بدین صورت که واژه‌ها در بخش‌های جداگانه گروه‌بندی می‌شوند، 
	%%% عنوان بخش همان نام حرفی است که هر واژه در آن گروه با آن شروع شده است. 
	\renewenvironment{theglossary}{}{}
	\renewcommand*{\glsgroupskip}{}
	% \renewcommand*{\glsgroupheading}[1]{\begin{LTR} \subsection*{\glsgetgrouptitle{##1}} \end{LTR}}
	%%% در این دستور نحوه نمایش واژه‌ها می‌آید. در این جا واژه فارسی در سمت راست و واژه انگلیسی در سمت چپ قرار داده شده است، و بین آن با نقطه پر می‌شود. 
	\renewcommand*{\glossentry}[2]{\noindent\glsentrytext{##1}\dotfill\space \glsentryname{##1}
		
	}
}

%%% تعیین استایل برای فهرست اختصارات
\newglossarystyle{myAbbrlist}{%
	%%% این دستور در حقیقت عملیات گروه‌بندی را انجام می‌دهد. بدین صورت که اختصارات‌ در بخش‌های جداگانه گروه‌بندی می‌شوند، 
	%%% عنوان بخش همان نام حرفی است که هر اختصار در آن گروه با آن شروع شده است. 
	\renewenvironment{theglossary}{}{}
	\renewcommand*{\glsgroupskip}{\vskip 10mm}
	\renewcommand*{\glsgroupheading}[1]{\begin{LTR} \subsection*{\glsgetgrouptitle{##1}} \end{LTR}}
	%%% در این دستور نحوه نمایش اختصارات می‌آید. در این جا حالت کوچک اختصار در سمت چپ و حالت بزرگ در سمت راست قرار داده شده است، و بین آن با نقطه پر می‌شود. 
	\renewcommand*{\glossentry}[2]{\noindent\glsentrytext{##1}\dotfill\space \Glsentrylong{##1}
		
	}
	%%% تغییر نام محیط abbreviation به فهرست اختصارات
	\renewcommand*{\acronymname}{\rl{فهرست اختصارات}}
}

```
سپس کدهای بعد را در ادامه اضافه می کنیم.

```
\newglossary[glg]{english}{gls}{glo}{واژه‌نامه انگلیسی به فارسی}
\newglossary[blg]{persian}{bls}{blo}{واژه‌نامه فارسی به انگلیسی}
\makeglossaries
\glsdisablehyper
%%% تعاریف مربوط به تولید واژه نامه و فهرست اختصارات و فهرست نمادها
%%%  در این فایل یکسری دستورات عمومی برای وارد کردن واژه‌نامه آمده است.
%%%  به دلیل این‌که قرار است این دستورات پایه‌ای را بازنویسی کنیم در این‌جا تعریف می‌کنیم. 
\let\oldgls\gls
\let\oldglspl\glspl

\makeatletter

\renewrobustcmd*{\gls}{\@ifstar\@msgls\@mgls}
\newcommand*{\@mgls}[1] {\ifthenelse{\equal{\glsentrytype{#1}}{english}}{\oldgls{#1}\glsuseri{f-#1}}{\lr{\oldgls{#1}}}}
\newcommand*{\@msgls}[1]{\ifthenelse{\equal{\glsentrytype{#1}}{english}}{\glstext{#1}\glsuseri{f-#1}}{\lr{\glsentryname{#1}}}}

\renewrobustcmd*{\glspl}{\@ifstar\@msglspl\@mglspl}
\newcommand*{\@mglspl}[1] {\ifthenelse{\equal{\glsentrytype{#1}}{english}}{\oldglspl{#1}\glsuseri{f-#1}}{\oldglspl{#1}}}
\newcommand*{\@msglspl}[1]{\ifthenelse{\equal{\glsentrytype{#1}}{english}}{\glsplural{#1}\glsuseri{f-#1}}{\glsentryplural{#1}}}

\makeatother

\newcommand{\newword}[4]{
	\newglossaryentry{#1}     {type={english},name={\lr{#2}},plural={#4},text={#3},description={}}
	\newglossaryentry{f-#1} {type={persian},name={#3},text={\lr{#2}},description={}}
}

%%% بر طبق این دستور، در اولین باری که واژه مورد نظر از واژه‌نامه وارد شود، پاورقی زده می‌شود. 
\defglsentryfmt[english]{\glsgenentryfmt\ifglsused{\glslabel}{}{\LTRfootnote{\glsentryname{\glslabel}}}}

%%% بر طبق این دستور، در اولین باری که واژه مورد نظر از فهرست اختصارات وارد شود، پاورقی زده می‌شود. 
\defglsentryfmt[acronym]{\glsentryname{\glslabel}\ifglsused{\glslabel}{}{\LTRfootnote{\glsentrydesc{\glslabel}}}}


%%%%%% ============================================================================================================

\newcommand{\printacronyms}{\printabbreviation}
%%% در این جا محیط هر دو واژه نامه را باز تعریف کرده ایم، تا اولا مشکل قرار دادن صفحه اضافی را حل کنیم، ثانیا عنوان واژه نامه ها را با دستور addcontentlist وارد فهرست مطالب کرده ایم.
\let\Oldprintglossary\printglossary
\renewcommand{\printglossary}{
	\let\appendix\relax
	%% تنظیم کننده فاصله بین خطوط در این قسمت
	\clearpage
	\phantomsection
	%% این دستور موجب این می‌شود که واژه‌نامه‌ها در  حالت دو ستونی نوشته شود. 
	% \twocolumn{}
	%% با این دستور عنوان واژه‌نامه به فهرست مطالب اضافه می‌شود. 
	\addcontentsline{toc}{chapter}{واژه نامه انگلیسی به فارسی}
	\setglossarystyle{myEntoFa}
	\Oldprintglossary[type=english]
	
	\clearpage
	\phantomsection
	%% با این دستور عنوان واژه‌نامه به فهرست مطالب اضافه می‌شود. 
	\addcontentsline{toc}{chapter}{واژه نامه فارسی به انگلیسی}
	\setglossarystyle{myFaToEn}
	\Oldprintglossary[type=persian]
	\onecolumn{}
}%
```

در نهایت برای ایجاد واژه نامه باید دستور `\printglossary` را در جایی که میخواهیم واژه نامه چاپ شود بگذاریم. در این پایان نامه این دستور را بعد از بقیه ی فصل ها به صورت زیر قرار می دهیم.

```
\input{Sections/pishgoftar}

\tableofcontents
\listoftables
\listoffigures

\input{Sections/S1}
\input{Sections/S2}
\input{Sections/S3}
\input{Sections/S4}
\input{Sections/S5}

\printglossary
```

تا اینجای کار، کدهای لاتک لازم را قرار دادیم. طبق سایت برای ایجاد واژه نامه فارسی به انگلیسی و مرتب شدن کلمات فارسی باید از پکیج xindy استفاده کنیم و یکسری دستوراتی را وارد کنیم که پکیج xindy کد ما را کامپایل کند. برای اینکار باید فایل setting.json  را درش تغییر ایجاد کنیم. دسترسی به این فایل در vscode از طریق `command + shift + p` و انتخاب گزینه `Preferences : Open User Settings (JSON)` امکان پذیر است. حال برای کامپایل شدن توسط xindy چون در vscode کار میکنیم طبق دستور سایت نمیتونیم پیش بریم پس محتوای فایل json را اینگونه تغییر می دهیم.

```
{
    "workbench.colorTheme": "Default Dark+",
    "files.autoSave": "afterDelay",
    "remote.SSH.remotePlatform": {
        "192.168.192.19": "linux"
    },
    "editor.unicodeHighlight.ambiguousCharacters": false,
    "github.copilot.enable": {
        "*": false,
        "yaml": false,
        "plaintext": false,
        "markdown": false,
        "python": false,
        "latex": false
    },
    "python.defaultInterpreterPath": "/Users/zahra/opt/anaconda3/bin/python",
    "security.workspace.trust.untrustedFiles": "open",
    "editor.inlineSuggest.enabled": true,
    "diffEditor.ignoreTrimWhitespace": false,
    "editor.minimap.enabled": false,
    "editor.copyWithSyntaxHighlighting": false,
    "latex-workshop.latex.build.forceRecipeUsage": false ,

    "latex-workshop.latex.tools": [
        {
         "name": "latexmk",
         "command": "latexmk",
         "args": [
          "-synctex=1",
          "-interaction=nonstopmode",
          "-file-line-error",
          "-pdf",
          "-outdir=%OUTDIR%",
          "%DOC%.tex"
         ],
         "env": {}
        },
        {
         "name": "xelatex",
         "command": "xelatex",
         "args": [
          "-synctex=1",
          "-interaction=nonstopmode",
          "-file-line-error",
          "%DOC%.tex"
         ],
         "env": {}
        },
        {
         "name": "pdflatex",
         "command": "pdflatex",
         "args": [
          "-synctex=1",
          "-interaction=nonstopmode",
          "-file-line-error",
          "%DOC%.tex"
         ],
         "env": {}
        },
        {
         "name": "bibtex",
         "command": "bibtex",
         "args": [
          "%DOCFILE%"
         ],
         "env": {}
        },
        {
        "name": "makeglossaries",
        "command": "makeglossaries",
        "args": [
            "%DOCFILE%"
        ],
        "env": {}
        },
        {
        "name": "xindy_persian_glossary",
        "command": "xindy",
        "args": [
            "-L",
            "persian-variant1",
            "-C",
            "utf8",
            "-I",
            "xindy",
            "-M",
            "%DOCFILE%.xdy",
            "-t",
            "%DOCFILE%.glg",
            "-o",
            "%DOCFILE%.gls",
            "%DOCFILE%.glo"
            // Add or modify arguments as needed
        ],
        "env": {}
        },
        {
        "name": "xindy_persian_bibliography",
        "command": "xindy",
        "args": [
            "-L",
            "persian-variant1",
            "-C",
            "utf8",
            "-I",
            "xindy",
            "-M",
            "%DOCFILE%.xdy",
            "-t",
            "%DOCFILE%.blg",
            "-o",
            "%DOCFILE%.bls",
            "%DOCFILE%.blo"
            // Add or modify arguments as needed
        ],
        "env": {}
        },
        {
        "name": "xindy_english_acronym",
        "command": "xindy",
        "args": [
            "-L",
            "english",
            "-C",
            "utf8",
            "-I",
            "xindy",
            "-M",
            "%DOCFILE%.xdy",
            "-t",
            "%DOCFILE%.alg",
            "-o",
            "%DOCFILE%.acr",
            "%DOCFILE%.acn"
            // Add or modify arguments as needed
        ],
        "env": {}
        }
        
       ],
    "latex-workshop.latex.recipes": [
    {
    "name": "xelatex ➞ bibtex ➞ makeglossaries ➞ xelatex`×2 ➞ xindy_persian_glossary ➞ xindy_persian_bibliography ➞ xindy_english_acronym ➞ xelatex`×2",
    "tools": [
        "xelatex",
        "bibtex",
        "makeglossaries",
        "xelatex",
        "xelatex",
        "xindy_persian_glossary",
        "xindy_persian_bibliography",
        "xindy_english_acronym",
        "xelatex",
        "xelatex",
        ]
    }
    // {
    // "name": "xindy for Persian Glossary",
    // "tools": [
    //     "xindy_persian_glossary"
    // ]
    // },
    // {
    // "name": "xindy for Persian Bibliography",
    // "tools": [
    //     "xindy_persian_bibliography"
    // ]
    // },
    // {
    // "name": "xindy for English Acronym",
    // "tools": [
    //     "xindy_english_acronym"
    // ]
    // }
    // ,{
        // "name": "pdfLaTeX",
        // "tools": [
        //  "pdflatex"
        // ]
    // }
    ],
    "[latex]": {
        "editor.defaultFormatter": "James-Yu.latex-workshop"
    },
    "latex-workshop.linting.chktex.exec.args": [
        "-wall",
        "-n22",
        "-n30",
        "-e16",
        "-q",
        "-n3"
    ],
    "notebook.output.textLineLimit": 62,
    "notebook.lineNumbers": "on",
    "jupyter.widgetScriptSources": [
        "jsdelivr.com",
        "unpkg.com"
    ],
    "window.zoomLevel": 1
}

```
 با اینکار به درستی واژه نامه انگلیسی به فارسی و فارسی به انگلیسی ایجاد میشن.

 فقط برای ایجاد این واژه نامه باید یک فایل جدا به نام `myglossary.tex` بسازیم و قبل از  begin{document} دستور  input{myglossary} را بزنیم. در این فایل باید واژه ها را ایجاد کنیم به صورت زیر:
```
\newword{arg1}{arg2}{arg3}{arg4}
```

arg1: هر واژه یک برچسب یکتا باید برای خود داشته باشد. تمامی ارجاعات به واژه با استفاده از این برچسب انجام می‌پذیرد.
arg2: آرگومان دوم تعیین کننده معادل انگلیسی هر واژه است.
arg3: آرگومان سوم تعیین‌کننده معادل فارسی کلمه مورد نظر است.
arg4: این آرگومان حالت جمع arg3 است.



و در فایل tex اصلی دیگر از این به بعد به جای استفاده از LTRfootnote\ از دستور {arg1}gls\ استفاده میشه 
