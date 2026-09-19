[English](./README.md) · **العربية**

# 🛒 KitchenShop (رَحْمَة) - تطبيق تجارة إلكترونية

<div align="center">
  <p>تطبيق تجارة إلكترونية جاهز للإنتاج، مُصمّم بعناية، موجّه للعرب في المقام الأول، مبنيّ بلغة Flutter.</p>
  <p>
    <strong>Offline-First • مزامنة ذكية • إتمام طلب عبر واتساب • أداء فائق التحسين</strong>
  </p>
</div>

---

> 🔒 **ملاحظة:** كود المصدر لهذا المشروع مملوك وغير مفتوح المصدر لأنه طُوّر لعميل خاص. يعمل هذا المستودع كعرض بورتفوليو للمعمارية والميزات وواجهة المستخدم فقط.

---

## 🎥 عروض فيديو

### شاشات الترحيب والإشعارات المخصّصة
<div align="center">
  <img src="screenshots/video.gif" width="250" alt="عرض توضيحي لشاشات الترحيب والإشعارات المخصصة" />
</div>

---

## 📸 لقطات الشاشة

<div align="center">
  <img src="screenshots/main%20home%20page.jpg" width="30%" alt="الصفحة الرئيسية" />
  <img src="screenshots/category.jpg" width="30%" alt="التصنيفات" />
  <img src="screenshots/product%20screen.jpg" width="30%" alt="شاشة المنتج" />
</div>

<br>

<div align="center">
  <img src="screenshots/order%20page%20to%20fnish%20ordering.jpg" width="30%" alt="سلة / صفحة الطلب" />
  <img src="screenshots/image%20of%20the%20order%20canva%20generated%20by%20the%20app.jpg" width="30%" alt="إيصال مولّد عبر Canvas" />
  <img src="screenshots/fav%20produts.jpg" width="30%" alt="المنتجات المفضلة" />
</div>

<br>

<div align="center">
  <img src="screenshots/get%20notification%20and%20go%20right%20away%20to%20the%20prodcut.jpg" width="30%" alt="الإشعارات الفورية" />
  <img src="screenshots/nice%20images%20and%20videos%20of%20the%20product.jpg" width="30%" alt="صور وفيديوهات المنتج" />
  <img src="screenshots/order%20a%20prodcut%20by%20demnad.jpg" width="30%" alt="طلبات مخصصة" />
</div>

---

## 🌟 نظرة عامة

KitchenShop تطبيق تجارة إلكترونية متكامل صُمّم خصيصًا للمستخدمين الناطقين بالعربية. يعتمد على معمارية **Feature-First** صارمة، باستخدام إمكانيات Flutter الحديثة، و **Riverpod** لإدارة حالة قابلة للتنبؤ، و **Supabase** لعمليات الخلفية، و **Hive CE** لتخزين مؤقت محلي فائق السرعة.

هذا المشروع ليس مجرد تطبيق تسوق آخر؛ بل مُهندِس بعناية فنية عميقة لتحقيق **الأداء**، و**إتاحة الوصول دون اتصال**، و**حلول إبداعية للمشكلات** (مثل تدفق إنهاء الطلب المميز عبر WhatsApp-Canvas).

---

## 🧠 الميزات "الذكية" (ما الذي يجعل هذا التطبيق مميزًا)

### 📦 1. وحدة المنتجات: مزامنة ذكية Offline-First
بدلًا من جلب قاعدة البيانات كاملة عند كل تشغيل، يستخدم التطبيق استراتيجية **Delta Sync** عالية التحسين:
* **أول تشغيل**: "مزامنة كاملة" تحمّل كل المنتجات وتخزّنها محليًا باستخدام Hive.
* **التشغيلات التالية**: يقوم التطبيق بـ"مزامنة تفاضلية" (Delta Sync)، حيث يرسل `last_sync_time` إلى Supabase ويحمّل *فقط* المنتجات التي أُضيفت أو عُدّلت أو حُذِفت بذكاء منذ آخر جلسة.
* **الرجوع دون اتصال**: إذا لم تتوفر شبكة إنترنت، تعود الواجهة فورًا إلى الكاش المحلي في Hive، ليبقى التطبيق سريعًا ومتاحًا دائمًا.
* **الحذف الناعم**: العناصر المعلّمة بـ `isDeleted` في الخلفية تُزال صامتةً من الكاش المحلي، مما يمنع فوضى الواجهة دون عمليات قاعدة بيانات ثقيلة.

### 💳 2. السلة وإتمام الطلب: الإيصال المرئي عبر واتساب
بوابات الدفع التقليدية ثقيلة ومكلفة للشركات الصغيرة. يتجاوز KitchenShop هذا تمامًا بنهج "التواصل المباشر مع التاجر" البسيط والعبقري:
* **الرسم عبر Canvas**: باستخدام `Canvas` في Flutter، يجمّع `OrderImageGenerator` محتوى سلة المستخدم في **صورة** إيصال منسّقة وجميلة تبدو كإيصال حقيقي.
* **التكامل مع واتساب**: يلتقط `WhatsAppOrderService` هذه الصورة عالية الجودة ويفتح محادثة واتساب مباشرةً مع التاجر. لا حاجة لبنية معقدة لإتمام الدفع — فقط قناة مبيعات مرئية مباشرة وفعّالة.

