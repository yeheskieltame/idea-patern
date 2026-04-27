# Bab 7: Metodologi Eksekusi

> **Hook:** Juri ngga punya waktu buat ngehargain genius kamu. Mereka punya 200 submission buat dilihat dalam 4 jam. Submission yang ngga clear = submission yang di-skip.

## Dari Ide ke Winning Submission

Banyak builder ngerjain code 47 jam, lalu ngerjain video demo 1 jam terakhir — dan kalah. Submission yang menang itu **bukan yang paling kompleks**, tapi **yang paling gampang dievaluasi juri**. Bab ini ngasih playbook eksekusi yang udah dipakai pemenang ETHGlobal dan Base Batches.

Setelah ide ditentukan, eksekusi di hackathon harus ngikutin pola yang **minimize friction buat juri**. Berdasarkan guideline dari **ETHGlobal** dan accelerator lain, **submission quality sering kali sama pentingnya** sama code quality.

{% hint style="danger" %}
Banyak proyek dengan code brilian gagal menang gara-gara **submission yang jelek**. Sebaliknya, proyek simple dengan polished submission sering ngalahin proyek ambisius yang gagal demo.
{% endhint %}

---

## MVP Structure (Minimum Viable Product)

Juri lebih ngehargain **proyek simple yang jalan sempurna** daripada **arsitektur ambisius yang full bug**.

> **"Start Simple"** adalah aturan emas.

### Prinsip 1: Fokus ke Core Loop

Demo-in **satu main workflow** yang paling penting.

**Contoh good:** Gimana AI agent ngelakuin micropayment otomatis (single flow lengkap dari awal sampai akhir).

**Contoh bad:** Multi-agent system dengan governance, treasury, dan marketplace — semua setengah jadi.

### Prinsip 2: UX dan Design Matters

Proyek yang punya **intuitive interface** atau **good developer experience (DX)** punya **competitive advantage** signifikan.

#### Standar Minimum UX untuk Hackathon 2026

- **Onboarding flow** yang bisa dimengerti dalam <30 detik
- **Loading states** yang informatif (bukan blank screen)
- **Error messages** yang humane
- **Mobile responsive** (terutama buat demo video)

### Prinsip 3: Documentation dan Code Commits

{% hint style="warning" %}
Submission harus punya **clear commit history** di GitHub buat ngebukti kerjaan dilakuin **selama periode hackathon**. **Single massive commit** di hari terakhir sering jadi alasan **disqualification**.
{% endhint %}

#### Best Practices untuk Git Hygiene

| Practice | Kenapa Penting |
|----------|----------------|
| Commit kecil dan sering | Bukti kerjaan organik |
| Descriptive commit message | Mudah buat juri telusurin progress |
| Structured feature branches | Nunjukin maturity tim |
| Lengkap README | Entry point buat juri |
| Demo `.env.example` | Juri bisa run lokal |

### Recommended Repository Structure

```
project-root/
├── README.md (deskripsi, demo link, setup)
├── DEMO.md (demo steps + screenshots)
├── ARCHITECTURE.md (diagram + teknologi)
├── contracts/ (smart contracts dengan tests)
├── frontend/ (UI/UX layer)
├── backend/ (off-chain components kalau ada)
├── docs/ (dokumentasi tambahan)
└── .env.example
```

### Pro Tip: Setup AI-Assisted Development dari Awal

{% hint style="success" %}
Sebelum mulai coding, setup AI-assisted dev environment dengan resource LLM-friendly:

1. Download `llms.txt` / `llms-full.txt` dari protocol target
2. Install **MCP server** untuk RPC chain target (biar AI bisa query on-chain langsung)
3. Pasang **Claude Skills** atau **Cursor rules** yang relevan
4. Save ke folder `.cursor/` atau `.claude/` di repo

Ini ngehemat 30-40% waktu debugging karena AI assistant kamu udah punya context akurat.
{% endhint %}

---

## Demo Video dan Presentation

**Demo video adalah materi paling penting** buat juri yang ngelakuin **async judging**.

### Spesifikasi Teknis Video

#### Durasi

{% hint style="info" %}
Pastiin video ada di range **2 sampai 4 menit**. Video yang **terlalu pendek atau terlalu panjang** bisa di-reject otomatis sama submission system.
{% endhint %}

#### Konten

**Jangan habisin terlalu banyak waktu di background.**

Struktur video pemenang:

