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
2. بينفتح **واتساب** برسالة جاهزة فيها كل تفاصيل الزبون → بتوصلك فورًا على تلفونك.
3. بيظهر للزبون تأكيد إنه الطلب انبعث.

في كمان honeypot ضد البوتات (حقل مخفي `company_website`).

### إذا بدك الطلبات تيجي عالميل أوتوماتيكيًا (بدون واتساب)

1. افتح حساب مجاني على [formspree.io](https://formspree.io) واربطه بـ `nexora131415@gmail.com`.
2. خد الـendpoint (شكله `https://formspree.io/f/xxxxxxxx`).
3. بملف `index.html`، بآخر الملف، حطه هون:

```js
const CFG = {
  phoneIntl: "972523674478",
  email: "nexora131415@gmail.com",
  formEndpoint: "https://formspree.io/f/xxxxxxxx"   // ← هون
};
```

وقتها الطلب بينبعث عالميل مباشرة، وإذا فشل الإرسال بيرجع أوتوماتيكيًا لطريقة الواتساب.

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
