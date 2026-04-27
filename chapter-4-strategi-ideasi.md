# Bab 4: Strategi Penentuan Ide

> **Hook:** Ide paling kreatif jarang menang. Ide paling **align** yang menang. Ada bedanya — dan bab ini ngajarin kamu cara nyari yang kedua.

## Selaraskan Kreativitas dengan Ecosystem Gaps

Builder pemula sering kejebak: nyari ide "yang belum pernah dipikirin orang." Padahal sponsor justru nyari **ide yang udah mereka pikirin tapi belum ada yang bikin** — itu yang ada di Wishlist dan RFP mereka. Selaraskan kreativitas kamu sama gap yang udah didokumentasikan, dan peluang menang naik drastis.

Nentuin ide hackathon yang menang butuh metodologi yang **lebih dari sekadar ngikutin tren**. Berdasarkan praktik dari **Alchemy** dan sponsor besar lainnya, strategi ideasi yang efektif harus bersandar pada:

1. Identifikasi **pain points** yang nyata
2. Alignment dengan **technical priority** sponsor
3. **Market validation** yang terbukti

{% hint style="info" %}
Untuk workflow brainstorming langkah-demi-langkah pakai Grok, Claude, dan Gemini, langsung lompat ke [Bab 9: Cheatsheet Brainstorming](chapter-9-cheatsheet-brainstorming.md). Bab ini fokus ke **kerangka konseptual**, bab 9 fokus ke **eksekusi praktis**.
{% endhint %}

---

## Wishlist dan RFP Approach

Buat builder yang mau **minimize rejection risk**, cara paling aman: build sesuatu yang **udah diminta ekosistem**.

### Cara Kerja Wishlist

Banyak foundation publish **Wishlist** atau **RFP** yang spesifik tentang tooling atau infrastruktur yang mereka butuhin.

{% hint style="info" %}
**Ethereum Foundation ESP Wishlist** ngehighlight kebutuhan akan **existing tooling** kayak:
- **Compiler**
- **Testing framework**
- **Account abstraction infrastructure**
{% endhint %}

### Keuntungan Approach Ini

Build solusi dari item wishlist kasih jaminan:

- ✅ Ada **judging audience** yang udah nungguin solusi
- ✅ Kebutuhan udah divalidasi sama ekosistem
- ✅ Risk ditolak karena "ngga relevan" sangat rendah
- ✅ Potensi **follow-up grant** lebih tinggi

### Daftar Sumber Wishlist Aktif 2026

| Ekosistem | Sumber Wishlist | Update |
|-----------|----------------|--------|
| Ethereum | Ethereum Foundation ESP | Mingguan |
| Solana | Superteam Earn Idea Bank | Harian |
| Base | Coinbase Ventures Thesis | Triwulanan |
| Hedera | Hedera Apex Track Briefs | Per event |

### Tips: Cari Resource LLM-Friendly Sebelum Build

{% hint style="success" %}
**Sebelum mulai build**, cek apakah protocol target punya resource LLM-friendly. Ini bikin AI assistant kamu (Claude, Gemini, Cursor, dll) jauh lebih akurat.

Yang dicari:
- **`llms.txt` / `llms-full.txt`** di root domain docs
- **Claude Skills** atau **Cursor rules** resmi
- **MCP server** untuk RPC, GitHub, atau docs

Detail di [Bab 9](chapter-9-cheatsheet-brainstorming.md).
{% endhint %}

---

## Alchemy Ideation Framework

**Alchemy** nyaranin framework **7 langkah** untuk nyusun ide hackathon yang kuat.

### Langkah 1: Pakai Tooling Web3 Terbaru dari Sponsor

Sponsor mau liat **tech baru mereka diuji praktis**. Build di atas tooling terbaru sponsor kasih sinyal positif ke juri.

### Langkah 2: Cari Public Complaints

Pantau platform sosial buat nemu **pain points**:

- **Twitter/X** — Search keyword: "frustrating", "broken", "wish there was", "kenapa belum ada"
- **Discord** — Channel `#suggestions` di komunitas protocol
- **GitHub Issues** — Repo populer dengan label `enhancement` atau `help wanted`

### Langkah 3: Identifikasi Functionality Gaps

Lewat monitoring channel `#suggestions` atau diskusi teknis di GitHub, tim bisa nemuin **functionality gaps** di aplikasi populer saat ini.

### Langkah 4: Build "Building Blocks"

