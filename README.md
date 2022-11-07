<html dir='rtl'>
<h2 dir='rtl'>
توضیخ کلی کار
</h2>
<p dir='rtl'>
در این نوت بوک،‌ مقاله‌هایی در زمینه مدل‌رانه، توصیه‌گر و استفاده از توصیه‌گر در فرایند مدل‌رانه مورد پردازش قرار گرفته است تا تراکم کلمات استفاده شده در آن و کلماتی که به یکدیگر مرتبط هستند، مشخص شوند.
</p>

<h2 dir='rtl'>
نوت بوک به تفکیک بخش‌ها
</h2>
<p dir='rtl'>
در ادامه بخش‌های مختلف نوت بوک به همراه توضیحاتی درمورد هر بخش، آورده شده است.
</p>
<h3 dir='rtl'>
نصب پیش‌نیازها
</h3>
<p dir='rtl'>
در اولین سلول این نوت بوک، پیش‌نیازهایی که برای اجرای این نوت بوک مورد نیاز است آورده شده است تا نصب شوند. بنابراین این سلول باید قبل از اجرای سلول‌های دیگر اجرا شود.
</p>

<h3 dir='rtl'>
درون‌ریزی کتابخانه‌ها و تنظیمات اولیه
</h3>
<p dir='rtl'>
در این بخش، کتابخانه‌هایی که در ادامه مورد نیاز بوده اند درون‌ریزی شده اند و برخی کتابخانه‌ها که نیاز به پیش‌تنظیمات داشته اند، تنظیم شده اند.
</p>

<h3 dir='rtl'>
خزنده
</h3>
<p dir='rtl'>
در این بخش، خزنده کلیه‌ی فایل‌های پی دی اف را پردازش کرده و متن آنها را از صفحات مختلف استخراح می‌کند تا در مراحل بعد پیش‌پردازش و پردازش روی متن استخراج شده انجام گیرد.
</p>

<h3 dir='rtl'>
ابزار تمیزکردن متن و جملات
</h3>
<p dir='rtl'>
در این بخش ابزارهایی به منظور بالابردن خوانایی در پیش‌پردازش تعریف شده اند که یکی برای تمیز کردن متنی است که به صورت خام استخراج شده است و دیگری برای تمیز کردن جملات.
</p>

<h3 dir='rtl'>
خواندن دیتاست و پیش‌پردازش آن
</h3>
<p dir='rtl'>
در این گام دیتاستی که ذخیره شده بود، خوانده می‌شود و سپس مراحل پیش‌پردازش به کمک ابزارهای تعریف‌شده در بخش قبل و ابزارهای کتابخانه‌های درون‌ریزی شده مانند nltk، انجام می‌شوند.
</p>

<h3 dir='rtl'>
ابزار پردازش وردنت
</h3>
<p dir='rtl'>
برای بهتر شدن خوانایی کد،‌ دو تابع تعریف شده اند که به ترتیب بسامد کلمات و ارتباط آنها با یکدیگر را توسط وردنت تحلیل می‌کند.
</p>

<h3 dir='rtl'>
پردازش آماری
</h3>
<p dir='rtl'>
در این بخش، آماری از کل جملات مقالات آورده شده است که از جمله‌ی آن تراکم کلمات در جملات و ارتباط بین کلمات شبیه به یکدیگر و گروه‌بندی آنها هستند.
</p>
</html>


