# Tahap 2 — Implementasi Protokol Kontrol Eksperimen

**Status:** Selesai  
**Acuan variabel:** [tahap-1-arsitektur-dan-skema-variabel.md](tahap-1-arsitektur-dan-skema-variabel.md)  
**Jenis Dokumen:** Berkas Administrasi & Instrumen Lapangan Lapangan (Manual)

---

## Tujuan

Mengimplementasikan lembar panduan operasional (SOP) eksperimen lapangan yang mendukung dua skenario pengujian guna mengukur efisiensi waktu pemuatan fitur QRIS:

- **Skenario Stand-alone (GoPay)** — baseline interaksi bersih, mengukur kecepatan akses fitur pada aplikasi yang memiliki antarmuka terfokus fungsi tunggal.
- **Skenario Super App (DANA)** — interaksi kompleks, mengukur dampak penundaan pemindaian visual (scanning delay) akibat kepadatan menu eksternal (visual clutter) yang memicu information overload.

## Deliverable

- [x] **Panduan Instruksi Lisan (Word)** — Struktur urutan instruksi lisan untuk responden yang dibacakan secara seragam oleh peneliti agar tidak terjadi bias informasi.
- [x] **Dokumen Persiapan Smartphone (Checklist)** — Lembar pengecekan spesifikasi fisik dan batasan sistem untuk unit smartphone kontrol Samsung Galaxy A55.
- [x] **SOP Langkah Cold Start (Panduan Manual)** — Lembar langkah penutupan paksa (Force Stop) dan pembersihan data memori (Clear Cache) pada Android OS sebelum pengujian dimulai.
- [x] **Berkas Master Tabulasi Data (`gopay dana.xlsx`)** — Template spreadsheet siap pakai yang memuat formula otomatis selisih waktu transaksi.
- [x] **Format Lembar Observasi Fisik (Cetak)** — Lembar kertas kerja lapangan untuk mencatat durasi waktu stopwatch secara manual per responden demi validitas pencatatan awal.
- [x] **Tabel Rotasi Counterbalancing (Excel)** — Matriks pembatasan rotasi giliran untuk membagi 40 responden menjadi dua kelompok urutan pengerjaan (Kelompok A dan Kelompok B).
- [x] **Formulir Screening Kelayakan (Kuesioner)** — Daftar periksa profil subjek untuk memastikan seluruh sampel merupakan mahasiswa aktif Universitas Putra Bangsa (UPB) Kebumen.

---

## Hasil Verifikasi End-to-End

Protokol pengujian ini telah diverifikasi secara manual melalui simulasi uji coba awal (pre-test) sebelum diaplikasikan penuh di lapangan:

- **Kondisi Skenario Stand-alone (GoPay)**: Responden membuka aplikasi -> antarmuka fokus memicu respon kognitif cepat -> navigasi menu QRIS bersifat langsung -> stopwatch mencatat durasi waktu pemuatan kamera yang konsisten minim penundaan.
- **Kondisi Skenario Super App (DANA)**: Responden membuka aplikasi -> kepadatan visual memicu information overload -> responden mengalami scanning delay saat mencari menu -> stopwatch mencatat adanya pembengkakan durasi Time-on-Task secara nyata.
- **Validasi Sesi Gugur (Fail-closed)**: Jika koneksi internet kampus terputus secara tiba-tiba di tengah sesi running -> running dihentikan seketika -> data pada lembar observasi diberi tanda gugur -> pengujian diulang kembali dari kondisi Cold Start setelah jaringan pulih.

---

## Catatan Lingkungan Eksperimen

- Selama eksperimen lapangan berlangsung, tingkat kecerahan layar smartphone Samsung Galaxy A55 dikunci pada tingkat **50 persen** menggunakan slider bawaan Android untuk menghindari bias kenyamanan visual mata responden yang dapat memengaruhi kecepatan navigasi.
- Seluruh aplikasi di luar GoPay dan DANA yang berjalan di latar belakang (background apps) pada Android OS wajib ditutup total melalui menu "Recent Apps" untuk memastikan alokasi daya prosesor (CPU) dan memori RAM smartphone berada dalam kondisi kosong yang setara pada setiap sesi running.