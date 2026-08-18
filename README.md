# CRM Bank Sampah

Website CRM untuk pengelolaan Bank Sampah, dibangun dari nol dengan pendekatan
yang bersih, profesional, scalable, dan mudah dikembangkan.

Tahap saat ini: **Pondasi Project** (belum ada fitur CRM, autentikasi, atau
koneksi database aktif).

## Tech Stack

- HTML5
- CSS3 (native, tanpa framework)
- Vanilla JavaScript (ES6 Modules)
- Supabase (akan digunakan pada tahap berikutnya)
- Netlify (hosting)

## Struktur Folder

```
crm-bank-sampah/
├── index.html          # Entry point, redirect ke pages/dashboard.html
├── assets/              # Gambar, ikon, dan font statis
├── css/                 # Seluruh stylesheet, dipisah per tanggung jawab
├── js/
│   ├── app.js           # Entry point JS, menyusun layout di setiap halaman
│   ├── router.js        # Helper identifikasi halaman aktif (bukan SPA)
│   ├── config.js        # Satu-satunya sumber konfigurasi aplikasi
│   ├── components/      # Sidebar, navbar, footer yang reusable
│   ├── pages/            # Logika khusus tiap halaman
│   ├── services/         # (disiapkan) layanan pengambilan data
│   ├── utils/            # (disiapkan) fungsi bantu umum
│   └── modules/          # (disiapkan) modul fitur besar
├── pages/                # Halaman-halaman HTML aplikasi
├── partials/             # Markup HTML sidebar, navbar, footer
└── supabase/
    └── supabase.js       # Inisialisasi client Supabase
```

## Cara Menjalankan

Karena project ini menggunakan ES6 Modules dan `fetch()` untuk memuat partial
HTML, project harus dijalankan melalui local server (tidak bisa dibuka
langsung sebagai file://).

Contoh menggunakan VS Code Live Server, atau:

```bash
npx serve .
```

Lalu buka `http://localhost:PORT/` di browser.

## Konfigurasi

Seluruh konfigurasi aplikasi (nama aplikasi, versi, URL & key Supabase)
berada di `js/config.js`. Jangan menuliskan URL atau API Key langsung di
file lain — selalu import dari `config.js`.

## Design System (Tahap 2)

Warna, tipografi, dan komponen UI didefinisikan sebagai variable pada
`css/variables.css` dan komponen reusable pada `css/components.css`.

**Warna utama:** Primary `#16A34A`, Primary Hover `#15803D`, Primary Light `#DCFCE7`.
**Font:** Poppins (fallback `sans-serif`), dimuat via Google Fonts di `css/global.css`.
**Ikon:** Google Material Symbols Outlined (CDN, dimuat di `<head>` setiap halaman).

Komponen UI yang tersedia (lihat contoh penggunaan di `pages/dashboard.html`):

| Komponen | CSS | Perilaku JS |
|---|---|---|
| Button (Primary/Secondary/Outline/Danger/Ghost) | `components.css` | - |
| Input, Textarea, Select | `components.css` | - |
| Checkbox, Radio | `components.css` | - |
| Search Box | `components.css` / `navbar.css` | - |
| Table (sticky header, hover row) | `components.css` | - |
| Badge | `components.css` | - |
| Card (dengan hover effect) | `components.css` | - |
| Alert (dismissible) | `components.css` | `js/utils/alert.js` |
| Modal | `components.css` | `js/utils/modal.js` |
| Dropdown | `components.css` | `js/utils/dropdown.js` |
| Pagination | `components.css` | `js/utils/pagination.js` |
| Loading Spinner | `components.css` | - |

Sidebar mendukung mode **collapse** (desktop/tablet, disimpan di `localStorage`)
dan mode **drawer** (mobile, dengan overlay). Navbar berisi judul halaman,
search box, ikon notifikasi, dan dropdown profil pengguna.

## Status Pengembangan

- [x] Struktur project
- [x] Layout (sidebar, navbar, content)
- [x] Halaman kosong untuk seluruh modul CRM
- [x] Design System (warna, tipografi, komponen UI reusable)
- [x] Sidebar & Navbar modern, responsive (desktop/tablet/mobile)
- [ ] Autentikasi & Login
- [ ] Koneksi Supabase (query & CRUD)
- [ ] Dashboard Analytics (data nyata)
- [ ] Fitur CRM (Customers, Transactions, dll.)