```python
# Install Dependencies

%pip install pypdf2
%pip install pycryptodome
%pip install nltk
%pip install tqdm
%pip install spacy
!python -m spacy download en_core_web_sm
```

    Collecting pypdf2
      Using cached PyPDF2-2.11.1-py3-none-any.whl (220 kB)
    Requirement already satisfied: typing-extensions>=3.10.0.0 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from pypdf2) (4.4.0)
    Installing collected packages: pypdf2
    Successfully installed pypdf2-2.11.1
    Note: you may need to restart the kernel to use updated packages.
    Collecting pycryptodome
      Using cached pycryptodome-3.15.0-cp35-abi3-win_amd64.whl (1.9 MB)
    Installing collected packages: pycryptodome
    Successfully installed pycryptodome-3.15.0
    Note: you may need to restart the kernel to use updated packages.
    Collecting nltk
      Downloading nltk-3.7-py3-none-any.whl (1.5 MB)
         ---------------------------------------- 1.5/1.5 MB 372.2 kB/s eta 0:00:00
    Collecting joblib
      Using cached joblib-1.2.0-py3-none-any.whl (297 kB)
    Requirement already satisfied: tqdm in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from nltk) (4.64.1)
    Collecting regex>=2021.8.3
      Downloading regex-2022.10.31-cp39-cp39-win_amd64.whl (267 kB)
         ------------------------------------ 267.8/267.8 kB 225.7 kB/s eta 0:00:00
    Requirement already satisfied: click in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from nltk) (8.1.3)
    Requirement already satisfied: colorama in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from click->nltk) (0.4.6)
    Installing collected packages: regex, joblib, nltk
    Successfully installed joblib-1.2.0 nltk-3.7 regex-2022.10.31
    Note: you may need to restart the kernel to use updated packages.
    Requirement already satisfied: tqdm in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (4.64.1)Note: you may need to restart the kernel to use updated packages.
    
    Requirement already satisfied: colorama in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from tqdm) (0.4.6)
    Requirement already satisfied: spacy in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (3.4.2)
    Requirement already satisfied: jinja2 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from spacy) (3.1.2)
    Requirement already satisfied: setuptools in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from spacy) (65.2.0)
    Requirement already satisfied: wasabi<1.1.0,>=0.9.1 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from spacy) (0.10.1)
    Requirement already satisfied: murmurhash<1.1.0,>=0.28.0 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from spacy) (1.0.9)
    Requirement already satisfied: cymem<2.1.0,>=2.0.2 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from spacy) (2.0.7)
    Requirement already satisfied: spacy-loggers<2.0.0,>=1.0.0 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from spacy) (1.0.3)
    Requirement already satisfied: preshed<3.1.0,>=3.0.2 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from spacy) (3.0.8)
    Requirement already satisfied: langcodes<4.0.0,>=3.2.0 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from spacy) (3.3.0)
    Requirement already satisfied: packaging>=20.0 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from spacy) (21.3)
    Requirement already satisfied: thinc<8.2.0,>=8.1.0 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from spacy) (8.1.5)
    Requirement already satisfied: srsly<3.0.0,>=2.4.3 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from spacy) (2.4.5)
    Requirement already satisfied: pathy>=0.3.5 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from spacy) (0.6.2)
    Requirement already satisfied: catalogue<2.1.0,>=2.0.6 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from spacy) (2.0.8)
    Requirement already satisfied: spacy-legacy<3.1.0,>=3.0.10 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from spacy) (3.0.10)
    Requirement already satisfied: tqdm<5.0.0,>=4.38.0 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from spacy) (4.64.1)
    Requirement already satisfied: typer<0.5.0,>=0.3.0 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from spacy) (0.4.2)
    Requirement already satisfied: pydantic!=1.8,!=1.8.1,<1.11.0,>=1.7.4 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from spacy) (1.10.2)
    Requirement already satisfied: requests<3.0.0,>=2.13.0 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from spacy) (2.28.1)
    Requirement already satisfied: numpy>=1.15.0 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from spacy) (1.23.4)
    Requirement already satisfied: pyparsing!=3.0.5,>=2.0.2 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from packaging>=20.0->spacy) (3.0.9)
    Requirement already satisfied: smart-open<6.0.0,>=5.2.1 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from pathy>=0.3.5->spacy) (5.2.1)
    Requirement already satisfied: typing-extensions>=4.1.0 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from pydantic!=1.8,!=1.8.1,<1.11.0,>=1.7.4->spacy) (4.4.0)
    Requirement already satisfied: charset-normalizer<3,>=2 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from requests<3.0.0,>=2.13.0->spacy) (2.1.1)
    Requirement already satisfied: certifi>=2017.4.17 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from requests<3.0.0,>=2.13.0->spacy) (2022.9.24)
    Requirement already satisfied: urllib3<1.27,>=1.21.1 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from requests<3.0.0,>=2.13.0->spacy) (1.26.12)
    Requirement already satisfied: idna<4,>=2.5 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from requests<3.0.0,>=2.13.0->spacy) (3.4)
    Requirement already satisfied: confection<1.0.0,>=0.0.1 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from thinc<8.2.0,>=8.1.0->spacy) (0.0.3)
    Requirement already satisfied: blis<0.8.0,>=0.7.8 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from thinc<8.2.0,>=8.1.0->spacy) (0.7.9)
    Requirement already satisfied: colorama in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from tqdm<5.0.0,>=4.38.0->spacy) (0.4.6)
    Requirement already satisfied: click<9.0.0,>=7.1.1 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from typer<0.5.0,>=0.3.0->spacy) (8.1.3)
    Requirement already satisfied: MarkupSafe>=2.0 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from jinja2->spacy) (2.1.1)
    Note: you may need to restart the kernel to use updated packages.
    Collecting en-core-web-sm==3.4.1
      Downloading https://github.com/explosion/spacy-models/releases/download/en_core_web_sm-3.4.1/en_core_web_sm-3.4.1-py3-none-any.whl (12.8 MB)
         -------------------------------------- 12.8/12.8 MB 969.3 kB/s eta 0:00:00
    Requirement already satisfied: spacy<3.5.0,>=3.4.0 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from en-core-web-sm==3.4.1) (3.4.2)
    Requirement already satisfied: tqdm<5.0.0,>=4.38.0 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from spacy<3.5.0,>=3.4.0->en-core-web-sm==3.4.1) (4.64.1)
    Requirement already satisfied: typer<0.5.0,>=0.3.0 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from spacy<3.5.0,>=3.4.0->en-core-web-sm==3.4.1) (0.4.2)
    Requirement already satisfied: thinc<8.2.0,>=8.1.0 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from spacy<3.5.0,>=3.4.0->en-core-web-sm==3.4.1) (8.1.5)
    Requirement already satisfied: langcodes<4.0.0,>=3.2.0 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from spacy<3.5.0,>=3.4.0->en-core-web-sm==3.4.1) (3.3.0)
    Requirement already satisfied: wasabi<1.1.0,>=0.9.1 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from spacy<3.5.0,>=3.4.0->en-core-web-sm==3.4.1) (0.10.1)
    Requirement already satisfied: jinja2 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from spacy<3.5.0,>=3.4.0->en-core-web-sm==3.4.1) (3.1.2)
    Requirement already satisfied: cymem<2.1.0,>=2.0.2 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from spacy<3.5.0,>=3.4.0->en-core-web-sm==3.4.1) (2.0.7)
    Requirement already satisfied: pathy>=0.3.5 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from spacy<3.5.0,>=3.4.0->en-core-web-sm==3.4.1) (0.6.2)
    Requirement already satisfied: murmurhash<1.1.0,>=0.28.0 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from spacy<3.5.0,>=3.4.0->en-core-web-sm==3.4.1) (1.0.9)
    Requirement already satisfied: spacy-loggers<2.0.0,>=1.0.0 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from spacy<3.5.0,>=3.4.0->en-core-web-sm==3.4.1) (1.0.3)
    Requirement already satisfied: numpy>=1.15.0 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from spacy<3.5.0,>=3.4.0->en-core-web-sm==3.4.1) (1.23.4)
    Requirement already satisfied: srsly<3.0.0,>=2.4.3 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from spacy<3.5.0,>=3.4.0->en-core-web-sm==3.4.1) (2.4.5)
    Requirement already satisfied: catalogue<2.1.0,>=2.0.6 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from spacy<3.5.0,>=3.4.0->en-core-web-sm==3.4.1) (2.0.8)
    Requirement already satisfied: pydantic!=1.8,!=1.8.1,<1.11.0,>=1.7.4 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from spacy<3.5.0,>=3.4.0->en-core-web-sm==3.4.1) (1.10.2)
    Requirement already satisfied: spacy-legacy<3.1.0,>=3.0.10 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from spacy<3.5.0,>=3.4.0->en-core-web-sm==3.4.1) (3.0.10)
    Requirement already satisfied: requests<3.0.0,>=2.13.0 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from spacy<3.5.0,>=3.4.0->en-core-web-sm==3.4.1) (2.28.1)
    Requirement already satisfied: preshed<3.1.0,>=3.0.2 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from spacy<3.5.0,>=3.4.0->en-core-web-sm==3.4.1) (3.0.8)
    Requirement already satisfied: packaging>=20.0 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from spacy<3.5.0,>=3.4.0->en-core-web-sm==3.4.1) (21.3)
    Requirement already satisfied: setuptools in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from spacy<3.5.0,>=3.4.0->en-core-web-sm==3.4.1) (65.2.0)
    Requirement already satisfied: pyparsing!=3.0.5,>=2.0.2 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from packaging>=20.0->spacy<3.5.0,>=3.4.0->en-core-web-sm==3.4.1) (3.0.9)
    Requirement already satisfied: smart-open<6.0.0,>=5.2.1 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from pathy>=0.3.5->spacy<3.5.0,>=3.4.0->en-core-web-sm==3.4.1) (5.2.1)
    Requirement already satisfied: typing-extensions>=4.1.0 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from pydantic!=1.8,!=1.8.1,<1.11.0,>=1.7.4->spacy<3.5.0,>=3.4.0->en-core-web-sm==3.4.1) (4.4.0)
    Requirement already satisfied: certifi>=2017.4.17 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from requests<3.0.0,>=2.13.0->spacy<3.5.0,>=3.4.0->en-core-web-sm==3.4.1) (2022.9.24)
    Requirement already satisfied: urllib3<1.27,>=1.21.1 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from requests<3.0.0,>=2.13.0->spacy<3.5.0,>=3.4.0->en-core-web-sm==3.4.1) (1.26.12)
    Requirement already satisfied: charset-normalizer<3,>=2 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from requests<3.0.0,>=2.13.0->spacy<3.5.0,>=3.4.0->en-core-web-sm==3.4.1) (2.1.1)
    Requirement already satisfied: idna<4,>=2.5 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from requests<3.0.0,>=2.13.0->spacy<3.5.0,>=3.4.0->en-core-web-sm==3.4.1) (3.4)
    Requirement already satisfied: blis<0.8.0,>=0.7.8 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from thinc<8.2.0,>=8.1.0->spacy<3.5.0,>=3.4.0->en-core-web-sm==3.4.1) (0.7.9)
    Requirement already satisfied: confection<1.0.0,>=0.0.1 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from thinc<8.2.0,>=8.1.0->spacy<3.5.0,>=3.4.0->en-core-web-sm==3.4.1) (0.0.3)
    Requirement already satisfied: colorama in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from tqdm<5.0.0,>=4.38.0->spacy<3.5.0,>=3.4.0->en-core-web-sm==3.4.1) (0.4.6)
    Requirement already satisfied: click<9.0.0,>=7.1.1 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from typer<0.5.0,>=0.3.0->spacy<3.5.0,>=3.4.0->en-core-web-sm==3.4.1) (8.1.3)
    Requirement already satisfied: MarkupSafe>=2.0 in d:\education\master\semesters\semester 3\nlp\hws\1\notebook\venv\lib\site-packages (from jinja2->spacy<3.5.0,>=3.4.0->en-core-web-sm==3.4.1) (2.1.1)
    Installing collected packages: en-core-web-sm
    Successfully installed en-core-web-sm-3.4.1
    [+] Download and installation successful
    You can now load the package via spacy.load('en_core_web_sm')
    


