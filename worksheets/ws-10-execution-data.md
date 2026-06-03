# WS-10: Experiment Execution & Data Collection

> **Bab 10 — Eksekusi Eksperimen & Pengumpulan Data**

---

## Ringkasan Materi

### Experiment Execution Pipeline

```
Design → Execution Plan → Controlled Execution → Data Collection → Data Logging → Dataset for Analysis
```

### Multiple Run = Non-Negotiable

Single run **tidak pernah cukup** untuk klaim ilmiah. Minimum 5-10 run per skenario dengan seed berbeda. Multiple run menghasilkan:
- Mean, std, confidence interval
- Distribusi hasil → uji statistik
- Variabilitas → error bar di grafik

### Execution Plan

Setiap eksperimen harus memiliki plan sebelum eksekusi:
- Daftar skenario
- Jumlah run per skenario
- Random seed per run (pre-determined!)
- Urutan eksekusi (randomisasi/counterbalancing)
- Pre-execution checklist

### Data Logging Komprehensif

Setiap run menghasilkan log terstruktur:
1. **Identitas** — Run ID, timestamp, skenario
2. **Konfigurasi** — Semua parameter, seed, code version
3. **Hasil** — Semua metrik, output detail
4. **Metadata** — Waktu eksekusi, resource usage, warning/error

Format: CSV/JSON/database — **bukan stdout yang di-copy-paste**.

### Engineering vs Research Execution

| Aspek | Engineering | Research |
|-------|-----------|---------|
| Run | Sekali (deploy) | Multiple (min 5-10, seed berbeda) |
| Logging | Error log, access log | Semua parameter, metrik, metadata |
| Anomali | Bug → fix → redeploy | Investigasi → dokumentasi → analisis |
| Urutan | Tidak penting | Bisa bias — perlu randomisasi |

### Anomali = Dokumentasi, Bukan Hapus

Run gagal/anomali tidak boleh dihapus tanpa dokumentasi. Bisa jadi:
- **Bug** → fix & re-run (dokumentasikan!)
- **Batas kemampuan metode** → DNF = temuan
- **Data yang bias** jika hanya simpan run "berhasil"

### Jebakan Kognitif

1. "Satu angka cukup" → tanpa distribusi, tidak bisa diuji
2. "Seed tidak penting" → bahkan algoritma deterministik bisa dipengaruhi library stokastik
3. "Run gagal langsung hapus" → kehilangan temuan potensial
4. "Semua run harus hari ini" → thermal throttling, fatigue

---

## Template A.10 — Execution Plan & Data Log

```
EXECUTION PLAN

| Run # | Skenario | Seed | Parameter | Status | Waktu | Output File |
|-------|----------|------|-----------|--------|-------|-------------|
| 1 | Responden 1 (Aplikasi GoPay) | Not Applicable | Kelompok A (Urutan: GoPay -> DANA) | Completed | 3.2s | Note HP (Temporary) |
| 2 | Responden 1 (Aplikasi DANA) | Not Applicable | Kelompok A (Urutan: GoPay -> DANA) | Completed | 5.8s | Note HP (Temporary) |
| ... | ... | ... | ... | ... | ... | ... |
| 41 | Responden 21 (Aplikasi DANA) | Not Applicable | Kelompok B (Urutan: DANA -> GoPay) | Completed | 6.1s | Note HP (Temporary) |
| 42 | Responden 21 (Aplikasi GoPay) | Not Applicable | Kelompok B (Urutan: DANA -> GoPay) | Completed | 3.5s | Note HP (Temporary) |

Jumlah runs per skenario : 40 runs per aplikasi (GoPay dan DANA)
Total runs               : 80 total data point (40 responden x 2 aplikasi)

DATA LOG (per run):
  Run ID    : R1-GP
  Timestamp : 2026-05-18T09:00:00+07:00
  Skenario  : Pembukaan Fitur QRIS GoPay (Model Stand-alone) oleh Responden Kelompok A (No. Urut 1-20)
  Input     : Ketukan jari responden pada ikon GoPay di Home Screen Samsung A55 5G
  Output    : Layar kamera pemindai QRIS terbuka sempurna, durasi 3.2s dicatat di Note HP, lalu direkap ke lapangan_raw.csv
  Anomali   : None
  Catatan   : Responden nomor urut 1 memulai pengujian dari kelompok A (GoPay duluan baru DANA), koneksi internet stabil

DATA LOG (per run):
  Run ID    : R21-DN
  Timestamp : 2026-05-18T13:00:00+07:00
  Skenario  : Pembukaan Fitur QRIS DANA (Model Super App) oleh Responden Kelompok B (No. Urut 21-40)
  Input     : Ketukan jari responden pada ikon DANA di Home Screen Samsung A55 5G
  Output    : Layar kamera pemindai QRIS terbuka sempurna, durasi 6.1s dicatat di Note HP, lalu direkap ke lapangan_raw.csv
  Anomali   : None
  Catatan   : Responden nomor urut 21 memulai pengujian dari kelompok B (DANA duluan baru GoPay), kondisi spesifikasi hardware dan lingkungan tetap konstan
```

---

## Latihan 1 — Execution Plan

