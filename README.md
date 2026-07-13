# LetterLog Pro - Document Tracker

> Aplikasi pelacak dokumen berbasis web dengan antarmuka modern, animasi kaya, sinkronisasi GitHub Gist, dan efek mouse trail. **Hanya 1 file HTML** - tidak perlu instalasi!

---

## Fitur Utama

### Manajemen Dokumen
- **Buat Dokumen** dengan sistem nomor surat otomatis berbasis template
- **Template Kustom** - Template default yang bisa diedit/ditambah dengan **counter awal yang bisa diatur** (misal: mulai dari nomor 30, 100, atau berapapun)
- **Segmen Drag & Drop** - Ubah urutan segmen nomor surat (counter, perusahaan, divisi, proyek, bulan, tahun)
- **Arsip Dokumen** - Pencarian, filter multi-kriteria, sorting, batch operations
- **Status Workflow** - Draft → Review → Sent → Received → Archived (dapat dikustomisasi)

### Master Data Lengkap
- **Edit Label Segmen** - Ubah nama label seperti "Divisi" → "Departemen", "Proyek" → "Program", dll
- **Edit Kode Referensi** - Edit semua kode (IPI, MBG, SRT, BAHP, dll) langsung dari satu halaman
- **Segmen Custom** - Tambahkan segmen baru (maksimal 10 segmen total)
- **Template Builder** - Buat template baru dengan pratinjau langsung (2 kolom: form kiri, preview kanan)

### Tema & Personalisasi
- **15 Preset Tema** - Warm Sand, Cool Breeze, Forest, Ocean, Sunset, Midnight, Coffee, Lavender, Rose, Slate, Mint, Berry, Charcoal, Gold, Nord
- **Mode Terang/Gelap/Otomatis** dengan transisi halus
- **Warna Kustom** - Atur background, surface, primary, accent, text color
- **CSS Editor** - Untuk kustomisasi advanced via CSS variables

### Sinkronisasi Cloud (GitHub Gist)
- **Upload ke Gist** - Backup seluruh data ke GitHub Gist
- **Download dari Gist** - Restore data di perangkat lain
- **Test Koneksi** - Verifikasi token GitHub
- **Token tersimpan lokal** - Aman di localStorage browser

### Efek Visual
- **30+ Animasi Micro-interaction** - Hover effects, ripple buttons, transitions
- **Ambient Background** - Aurora sebagai default, dengan opsi Fireflies, Embers, atau tanpa animasi
- **Glassy Workspace** - Surface transparan lembut yang mengikuti warna tema aktif
- **Kontrol Intensitas** - Atur kekuatan efek ambient secara terpisah dari mouse trail
- **4 Pilihan Mouse Trail** - Nonaktif, Glow Dots, Sparkle, Constellation
- **Confetti** - Saat berhasil menyimpan dokumen/export data
- **Scroll Indicator** - Progress bar di atas layar

### Keyboard Shortcuts
| Shortcut | Fungsi |
|----------|--------|
| `Alt + D` | Dashboard |
| `Alt + M` | Master Data |
| `Alt + B` | Buat Dokumen |
| `Alt + A` | Arsip |
| `Alt + P` | Pengaturan |
| `Ctrl + Enter` | Simpan dokumen / simpan template |
| `Escape` | Tutup modal / batal edit template |

---

## Cara Menggunakan

### Memulai
1. Buka file `LetterLog_Pro_Animated.html` di browser apa saja
2. Data otomatis tersimpan di **localStorage** browser

### Membuat Dokumen Baru
1. Klik **Buat Dokumen** di sidebar atau tombol "+" di Dashboard
2. Pilih **Template** yang sesuai
3. Isi detail dokumen (keterangan wajib diisi)
4. Drag & drop segmen untuk mengubah urutan nomor surat
5. Klik **Simpan Dokumen** atau tekan `Ctrl + Enter`

### Sinkronisasi ke GitHub Gist

