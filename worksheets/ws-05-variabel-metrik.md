# WS-05: Variabel & Metrik

> **Bab 5 — Metric, Measurement & Data**

---

## Ringkasan Materi

### Measurement Alignment Model

Setiap pengukuran yang valid harus bisa ditelusuri melalui rantai ini tanpa lompatan logis:

```
Problem → Concept → Variable → Metric → Data → Result
```

### Operationalization = Keputusan Desain

Menerjemahkan konsep abstrak menjadi variabel terukur bukan proses mekanis. "Code quality" yang diukur via SonarQube code smells membawa asumsi implisit. Setiap operasionalisasi harus didokumentasikan dan dijustifikasi.

### Empat Tipe Data (NOIR)

| Tipe | Ciri | Contoh | Operasi Valid |
|------|------|--------|---------------|
| **Nominal** | Kategori, tanpa urutan | Jenis algoritma (RF, SVM, CNN) | Modus, chi-square |
| **Ordinal** | Urutan, interval tidak sama | Skala Likert (1-5) | Median, Spearman |
| **Interval** | Jarak bermakna, tanpa nol absolut | Suhu Celsius | Mean, Pearson, t-test |
| **Ratio** | Jarak bermakna + nol absolut | Waktu eksekusi (ms) | Semua operasi |

Tipe data menentukan uji statistik yang valid. Kebanyakan metrik performa TI = ratio; persepsi pengguna = ordinal.

### Kriteria Pemilihan Metrik

- **Representative** — Mewakili konsep yang diteliti
- **Sensitive** — Cukup peka menangkap perbedaan bermakna (hindari ceiling effect)
- **Feasible** — Bisa dikumpulkan dalam batasan waktu dan biaya

### Pre-registration

Metrik harus ditentukan **sebelum** eksperimen. Memilih metrik setelah melihat data = **p-hacking**. Metrik tambahan yang ditemukan kemudian dilaporkan sebagai *exploratory*, bukan *confirmatory*.

### Primary vs Secondary Metric

- **Primary Metric** — Langsung terikat ke hipotesis, menentukan kesimpulan
- **Secondary Metric** — Pendukung, dilaporkan di samping primary; statusnya suplementer

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Pemilihan metrik | Berdasarkan kebiasaan/tool yang ada | Berdasarkan construct validity |
| Anomali | Dihapus untuk laporan bersih | Diinvestigasi — bisa jadi temuan |
| Kapan dipilih | Setelah sistem jadi (monitoring) | Sebelum eksperimen (by design) |

### Istilah Penting

- **Operationalization** — Transformasi konsep abstrak menjadi variabel terukur
- **Construct Validity** — Sejauh mana pengukuran benar-benar mengukur konsep yang dimaksud
- **Measurement Scale** — Klasifikasi data (NOIR) yang menentukan analisis valid
- **Multi-metric Evaluation** — Menggunakan beberapa metrik untuk menangkap konsep kompleks

---

## Template A.5 — Definisi Variabel, Metrik & Justifikasi

```
VARIABLE & METRIC DEFINITION

Research Question: Apakah terdapat perbedaan signifikan pada rata-rata durasi waktu transaksi (Time-on-Task) antara aplikasi GoPay (stand-alone) dan aplikasi DANA (super app) menggunakan perangkat terkontrol pada mahasiswa Universitas Putra Bangsa?

| Variabel | Tipe | Konsep | Metrik | Skala | Satuan | Cara Mengukur | Justifikasi |
|----------|------|--------|--------|-------|--------|---------------|-------------|
| Model Arsitektur Aplikasi | IV | Jenis struktur layanan e-wallet | Kategori: Stand-alone vs Super App | Nominal | - | Membedakan subjek uji antara GoPay dan DANA. | Merupakan variabel bebas yang dimanipulasi untuk melihat pengaruhnya. |
| Efisiensi Waktu | DV | Kecepatan interaksi pengguna | Time-on-Task (ToT) | Ratio | Detik (s) | Stopwatch digital (mulai dari klik icon aplikasi hingga kamera QRIS aktif). | Metrik standar efisiensi objektif dalam Human-Computer Interaction (HCI). |
| Spesifikasi Perangkat | CV | Performa Hardware & Koneksi | Satu unit smartphone yang identik | Nominal | - | Menggunakan 1 HP yang sama untuk seluruh responden. | Menghindari bias perbedaan kecepatan RAM/prosesor antar device responden. |

Alignment Check:
  RQ → Concept → Variable → Metric → Data → Result
  [X] Setiap langkah terdokumentasi
  [X] Tidak ada "lompatan logis"
  [X] Metrik mengukur apa yang dimaksud (construct validity)
```

---

## Latihan 1 — Operationalization Chain

Gunakan RQ dari WS-04. Definisikan variabel dan metriknya.

