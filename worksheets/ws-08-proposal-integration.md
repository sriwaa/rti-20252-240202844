# WS-08: Proposal Integration (UTS)

> **Bab 8 — Proposal & Checkpoint**

---

## Ringkasan Materi

### Proposal = Satu Argumen Utuh

Proposal riset bukan kumpulan bab yang independen. Ia adalah **satu argumen** yang mengalir dari masalah ke rencana solusi. Jika satu koneksi putus, seluruh proposal kehilangan koherensi.

### Integration Map — 6 Koneksi Kritis

```
Problem (Bab 2) → Gap (Bab 3) → RQ & H (Bab 4) → Metrik (Bab 5) → Sistem (Bab 6) → Eksperimen (Bab 7)
```

| Koneksi | Pertanyaan Verifikasi |
|---------|----------------------|
| Problem → Gap | Apakah gap muncul dari analisis literatur terhadap masalah? |
| Gap → RQ | Apakah RQ langsung menjawab gap yang teridentifikasi? |
| RQ → Metrik | Apakah setiap variabel di RQ punya metrik terdefinisi? |
| Metrik → Sistem | Apakah setiap metrik bisa diukur oleh komponen sistem? |
| Sistem → Eksperimen | Apakah desain eksperimen menggunakan sistem sebagai instrumen? |

### Koherensi Vertikal + Horizontal

- **Vertikal** — Alur logis atas-ke-bawah (problem → experiment)
- **Horizontal** — Konsistensi terminologi (nama variabel di RQ = di hipotesis = di metrik = di desain)

### Jebakan Kognitif

| Jebakan | Deskripsi |
|---------|----------|
| "Selling" Introduction | Menulis promosi, bukan menyajikan data dan gap |
| Copy-paste Methodology | Menyalin deskripsi tekstbook tanpa menyesuaikan ke RQ |
| Optimistic Timeline | Meremehkan waktu implementasi; selalu tambah buffer 30-50% |
| No Possibility of Failure | Mengimplikasikan hasil pasti sukses — proposal jujur mengakui H₀ mungkin tidak ditolak |

### Struktur Proposal

1. **Pendahuluan** — Latar belakang + problem statement (Bab 1-2)
2. **Tinjauan Pustaka** — Literature review + gap + baseline (Bab 3)
3. **RQ / Kontribusi / Hipotesis** — (Bab 4)
4. **Metodologi** — Metrik + sistem + desain eksperimen (Bab 5-7)
5. **Timeline & Output**

### Istilah Penting

- **Integration Map** — Diagram 6 koneksi kritis antar komponen proposal
- **Vertical Coherence** — Alur logis atas-ke-bawah
- **Horizontal Coherence** — Konsistensi terminologi di semua bagian
- **Checkpoint** — Titik self-assessment sebelum transisi dari desain ke eksekusi

---

## Template A.8 — Integration Checklist

```
PROPOSAL INTEGRATION CHECKLIST

Koneksi Vertikal (Flow Atas-Bawah):
  [X] Problem → Gap: masalah terdokumentasi di literatur
  [X] Gap → RQ: pertanyaan menjawab gap spesifik
  [X] RQ → Hypothesis: hipotesis memprediksi jawaban
  [X] Hypothesis → Metric: metrik mengukur variabel dalam hipotesis
  [X] Metric → System: komponen sistem menghasilkan/mengukur metrik
  [X] System → Experiment: desain eksperimen menggunakan sistem

Koneksi Horizontal (Konsistensi):
  [X] Istilah sama di semua bagian
  [X] Variabel di RQ = variabel di hipotesis = metrik di desain
  [X] Scope tidak berubah dari masalah ke eksperimen

Rubrik Self-Assessment:
| Kriteria | 1 (Lemah) | 2 (Cukup) | 3 (Baik) | Skor |
|----------|-----------|-----------|----------|------|
| Koherensi |          |           |   X     |  3    |
| Specificity |        |           |   X     |  3    |
| Feasibility |        |           |   X     |  3    |
| Rigor     |          |           |   X     |  3    |
```
---

