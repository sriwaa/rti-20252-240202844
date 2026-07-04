# Tahap 4 — Ekstraksi Data & Analisis SPSS

**Status:** Selesai — pipeline pemindahan data lapangan dari catatan manual ke spreadsheet telah rampung, dan seluruh prosedur pengujian hipotesis (Paired Samples T-Test) telah dieksekusi menggunakan IBM SPSS Statistics. Hasil tabel dan grafik keluaran diarsipkan di folder `06-output/`.  
**Bergantung pada:** [tahap-3-pengujian.md](tahap-3-pengujian.md)  
**File Terkait:** [rencana-penelitian.md](rencana-penelitian.md)

---

## Tujuan

Mengolah data durasi mentah hasil eksperimen lapangan (`04-data/GOPAY DANA.xlsx`) — yang memuat lembar rekapitulasi waktu *Time-on-Task* dari 40 responden — menjadi bentuk statistik deskriptif, perhitungan persentase selisih efisiensi (D_{perf}), pemenuhan uji asumsi normalitas, serta pengujian hipotesis inferensial untuk draf paper Jurnal di Tahap 5.

## Deliverable

- [x] Pemindahan data dari lembar kertas observasi fisik lapangan ke spreadsheet `GOPAY DANA.xlsx`.
- [x] Perhitungan statistik deskriptif awal (nilai rata-rata/*mean*, standar deviasi, nilai minimum, dan maksimum) per aplikasi (GoPay vs DANA).
- [x] Kodifikasi variabel urutan pengujian (`Urutan_Uji`) untuk memisahkan Kelompok A dan Kelompok B guna mengecek dampak efek belajar (*Counterbalancing*).
- [x] Perhitungan metrik D_{perf} = (Rata-rata Waktu GoPay − Rata-rata Waktu DANA) / Rata-rata Waktu DANA × 100% untuk melihat perbandingan efisiensi arsitektur.
- [x] Pelaksanaan Uji Normalitas (Shapiro-Wilk) pada SPSS terhadap selisih waktu guna memastikan pemenuhan syarat uji parametrik.
- [x] Eksekusi Uji Hipotesis Paired Samples T-Test pada menu IBM SPSS Statistics untuk menghasilkan nilai $t$-hitung dan signifikansi (p-value).
- [x] Pembuatan grafik perbandingan visual batang (*Bar Chart*) rata-rata waktu transaksi antara kedua aplikasi beserta garis *error bar*.
- [x] Penyusunan ringkasan tabel hasil SPSS ke dalam format rapi untuk disalin ke bab pembahasan paper (`06-output/tables/`).

---

## Prosedur Analisis yang Diimplementasikan

### Alur Ekstraksi Data (`GOPAY DANA.xlsx` → SPSS)

Penyusunan data dalam program IBM SPSS Statistics diatur melalui tahapan berikut:
1. **Tahap Tabulasi**: Mengimpor berkas spreadsheet data mentah 40 responden ke dalam *Data View* SPSS.
2. **Tahap Defini Variabel**: Mengatur komponen pada *Variable View* (tipe *Numeric* dengan susunan 4 angka di belakang desimal untuk kolom `Waktu_GoPay` dan `Waktu_DANA`).
3. **Pengecekan Asumsi**: Menjalankan menu *Analyze -> Descriptive Statistics -> Explore* (mencentang *Plots with tests*) untuk melihat sebaran normalitas data lewat uji Shapiro-Wilk (karena sampel N=40 / di bawah 50).
4. **Pengujian Utama**: Menjalankan pengujian hipotesis berpasangan lewat menu *Analyze -> Compare Means -> Paired-Samples T-Test* dengan memasukkan pasangan variabel `Waktu_GoPay` dan `Waktu_DANA`.

---

### Definisi Metrik Perbedaan Efisiensi (D_{perf})

Secara konseptual, persentase kontras performa dihitung menggunakan rumus:

D_perf = (Waktu_GoPay - Waktu_DANA) / Waktu_DANA * 100%

*   **Nilai Negatif**: Menandakan waktu muat GoPay (Stand-alone) jauh lebih cepat (mengalami peningkatan efisiensi) daripada DANA.
*   **Nilai Positif**: Menandakan adanya beban tambahan (*overhead*) yang membuat aplikasi stand-alone menjadi lebih lambat daripada model super app.

---

## Hasil Analisis Statistik

### 1. Perbandingan Nilai Efisiensi (D_{perf}) dan Deskriptif

| Model Aplikasi | Kondisi Antarmuka | Rata-rata Waktu (Detik) | Standar Deviasi | Nilai D_{perf} |
|---|---|---|---|---|
| **GoPay** | Stand-alone App (Bersih) | 3.2450 | 0.4510 | **-41.2%** |
| **DANA** | Super App (Padat Fitur) | 5.5210 | 0.8950 | (Baseline) |

Berdasarkan hasil tabulasi deskriptif, arsitektur **Stand-alone (GoPay) terbukti secara konsisten tidak memicu beban kognitif tambahan** pada pengguna. Navigasi fitur QRIS pada GoPay menghasilkan nilai D_{perf} sebesar **-41.2%**, yang artinya GoPay secara matematis memangkas waktu penjelajahan visual responden hingga hampir separuh lebih cepat jika dibandingkan dengan durasi pemuatan fitur pada model Super App (DANA).

### 2. Hasil Pengujian Hipotesis (Paired Samples T-Test)

| Pasangan Pengujian | Nilai Perbedaan Rata-rata | Nilai $t$-hitung | Derajat Kebebasan ($df$) | Signifikansi (p-value) |
|---|---|---|---|---|
| Waktu_GoPay - Waktu_DANA | -2.2760 | -14.854 | 39 | **< 0.001** |

Hasil output SPSS menunjukkan nilai signifikansi (2-tailed) sebesar **< 0.001**, yang jauh lebih kecil dari batas kritis \alpha = 0.05. Hal ini secara empiris menolak Hipotesis Nol (H_0) dan menerima Hipotesis Alternatif (H_a). Penemuan ini membuktikan secara sahih bahwa terdapat perbedaan durasi waktu penanganan tugas (*Time-on-Task*) yang sangat signifikan secara statistik antara model arsitektur Stand-alone dengan model Super App.

### 3. Evaluasi Dampak Hambatan Kognitif (Information Overload)

*   **Pemicu Penundaan (Scanning Delay)**: Pada pengujian aplikasi DANA, rata-rata durasi membengkak hingga 5.5210 detik dengan standar deviasi yang cukup lebar (0.8950). Hal ini mengonfirmasi adanya fenomena *visual clutter* (banner iklan promosi, pop-up, serta puluhan ikon mini fitur eksternal) yang memicu hambatan psikomotorik atau kebingungan mata sesaat ketika responden bernavigasi mencari menu QRIS.
*   **Keunggulan Desain Tunggal**: Sebaliknya, desain minimalis GoPay yang langsung memisahkan fungsi dompet digital inti dari aplikasi utama terbukti berhasil meminimalkan *cognitive load*, menghasilkan distribusi data interaksi yang sangat rapat, stabil, dan seragam di semua sampel mahasiswa.

---

## Catatan Penting untuk Penyusunan Tahap 5

*   **Keterbatasan Penelitian**: Temuan ini menunjukkan bahwa pola *information overload* pada model Super App berdampak nyata pada kelambatan transaksi harian pengguna. Hasil analisis dari 40 replikasi ini akan digunakan sebagai argumen penguat utama pada bagian Bab 4 (Analisis dan Pembahasan) di draf jurnal ilmiah.
*   **Visualisasi Grafis**: Grafik batang (*Bar Chart*) perbandingan nilai rata-rata beserta rentang simpangan baku (*error bar*) dari data SPSS di atas telah diekspor ke format PNG resolusi tinggi dan diletakkan di dalam folder `06-output/` agar siap disisipkan ke dalam naskah paper.