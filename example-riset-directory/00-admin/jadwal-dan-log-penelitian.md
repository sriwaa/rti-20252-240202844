# Jadwal & Log Pelaksanaan Penelitian

Catatan kronologis pelaksanaan tiap tahap (sumber: riwayat commit git & dokumen `09-docs/tahap-N-*.md`). Tanggal mengikuti `git log`.

## Log Pelaksanaan
# Jadwal & Log Pelaksanaan Penelitian (Kombinasi WS & Migrasi Direktori)

Catatan kronologis pelaksanaan tiap tahap pengisian WS serta rencana migrasi data ke dalam struktur `example-riset-directory`. Tanggal mengikuti realisasi commit dan perencanaan ke depan.

## Log Pelaksanaan

| Tanggal | Tahap | Aktivitas | Referensi / Output Target |
|---|---|---|---|
| **2026-04-06** | Tahap 1 | **WS-01 & WS-02**: Membangun fondasi pemikiran riset (*Research Mindset*), mengisolasi distorsi paradigma, dan merumuskan deskripsi masalah (*Problem Statement*) latensi QRIS. | `worksheets/ws-01-distorsi-paradigma.md`<br>`worksheets/ws-02-problem-statement.md` |
| **2026-04-13** | Tahap 1 | **WS-03**: Melakukan pemetaan literatur (*literature mapping*) terdahulu guna mengidentifikasi celah riset murni (*literature gap*). | `worksheets/ws-03-literature-gap.md` |
| **2026-04-20** | Tahap 1 | **WS-04**: Menentukan rumusan masalah utama (*Research Question*) dan menarik hipotesis komparatif performa kecepatan QRIS. | `worksheets/ws-04-rq-hypothesis.md` |
| **2026-04-28** | Tahap 1 | **WS-05**: Menetapkan definisi operasional variabel bebas, variabel terikat (durasi milidetik), serta metrik pengujian stopwatch laboratorium. | `worksheets/ws-05-variabel-metrik.md` |
| **2026-05-11** | Tahap 2 | **WS-06 & WS-07**: Merancang arsitektur pemetaan eksperimen sistem informasi beserta perencanaan validitas desain eksperimental. | `worksheets/ws-06-system-experiment.md`<br>`worksheets/ws-07-experiment-design.md` |
| **2026-05-18** | Tahap 2 | **WS-08**: Melakukan integrasi draft awal proposal riset komparasi aplikasi dompet digital (*Stand-alone App* vs *Super App*). | `worksheets/ws-08-proposal-integration.md` |
| **2026-05-25** | Tahap 3 | **WS-09 & WS-10**: Menyusun rencana implementasi instrumen pengumpulan data kuantitatif serta mengeksekusi pengumpulan data empiris (n=40 responden). | `worksheets/ws-09-implementation.md`<br>`worksheets/ws-10-execution-data.md` |
| **2026-06-21** | Tahap 4 | **WS-11 s.d. WS-15**: Fase intensif analisis data: validasi kebersihan data mentah, tahap *preprocessing*, komputasi uji statistik inferensial *Paired Samples T-Test* via SPSS, serta penulisan draf artikel. | `worksheets/ws-11-data-validation.md` s.d.<br>`worksheets/ws-15-scientific-writing.md` |
| **2026-06-28** | Tahap 5 | **WS-16 (UAS)**: Finalisasi draf persiapan sidang akbar riset (*Defense Preparation Sheet*), menyusun rancangan visual *Slide Outline*, dan mematangkan matriks jawaban CER. | `worksheets/ws-16-presentation-defense.md` |
| **2026-7-04** | Tahap Admin | **Inisiasi Direktori**: Pengisian file `jadwal-dan-log-penelitian.md` ini untuk merangkum seluruh rekam jejak pengerjaan WS lama dan plotting target 6 hari ke depan. | `example-riset-directory/00-admin/jadwal-dan-log-penelitian.md` |
| **2026-07-04** | Rencana 1 | **Migrasi Komponen Proposal & Teori**: Memecah materi dari WS-02, WS-04, dan WS-05 untuk dijadikan dokumen proposal riset resmi serta draf landasan teori kegunaan sistem digital. | Target: `01-proposal/` & `03-teori/` |
| **2026-07-04** | Rencana 2 | **Penyusunan Matriks Literatur**: Memindahkan hasil pemetaan *literature gap* dan referensi dari WS-03 ke dokumen manajemen literatur terstruktur. | Target: `02-literatur/` |
| **2026-07-04** | Rencana 3 | **Konsolidasi Data Eksperimen**: Mengunggah file data mentah sebaran waktu muat QRIS hasil kuesioner/stopwatch (WS-10) beserta script pengolahan SPSS ke folder repositori. | Target: `04-data/` & `05-kode/` |
| **2026-07-04** | Rencana 4 | **Pengepakan Grafik & Output**: Memasukkan file gambar grafik histogram, plot normalitas, dan tabel ringkasan output SPSS (WS-11 & WS-12) ke folder output riset. | Target: `06-output/` |
| **2026-07-04** | Rencana 5 | **Penyusunan Manuskrip Jurnal**: Merakit draf artikel ilmiah utuh berdasarkan materi *Scientific Writing* dari WS-15 yang disesuaikan dengan template target jurnal publikasi. | Target: `07-manuskrip/` |
| **2026-07-04** | Rencana 6 | **Finalisasi Laporan & Dokumentasi**: Mengompilasi seluruh dokumen laporan akhir riset komparasi QRIS dan memperbarui berkas rekap tahapan 1 sampai 5 secara komprehensif. | Target: `08-laporan/` & `09-docs/` |

## Status Ringkas

- **Tahap 1 (Worksheets WS-01 s.d. WS-16)**: **SELESAI 100%**. Seluruh berkas lembar kerja dari bab awal pengenalan riset hingga persiapan presentasi kelayakan sidang akhir telah sukses diisi penuh dan tersinkronisasi bersih di repositori GitHub pribadi (`rti-20252-240202844`).
- **Tahap 2 (Migrasi Direktori Riset)**: **DALAM PROSES**. Sedang dalam fase pemecahan materi substansi dari file worksheets ke dalam 9 sub-folder administrasi riset (`example-riset-directory`) sesuai target jadwal harian hingga 4 Juli 2026.

## Item Tindak Lanjut (Checklist Pemetaan Direktori Baru)

- [x] Sinkronisasi folder repositori lokal dengan pembaruan struktur direktori dari dosen pengampu
- [x] Rekapitulasi tanggal riwayat commit asli WS-01 sampai WS-16 ke logbook administrasi
- [ ] Memecah materi masalah dan metrik riset QRIS (WS-02, 04, 05) ke folder `01-proposal/` dan `03-teori/`
- [ ] Memindahkan pemetaan *literature gap* (WS-03) ke folder `02-literatur/matriks-literatur.md`
- [ ] Mengunggah file data kuantitatif mentah hasil survei/kuesioner (WS-10) ke folder `04-data/`
- [ ] Menyusun ulang visualisasi grafik dan tabel hasil output SPSS (WS-11, 12) ke folder `06-output/`
- [ ] Merakit draf manuskrip artikel ilmiah utuh (WS-15) ke dalam folder `07-manuskrip/`
- [ ] Melakukan review akhir (*final cross-check*) keterisian berkas template di sub-folder `08-laporan/` dan `09-docs/`

## Korespondensi

*(belum ada — tambahkan catatan korespondensi dengan pembimbing/editor jurnal di sini saat tersedia)*
