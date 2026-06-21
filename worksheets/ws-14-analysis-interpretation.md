# WS-14: Analysis, Interpretation & Failure Analysis

> **Bab 14 — Analisis Data, Interpretasi & Failure Analysis**

---

## Ringkasan Materi

### Data → Knowledge Model

```
Data → Analysis → Interpretation → Explanation → Knowledge
```

Tiga level yang berbeda:
- **Analysis** — "Apa yang terjadi?" (deskriptif + inferensial)
- **Interpretation** — "Apa artinya?" (konteks RQ + literatur)
- **Failure Analysis** — "Mengapa tidak berhasil?" (boundary conditions)

### Beyond p-value

**Statistical significance ≠ practical significance.** Selalu laporkan:
1. p-value (signifikansi statistik)
2. Effect size (besarnya efek)
3. Confidence interval (rentang ketidakpastian)

| Effect Size (Cohen's d) | Interpretasi |
|-------------------------|-------------|
| < 0.2 | Small |
| 0.2 – 0.8 | Medium |
| > 0.8 | Large |

### Pemilihan Uji Statistik

| Kondisi | Uji yang Tepat |
|---------|---------------|
| 2 grup, normal, paired | Paired t-test |
| 2 grup, non-normal | Wilcoxon signed-rank |
| > 2 grup, normal | One-way ANOVA + post-hoc |
| > 2 grup, non-normal | Kruskal-Wallis + post-hoc |
| 2 variabel kontinu | Pearson (normal) / Spearman (rank) |

### Failure Analysis as Contribution

Hipotesis yang ditolak adalah **temuan yang berharga**:

| Dataset | New (F1) | Baseline (F1) | p-value | Cohen's d |
|---------|---------|--------------|---------|-----------|
| DS-1 (small, clean) | 94.2±1.1 | 89.3±1.5 | <0.001 | **3.7** |
| DS-4 (medium, noisy) | 78.3±3.2 | 82.1±2.8 | 0.008 | **-1.3** |
| DS-5 (large, noisy) | 71.6±4.1 | 80.5±3.0 | <0.001 | **-2.5** |

**Insight:** Metode baru unggul di data bersih tapi gagal di data noisy → asumsi Gaussian dilanggar → **boundary condition** ditemukan → hybrid approach direkomendasikan.

**Partial failure + deep analysis = kontribusi lebih kaya daripada full success tanpa analisis.**

### Limitation Types

| Jenis | Contoh |
|-------|--------|
| Internal validity | Confounders yang tidak dikontrol |
| External validity | Generalisasi ke domain lain |
| Construct validity | Metrik mengukur apa yang dimaksud? |
| Statistical limitation | Sample size, asumsi distribusi |

### Jebakan Kognitif

1. "Signifikan statistik = penting secara praktis" → cek effect size
2. "Hipotesis tidak didukung → cari sudut baru" → p-hacking
3. "Kegagalan tidak perlu dilaporkan detail" → missed insight
4. "Limitasi cukup disebutkan, tidak perlu dianalisis" → kedalaman hilang

---

## Template A.14 — Analysis & Interpretation Report

```
ANALYSIS & INTERPRETATION

1. Statistik Deskriptif:
   | Skenario | Mean | Std | Median | Min | Max | n |
   |----------|------|-----|--------|-----|-----|---|
   | Durasi_Gopay | 4.8565 | 0.65912 | 4.6900 | 3.90 | 6.97 | 40 |
   | Durasi_Dana  | 6.0450 | 0.84165 | 5.9950 | 4.55 | 8.33 | 40 |

2. Uji Hipotesis:
   Uji yang digunakan  : Paired Samples T-Test
   Justifikasi         : Membandingkan nilai rata-rata dari dua skenario aplikasi yang saling berpasangan (diuji pada subjek responden yang sama) dengan skala data rasio berdistribusi normal.
   Hasil: p = .000 (p < 0.001), effect size (Cohen's d) = 1.58
   CI 95%               : [-1.42643, -.95057]

3. Keputusan:
   [✓] H₀ ditolak → H₁ diterima
   [ ] H₀ tidak ditolak

4. Interpretasi:
   Hubungan ke RQ       : Eksperimen membuktikan secara inferensial terdapat perbedaan durasi waktu muat QRIS yang signifikan antara GoPay dan DANA, menjawab bahwa model aplikasi berpengaruh nyata terhadap kecepatan performa.
   Practical significance: Selisih rata-rata sebesar 1.188 detik sangat bermakna secara praktis dalam industri fintech, karena mampu memangkas waktu tunggu transaksi pengguna di kasir secara riil.
   Perbandingan literatur: Hasil ini konsisten dengan teori interaksi manusia dan komputer, di mana aplikasi berkonsep *stand-alone* (GoPay) terbukti memiliki waktu inisialisasi visual yang lebih responsif daripada konsep *super app* (DANA).

5. Limitation:
   | Jenis | Ancaman | Dampak | Mitigasi |
   |-------|---------|--------|----------|
   | External validity | Sampel terfokus pada mahasiswa Universitas Putra Bangsa Kebumen | Hasil riset mungkin berbeda jika digeneralisasikan pada kelompok usia non-produktif | Disarankan memperluas rentang demografi responden pada penelitian berikutnya |
   | Internal validity | Ketidakstabilan latensi jaringan internet provider saat pengujian | Variasi sinyal gawai dapat menjadi variabel pengganggu kecepatan murni aplikasi | Pengujian dilakukan pada waktu dan titik lokasi *hotspot* Wi-Fi laboratorium yang sama |

6. Failure Analysis (jika H₀ tidak ditolak):
   Penyebab potensial  : N/A (Hipotesis H₀ berhasil ditolak secara signifikan)
   Boundary condition   : N/A
   Insight              : N/A

---

## Latihan 1 — Pemilihan Uji Statistik

Tentukan uji statistik yang tepat untuk eksperimen Anda.

| Pertanyaan | Jawaban |
|-----------|---------|
| Berapa grup yang dibandingkan? | 2 Skenario Aplikasi (GoPay dan DANA) |
| Apakah data berpasangan (paired)? | Ya, berpasangan (diuji pada 40 responden mahasiswa yang sama) |
| Apakah distribusi normal? (uji normalitas) | Ya, berdistribusi normal (terbukti dari kelayakan sebaran data) |
| **Uji yang dipilih:** | **Paired Samples T-Test** |
| **Justifikasi:** | Data berskala rasio, memiliki 2 kelompok sampel yang saling berpasangan, dan memenuhi asumsi normalitas statistik parametrik. |

**Effect size yang akan dilaporkan:** [✓] Cohen's d / [ ] Eta-squared / [ ] Lainnya: ____
---

## Latihan 2 — Interpretasi Hasil

Gunakan data berikut (atau data riil Anda) untuk berlatih interpretasi.

**Data:**
| Aplikasi | Durasi (mean ± std) | n |
|-------|----------------------|---|
| GoPay | 4.8565 ± 0.65912 | 40 |
| DANA | 6.0450 ± 0.84165 | 40 |

p = .000 (p < 0.001), Cohen's d = 1.58, CI 95% = [-1.42643, -.95057]

| Aspek | Interpretasi |
|-------|-------------|
| Signifikansi statistik | $p < 0.001 \rightarrow$ Sangat signifikan secara statistik pada tingkat kepercayaan $\alpha=0.05$. Hipotesis nol (H₀) resmi ditolak. |
| Effect size | $d = 1.58 \rightarrow$ Masuk dalam kategori *Large Effect* (efek sangat besar), membuktikan variasi model aplikasi memberikan perbedaan durasi yang masif di lapangan. |
| Practical significance | Selisih rata-rata sebesar 1.188 detik sangat nyata dampaknya bagi pengguna di kasir belanja, karena mampu mengurangi waktu tunggu antrean transaksi digital secara instan. |
| Hubungan ke RQ | Sukses menjawab pertanyaan penelitian bahwa tipe arsitektur aplikasi (Stand-alone vs Super App) berpengaruh nyata terhadap efisiensi waktu muat halaman QRIS. |
| Perbandingan literatur | Temuan ini sejalan dengan teori kegunaan perangkat lunak mobile, di mana aplikasi dengan fitur terfokus jauh lebih tangkas menginisialisasi modul antarmuka dibandingkan aplikasi multi-layanan. |

---

## Latihan 3 — Failure Analysis

Latih kemampuan failure analysis: hipotesis TIDAK didukung. Apa yang bisa dipelajari?

**Skenario:** Metode baru Anda mendapat F1 = 83.2%, baseline = 84.7%. p = 0.12 (tidak signifikan).

| Pertanyaan | Jawaban |
|-----------|---------|
| Apakah ini "gagal"? | Bukan gagal total — Hipotesis yang tidak didukung merupakan temuan ilmiah yang valid dan objektif, serta diakui sebagai bentuk kontribusi pengetahuan. |
| Kemungkinan penyebab? | Metode baru meningkatkan kompleksitas kalkulasi kode (+40% waktu pemrosesan) tanpa disertai kemampuan ekstraksi fitur yang lebih baik daripada model dasar. |
| Boundary condition? | Arsitektur baru ini terbukti hanya optimal jika diaplikasikan pada dataset skala besar ($\geq 10.000$ baris); untuk dataset mini ($< 1.000$), algoritma baseline jauh lebih stabil. |
| Insight yang bisa diambil? | Terjadi fenomena *over-engineering* akibat adanya *trade-off* nyata antara volume data dengan kedalaman struktur model. Disarankan menggunakan pendekatan hibrida adaptif. |
| Apakah layak dilaporkan? Mengapa? | Sangat layak — Publikasi hasil negatif (*negative result*) disertai analisis batas kegagalan akan mencegah komunitas peneliti lain mengulang modifikasi kode yang redundan. |

**Limitation terkait:**
| Jenis | Ancaman | Dampak |
|-------|---------|--------|
| Statistical | Hanya melakukan running eksperimen sebanyak 5 kali per skenario | Nilai kekuatan uji statistik (*power test*) menjadi lemah dan rentan bias volatilitas |
| Construct validity | Indikator evaluasi performa hanya bersandar pada metrik tunggal F1-Score | Kurang mampu menyajikan analisis efisiensi model dari sudut pandang pemakaian memori gawai |

---

## Refleksi

> Apakah "failure" dalam riset benar-benar gagal, atau justru kontribusi? Bagaimana failure analysis mengubah cara Anda melihat hasil negatif?

> Hasil "failure" atau tidak terdukungnya hipotesis dalam sebuah riset ilmiah bukanlah sebuah kegagalan sejati, melainkan sebuah bentuk kontribusi nyata bagi khazanah ilmu pengetahuan. Riset baru bisa dikatakan gagal total apabila penelitinya melakukan manipulasi data (*p-hacking*) demi mengejar status "signifikan" secara artifisial, yang justru mencederai objektivitas akademis.
> 
> Keberadaan *failure analysis* mengubah cara pandang saya secara mendasar terhadap hasil negatif: nilai tersebut tidak lagi dipandang sebagai aib atau kesalahan eksperimen yang harus disembunyikan, melainkan sebuah indikator berharga yang menyingkap batasan kondisi operasional (*boundary conditions*). Memahami secara mendalam mengapa dan kapan suatu metode menemui kegagalan memberikan kontribusi kedalaman teoretis yang sangat kaya—menghindarkan peneliti lain dari siklus duplikasi kesalahan yang sama, serta mengarahkan peta jalan riset ke arah modifikasi yang jauh lebih tepat sasaran.