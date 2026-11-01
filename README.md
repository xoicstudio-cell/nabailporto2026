# Website portofolio — Naba'ilsae Wildan Rosadi

Website statis (tanpa build) untuk Cloudflare Pages. Semua isi website dibaca dari folder `content/`, jadi kamu cukup mengubah isi lewat panel `/admin` tanpa menyentuh kode.

```
index.html               halaman utama + halaman "All work" (#all-work)
content/profile.json     nama, foto, intro, email, WhatsApp, LinkedIn
content/works.json       semua karya (urutan = urutan tampil)
content/certifications.json
assets/logos/            logo software, sertifikat, platform, kontak
images/certs/            gambar sertifikat
images/uploads/          gambar yang kamu upload lewat /admin
admin/                   panel admin (Sveltia CMS)
```

## Setup sekali saja

1. **Upload ke GitHub**
   - Buat repo baru di github.com, misalnya `portfolio`.
   - Pilih "uploading an existing file", lalu drag semua isi folder ini (termasuk folder `admin`, `content`, dan lainnya), lalu klik Commit.

2. **Nama repo di admin** sudah diisi: `xoicstudio-cell/nabailporto2026`. Kalau nama repo kamu berbeda, ubah baris `repo:` di `admin/config.yml`.

3. **Hubungkan ke Cloudflare Pages**
   - Buka dash.cloudflare.com, lalu masuk ke Workers & Pages, pilih Create, lalu Pages, lalu Connect to Git.
   - Pilih repo-nya.
   - Framework preset: **None**. Build command: **kosongkan**. Build output directory: **/**.
   - Klik Save and Deploy. Website kamu akan tayang di `nama-project.pages.dev`. Custom domain bisa ditambah nanti di tab Custom domains.

4. **Buat token untuk login ke admin**
   - Buka GitHub, lalu Settings, Developer settings, Personal access tokens, Fine-grained tokens, lalu Generate new token.
   - Repository access: pilih **Only select repositories**, lalu pilih repo portofolio.
   - Permissions, bagian Repository permissions: **Contents: Read and write**.
   - Simpan token di tempat aman (misalnya password manager). Jangan bagikan ke siapa pun.

## Cara update website

1. Buka `https://domain-kamu/admin/`.
2. Pilih **Sign In with Token**, lalu tempel token dari langkah 4.
3. Pilih menu yang mau diubah:
   - **Profile & contact**: foto (rasio 4:5), nama, intro, kontak, dan badge "open for work".
   - **Work**: tambah atau edit karya, upload cover (rasio 4:3) dan gambar tambahan, isi platform, link, tools dan peran. Centang **Featured** untuk maksimal 6 karya yang tampil di homepage. Urutan bisa diatur dengan drag.
   - **Certifications**: tambah sertifikat baru beserta gambar dan link verifikasinya.
4. Klik **Save**. Perubahan otomatis masuk ke GitHub, lalu Cloudflare men-deploy ulang dalam sekitar 1 menit.

## Tips gambar
- Pakai JPG atau WebP, lebar sekitar 1600–2000 px, dan usahakan di bawah 1 MB per gambar supaya website tetap cepat.
- Selama cover belum diisi, kartu karya menampilkan mockup flat dengan label "Add images".
