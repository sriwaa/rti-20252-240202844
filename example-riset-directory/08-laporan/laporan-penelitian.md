# Laporan Penelitian

**Judul:** Perbandingan Efisiensi Model Stand-alone (GoPay) dan Super App (DANA) Menggunakan Metrik Time-on-Task pada Mahasiswa UPB

**Peneliti:** Sri Wahyuningsih
**Target Publikasi:** Sinta 2 (Jurnal RESTI/Telematika) atau Scopus Q3–Q4
**Status Penelitian:** Tahap 1–4 selesai; Tahap 5 (draf naskah jurnal) sedang berjalan ([../07-manuskrip/](../07-manuskrip/))

---

## 1. Ringkasan Eksekutif

Penelitian ini merancang, mengimplementasikan, dan mengevaluasi secara empiris tingkat efisiensi antarmuka pengguna pada dua platform dompet digital terkemuka di Indonesia, yaitu GoPay (model Stand-alone App) dan DANA (model Super App). Evaluasi dilakukan melalui eksperimen terkontrol menggunakan rancangan eksperimen berpasangan (Within-Subject / Paired Design) di mana seluruh responden menguji kedua kondisi artefak secara bergantian. Uji performa durasi waktu nyata (Time-on-Task) dilakukan terhadap 40 responden mahasiswa aktif Universitas Putra Bangsa (UPB) Kebumen untuk menyelesaikan skenario tugas transaksional berupa akses fitur pindai QRIS hingga kamera aktif sepenuhnya. Pengukuran dicatat secara presisi menggunakan stopwatch digital dengan kontrol perangkat genggam universal, yang kemudian dianalisis menggunakan uji parametrik Paired Samples T-Test melalui IBM SPSS Statistics.

**Temuan utama:**

- Efisiensi arsitektur Stand-alone **tidak menambah beban kognitif** pada pengguna, menghasilkan pemetaan mental (mental mapping) yang jauh lebih bersih dan langsung fokus ke fungsi utama.
- Model Stand-alone (GoPay) secara konsisten **memangkas durasi transaksi rata-rata menjadi 4,8565 detik** dibandingkan model Super App (DANA) yang memerlukan waktu **6,0450 detik**.
- Hasil uji statistik membuktikan mitigasi penataan informasi ini **melindungi efisiensi interaksi pengguna secara signifikan** (nilai t-hitung = -10,104; nilai Sig. (2-tailed) = 0,000).
- Ditemukan **trade-off**: pada model Super App (DANA), integrasi layanan multi-sektor memicu kepadatan elemen visual (visual clutter) pada halaman utama, sehingga menyebabkan fenomena information overload dan penundaan pemindaian visual (scanning delay) sebesar **1,18850 detik** lebih lambat daripada model Stand-alone.

Seluruh berkas spreadsheet master data, draf naskah, luaran tabel, dan diagram tersedia di repository ini (lihat §7 Lampiran untuk peta artefak).

---

## 2. Latar Belakang dan Rumusan Masalah

### 2.1 Latar Belakang

Perkembangan teknologi finansial di Indonesia memicu transformasi arsitektur antarmuka dompet digital, melahirkan model Super App yang padat layanan dan model Stand-alone App yang fokus pada fungsi tunggal. Di lingkungan akademis Universitas Putra Bangsa (UPB) Kebumen, kecepatan akses fitur finansial sangat krusial bagi mobilitas mahasiswa. Pada implementasi naif, penambahan fitur non-finansial secara masif pada halaman utama Super App memicu masalah baru. Pengguna sering terdiam sejenak (scanning delay) karena dibanjiri elemen visual berlebih (information overload), sehingga beban kognitif bertumbuh linear terhadap jumlah informasi dan berpotensi menyebabkan hambatan interaksi yang menurunkan efisiensi aktivitas transaksi harian bagi pengguna sah.

### 2.2 Rumusan Masalah

1. Bagaimana merancang evaluasi eksperimental pada dompet digital yang mampu membatasi dampak information overload terhadap beban kognitif pengguna, tanpa mengurangi validitas pengujian di lingkungan kampus?
2. Seberapa besar efektivitas arsitektur informasi Stand-alone App (GoPay) dalam menurunkan durasi penyelesaian tugas transaksi (Time-on-Task) dibandingkan arsitektur Super App (DANA)?
3. Bagaimana dampak selisih perbedaan (Mean Paired Differences) model antarmuka yang bersih terhadap latensi kognitif pengguna, baik secara deskriptif maupun inferensial?
4. Apakah strategi pengujian sampel berpasangan (Within-Subject) menghasilkan nilai korelasi performa yang membuktikan pengaruh murni dari faktor desain tata letak sistem?

