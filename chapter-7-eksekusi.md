# Bab 7: Metodologi Eksekusi

## Dari Ide ke Submisi Pemenang

Setelah ide ditentukan, eksekusi dalam hackathon harus mengikuti pola yang **meminimalkan gesekan bagi juri**. Berdasarkan pedoman dari **ETHGlobal** dan program akselerator lainnya, **kualitas submisi sering kali sama pentingnya** dengan kualitas kode itu sendiri.

{% hint style="danger" %}
Banyak proyek dengan kode brilian gagal menang karena **submisi yang buruk**. Sebaliknya, proyek sederhana dengan submisi yang dipoles sering mengalahkan proyek ambisius yang gagal mendemonstrasikan nilainya.
{% endhint %}

---

## Struktur Minimum Viable Product (MVP)

Juri lebih menghargai **proyek sederhana yang bekerja dengan sempurna** daripada arsitektur ambisius yang penuh bug.

> **"Start Simple"** adalah aturan emas.

### Prinsip 1: Fokus pada Core Loop

Demonstrasikan **satu alur kerja utama** yang paling penting.

**Contoh good:** Bagaimana agen AI melakukan transaksi mikro secara otomatis (alur tunggal yang lengkap dari awal sampai akhir).

**Contoh bad:** Sistem multi-agent dengan governance, treasury, dan marketplace — semuanya setengah jadi.

### Prinsip 2: UX dan Desain Matter

Proyek yang memiliki **antarmuka yang intuitif** atau **pengalaman pengembang (DX) yang baik** memiliki **keunggulan kompetitif yang signifikan**.

#### Standar Minimum UX untuk Hackathon 2026

- **Onboarding flow** yang dapat dimengerti dalam <30 detik
- **Loading states** yang informatif (bukan blank screen)
- **Error messages** yang manusiawi
- **Mobile responsive** (terutama untuk demo video)

### Prinsip 3: Dokumentasi dan Komitmen Kode

{% hint style="warning" %}
Submisi harus memiliki **riwayat commit yang jelas** di GitHub untuk membuktikan bahwa pekerjaan dilakukan **selama periode hackathon**. **Commit tunggal dalam jumlah besar** di hari terakhir sering kali menjadi alasan **diskualifikasi**.
{% endhint %}

#### Best Practices untuk Git Hygiene

| Praktik | Mengapa Penting |
|---------|----------------|
| Commit kecil dan sering | Bukti pekerjaan organik |
| Pesan commit yang deskriptif | Memudahkan juri menelusuri progres |
| Branch feature yang terstruktur | Menunjukkan kematangan tim |
| README yang lengkap | Entry point untuk juri |
| Demo `.env.example` | Memungkinkan juri menjalankan lokal |

### Struktur Repository yang Disarankan

```
project-root/
├── README.md (deskripsi, demo link, setup)
├── DEMO.md (langkah demo dengan screenshot)
├── ARCHITECTURE.md (diagram dan teknologi)
├── contracts/ (smart contracts dengan tests)
├── frontend/ (UI/UX layer)
├── backend/ (jika ada off-chain components)
├── docs/ (dokumentasi tambahan)
└── .env.example
```

---

## Presentasi dan Demo Video

**Video demo adalah materi paling penting** bagi juri yang melakukan **penilaian secara asinkron**.

### Spesifikasi Teknis Video

#### Durasi

{% hint style="info" %}
Pastikan video berada dalam rentang **2 hingga 4 menit**. Video yang **terlalu pendek atau terlalu panjang** dapat ditolak secara otomatis oleh sistem submission.
{% endhint %}

#### Konten

**Jangan habiskan terlalu banyak waktu pada latar belakang.**

Struktur video pemenang:

| Waktu | Bagian | Tips |
|-------|--------|------|
| 0:00 - 0:20 | Hook + Problem statement | Mulai dengan pain point konkret |
| 0:20 - 2:30 | Demonstrasi fitur dalam aksi | Bagian terpanjang — tunjukkan produk berjalan |
| 2:30 - 3:00 | Arsitektur teknis (singkat) | Diagram + teknologi yang digunakan |
| 3:00 - 3:30 | Roadmap singkat | Apa yang akan dibangun setelah hackathon |
| 3:30 - 4:00 | Tim & call-to-action | Siapa dan bagaimana follow-up |

**Aturan penting:** Gunakan slide **hanya untuk meringkas poin-poin utama**. Mayoritas waktu harus berupa **screen recording produk yang berjalan**.

