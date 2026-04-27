# Bab 9: Cheatsheet Brainstorming Ide Hackathon

> **Hook:** Habis baca 8 bab teori, sekarang waktunya **action**. Print bab ini, tempel di tembok, eksekusi step by step.

Cheatsheet ini adalah **workflow praktis** dari nol sampai dapat ide yang siap di-build. Ikuti urutannya — setiap step menyiapkan konteks untuk step berikutnya.

> **Gunain bareng AI:** Tiap step di bawah punya prompt template siap pakai. Pakai **Grok** untuk research (Step 1, 3, 4) karena native X access. Pakai **Claude/Gemini** untuk architecture (Step 5) karena reasoning lebih dalam.

{% hint style="info" %}
**Filosofi utama:** AI sekarang sangat membantu untuk research dan brainstorm, tapi kualitas output AI bergantung pada kualitas konteks yang kamu kasih. Step 1-3 di bawah adalah soal **mengumpulkan konteks**, baru step 4-6 soal **menggunakan AI** untuk generate dan refine ide.
{% endhint %}

---

## Step 1: Riset Penyelenggara (Sponsor Discovery)

Sebelum mikirin ide, **kenali dulu siapa yang nyelenggarain** dan apa yang mereka cari.

### Yang harus dikumpulin:

- [ ] **Nama hackathon + penyelenggara utama** (foundation, exchange, atau protocol?)
- [ ] **Daftar sponsor & partner** — sering ada bounty terpisah per sponsor
- [ ] **Total prize pool** dan breakdown per track
- [ ] **Deadline submission** + jadwal judging
- [ ] **Format judging** (live demo, async video, atau hybrid)
- [ ] **Track tematik** yang tersedia
- [ ] **Eligibility** (region, tim size, open source requirement)

### Sumber yang dicek:

| Sumber | Yang dicari |
|--------|------------|
| Landing page hackathon | Overview umum, deadline, prize |
| Twitter/X penyelenggara | Update real-time, signal vertikal yang dipush |
| Discord/Telegram resmi | Q&A peserta lain, klarifikasi rules |
| Past winners (showcase) | Standar kualitas, pola yang sering menang |
| Blog/Medium sponsor | Thesis investasi, vertikal yang lagi panas |

### Tips Grok untuk step ini:

{% hint style="success" %}
**Grok punya akses native ke X (Twitter)** — pakai ini untuk dapat info paling fresh tentang hackathon Web3. Twitter/X masih jadi pusat percakapan Web3, dan Grok bisa surface tweet-tweet relevan yang belum ke-index Google.

**Contoh prompt Grok:**
> "Cariin info tentang [nama hackathon] 2026, siapa sponsor utamanya, track apa aja, dan trending vertikal apa yang dibahas peserta di X dalam 2 minggu terakhir."
{% endhint %}

---

## Step 2: Kumpulkan Docs Teknologi (Tech Stack Discovery)

Setelah tahu sponsor, kumpulin **dokumentasi teknologi** yang mereka push atau rekomendasikan. Ini penting karena banyak hackathon kasih bonus prize buat proyek yang pakai stack mereka.

### Yang harus dikumpulin:

- [ ] **Official docs** dari chain/protocol utama
- [ ] **SDK/library docs** yang direkomendasikan
- [ ] **Smart contract examples** atau template
- [ ] **API reference** kalau ada layanan off-chain
- [ ] **Tutorial & cookbook** dari tim devrel
- [ ] **Repo contoh** di GitHub (search: `awesome-[chain-name]`)

### Cari resource yang LLM-friendly

{% hint style="warning" %}
**Penting:** Sebelum bikin prompt ke AI, cek dulu apakah teknologi yang kamu pakai punya resource khusus untuk LLM. Ini bikin AI jauh lebih akurat saat bantu coding/desain arsitektur.

**Yang harus dicari:**

1. **`llms.txt` atau `llm.txt`** — file standar di root domain docs (contoh: `docs.protocol.com/llms.txt`) yang berisi versi ringkas docs untuk dikonsumsi LLM. Banyak project Web3 modern udah punya ini.

