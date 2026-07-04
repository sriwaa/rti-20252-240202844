# WS-06: System-Experiment Mapping

> **Bab 6 — System Design sebagai Experimental Artifact**

---

## Ringkasan Materi

### Sistem = Instrumen Pengujian, Bukan Produk

Seorang engineer bertanya "apakah sistem bekerja?" — seorang peneliti bertanya "apa yang bisa dibuktikan sistem ini?" Sistem dalam riset adalah **artifact** — objek yang sengaja dibuat untuk menguji klaim spesifik.

### System as Experiment Model

```
RQ → Variable → System Component → Experimental Setup → Output
```

Setiap komponen sistem harus bisa ditelusuri ke variabel riset (top-down), dan setiap pengukuran harus menjawab RQ (bottom-up).

### Mapping Variabel ke Komponen

| Tipe Variabel | Peran di Sistem | Contoh |
|---------------|----------------|--------|
| **IV** (Independent) | Modul yang bisa di-toggle/swap | Algoritma A vs B |
| **DV** (Dependent) | Modul pengukuran | Logger, metrics collector |
| **CV** (Control) | Config yang dikunci | Dataset, parameter tetap |

Jika variabel tidak bisa di-map ke komponen apapun → arsitektur perlu didesain ulang.

### 4 Prinsip Desain Eksperimental

| Prinsip | Pertanyaan Kunci |
|---------|-----------------|
| **Traceability** | Komponen ini melayani variabel yang mana? |
| **Modularity** | Bisakah IV diubah tanpa memengaruhi yang lain? |
| **Controllability** | Apakah CV dieksternalisasi ke config file? |
| **Measurability** | Apakah sistem otomatis menghasilkan data yang dibutuhkan? |

### Variable Isolation melalui Arsitektur

- **Modular architecture** — Pisahkan berdasarkan variabel
- **Configuration-driven** — Ubah config (YAML/JSON), bukan code
- **Feature toggles** — On/off flag untuk ablation study

  Contoh config YAML dengan feature toggles:
  ```yaml
  model:
    type: cnn          # IV: ganti "rf" untuk kondisi baseline
  features:
    use_temporal: true  # toggle komponen temporal
    use_normalization: true  # toggle preprocessing
  experiment:
    seed: 42
    runs: 5
  ```
  Dengan pendekatan ini, berbeda kondisi eksperimen = berbeda satu baris config, **tanpa mengubah kode**.

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Tujuan sistem | Memenuhi kebutuhan user | Menguji hipotesis, menghasilkan bukti |
| Arsitektur | Optimasi performa & skalabilitas | Optimasi isolasi variabel & reprodusibilitas |
| Konfigurasi | Sering hardcoded | Dieksternalisasi ke config file |
| Fitur tambahan | Menambah nilai user | Menambah noise jika tidak terkait RQ |

### Istilah Penting

- **Artifact** — Objek yang sengaja dibuat untuk memecahkan masalah atau menguji proposisi
- **Traceability** — Kemampuan menelusuri hubungan RQ → variabel → komponen → output
- **Variable Isolation** — Mengubah hanya satu variabel sambil menahan yang lain konstan
- **Ablation Study** — Menguji kontribusi tiap komponen dengan melepasnya satu per satu
- **Configuration-driven Execution** — Semua parameter di config file, bukan hardcoded

---

## Template A.6 — Mapping RQ ke Arsitektur Sistem

```
SYSTEM-EXPERIMENT MAPPING

Research Question: Apakah terdapat perbedaan signifikan pada rata-rata durasi waktu transaksi (Time-on-Task) antara aplikasi GoPay (stand-alone) dan aplikasi DANA (super app) menggunakan perangkat terkontrol pada mahasiswa Universitas Putra Bangsa?

Variable → Component Mapping:
| Variabel | Tipe | Komponen Sistem | Cara Manipulasi/Pengukuran |
| :--- | :--- | :--- | :--- |
| Model Arsitektur Aplikasi | IV | App Interface (GoPay vs DANA) | Swapping/berpindah antar subjek aplikasi pada task yang identik. |
| Efisiensi Waktu | DV | Data Logger (Manual Stopwatch) | Mencatat durasi dari saat icon diklik hingga kamera QRIS aktif. |
| Spesifikasi Perangkat | CV | Testing Device & Network | Mengunci penggunaan 1 HP Samsung A55 dan Data Seluler tetap. |

4 Prinsip Desain:
[x] Traceability — Setiap komponen (Aplikasi, Stopwatch, HP) melayani variabel riset.
[x] Variable Isolation — IV (Aplikasi) bisa diganti tanpa mengubah metode ukur/perangkat (CV).
[x] Measurement Integration — Pengukuran DV (detik) sudah menyatu dalam alur pengujian menggunakan stopwatch.
[x] Reproducibility — Prosedur pengujian bisa direkonstruksi dengan hasil yang konsisten bagi 40 responden mahasiswa UPB.

Experimental Setup:
Input data: Skenario tugas tunggal (Akses fitur Scan QRIS).
Parameter: 1 Unit Smartphone Samsung A55, 40 Responden Mahasiswa, Data Seluler.
Output format: Log durasi waktu (detik/seconds).
```
---

## Latihan 1 — Variable-to-Component Mapping

