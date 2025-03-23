# Next.js Eğitim Dokümantasyonu

## İçindekiler

- [1. Önemli Teorik Bilgiler](#-1-önemli-teorik-bilgiler)
- [2. Next.js Kurulumu](#-2-nextjs-kurulumu)
- [3. Temel Bir Component Oluşturmak](#-3-temel-bir-component-oluşturmak)
- [4. Routing İşlemleri](#-4-routing-işlemleri)
- [5. Hata Sayfası Oluşturma](#-5-hata-sayfası-oluşturma)
- [6. Dosya Yapısı (File Convention)](#-6-dosya-yapısı-file-convention)
- [7. Navigation İşlemleri](#-7-navigation-işlemleri)
- [8. Metadata İşlemleri](#-8-metadata-işlemleri)
- [9. Error Handling (Hata Yönetimi)](#-9-error-handling-hata-yönetimi)
- [10. Paralel Rotalar](#-10-paralel-rotalar)
- [11. Route Handlers (API Rotaları Yönetimi)](#-11-route-handlers-api-rotaları-yönetimi)
- [12. Önemli Yapılar](#-12-önemli-yapılar)

---

## 📌 Next.js Eğitim Dokümantasyonu

### 🚀 1. Önemli Teorik Bilgiler

**Kısa Açıklama:** Bu bölümde Next.js'in ne olduğu, React ile farkları, SSR ve CSR kavramlarının avantajları, ayrıca Client Side Components (CSC) ve Server Side Components (SSC) ayrımı hakkında temel bilgiler edineceksiniz.

Next.js, React tabanlı uygulamalar oluşturmak için kullanılan popüler bir framework'tür. Hem statik web siteleri (SSG) hem de sunucu taraflı render işlemleri (SSR) için güçlü araçlar sunar. Next.js, SEO optimizasyonu, yüksek performans ve hızlı geliştirme süreçleri sağlayarak React uygulamalarını daha verimli hale getirir.

- 🔹 **Framework vs Library:**

  - 📚 **Library:** Belirli görevleri yerine getiren hazır fonksiyon ve metodlar bütünüdür. Örneğin React, UI oluşturmak için bileşen tabanlı bir yapı sunar ancak uygulamanın genel yapısına karışmaz.
  - 🔧 **Framework:** Uygulama geliştirme sürecinde belirli standartlar ve kurallar sağlayarak uygulamanın akışını kontrol eder. Next.js, React uygulamalarının nasıl yapılandırılacağını belirler ve geliştiricilere net bir yol haritası sağlar.

- 🔹 **SSR ve CSR:**

  - 🌐 **Server Side Rendering (SSR):** İçerikler sunucu tarafında HTML olarak hazırlanıp kullanıcıya gönderilir. Bu, SEO için avantajlıdır ve ilk yükleme hızını artırır.
  - 💻 **Client Side Rendering (CSR):** İçerikler kullanıcı tarafında JavaScript kullanılarak oluşturulur. Bu yöntem, dinamik ve interaktif uygulamalar için uygundur.

- 🔹 **CSC ve SSC:**
  - 🎛️ **Client Side Components (CSC):** Kullanıcı etkileşimine bağlı dinamik bileşenlerdir (formlar, butonlar, interaktif tablolar gibi).
  - 📃 **Server Side Components (SSC):** Statik veya SEO amaçlı içeriklerin sunucu tarafında oluşturulduğu bileşenlerdir (bloglar, makaleler, ürün açıklamaları gibi).

---

### 🔧 2. Next.js Kurulumu

**Kısa Açıklama:** Bu bölümde, Next.js projesini nasıl oluşturacağınızı, temel klasör yapısını ve temel konfigürasyonları öğreneceksiniz.

Next.js kurulumu için temel adımlar:

```bash
npx create-next-app@latest proje-adi
cd proje-adi
npm run dev
```

**Temel Klasör Yapısı:**

- 📁 **app:** Tüm sayfaların ve bileşenlerin yer aldığı klasördür.
- 📂 **public:** Statik dosyaların (görseller, favicon) tutulduğu yerdir.
- 📦 **package.json:** Proje bağımlılıklarını ve komutları tanımlar.

---

### 🛠️ 3. Temel Bir Component Oluşturmak

**Kısa Açıklama:** Bu bölümde, React tabanlı bir Next.js bileşeni nasıl oluşturulacağını ve Tailwind CSS'in projeye nasıl entegre edileceğini göreceksiniz.

Header bileşeni örneği:

```jsx
// components/Header.js
export default function Header() {
  return <header className="bg-blue-500 text-white p-4">Hoşgeldiniz!</header>;
}
```

Tailwind CSS kurulumu:

```bash
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

Tailwind CSS kullanarak stil ekleyebilirsiniz.

---

### 🔗 4. Routing İşlemleri

**Kısa Açıklama:** Bu bölüm, Next.js ile sayfalar arasında nasıl yönlendirme (routing) yapabileceğinizi ve dinamik rotaları nasıl oluşturabileceğinizi anlatır.

Next.js ile basit yönlendirme:

```jsx
// app/page.js
export default function Home() {
  return <h1>Ana Sayfa</h1>;
}

// app/about/page.js
export default function About() {
  return <h1>Hakkımızda</h1>;
}
```

Dinamik rota oluşturma:

```jsx
// app/posts/[id]/page.js
export default function Post({ params }) {
  return <div>Post ID: {params.id}</div>;
}
```

---

### ⚠️ 5. Hata Sayfası Oluşturma

**Kısa Açıklama:** Bu bölümde, uygulamanızda karşılaşılabilecek hataları kullanıcı dostu bir şekilde nasıl ele alabileceğinizi öğreneceksiniz.

Genel hata yönetimi için:

```jsx
// app/error.js
export default function Error({ error }) {
  return <div>Bir hata oluştu: {error.message}</div>;
}
```

404 (Sayfa bulunamadı) sayfası oluşturma:

```jsx
// app/not-found.js
export default function NotFound() {
  return <div>Sayfa bulunamadı!</div>;
}
```

---

### 📂 6. Dosya Yapısı (File Convention)

**Kısa Açıklama:** Bu bölüm, Next.js içinde özel klasörlerin nasıl düzenlendiğini, rota gruplarının nasıl yönetildiğini ve layout yapılarını nasıl kullanabileceğinizi açıklar.

Özel klasör ve yapılandırmalar:

- 🔐 **Gizli klasörler (private):** Sunucu tarafında erişilebilen özel dosyalar.
- 📑 **Route Groups:** `(groupName)` syntax’ı ile rota grupları oluşturabilirsiniz.

Layout kullanımı:

```jsx
// app/layout.js
export default function RootLayout({ children }) {
  return (
    <html lang="tr">
      <body>{children}</body>
    </html>
  );
}
```

---

### 🧭 7. Navigation İşlemleri

**Kısa Açıklama:** Bu bölümde, kullanıcıların sitenizde kolayca gezinebilmesi için `Link` bileşenini ve programatik navigasyonun nasıl yapılacağını öğrenebilirsiniz.

Sayfalar arasında gezinme için Link kullanımı:

```jsx
import Link from "next/link";

export default function Navbar() {
  return (
    <nav>
      <Link href="/">Ana Sayfa</Link>
      <Link href="/about">Hakkımızda</Link>
    </nav>
  );
}
```

Programatik navigasyon için useRouter:

```jsx
"use client";
import { useRouter } from "next/navigation";

export default function Button() {
  const router = useRouter();
  return <button onClick={() => router.push("/about")}>Hakkımızda Git</button>;
}
```

---

### 🏷️ 8. Metadata İşlemleri

**Kısa Açıklama:** Bu bölümde, Next.js sayfalarınızın tarayıcı sekme başlığı ve meta açıklamaları gibi önemli verilerini nasıl ekleyebileceğinizi göreceksiniz.

Sayfa metadata ayarları:

```jsx
export const metadata = {
  title: "Ana Sayfa",
  description: "Ana sayfa açıklaması",
};
```

---

### ❗ 9. Error Handling (Hata Yönetimi)

**Kısa Açıklama:** Bu bölümde, uygulama çalışırken oluşan hataları yönetebilmek ve kullanıcılara daha güzel hata mesajları sunabilmek için hata yakalama yöntemlerini inceleyeceksiniz.

Hata durumlarında kullanıcıyı bilgilendirme ve kurtarma:

```jsx
// app/error.js
export default function Error({ error, reset }) {
  return (
    <div>
      <h2>Hata oluştu!</h2>
      <button onClick={() => reset()}>Tekrar Dene</button>
    </div>
  );
}
```

---

### 🛣️ 10. Paralel Rotalar

**Kısa Açıklama:** Bu bölüm, aynı URL üzerinde birden fazla farklı içerik parçasını eş zamanlı olarak render edebilmenizi sağlayan paralel rotaların kullanımını gösterir.

Paralel rotalar kullanarak farklı içerik bloklarını aynı anda yönetebilirsiniz:

```jsx
// app/@sidebar/page.js
export default function Sidebar() {
  return <div>Sidebar içeriği</div>;
}
```

---

### 📡 11. Route Handlers (API Rotaları Yönetimi)

**Kısa Açıklama:** Bu bölümde, Next.js ile birlikte gelen dahili API rotaları aracılığıyla sunucu taraflı veri işlemlerini nasıl gerçekleştireceğinizi öğreneceksiniz.

API oluşturma ve GET isteği örneği:

```jsx
// app/api/data/route.js
export async function GET() {
  return Response.json({ message: "Merhaba!" });
}
```

---

### ⚙️ 12. Önemli Yapılar

**Kısa Açıklama:** Bu bölüm, Next.js uygulamalarında özel davranışları kontrol edebilmek, performansı artırmak veya güvenlik önlemleri almak için kullanılan temel mekanizmaları içerir.

Middleware ile rota kontrolü:

```js
// middleware.js
export function middleware(request) {
  if (!request.nextUrl.pathname.startsWith("/dashboard")) {
    return Response.redirect(new URL("/", request.url));
  }
}
```
