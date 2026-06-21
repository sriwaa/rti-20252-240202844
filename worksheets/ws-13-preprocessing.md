# WS-13: Data Preprocessing

> **Bab 13 — Preprocessing & Persiapan Data untuk Analisis**

---

## Ringkasan Materi

### Data Refinement Pipeline

```
Raw Data → Cleaning → Transformation → Normalization → Processed Data → Analysis Ready
```

Setiap tahap memiliki tujuan berbeda. **Preprocessing bukan langkah teknis biasa** — setiap keputusan preprocessing adalah keputusan riset yang bisa mengubah kesimpulan.

### Empat Prinsip Preprocessing

| Prinsip | Deskripsi |
|---------|----------|
| **Consistency** | Metode sama untuk data yang sama |
| **Transparency** | Setiap langkah terdokumentasi |
| **Reproducibility** | Orang lain bisa mengulang dengan hasil sama |
| **Minimal Distortion** | Ubah sesedikit mungkin; jika normalisasi tidak perlu, jangan lakukan |

### Cleaning Triad

| Masalah | Strategi | Risiko |
|---------|---------|--------|
| **Missing values** | | |
| — Listwise deletion | Missing < 5%, random | Data loss |
| — Mean/median imputation | Sedikit missing, dist. normal | Mengurangi variabilitas |
| — Model-based imputation | Banyak missing, pola sistematis | Introduces dependency |
| — Flag & separate | Missing karena alasan substantif | Kompleksitas analisis |
| **Duplikat** | Identifikasi → verifikasi → hapus | False positive (data mirip ≠ duplikat) |
| **Error format** | Standardisasi tipe, encoding | Kehilangan informasi saat konversi |

### Normalisasi — Kapan & Metode Mana

| Metode | Formula | Output | Sensitif Outlier? |
|--------|---------|--------|-------------------|
| Min-max | (x-min)/(max-min) | [0, 1] | Ya |
| Z-score | (x-mean)/std | Unbounded | Lebih robust |
| Robust scaling | (x-median)/IQR | Unbounded | Paling robust |

**Kunci:** Parameter normalisasi harus dihitung dari **training set saja** — bukan seluruh data. Pelanggaran = **data leakage**.

### Data Leakage Prevention

Data leakage terjadi ketika informasi dari test set "bocor" ke preprocessing:
- Normalisasi parameter dari seluruh dataset ← **SALAH**
- Cross-validation dilakukan sebelum split ← **SALAH**
- Feature selection menggunakan label test set ← **SALAH**

### Jebakan Kognitif

1. "Preprocessing cuma teknis — tidak perlu detail" → bisa ubah kesimpulan
2. "Lebih banyak preprocessing = lebih bersih = lebih baik" → over-processing distorsi data
3. "Normalisasi selalu diperlukan" → belum tentu, tergantung metode analisis
4. "Imputation sama untuk semua situasi" → strategi harus sesuai konteks

---

## Template A.13 — Preprocessing Documentation Log

```
PREPROCESSING LOG

Dataset           : Eksperimen Kecepatan QRIS GoPay vs DANA
Jumlah data awal  : 80 data points (40 responden × 2 aplikasi)

Cleaning:
| Masalah | Jumlah Kasus | Penanganan | Justifikasi |
|---------|-------------|------------|-------------|
| Missing | 0 Kasus     | Tidak ada tindakan | Data terkumpul 100% utuh tanpa ada yang kosong. |
| Duplikat| 0 Kasus     | Tidak ada tindakan | Setiap ID Responden (RESP-1 s.d RESP-40) terverifikasi unik. |
| Error   | 0 Kasus     | Tidak ada tindakan | Semua input data berupa format angka numerik desimal murni. |

Transformation:
| Transformasi | Variabel | Detail | Alasan |
|-------------|----------|--------|--------|
| Penggabungan Format Melebar | Durasi_Gopay, Durasi_Dana | Menyandingkan dua variabel dalam satu baris per ID Responden (Wide Format). | Memenuhi syarat struktur data input untuk pengujian Paired Sample T-Test di SPSS. |

Normalization:
  Metode    : Tidak dilakukan normalisasi
  Alasan    : Skala data sudah seragam menggunakan satuan detik dan analisis T-Test membutuhkan nilai asli agar maknanya logis.
  Parameter : (dihitung dari: seluruh data)

Leakage Check:
  [✓] Parameter normalisasi dari training set saja
  [✓] Tidak ada informasi test set dalam preprocessing
  [✓] Cross-validation dilakukan setelah split

Jumlah data akhir : 80 data points
Script tersedia   : [✓] Ya → path: Master_Data.xlsx | [ ] Belum
```

