# WS-07: Experimental Design & Validity

> **Bab 7 — Experimental Design & Validity**

---

## Ringkasan Materi

### Correlation ≠ Causality

Kausalitas membutuhkan 3 syarat:
1. **Covariance** — X dan Y bergerak bersama
2. **Temporal precedence** — X berubah sebelum Y
3. **Elimination of alternatives** — Tidak ada faktor lain yang menjelaskan Y

Controlled experiment adalah satu-satunya metode yang bisa membuktikan kausalitas.

### Empat Jenis Validitas

| Jenis | Pertanyaan | Ancaman Umum |
|-------|-----------|-------------|
| **Internal** | Apakah hubungan IV→DV nyata? | Confounding variable, selection bias |
| **External** | Apakah bisa digeneralisasi? | Dataset terlalu spesifik |
| **Construct** | Apakah mengukur konsep yang benar? | Metrik tidak sesuai |
| **Conclusion** | Apakah kesimpulan statistik valid? | Sample size kecil, uji salah |

Internal dan external validity sering berkonflik: semakin terkontrol (internal kuat) → semakin artificial (external lemah).

### Tiga Tipe Eksperimen dalam Riset TI

| Tipe | Deskripsi | Kapan Digunakan |
|------|----------|----------------|
| **Comparison Study** | Metode A vs B pada kondisi identik | Membandingkan pendekatan berbeda |
| **Ablation Study** | Full system → lepas komponen satu per satu | Mengukur kontribusi tiap komponen |
| **Parameter Study** | Variasikan satu parameter, amati dampak | Uji sensitifitas/robustness |

### Fairness dalam Perbandingan

Perbandingan yang adil = **kondisi identik** untuk semua metode: dataset sama, preprocessing sama, tuning effort sebanding, environment sama, metrik sama.

Contoh tidak adil: Transformer (30 fitur tambahan + Bayesian optimization) vs RF (default params) → hasilnya misleading.

### Threats to Validity = Diidentifikasi Sebelum Eksperimen

Ancaman validitas harus diidentifikasi **sebelum** eksperimen dan mitigasinya dirancang sebagai bagian dari desain — bukan ditulis sebagai boilerplate setelah selesai.

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Tujuan testing | Memastikan sistem memenuhi requirement | Membuktikan hubungan kausal antar variabel |
| Baseline | Versi sebelumnya (last release) | Metode tervalidasi dari literatur |
| Kegagalan | Bug → fix → release | H₀ tidak ditolak → tetap kontribusi ilmiah |
| Sukses | 100% test pass | Evidence valid — mendukung atau menolak hipotesis |

### Istilah Penting

- **Causality** — Hubungan sebab-akibat (covariance + temporal + elimination)
- **Controlled Experiment** — Ubah satu variabel, kontrol sisanya, amati efek
- **Fairness** — Semua metode diuji pada kondisi yang benar-benar identik
- **Threats to Validity** — Faktor yang bisa melemahkan kesimpulan jika tidak dimitigasi
- **Conclusion Validity** — Validitas statistik: power, sample size, uji yang tepat

---

## Template A.7 — Desain Eksperimen Lengkap

**EXPERIMENT DESIGN**

**Research Question**: Apakah terdapat perbedaan signifikan pada rata-rata durasi waktu transaksi (Time-on-Task) antara aplikasi GoPay (stand-alone) dan aplikasi DANA (super app) menggunakan perangkat terkontrol pada mahasiswa Universitas Putra Bangsa?

**Hypothesis**: Terdapat perbedaan durasi waktu transaksi yang signifikan antara GoPay (lebih cepat) dan DANA (lebih lambat) karena perbedaan kompleksitas arsitektur aplikasi.

**Tipe Eksperimen**: [X] Comparison  [ ] Ablation  [ ] Parameter

**Kondisi Eksperimen:**
| Kondisi | Deskripsi | IV Value | CV Settings |
|:--- |:--- |:--- |:--- |
| Control | Pengujian pada model Super App (DANA) sebagai baseline aplikasi kompleks. | DANA (Super App) | HP Samsung A55,  Data Seluler, Task: Scan QRIS. |
| Treatment | Pengujian pada model Stand-alone (GoPay) untuk melihat efisiensi model lean. | GoPay (Stand-alone) | HP Samsung A55, Data Seluler, Task: Scan QRIS. |

**Fairness Checklist:**
* [x] Dataset/Task identik untuk semua kondisi (Sama-sama scan QRIS).
* [x] Preprocessing setara (Aplikasi dimulai dari kondisi 'Cold Start' yang sama).
* [x] Tuning effort setara (Tidak ada penggunaan shortcut/widget khusus).
* [x] Environment identik (MMenggunakan HP Samsung A55 dan Jaringan Data Seluler yang sama).
* [x] Metrik evaluasi sama (Sama-sama menggunakan Time-on-Task dalam detik).