### 3. تكامل الإشعارات الفورية
* **Firebase Cloud Messaging (FCM)** يبقي المستخدمين على تواصل مع تحديثات فورية عن المنتجات الجديدة أو الخصومات الترويجية.
* يتم تحليل إشعارات الخلفية والأمامية بدقة لإيقاظ التطبيق وتوجيه المستخدم بسلاسة دون تعطيل سلسلة رسم الواجهة.

### 🔍 4. البحث: تطبيع عربي واعٍ بالثقافة
البحث بالعربية قد يكون صعبًا بسبب التشكيل (التشكيل) وتغيّر أشكال الحروف (مثل أ، إ، ا).
* **مطبِّع عربي**: أداة مخصّصة تزيل التشكيل وتطبّع الأحرف العربية في الزمن الفعلي، ليصل المستخدم لما يبحث عنه بسلاسة مهما كانت طريقة كتابته.
* **ترشيح ضبابي**: يرشّح المنتجات فورًا من الكاش المحلي في Hive لنتائج بحث بلا تأخير.
* **عمليات بحث حديثة**: يحتفظ بسجلّ البحث محليًا لتجربة مستخدم أفضل.

### 🏠 5. الرئيسية والواجهة: عرض واعٍ بالتمرير
لوحة التحكم مليئة بالكروت والأنماط البصرية الجذابة، لكنها تعمل بسلاسة كاملة عند 60/120 إطارًا في الثانية.
* **رسوم متحركة تتوقف عند التمرير**: عبر `NotificationListener<ScrollNotification>` عام، تُوقَف العمليات الثقيلة (مثل شرائح الكاروسيل التي تعمل تلقائيًا) أثناء تمرير المستخدم، لتحرير سلسلة الرسم.
* **قائمة جانبية بتحميل كسول**: القائمة المعقدة `AdvancedDrawer` ليست مجرد إخفاء؛ بل تُفصل تمامًا من شجرة الـ Widgets عند إغلاقها، فلا تحمل أي عبء رسم في الخلفية.
* **تجاوز العناصر غير المرئية**: مكوّنات `SliverPersistentHeader` التي تختفي عند التمرير تتجاوز صراحةً مراحل الـ layout والـ build بمجرد وصول الشفافية إلى الصفر.

### ❤️ 6. المفضلة وتسجيل الدخول والترحيب
* **المفضلة (حالة مشتقة محفوظة):** مزوّد `@riverpod` مخصّص يعمل كوسيط لمنطق المفضلة ويحسب التقاطعات محليًا، لتفادي تراجع الأداء الذي كانت تسبّبه الفلاتر على مستوى `build()`.
* **ترحيب منسّق:** شاشات البداية ترشد المستخدمين الجدد بسلاسة قبل تخزين تفضيلاتهم الأولية عبر طبقات الكاش.
* **مصادقة مدمجة:** تسجيل دخول آمن ومرن عبر مزوّدين متعددين تُنفّذه بنية Firebase.

---

## 🛠 تقنيات البنية والمعمارية

* **الإطار:** Flutter (Dart)
* **إدارة الحالة:** Riverpod 3.0 (`AsyncNotifier` و `Notifier`)
* **الخلفية:** Supabase (قاعدة البيانات وواجهات API) و Firebase (المصادقة والرسائل السحابية)
* **التخزين المحلي:** Hive CE (حفظ البيانات دون اتصال)
* **الواجهة:** `flutter_screenutil` (تصميم متجاوب) و `flutter_animate` (تفاعلات دقيقة)
* **المعمارية:** Feature-First بمعايير Clean Architecture.