Susun execution plan untuk eksperimen Anda. Tentukan skenario, jumlah run, dan seed sebelum eksekusi.

| Run # | Skenario | Seed | Parameter Kunci | Status |
|-------|----------|------|----------------|--------|
| 1 | Responden 1-20 (Aplikasi GoPay) | Not Applicable | Kelompok A (Urutan: GoPay -> DANA) | Planned |
| 2 | Responden 1-20 (Aplikasi DANA) | Not Applicable | Kelompok A (Urutan: GoPay -> DANA) | Planned |
| 3 | Responden 21-40 (Aplikasi DANA) | Not Applicable | Kelompok B (Urutan: DANA -> GoPay) | Planned |
| 4 | Responden 21-40 (Aplikasi GoPay) | Not Applicable | Kelompok B (Urutan: DANA -> GoPay) | Planned |

**Total skenario:** 2 (Model Stand-alone GoPay vs Model Super App DANA)
**Run per skenario:** 40 run per aplikasi
**Total run keseluruhan:** 80 total data point

---

## Latihan 2 — Data Log Terstruktur

Desain format data log untuk eksperimen Anda. Tentukan field apa saja yang akan dicatat.

**Identitas:**
| Field | Contoh |
|-------|--------|
| Run ID | R1-GP |
| Timestamp | 2026-05-18T09:00:00 |
| Responden ID | RESP-1 |

**Konfigurasi:**
| Field | Contoh |
|-------|--------|
| Seed | Not Applicable |
| Perangkat Uji | Samsung Galaxy A55 5G (RAM 12GB, Exynos 1480) |
| Metode Instruksi | Instruksi Lisan Seragam (Counterbalancing Manual) |

**Hasil:**
| Metrik | Tipe Data | Range Valid |
|--------|----------|-------------|
| Time-on-Task (ToT) | float | 1.0 – 60.0 (satuan detik) |
| Kelompok Responden | string | Kelompok A / Kelompok B |
| Nama Aplikasi | string | GoPay / DANA |

**Format output:** [✓] CSV / [ ] JSON / [ ] Database / [✓] Lainnya: File sementara di Note HP dan Berkas .sav (IBM SPSS)

---

## Latihan 3 — Anomaly Protocol

Rencanakan bagaimana menangani anomali. Untuk setiap jenis, tentukan langkah yang diambil.

| Jenis Anomali | Contoh | Tindakan |
|---------------|--------|----------|
| Run gagal (crash) | Aplikasi tiba-tiba mengalami *Force Close* saat responden mengetuk ikon menu QRIS. | Catat kejadian sebagai kegagalan sistem perangkat, lakukan pembersihan total *cache* aplikasi pada Samsung A55 5G, istirahatkan komponen internal selama 1 menit, lalu ulangi run tersebut. |
| Hasil ekstrem | Durasi waktu *Time-on-Task* membengkak melebihi 30 detik karena responden tidak sengaja salah menekan menu lain. | Batalkan pencatatan waktu yang berjalan, beri tanda khusus (outlier) pada catatan lapangan untuk transparansi data, berikan waktu istirahat sejenak kepada responden, lalu lakukan pengujian ulang pada skenario tersebut. |
| Waktu eksekusi anomali | Penghitungan waktu detik stopwatch mendadak menjadi sangat lama akibat jaringan seluler mendadak putus (*Request Time Out*). | Hentikan proses pengujian sementara, catat kendala sinyal operator di lokasi area kampus UPB Kebumen ke dalam buku log fisik, tunggu hingga indikator sinyal seluler stabil kembali, lalu lakukan *re-run*. |
| Inkonsistensi dengan run lain | Responden mendadak kebingungan atau mengalami *delay* respons motorik (bengong) setelah peneliti memberikan aba-aba mulai. | Jangan masukkan durasi detik yang bias tersebut ke dalam data utama. Dokumentasikan kendala salah paham instruksi tersebut, tenangkan responden, perjelas aba-aba lisan, lalu lakukan pengambilan data ulang. |

**Prinsip:** Detect → Investigate → Document → Decide

---

## Refleksi

> Pernahkah Anda melaporkan hasil riset/tugas dari single run? Apa risikonya? Bagaimana multiple run mengubah kepercayaan terhadap hasil?

**Pengalaman sebelumnya:**
> Ya, pada tugas-tugas awal kuliah pemrograman atau analisis statistik sederhana, seringkali saya hanya mengambil satu kali sampel pengujian data atau sekali running program saja lalu langsung mengambil kesimpulannya untuk dimasukkan ke laporan.

**Yang akan dilakukan berbeda:**
> Risiko dari single run sangat berbahaya karena angka yang didapatkan bisa jadi merupakan faktor kebetulan (misal pas internet lagi sangat cepat atau justru pas device sedang lag). Hasilnya tidak mewakili performa asli sistem. Dengan mengumpulkan data berbasis multiple run (40 responden mahasiswa yang diuji silang via counterbalancing), variasi durasi detik waktu akan membentuk sebaran distribusi normal yang adil. Rata-rata waktu yang didapat dari SPSS nantinya jauh lebih valid, dapat dipertanggungjawabkan secara ilmiah, dan dipercaya oleh dosen penguji karena minim bias faktor luar.