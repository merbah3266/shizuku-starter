## اللغات

- [English](README.md)  
- العربية


<h1 align="center">مشغل Shizuku التلقائي</h1>

### ما الذي تقوم به هذه الوحدة؟

تقوم هذه الوحدة بتشغيل **Shizuku** تلقائيًا عند إقلاع الجهاز.  
لا حاجة لفتح التطبيق أو تنفيذ أوامر يدويًا.

### ما هو هذا المشروع؟

وحدة بسيطة مبنية باستخدام **Shell**. عند تثبيتها، تقوم تلقائيًا بتشغيل `service.sh` بعد كل إعادة تشغيل للجهاز.  
يبحث السكربت عن `libshizuku.so` (الخاص بتطبيق Shizuku) ويقوم بتنفيذه.

### كيف تعمل؟

1. ينتظر إقلاع النظام بالكامل.
2. ينتظر 5 ثوانٍ إضافية.
3. يبحث عن `libshizuku.so` داخل `/data/app/`.
4. إذا وُجد:
   - يمنحه صلاحية التنفيذ.
   - يقوم بتنفيذه.
5. يسجل كل شيء في `shizuku_exec.log`.

### المتطلبات

- جهاز أندرويد بصلاحيات root  
- تطبيق Shizuku مثبت

### تم اختباره على

- Redmi Note 11 SE (مروّت باستخدام Magisk)

### ملاحظات مهمة

- تم اختباره فقط على **Magisk**
- لا أضمن عمله على **KernelSU** أو **APatch** أو أي بيئة مخصصة أخرى
- استخدامه خارج Magisk على مسؤوليتك الخاصة

### ملفات الوحدة

| الملف               | الوصف                                  |
|---------------------|-----------------------------------------|
| `service.sh`        | السكريبت الأساسي – يعمل تلقائيًا بعد الإقلاع |
| `shizuku_exec.log`  | ملف السجل – يُنشأ تلقائيًا              |
| `module.prop`       | ملف التعريف الخاص بوحدة Magisk         |
> [!WARNING]
> استخدامك لهذه الوحدة يتم على **مسؤوليتك الخاصة بالكامل**.  
> لا يتحمل المطوّر أي ضرر قد يصيب جهازك أو بياناتك نتيجة الاستخدام الخاطئ أو غير المدعوم.
