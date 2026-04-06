# WS-02: Problem Statement

> **Bab 2 — Problem Formulation & System Context**

---

## Ringkasan Materi

### Problem Formation Model

Masalah riset melewati 5 tahap transformasi. Melompat langsung dari Reality ke Variable adalah kesalahan paling umum.

```
Reality → Observed Issue (Symptom) → Diagnosed Problem (Root Cause)
→ Researchable Problem (Scoped) → Measurable Variable (Operationalized)
```

### Topic ≠ Problem ≠ Research Problem

| Level | Contoh | Status |
|-------|--------|--------|
| **Topik** | Keamanan IoT | Terlalu luas, tidak bisa diuji |
| **Problem** | MQTT tidak terenkripsi | Spesifik tapi belum riset |
| **Research Problem** | Belum ada studi membandingkan overhead TLS 1.3 vs DTLS pada MQTT di IoT RAM < 64KB | Bisa dirancang eksperimennya |

### Symptom vs Root Cause

Apa yang diamati (gejala) ≠ mengapa terjadi (akar masalah). Gunakan **5 Whys** atau **Fishbone Diagram** untuk menggali.

Contoh: "User meninggalkan checkout" (symptom) → "Waktu loading > 8 detik karena API call sequential" (root cause).

### System Thinking

Setiap masalah riset TI harus terikat pada komponen sistem: **Input → Process → Output → Outcome → Constraints → Stakeholders**.

### Problem Quality Check

Masalah riset yang layak harus memenuhi 5 kriteria:
- **Clarity** — Satu orang membaca akan paham
- **Measurability** — Ada metrik kuantitatif
- **Relevance** — Penting untuk domain
- **Testability** — Bisa gagal (falsifiable)
- **Impact** — Ada kontribusi jika terjawab

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Tujuan | Menyelesaikan masalah (*solve*) | Memahami dan membuktikan (*understand & prove*) |
| Masalah | Bug, error, fitur belum ada | Gap dalam pengetahuan |
| Scope | Selesaikan semua yang perlu | Batasi agar bisa dibuktikan |
| Output | Working system | Evidence, paper, replicable findings |

### Istilah Penting

- **Problem Statement** — Formulasi tertulis: konteks sistem + gap + dampak + justifikasi
- **System Context** — Deskripsi lengkap: input, proses, output, outcome, constraints, stakeholders
- **Problem Drift** — Masalah "bermutasi" dari pendahuluan ke metodologi karena statement awal tidak presisi
- **Solution-First Thinking** — Memulai dari solusi tanpa masalah yang jelas — berbahaya dalam riset
- **Operational Definition** — Definisi variabel yang cukup jelas agar peneliti lain bisa mengukur hal yang sama

---

## Template A.2 — Problem Statement Builder

```
PROBLEM STATEMENT BUILDER

Domain & Konteks
  Domain   : Human-Computer Interaction (HCI) / Interaksi Manusia dan Komputer.
  Konteks  : Efisiensi navigasi pada aplikasi dompet digital (E-wallet).

System Context
  Input       : Skenario tugas transaksi (misal: Transfer uang/Scan QRIS), perangkat smartphone, dan aplikasi (DANA & GoPay).
  Process     : Pengujian kegunaan (usability testing), observasi langsung, dan pengukuran waktu menggunakan stopwatch.
  Output      : Data kuantitatif berupa durasi waktu (time on task) dan jumlah klik pengguna.
  Outcome     : Rekomendasi model arsitektur informasi yang paling efisien untuk mempercepat transaksi pengguna.
  Constraints : Variasi kecepatan internet (latensi) dan spesifikasi RAM perangkat responden.
  Stakeholders: Mahasiswa Ilmu Komputer, UI/UX Researcher, dan pengembang aplikasi finansial.

Fenomena → Problem
  Fenomena yang diamati             : Strategi pengembangan aplikasi yang beralih dari model Super App (fitur padat) ke model Stand-alone App (fitur fokus/sat-set).
  Gejala (symptom) yang terukur     : Pengguna membutuhkan waktu lebih dari 10 detik dan melakukan lebih dari 5 klik hanya untuk menemukan fitur utama.
  Masalah yang didiagnosis          : Information Overload (beban informasi) akibat kepadatan elemen visual pada halaman utama.
  Masalah riset (researchable)      : Perbandingan efisiensi waktu penyelesaian tugas antara desain antarmuka Super App (DANA) dan Stand-alone App (GoPay).
  Variabel yang terukur             : Time on Task (detik) dan Number of Clicks (jumlah klik).

Problem Quality Check
  [X] Clarity — Masalah perbandingan efisiensi dua model aplikasi sangat jelas.
  [X] Measurability — Data berupa angka pasti (detik dan klik) sangat objektif.
  [X] Relevance — Penting bagi industri TI untuk menentukan model aplikasi masa depan.
  [X] Testability — Bisa dibuktikan melalui eksperimen langsung ke pengguna.
  [X] Impact — Memberikan bukti empiris mengenai efektivitas penyederhanaan antarmuka.

Problem Statement (1 paragraf):
  Munculnya fenomena aplikasi stand-alone seperti GoPay App sebagai alternatif dari model super app seperti DANA menimbulkan pertanyaan mengenai efisiensi interaksi pengguna. Meskipun super app menawarkan kelengkapan fitur, kepadatan elemen visual di dalamnya diduga meningkatkan beban kognitif yang memicu keterlambatan waktu transaksi. Riset ini bertujuan untuk membandingkan secara komparatif efisiensi User Experience (UX) kedua model tersebut dengan mengukur variabel time on task dan number of clicks guna membuktikan model mana yang paling optimal bagi produktivitas pengguna.
```

