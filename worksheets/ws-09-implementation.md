# WS-09: Implementation & Environment

> **Bab 9 — Implementasi Riset & Kontrol Lingkungan**

---

## Ringkasan Materi

### Implementasi Riset ≠ Coding Biasa

Tujuan implementasi riset bukan membuat software yang berfungsi, melainkan membangun **instrumen pengukuran yang konsisten**. Setiap modul harus di-mapping ke variabel (dari Bab 6), parameter harus config-driven, dan logging aktif dari hari pertama.

### Reproducible Implementation Model

```
Design → Implementation → Environment Setup → Execution Consistency → Reproducibility → Trustworthy Result
```

Setiap transisi memiliki syarat:
- Design → Implementation: kode sesuai mapping variabel-ke-komponen
- Implementation → Environment: versi, dependency, seed, path, OS eksplisit
- Environment → Consistency: seed terkunci, urutan deterministik
- Consistency → Reproducibility: dokumentasi lengkap
- Reproducibility → Trust: siapa pun ikuti dokumentasi → hasil sama/serupa

### Repeatability vs Reproducibility

| Level | Peneliti | Environment | Hasil |
|-------|---------|-------------|-------|
| **Repeatability** | Sama | Sama | Sama persis |
| **Reproducibility** | Berbeda | Berbeda (ikuti docs) | Sama/serupa |

Capai **repeatability** dulu, baru **reproducibility**.

### Engineering vs Research Perspective

| Aspek | Engineering | Research |
|-------|-----------|---------|
| Tujuan | Sistem berfungsi untuk user | Instrumen pengukuran konsisten |
| Dependency | Update ke terbaru | Lock di versi spesifik |
| Testing | Unit, integration, E2E | Repeatability test (run ulang → sama?) |
| Dokumentasi | User guide, API docs | Environment spec, execution steps, expected output |
| Config | Default masuk akal | Setiap parameter eksplisit & adjustable |

### Jebakan Kognitif

1. Menunda environment setup → bug sulit dilacak
2. Tidak pakai version control → hasil tidak bisa direkonstruksi
3. Menolak Docker/container → "di laptop saya bisa" saat review
4. 3× hasil sama ≠ repeatable (bisa cache/state tersimpan)

### Istilah Penting

- **Environment Specification** — Deskripsi lengkap: hardware, OS, runtime, library + versi, config, seed
- **Dependency** — Komponen eksternal yang harus di-lock versinya
- **Config-driven** — Parameter dieksternalisasi ke file konfigurasi, bukan hardcode

---

## Template A.9 — Dokumentasi Setup Eksperimen

```
EXPERIMENT SETUP DOCUMENTATION

Hardware:
  CPU     : Exynos 1480 Octa-core (Smartphone Samsung Galaxy A55 5G - Perangkat Utama Pengujian)
  RAM     : 12 GB LPDDR5
  GPU     : Xclipse 530
  Storage : 256 GB UFS 3.1 (Sisa storage dikondisikan low-load >50GB demi kestabilan sistem)
  Perangkat Ukur Eksternal : iPhone XS (Digunakan khusus sebagai instrumen pencatat waktu / *Stopwatch*)

Software:
  OS        : Android 14 dengan One UI 6.1 (Perangkat Samsung A55) & Windows 11 Home (Laptop Acer Aspire 3 untuk Analisis)
  Runtime   : Android Runtime (ART) & Java Virtual Machine (JVM 17 pada Acer Aspire 3 untuk IBM SPSS)
  Framework : Samsung Knox Core & Android Open Source Project (AOSP) Base UI Ecosystem
  
Dependencies:
| Library | Version | Sumber | Hash/Checksum |
|---------|---------|--------|---------------|
| GoPay Stand-alone | v1.12.0 | Google Play Store | APK-Ident-GP-01 |
| DANA Super App | v2.55.1 | Google Play Store | APK-Ident-DN-02 |
| IBM SPSS Statistics | v27.0 | Official IBM Installer | SHA-256-SPSS-ACER3 |
| Apple iOS Clock App | iOS 17 Native | Perangkat iPhone XS | Calibrated-iOS-Clock |
| Python (Data Prep) | v3.11.5 | Python Org (Acer Aspire 3) | SHA-256-PY3115 |

Konfigurasi:
  Config file     : Not Applicable (Instruksi lisan langsung secara seragam kepada setiap responden)
  Random seed     : Not Applicable (Pembagian manual: 20 responden awal GoPay-DANA, 20 responden akhir DANA-GoPay)
  Hyperparameters : `Threshold_Timeout = 60s`, `Inter_Session_Rest = 60s`, `Screen_Refresh_Rate = 120Hz`

Reproducibility Check:
  [✓] Dependency terdokumentasi (Versi aplikasi GoPay v1.12.0 dan DANA v2.55.1 dicatat secara konstan)
  [✓] Seed ditetapkan di semua level (Not Applicable - Pembagian kelompok counterbalancing dilakukan secara manual)
  [✓] Config di version control (Not Applicable - Kontrol eksperimen berbasis instruksi lisan langsung secara seragam)
  [✓] README instruksi reproduksi lengkap (Mencakup panduan lisan pengerjaan, pembersihan cache Samsung A55, dan input data ke SPSS di Acer Aspire 3)
```