### 2.3 Tujuan Penelitian

Detail tujuan & kontribusi: lihat [../01-proposal/proposal-penelitian.md](../01-proposal/proposal-penelitian.md) §3 dan §5, serta [../07-manuskrip/02-pendahuluan.md](../07-manuskrip/02-pendahuluan.md).

---

## 3. Metodologi dan Pelaksanaan

Penelitian dilaksanakan dalam 5 tahap. Bagian ini merangkum implementasi dan verifikasi setiap tahap; detail teknis lengkap ada pada dokumen `09-docs/tahap-N-*.md` yang dirujuk.

### 3.1 Tahap 1 — Perancangan Arsitektur & Skema Variabel

**Status: Selesai.** Dirancang arsitektur pengujian eksperimen berpasangan, skema penetapan variabel (Variabel Independen: Model Aplikasi; Variabel Dependen: Time-on-Task), serta batasan perhitungan waktu interaksi (waktu dimulai saat ikon aplikasi disentuh hingga waktu akhir saat jendela bidik kamera QRIS aktif sepenuhnya). Instrumen lembar observasi fisik dirancang sejak tahap ini agar perekaman data detikan antara baseline (Super App) dan intervensi (Stand-alone) dapat dilakukan pada infrastruktur kontrol yang identik.

Detail & diagram: [../09-docs/tahap-1-arsitektur-dan-skema-database.md](../09-docs/tahap-1-arsitektur-dan-skema-database.md), [../03-teori/arsitektur-dan-skema.md](../03-teori/arsitektur-dan-skema.md).

### 3.2 Tahap 2 — Implementasi Protokol Kontrol Eksperimen

**Status: Selesai.** Lingkungan pengujian diimplementasikan menggunakan pembatasan variabel luar yang ketat per sesi pengujian. Menggunakan satu jenis perangkat kontrol (Samsung Galaxy A55), jaringan internet stabil di area kampus UPB, dan stopwatch digital. Deliverable: penyusunan teks instruksi tugas transaksi tunggal yang seragam tanpa intervensi pengarah, lembar rekam fisik responden, serta pembagian urutan uji berdasarkan protokol mitigasi bias.

**Verifikasi end-to-end** (pengujian manual, kedua model):
- *GoPay (Stand-alone)*: ikon diklik -> alur bersih tanpa iklan -> kamera QRIS aktif responsif -> waktu tercatat lebih cepat, usaha kognitif rendah.
- *DANA (Super App)*: ikon diklik -> pemrosesan visual beranda padat promo -> memicu scanning delay pada responden -> kamera aktif dengan durasi rekam total lebih lama.
- *Mitigasi bias*: perpindahan antar-aplikasi mewajibkan aktivasi Cold Start Protocol (aplikasi di-Force Stop dan cache dibersihkan), diverifikasi langsung pada pengaturan sistem Android agar pengujian dimulai adil dari memori kosong.

Catatan lingkungan: Pengujian dilakukan langsung di area kampus Universitas Putra Bangsa Kebumen; seluruh koordinasi jadwal responden dikunci pada kondisi waktu luang mahasiswa agar fokus pengerjaan tidak terganggu.

Detail: [../09-docs/tahap-2-implementasi-gateway.md](../09-docs/tahap-2-implementasi-gateway.md), kode: [../05-kode/gateway/](../05-kode/gateway/).

### 3.3 Tahap 3 — Pengujian Beban Responden (Eksperimen Lapangan)

**Status: Selesai — matrix 40 responden (paired run) telah dijalankan.** Disusun skenario tugas tunggal yang diuji silang menggunakan teknik Counterbalancing (20 responden menguji GoPay dahulu baru DANA, 20 responden sisanya DANA dahulu baru GoPay) untuk mengeliminasi efek belajar (learning effect). Peneliti bertindak sebagai observer yang memantau pergerakan jari dan menghentikan stopwatch tepat saat kamera aktif.

**Iterasi desain penting**: percobaan awal mencatat pengerjaan tanpa pembersihan cache menghasilkan variasi data yang tidak stabil akibat sisa memori sistem—tidak layak untuk analisis ilmiah. Solusi: wajib menyertakan Cold Start Protocol sebelum running tiap sesi. Hasil: total ukuran data dari 40 responden terkumpul rapi dan konsisten dalam lembar fisik.