{% hint style="success" %}
Ide paling bernilai sering kali adalah **building blocks** yang **composable** — proyek yang bisa dipake developer lain buat build sesuatu yang lebih besar.
{% endhint %}

### Langkah 5: Validasi ke Komunitas

Sebelum nulis code, post ide di forum atau Discord buat dapet **early feedback**.

### Langkah 6: Cek Kompetitor

Search di **DoraHacks** dan **ETHGlobal Showcase** apakah ide serupa udah ada. Kalau udah, tentuin **unique differentiator** kamu.

### Langkah 7: Align ke Prize Tracks

Tiap hackathon punya track tematik. Pastiin ide kamu **memenuhi 2-3 track sekaligus** buat maximize **layered prize**.

---

## Market Validation dan GTM

Kalau target accelerator, ide harus didukung **market validation evidence**.

### Kriteria Coinbase Ventures (Base Batches)

**Coinbase Ventures** lewat Base Batches evaluasi tim berdasarkan:

#### "Demonstrated Mastery"

Apakah tim punya **proprietary insights** soal market mereka?

- Pengalaman langsung di industri yang dilayani
- Data atau riset yang ngga dimiliki kompetitor
- Hubungan sama early users yang butuh solusi

#### "Velocity"

Kecepatan tim dalam:

- **Shipping** product
- Testing growth strategy
- Iterasi berdasarkan user feedback

### Komponen Wajib GTM Plan

Di proposal accelerator, GTM plan harus mencakup tiga komponen kritis:

#### 1. Ideal Customer Profile (ICP)

> Siapa user pertama yang bakal **pay atau use** product ini secara konsisten?

Spesifikasi ICP harus mencakup:

- Demografi/psikografi yang jelas
- Pain point spesifik yang dialamin
- **Acquisition channel** yang measurable
- **Willingness to pay** (kalau berbayar)

#### 2. Unique Mission Statement

> Kenapa company ini perlu ada dan apa **specific problem** yang mereka pecahin yang **ngga bisa dipecahin kompetitor**?

Hindari pernyataan generik kayak "kami democratize finance." Spesifikasiin dengan tajem.

#### 3. Success Metrics

> Gimana proyek bakal ngukur growth?

Metrics tipikal yang diakui:

| Vertikal | Key Metrics |
|----------|-------------|
| **DeFi** | TVL, transaction volume, fee generated |
| **Consumer** | DAU/MAU, 30-day retention, NPS |
| **Infrastructure** | API calls, developer adoption, integration partners |
| **Prediction markets** | Open interest, trading volume, resolution accuracy |

---

## Matriks Ideasi: Pilih Vertikal yang Tepat

Pakai matriks ini buat prioritas ide berdasarkan **maturitas tim** dan **market timing**:

| Vertikal | Market Maturity 2026 | Tingkat Kompetisi | Rekomendasi |
|----------|----------------------|-------------------|-------------|
| **AI Agents Payments** | Awal (high upside) | Rendah | ⭐⭐⭐ Sangat direkomendasiin |
| **Stablecoin Infrastructure** | Matang | Tinggi | ⭐⭐ Butuh diferensiasi kuat |
| **RWA Tokenization** | Berkembang | Sedang | ⭐⭐⭐ Sweet spot |
| **Privacy / zk Apps** | Awal-menengah | Sedang | ⭐⭐⭐ Strategis |
| **Generic DeFi** | Saturasi | Sangat tinggi | ⭐ Hindari kecuali ada inovasi besar |
| **Prediction Markets** | Berkembang cepat | Tinggi | ⭐⭐ Butuh distribusi unik |

---

## Checklist Sebelum Mulai Coding

Sebelum nulis baris code pertama, pastiin ide kamu memenuhi:

- [ ] Align minimal **satu wishlist atau RFP** dari sponsor
- [ ] Punya **clear differentiation** dari proyek serupa di showcase
- [ ] Bisa di-demo dalam **2-4 menit video**
- [ ] Memenuhi minimal **2 prize tracks** sekaligus
- [ ] Punya **satu success metric** yang bisa ditampilin saat demo
- [ ] Tim punya **proprietary insight** soal masalah yang dipecahin
- [ ] Udah cek `llms.txt` / Skills / MCP buat tech stack yang dipake

---

*Lanjutkan ke [Bab 5: Studi Kasus Program 2026](chapter-5-studi-kasus.md) →*

---

*Made with ☕ by [Dev Web3 Jogja Community](https://devweb3-jogja.gitbook.io/devweb3-jogja-docs/) — for builders, by builders.*
