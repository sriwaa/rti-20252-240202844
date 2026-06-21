# WS-11: Data Validation & Integrity

> **Bab 11 — Validasi Data & Integritas**

---

## Ringkasan Materi

### Data Trust Model

```
Raw Data → Data Cleaning → Consistency Check → Validation Process → Trusted Data
```

Data mentah belum bisa dipercaya. Harus melewati pipeline validasi sebelum siap untuk analisis statistik.

### Empat Pilar Data Quality

| Pilar | Deskripsi | Contoh Pelanggaran |
|-------|----------|-------------------|
| **Accuracy** | Nilai dalam range masuk akal | Akurasi = 1.5 (di luar [0,1]) |
| **Consistency** | Format seragam di semua run | Run 1: CSV, Run 2: JSON |
| **Completeness** | Tidak ada data hilang dari plan | 97 dari 100 run tercatat |
| **Validity** | Data sesuai desain eksperimen | Parameter baseline tercampur treatment |

### Proses Validasi Progresif

1. **Format validation** — Tipe file, header, kolom
2. **Range validation** — Nilai dalam batas logis
3. **Consistency validation** — Format seragam antar-run
4. **Logic validation** — Data cocok dengan desain eksperimen

Jika gagal di langkah awal → tidak perlu lanjut.

### Anomaly Detection — 3 Jenis

| Jenis | Deskripsi | Deteksi |
|-------|----------|---------|
| **Statistical outlier** | Nilai di luar distribusi normal | IQR: < Q1-1.5×IQR atau > Q3+1.5×IQR |
| **Contextual anomaly** | Normal absolut, abnormal dalam konteks | Run 1-10: ~91%, Run 11-20: ~88% |
| **Pattern anomaly** | Pola sistematis (bukan random) | Performa menurun berurutan |

**Prinsip:** Detect → Investigate → Document → Decide — **JANGAN langsung hapus.**

### Engineering vs Research Validation

| Aspek | Engineering | Research |
|-------|-----------|---------|
| Tujuan | Data sesuai spesifikasi bisnis | Data layak untuk analisis statistik |
| Missing data | Impute / set default | Investigasi penyebab → dokumentasi |
| Outlier | Bug → fix | Mungkin temuan → investigasi |
| Dokumentasi | Minimal (log error) | Komprehensif (anomali + keputusan) |

### Jebakan Kognitif

1. "Logging otomatis ≠ data benar" → bisa ada bug di logger
2. "Outlier = hapus" → bisa jadi temuan penting
3. "Dataset kecil tidak perlu validasi" → justru lebih rentan
4. "Mean normal = data benar" → [94, 95, 93, **44**, 94] → mean 84% terlihat wajar

---

## Template A.11 — Data Validation Checklist

```
DATA VALIDATION CHECKLIST

Completeness:
  [✓] Semua skenario tercakup
  [✓] Jumlah run sesuai rencana
  [✓] Tidak ada file output hilang
  Missing: 0 dari 80 data points

Format Consistency:
  [✓] Semua file format sama (Excel / Berkas Melebar)
  [✓] Header konsisten (NO, Responden_ID, Kelompok, Durasi_Gopay, Durasi_Dana)
  [✓] Tipe data konsisten (Numerik desimal murni tanpa huruf satuan)

Range & Logic:
  [✓] Nilai dalam range masuk akal
  [✓] Tidak ada waktu negatif
  [✓] Metrik 0–100%, tidak di luar range
Anomali ditemukan: Tidak ada anomali fatal. Rentang data GoPay (3.90s - 6.97s) dan DANA (4.55s - 8.33s) seluruhnya logis dan aman untuk diuji.

Cross-Validation:
  [✓] Run identik → hasil mendekati
  [✓] Trend konsisten dengan ekspektasi teori (Durasi GoPay secara konsisten lebih cepat daripada DANA pada hampir seluruh responden)

Keputusan:
[✓] Data siap analisis
[ ] Perlu cleaning
[ ] Perlu re-run (skenario: ____)

```
---

## Latihan 1 — Completeness Check

Verifikasi apakah semua data yang direncanakan sudah terkumpul.