**RQ:** Apakah terdapat perbedaan signifikan pada rata-rata durasi waktu transaksi (Time-on-Task) antara aplikasi GoPay (stand-alone) dan aplikasi DANA (super app) menggunakan perangkat terkontrol pada mahasiswa?

| Variabel | Tipe | Konsep Abstrak | Metrik Konkret | Skala (NOIR) | Satuan |
|----------|------|---------------|----------------|-------------|--------|
| Model Aplikasi | IV | Arsitektur Layanan | Kategori: GoPay vs DANA | Nominal | — |
| Efisiensi | DV | Kecepatan Interaksi | Time-on-Task (ToT) | Ratio | Detik (s) |
| Perangkat | CV | Performa Hardware | Spesifikasi HP tunggal | Nominal | — |

**Apakah ada lompatan logis dalam rantai?** [ ] Ya / [X] Tidak
> Jika ya, di mana? Tidak ada. Konsep "efisiensi" dioperasionalisasikan secara langsung menjadi durasi waktu (detik) yang merupakan standar pengukuran performa teknis dalam pengujian usability (ISO 9241-11).

---

## Latihan 2 — Evaluasi Metrik

Evaluasi metrik DV yang dipilih di Latihan 1 menggunakan 3 kriteria.

| Kriteria | Skor (1-5) | Justifikasi |
|----------|-----------|-------------|
| Representative | 5 | Time-on-Task (ToT) secara langsung mewakili konsep efisiensi dalam penyelesaian tugas spesifik (transaksi QRIS). |
| Sensitive | 4 | Stopwatch mampu menangkap perbedaan waktu yang sangat kecil (milidetik) antara dua alur UI yang berbeda. |
| Feasible | 5 | Sangat mudah dikumpulkan menggunakan alat ukur standar tanpa memerlukan biaya tambahan atau perangkat lunak mahal. |

**Apakah perlu secondary metric?** [X] Ya / [ ] Tidak
> Jika ya, apa dan mengapa? **Success Rate (Berhasil/Gagal)**. Metrik ini penting untuk memastikan bahwa responden tidak hanya cepat dalam menekan tombol, tetapi benar-benar sampai ke tujuan yang benar (halaman scan QRIS).

**Contoh kasus ceiling effect untuk metrik ini:**
> Jika kedua aplikasi meletakkan fitur QRIS di tombol fisik atau gesture yang sangat instan, maka waktu yang dihasilkan akan sangat cepat (misal: semuanya 0.5 detik). Akibatnya, metrik waktu tidak lagi sensitif untuk menunjukkan perbedaan efisiensi antar kedua desain.

---

## Latihan 3 — Data Quality Check

Bayangkan data yang akan dikumpulkan dari eksperimen. Evaluasi 4 dimensi kualitas data.


| Dimensi | Pertanyaan | Jawaban | Strategi Mitigasi |
|---------|-----------|---------|------------------|
| Completeness | Apakah semua data point terkumpul? | Potensi data hilang jika responden membatalkan tugas di tengah jalan. | Memberikan briefing yang jelas di awal dan memastikan koneksi internet stabil sebelum tes dimulai. |
| Consistency | Apakah ada kontradiksi internal? | Ada risiko variasi waktu akibat faktor human error (salah klik karena grogi). | Memberikan waktu uji coba (trial) selama 1 menit agar responden terbiasa dengan perangkat uji. |
| Validity | Apakah benar-benar mengukur yang dimaksud? | Ya, durasi waktu akses QRIS secara valid mengukur efisiensi navigasi UI. | Menetapkan titik mulai (saat icon ditekan) dan titik henti (kamera scan aktif) yang seragam di setiap tes. |
| Representativeness | Apakah sampel mewakili populasi target? | Ya, selama sampel mencakup berbagai angkatan mahasiswa di UPB. | Melakukan teknik sampling di area publik kampus (kantin/perpustakaan) pada jam istirahat. |

---

## Refleksi

> Mengapa memilih metrik setelah melihat data dianggap p-hacking? Apa bedanya dengan eksplorasi data yang sah?

**Jawaban:**
> Memilih metrik setelah melihat data dianggap **p-hacking** karena peneliti secara tidak jujur hanya memilih metrik yang memberikan hasil "bagus" atau signifikan secara statistik demi memvalidasi hipotesisnya. Hal ini mencederai integritas ilmiah karena hasil riset menjadi bias dan tidak objektif.
>
> Perbedaannya dengan **eksplorasi data yang sah** terletak pada tujuannya. Eksplorasi data dilakukan untuk mencari wawasan atau pola baru tanpa mengklaimnya sebagai pembuktian hipotesis utama yang sudah ditentukan di awal. Temuan eksplorasi biasanya digunakan sebagai dasar untuk riset di masa depan, bukan sebagai kesimpulan final dari penelitian saat ini.

