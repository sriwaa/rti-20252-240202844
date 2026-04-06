# WS-01: Distorsi & Paradigma

> **Bab 1 — Research Mindset in IT**

---

## Ringkasan Materi

### Research Trust Model

Pengetahuan ilmiah tidak muncul langsung dari kenyataan. Ia melewati **6 tahap transformasi** yang masing-masing rawan distorsi:

```
Reality → Data → Processing → Analysis → Inference → Knowledge
```

Etika mencegah distorsi yang disengaja (fabrikasi, cherry-picking). Validitas mendeteksi distorsi yang tidak disengaja (confounding variable, sampling bias).

### Tiga Jenis Validitas

| Jenis | Pertanyaan | Contoh Ancaman |
|-------|-----------|----------------|
| **Internal Validity** | Apakah hubungan kausal benar ada? | Confounding variable |
| **External Validity** | Apakah bisa digeneralisasi? | Dataset terlalu homogen |
| **Construct Validity** | Apakah mengukur hal yang benar? | Metrik tidak sesuai klaim |

### Paradigma Riset

Mata kuliah ini menggunakan pendekatan **Positivist** (fenomena TI bisa diukur objektif melalui eksperimen terkontrol) diperkuat **Design Science Research** (artefak dibuat sebagai instrumen pengujian hipotesis, bukan tujuan akhir).

### Mode Berpikir Peneliti

**Curious** (mempertanyakan fenomena) → **Critical** (mengevaluasi klaim berdasarkan bukti) → **Systematic** (merancang investigasi terstruktur dan reproducible).

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Tujuan | Membuat sistem yang bekerja | Menghasilkan pengetahuan yang valid |
| Pertanyaan khas | "Bagaimana membuatnya jalan?" | "Apakah klaim ini benar?" |
| Ukuran sukses | Sistem berfungsi, client puas | Hipotesis terjawab, temuan tervalidasi |
| Kegagalan | Harus dihindari | Harus dilaporkan (negative result = kontribusi) |

### Istilah Penting

- **Research Mindset** — Pola pikir yang menuntut bukti dan mempertanyakan asumsi
- **Research Ethics** — Prinsip perilaku: kejujuran, objektivitas, keterbukaan, akuntabilitas
- **HARKing** — Hypothesizing After Results are Known — merumuskan hipotesis setelah melihat data
- **Falsifiability** — Hipotesis harus bisa dibuktikan salah

---

## Template A.1 — Research Mindset Self-Assessment

