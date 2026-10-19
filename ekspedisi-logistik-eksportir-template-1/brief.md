# Brief — Ekspedisi, Logistik & Eksportir (Template 1)

Brief ini adalah panduan kerja untuk kategori ini. Bangun dengan **Tokigo starter** (Next.js 16 App Router + Tailwind v4 + TypeScript strict). Baca dan patuhi **`AGENTS.md`**; brief ini melengkapi aturan tersebut.

## Yang wajib ada (semua kategori)

- Navbar (logo, menu maks 5, tombol CTA minta penawaran) · Hero · Tentang + keunggulan (min 3 poin) · Layanan (deskripsi + cakupan) · Jangkauan rute & kapabilitas operasional · Testimoni klien · FAQ · Kontak (kantor, email, telepon, jam kerja, Maps) · CTA minta penawaran · Footer.
- **CTA utama kategori ini adalah "minta penawaran" (RFQ) lewat form/email, bukan WhatsApp.** WhatsApp boleh ada sebagai kanal sekunder di footer/kontak untuk pertanyaan cepat, tetapi jangan dijadikan tombol utama di header.
- Responsive 375–1600px+ tanpa horizontal overflow; **light & dark mode** wajib (pakai `ThemeToggle` bawaan starter).
- Semua tombol, navigasi, dan kartu berfungsi — tidak ada link mati, `href="#"`, atau kartu tanpa halaman tujuan.
- Konten contoh relevan kategori (bukan Lorem Ipsum); harga format `Rp 25.000`; jangan mengarang alamat/harga/data klien yang belum diberikan.
- SEO: metadata tiap halaman, heading berurutan, alt text gambar; favicon + identitas brand.
- Gambar dari Unsplash/Pexels/Pixabay — unduh ke `public/` (jangan hotlink), render dengan `next/image`.
- Selesai hanya jika `pnpm typecheck && pnpm lint && pnpm format:check && pnpm build` lolos.
- Pengecekan visual & browser console (tidak ada error, tidak ada gambar gagal muat) dilakukan oleh developer sebelum menyerahkan hasil — agent dilarang memverifikasi via browser.

## Arah visual

- Referensi desain utama: gambar referensi ada langsung di folder ini (root folder — mis. `original-*.webp`). Ikuti nuansa, tipografi, palet, dan komposisinya.
- Jangan menyalin aset atau teks mentah dari referensi, dan jangan hotlink gambar — foto tetap diunduh (Unsplash/Pexels/Pixabay) ke `public/`.
- Nama brand/website **tidak boleh mengikuti contoh pada gambar referensi** — tentukan sendiri nama yang baik, relevan dengan kategori ini, dan terasa natural dalam bahasa Indonesia.
- Jika gambar referensi belum tersedia: ajukan design brief singkat (hero, tipografi, palet, ritme, signature detail) dan tunggu konfirmasi sebelum menulis kode.
- Aturan tampilan tetap mengikuti `AGENTS.md`: anti AI-slop, maks 2 font family, gradient/glass seperlunya, motion satu bahasa gerak, wajib light & dark mode.
- Hasil antar template di kategori yang sama harus terlihat berbeda; gambar referensi adalah pembedanya.
- Catatan tambahan di bagian bawah bersifat tips — jika bertentangan dengan referensi, ikuti referensi.

## Profil

Perusahaan freight forwarding/ekspedisi (laut, udara, darat), customs clearance (PPJK), pergudangan, dan door-to-door — atau perusahaan eksportir produk. Pembelinya B2B dan melakukan due diligence: legalitas, pengalaman, jangkauan rute, dan kecepatan respons penawaran. CTA: **minta penawaran (RFQ)** lewat form/email; telepon operasional untuk urusan berjalan; WhatsApp sekunder.

## Halaman & section khas

**Halaman wajib:** `/`, `/layanan`, `/rute`, `/penawaran`, `/lacak`, `/tentang` — harus dibuat sebagai route nyata, bukan hanya section di homepage. Semua kartu/tombol yang mengarah ke detail harus punya halaman tujuan yang benar-benar dibuat.

