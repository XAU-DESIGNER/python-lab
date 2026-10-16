## venv
فرض کنیم داخل فولدر پروژه‌ات هستی:

```
cd ~/path/to/project
```

### 1. ساختن venv

```
python3 -m venv .venv
```

این دستور یک فولدر به اسم `.venv` داخل پروژه می‌سازه:

```
project/
├── .venv/
├── app.py
└── ...
```

### 2. فعال کردن

روی Ubuntu:

```
source .venv/bin/activate
```

بعد ترمینالت چیزی شبیه این می‌شه:

```
(.venv) xau-designer@xau-designer-pc:~/project$
```

### 3. حالا Python و pip مربوط به همین محیط‌اند

```
python --version
pip --version
```

مثلاً:

```
Python 3.14.4
```

و نصب پکیج‌ها:

```
pip install requests
```

فقط داخل همین venv نصب می‌شود.

### 4. خروج از venv

```
deactivate
```

---

### پیشنهاد من برای پروژه‌های Uranium

بهتره اسمش رو `.venv` بذاری:

```
python3 -m venv .venv
```

و بعد `.venv` رو وارد `.gitignore` کنی:

```
.venv/
```

اینطوری محیط مجازی هر پروژه کاملاً جداست و خود فولدر venv هم وارد Git نمی‌شه.

---
اگر پروژه `requirements.txt` داره، ترتیب کار اینه:

```
# داخل فولدر پروژه
python3 -m venv .venv
```

بعد فعالش کن:

```
source .venv/bin/activate
```

بعد **requirements.txt رو نصب کن**:

```
pip install -r requirements.txt
```

برای اطمینان:

```
pip list
```

یا:

```
pip freeze
```

### در نهایت ساختار پروژه:

```
my-project/
├── .venv/
├── requirements.txt
├── app.py
└── ...
```

و یادت باشه `.venv` رو داخل Git نذاری:

```
.venv/
```

اگر پروژه رو از Git کلون کردی، معمولاً **خود `.venv` همراه پروژه نمیاد**؛ فقط:

```
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

و محیطت دوباره آماده‌ست. 🚀