```python
# Import required modules and initial config

import PyPDF2
import glob
import pickle
import string
import nltk
import re
import spacy
from string import punctuation
from nltk.stem import WordNetLemmatizer
from nltk.stem.porter import PorterStemmer
from string import *
from nltk.probability import FreqDist
import numpy as np
import itertools
import re
from nltk.corpus import wordnet as wn
from collections import defaultdict

DATASEST_FILENAME = 'dataset.pickle'
nlp = spacy.load('en_core_web_sm') # or whatever model you have installed
nltk.download('wordnet')
```

    [nltk_data] Downloading package wordnet to
    [nltk_data]     C:\Users\arman\AppData\Roaming\nltk_data...
    [nltk_data]   Package wordnet is already up-to-date!
    




    True




```python
# Crawl all text of the articles

all_text = []

for f in glob.glob("corpus/*.pdf"):
    
    with open(f, 'rb') as f_obj:
        file_sentences = []
        
        # creating a pdf reader object
        pdfReader = PyPDF2.PdfFileReader(f_obj)
  
        # printing number of pages in pdf file
        for p in range(pdfReader.numPages):
            # creating a page object
            pageObj = pdfReader.getPage(p)
        
            # extracting text from page
            file_sentences.append(pageObj.extractText())
            
        all_text.append(file_sentences)
        
with open(DATASEST_FILENAME, 'wb+') as f:
    pickle.dump(all_text, f)
    
```

    Xref table not zero-indexed. ID numbers for objects will be corrected.
    Xref table not zero-indexed. ID numbers for objects will be corrected.
    Xref table not zero-indexed. ID numbers for objects will be corrected.
    Xref table not zero-indexed. ID numbers for objects will be corrected.
    Xref table not zero-indexed. ID numbers for objects will be corrected.
    