#### Kualitas Teknis

- **Resolusi minimal 720p** (1080p direkomendasikan)
- **Audio jernih** — gunakan microphone external jika memungkinkan
- **Hindari penggunaan suara AI (text-to-speech) yang tidak alami**
- Volume musik latar **maksimal 20%** dari volume narasi

### Checklist Sebelum Upload Video

- [ ] Durasi antara 2-4 menit
- [ ] Resolusi 720p atau lebih tinggi
- [ ] Audio narasi jelas tanpa noise
- [ ] Demo produk berjalan tanpa bug visual
- [ ] Caption/subtitle untuk aksesibilitas
- [ ] Link ke repository ada di deskripsi
- [ ] Thumbnail yang representatif

---

## Kriteria Penilaian Juri

Memahami **bobot penilaian** memungkinkan tim untuk **mengalokasikan waktu development** secara strategis.

### Tabel Bobot Penilaian Umum

| Aspek Penilaian | Bobot Umum | Fokus Utama Juri |
|-----------------|------------|------------------|
| **Teknis (Technicality)** | 30% - 40% | Kompleksitas masalah & kecanggihan solusi |
| **Inovasi (Originality)** | 20% - 30% | Kebaruan ide atau pendekatan kreatif |
| **Kegunaan (Practicality)** | 20% | Seberapa fungsional & siap pakai proyek tersebut |
| **Desain (UI/UX)** | 10% | Intuisi penggunaan & estetika antarmuka |
| **WOW Factor** | 10% | Kesan unik atau prestasi luar biasa lainnya |

### Strategi Alokasi Waktu Berdasarkan Bobot

Untuk hackathon **48 jam** (sekitar 36 jam efektif), distribusikan:

```
Teknis (35%) ─────────► ~12.5 jam coding inti
Inovasi (25%) ────────► Built-in dari ide awal (sudah ditentukan)
Kegunaan (20%) ───────► ~7 jam polish & testing
Desain (10%) ─────────► ~3.5 jam UI/UX
WOW Factor (10%) ────► ~3.5 jam easter egg / demo flair
Submisi/Video ───────► ~6 jam (sering diabaikan!)
Buffer ──────────────► ~3.5 jam untuk debugging
```

{% hint style="success" %}
**Insight kritis:** Banyak tim mengalokasikan **0% waktu untuk submisi** dan menyesalinya. Sediakan minimal **15-20% dari total waktu** untuk video, README, dan polish submisi.
{% endhint %}

### Checklist Hari Terakhir

24 jam sebelum deadline:

- [ ] Core loop berjalan tanpa bug pada demo path
- [ ] README.md lengkap dengan setup instructions
- [ ] Video demo direkam dan diedit
- [ ] Deployment ke testnet/mainnet selesai
- [ ] Live demo URL berfungsi (jika ada)

6 jam sebelum deadline:

- [ ] Test submission dari fresh browser session
- [ ] Verify all links work (GitHub, video, live demo)
- [ ] Cross-check semua track requirements terpenuhi
- [ ] Submit FORMULIR submission (jangan tunggu menit terakhir!)

---

## Pitfall Umum yang Harus Dihindari

### Pitfall 1: Over-engineering di Awal

Tim sering menghabiskan 50% waktu pada arsitektur "yang benar" sebelum punya produk berjalan. **Solusi:** Build the ugly version first, beautify last.

### Pitfall 2: Tidak Membaca Track Requirements

Setiap hadiah memiliki kriteria spesifik. Submisi yang tidak memenuhi requirement otomatis didiskualifikasi dari track itu.

### Pitfall 3: Demo yang Tidak Bisa Direproduksi

Jika juri mencoba menjalankan kode dan gagal, kepercayaan hilang. **Selalu uji setup instructions dari fresh environment.**

### Pitfall 4: Mengabaikan Submission Deadline

Banyak hackathon menutup form submission **secara otomatis** pada deadline. Tidak ada toleransi keterlambatan. **Submit minimal 1 jam sebelum deadline.**

### Pitfall 5: Tim Tidak Hadir Saat Judging

Hackathon dengan judging live memerlukan kehadiran tim. **Catat jadwal judging session sejak hari pertama.**

---

*Lanjutkan ke [Bab 8: Kesimpulan & Navigasi Masa Depan](chapter-8-kesimpulan.md) →*