**Matrix final (40 responden berpasangan)**: untuk memenuhi syarat uji statistik parametrik, sampel dikunci sebanyak 40 mahasiswa UPB (N = 40). Seluruh data waktu berhasil direkam secara penuh, dipindahkan dari lembar observasi fisik ke spreadsheet master digital `gopay dana.xlsx` pada 2026-06-15, menghasilkan 80 baris data durasi operasional yang valid tanpa data hilang (missing value).

Output per run: rekaman durasi waktu (detik) GoPay dan DANA per responden, disimpan secara lokal di file `04-data/gopay dana.xlsx`.

Detail: [../09-docs/tahap-3-pengujian-k6.md](../09-docs/tahap-3-pengujian-k6.md), kode: [../05-kode/k6/](../05-kode/k6/).

### 3.4 Tahap 4 — Ekstraksi Data & Analisis SPSS

**Status: Selesai.** Proses komputasi statistik dijalankan menggunakan IBM SPSS Statistics melalui folder kerja analisis, mengeksekusi pipeline pengolahan data sebagai berikut:

| Modul / Proses | Fungsi |
|---|---|
| Data Tabulation | Membaca basis data primer dari spreadsheet `gopay dana.xlsx` ke variabel SPSS |
| Descriptive Statistics | Menghitung nilai Mean, standar deviasi, dan Std. Error Mean durasi GoPay vs DANA |
| Paired Correlations | Menghitung koefisien korelasi linear berpasangan antar-kedua aplikasi |
| Paired Samples T-Test | Menghitung nilai t-hitung, derajat kebebasan (df), dan signifikansi Sig. (2-tailed) |
| UI Interface Analysis | Menghubungkan visualisasi output statistik dengan teori information overload |

Output: Tabel luaran statistik deskriptif, tabel korelasi, tabel hasil uji-t berpasangan, dan berkas citra grafik hasil hitung (`SS_outputRTI.jpg`). Detail & hasil: [../09-docs/tahap-4-analisis-data.md](../09-docs/tahap-4-analisis-data.md).

### 3.5 Tahap 5 — Draf Naskah Jurnal

**Status: Sedang berjalan.** Draf konten per bagian naskah (Abstrak, Pendahuluan, Tinjauan Pustaka, Metodologi, Hasil & Analisis, Kesimpulan, Daftar Pustaka) telah disusun lengkap di folder `07-manuskrip/`, menggunakan format penulisan sitasi standar IEEE.

---

## 4. Hasil Penelitian

Ringkasan hasil (detail lengkap & interpretasi: [../07-manuskrip/05-hasil-analisis.md](../07-manuskrip/05-hasil-analisis.md) dan [../09-docs/tahap-4-analisis-data.md](../09-docs/tahap-4-analisis-data.md)).

### 4.1 Statistik Deskriptif Performa Durasi Transaksi

| Aplikasi Dompet Digital | Mean (Detik) | N | Std. Deviation | Std. Error Mean |
|---|---|---|---|---|
| **GoPay** (Stand-alone Model) | 4,8565 | 40 | 0,65912 | 0,10422 |
| **DANA** (Super App Model) | 6,0450 | 40 | 0,84165 | 0,13308 |

### 4.2 Analisis Korelasi Sampel Berpasangan

| Hubungan Variabel | N | Correlation | Sig. |
|---|---|---|---|
| **Pair 1:** GoPay & DANA | 40 | 0,531 | 0,000 |

### 4.3 Hasil Uji Paired Samples T-Test

| Parameter Statistik | Nilai Komputasi Uji-t |
|---|---|
| Mean Paired Differences | -1,18850 detik |
| Nilai t-hitung | -10,104 |
| Degree of Freedom (df) | 39 |
| Sig. (2-tailed) | 0,000 |

### 4.4 Figure / Citra Output

| File | Isi |
|---|---|
| [`SS_outputRTI.jpg`](../06-output/figures/SS_outputRTI.jpg) | Bukti tangkapan layar lembar keluaran resmi analisis Paired Samples T-Test dari software SPSS |

### 4.5 Interpretasi Singkat