2. **Claude Skills** — kalau pakai Claude Code, cek apakah ada skill resmi atau community untuk teknologi tersebut (contoh: `solidity`, `foundry`, `anchor-solana`).

3. **MCP servers** — Model Context Protocol servers yang nyambungin AI ke tooling. Cari di [github.com/modelcontextprotocol/servers](https://github.com/modelcontextprotocol/servers) atau community registry. Contoh yang berguna:
   - MCP untuk RPC blockchain (query on-chain data langsung dari AI)
   - MCP untuk GitHub (akses repo & PR dari conversation)
   - MCP untuk docs (search docs tanpa keluar dari AI)

4. **`/docs/llms-full.txt`** — versi panjang dari llms.txt, biasanya seluruh docs digabung jadi satu file siap-paste ke context window.
{% endhint %}

### Cara cek cepat ada `llms.txt` atau ngga:

```bash
# Coba akses langsung
curl https://docs.[nama-protocol].com/llms.txt
curl https://docs.[nama-protocol].com/llms-full.txt

# Atau search di Google
site:docs.[nama-protocol].com llms.txt
```

Kalau ada, **download dan simpan lokal** — bisa di-attach ke chat AI sebagai context.

---

## Step 3: Identifikasi Pain Points & Gaps

Sekarang konteks udah lengkap (sponsor + docs). Saatnya cari **masalah yang worth dipecahin**.

### Tempat nyari pain points:

| Tempat | Yang dilihat |
|--------|-------------|
| **GitHub Issues** repo populer | Label `help wanted`, `enhancement`, `bug` yang lama belum di-close |
| **Discord #suggestions** | Request berulang dari multiple user |
| **Twitter/X search** | Keyword: "wish there was", "frustrating", "kenapa belum ada" |
| **Reddit r/ethereum, r/solana** | Thread pain points dari developer |
| **Wishlist resmi** | EF ESP Wishlist, RFP Hub |
| **Past hackathon submissions** | Lihat ide yang gagal — ada gap yang bisa di-improve |

### Filter pain point yang bagus:

Pain point yang **layak dijadiin proyek hackathon** harus memenuhi:

1. ✅ **Disebut berulang** oleh banyak orang (bukan cuma 1-2 keluhan)
2. ✅ **Belum ada solusi yang bagus** (atau solusi existing punya weakness jelas)
3. ✅ **Bisa di-prototype dalam 2-4 minggu** (scope realistis)
4. ✅ **Selaras dengan track sponsor** (biar dapet multiple bounty)
5. ✅ **Punya pengguna jelas** (bukan solusi tanpa user)

---

## Step 4: Brainstorm Garis Besar Ide dengan Grok

Setelah punya konteks (Step 1-3), waktunya **generate ide kasar** dulu.

### Kenapa pakai Grok untuk step ini:

- **Native X access** — Grok bisa cross-reference apa yang lagi dibicarain di Web3 Twitter saat ini
- **Real-time info** — Update lebih cepat soal hackathon, launch, dan trend
- **Tone yang lebih casual** — Cocok buat phase eksplorasi liar

### Template prompt Grok untuk ideasi:

```
Konteks:
- Aku ikut hackathon: [nama hackathon]
- Sponsor utama: [list sponsor]
- Track yang aku target: [track 1, track 2]
- Stack teknologi yang aku kuasai: [Solidity/Rust/TS/Python]
- Pain points yang udah aku temuin: [list 3-5 pain points dari Step 3]

Tugas:
1. Generate 10 ide proyek yang nyambung dengan track di atas
2. Setiap ide kasih: nama, 1-line pitch, vertikal, why now
3. Tandain ide mana yang lagi trending di Web3 X 2 minggu terakhir
4. Skip ide yang udah saturated (banyak kompetitor di showcase ETHGlobal)
```

### Filter hasil dari Grok:

Dari 10 ide yang dikasih, biasanya cuma 2-3 yang **layak diteruskan**. Filter pakai kriteria:

- Apakah aku punya **proprietary insight** soal ide ini?
- Apakah scope-nya realistis untuk durasi hackathon?
- Apakah cocok dengan **multiple track** (biar bisa dapet bounty berlapis)?

---

## Step 5: Refine Arsitektur dengan Claude/Gemini

Setelah punya 2-3 ide kandidat dari Grok, **dalemin arsitekturnya** pakai Claude atau Gemini.

### Kenapa Claude/Gemini untuk step ini:

- **Reasoning lebih dalam** untuk desain teknis
- **Context window besar** — bisa load seluruh `llms-full.txt` dan ratusan baris code
- **Output structured** untuk diagram dan spec teknis

### Template prompt Claude/Gemini untuk arsitektur:

```
Aku mau bangun: [1-line pitch dari Step 4]

Stack:
- Chain: [Ethereum / Base / Solana / Hedera]
- Smart contract language: [Solidity / Rust / Move]
- Frontend: [Next.js / SvelteKit]
- Off-chain services: [list jika ada]

Aku attach docs LLM-friendly dari [protocol]: [paste llms-full.txt atau attach file]

Tolong bantuin:
1. Desain arsitektur high-level (komponen + data flow)
2. Identifikasi smart contract primitives yang dibutuhin
3. List API/SDK calls yang relevan dari docs di atas
4. Pinpoint risiko teknis utama (gas cost, security, scalability)
5. Saran MVP scope yang realistis dalam [X jam/hari] hackathon
```

### Iterasi sampai dapet desain yang solid:

- **Round 1:** High-level architecture
- **Round 2:** Detail per komponen
- **Round 3:** Edge cases & failure modes
- **Round 4:** MVP cut — apa yang in-scope vs out-of-scope

{% hint style="success" %}
**Pro tip:** Kalau Claude/Gemini-mu punya akses ke MCP RPC blockchain, kamu bisa minta dia **verify on-chain** apakah primitive yang didesain udah ada atau belum. Ini jauh lebih akurat daripada cuma reasoning dari memory training.
{% endhint %}

---

## Step 6: Validasi Ide dengan Komunitas

Sebelum mulai coding **full speed**, validasi dulu ide ke komunitas. 30 menit di sini bisa save 30 jam coding ke arah yang salah.

### Cara validasi cepat:

| Channel | Yang ditanyain |
|---------|---------------|
| Discord hackathon | "Apakah ide ini fit untuk track [X]?" |
| Twitter/X | Post 1-line pitch, lihat engagement |
| Mentor session (kalau ada) | "Apakah scope MVP-ku realistis?" |
| Past winners | DM ke pemenang tahun lalu, minta feedback |

### Red flags yang harus diwaspadai:

- 🚩 **Mentor langsung bilang "udah pernah ada"** — cek showcase, mungkin perlu pivot
- 🚩 **Sponsor representative diem** — biasanya signal ide ngga sesuai vision mereka
- 🚩 **Kompleksitas teknis bikin mentor ragu** — over-scoped, perlu disederhanain
- 🚩 **Ngga ada yang nanya soal kasus pengguna** — mungkin solusi tanpa problem

---

## Cheatsheet Quick-Reference

### Tools per Step

| Step | Tool Utama | Fungsi |
|------|-----------|--------|
| 1. Sponsor research | **Grok** | Real-time X intel, sponsor signal |
| 2. Tech docs | **`llms.txt`, MCP, Skills** | LLM-ready docs |
| 3. Pain points | **Grok + GitHub** | Issue mining, X pain points |
| 4. Idea generation | **Grok** | Liar, fresh, X-aware |
| 5. Architecture | **Claude / Gemini** | Deep reasoning, big context |
| 6. Validation | **Community** | Sanity check |

### Yang Harus Selalu Dicari Sebelum Coding

```
□ llms.txt / llms-full.txt dari protocol
□ Claude Skill resmi atau community
□ MCP server untuk chain target
□ MCP GitHub buat akses repo cepet
□ Awesome-list di GitHub
□ Devrel video tutorial terbaru
```

### Anti-Pattern yang Harus Dihindari

| Anti-Pattern | Kenapa Salah |
|--------------|--------------|
| Langsung coding tanpa Step 1-3 | Build sesuatu yang ngga align dengan sponsor |
| Cuma pakai 1 AI buat semua step | Tiap AI punya strength berbeda |
| Skip cari `llms.txt` | AI kasih info outdated/halu |
| Nanya AI tanpa attach docs | Output generic, ngga specific ke stack |
| Brainstorm sendirian tanpa validasi | Wasted effort kalau ide gak fit |

---

## Workflow Visual: 6 Step Brainstorming

```
┌─────────────────────────────────────────────────────────┐
│  STEP 1: Riset Penyelenggara                            │
│  → Grok (X intel) + landing page + Discord             │
└────────────────────────┬────────────────────────────────┘
                         ▼
┌─────────────────────────────────────────────────────────┐
│  STEP 2: Kumpulkan Docs Tech Stack                      │
│  → Cari llms.txt, MCP, Skills (LLM-friendly resources) │
└────────────────────────┬────────────────────────────────┘
                         ▼
┌─────────────────────────────────────────────────────────┐
│  STEP 3: Identifikasi Pain Points                       │
│  → GitHub Issues + Discord + Wishlist                  │
└────────────────────────┬────────────────────────────────┘
                         ▼
┌─────────────────────────────────────────────────────────┐
│  STEP 4: Generate Ide dengan Grok                       │
│  → 10 ide kasar → filter jadi 2-3 kandidat             │
└────────────────────────┬────────────────────────────────┘
                         ▼
┌─────────────────────────────────────────────────────────┐
│  STEP 5: Desain Arsitektur dengan Claude/Gemini         │
│  → Attach llms.txt, iterasi 4 round                    │
└────────────────────────┬────────────────────────────────┘
                         ▼
┌─────────────────────────────────────────────────────────┐
│  STEP 6: Validasi ke Komunitas                          │
│  → Discord, Twitter, Mentor session                    │
└────────────────────────┬────────────────────────────────┘
                         ▼
                   READY TO BUILD
```

---

## Bonus: Prompt Templates Siap Pakai

### Template 1: Sponsor Research (Grok)

```
Aku mau ikut [hackathon name]. Tolong rangkum:
1. Siapa main sponsor & cita-cita strategis mereka
2. Track apa aja yang dibuka & prize per track
3. Proyek pemenang tahun lalu (kalau ada)
4. Vertikal apa yang lagi heavily promoted di X 2 minggu terakhir
5. Mentor & judge yang udah diumumin (cek background mereka)
```

### Template 2: Technology Deep Dive (Claude)

```
Aku mau pakai [protocol/SDK]. Aku attach llms-full.txt mereka.

Tolong:
1. Summarize core primitives yang available
2. List 5 use case yang underexplored tapi feasible
3. Highlight gotcha & common mistakes
4. Saran tooling pendukung (testing, deployment, monitoring)
```

### Template 3: Idea-to-Architecture (Claude/Gemini)

```
Ide: [1-line pitch]
Target user: [ICP]
Pain point yang dipecahin: [pain point]

Stack: [list tech]
Durasi hackathon: [X hari]
Tim size: [N orang]

Desain MVP yang:
- Bisa di-demo dalam 3 menit video
- Punya 1 core loop yang fully working
- Scope realistis untuk durasi & tim size
- Maximize coverage track sponsor (list track)
```

### Template 4: Pre-Submission Review (Claude)

```
Aku mau submit proyek ke [hackathon]. Berikut:
- Repo: [link]
- Demo video: [link]
- README: [paste]

Review submission-ku:
1. Apakah README cukup buat juri reproduce setup?
2. Apakah video struktur 0:00-0:20 hook, 0:20-2:30 demo, dst?
3. Apakah covered semua track requirement: [list]?
4. Red flag yang bikin auto-DQ?
```

---

*Kembali ke [Daftar Isi](SUMMARY.md) | Lanjut ke [Glosarium →](glossary.md)*

---

*Made with ☕ by [Dev Web3 Jogja Community](https://devweb3-jogja.gitbook.io/devweb3-jogja-docs/) — for builders, by builders.*
