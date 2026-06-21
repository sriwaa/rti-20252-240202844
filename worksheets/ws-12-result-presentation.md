# WS-12: Result Presentation & Visualization

> **Bab 12 — Penyajian Hasil & Visualisasi**

---

## Ringkasan Materi

### Data → Insight Model

```
Validated Data → Structured Presentation → Visualization → Pattern Recognition → Insight
```

Penyajian **mendahului** analisis. Tabel dan grafik membantu peneliti "melihat" data sebelum menghitung. Langsung ke uji statistik tanpa visualisasi berisiko kesimpulan yang secara teknis benar tapi kontekstual salah (Anscombe's Quartet, 1973).

### Tabel = Presisi, Grafik = Pola

Keduanya **saling melengkapi**:
- Tabel: angka presisi, self-contained (dipahami tanpa teks), sortable
- Grafik: pola visual, tren, perbandingan cepat

### Jenis Grafik Berdasarkan Tujuan

| Tujuan | Jenis Grafik |
|--------|-------------|
| Perbandingan antar-skenario | Bar chart (grouped/stacked) |
| Distribusi per-skenario | Box plot / violin plot |
| Tren temporal | Line chart |
| Korelasi dua variabel | Scatter plot |
| Proporsi (total = 100%) | Pie chart (hati-hati!) |

### Contoh Tabel Hasil yang Baik

| Model | Accuracy (%) | F1-Score (%) | Training Time (min) |
|-------|-------------|-------------|---------------------|
| BERT | 88.4 ± 1.2 | 87.1 ± 1.4 | 45.2 ± 3.1 |
| LSTM | 86.1 ± 1.8 | 84.5 ± 2.0 | 12.8 ± 1.2 |
| SVM | 82.3 ± 0.9 | 80.7 ± 1.1 | 0.3 ± 0.1 |

*N=10 per model. Mean ± std. Diurutkan berdasarkan Accuracy.*

### Visualization Bias — Yang Harus Dihindari

| Bias | Deskripsi | Dampak |
|------|----------|--------|
| Truncated axis | Y tidak dari 0 | Memperbesar perbedaan kecil |
| Inconsistent scale | Dua grafik skala beda | Perbandingan menyesatkan |
| Cherry-picked data | Hanya tampilkan yang "menang" | Selektif, tidak jujur |
| 3D effects | Efek 3D tanpa dimensi data ke-3 | Distorsi tanpa informasi |
| Missing error bar | Tidak ada variabilitas | Menyembunyikan ketidakpastian |

### Engineering vs Research Presentation

| Aspek | Engineering | Research |
|-------|-----------|---------|
| Tujuan grafik | Dashboard monitoring | Mendukung argumen ilmiah |
| Informasi wajib | KPI, threshold | Mean, std, CI, N, p-value |
| Bias handling | Less critical | Wajib dihindari (peer-review) |

---

## Template A.12 — Result Presentation Plan

```
RESULT PRESENTATION PLAN

Research Question : Apakah terdapat perbedaan durasi waktu (Time-on-Task) pembukaan fitur QRIS yang signifikan antara model aplikasi Stand-alone (GoPay) dan Super App (DANA) pada mahasiswa UPB Kebumen?
Metrik Utama      : Time-on-Task (durasi waktu muat menu QRIS dalam satuan detik)

Tabel Hasil:
| Skenario | Metrik 1 (mean ± std) | n |
|---------- | ---------------------- | ---|
| GoPay (Model Stand-alone) | 4.70 ± 0.69 detik | 40 |
| DANA (Model Super App) | 6.07 ± 0.90 detik | 40 |

Visualisasi yang Direncanakan:
| # | Jenis Grafik | Pesan Utama | Metrik |
|---|-------------|-------------|--------|
| 1 | Bar Chart + Error Bar | Perbandingan nilai rata-rata (mean) durasi kecepatan pembukaan QRIS antara GoPay dan DANA. |Mean ± Standard Deviation|
| 2 | Box Plot | Distribusi sebaran nilai minimum, kuartil, dan maksimum untuk melihat konsistensi performa di lapangan. | Seluruh nilai sebaran data 80 runs |

Bias Check:
  [✓] Y-axis mulai dari 0 (atau dijustifikasi)
  [✓] Error bar/CI ditampilkan
  [✓] Semua data disertakan (tidak cherry-picked)
  [✓] Tidak menggunakan 3D tanpa alasan
```

---

## Latihan 1 — Tabel Hasil

Buat tabel hasil eksperimen Anda (Menggunakan Data Riil Hasil Pengujian).

| Skenario | Durasi Kecepatan (mean ± std) | Rentang Nilai (Min - Maks) | n |
|----------|-------------------------------|----------------------------|---|
| GoPay (Model Stand-alone) | 4.70 ± 0.69 detik | 3.90 detik – 6.97 detik | 40 |
| DANA (Model Super App) | 6.07 ± 0.90 detik | 4.55 detik – 8.33 detik | 40 |

**Checklist tabel:**
- [✓] Self-contained (judul jelas, satuan ada, N tercantum)
- [✓] Mean ± std (bukan single number)
- [✓] Diurutkan berdasarkan metrik utama (GoPay yang tercepat ditaruh di atas)
- [✓] Format konsisten di semua baris

---

## Latihan 2 — Rencana Visualisasi

Rencanakan 2-3 grafik untuk menyajikan data dari Latihan 1. Setiap grafik = satu pesan.

| # | Jenis Grafik | Pesan | Data yang Digunakan |
|---|-------------|-------|---------------------|
| 1 | Bar Chart + Error Bar | Memperlihatkan secara visual bahwa rata-rata (*mean*) durasi waktu muat fitur QRIS GoPay lebih cepat daripada DANA, lengkap dengan simpangan bakunya. | Rata-rata (*mean*) durasi waktu ± standar deviasi (*std*) dari GoPay dan DANA. |
| 2 | Box Plot | Menunjukkan sebaran distribusi data dan rentang variasi waktu (nilai minimum, kuartil, nilai maksimum) untuk melihat konsistensi performa kedua aplikasi di lapangan. | Seluruh data mentah (80 data points) dari durasi waktu GoPay dan DANA. |

---

## Latihan 3 — Bias Detection

Evaluasi visualisasi berikut untuk bias (skenario dari contoh):

**Skenario:** Metode A = 91.2%, Metode B = 90.8%. Bar chart dengan Y-axis mulai dari 90%.

| Pertanyaan | Jawaban |
|-----------|---------|
| Apakah Y-axis menyesatkan? | Ya — Pemotongan sumbu Y (di mulai dari 90%) akan mendistorsi visual, membuat Metode A terlihat seolah-olah 2x lipat lebih tinggi dan jauh lebih unggul, padahal selisih aslinya hanya 0.4%. |
| Apakah error bar ditampilkan? | Tidak ditampilkan, sehingga menyembunyikan tingkat variabilitas dan ketidakpastian sebaran data sampel tersebut. |
| Apakah semua kondisi ditampilkan? | Ya, semua kondisi dari kedua metode (Metode A dan Metode B) sudah ditampilkan secara lengkap di dalam grafik. |
| Apa solusinya? | Mengatur ulang sumbu Y agar wajib dimulai dari angka 0 (nol) supaya proporsi tinggi batang mencerminkan perbedaan yang jujur dan objektif secara visual. |

**Evaluasi grafik Anda sendiri dari Latihan 2:**
- [✓] Semua bias check lulus
- [ ] Ada yang perlu diperbaiki: —

---

## Refleksi

> Mengapa tabel dan grafik keduanya diperlukan — tidak cukup salah satu saja? Pernahkah Anda membuat grafik yang (tanpa sengaja) menyesatkan?

> Tabel dan grafik keduanya mutlak diperlukan karena fungsi penyajian data mereka saling melengkapi satu sama lain. Tabel sangat unggul dalam menyajikan presisi data berupa angka desimal murni yang lengkap dan mendetail, namun mata manusia akan kesulitan membaca pola atau tren makronya secara instan jika hanya melihat tumpukan angka tersebut. Sebaliknya, grafik sangat unggul dalam memperlihatkan perbandingan visual, sebaran distribusi, dan anomali data (seperti melihat perbedaan rata-rata kecepatan GoPay vs DANA) secara cepat dalam sekali pandang, tetapi grafik tidak bisa menyajikan ketepatan angka mentah secara mendetail. Oleh karena itu, menggunakan keduanya secara bersamaan akan memberikan pemahaman yang utuh, akurat, dan komprehensif bagi pembaca riset.

> Saya pribadi berkomitmen penuh untuk menghindari pembuatan grafik yang menyesatkan dengan selalu menerapkan standar validasi formal, seperti memastikan sumbu Y selalu dimulai dari angka nol (0) agar proporsi visualnya jujur, serta selalu menyertakan komponen error bar/standar deviasi untuk menunjukkan variabilitas data di lapangan. Hal ini sangat penting agar hasil penelitian komparasi model aplikasi ini murni menyajikan fakta ilmiah yang objektif dan tepercaya tanpa adanya manipulasi visual yang tidak disengaja.