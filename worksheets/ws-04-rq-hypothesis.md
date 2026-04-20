# WS-04: Research Question & Hypothesis

> **Bab 4 — Research Question, Contribution & Hypothesis**

---

## Ringkasan Materi

### RQ Bukan Pertanyaan Biasa

Research Question yang baik secara implisit mengandung cetak biru eksperimen: subjek, baseline, metrik, domain, dataset.

| Kualitas | Contoh |
|----------|--------|
| **Buruk** | "Bagaimana pengaruh deep learning terhadap deteksi malware?" |
| **Baik** | "Apakah CNN menghasilkan F1-Score lebih tinggi dari RF pada CIC-MalMem-2022?" |

Perbedaan: RQ yang baik menyebutkan **metode spesifik**, **metrik terukur**, **baseline**, dan **dataset**.

### Tiga Jenis RQ

| Jenis | Pola | Kebutuhan |
|-------|------|-----------|
| **Comparison** | A vs B → mana lebih baik? | ≥ 2 metode, metrik sama |
| **Improvement** | A' vs A → modifikasi lebih baik? | Pre/post, bukti perbaikan |
| **Exploratory** | Faktor X₁...Xₙ → pengaruh terhadap Y? | Multi-variabel, korelasi/regresi |

### Contribution Statement

Tiga jenis kontribusi: **Improvement** (metode terbukti lebih baik), **Comparison** (perbandingan sistematis yang belum ada), **Novel Approach** (pendekatan baru). Kontribusi harus terhubung langsung dengan gap — kontribusi tanpa gap = klaim tanpa justifikasi.

### Hypothesis H₀ / H₁

- **H₀** (Null) = Tidak ada perbedaan signifikan — asumsi default, harus dibuktikan salah
- **H₁** (Alternative) = Ada perbedaan signifikan — diterima hanya jika H₀ ditolak
- Harus **falsifiable**, mengandung **metrik terukur**, dirumuskan **SEBELUM eksperimen**

### Rantai Operasionalisasi

```
RQ → Variable → Metric → Data → Analysis
```

Jika rantai ini tidak lengkap, RQ belum mature. Bi-directional: RQ yang tidak bisa jadi hipotesis testable harus direvisi mundur.

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Tujuan pertanyaan | Apa yang harus dibangun? | Apa yang harus dibuktikan? |
| Bentuk jawaban | Sistem yang berfungsi | Bukti empiris terukur |
| Sukses diukur oleh | User satisfaction, uptime | Signifikansi statistik, effect size |
| Jika gagal | Debug dan perbaiki | Laporkan, analisis mengapa |

### Istilah Penting

- **Research Question (RQ)** — Pertanyaan spesifik: variabel terukur + metrik + konteks
- **Contribution Statement** — Apa yang diketahui setelah riset selesai yang sebelumnya belum ada
- **H₀ / H₁** — Null vs Alternative Hypothesis
- **Falsifiability** — Kondisi hipotesis ditolak harus bisa didefinisikan sebelum eksperimen
- **Operationalization** — Proses mewujudkan konsep abstrak menjadi variabel terukur

---

## Template A.4 — RQ-Contribution-Hypothesis

```
RQ-CONTRIBUTION-HYPOTHESIS

Gap Statement   : Mayoritas penelitian UX e-wallet saat ini masih bergantung pada data persepsi subjektif melalui kuesioner (UEQ/SUS), sehingga belum ada data empiris yang objektif mengenai kecepatan transaksi (time-on-task) antar model aplikasi (Super App vs Stand-alone).

Research Question:
  Tipe         : [X] Comparison  [ ] Improvement  [ ] Exploratory
  Formulasi    : Apakah terdapat perbedaan signifikan pada rata-rata durasi waktu transaksi (Time-on-Task) antara aplikasi GoPay (stand-alone) dan aplikasi DANA (super app) bagi pengguna mahasiswa?
  Variabel IV  : Model arsitektur aplikasi (GoPay Stand-alone vs DANA Super App)
  Variabel DV  : Waktu penyelesaian tugas (Time-on-Task dalam detik)
  Metrik       : Mean Task Completion Time (MTTC)
  Dataset      : 30 responden mahasiswa (menggunakan satu perangkat terkontrol untuk konsistensi hardware)
  Baseline     : Performa efisiensi aplikasi DANA sebagai representasi Super App

Quality Check RQ:
  [X] Variabel spesifik
  [X] Metrik jelas
  [X] Baseline ada
  [X] Konteks disebutkan
  [X] Memerlukan eksperimen (bukan hanya survei literatur)

Contribution Statement:
  Apa yang baru diketahui : Bukti empiris mengenai pengaruh model arsitektur aplikasi (Super App vs Stand-alone) terhadap efisiensi waktu penyelesaian tugas pengguna.
  Jenis kontribusi       : [ ] Improvement  [X] Comparison  [ ] Novel approach
  Gap yang diisi         : Mengisi Method Gap; beralih dari pengukuran persepsi subjektif ke pengukuran performa objektif (metode stopwatch).

Hypothesis Pair:
  H₀ : Tidak terdapat perbedaan yang signifikan secara statistik pada durasi waktu transaksi antara aplikasi GoPay dan aplikasi DANA.
  H₁ : Aplikasi GoPay (stand-alone) memiliki durasi waktu transaksi yang lebih cepat secara signifikan dibandingkan aplikasi DANA (super app).
  Threshold              : p-value < 0.05
  Justifikasi threshold  : Ambang batas standar signifikansi statistik (95% confidence level) untuk menolak hipotesis nol dalam pengujian komparatif.
```
---

