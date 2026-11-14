# دستورات پایه Git

## ۱ Git چیست؟

Git یک سیستم کنترل نسخه توزیع شده است. با استفاده از آن می توان تغییرات فایل های یک پروژه را در طول زمان ثبت کرد، نسخه های قبلی را مشاهده کرد و کار چند توسعه دهنده را با یکدیگر ترکیب کرد. Git روی رایانه اجرا می شود و برای کار با آن الزاماً به اینترنت نیاز نیست.

## ۲ نصب و بررسی Git

پس از نصب Git در ترمینال یا Command Prompt دستور زیر را اجرا کنید:

git --version

این دستور نسخه نصب شده Git را نمایش می دهد.

## ۳ تنظیم نام و ایمیل کاربر

Git از این اطلاعات برای ثبت هویت نویسنده Commitها استفاده می کند:

git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"

برای مشاهده تنظیمات:

git config --global --list

بهتر است از ایمیلی استفاده کنید که در حساب GitHub شما ثبت شده است.

## ۴ دریافت یک مخزن با Clone

برای دریافت یک نسخه محلی از مخزن GitHub:

git clone https://github.com/OWNER/GitHub-Guide.git
cd GitHub-Guide

به جای `OWNER` نام کاربری مالک مخزن را قرار دهید. دستور `clone` فایل ها و تاریخچه مخزن را دریافت می کند و ارتباطی به نام `origin` برای مخزن راه دور می سازد.

## ۵ مشاهده وضعیت فایل ها

git status

این دستور نشان می دهد کدام فایل ها تغییر کرده اند، کدام فایل ها برای Commit آماده شده اند و در حال حاضر روی کدام Branch قرار دارید.

## ۶ آماده سازی تغییرات با Add

برای قرار دادن یک فایل در بخش Stage:

git add basic-commands.md

برای آماده سازی همه تغییرات پوشه فعلی:

git add .

مرحله Stage به شما اجازه می دهد مشخص کنید کدام تغییرات در Commit بعدی ثبت شوند.

## ۷ ثبت تغییرات با Commit

git commit -m "Add basic Git command documentation"

هر Commit یک نقطه ثبت شده در تاریخچه پروژه است. پیام Commit باید کوتاه، دقیق و مرتبط با تغییرات باشد. برای مثال:

Add Git installation instructions
Explain clone and status commands
Add examples for staging and committing

## ۸ مشاهده تاریخچه

git log

نمایش خلاصه هر Commit:

git log --oneline

نمایش تاریخچه به صورت نمودار شاخه ها و ادغام ها:

git log --oneline --graph --decorate --all

## ۹ ارسال تغییرات با Push

برای ارسال Branch به مخزن GitHub:

git push -u origin docs/your-name-basic-commands

در این مثال `origin` نام مخزن و بخش آخر نام Branch است. گزینه `-u` ارتباط Branch محلی با Branch راه دور را برای Pushهای بعدی تنظیم می کند. پس از آن معمولاً می توان از دستور ساده تر زیر استفاده کرد:

git push

## ۱۰ دریافت تغییرات با Fetch و Pull

دریافت اطلاعات جدید از مخزن راه دور بدون ادغام آن ها در Branch فعلی:

git fetch origin

دریافت تغییرات Branch اصلی و ادغام آن ها در Branch فعلی (ابتدا روی `main` قرار بگیرید):

git switch main
git pull origin main

تفاوت مهم: `fetch` اطلاعات جدید را دریافت می کند اما به تنهایی فایل های Branch فعلی را تغییر نمی دهد. `pull` ابتدا اطلاعات را دریافت و سپس آن ها را در Branch فعلی ادغام می کند.

## ۱۱ لغو Stage یا کنار گذاشتن تغییرات

خارج کردن یک فایل از Stage بدون حذف تغییرات داخل آن:

git restore --staged basic-commands.md

بازگرداندن تغییرات ذخیره نشده یک فایل به آخرین وضعیت ثبت شده:

git restore basic-commands.md

هشدار: دستور دوم تغییرات ذخیره نشده آن فایل را حذف می کند. پیش از اجرای آن مطمئن شوید به تغییرات نیاز ندارید.

## جمع بندی کار 

git status
git add filename.md
git commit -m "Describe the change"
git push

