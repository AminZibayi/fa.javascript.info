# حالت مدرن، “use strict”

برای مدتی طولانی جاوا اسکریپت بدون مشکل سازگار پذیری توسعه داده می‌شد و امکانات جدید بدون اینکه نیازی به تغییر در امکانات قبلی باشد، به این زبان اضافه می‌شد.

مزیت این موضوع در این بود که هیچگاه در کدهای قدیمی اشکالی بوجود نمی‌آمد. اما مشکل اینجا بود که اگر اشکالی در طراحی زبان، توسط خالقان جاوا اسکریپت رخ داده بود، تا ابد بجا می‌ماند.

<<<<<<< HEAD
این موضوع تا سال 2009 که ECMAScript 5 (ES5) معرفی شد، ادامه داشت.ES5 قابلیت‌های جدیدی را به زبان افزود و اصلاحاتی را نیز بر روی امکانات فعلی انجام داد. 

به منظور اینکه کدهای قدیمی کار کنند، بیشتر تغییراتی که در ES5 اتفاق افتاد، به صورت پیش‌فرض غیر فعال است، و برای فعال‌سازی آنها باید از طریق عبارت `"use strict"` چنین کاری را انجام داد.
=======
This was the case until 2009 when ECMAScript 5 (ES5) appeared. It added new features to the language and modified some of the existing ones. To keep the old code working, most such modifications are off by default. You need to explicitly enable them with a special directive: `"use strict"`.
>>>>>>> 34e9cdca3642882bd36c6733433a503a40c6da74

## "use strict"

عبارتِ دستوریِ (directive) `"use strict"` یا `'use strict'` شبیه به یک رشته است که زمانیکه در ابتدای اسکریپت قرار می‌گیرد، تمام اسکریپت در حالت مدرن کار خواهد کرد.
برای نمونه :


```js
"use strict";

// this code works the modern way
...
```

<<<<<<< HEAD
در مورد فانکشِن‌ها (روشی برای گروه‌بندی کردن دستورات) در آینده خواهیم آموخت. 

در اینجا صرفا بدانید که می‌توانیم در ابتدای اکثر فانکشن‌ها `"use strict"` قرار دهیم تا قواعد مدرن صرفا بر روی کدهای داخل فانکشن اعمال شوند.
=======
We will learn functions (a way to group commands) soon. Looking ahead, let's note that `"use strict"` can be put at the start of most kinds of functions instead of the whole script. Doing that enables strict mode in that function only. But usually, people use it for the whole script.
>>>>>>> 34e9cdca3642882bd36c6733433a503a40c6da74


````warn header="از بالا بودن عبارت \"use strict\" در کدهای خود مطمئن شوید"

این عبارت حتما باید در ابتدای اسکریپت شما باشد، در غیر این صورت حالت مدرن فعال نخواهد شد.
Strict mode در اینجا فعال نیست :

```js no-strict
alert("some code");
// "use strict" below is ignored--it must be at the top

"use strict";

// strict mode is not activated
```

فقط Comment ها می‌توانند در بالای `"use strict"` قرار گیرند..
````

```warn header="هیچ راه برای خنثی کردن `use strict` وجود ندارد"
هیچ دستوری مانند `no use strict` وجود ندارد تا به موتور جاوا اسکریپت دستور دهد به روش قدیمی کار کند.
زمانی‌که `use strict` را قرار می‌دهیم، راه برگشتی وجود ندارد.

```

## کنسول مرورگر

در ادامه کار زمانیکه از کنسول مرورگر خود برای اجرای کدها استفاده می‌کنید در نظر داشته باشید که این کنسول به طور پیش فرض از `use strict` استفاده نمی‌کند.
گاهی اوقات زمانیکه وجود `use strict` تفاوتی ایجاد می‌کند، استفاده از کنسول مرورگر نتایج اشتباهی به شما خواهد داد.
حتی اگر از `key:Shift+Enter` برای وارد کردن عبارت `use strict` استفاده نمایید، نتیجه نخواهد داد.

راه حل قابل اتکا برای این موضوع آن است که به این شکل عبارت `use strict` را وارد نمایید :

```js
(function() {
  'use strict';

  // ...your code...
})()
```

## همیشه از "use strict" استفاده کنید

ما همچنان باید به آموختن تفاوت‌های use strict و default mode ادامه دهیم.

در بخش‌های بعدی که با قابلیت‌های زبان جاوا اسکریپت آشنا می‌شویم، به تفاوت‌های بین strict mode و "default" mode اشاره خواهیم کرد و خواهیم دید که use strict چطور زندگی ما را راحت‌تر کرده است.

تا به اینجا کافیست بدانید :


1. عبارت `"use strict"` باعث فعال شدن حالت مدرن موتور جاوا اسکریپت می‌شود و رفتار برخی قابلیت‌های درونی موتور را تغییر می‌دهد.
2. این حالت با قرار دادن رشته `"strict mode"` در ابتدای اسکریپت یا فانکشن فعال می‌شود. برخی قابلیت‌های زبان از جمله "class" ها و "module" ها به صورت خودکار use strict را فعال می‌کنند.
3. Use strict توسط اکثر مرورگرهای مدرن پشتیبانی می‌شود.
4. ما توصیه می‌کنیم تا همیشه از `"use strict"` استفاده کنید. تمام مثال‌های این آموزش‌ها با `"use strict"` فعال انجام می‌شوند (مگر در موارد استثنایی که ذکر خواهند شد).