```
Nama Peneliti    : Sri Wahyuningsih
Tanggal          : 06 April 2026

1. Ketika membaca klaim "metode X 95% akurat":
   - Pertanyaan pertama saya: 
   Bagaimana karakteristik partisipan yang diuji dan apakah instrumen pengukurannya (seperti UEQ) sudah tervalidasi?
   - Data yang dibutuhkan untuk verifikasi: 
   Data mentah skor User Experience Questionnaire (UEQ), catatan waktu per tugas (Time per Completed Task), dan jumlah klik partisipan.

2. Posisi paradigma:
   - Pendekatan: [X] Positivis  [ ] Interpretivis  [ ] Design Science  [X] Mixed
   - Alasan: R
   iset ini menggunakan pendekatan Positivis karena mengukur efisiensi secara objektif (angka/statistik) dan menggunakan Mixed Method karena menggabungkan data kuantitatif dari Usability Testing dengan data persepsi subjektif dari kuesioner UEQ.

3. Identifikasi distorsi:
   - Asumsi tersembunyi: 
   Diasumsikan bahwa kenyamanan pengguna hanya dipengaruhi oleh metode autentikasi (PIN vs mToken), tanpa mempertimbangkan faktor eksternal seperti loyalitas terhadap brand bank tertentu.
   - Sumber bias potensial: 
   Sampling Bias karena hanya melibatkan 11 partisipan untuk pengujian skenario dan Hawthorne Effect karena peneliti memperhatikan langsung saat partisipan mengerjakan tugas.
   - Langkah mitigasi: 
   Melakukan uji normalitas (Shapiro-Wilk) untuk memastikan sebaran data valid dan menggunakan uji-t sampel independen untuk membuktikan apakah perbedaan hasil memang signifikan secara statistik atau hanya kebetulan.

4. Komitmen etika:
   - Data yang tidak akan dimanipulasi: 
   Skor asli dari 26 elemen pertanyaan dalam kuesioner UEQ dan catatan waktu murni hasil rekaman pengujian skenario.
   - Batasan yang diakui sejak awal: 
   Jumlah partisipan yang terbatas dan pengujian yang hanya fokus pada satu fitur (transfer uang ke bank lain), sehingga tidak mencerminkan seluruh pengalaman fitur aplikasi secara total.

---

## Latihan 1 — Identifikasi Distorsi

Pilih satu paper riset di bidang TI yang mengklaim "metode X meningkatkan performa." Telusuri setiap tahap Research Trust Model.

**Paper yang dipilih:**
> Judul: Analisis Perbandingan Metode Autentikasi pada Mobile Banking menggunakan Usability Testing dan User Experience Questionnaire (UEQ) (Studi pada BTN Mobile dan Livin' by Mandiri)  
> Penulis (Tahun): Gusti Agzalia, Aryo Pinandito, & Hanifah Muslimah Az-Zahra (2023)

| Tahap | Apa yang Dilakukan | Potensi Distorsi |
|-------|-------------------|------------------|
| Reality → Data | Mengumpulkan data waktu dan jumlah klik dari 11 partisipan saat melakukan transfer. | Sampling Bias: Jumlah partisipan (11 orang) terlalu kecil untuk mewakili profil jutaan nasabah bank yang beragam usia dan literasi digitalnya. |
| Data → Processing | Membersihkan data dan melakukan uji normalitas Shapiro-Wilk pada hasil rekaman. | Measurement Bias: Kesalahan manual saat menekan stopwatch atau menghitung jumlah klik selama proses pengujian skenario berlangsung. |
| Processing → Analysis | Mengolah data menggunakan uji-t sampel independen untuk membandingkan rata-rata skor. | Confounding Variable: Adanya variabel pengganggu seperti biaya SMS Rp500 pada BTN yang bisa merusak objektivitas penilaian partisipan terhadap "efisiensi" sistem. |
| Analysis → Inference | Menyimpulkan bahwa metode PIN lebih efisien dan memberikan impresi lebih baik daripada mToken. | Confirmation Bias: Peneliti mungkin cenderung mengunggulkan metode PIN karena secara umum memang lebih modern, sehingga mengabaikan aspek keamanan yang mungkin lebih kuat di mToken. |
| Inference → Knowledge | Mengklaim bahwa Livin' by Mandiri lebih unggul di semua aspek UX dibanding BTN Mobile. | Overgeneralization: Menganggap hasil dari satu fitur (transfer) sudah cukup untuk menilai kualitas keseluruhan aplikasi m-banking secara total. |

**Distorsi paling besar di tahap:** Reality → Data

**Dua distorsi spesifik yang teridentifikasi:**
1. Sampling Bias: Kriteria partisipan yang sangat spesifik (pengguna aktif yang sudah melakukan 5x transaksi)  membuat hasil riset ini tidak bisa digeneralisasi untuk pengguna baru atau calon nasabah yang belum familiar dengan aplikasi tersebut.
2. Hawthorne Effect: Karena peneliti memperhatikan langsung setiap tahap yang dilakukan partisipan agar tidak salah pilih fitur, hal ini menciptakan kondisi tidak alami yang membuat partisipan bertindak lebih hati-hati dibanding penggunaan sehari-hari di dunia nyata.

---

## Latihan 2 — Analisis Kasus Etika

Skenario: Seorang peneliti menemukan bahwa jika 3 data point outlier dihapus, hasil eksperimennya menjadi signifikan. Dengan outlier, hasilnya tidak signifikan.

| Perspektif | Analisis |
|------------|----------|
| Kejujuran ilmiah | Melaporkan kedua versi (dengan dan tanpa outlier). Menghapus data hanya agar hasil terlihat "bagus" atau signifikan tanpa alasan teknis yang jelas adalah bentuk devaluasi kebenaran. |
| Transparansi | Peneliti wajib menjelaskan alasan mengapa 3 data tersebut dianggap outlier (misal: karena error sistem atau gangguan teknis). Metode pembersihan data harus dituliskan secara detail di bagian metodologi agar pembaca tahu prosesnya. |
| Peer review | Dengan bersikap jujur, penelaah (reviewer) dapat memberikan masukan apakah penghapusan tersebut sah secara statistik atau justru indikasi bahwa metode yang diuji memang tidak stabil. |

**Keputusan akhir dan justifikasi:**
> Keputusan: Tetap menyertakan seluruh data dalam laporan, namun memberikan analisis tambahan pada hasil setelah outlier dihapus dengan penjelasan medis/teknis yang mendasari penghapusan tersebut.  
> Justifikasi: Dalam riset TI, integritas data lebih utama daripada hasil yang signifikan. Menghapus outlier tanpa transparansi termasuk dalam kategori manipulasi data. Jika outlier tersebut memang disebabkan oleh anomali teknis (bukan perilaku pengguna asli), maka penghapusan boleh dilakukan asalkan dideklarasikan secara terbuka agar tidak menyesatkan peneliti selanjutnya.

---

## Latihan 3 — Posisi Paradigma

**Topik riset:** Analisis Perbandingan Metode Autentikasi pada Mobile Banking menggunakan Usability Testing dan UEQ (Studi pada BTN Mobile dan Livin’ by Mandiri).

| Kriteria | Positivis | Interpretivis | Design Science |
|----------|-----------|---------------|----------------|
| Kesesuaian dengan topik (1–5) | 5 | 2 | 4 |
| Jenis data yang dikumpulkan | Data kuantitatif (detik waktu, jumlah klik, skor skala likert UEQ). | Data kualitatif (opini personal, perasaan pengguna secara mendalam). | Data pengujian artefak (prototipe desain atau fitur autentikasi baru). |
| Limitasi paradigma | Cenderung mengabaikan konteks emosional pengguna yang lebih luas di luar angka. | Hasil sangat subjektif dan sulit untuk digeneralisasi ke populasi besar. | Fokus pada fungsionalitas sistem, terkadang kurang mengevaluasi aspek sosial. |

**Paradigma yang dipilih:** Positivis (didukung oleh kerangka evaluasi Design Science).  
**Alasan:** Riset ini berfokus pada pengukuran fenomena secara objektif menggunakan standar yang baku (UEQ dan Usability Testing). Tujuan utamanya adalah untuk menguji hipotesis melalui angka dan statistik guna menarik kesimpulan yang tidak bias mengenai efisiensi sistem.

---

## Refleksi

> Sebelum membaca materi ini, apakah pernah mempertanyakan klaim "95% akurat"? Setelah memahami rantai distorsi, pertanyaan apa yang sekarang akan diajukan saat membaca paper?

**Jawaban:**
> Sebelum membaca materi ini, saya cenderung menerima klaim persentase akurasi atau efisiensi secara mentah-mentah asalkan terlihat "ilmiah". Namun, setelah memahami Research Trust Model, saya menyadari bahwa setiap angka melewati rantai transformasi yang rawan distorsi.
Sekarang, saat membaca paper, pertanyaan yang akan saya ajukan adalah:
1. "Bagaimana proses pengambilan datanya? Apakah ada sampling bias atau confounding variable (seperti biaya SMS pada BTN tadi) yang mengganggu hasil?"
2. "Apakah peneliti melakukan HARKing atau manipulasi outlier untuk mendapatkan hasil yang signifikan secara paksa?"
3. "Apakah instrumen pengukurannya benar-benar mengukur apa yang diklaim (validitas konstruk)?"