- `/` — hero B2B (positioning + angka: tahun pengalaman, jumlah pengiriman, kantor), layanan utama, jangkauan rute ringkas, keunggulan (legalitas PPJK/ISO, jaringan agen global, respons cepat), industri yang dilayani, testimoni korporat, FAQ, CTA penawaran.
- `/layanan` — laut (FCL/LCL), udara, darat/trucking & distribusi, customs clearance (PPJK), pergudangan, kargo proyek/khusus, door-to-door; tiap layanan: cakupan, jenis barang yang cocok, dokumen yang ditangani.
- `/rute` — daftar rute populer (asal → tujuan, moda, estimasi transit) dengan catatan bahwa estimasi bersifat indikatif; jangkauan pelabuhan/bandara sesuai klien (mis. Tanjung Priok, Tanjung Perak, Belawan, Soekarno-Hatta).
- `/penawaran` — form RFQ terstruktur: perusahaan, PIC, email bisnis, telepon, moda, asal, tujuan, jenis barang, HS code (opsional), berat/volume, incoterms, jadwal, catatan → satu email terstruktur; sertakan janji waktu respons (mis. maksimal 1×24 jam kerja).
- `/lacak` — form nomor booking/BL/AWB yang meneruskan permintaan status ke email/WA operasional. **Jangan menampilkan posisi palsu**; jelaskan kanal tracking resmi klien bila ada.
- `/tentang` — profil & sejarah singkat, legalitas (izin PPJK, NIB, keanggotaan asosiasi seperti ALFI, ISO), tim, kantor/gudang, kontak + jam kerja.

## Fitur interaktif

- Form RFQ terstruktur (pilihan moda, incoterms, rentang berat/volume) yang menghasilkan satu pesan rapi, bukan field bebas tanpa arah.
- Form lacak sebagai permintaan status (jujur dan berfungsi), bukan halaman tracking tiruan.
- Filter rute per moda/negara bila jumlahnya banyak.

## Data di `content/`

- Layanan: `{ nama, deskripsi, cakupan[], cocokUntuk[] }`.
- Rute: `{ asal, tujuan, moda, estimasi }`.
- Legalitas: `{ nama, keterangan }` (izin PPJK, ISO, keanggotaan asosiasi).
- Kantor: `{ tipe (kantor/gudang), alamat, telepon, email, jam }`.
- Testimoni: `{ nama, jabatan, perusahaan }`.
- FAQ: daftar tanya-jawab.

## SEO & JSON-LD

- `Organization` + `LocalBusiness` untuk kantor; FAQPage (dokumen yang diperlukan, estimasi transit, asuransi, minimum berat, cara pembayaran).
- Kata kunci alami (freight forwarding, ekspedisi, ekspor-impor, PPJK) — tanpa stuffing.
- Jika klien menargetkan pembeli luar negeri: sediakan ringkasan berbahasa Inggris minimal di hero/tentang dan company profile PDF yang bisa diunduh.

## Catatan tambahan

- Pembeli korporat mengharapkan form penawaran/email bisnis dan janji waktu respons — bukan chatting WA. Jangan menjadikan WA CTA utama di header.
- Tracking: lebih baik form permintaan status yang jujur daripada halaman tracking palsu yang tidak berfungsi. Jika klien punya sistem tracking asli, tautkan/integrasikan alih-alih membuat simulasi.
- Hindari superlatif kosong ("termurah", "tercepat nomor 1"); tunjukkan legalitas (nomor izin PPJK), rute nyata, dan angka pengalaman.
- Jangan menampilkan foto armada/gudang yang bukan milik klien sebagai milik sendiri; foto stok untuk template wajib ditandai agar diganti.
- Varian eksportir produk (bukan jasa logistik): fokus bergeser ke katalog komoditas, negara tujuan, dan sertifikasi produk (HACCP, halal, SNI — hanya yang benar-benar dimiliki) + RFQ buyer (produk, kuantitas, port tujuan, MOQ/packing); pola halaman dan CTA tetap sama.
- Tone: profesional, ringkas, spesifik, berorientasi angka — bukan brosur wisata.