---

## Latihan 1 — Environment Specification

Dokumentasikan environment untuk eksperimen Anda berdasarkan spesifikasi fisik perangkat nyata yang Anda gunakan di lapangan (Samsung A55, iPhone XS, dan Acer Aspire 3) tanpa embel-embel kode acak.

| Komponen | Spesifikasi |
|----------|------------|
| CPU | Exynos 1480 Octa-core (Sisi Perangkat HP) & Intel/AMD Processor (Sisi Laptop Acer Aspire 3) |
| RAM | 12 GB RAM (Samsung Galaxy A55 5G) |
| GPU | Samsung Xclipse 530 (Mobile Graphics) |
| OS | Android 14 One UI 6.1 (Perangkat Uji) & Windows 11 Home (Laptop Analisis) |
| Runtime | Android Runtime (ART) & Java Virtual Machine (JVM 17 untuk Eksekusi SPSS) |
| Framework | Samsung Knox Core & Android Open Source Project (AOSP) Base UI Ecosystem |
| Random Seed | Not Applicable (Pembagian kelompok counterbalancing dilakukan secara manual langsung di lapangan) |

**Dependencies (minimal 5):**

| Library | Version | Alasan Dibutuhkan |
|---------|---------|-------------------|
| GoPay App | v1.12.0 | Objek pengujian utama untuk Independent Variable (IV) model aplikasi Stand-alone. |
| DANA App | v2.55.1 | Objek pengujian utama untuk Independent Variable (IV) model aplikasi Super App. |
| IBM SPSS Statistics | v27.0 | Software statistik di laptop Acer Aspire 3 untuk uji hipotesis Paired Samples T-Test. |
| Apple iOS Clock App | iOS 17 Native | Fitur Stopwatch bawaan iPhone XS sebagai instrumen pencatat waktu transaksi (ToT). |
| Android OS System UI | v14.0 | Sistem antarmuka dasar pada HP Samsung A55 untuk menjamin kelancaran rendering layar aplikasi. |

---

## Latihan 2 — Repeatability Test Plan

Rancang tes repeatability sederhana: jalankan skenario pengujian akses menu QRIS yang sama sebanyak 3 kali secara mandiri oleh peneliti menggunakan perangkat kontrol yang sama.

| Run | Seed | Metrik Utama | Hasil Sama? |
|-----|------|-------------|-------------|
| 1 | Not Applicable | Time-on-Task (ToT) Akses QRIS GoPay (detik) | — |
| 2 | Not Applicable | Time-on-Task (ToT) Akses QRIS GoPay (detik) | [✓] Ya / [ ] Tidak |
| 3 | Not Applicable | Time-on-Task (ToT) Akses QRIS GoPay (detik) | [✓] Ya / [ ] Tidak |

**Jika hasil berbeda, kemungkinan penyebab:**
> Durasi detik waktu transaksi dapat sedikit bergeser karena fluktuasi kecepatan internet (latensi jaringan) di area kampus UPB Kebumen saat memuat menu QRIS, atau akibat ketepatan refleks motorik tangan peneliti saat menekan tombol stopwatch di iPhone XS.

**Checklist kontrol yang sudah diterapkan:**
- [✓] Not Applicable (Pembagian urutan pengerjaan responden dikunci manual 20-20)
- [✓] Tidak ada background process yang mengganggu (Mengaktifkan fitur Do Not Disturb di Samsung A55 dan mematikan auto-update)
- [✓] Cache dibersihkan antar-run (Menerapkan protokol Cold Start dengan Force Stop dan Clear Cache setiap kali sesi uji selesai)
- [✓] Instruksi lisan yang sama untuk semua run (Instruksi lisan disampaikan secara seragam tanpa mengubah kalimat petunjuk)

---

## Latihan 3 — README Eksperimen

Tulis README minimum untuk eksperimen Anda (6 komponen wajib).

# Judul Eksperimen: Analisis Efisiensi Waktu Transaksi QRIS Menggunakan Model Stand-alone App (GoPay) vs Super App (DANA) Pada Mahasiswa UPB Kebumen

## 1. Environment
* **Perangkat Uji Utama:** Samsung Galaxy A55 5G (Exynos 1480, 12 GB RAM, Android 14 One UI 6.1)
* **Perangkat Pengukur Durasi:** iPhone XS iOS 17 Native Clock App (Stopwatch)
* **Perangkat Analisis Statistik:** Laptop Acer Aspire 3 (Windows 11 Home, IBM SPSS v27.0)
* **Subjek & Lokasi:** 40 Responden Mahasiswa Aktif Universitas Putra Bangsa, Kampus Kebumen