```python
# Sanitizing text and sentences utils

def sanitize_text(text):
    # try to remove all refrencese 
    text = re.sub(r'\n\[\s*\d\s*\][^\n]+\n', r'\n', text)
    
    # remove links
    text = re.sub(r'http[\S]+[\s]', '', text)
    text = re.sub(r'(www|WWW)[\S]+[\s]', '', text)
    
    # remove spacee before the dash in names having dash
    text = re.sub(r'[ ](-\w)', r'\1', text)

    # complete sentences splited by breakline
    text = re.sub(r'-[\n]', '', text)

    # remove non-content setntences
    text = re.sub(r'[\n].+[^.][\n]', '\n', text)

    # replace multispace with single space
    text = re.sub(r'[\s]+', ' ', text)

    # remove references
    text = re.sub(r'\[.+?\]', '', text)
    
    # remove three dots
    text = re.sub(r'[.]{3} | [*]', '', text)
        
    return text

def normalize_sentence(tokenized_sents, minimum_length=2, stopword_removal=True, stopwords_domain=[], lower_case=False, punctuation_removal=True):
    '''
    normalization function
    '''
    normalized_sents = tokenized_sents
    
    if stopword_removal:
        # Remove stopwords in English and also the given domain stopwords
        stopwords = [x.lower() for x in nltk.corpus.stopwords.words('english')]
        normalized_sents=[[word for word in sentence if (word.lower() not in stopwords_domain + stopwords)] for sentence in tokenized_sents ]

    if punctuation_removal:
        # Remove punctuations
        normalized_sents=[[word for word in sentence if word not in string.punctuation] for sentence in normalized_sents ]

    if lower_case:
        # Convert everything to lowercase and filter based on a min length
        normalized_sents=[[word.lower() for word in sentence if len(word)>minimum_length] for sentence in normalized_sents ]

    elif minimum_length>1:
        normalized_sents= [[word for word in sentence if len(word)>minimum_length] for sentence in normalized_sents ]        
        
    return normalized_sents
```