## Latihan 1 — Dari Gap ke RQ

Gunakan gap yang ditemukan di WS-03. Transformasikan menjadi Research Question.

**Gap dari WS-03:** Adanya *Method Gap* di mana penelitian sebelumnya lebih banyak menggunakan kuesioner subjektif (UEQ/SUS), sehingga belum ada pembuktian empiris menggunakan metrik performa objektif (seperti stopwatch) untuk membandingkan efisiensi DANA dan GoPay.

**RQ versi pertama (tulis bebas):**
> Apakah GoPay lebih cepat daripada DANA kalau dihitung pakai waktu asli saat transaksi?

**Evaluasi RQ:**

| Komponen | Ada? | Isi |
|----------|------|-----|
| Metode spesifik | Ya | Perbandingan efisiensi melalui eksperimen langsung (Usability Testing). |
| Metrik terukur | Ya | Durasi waktu penyelesaian tugas (Time-on-Task). |
| Baseline | Ya | Aplikasi DANA sebagai representasi model Super App. |
| Dataset/konteks | Ya | 30 responden mahasiswa UPB (Eksperimen terkontrol). |

**Tipe RQ:** [X] Comparison / [ ] Improvement / [ ] Exploratory

**RQ versi revisi (setelah evaluasi):**
> Apakah terdapat perbedaan signifikan pada rata-rata durasi waktu transaksi (Time-on-Task) antara aplikasi GoPay (stand-alone) dan aplikasi DANA (super app) di kalangan mahasiswa Universitas Putra Bangsa?

---

## Latihan 2 — Hypothesis Pair

Rumuskan pasangan hipotesis dari RQ di Latihan 1.

| Komponen | Isi |
|----------|-----|
| H₀ | Tidak ada perbedaan signifikan pada rata-rata durasi waktu transaksi (Time-on-Task) antara aplikasi GoPay (stand-alone) dan aplikasi DANA (super app). |
| H₁ | Aplikasi GoPay (stand-alone) memiliki durasi waktu transaksi yang secara signifikan lebih cepat dibandingkan aplikasi DANA (super app). |
| Metrik | Mean Task Completion Time (Waktu rata-rata dalam satuan detik). |
| Threshold | p-value < 0,05 (Alpha 5%). |
| Justifikasi threshold | Merupakan standar signifikansi statistik yang umum digunakan dalam penelitian Human-Computer Interaction (HCI) untuk meminimalkan risiko kesalahan tipe I (false positive). |

**Apakah hipotesis ini falsifiable?** [X] Ya / [ ] Tidak
> Bagaimana cara membuktikannya salah? Hipotesis H₁ akan terbukti salah jika setelah dilakukan uji statistik (misalnya Independent T-Test), nilai p-value yang dihasilkan lebih besar dari 0,05 (p > 0,05). Hal ini menunjukkan bahwa perbedaan waktu yang ditemukan tidak signifikan secara statistik atau hanya terjadi karena kebetulan, sehingga H₀ gagal ditolak.

---

## Latihan 3 — Rantai Operasionalisasi

Lengkapi rantai dari RQ hingga metode analisis.

| Tahap | Isi |
|-------|-----|
| RQ | Apakah terdapat perbedaan signifikan pada rata-rata durasi waktu transaksi (Time-on-Task) antara aplikasi GoPay (stand-alone) dan aplikasi DANA (super app) di kalangan mahasiswa? |
| Variable (IV) | Model arsitektur aplikasi (GoPay Stand-alone vs DANA Super App) |
| Variable (DV) | Efisiensi performa aplikasi (Efisiensi Objektif) |
| Metric | Time-on-Task (durasi waktu dalam satuan detik) |
| Data source | Data primer hasil observasi langsung (Usability Testing) menggunakan stopwatch terhadap 30 responden. |
| Analysis method | Uji statistik parametrik (Independent Samples T-Test) untuk membandingkan rata-rata waktu dua kelompok. |

**Apakah rantai lengkap?** [X] Ya / [ ] Tidak
> Jika tidak, tahap mana yang perlu direvisi? (Rantai sudah lengkap dan saling terhubung dari identifikasi variabel hingga metode analisis).

---

## Refleksi

> Ambil satu judul skripsi/paper yang pernah dibaca. Coba ekstrak RQ-nya. Apakah RQ tersebut memenuhi semua komponen (metode, metrik, baseline, konteks)? Jika tidak, apa yang hilang?

**Judul:** Analisis Kegunaan Aplikasi GoPay Berdasarkan Metode System Usability Scale (SUS) - Jurnal Minfo Polgan, 2024.
**RQ yang diekstrak:** Bagaimana tingkat kegunaan (usability) aplikasi GoPay menurut pengguna aktif berdasarkan metode System Usability Scale (SUS)?
**Komponen yang hilang:** RQ tersebut kehilangan komponen **Baseline/Comparison**. Penelitian hanya mengukur satu subjek (GoPay) secara mandiri. Tanpa adanya baseline atau perbandingan dengan aplikasi kompetitor (seperti DANA), hasil skor SUS tersebut tidak dapat menunjukkan posisi efisiensi GoPay secara kompetitif di industri.

---