## Latihan 1 — Kompilasi Proposal Mini

Kumpulkan hasil dari WS-02 sampai WS-07 menjadi satu ringkasan proposal.

| Komponen | Sumber | Isi (1-2 kalimat) |
|----------|--------|-------------------|
| **Problem Statement** | WS-02 | Mahasiswa Universitas Putra Bangsa Kebumen mengalami penurunan efisiensi waktu transaksi akibat beban kognitif dari kepadatan elemen visual pada antarmuka *Super App* (DANA), yang menghambat kecepatan aktivitas finansial harian mereka. |
| **Gap** | WS-03 | Studi terdokumentasi masih didominasi oleh evaluasi persepsi subjektif pengguna (kuesioner SUS/UEQ), sehingga terdapat *method gap* berupa kelangkaan bukti empiris yang menguji performa kecepatan riil antara model *Stand-alone* dan *Super App* menggunakan metrik durasi waktu nyata. |
| **RQ** | WS-04 | Apakah terdapat perbedaan signifikan pada rata-rata durasi waktu transaksi (*Time-on-Task*) antara aplikasi GoPay (model *Stand-alone*) dan aplikasi DANA (model *Super App*) menggunakan HP peneliti pada mahasiswa Universitas Putra Bangsa Kebumen? |
| **Hipotesis** | WS-04 | **H₁:** Aplikasi dengan model *Stand-alone* (GoPay) menghasilkan rata-rata durasi waktu transaksi (*Time-on-Task*) yang lebih cepat secara signifikan (nilai *mean* lebih kecil, $p < 0.05$) dibandingkan aplikasi model *Super App* (DANA) sebagai *baseline*. |
| **Variabel & Metrik** | WS-05 | **IV:** Model Arsitektur Antarmuka Aplikasi (GoPay vs DANA); **DV:** Efisiensi Interaksi Pengguna; **Metrik:** *Time-on-Task* (ToT) skala rasio dalam satuan detik (s). |
| **Sistem** | WS-06 | Dua artefak sistem operasional (aplikasi GoPay versi mandiri dan aplikasi DANA) yang diinstalkan dan dijalankan pada satu perangkat kontrol utama, yaitu **Smartphone/HP milik peneliti sendiri**. |
| **Desain Eksperimen** | WS-07 | Eksperimen terkontrol (*Within-Subject Design*) terhadap 40 responden mahasiswa UPB menggunakan teknik *Counterbalancing* (Kelompok A menguji GoPay dulu; Kelompok B menguji DANA dulu) dan protokol *Cold Start* pada HP peneliti untuk mengeliminasi bias. |

---

## Latihan 2 — Integration Checklist

Verifikasi 6 koneksi kritis. Isi dengan merujuk tabel di Latihan 1.
| Koneksi | Status | Bukti |
|---------|--------|-------|
| **Problem → Gap** | ✅ | Gap muncul dari analisis literatur yang menunjukkan evaluasi dompet digital saat ini masih didominasi kuesioner kualitatif, bukan performa efisiensi waktu riil. |
| **Gap → RQ** | ✅ | RQ secara langsung menginterogasi solusi objektif berupa pengukuran durasi waktu nyata (*Time-on-Task*) demi menyelesaikan keterbatasan data subjektif dari *gap* tersebut. |
| **RQ → Hypothesis** | ✅ | Hipotesis memprediksi secara spesifik arah jawaban dari RQ, yaitu model *Stand-alone* (GoPay) akan memiliki durasi ToT yang lebih singkat dibandingkan baseline *Super App* (DANA). |
| **Hypothesis → Metric** | ✅ | Variabel kecepatan transaksi yang ada di dalam hipotesis diukur menggunakan metrik formal *Time-on-Task* (ToT) dengan satuan rasio detik. |
| **Metric → System** | ✅ | Metrik durasi detik diproduksi langsung melalui respons fisik antarmuka aplikasi GoPay dan DANA yang diproses secara independen di dalam ekosistem HP peneliti. |
| **System → Experiment** | ✅ | Desain eksperimen menggunakan HP peneliti sebagai instrumen fisik tunggal yang dipinjamkan bergantian guna mengontrol bias spesifikasi perangkat keras selama pengujian. |