#### Langkah 1: Buat GitHub Personal Access Token
1. Kunjungi [github.com/settings/tokens/new](https://github.com/settings/tokens/new)
2. Beri nama token (contoh: "LetterLog Sync")
3. Centang scope **gist**
4. Klik **Generate token**
5. **Copy token** yang muncul (hanya ditampilkan sekali!)

#### Langkah 2: Setup di Aplikasi
1. Buka menu **Pengaturan**
2. Scroll ke section **Sinkronisasi GitHub Gist**
3. Paste token ke field **GitHub Personal Access Token**
4. Klik **Test Koneksi** untuk verifikasi
5. Klik **Upload ke Gist** untuk backup pertama

#### Langkah 3: Restore di Perangkat Lain
1. Masukkan token dan **Gist ID** (lihat di info panel setelah upload)
2. Klik **Download dari Gist**
3. Konfirmasi import untuk menimpa data lokal

### Mengaktifkan Mouse Trail
1. Buka menu **Pengaturan**
2. Pilih salah satu efek di section **Efek Jejak Kursor**:
   - **Nonaktif** - Default, tanpa efek
   - **Glow Dots** - Titik-titik halus mengikuti kursor
   - **Sparkle** - Partikel berkilau
   - **Constellation** - Jaringan titik terhubung (paling berat)

### Mengatur Background Ambient
1. Buka menu **Pengaturan**
2. Buka bagian **Motion & Atmosphere**
3. Pilih **Aurora**, **Fireflies**, **Embers**, atau **Tenang**
4. Atur intensitas dan aktifkan/nonaktifkan **Glassy Workspace** sesuai kebutuhan

Efek ambient dan mouse trail merupakan dua pengaturan terpisah. Animasi ambient otomatis disederhanakan pada layar kecil, berhenti saat tab tidak aktif, dan menghormati preferensi `prefers-reduced-motion`.

---

## Format Nomor Surat

Sistem menggunakan segmen yang bisa diatur urutannya:

| Segmen | Contoh | Keterangan |
|--------|--------|------------|
| Counter | `291` | Nomor urut otomatis (3 digit) |
| Perusahaan | `IPI` | Kode perusahaan (bisa diedit di Master Data) |
| Divisi | `BAHP` | Kode divisi (bisa diedit di Master Data) |
| Proyek | `MBG` | Kode proyek (bisa diedit di Master Data) |
| Tipe Surat | `SRT` | Jenis dokumen (bisa diedit di Master Data) |
| Bulan | `VI` | Format bisa diubah (Romawi/Angka/Nama) |
| Tahun | `2026` | Tahun otomatis |
| **Custom** | `XXX` | **Segmen buatan sendiri (maks 10 total)** |

**Contoh output**: `291/IPI/BAHP/MBG/VI/2026`

---

## Data Storage

| Lokasi | Kegunaan | Data |
|--------|----------|------|
| **localStorage** | Default | Semua data dokumen, template, pengaturan |
| **GitHub Gist** | Cloud backup | Backup terenkripsi via token pribadi |
| **File JSON** | Export/Import manual | File `.json` yang bisa diunduh |

---

## Teknologi

- **HTML5** - Struktur semantik
- **CSS3** - Keyframe animations, transitions, flexbox, grid, CSS variables
- **Vanilla JavaScript** - ES6+, tanpa framework (zero dependency)
- **GitHub REST API** - Untuk sinkronisasi Gist
- **Canvas API** - Untuk efek Constellation mouse trail

---

## Catatan Keamanan

- Token GitHub disimpan di **localStorage browser** (sisi client)
- Gist yang dibuat bersifat **private** (tidak public)
- Tidak ada data yang dikirim ke server selain GitHub API
- Semua data tetap berada di bawah kontrol pengguna

---

## Browser Support

| Browser | Support |
|---------|---------|
| Chrome/Edge | Dukung penuh |
| Firefox | Dukung penuh |
| Safari | Dukung penuh |
| Opera | Dukung penuh |

---

## Lisensi

Free to use - untuk keperluan personal dan profesional.