| Waktu | Bagian | Tips |
|-------|--------|------|
| 0:00 - 0:20 | Hook + problem statement | Mulai dengan concrete pain point |
| 0:20 - 2:30 | Demo fitur dalam aksi | Bagian terpanjang — tunjukin product berjalan |
| 2:30 - 3:00 | Technical architecture (singkat) | Diagram + teknologi yang dipake |
| 3:00 - 3:30 | Roadmap singkat | Apa yang bakal dibangun setelah hackathon |
| 3:30 - 4:00 | Tim & call-to-action | Siapa dan gimana follow-up |

**Aturan penting:** Pakai slide **cuma buat ngeringkas main points**. Mayoritas waktu harus berupa **screen recording product yang berjalan**.

#### Technical Quality

- **Resolusi minimal 720p** (1080p direkomendasiin)
- **Audio jernih** — pakai external microphone kalau bisa
- **Hindari penggunaan AI text-to-speech** yang ngga natural
- Background music volume **maksimal 20%** dari volume narasi

### Checklist Sebelum Upload Video

- [ ] Durasi antara 2-4 menit
- [ ] Resolusi 720p atau lebih tinggi
- [ ] Audio narasi jelas tanpa noise
- [ ] Demo product berjalan tanpa visual bug
- [ ] Caption/subtitle untuk aksesibilitas
- [ ] Link ke repository ada di deskripsi
- [ ] Thumbnail yang representatif

---

## Judging Criteria

Pahamin **bobot penilaian** ngebuat tim bisa **alokasiin waktu development** strategis.

### Tabel Bobot Penilaian Umum

| Aspek Penilaian | Bobot Umum | Fokus Utama Juri |
|-----------------|------------|------------------|
| **Technicality** | 30% - 40% | Kompleksitas masalah & sophistication solusi |
| **Originality** | 20% - 30% | Kebaruan ide atau pendekatan kreatif |
| **Practicality** | 20% | Seberapa functional & ready-to-use |
| **Design (UI/UX)** | 10% | Intuisi penggunaan & estetika interface |
| **WOW Factor** | 10% | Kesan unik atau prestasi luar biasa |

### Strategi Time Allocation Berdasarkan Bobot

Buat hackathon **48 jam** (sekitar 36 jam efektif), distribusiin:

```
Technicality (35%) ─────► ~12.5 jam core coding
Originality (25%) ──────► Built-in dari ide awal (udah ditentuin)
Practicality (20%) ─────► ~7 jam polish & testing
Design (10%) ───────────► ~3.5 jam UI/UX
WOW Factor (10%) ───────► ~3.5 jam easter egg / demo flair
Submission/Video ──────► ~6 jam (sering diabaikan!)
Buffer ────────────────► ~3.5 jam buat debugging
```

{% hint style="success" %}
**Critical insight:** Banyak tim alokasiin **0% waktu buat submission** dan nyeselin. Sediain minimal **15-20% dari total waktu** buat video, README, dan submission polish.
{% endhint %}

### Checklist Last Day

24 jam sebelum deadline:

- [ ] Core loop berjalan tanpa bug di demo path
- [ ] README.md lengkap dengan setup instructions
- [ ] Demo video direkam dan diedit
- [ ] Deployment ke testnet/mainnet selesai
- [ ] Live demo URL berfungsi (kalau ada)

6 jam sebelum deadline:

- [ ] Test submission dari fresh browser session
- [ ] Verify all links work (GitHub, video, live demo)
- [ ] Cross-check semua track requirement terpenuhi
- [ ] Submit FORM submission (jangan tunggu menit terakhir!)

---

## Pitfall Umum yang Harus Dihindari

### Pitfall 1: Over-engineering di Awal

Tim sering ngehabisin 50% waktu di "correct architecture" sebelum punya product berjalan. **Solution:** Build the ugly version first, beautify last.

### Pitfall 2: Ngga Baca Track Requirements

Tiap prize punya specific criteria. Submission yang ngga match requirement otomatis disqualified dari track itu.

### Pitfall 3: Demo yang Ngga Reproducible

Kalau juri nyoba run code dan gagal, kepercayaan hilang. **Selalu test setup instructions dari fresh environment.**

### Pitfall 4: Ngabaiin Submission Deadline

Banyak hackathon nutup submission form **otomatis** di deadline. Ngga ada toleransi keterlambatan. **Submit minimal 1 jam sebelum deadline.**

### Pitfall 5: Tim Ngga Hadir Saat Judging

Hackathon dengan live judging butuh kehadiran tim. **Catat jadwal judging session dari hari pertama.**

---

*Lanjutkan ke [Bab 8: Kesimpulan & Roadmap](chapter-8-kesimpulan.md) →*

---

*Made with ☕ by [Dev Web3 Jogja Community](https://devweb3-jogja.gitbook.io/idea/) — for builders, by builders.*