**Koneksi mana yang paling lemah?** Koneksi Metric → System

**Bagaimana cara memperkuatnya?**
> Memperkuatnya dengan cara menerapkan protokol *Cold Start* (*Clear Cache* dan *Force Stop* aplikasi) secara ketat pada HP peneliti sebelum penyerahan ke responden berikutnya agar sisa memori sistem tidak mencemari validitas data durasi waktu.

**Konsistensi horizontal — apakah istilah dan scope konsisten?** [✓] Ya / [ ] Tidak
> Jika tidak, di bagian mana terjadi inkonsistensi? (Semua bagian sudah konsisten pada subjek mahasiswa UPB Kebumen, metrik durasi detik, dan penggunaan satu HP peneliti sebagai variabel kontrol).

---

## Latihan 3 — Rubrik Self-Assessment

Evaluasi proposal mini menggunakan rubrik.

| Kriteria | Skor (1-3) | Justifikasi |
|----------|-----------|-------------|
| **Koherensi** | 3 | Alur argumen dari perumusan masalah, penurunan beban kognitif, penentuan metrik detik, hingga penguncian instrumen di HP peneliti mengalir logis tanpa patah. |
| **Specificity** | 3 | Semua metrik (*Time-on-Task*) dan parameter operasional (40 responden, satu perangkat HP peneliti) sudah terdefinisi secara numerik dan presisi. |
| **Feasibility** | 3 | Eksperimen sangat fisibel dilaksanakan karena subjek mudah diakses di area kampus UPB Kebumen, aplikasi bersifat gratis, dan alat pengujian menggunakan HP pribadi milik peneliti. |
| **Rigor** | 3 | Prosedur pengujian ketat dengan integrasi teknik *Counterbalancing* untuk menghalau efek belajar serta penguncian spesifikasi RAM/Prosesor melalui HP peneliti. |

**Skor total:** 12 / 12

**Apakah proposal siap untuk fase eksekusi?** [✓] Ya / [ ] Belum
> Jika belum, apa yang perlu diperbaiki? (Proposal sudah sangat siap karena semua komponen kritis terisi maksimal dan metodologinya kokoh).

---

## Refleksi
> Dari seluruh proses WS-01 sampai WS-08, bagian mana yang paling mudah dan paling sulit? Mengapa? Apa yang akan dilakukan berbeda jika mengulang dari awal?

**Bagian termudah:** Proses penentuan topik riset pada **WS-01 (Introduction)** dan merumuskan *Research Question* (RQ) pada **WS-04 (RQ & Hypothesis)**. Bagian ini terasa paling mudah karena fenomena menumpuknya fitur pada antarmuka *Super App* (DANA) yang membuat transaksi terasa lebih berat dan membingungkan adalah masalah nyata yang sangat sering saya rasakan langsung dalam aktivitas sehari-hari di lingkungan kampus UPB Kebumen.

**Bagian tersulit:** Merancang komponen metodologi kontrol pada **WS-06 (System Component)** dan memetakan rancangan eksperimen pada **WS-07 (Experimental Design)**. Bagian ini sangat sulit karena saya harus memikirkan cara mengunci seluruh potensi bias pengganggu secara ketat, seperti menyamakan spesifikasi perangkat fisik dengan memakai satu **HP milik peneliti** serta mengatur urutan pengujian agar memori motorik responden tidak memengaruhi keaslian data durasi detik yang keluar.

**Yang akan dilakukan berbeda:**
> Jika mengulang kembali proses dari awal semester, saya akan langsung menetapkan penggunaan satu perangkat kontrol tunggal (**HP milik peneliti**) sejak tahap perancangan instruksi tugas, serta langsung fokus mengadopsi metrik objektif *Time-on-Task* (ToT) daripada membuang waktu menganalisis metode kuesioner kualitatif subjektif yang rawan terhadap bias ingatan responden.

