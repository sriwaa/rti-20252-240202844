# Tahap 3 — Pengujian Beban Responden (Eksperimen Lapangan N=40)

**Status:** Selesai — matriks pengujian terhadap 40 responden (masing-masing 2 kali pengujian lintas aplikasi, total 80 running sesi) telah selesai dijalankan. Data primer mentah gabungan dan data pre-test diarsipkan bersama dalam folder `04-data/` pada file utama `GOPAY DANA.xlsx`.

**Bergantung pada:** [tahap-2-implementasi-protokol.md](tahap-2-implementasi-protokol.md)  
**File Terkait:** [rencana-penelitian.md](rencana-penelitian.md)

---

## Tujuan

Menyusun skenario dan mengeksekusi pengujian lapangan untuk membandingkan efisiensi model antarmuka Stand-alone (GoPay) sebagai baseline vs model Super App (DANA) sebagai kondisi intervensi kompleksitas visual, melalui tiga jenis pengamatan perilaku pengguna:

- **Legitimate interaction (Navigasi Lancar)** — sesi di mana responden melakukan pemindaian visual secara konstan tanpa kebingungan, mensimulasikan beban kognitif normal.
- **Overload interaction (Scanning Delay)** — sesi di mana responden mengalami kebingungan visual akibat kepadatan menu eksternal, mensimulasikan fenomena information overload yang menghambat pencarian menu QRIS.
- **Mixed interaction (Kombinasi Kondisi)** — pengamatan silang untuk mengukur bagaimana performa kecepatan responden saat berpindah dari satu model aplikasi ke aplikasi lainnya.

## Deliverable

- [x] Lembar panduan pengujian GoPay (pengukuran durasi interaksi bersih)
- [x] Lembar panduan pengujian DANA (pengukuran penundaan navigasi visual)
- [x] Kertas kuesioner kontrol gabungan (untuk mencatat karakteristik demografi responden)
- [x] Konfigurasi batasan waktu (maksimal 60 detik per penugasan) untuk tiap responden agar pengujian seragam
- [x] Luaran angka durasi riil dalam satuan detik (Time-on-Task) yang siap dipindahkan ke Excel untuk kebutuhan Tahap 4
- [x] Pre-test (kalibrasi akurasi stopwatch dan pembacaan instruksi lisan sebelum pengambilan sampel penuh)
- [x] Pengisian matriks sampel penuh N=40 responden (2 model aplikasi × 40 responden = 80 total data rekaman running)

---

## Desain Berkas Administrasi Lapangan (`05-prosedur/eksperimen/`)

Seluruh rangkaian pengujian ini dipandu dan dicatat menggunakan dokumen kerja berikut:

*   **Panduan_Instruksi_Lisan.docx** — Teks instruksi baku yang dibacakan oleh peneliti secara seragam kepada setiap responden agar tidak menimbulkan bias informasi.
*   **Lembar_Observasi_Cetak.pdf** — Lembar kertas fisik yang dibawa peneliti di lapangan untuk menuliskan langsung durasi detik hasil jepretan stopwatch secara manual di tempat.
*   **Form_Screening_Biodata.docx** — Kuesioner singkat untuk memastikan responden adalah mahasiswa aktif UPB Kebumen dan mencatat profil demografi dasar mereka.
*   **Matriks_Rotasi_Counterbalancing.xlsx** — Tabel pembagian giliran urutan uji coba aplikasi untuk memisahkan Responden 1-20 (Kelompok A) dan Responden 21-40 (Kelompok B).

---

### Skenario dan Alur Tugas Lapangan

| Skenario Pengujian | Petunjuk Pelaksanaan | Batasan Durasi | Variabel Pengendali |
|---|---|---|---|
| **Skenario GoPay** | Responden membuka menu QRIS dari halaman utama GoPay | Maksimal 60 detik | Durasi penemuan menu QRIS GoPay |
| **Skenario DANA** | Responden membuka menu QRIS dari halaman utama DANA | Maksimal 60 detik | Durasi penemuan menu QRIS DANA (terdapat visual clutter) |

**Strategi Pengujian Navigasi Visual:**
- **Kondisi Fokus (GoPay)** — antarmuka bersih langsung membawa mata responden ke tombol target utama, menguji efisiensi interaksi terfokus.
- **Kondisi Terdistraksi (DANA)** — banner promosi dan puluhan ikon layanan tambahan di beranda memicu kejenuhan pandangan (information overload), menguji sensitivitas hambatan psikomotorik pengguna.

---

### Matriks Pengumpulan Sampel

| Dimensi Kontrol | Nilai Pengelompokan |
|---|---|
| **Model Aplikasi (Variabel Independen)** | GoPay, DANA |
| **Varian Urutan Uji** | Kelompok A (GoPay -> DANA), Kelompok B (DANA -> GoPay) |
| **Jumlah Replikasi Sampel** | 40 Mahasiswa Universitas Putra Bangsa (UPB) |