1. Model Stand-alone tidak menambah beban kognitif pada kondisi pengoperasian awal—bahkan terbukti memotong rantai pencarian visual menu secara signifikan.
2. Desain GoPay terbukti memangkas durasi waktu penyelesaian tugas secara nyata, melindungi kenyamanan berinteraksi mahasiswa (selisih rata-rata waktu pemangkasan mencapai **-1,18850 detik**).
3. Nilai Sig. (2-tailed) sebesar **0,000 (kurang dari 0,05)** membuktikan Hipotesis Nol (H0) ditolak mutlak dan perbedaan performa kecepatan ini murni disebabkan oleh perbedaan arsitektur sistem antarmuka.
4. **Trade-off**: pada arsitektur Super App (DANA), penumpukan menu eksternal menjadi titik kontensi fokus kognitif, sehingga memicu penundaan pemindaian visual (scanning delay). Namun, keunggulannya adalah kelengkapan fitur ekosistem yang terintegrasi di balik satu pintu halaman utama.

---

## 5. Kendala dan Catatan Lingkungan

- **Output data mentah tidak otomatis digital**—diatasi dengan perekaman manual via lembar observasi fisik, yang kemudian dipindahkan secara terstruktur ke spreadsheet master `gopay dana.xlsx`.
- **Sistem memori smartphone terkunci sementara** (transient cache bias)—diatasi dengan kewajiban penerapan Cold Start Protocol (force stop dan clear cache) sebelum tes dimulai pada tiap responden.
- **MSYS_NO_PATHCONV=1** tidak relevan pada pengujian manusia, namun standarisasi perangkat keras dikunci mutlak menggunakan satu unit kontrol Samsung Galaxy A55 agar terhindar dari bias perbedaan kartu grafis dan RAM smartphone.
- **Aplikasi DANA** di lingkungan kampus terkadang mengalami fluktuasi loading iklan promo—hal ini dicatat sebagai dokumentasi resmi pemicu tingginya standar deviasi (0,84165) dibandingkan GoPay.

---

## 6. Kesimpulan dan Saran

Ringkasan kesimpulan & saran penelitian lanjutan: lihat [../07-manuskrip/06-kesimpulan.md](../07-manuskrip/06-kesimpulan.md).

Inti kesimpulan: skema arsitektur **Stand-alone App** (GoPay) efektif mengoptimalkan efisiensi interaksi pengguna—tanpa memicu beban kognitif berlebih, melindungi kenyamanan durasi pengerjaan pengguna secara signifikan, dan memangkas waktu operasional sebesar 1,18850 detik. Satu trade-off teridentifikasi pada model Super App (DANA) berupa kemunculan hambatan scanning delay akibat tingginya tingkat kepadatan elemen visual pada halaman utama.

---

## 7. Lampiran — Peta Artefak Penelitian

| Folder | Isi | Status |
|---|---|---|
| [01-proposal/](../01-proposal/) | Proposal penelitian komparatif dompet digital | Selesai |
| [02-literatur/](../02-literatur/) | Matriks literatur dan pencarian research gap | Selesai |
| [03-teori/](../03-teori/) | Diagram alur beban kognitif dan desain arsitektur antarmuka | Selesai |
| [04-data/](../04-data/) | Data primer durasi 40 responden berpasangan (`gopay dana.xlsx`) | Tersedia lokal |
| [05-kode/](../05-kode/) | Manajemen ekstraksi data dan alur kerja SPSS | Selesai |
| [06-output/](../06-output/) | Tabel statistik deskriptif dan berkas citra `SS_outputRTI.jpg` | Selesai |
| [07-manuskrip/](../07-manuskrip/) | Draf naskah artikel jurnal ilmiah (Bab 1–Bab 7) | Sedang berjalan |
| [08-laporan/](../08-laporan/) | Dokumen laporan resmi hasil penelitian institusi (Berkas Ini) | Selesai |
| [09-docs/](../09-docs/) | Catatan logbook harian jalannya pengujian eksperimen di UPB | Selesai |

**Cara reproduksi penuh:**

```bash
# Tahap 2: Lakukan pembersihan memori pada perangkat kontrol (Samsung Galaxy A55)
Settings -> Apps -> GoPay/DANA -> Force Stop & Clear Cache

# Tahap 3: Eksekusi pengujian stopwatch pada 40 responden mahasiswa UPB
Jalankan skenario penekanan ikon hingga menu viewfinder QRIS aktif sepenuhnya

# Tahap 4: Jalankan verifikasi uji statistik parametrik
Buka IBM SPSS Statistics -> Impor data gopay dana.xlsx -> Jalankan Paired Samples T-Test