### 🗂 هيكل المشروع الكامل
```text
lib/
├── core/
│   ├── animation_extensions.dart
│   ├── config.dart
│   ├── constants/
│   │   └── app_constants.dart
│   ├── network/
│   │   ├── http_overrides_io.dart
│   │   └── http_overrides_stub.dart
│   ├── providers/
│   │   ├── app_contacts_provider.dart
│   │   ├── hive_provider.dart
│   │   ├── notification_provider.dart
│   │   ├── repo_provider.dart
│   │   └── supabase_provider.dart
│   ├── services/
│   │   ├── notification_service.dart
│   │   ├── order_image_generator.dart
│   │   └── whatsapp_order_service.dart
│   ├── theme/
│   │   ├── app_colors.dart
│   │   └── app_theme.dart
│   └── utils/
│       ├── deep_link_handler.dart
│       └── whatsapp_helper.dart
├── features/
│   ├── account/
│   │   ├── account_screen.dart
│   │   ├── customer_requests/
│   │   │   ├── data/
│   │   │   │   ├── customer_profile_model.dart
│   │   │   │   ├── customer_request_model.dart
│   │   │   │   ├── customer_requests_provider.dart
│   │   │   │   └── customer_requests_service.dart
│   │   │   └── presentation/
│   │   │       ├── screens/
│   │   │       │   └── my_requests_screen.dart
│   │   │       └── widgets/
│   │   │           ├── customer_profile_form.dart
│   │   │           ├── new_request_bottom_sheet.dart
│   │   │           └── request_card.dart
│   │   └── favorites/
│   │       ├── data/
│   │       │   ├── favorites_provider.dart
│   │       │   └── favorites_service.dart
│   │       └── presentation/
│   │           └── screens/
│   │               └── favorites_screen.dart
│   ├── auth/
│   │   ├── data/
│   │   │   ├── auth_provider.dart
│   │   │   └── auth_service.dart
│   │   └── presentation/
│   │       └── widgets/
│   │           └── sign_in_bottom_sheet.dart
│   ├── cart/
│   │   ├── data/
│   │   │   ├── cart_provider.dart
│   │   │   └── models/
│   │   │       ├── cart_item_model.dart
│   │   │       └── cart_item_model.g.dart
│   │   └── presentation/
│   │       └── screens/
│   │           └── cart_screen.dart
│   ├── categories/
│   │   ├── data/
│   │   │   ├── apis/
│   │   │   │   └── category_api.dart
│   │   │   ├── models/
│   │   │   │   ├── category_model.dart
│   │   │   │   └── category_model.g.dart
│   │   │   └── repos/
│   │   │       └── category_repo.dart
│   │   └── presentation/
│   │       ├── providers/
│   │       │   └── category_provider.dart
│   │       ├── screens/
│   │       │   ├── categories_screen.dart
│   │       │   └── category_products_screen.dart
│   │       └── widgets/
│   │           ├── category_card.dart
│   │           └── category_grid.dart
│   ├── home/
│   │   ├── data/
│   │   │   ├── apis/
│   │   │   │   └── banner_api.dart
│   │   │   ├── models/
│   │   │   │   ├── banner_model.dart
│   │   │   │   ├── banner_model.g.dart
│   │   │   │   └── nav_item.dart
│   │   │   └── repos/
│   │   │       └── banner_repo.dart
│   │   └── presentation/
│   │       ├── providers/
│   │       │   └── banner_provider.dart
│   │       ├── screens/
│   │       │   └── home_screen.dart
│   │       ├── sections/
│   │       │   ├── discounted_section.dart
│   │       │   ├── new_arrivals_section.dart
│   │       │   ├── section_screen.dart
│   │       │   └── section_widget.dart
│   │       └── widgets/
│   │           ├── advanced_drawer_content.dart
│   │           ├── banner_widget.dart
│   │           ├── floating_nav_bar.dart
│   │           └── silverheader_widget.dart
│   ├── main_screen.dart
│   ├── onboarding/
│   │   ├── data/
│   │   │   └── repo/
│   │   │       └── onborading_repo.dart
│   │   └── presentation/
│   │       └── screens/
│   │           ├── loading_screen.dart
│   │           ├── onboarding1_screen.dart
│   │           ├── onboarding2_screen.dart
│   │           ├── onboarding3_screen.dart
│   │           ├── onboarding_notification_screen.dart
│   │           └── onboarding_tree.dart
│   ├── product/
│   │   ├── data/
│   │   │   ├── apis/
│   │   │   │   └── product_api.dart
│   │   │   ├── models/
│   │   │   │   ├── product_model.dart
│   │   │   │   └── product_model.g.dart
│   │   │   └── repos/
│   │   │       └── product_repo.dart
│   │   └── presentation/
│   │       ├── providers/
│   │       │   └── product_provider.dart
│   │       ├── screens/
│   │       │   └── product_screen.dart
│   │       └── widget/
│   │           ├── product_card.dart
│   │           └── product_grid.dart
│   └── search/
│       ├── data/
│       │   ├── recent_searches_service.dart
│       │   └── search_service.dart
│       ├── presentation/
│       │   ├── screens/
│       │   │   └── product_search_delegate.dart
│       │   └── widgets/
│       │       └── product_search_results.dart
│       └── utils/
│           └── arabic_normalizer.dart
├── firebase_options.dart
├── hive_registrar.g.dart
└── main.dart
```

---

## ⚡ إنجازات الأداء

نعتبر التقطُّع (Jank) خطأً. إليك كيف يحافظ KitchenShop على تمريرٍ سلسٍ كالحرير:
1. **تحديد نطاق الـ Providers بدقة:** تُبقى مُستمعات الحالة العامة (مثل تهيئة FCM) خارج الأشجار القابلة للتمرير.
2. **استخدام مكثّف لـ `RepaintBoundary`:** الرسوم الدقيقة (مثل قلب الإعجاب أو إضافة إلى السلة) تستخدم `RepaintBoundary` بقوة حتى لا تسبب إعادة رسم لعرض التمرير كاملًا.
3. **Slivers في كل مكان:** اعتماد كامل على `CustomScrollView` و `SliverGrid` والقوائم ذات التحميل الكسول بدلًا من ScrollViews التقليدية للشاشات المعقدة متعددة الأقسام.

---

<div align="center">
  <i>صُنع بشغف للأداء وكود أنيق وتجارب مستخدم سلسة.</i>
</div>