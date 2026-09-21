# Nexora — موقع الشركة

موقع تعريفي بالعبرية (RTL) لـ **Nexora** — Marketing · Advertising · Web Development.

```
nexora-site/
├─ index.html                     ← الموقع كامل (صفحة واحدة، بدون build)
└─ assets/
   ├─ nexora-logo.png             ← اللوجو الأصلي (خلفية سوداء)
   └─ nexora-logo-alpha.png       ← نفس اللوجو بخلفية شفافة (المستخدم بالموقع)
```

## معلومات التواصل الموجودة بالموقع

| | |
|---|---|
| تلفون | 052-367-4478 (`tel:+972523674478`) |
| واتساب | `https://wa.me/972523674478` |
| ميل | nexora131415@gmail.com |
| إنستغرام | [@nextora.production](https://www.instagram.com/nextora.production/) |

لتغيير أي إشي منهم: كلهم موجودين بأول الـ`<script>` بآخر الملف تحت `CFG`، وكمان بقسم "צרו קשר" وبالـfooter.

## كيف بيشتغل فورم "اتركوا تفاصيلكم"

الزبون بيعبّي: اسم (إجباري)، تلفون و/أو ميل (لازم واحد منهم على الأقل)، نوع المشروع، ورسالة.

بعد الضغط على **שליחת הפרטים**:
1. بيصير فحص للبيانات (رسائل الخطأ بالعبرية).
2. التفاصيل بتنبعث **أوتوماتيكيًا عالميل `nexora131415@gmail.com`** عن طريق [FormSubmit](https://formsubmit.co) (مجاني، بدون سيرفر).
   - الموضوع: `פנייה חדשה מהאתר — <اسم الزبون>`، والتفاصيل بجدول.
   - إذا الزبون كتب ميل، بتكبس **Reply** بالجيميل والرد بيروح لإله مباشرة.
3. بيظهر للزبون تأكيد إنه الطلب انبعث. إذا فشل الإرسال بتطلعله رسالة خطأ مع الميل.

في كمان honeypot ضد البوتات (حقل مخفي `company_website`).

### تفعيل لمرة وحدة
أول مرة بينبعث فيها طلب، FormSubmit بيبعت لـ`nexora131415@gmail.com` ميل **"Action Required: Activate FormSubmit"**. لازم تكبس **Activate Form** فيه — وبعدها كل الطلبات بتوصل عالميل. (الطلبات اللي بتنبعث قبل التفعيل ما بتوصل.)

الـendpoint موجود بآخر `index.html`:

```js
formEndpoint: "https://formsubmit.co/ajax/nexora131415@gmail.com"
```

## تشغيل محلي

```bash
npx serve nexora-site
```

## النشر على Vercel

```bash
npx vercel --cwd "nexora-site" --prod
```

الموقع static بالكامل — ما في build ولا dependencies.

## ملاحظات تقنية

- الخطوط: Heebo + Space Grotesk من Google Fonts.
- الألوان مأخوذة من اللوجو: بنفسجي `#8B5CF6` → أزرق `#3B82F6` على خلفية `#07070C`.
- متجاوب من 360px وفوق، بدون scroll أفقي.
- فيه Schema.org (ProfessionalService) + Open Graph للمشاركة.
- كل النصوص بالـHTML مباشرة — بتقدر تعدّلها بأي محرر نصوص.