---

## Latihan 1 — Cleaning Plan

Periksa dataset Anda (atau dataset contoh) dan dokumentasikan masalah yang ditemukan.

| Masalah | Jumlah Kasus | Penanganan | Justifikasi |
|---------|-------------|------------|-------------|
| Missing Data | 0 Kasus | Tidak ada tindakan | Data komplit 100% dari seluruh responden. |
| Duplikasi Baris | 0 Kasus | Tidak ada tindakan | Seluruh nomor ID responden terverifikasi unik (RESP-1 s.d RESP-40). |
| Eror Format / Teks | 0 Kasus | Tidak ada tindakan | Satuan detik ("s") sudah dibersihkan sejak awal sehingga menjadi numerik desimal murni. |

**Jumlah data sebelum cleaning:** 80
**Jumlah data setelah cleaning:** 80
**Persentase data yang hilang/berubah:** 0%

---

## Latihan 2 — Normalisasi Decision

Tentukan apakah data Anda perlu normalisasi, dan jika ya, metode apa yang tepat.

| Variabel | Range Asli | Distribusi | Outlier? | Metode Normalisasi | Alasan |
|----------|-----------|-----------|----------|-------------------|--------|
| Durasi_Gopay | 3.90 – 6.97s | Normal | Tidak ada yang fatal | Tidak perlu | Mempertahankan keaslian satuan waktu (detik) untuk interpretasi rata-rata nilai asli. |
| Durasi_Dana | 4.55 – 8.33s | Normal | Tidak ada yang fatal | Tidak perlu | Jika dinormalisasi, makna komparasi durasi riil antarkelompok aplikasi akan hilang. |

**Apakah normalisasi diperlukan?** [ ] Ya / [✓] Tidak
**Justifikasi:**
> Normalisasi tidak diperlukan karena kedua variabel sudah memiliki satuan ukuran yang identik, yaitu detik (seconds). Selain itu, tujuan utama riset ini adalah membandingkan nilai rata-rata empiris (mean difference) menggunakan Paired Sample T-Test, yang mana membutuhkan data asli agar hasil interpretasi statistik tetap memiliki arti fungsional yang logis di lapangan.

**Leakage check:**
- [✓] Parameter dihitung dari training set saja (N/A — data deskriptif komparatif)
- [✓] Normalisasi diterapkan setelah train-test split

---

## Latihan 3 — Preprocessing Report

Buat ringkasan preprocessing lengkap — dokumentasi yang cukup bagi orang lain untuk mereplikasi.

```
PREPROCESSING SUMMARY

1. Dataset: Eksperimen Kecepatan QRIS (GoPay vs DANA)
2. Data awal: 40 records, 4 features
3. Cleaning:
   - Missing values: 0 kasus, metode: Tidak ada tindakan
   - Duplikat: 0 kasus, tindakan: Tidak ada tindakan
   - Error: 0 kasus, tindakan: Tidak ada tindakan
4. Transformation: Restrukturisasi tabel dari format kelompok memanjang menjadi format melebar berpasangan (Wide Format) untuk menyandingkan variabel Durasi_Gopay dan Durasi_Dana per responden.
5. Normalisasi: Tidak diperlukan (menggunakan nilai asli satuan detik), parameter dari seluruh data
6. Data akhir: 40 records, 4 features
7. Leakage check: [✓] Lulus / [ ] Ada masalah
```

---

## Refleksi

> Apakah Anda pernah melakukan normalisasi "karena biasa dilakukan" tanpa mempertimbangkan apakah benar-benar diperlukan? Apa risiko over-preprocessing?

> Pernah, terkadang ada kecenderungan untuk langsung melakukan normalisasi (seperti Min-Max Scaling) hanya karena menganggap semua data numerik harus berada di rentang 0-1 agar terlihat rapi dan seragam. Namun, tindakan tersebut adalah bentuk kekeliruan kognitif dalam riset.
> 
> Risiko dari over-preprocessing atau pemrosesan data yang berlebihan adalah terjadinya distorsi informasi asli. Nilai variabilitas alami dan interpretasi fisik dari data (seperti satuan detik dalam pengukuran performa aplikasi ini) bisa hilang. Data yang terlalu banyak dimanipulasi justru dapat menjauhkan peneliti dari kondisi riil di lapangan dan berpotensi memunculkan kesimpulan statistik yang bias atau tidak relevan secara kontekstual.
