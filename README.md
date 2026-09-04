# Koleksi Dr. Pinguin — Cloudflare Pages

Gallery video embed (IndoAV / userbokep) untuk domain **https://koleksidrpinguin.site**

Struktur bersih, tanpa build step. Cocok untuk Cloudflare Pages.

```
koleksidrpinguin-cf/
├── index.html       # Gallery
├── admin.html       # Admin tambah video
├── videos.json      # Data video (mulai dari [])
├── wrangler.toml
├── _headers
├── robots.txt
└── README.md
```

## Deploy ke Cloudflare Pages

1. Buka [Cloudflare Dashboard](https://dash.cloudflare.com) → **Workers & Pages** → **Create** → **Pages** → **Connect to Git**
2. Pilih repo: `fashfdhgacd/koleksidrpinguin-cf`
3. Production branch: `main`
4. Build command: **kosong**
5. Output directory: `/`  (atau `.`)
6. Save and Deploy

### Pasang domain koleksidrpinguin.site

1. Di project Pages → **Custom domains** → Add `koleksidrpinguin.site` dan `www.koleksidrpinguin.site`
2. Kalau domain sudah di Cloudflare DNS:
   - Type `CNAME` name `@` target `koleksidrpinguin-cf.pages.dev` (atau sesuai instruksi CF)
   - Type `CNAME` name `www` target yang sama
3. Kalau nameserver domain belum di Cloudflare, pindahkan NS ke CF dulu, atau set CNAME di registrar sesuai petunjuk Pages.
4. Tunggu status **Active**. Hard refresh (Ctrl+Shift+R).

Jangan hapus project Vercel lama sebelum domain di Cloudflare sudah hijau.

## Admin

- URL: `https://koleksidrpinguin.site/admin.html`
- Password: `Koleksi Dr. Pinguin Bokep, M.S.B`
- Tambah video **maks 30–50 per submit**
- Setelah bulk, klik **Export JSON**, lalu ganti `videos.json` di GitHub (atau pakai tombol Simpan ke GitHub)
- Hard refresh gallery setelah deploy

## Import koleksi lama

Kalau mau pindahkan data dari repo `koleksi-dr-pinguin`:

1. Copy isi `data/videos.json` atau `videos.json` lama
2. Paste ke file `videos.json` di repo ini
3. Commit & push — Pages auto-deploy

## Aturan biar tidak error

- Jangan submit ratusan video sekaligus
- Kalau "Unexpected end of JSON input" → reset `videos.json` ke `[]`
- Edit hapus video lebih aman langsung di GitHub, bukan lewat Admin
