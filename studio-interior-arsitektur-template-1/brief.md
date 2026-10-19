# Brief — Studio Interior & Arsitektur (Template 1)

Brief ini adalah panduan kerja untuk kategori ini. Bangun dengan **Tokigo starter** (Next.js 16 App Router + Tailwind v4 + TypeScript strict). Baca dan patuhi **`AGENTS.md`**; brief ini melengkapi aturan tersebut.

## Yang wajib ada (semua kategori)

- Navbar (logo, menu maks 5, tombol CTA konsultasi proyek) · Hero · Tentang + keunggulan (min 3 poin) · Layanan (deskripsi + cakupan) · Portofolio proyek · Testimoni · FAQ · Kontak (alamat studio, email, telepon, jam, Maps) · CTA konsultasi · Footer.
- **CTA utama kategori ini adalah form/email konsultasi, bukan WhatsApp.** WhatsApp boleh tersedia sebagai kanal sekunder di footer/kontak, tetapi jangan dijadikan tombol utama di header.
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

Studio desain interior dan/atau arsitektur untuk proyek hunian maupun komersial. Keputusan bernilai tinggi dan penuh pertimbangan: klien menilai portofolio, kejelasan proses, transparansi biaya, dan legalitas (STRA/IAI, pengalaman pengurusan PBG). CTA: **ajukan konsultasi proyek** lewat form; komunikasi lanjutan via email/telepon. WhatsApp hanya kanal sekunder untuk pertanyaan cepat.

## Halaman & section khas

**Halaman wajib:** `/`, `/layanan`, `/proyek`, `/proyek/[slug]`, `/proses`, `/kontak` — harus dibuat sebagai route nyata, bukan hanya section di homepage. Semua kartu/tombol yang mengarah ke detail harus punya halaman tujuan yang benar-benar dibuat.

- `/` — hero editorial (foto proyek terbaik, positioning singkat, CTA konsultasi), layanan inti, proyek unggulan, proses bernomor ringkas, keunggulan (pengalaman, legalitas, tim), testimoni klien, FAQ, CTA.
- `/layanan` — desain arsitektur, desain interior, renovasi/re-desain, visualisasi 3D, gambar kerja/DED, bantuan PBG, design & build — sesuai studio. Tiap layanan cantumkan cakupan dan deliverables dengan jelas.
- `/proyek` dan `/proyek/[slug]` — filter per jenis (hunian, kantor, F&B, retail) dan/atau gaya; detail: latar kebutuhan klien, lingkup kerja, luas, lokasi, tahun, palet material, foto (before-after untuk renovasi).
- `/proses` — konsultasi awal → survei & pengukuran → konsep & moodboard → 3D rendering → gambar kerja & RAB → pengawasan/serah terima. Sebut estimasi durasi dan hasil yang didapat klien di tiap tahap.
- `/kontak` — form konsultasi proyek: jenis proyek, lokasi, luas, layanan yang dibutuhkan, tahap saat ini, rentang budget, target mulai, pesan → email terstruktur. Sertakan alamat studio, Maps, jam kerja, email, telepon; WA opsional.

## Fitur interaktif

- Filter portofolio per jenis/gaya.
- Form konsultasi terstruktur dengan rentang budget berupa pilihan (bukan input bebas) → email (mailto) atau WA opsional.
- Before-after sederhana pada proyek renovasi (dua foto berdampingan atau slider CSS ringan; hindari library berat).

## Data di `content/`

- Layanan: `{ nama, deskripsi, cakupan[] }`.
- Proyek: `{ slug, nama, jenis, gaya, lokasi, tahun, luas, lingkup, ringkasan, foto[] }`.
- Proses: `{ judul, deskripsi, durasi? }`.
- Legalitas: `{ nama, keterangan }` (STRA, keanggotaan IAI, dsb.).
- Tim: `{ nama, peran, foto? }`.
- Testimoni: `{ nama, peran, isi }`.

## SEO & JSON-LD

- `ProfessionalService` / `HomeAndConstructionBusiness`; FAQ (biaya desain, boleh desain saja tanpa pelaksanaan, jumlah revisi, durasi, pengurusan PBG, area layanan).

## Catatan tambahan

- Portofolio adalah segalanya: kualitas dan konsistensi foto menentukan persepsi harga studio. Foto stok untuk template wajib ditandai agar diganti foto proyek asli sebelum go-live — jangan pernah mengklaim foto stok sebagai proyek milik klien.
- Transparansi biaya menang di pasar Indonesia: jelaskan mekanisme fee (per m² atau per paket beserta cakupannya), bukan sekadar "hubungi kami". Jangan mengarang angka final — gunakan rentang atau bahasa "estimasi setelah survei".
- Legalitas adalah sinyal kepercayaan: tampilkan nomor STRA dan keanggotaan IAI (bila ada), serta pengalaman PBG, di halaman tentang/proses.
- Motion halus (reveal foto, hover, transisi halaman) cocok untuk studio ini, tetapi satu bahasa gerak dan tidak boleh memperlambat halaman.
- Nada visual: tenang, editorial, banyak ruang kosong, foto dominan. Hindari gradien/kaca dekoratif dan kesan "template korporat biru generik".
- Jangan memakai superlatif tanpa bukti ("terbaik", "termurah"); tunjukkan proyek, proses, dan angka.
