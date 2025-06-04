# 👕 Premium Men’s Shirt Store

A smooth, fast, and elegant e-commerce web app built for selling **premium men’s shirts**. Powered by **Supabase** for the backend (auth, database, and CMS), and built with a focus on **minimalist design**, **responsive layout**, and **frictionless user experience**.

---

## 🚀 Features

- ⚡ **High-performance UI** with smooth page transitions (Framer Motion)
- 🧑‍💼 **User Authentication** via Supabase Auth
- 📦 **Dynamic Product Catalog** (Shirts only)
- 🛒 **Shopping Cart** & smooth Checkout flow
- 🎯 **Product Filters** (by color, size, stock)
- ✍️ **Content Management** via Supabase (Products, Orders, Blog Posts)
- 📱 **Mobile-first Responsive Design**
- 🔐 **Secure CRUD operations**

---

## 🧩 Tech Stack

- **Frontend:** React.js / Next.js / Vite (based on what Bolt generated)
- **Styling:** Tailwind CSS (recommended for scalability)
- **Animation:** Framer Motion
- **Backend:** [Supabase](https://supabase.io) (Auth, Realtime DB, Storage)
- **CMS:** Supabase Table Editor (for now)

---

## 🗃️ Supabase Schema

### `products`
| Column       | Type       |
|--------------|------------|
| id           | UUID (PK)  |
| name         | Text       |
| description  | Text       |
| price        | Numeric    |
| image_url    | Text       |
| slug         | Text       |
| sizes        | Text[]     |
| stock        | Integer    |
| category     | Text       |
| created_at   | Timestamp  |

---

### `users` (via Supabase Auth)
Handled automatically by Supabase.

---

### `orders`
| Column       | Type       |
|--------------|------------|
| id           | UUID (PK)  |
| user_id      | UUID (FK)  |
| status       | Text       |
| total_amount | Numeric    |
| created_at   | Timestamp  |

---

### `order_items`
| Column      | Type       |
|-------------|------------|
| id          | UUID (PK)  |
| order_id    | UUID (FK)  |
| product_id  | UUID (FK)  |
| quantity    | Integer    |
| size        | Text       |
| price       | Numeric    |

---

### `cart_items`
| Column      | Type       |
|-------------|------------|
| user_id     | UUID (FK)  |
| product_id  | UUID (FK)  |
| quantity    | Integer    |
| size        | Text       |

---

### `inventory`
| Column            | Type       |
|-------------------|------------|
| product_id        | UUID (FK)  |
| quantity_available| Integer    |
| updated_at        | Timestamp  |

---

### `blog_posts`
| Column      | Type       |
|-------------|------------|
| id          | UUID (PK)  |
| title       | Text       |
| content     | Text       |
| cover_image | Text       |
| slug        | Text       |
| published_at| Timestamp  |

---

## 🛠️ Getting Started

### 1. Clone the repo

```bash
git clone https://github.com/yourusername/mens-shirt-store.git
cd mens-shirt-store
```
### 2. Install dependencies
```bash
npm install
# or
yarn
```
### 3. Set up Supabase
--Go to supabase.io and create a new project

--Create the tables above (or use the SQL script if available)

--Enable Supabase Auth (Email/Password)

--Get your Supabase URL and Anon Key

### 4. Add environment variables
Create a .env.local file and add:
```bash
VITE_SUPABASE_URL=your-supabase-url
VITE_SUPABASE_ANON_KEY=your-anon-key
```

### 5. Run the app
```bash
npm run dev
# or
yarn dev
```
📦 Future Improvements
Admin dashboard for managing products and orders

Email notifications on order

Stripe integration for payments

Image uploads to Supabase Storage

Enhanced customer reviews