| Skenario | Run Direncanakan | Run Tercatat | Missing | Alasan |
|----------|-----------------|-------------|---------|--------|
| Kelompok A (Responden 1-20) - GoPay & DANA | 40 | 40 | 0 | Prosedur pengujian berjalan lancar sesuai urutan counterbalancing. |
| Kelompok B (Responden 21-40) - DANA & GoPay | 40 | 40 | 0 | Seluruh responden berhasil menyelesaikan pengujian tanpa kendala teknis. |

**Total expected:** 80 | **Total actual:** 80 | **Missing:** 0

**Keputusan untuk data missing:**
> Tidak ada data yang hilang (*zero missing data*). Seluruh data dari 40 responden mahasiswa yang melakukan total 80 kali uji coba pencatatan waktu stopwatch berhasil terekam secara utuh dan lengkap, sehingga data sudah 100% siap untuk dimasukkan ke dalam file `.sav` IBM SPSS.


---

## Latihan 2 — Anomaly Investigation

Periksa data Anda untuk anomali. Gunakan metode IQR atau z-score.

**Dataset sampel (Data Riil 5 Responden Pertama - Durasi GoPay):**

| Run | Durasi GoPay (Detik) |
|-----|----------------------|
| 1   | 4.41                 |
| 2   | 4.54                 |
| 3   | 5.78                 |
| 4   | 4.78                 |
| 5   | 4.67                 |

**Deteksi outlier:**
*Urutan data dari terkecil ke terbesar: 4.41, 4.54, 4.67, 4.78, 5.78*
- Q1 = 4.54 | Q3 = 4.78 | IQR = 0.24
- Batas bawah (Q1 - 1.5×IQR) = 4.54 - 0.36 = 4.18
- Batas atas (Q3 + 1.5×IQR) = 4.78 + 0.36 = 5.14
- Outlier terdeteksi: **Run 3 (5.78)** karena nilainya berada di atas batas atas (5.78 > 5.14).

**Investigasi (untuk setiap outlier):**

| Outlier | Nilai | Kemungkinan Penyebab | Keputusan |
|---------|-------|---------------------|-----------|
| Run 3   | 5.78  | *Network latency* singkat (lonjakan ping) saat aplikasi GoPay melakukan jabat tangan (*handshake*) ke server QRIS melalui jaringan seluler kampus. | Tetap mempertahankan data ini di file master Excel karena angkanya masih sangat logis (<15 detik) dan mencerminkan variasi nyata kondisi sinyal di lapangan. |

---

## Latihan 3 — Validation Report

Buat laporan validasi ringkas untuk dataset eksperimen Anda.

**1. Completeness:** 100% data terkumpul (80 data points dari 40 responden lengkap).
**2. Format:** [✓] Konsisten / [ ] Ada inkonsistensi: —
**3. Range check (anomali):** Seluruh durasi waktu bernilai positif antara 3.90s sampai 8.33s (tidak ada anomali negatif atau angka di luar batas logis).
**4. Logic check:** [✓] Parameter sesuai plan / [ ] Ada ketidaksesuaian: —

**Kesimpulan:** [✓] Data siap analisis / [ ] Perlu tindakan: —

---

## Refleksi

> Apa perbedaan antara "data yang benar" dan "data yang dipercaya"? Mengapa proses validasi formal diperlukan meskipun data dikumpulkan secara otomatis?

> **"Data yang benar"** adalah data angka mentah yang apa adanya keluar dari hasil pengukuran alat di lapangan (misal angka detik yang tertera di layar stopwatch gawai). Sedangkan **"data yang dipercaya"** adalah data yang tidak hanya benar secara angka, melainkan sudah lolos pengujian kualitas formal: formatnya seragam, jumlahnya lengkap 100% sesuai target eksperimen, dan terbukti bebas dari bias eror yang bisa merusak model statistik.

> Proses validasi formal tetap mutlak diperlukan meskipun data dikumpulkan atau dicatat secara otomatis. Hal ini karena alat pencatat otomatis tidak bisa mendeteksi gangguan eksternal di lapangan saat eksperimen berlangsung, seperti lonjakan latensi (*ping*) jaringan internet operator, adanya *cache* RAM gawai yang mendadak penuh, hingga keterlambatan motorik jari responden saat menyentuh layar. Validasi formal bertindak sebagai filter akhir untuk memastikan bahwa data yang di-import ke IBM SPSS beneran data bersih yang layak diuji secara ilmiah.