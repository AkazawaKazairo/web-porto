# 📧 Cara Setup EmailJS untuk Form Kontak

Form kontak di website Anda sekarang sudah terintegrasi dengan EmailJS. Ikuti langkah-langkah berikut untuk mengaktifkannya:

## 🚀 Langkah 1: Buat Akun EmailJS (GRATIS)

1. Buka https://www.emailjs.com
2. Klik **"Sign Up"** di pojok kanan atas
3. Pilih **"Sign up with Google"** dan gunakan email Anda: `shelloardiansyaharrofieska@gmail.com`
4. Setelah login, Anda akan masuk ke Dashboard EmailJS

## 📩 Langkah 2: Tambahkan Email Service

1. Di Dashboard, klik **"Email Services"** di sidebar kiri
2. Klik tombol **"Add New Service"**
3. Pilih **"Gmail"**
4. Klik **"Connect Account"** dan login dengan Gmail Anda
5. Beri nama service (misal: `gmail_service`)
6. Klik **"Create Service"**
7. **PENTING**: Salin **Service ID** yang muncul (misal: `service_abc123`)

## 📝 Langkah 3: Buat Email Template

1. Klik **"Email Templates"** di sidebar kiri
2. Klik **"Create New Template"**
3. Gunakan template berikut:

**Subject:**
```
Pesan Baru dari {{from_name}} - Portofolio
```

**Content:**
```
Anda mendapat pesan baru dari form kontak website Anda!

Nama: {{from_name}}
Email: {{from_email}}

Pesan:
{{message}}

---
Dikirim dari website portofolio Anda
```

4. **To Email** (di bagian Settings): Ketik `{{to_email}}`
5. **To Name**: Ketik `Shello Ardiansyah`
6. Beri nama template (misal: `contact_form`)
7. Klik **"Save"**
8. **PENTING**: Salin **Template ID** (misal: `template_xyz789`)

## 🔑 Langkah 4: Dapatkan Public Key

1. Klik **"Account"** di sidebar kiri
2. Scroll ke bawah sampai menemukan **"API Keys"**
3. **PENTING**: Salin **Public Key** Anda (misal: `aBc123XyZ`)

## ⚙️ Langkah 5: Setup di Website

1. Di folder `d:\Portofolio`, buat file baru bernama `.env`
2. Copy isi dari file `.env.example` ke `.env`
3. Ganti nilai-nilai berikut dengan kredensial Anda:

```env
VITE_EMAILJS_SERVICE_ID=service_abc123
VITE_EMAILJS_TEMPLATE_ID=template_xyz789
VITE_EMAILJS_PUBLIC_KEY=aBc123XyZ
```

4. **Simpan** file `.env`
5. **Restart** development server:
   - Tekan `Ctrl+C` di terminal untuk stop server
   - Jalankan `npm run dev` lagi

## ✅ Langkah 6: Test Form Kontak

1. Buka website Anda
2. Scroll ke bagian **Kontak**
3. Isi form dan klik **"Kirim Pesan"**
4. Jika berhasil, Anda akan melihat pesan sukses berwarna hijau
5. Cek email `shelloardiansyaharrofieska@gmail.com` - pesan seharusnya sudah masuk!

## 🔧 Troubleshooting

**Jika muncul error "Failed to send email":**
- Pastikan file `.env` sudah dibuat dan berisi kredensial yang benar
- Pastikan sudah restart dev server setelah membuat `.env`
- Cek apkah Service ID, Template ID, dan Public Key sudah benar

**Jika email tidak masuk:**
- Cek folder Spam di Gmail
- Pastikan di EmailJS Template, **To Email** sudah diisi dengan `{{to_email}}`

## 📊 Limit Gratis EmailJS

- **200 email per bulan** (gratis selamanya)
- Cukup untuk website portofolio personal!

---

**✨ Selesai! Form kontak Anda sekarang sudah berfungsi penuh!**
