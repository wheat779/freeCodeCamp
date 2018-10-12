---
title: Git Behind a Proxy Server
localeTitle: بوابة وراء خادم وكيل
---
**استخدم حالات**

قد تحتاج إلى تعديل أوامر `git` التي تصل إلى المستودعات البعيدة (للتحديث والقراءة من) إذا كان الدخول إلى الإنترنت من خلال [خادم وكيل](https://en.wikipedia.org/wiki/Proxy_server) .

تُعد خوادم الوكيل شائعة في البيئات من نوع الكلية والأعمال.

يمكنك [تحديد إعدادات الخادم الوكيل](http://www.wikihow.com/Change-Proxy-Settings) من لوحة إعدادات المتصفح.

## باستخدام بروكسي مع جيت

بمجرد الحصول على إعدادات الوكيل (عنوان URL الخادم والمنفذ واسم المستخدم وكلمة المرور) ؛ تحتاج إلى تكوين بوابة الخاص بك على النحو التالي:

 `$ git config --global http.proxy http://<username>:<password>@<proxy-server-url>:<port> 
` 

ستحتاج إلى استبدال `<username>` و `<password>` و `<proxy-server-url>` و `<port>` بالقيم الخاصة ببيانات اعتماد الخادم الوكيل. هذه الحقول اختيارية. على سبيل المثال ، قد لا يتطلب الخادم الوكيل الخاص بك `<username>` و `<password>` ، أو ربما يعمل على المنفذ 80 (وفي هذه الحالة ، لا يكون `<port>` مطلوبًا).

وبمجرد الانتهاء من ضبطها ، فإن `git pull` `git push` أو `git push` أو حتى `git fetch` سيعمل بشكل صحيح.

## متى لا تستخدم

لا يجب عليك استخدام أوامر `git` مع إعدادات الوكيل ، في حالة حدوث أي مما يلي

*   لا يسمح لك مسؤول النظام أو سياسة الشركة بالدخول إلى مستودعات `git` البعيدة من GitHub و BitBucket إلخ.
*   مستودع التخزين البعيد غير موجود في جهازك ، ولكنه موجود داخل الشبكة الداخلية. مثال على GitLab تم نشره داخليًا في شركتك هو مثال جيد.

## غير إعدادات الوكيل

استخدم مناقشة Stack Overflow [هذه](http://stackoverflow.com/questions/11499805/git-http-proxy-setting) لإلغاء تعيين إعدادات الوكيل.

## مصادر

يمكنك استخدام ما يلي لمزيد من القراءة حول هذا:

*   [هل يمكنني تسجيل الدخول خلف خادم وكيل](https://help.github.com/desktop/faq/articles/can-i-log-in-behind-a-proxy-server/#platform-windows)
*   [Git Config](https://git-scm.com/docs/git-config)