**Threat Analysis:**
| Threat Type | Ancaman Spesifik | Mitigasi |
|:--- |:--- |:--- |
| Internal | Efek belajar (Responden lebih cepat di tes kedua karena sudah tahu letak tombol). | Counterbalancing: Setengah responden mulai dengan GoPay dulu, setengah lagi mulai dengan DANA. |
| External | Hasil hanya berlaku pada mahasiswa (generasi tech-savvy). | Mendokumentasikan profil responden sebagai batasan penelitian (Gen-Z fokus). |
| Construct | Stopwatch manual memiliki risiko human error/delay pencet. | Peneliti melakukan sinkronisasi aba-aba yang ketat dan melakukan uji coba (trial) sebelum pengukuran asli. |
| Conclusion | Jumlah sampel tidak mencukupi untuk distribusi normal. | MMenggunakan 40 responden untuk meningkatkan power statistik dan memenuhi syarat distribusi normal. |

**Statistical Plan:**
* **Uji statistik**: Independent Samples T-Test (atau Mann-Whitney jika tidak normal).
* **Justifikasi**: Membandingkan rata-rata dari dua kelompok independen (GoPay vs DANA).
* **Alpha**: 0.05 (Tingkat kepercayaan 95%).
* **Effect size min**: Cohen's d > 0.5 (Efek menengah).

---

## Latihan 1 — Desain Eksperimen

**RQ:** Apakah terdapat perbedaan signifikan pada rata-rata durasi waktu transaksi (Time-on-Task) antara aplikasi GoPay (stand-alone) dan aplikasi DANA (super app) menggunakan perangkat terkontrol pada mahasiswa?

**Tipe eksperimen:** [X] Comparison / [ ] Ablation / [ ] Parameter

| Kondisi | Deskripsi | IV Value | CV Settings |
|:--- |:--- |:--- |:--- |
| Control | Pengujian pada aplikasi DANA (Super App). | DANA | Device: Samsung A55, RAM 8GB, Data Seluler 4G/5G. |
| Treatment | Pengujian pada aplikasi GoPay (Stand-alone). | GoPay | Device: Samsung A55, RAM 8GB, Data Seluler 4G/5G. |

---

## Latihan 2 — Fairness Checklist

| Kriteria | Status | Detail |
|:--- |:--- |:--- |
| Dataset/Task identik | ✅ | Keduanya melakukan tugas "Membuka Menu QRIS" dari halaman utama. |
| Preprocessing setara | ✅ | Keduanya memulai aplikasi dari posisi tertutup total (Force Stop) untuk menghindari cache. |
| Tuning effort setara | ✅ | Responden tidak diperbolehkan menggunakan shortcut widget di homescreen HP. |
| Environment identik | ✅ | Keduanya dijalankan pada HP Samsung A55 yang sama secara bergantian. |
| Metrik evaluasi sama | ✅ | Keduanya diukur menggunakan satuan detik (s) hingga kamera scan terbuka. |

**Ada yang tidak fair?** [ ] Ya / [X] Tidak
> **Jika ya, bagaimana cara memperbaikinya?** - (Sudah fair karena environment dikunci total).

---

## Latihan 3 — Threat Analysis

| Threat Type | Ancaman Spesifik | Mitigasi |
|:--- |:--- |:--- |
| Internal | Kecepatan data seluler yang fluktuatif (sinyal naik-turun). | Memastikan kuota mencukupi dan pengujian dilakukan di titik lokasi yang memiliki bar sinyal penuh. |
| External | Spesifikasi HP (Samsung A55) mungkin terlalu lancar dibanding HP entry-level. | Mencatat bahwa hasil ini adalah potensi "performa maksimal" pada perangkat mid-range. |
| Construct | Kesalahan peneliti saat memencet tombol stopwatch (Human Error). | Melakukan latihan prosedur pengukuran berulang kali sebelum mengambil data dari 40 responden. |
| Conclusion | Adanya data outlier (responden yang terlalu lama karena bingung). | Melakukan skrining data awal dan menggunakan teknik pembersihan outlier sebelum uji statistik dilakukan. |

**Ancaman mana yang paling sulit dimitigasi?** Internal (Learning Effect).
**Mengapa?**
> Karena responden mencoba kedua aplikasi. Meskipun urutannya dibalik (Counterbalancing), faktor kebiasaan memegang HP yang sama (Samsung A55) bisa membuat waktu di aplikasi kedua secara alami lebih cepat.
---

## Refleksi

> Sebuah paper melaporkan "metode kami mengalahkan semua baseline." Apa 3 pertanyaan pertama yang harus diajukan untuk mengevaluasi klaim ini?

**Jawaban:**
1. **Apakah Baseline sudah di-tuning dengan maksimal?** (Apakah aplikasi pembanding dijalankan dengan kondisi optimal yang sama?).
2. **Apakah Environment-nya adil (Fair)?** (Apakah semua diuji pada perangkat Samsung A55 dan koneksi yang setara?).
3. **Apakah sampel 40 responden memberikan signifikansi statistik?** (Apakah keunggulan tersebut nyata secara angka atau hanya margin error kecil?).