## 2. Installation
1. Pastikan smartphone Samsung Galaxy A55 5G sudah terinstal aplikasi GoPay v1.12.0 (Stand-alone) dan DANA v2.55.1 (Super App) versi resmi dari Google Play Store.
2. Tempatkan ikon aplikasi GoPay dan DANA secara berdampingan di halaman utama (home screen) HP Samsung A55 untuk mempermudah akses saat pengujian dimulai.
3. Pastikan kedua aplikasi sudah dalam kondisi login aktif (sesi akun terbuka), sehingga saat ikon diklik tidak tertahan oleh halaman login.
4. Instalasi software IBM SPSS Statistics v27.0 pada laptop Acer Aspire 3 untuk persiapan pemrosesan data kuantitatif akhir.

## 3. Data
* **Jenis Data:** Data Kuantitatif Primer (Skala Rasio dalam satuan detik).
* **Format Pengumpulan:** Logbook fisik pencatatan lapangan yang kemudian dipindahkan ke file tabel .csv dengan kolom: ID_Responden, Kelompok_Uji, ToT_GoPay (detik), dan ToT_DANA (detik).
* **Ukuran Sampel:** Total 40 baris data entri dari 40 responden mahasiswa aktif UPB Kebumen (N=40).

## 4. Execution
1. Sebelum pengujian per responden dimulai, buka pengaturan aplikasi Android di Samsung A55, pilih aplikasi GoPay/DANA, lalu lakukan 'Force Stop' dan 'Clear Cache' (Protokol Cold Start) agar aplikasi benar-benar mati total.
2. Kondisikan layar HP Samsung A55 pada posisi Home Screen Android yang menampilkan ikon GoPay dan DANA, lalu serahkan smartphone ke responden mahasiswa sesuai urutan kelompoknya.
3. Berikan instruksi lisan secara langsung dan seragam: "Klik ikon aplikasi ini dan langsung akses sampai menu scan QRIS terbuka secepat mungkin setelah aba-aba mulai".
4. Penguji menekan tombol 'Start' pada stopwatch iPhone XS tepat saat jempol responden mengetuk ikon aplikasi di Home Screen HP, dan menekan 'Stop' tepat saat layar pemindai kamera (viewfinder) QRIS di dalam aplikasi terbuka sempurna.
5. Catat hasil durasi ke logbook, berikan jeda istirahat sistem selama 1 menit, lalu kembalikan HP ke kondisi Home Screen Android untuk menguji aplikasi pembandingnya.

## 5. Configuration
* Kunci jaringan seluler pada satu provider yang sama sepanjang waktu eksperimen di titik lokasi lingkungan kampus UPB Kebumen untuk menghindari bias latensi sinyal.
* Tingkat kecerahan layar HP Samsung A55 diatur konstan pada angka 50%, dan refresh rate layar dikunci statis pada tingkat 120Hz.
* Pembagian kelompok responden dilakukan secara manual: Responden nomor urut 1-20 masuk Kelompok A (menguji GoPay dulu baru DANA), sedangkan responden nomor urut 21-40 masuk Kelompok B (menguji DANA dulu baru GoPay).

## 6. Expected Output
Output yang diharapkan berupa file data mentah berformat .sav dan log output tabel hasil analisis statistik inferensial dari IBM SPSS v27.0. Hasil pengujian Paired Samples T-Test diharapkan menolak H₀ dengan nilai signifikansi p-value (2-tailed) < 0.05, yang membuktikan secara empiris bahwa model arsitektur Stand-alone (GoPay) menghasilkan durasi waktu transaksi (Time-on-Task) yang lebih cepat secara signifikan dibandingkan arsitektur Super App (DANA).

---

## Refleksi

> Apakah eksperimen Anda saat ini bisa direproduksi oleh orang lain tanpa bantuan Anda? Komponen apa yang masih hilang?

**Level saat ini:** [✓] Repeatability / [ ] Reproducibility / [ ] Belum keduanya

**Komponen yang belum terdokumentasi:**
> Eksperimen riset saya saat ini berada pada tingkatan **Repeatability** yang matang karena saya selaku peneliti mampu mengulang seluruh rangkaian prosedur pada infrastruktur Samsung A55, iPhone XS, dan laptop Acer Aspire 3 milik saya sendiri dengan hasil yang konsisten. Komponen yang masih belum terdokumentasi sempurna untuk mencapai level *Reproducibility* total (dapat direplikasi oleh peneliti independen lain secara mandiri) adalah petunjuk penyesuaian skor atau *hardware variance calibration guide*. Komponen ini krusial jika peneliti lain melakukan replikasi menggunakan tipe smartphone dengan spesifikasi chipset atau kapasitas RAM yang berada di bawah Samsung A55, yang mana perbedaan spesifikasi hardware tersebut pasti akan menciptakan perbedaan basis kecepatan muat aplikasi (*baseline rendering speed*) di luar variabel antarmuka yang sedang diuji.