```python
# Read dataset and pre-prcoessing

with open(DATASEST_FILENAME, 'rb') as f:
    all_text = pickle.load(f)

# merge all pages of each article
articles = ['\n'.join(article_pages_list) for article_pages_list in all_text]

# merge all articles
text = '\n'.join(articles)
text = sanitize_text(text)
sentences = nltk.tokenize.sent_tokenize(text)
tokenized_sentences = [[word for word in nltk.tokenize.word_tokenize(sent) if
                        len(word)<30 and word != '...'] for sent in sentences]
tokenized_sentences = filter(lambda x: len(x) > 6, tokenized_sentences)
normalized_sentences = normalize_sentence(tokenized_sentences)
```


```python
# WordNet util functions

def categories_from_hypernyms(termlist):
    hypterms = []
    hypterms_dict = defaultdict()
    for term in termlist:                  # for each term
        s = wn.synsets(term.lower(), 'n')  # get its nominal synsets
        for syn in s:                      # for each lemma synset
            for hyp in syn.hypernyms():    # It has a list of hypernyms
                hypterms.append(hyp.name())      # Extract the hypernym name and add to list
                if hyp.name() not in hypterms_dict:
                    hypterms_dict[hyp.name()] = list()
                hypterms_dict[hyp.name()].append(term)  # Extract examples and add them to dict
                
    hypfd = nltk.FreqDist(hypterms)             # After going through all the nouns, print out the hypernyms 
    for (name, count) in hypfd.most_common(25):  # that have accumulated the most counts (have seen the most descendents)
        print( name, '({0})'.format(count))
        print ('\t', ', '.join(set(hypterms_dict[name])))  # show the children found for each hypernym
        print ()
        
def freq_normed_unigrams(sents):
    wnl = WordNetLemmatizer()
    
    tagged_POS_sents = [nltk.pos_tag(sent) for sent in sents]
    
    normed_tagged_words = [wnl.lemmatize(word[0].lower()) for sent in tagged_POS_sents
                           for word in sent 
                           if word[0].lower() not in nltk.corpus.stopwords.words('english')
                           and word[0] not in punctuation
                           and not re.search(r'''^[\.,;"'?!():\-_`]+$''', word[0])
                           and word[1].startswith('N')]

    top_normed_unigrams = [word for (word, count) in nltk.FreqDist(normed_tagged_words).most_common(40)]
    return top_normed_unigrams
```


```python
# Generate different statastics

# frequency statastics
mp_freqdist = FreqDist(itertools.chain(*normalized_sentences))
top20words=mp_freqdist.most_common(20)
print ('%-16s' % 'word', '%-16s' % 'Frequency','%-16s' %  '% of the total')
for topword in top20words:
    percent=(topword[1]/len(normalized_sentences))*100
    print ('%-16s' % topword[0], '%-16s' % topword[1],'%-16s' %  percent)

print('\n', 60*'-', '\n')

# word and snetence averages
sentence_words = list(itertools.chain(*normalized_sentences))
print ('%-16s' % 'Number of words', '%-16s' % len(sentence_words))
print ('%-16s' % 'Number of unique words', '%-16s' % len(set(sentence_words)))
avg=np.sum([len(word) for word in sentence_words])/len(sentence_words)
print ('%-16s' % 'Average word length', '%-16s' % avg)
avg_sentence_length_c=np.mean([len(' '.join(sentence)) for sentence in normalized_sentences])
print ('%-16s' % 'Average sentence length in characters', '%-16s' % avg_sentence_length_c)
print ('%-16s' % 'Longest word', '%-16s' % sentence_words[np.argmax([len(word) for word in sentence_words])])

# WordNet
top_words = freq_normed_unigrams(normalized_sentences)
categories_from_hypernyms(top_words)

```

    word             Frequency        % of the total  
    model            1369             14.154259718775847
    models           770              7.9611248966087675
    user             690              7.133995037220843
    transformation   662              6.844499586435069
    system           553              5.717535153019024
    used             513              5.303970223325062
    recommendation   457              4.724979321753516
    data             440              4.549214226633581
    systems          412              4.259718775847808
    using            387              4.001240694789082
    use              375              3.8771712158808933
    tools            360              3.722084367245657
    users            350              3.618693134822167
    process          349              3.6083540115798183
    recommender      331              3.4222497932175346
    recommendations  330              3.411910669975186
    approach         326              3.37055417700579
    information      321              3.3188585607940446
    modeling         316              3.2671629445823 
    Model            307              3.1741108354011582
    
     ------------------------------------------------------------ 
    
    Number of words  111932          
    Number of unique words 19520           
    Average word length 7.426080120072902
    Average sentence length in characters 96.51385442514474
    Longest word     model-totextandmodel-to-model
    person.n.01 (4)
    	 case, user
    
    activity.n.01 (4)
    	 use, process, support
    
    body_part.n.01 (3)
    	 process, feature, system
    
    collection.n.01 (3)
    	 information, data, class
    
    cognition.n.01 (3)
    	 information, process
    
    concept.n.01 (3)
    	 section, rule
    
    direction.n.06 (3)
    	 rule
    
    hypothesis.n.02 (2)
    	 model, framework
    
    assistant.n.01 (2)
    	 model
    
    ideal.n.01 (2)
    	 model, example
    
    representation.n.01 (2)
    	 model, example
    
    method.n.01 (2)
    	 technique, system
    
    change.n.01 (2)
    	 development, transformation
    
    change_of_integrity.n.01 (2)
    	 transformation
    
    information.n.02 (2)
    	 example, data
    
    part.n.02 (2)
    	 element, section
    
    substance.n.01 (2)
    	 element
    
    use.n.01 (2)
    	 development, application
    
    part.n.01 (2)
    	 item
    
    fact.n.01 (2)
    	 item, case
    
    supporting_structure.n.01 (2)
    	 framework, support
    
    happening.n.01 (2)
    	 example, case
    
    gathering.n.01 (2)
    	 class
    
    time_period.n.01 (2)
    	 time
    
    resource.n.01 (2)
    	 support
    
    
