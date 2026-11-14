# کار با Branch در Git

## ۱ Branch چیست؟

Branch  یا شاخه مسیر مستقلی برای توسعه و ثبت تغییرات است. اعضای تیم می توانند هرکدام روی Branch جداگانه کار کنند. بنابراین تغییرات آن ها تا زمان ادغام از Branch اصلی جدا می ماند.

در این پروژه `main` شاخه اصلی است و هر عضو باید برای وظیفه خود Branch جداگانه ای بسازد.

## ۲ مشاهده Branchها

git branch

Branch فعلی با علامت `*` مشخص می شود. برای مشاهده Branchهای محلی و راه دور:

git branch -a

## ۳ به روزرسانی main پیش از ساخت Branch

ابتدا مطمئن شوید تغییرات جدید مخزن اصلی را دریافت کرده اید:

git switch main
git pull origin main

## ۴ ساخت و ورود به Branch جدید

برای ساخت Branch و جابه جایی به آن:

git switch -c docs/your-name-branching

نام Branch بهتر است هدف آن را مشخص کند. چند نمونه:

docs/basic-commands
 docs/branching
 docs/merging
 docs/collaboration

از فاصله در نام Branch استفاده نکنید.

## ۵ جابه جایی بین Branchها

git switch main
git switch docs/your-name-branching

پیش از جابه جایی وضعیت فایل ها را با `git status` بررسی کنید و تغییرات مهم را Commit کنید یا به شکل امن نگه دارید.

## ۶ ارسال Branch به GitHub

پس از ایجاد حداقل یک Commit Branch را به مخزن راه دور ارسال کنید:

git push -u origin docs/your-name-branching

پس از این کار Branch شما در GitHub نیز قابل مشاهده است.

## ۷ ادامه کار روی Branch

پس از تغییر فایل:

git status
git add branching.md
git commit -m "Explain Git branching workflow"
git push

## ۸ هماهنگ کردن Branch با main

اگر در زمان کار شما تغییرات دیگری وارد `main` شد می توانید آن ها را به Branch خود منتقل کنید. ابتدا اطلاعات راه دور را دریافت و سپس `main` را در Branch کاری ادغام کنید:

git fetch origin
git switch docs/your-name-branching
git merge origin/main

ممکن است این ادغام بدون تعارض انجام شود یا نیاز به حل Merge Conflict داشته باشد. روش حل تعارض در فایل (merging.md) توضیح داده شده است.

## ۹ حذف Branch پس از ادغام

پس از اینکه Pull Request ادغام شد و دیگر به Branch نیاز ندارید، می توانید نسخه محلی آن را حذف کنید:

git switch main
git pull origin main
git branch -d docs/your-name-branching

حذف Branch محلی با حذف تاریخچه Commitهای ادغام شده یکسان نیست. Commitهای ادغام شده در تاریخچه مخزن باقی می مانند.