---

## Latihan 1 — Dari Topik ke Masalah Riset

Pilih satu topik di bidang TI yang diminati. Transformasikan melalui 5 tahap Problem Formation Model.

**Topik awal:** Analisis Komparatif Efisiensi UX pada Aplikasi DANA dan GoPay.

| Tahap | Hasil |
|-------|-------|
| Reality | Aplikasi dompet digital memiliki dua gaya desain: sangat padat fitur (DANA) dan sangat minimalis (GoPay). |
| Observed Issue (Symptom) | Pengguna sering terdiam sejenak (scanning delay) saat mencari menu utama pada aplikasi yang padat fitur. |
| Diagnosed Problem (Root Cause) | Kompleksitas arsitektur informasi pada Super App memicu beban kognitif tinggi yang menghambat kecepatan transaksi.|
| Researchable Problem | Sejauh mana perbedaan efisiensi waktu transaksi antara model Super App dan Stand-alone App pada kalangan mahasiswa?|
| Measurable Variable | Completion Time (detik) dan Number of Clicks (jumlah klik jari).|

**Apakah terjebak solution-first thinking?** [ ] Ya / [X] Tidak

---

## Latihan 2 — System Context Decomposition

Gambarkan konteks sistem dari masalah riset di Latihan 1.

| Komponen | Deskripsi |
|----------|----------|
| Input | HP responden, stopwatch, dan instruksi "Transfer Saldo". |
| Process | Menghitung waktu transaksi dari mulai klik aplikasi hingga muncul status "Berhasil".|
| Output | Tabel perbandingan rata-rata waktu (detik) antara DANA dan GoPay.|
| Outcome | Kesimpulan ilmiah mengenai model aplikasi mana yang paling "sat-set".|
| Constraints | Gangguan notifikasi pada HP responden dan perbedaan kelancaran jaringan seluler.|
| Stakeholders | Mahasiswa Ilkom dan praktisi riset UI/UX.|

**Komponen mana yang paling relevan dengan masalah riset?** Process & Output.

---

## Latihan 3 — Problem Quality Check

Evaluasi problem statement yang sudah dibuat menggunakan 5 kriteria.

| Kriteria | Skor (1-5) | Justifikasi |
|----------|-----------|-------------|
| Clarity | 5 | Judul dan tujuan riset sangat spesifik dan mudah dipahami.|
| Measurability | 5| Menggunakan angka mutlak (detik) sehingga tidak ada debat opini.|
| Relevance | 5| Masalah efisiensi adalah inti dari disiplin Ilmu Komputer.|
| Testability | 5| Sangat mudah diuji dengan eksperimen ke teman-teman kampus.|
| Impact | 4| Memberikan kontribusi nyata pada standar desain aplikasi finansial.|

**Skor total:** 24 / 25

**Problem statement versi final (1 paragraf):**
> Munculnya fenomena aplikasi stand-alone seperti GoPay App sebagai alternatif dari model super app seperti DANA menimbulkan pertanyaan mengenai efisiensi interaksi pengguna. Meskipun super app menawarkan kelengkapan fitur, kepadatan elemen visual di dalamnya diduga meningkatkan beban kognitif yang memicu keterlambatan waktu transaksi. Riset ini bertujuan untuk membandingkan secara komparatif efisiensi User Experience (UX) kedua model tersebut dengan mengukur variabel time on task dan number of clicks guna membuktikan model mana yang paling optimal bagi produktivitas pengguna.
> 

---

## Refleksi

> Bandingkan "masalah" yang biasa ditemui saat coding (bug, error) dengan masalah riset. Apa perbedaan fundamental dalam cara mendefinisikan dan mendekati keduanya?

**Jawaban:**
> Perbedaan fundamental antara masalah coding dan masalah riset terletak pada tujuan dan pendekatannya. Masalah Coding bersifat praktis-deterministik, di mana kita mencari cara untuk memperbaiki kesalahan sistem (solve a bug) agar aplikasi berjalan normal. Sedangkan Masalah Riset bersifat teoritis-eksploratif, di mana kita mencari bukti atau alasan mengapa suatu fenomena terjadi (understand a gap). Dalam coding, kita berhadapan dengan mesin yang "mati", namun dalam riset TI, kita berhadapan dengan interaksi sistem dan manusia yang hasilnya harus dibuktikan melalui data variabel yang terukur secara objektif.
> 