**RQ:** Apakah terdapat perbedaan signifikan pada rata-rata durasi waktu transaksi (Time-on-Task) antara aplikasi GoPay (stand-alone) dan aplikasi DANA (super app) menggunakan perangkat terkontrol pada mahasiswa?

| Variabel | Tipe | Komponen Sistem | Cara Manipulasi / Pengukuran |
| :--- | :--- | :--- | :--- |
| Arsitektur Layanan | IV | App Environment (GoPay vs DANA) | Menukar instalasi aplikasi yang aktif digunakan responden. |
| Kecepatan Interaksi | DV | Time-on-Task Measurement Tool | Mengukur durasi penyelesaian tugas menggunakan stopwatch digital. |
| Performa Hardware | CV | Controlled Hardware (Device Tunggal) | Menggunakan spesifikasi RAM/Prosesor yang sama untuk semua tes. |

**Apakah semua variabel bisa di-map?** [X] Ya / [ ] Tidak
> **Jika tidak, komponen apa yang perlu ditambahkan?** Semua variabel sudah terpetakan secara lengkap ke dalam komponen setup eksperimen.
---

## Latihan 2 — 4 Prinsip Desain

| Prinsip | Status | Bukti / Penjelasan |
| :--- | :--- | :--- |
| Traceability | ✅ | Komponen aplikasi mewakili IV (model arsitektur) dan stopwatch mewakili DV (efisiensi). |
| Modularity | ✅ | Kita bisa mengganti GoPay dengan aplikasi lain (misal: OVO) tanpa merubah alat ukur stopwatch. |
| Controllability | ✅ | Semua parameter hardware dan jaringan dikunci dalam satu setup perangkat yang tetap. |
| Measurability | ✅ | Hasil akhir berupa angka (detik) yang objektif, bukan sekadar opini responden. |

**Prinsip mana yang paling sulit dipenuhi?** Controllability (Kontrol Lingkungan).
**Strategi untuk mengatasinya:**
> Memastikan kuota seluler penuh dan sinyal berada pada bar maksimal, serta menutup semua aplikasi latar belakang sebelum pengujian tiap responden dimulai.

---

## Latihan 3 — Ablation Study Planning

| Kondisi | Komponen A (Splash Screen) | Komponen B (Home Loading) | Komponen C (Navigasi Tombol) | Hasil yang Diharapkan |
| :--- | :--- | :--- | :--- | :--- |
| Full | ✅ Aktif | ✅ Aktif | ✅ Aktif | Baseline waktu transaksi total. |
| – A | ❌ (Tanpa Iklan) | ✅ | ✅ | Melihat pengaruh beban visual/iklan awal terhadap waktu. |
| – B | ✅ | ❌ (Pre-loaded) | ✅ | Menguji kecepatan murni interaksi UI tanpa hambatan server. |
| – C | ✅ | ✅ | ❌ (Shortcut/Widget) | Mengetahui efisiensi jika alur navigasi dipangkas. |

<<<<<<< HEAD
**Komponen mana yang diprediksi paling berkontribusi?** Komponen B (Home Loading).
=======
> **Panduan jumlah kondisi:** Untuk 3 komponen (A, B, C), kondisi minimal yang direkomendasikan:
> Full + (-A) + (-B) + (-C) = **4 kondisi dasar**. Jika waktu memungkinkan, tambahkan kombinasi ganda: (-A,-B), (-A,-C), (-B,-C) = **7 kondisi**. Sesuaikan dengan *computational cost* dan tenggat waktu penelitian.

| Kondisi | Komponen A | Komponen B | Komponen C | Hasil yang Diharapkan |
|---------|-----------|-----------|-----------|----------------------|
| Full | *Contoh: ✅ CNN* | *Contoh: ✅ Temporal features* | *Contoh: ✅ Z-score norm* | *Baseline penuh* |
| – A | ❌ (ganti RF) | ✅ | ✅ | |
| – B | ✅ | ❌ (tanpa temporal) | ✅ | |
| – C | ✅ | ✅ | ❌ (tanpa normalisasi) | |

**Komponen mana yang diprediksi paling berkontribusi?** _____
>>>>>>> ffac99b58491f20c5b78603a2b315eb77ca446fd
**Mengapa?**
> Karena pada Super App (DANA), sistem memuat lebih banyak aset dan menu secara bersamaan di halaman utama dibanding Stand-alone (GoPay), sehingga loading home menjadi titik hambat terbesar.

---

## Refleksi

> Apa risiko jika sistem dibangun seperti produk (monolitik, fitur lengkap) lalu baru dilakukan eksperimen? Mengapa arsitektur modular penting untuk riset?

**Jawaban:**
> Risikonya adalah munculnya *Confounding Variables* (variabel pengganggu). Jika sistem bersifat monolitik, kita tidak akan tahu secara pasti apakah lambatnya transaksi disebabkan oleh desain UI, banyaknya fitur iklan, atau arsitektur informasinya. Kita tidak bisa mengisolasi penyebab utamanya.

> Arsitektur modular penting untuk riset agar kita bisa melakukan **Isolasi Variabel**. Dengan modularitas, kita bisa mengubah satu bagian saja (IV) tanpa mengganggu bagian lain (CV), sehingga kesimpulan yang diambil benar-benar akurat dan membuktikan hubungan sebab-akibat yang jelas.

