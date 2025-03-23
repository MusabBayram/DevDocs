# Next.js Training Documentation

## Table of Contents

- [1. Important Theoretical Concepts](#-1-important-theoretical-concepts)
- [2. Next.js Installation](#-2-nextjs-installation)
- [3. Creating a Basic Component](#-3-creating-a-basic-component)
- [4. Routing Operations](#-4-routing-operations)
- [5. Creating Error Pages](#-5-creating-error-pages)
- [6. File Convention Structure](#-6-file-convention-structure)
- [7. Navigation Operations](#-7-navigation-operations)
- [8. Metadata Operations](#-8-metadata-operations)
- [9. Error Handling](#-9-error-handling)
- [10. Parallel Routes](#-10-parallel-routes)
- [11. Route Handlers (API Management)](#-11-route-handlers-api-management)
- [12. Important Structures](#-12-important-structures)

---

## 📌 Next.js Training Documentation

### 🚀 1. Important Theoretical Concepts

**Brief Description:** This section introduces what Next.js is, its differences from React, the advantages of SSR and CSR, and the distinction between Client Side Components (CSC) and Server Side Components (SSC).

Next.js is a popular framework for building React-based applications. It provides powerful tools for static site generation (SSG) and server-side rendering (SSR). Next.js improves SEO optimization, performance, and development speed.

- 🔹 **Framework vs Library:**

  - 📚 **Library:** A collection of pre-built functions and methods designed for specific tasks. For instance, React provides a component-based structure for building UI but does not dictate the overall structure of the application.
  - 🔧 **Framework:** Controls the flow and structure of an application, providing developers with standards and clear guidelines. Next.js defines how to structure React applications.

- 🔹 **SSR and CSR:**

  - 🌐 **Server Side Rendering (SSR):** HTML content is generated on the server and sent to the client. It enhances SEO and initial load speed.
  - 💻 **Client Side Rendering (CSR):** Content is generated in the browser using JavaScript, ideal for dynamic and interactive apps.

- 🔹 **CSC and SSC:**
  - 🎛️ **Client Side Components (CSC):** Interactive components based on user interaction (forms, buttons, dynamic tables).
  - 📃 **Server Side Components (SSC):** Components generated on the server side for static or SEO-focused content (blogs, articles, product descriptions).

---

### 🔧 2. Next.js Installation

**Brief Description:** This section covers the initial setup of a Next.js project, basic folder structure, and fundamental configurations.

Basic commands for installing Next.js:

```bash
npx create-next-app@latest project-name
cd project-name
npm run dev
```

**Basic Folder Structure:**

- 📁 **app:** Contains pages and components.
- 📂 **public:** Holds static assets (images, favicon).
- 📦 **package.json:** Defines project dependencies and commands.

---

### 🛠️ 3. Creating a Basic Component

**Brief Description:** Learn how to create a simple Next.js component and integrate Tailwind CSS into your project.

Header component example:

```jsx
// components/Header.js
export default function Header() {
  return <header className="bg-blue-500 text-white p-4">Welcome!</header>;
}
```

Tailwind CSS installation:

```bash
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

---

### 🔗 4. Routing Operations

**Brief Description:** This section explains how to perform basic routing and create dynamic routes in Next.js.

Basic routing:

```jsx
// app/page.js
export default function Home() {
  return <h1>Home Page</h1>;
}

// app/about/page.js
export default function About() {
  return <h1>About Us</h1>;
}
```

Dynamic routing:

```jsx
// app/posts/[id]/page.js
export default function Post({ params }) {
  return <div>Post ID: {params.id}</div>;
}
```

---

### ⚠️ 5. Creating Error Pages

**Brief Description:** Learn how to handle and display errors gracefully.

General error management:

```jsx
// app/error.js
export default function Error({ error }) {
  return <div>An error occurred: {error.message}</div>;
}
```

404 Page creation:

```jsx
// app/not-found.js
export default function NotFound() {
  return <div>Page not found!</div>;
}
```

---

### 📂 6. File Convention Structure

**Brief Description:** Details about special folders, route groups, and layouts.

Special folders and layout:

```jsx
// app/layout.js
export default function RootLayout({ children }) {
  return (
    <html lang="en">
      <body>{children}</body>
    </html>
  );
}
```

---

### 🧭 7. Navigation Operations

**Brief Description:** Use of `Link` component and programmatic navigation.

Link component:

```jsx
import Link from "next/link";

export default function Navbar() {
  return (
    <nav>
      <Link href="/">Home</Link>
      <Link href="/about">About Us</Link>
    </nav>
  );
}
```

---

### 🏷️ 8. Metadata Operations

**Brief Description:** Add page metadata for better SEO and user experience.

Metadata example:

```jsx
export const metadata = {
  title: "Home Page",
  description: "Description of the home page",
};
```

---

### ❗ 9. Error Handling

**Brief Description:** Techniques for handling errors gracefully and providing feedback to users.

Error handling example:

```jsx
// app/error.js
export default function Error({ error, reset }) {
  return (
    <div>
      <h2>An error occurred!</h2>
      <button onClick={() => reset()}>Try Again</button>
    </div>
  );
}
```

---

### 🛣️ 10. Parallel Routes

**Brief Description:** Render multiple content sections simultaneously.

Example:

```jsx
// app/@sidebar/page.js
export default function Sidebar() {
  return <div>Sidebar content</div>;
}
```

---

### 📡 11. Route Handlers (API Management)

**Brief Description:** Creating APIs in Next.js.

API creation example:

```jsx
// app/api/data/route.js
export async function GET() {
  return Response.json({ message: "Hello!" });
}
```

---

### ⚙️ 12. Important Structures

**Brief Description:** Middleware for route control.

Example middleware:

```js
// middleware.js
export function middleware(request) {
  if (!request.nextUrl.pathname.startsWith("/dashboard")) {
    return Response.redirect(new URL("/", request.url));
  }
}
```
