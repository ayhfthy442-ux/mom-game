# بيتنا الصغير — تطبيق أندرويد

لعبة الأم والبيبي «بيتنا الصغير» كاملة (ملف HTML واحد، أوفلاين) ملفوفة في
تطبيق أندرويد. نفس طريقة «مطبخ البنات»: GitHub Actions بتبني الـ APK على كل
دفعة إلى `main` وتنشره في وسم `latest`.

## رابط الإصدار

    https://github.com/ayhfthy442-ux/mom-game/releases/tag/latest

الرابط ثابت — أي نسخة جديدة تحل مكان الـ APK في نفس الصفحة.

## التثبيت

افتحي الرابط من الموبايل ← قسم **Assets** ← `app-debug.apk` ← نزّليه وثبّتيه.
لو الموبايل سأل عن السماح بالتثبيت من مصدر غير معروف، اسمحي.

## التحديث

عدّلي `app/src/main/assets/index.html` وارفعيه تاني، وزوّدي `versionCode`
و`versionName` في `app/build.gradle`. الـ Actions هتبني من جديد وتنشر في نفس
`latest`.

## بنية المشروع

- `app/src/main/assets/index.html` — اللعبة نفسها (ملف واحد، كله أوفلاين).
- `app/src/main/java/com/aya/momgame/MainActivity.java` — شاشة WebView بتفتح
  الصفحة من داخل التطبيق (مش من النت).
- `.github/workflows/build-apk.yml` — البناء والنشر التلقائي.

## ملاحظة

الحفظ بيتم في ذاكرة التطبيق (localStorage) وبيتبقي بين مرات الفتح ولو
قفلتي الموبايل. مسح بيانات التطبيق من إعدادات الأندرويد بيمسح الحفظ.