Total running: **2 × 20 × 2 = 80 rekaman data individual**, dikontrol penuh oleh peneliti menggunakan lembar rotasi manual untuk memastikan keseimbangan distribusi sampel.

---

### Protokol Pelaksanaan Sesi

Untuk setiap responden nomor urut 1 sampai 40 dengan kombinasi urutan tertentu:

1. Peneliti melakukan penyiapan smartphone Samsung Galaxy A55: Tutup semua aplikasi latar belakang, jalankan **Cold Start Protocol** (Force Stop & Clear Cache).
2. Responden diposisikan duduk dengan nyaman di area pengujian kampus UPB Kebumen.
3. Peneliti membacakan instruksi tugas secara lisan dengan artikulasi yang seragam berdasarkan berkas panduan.
4. Tepat saat responden menyentuh ikon aplikasi di layar, peneliti menekan tombol **Start** pada stopwatch digital.
5. Responden melakukan penjelajahan visual secara mandiri untuk mencari dan membuka fitur pemindai QRIS.
6. Tepat saat jendela bidik kamera pemindai QRIS muncul sepenuhnya di layar, peneliti menekan tombol **Stop** pada stopwatch.
7. Durasi waktu riil dicatat ke dalam lembar observasi fisik, lalu dipindahkan ke dalam berkas `GOPAY DANA.xlsx`.

---

### Berkas Rekam Data Final (`04-data/`)

Seluruh data yang terkumpul di lapangan dikonsolidasikan langsung ke dalam berkas master berikut untuk dianalisis pada tahap berikutnya:
*   **GOPAY DANA.xlsx** — Lembar rekapitulasi utama yang memuat durasi waktu (Time-on-Task) dalam satuan detik dari 40 responden untuk kedua aplikasi, lengkap dengan profil demografi responden serta data pre-test awal.

---

## Hasil Uji Coba Awal (Pre-test / Smoke Test)

Sesi uji coba awal dilakukan terhadap 2 orang responden cadangan di luar sampel utama untuk mengukur kelayakan instrumen sebelum lembar data master diisi penuh.

**Iterasi Pertama (Masalah Pencatatan Data)**:  
Awalnya peneliti mencoba menggunakan aplikasi perekam layar (*screen recorder*) internal smartphone untuk melacak durasi waktu pemuatan piksel kamera. Namun, hasil evaluasi menunjukkan bahwa proses perekaman layar latar belakang memakan kapasitas kerja prosesor dan memicu penurunan performa visual aplikasi (lag), yang merusak keaslian durasi waktu penjelajahan responden.

**Perbaikan Operasional**:  
Perekaman layar dibatalkan total. Sebagai gantinya, pencatatan waktu dialihkan sepenuhnya menggunakan stopwatch fisik digital eksternal berkepresisian tinggi yang dioperasikan secara manual oleh peneliti selaku observer utama. Penggunaan memori perangkat Samsung Galaxy A55 menjadi stabil 100 persen dan bebas hambatan prosesor.

**Iterasi Kedua (Setelah Perbaikan)**:  
Uji coba ulang berjalan lancar dengan metode pencatatan stopwatch fisik, waktu tercatat secara bersih tanpa ada kendala sistem pada smartphone, sehingga aman untuk dilanjutkan ke pengambilan data matriks penuh N=40 mahasiswa.

---

## Hasil Pengumpulan Data Penuh (N=40 Mahasiswa)

Pengujian lapangan sesungguhnya terhadap 40 responden mahasiswa Universitas Putra Bangsa (UPB) Kebumen diselesaikan secara bertahap. Seluruh sesi berjalan lancar tanpa ada responden yang mengundurkan diri di tengah jalan. 

- Seluruh 40 baris data master pada spreadsheet `GOPAY DANA.xlsx` terisi penuh tanpa ada kolom kosong (*missing values*).
- Riwayat cache dibersihkan secara konsisten di awal setiap sesi, membuat kondisi pengujian selalu dimulai dari kondisi awal yang adil (*cold start*).
- Data kuantitatif berpasangan dari 40 responden ini dikunci secara permanen dan siap dijadikan input utama untuk analisis statistik parametrik pada Tahap 4.

---

## Catatan Lingkungan Pengujian

- Pengaturan **MSYS_NO_PATHCONV=1** tidak berlaku dalam eksperimen fisik ini karena seluruh data dipindahkan secara manual lewat entri data spreadsheet di komputer lokal, bukan melalui perintah Docker virtual di terminal.
- Penguncian layar smartphone pada tingkat kecerahan konstan terbukti krusial untuk menjaga stabilitas fokus mata responden saat berhadapan dengan perbedaan warna dasar antara antarmuka hijau (GoPay) dan biru (DANA).