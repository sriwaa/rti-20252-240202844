# WS-03: Literature Mapping & Gap

> **Bab 3 — Literature Review, Research Gap & Baseline**

---

## Ringkasan Materi

### Literature Review = Positioning, Bukan Ringkasan

Literature review bukan merangkum paper satu per satu. Pendekatan yang benar adalah **concept-centric** — organisasi berdasarkan tema, metode, atau variabel. Tujuan: menemukan **pola, kontradiksi, dan gap**.

**Perbandingan pendekatan Author-centric vs Concept-centric:**

| Aspek | Author-centric (Hindari) | Concept-centric (Gunakan) |
|-------|--------------------------|---------------------------|
| Struktur | Per penulis/paper ("Rahman et al. menyatakan...") | Per konsep/metode ("Pendekatan berbasis transformer") |
| Tujuan | Ringkasan isi paper | Perbandingan metode & identifikasi gap |
| Contoh paragraph | "Rahman (2023) pakai CNN. Lee (2022) pakai LSTM. Zhang (2021) pakai RF." | "Tiga pendekatan dominan: CNN digunakan oleh 4 paper untuk representasi fitur visual; LSTM untuk data sekuensial; RF sebagai baseline klasik." |
| Hasil akhir | Daftar paper | Peta pengetahuan + gap yang teridentifikasi |

### Empat Jenis Research Gap

| Jenis Gap | Deskripsi | Contoh |
|-----------|----------|--------|
| **Performance Gap** | Performa belum memadai | Akurasi deteksi hanya 78% pada kasus tertentu |
| **Method Gap** | Pendekatan belum diterapkan | Belum ada yang pakai transformer untuk task ini |
| **Data Gap** | Dataset terbatas/tidak representatif | Semua studi pakai dataset sintetis |
| **Context Gap** | Belum diuji pada konteks berbeda | Belum ada evaluasi di negara berkembang |

Gap terkuat = kombinasi 2+ jenis.

### Systematic Search Strategy

1. **Database utama**: IEEE Xplore, ACM DL, Scopus
   - Akses IEEE/ACM melalui jaringan kampus atau VPN institusi
   - Alternatif bebas biaya: Google Scholar, ResearchGate ([researchgate.net](https://www.researchgate.net)), arXiv ([arxiv.org](https://arxiv.org))
2. **Boolean query** yang terdokumentasi eksplisit
   - Contoh: `("anomaly detection" OR "intrusion detection") AND ("deep learning" OR "neural network") NOT ("medical imaging")`
   - Gunakan tanda kutip untuk frasa eksak; AND/OR/NOT mengontrol scope
3. **Snowballing** — dua arah:
   - **Backward snowballing**: buka daftar referensi di paper kunci → telusuri paper yang dikutip
   - **Forward snowballing**: di Google Scholar, klik "Cited by" di bawah paper kunci → temukan paper yang mengutipnya
   - Ulangi 1–2 tingkat untuk membangun cakupan komprehensif
4. Klaim "belum ada penelitian" harus didukung **bukti pencarian**

### Baseline Selection — 3 Kriteria

| Kriteria | Pertanyaan |
|----------|-----------|
| **Relevan** | Apakah menyelesaikan masalah yang sama? |
| **Representatif** | Apakah mewakili common practice? |
| **State-of-the-Art** | Apakah terbaru/terbaik? |

Membandingkan deep learning 2024 dengan decision tree sederhana tanpa justifikasi = **straw man comparison** (perbandingan tidak jujur).

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Tujuan baca literatur | Mencari solusi yang sudah ada | Memahami apa yang belum terjawab |
| Cara membaca paper | Tutorial, how-to | Metode, limitasi, gap |
| Baseline | Framework terpopuler | State-of-the-art yang rigorous |
| Dokumentasi pencarian | Tidak diperlukan | Wajib (reproducible) |

### Istilah Penting

- **Concept-centric** — Organisasi literatur berdasarkan konsep/metode, bukan per penulis
- **Snowballing** — Backward (telusuri referensi) + Forward (cari yang mengutip paper kunci)
- **Research Position** — Pernyataan eksplisit posisi riset terhadap studi sebelumnya
- **Straw man comparison** — Memilih baseline lemah agar metode sendiri terlihat lebih baik

---

## Template A.3 — Literature Mapping & Gap Identification

```
LITERATURE MAPPING

Topik      : Analisis Komparatif Efisiensi UX pada Aplikasi DANA (Super App) dan GoPay (Stand-alone App).
Database   : Google Scholar
Query      : "Usability DANA GoPay", "Evaluasi UEQ DANA", "SUS GoPay", "Heuristic Evaluation E-wallet Indonesia". 
Tahun      : 2024 – 2026.
Hasil awal : 15 paper → Screening → 5 paper final

Literature Matrix (concept-centric):

| Study | Tahun | Method | Data | Result | Limitation |
|-------|-------|--------|------|--------|------------|
| M. Naufal | 2024 | UEQ | 30 User DANA  | DANA dinilai "Sangat Baik" secara subjektif. |  Tidak ada pengukuran waktu teknis (time-on-task). |
| P. Sa’adah et al. | 2024 | SUS | 100 User GoPay  | Skor SUS 70,15 (Grade C/Good). |  Fokus pada kegunaan umum, bukan kecepatan transaksi. |
| N.I. Rosyidah | 2026 | Heuristic Eval | 3 Expert Evaluator  | GoPay unggul tipis; DANA lebih informatif. |  Berdasarkan opini ahli, bukan performa real user. |
| Y.E. Achyani | 2024 | Usability (Nielsen) | 150 Responden  | Skor: ShopeePay > GoPay > DANA. |  Data berupa persentase kuesioner, bukan satuan detik. |
| Angga Permana | 2025 | UEQ (Comparative) | 45 Responden  | GoPay lebih efisien dibanding DANA & OVO. |  Belum ada pembuktian fisik menggunakan stopwatch. |


Pola yang ditemukan:
  Metode dominan     : Penggunaan kuesioner persepsi (SUS dan UEQ).
  Dataset umum       : Pengguna aktif e-wallet di kalangan mahasiswa dan masyarakat urban.
  Limitasi berulang  : Seluruh literatur masih bergantung pada data subjektif (apa yang dirasakan pengguna). Belum ada yang menggunakan metrik performa objektif (durasi waktu nyata).

GAP IDENTIFICATION

Gap 1: [Jenis: Method Gap]
  Deskripsi    : Penelitian mengenai efisiensi e-wallet saat ini hampir seluruhnya menggunakan metode berbasis persepsi (kuesioner UEQ/SUS), bukan pengukuran performa teknis secara langsung.
  Bukti        : Jurnal Muthi Naufal (2024), Angga Permana (2025), dan Achyani (2024) semuanya menggunakan kuesioner untuk mengukur "Efisiensi", sehingga hasilnya adalah opini pengguna, bukan data durasi waktu (detik) yang objektif.
  Signifikansi : Dengan menggunakan metode observasi langsung (stopwatch), hasil riset akan jauh lebih akurat secara saintifik dalam menentukan aplikasi mana yang paling cepat untuk transaksi.

Gap 2: [Jenis: Context Gap]
  Deskripsi    : Masih jarangnya perbandingan langsung antara aplikasi dompet digital dengan model bisnis yang berbeda (Super App vs Stand-alone App) dalam satu pengujian performa yang sama.
  Bukti        : Jurnal Rosyidah (2026) membandingkan DANA dan GoPay melalui Heuristic Evaluation (evaluasi ahli), namun belum ada yang menguji perbedaan performa keduanya ketika GoPay sudah resmi menjadi aplikasi terpisah (stand-alone).
  Signifikansi : Riset ini akan memberikan pandangan baru apakah pemisahan aplikasi (unbundling) benar-benar meningkatkan efisiensi pengguna secara signifikan atau tidak.

Baseline Selection:
| Baseline | Relevansi | Representatif | Source |
|----------|-----------|---------------|--------|
| Metode UEQ (Skala Efisiensi) | Menjadi tolok ukur hasil efisiensi berdasarkan "perasaan" pengguna. | Metode paling standar dalam evaluasi UX e-wallet (dipakai di 3 dari 5 jurnal). | Angga Permana (2025) & Muthi Naufal (2024) |
| 5 Komponen Usability Nielsen |  Memberikan definisi operasional tentang Efficiency dalam riset dompet digital.  |  Mewakili standar Common Practice dalam Ilmu Komputer (HCI).  | Yuni Eka Achyani (2024) |
```

---

## Latihan 1 — Concept-Centric Literature Table

Gunakan topik riset dari WS-02. Cari minimal 5 paper relevan menggunakan database akademik.

> **Panduan pencarian:**
> - Database: IEEE Xplore, ACM DL, Google Scholar, atau ResearchGate
> - Tulis query Boolean yang digunakan: contoh `("object detection" OR "image classification") AND ("edge computing") NOT ("medical")`. Dokumentasikan query secara eksplisit.
> - Akses gratis: buka Google Scholar → cari judul paper → klik [PDF] jika tersedia, atau akses lewat campus VPN

**Topik riset:** Analisis Komparatif Efisiensi UX pada Aplikasi DANA (Super App) dan GoPay (Stand-alone App)
**Query pencarian:** "Usability DANA GoPay", "Evaluasi UEQ DANA", "SUS GoPay", "Heuristic Evaluation E-wallet Indonesia"
**Database:** Google Scholar

| # | Study | Tahun | Method | Dataset | Result | Limitasi |
|---|-------|-------|--------|---------|--------|----------|
| 1 | Muthi Naufal | 2024 | UEQ (User Experience Questionnaire) | 30 Mahasiswa pengguna DANA | Aspek efisiensi DANA dinilai "Sangat Baik" dengan skor 2,29. | Data bersifat subjektif (persepsi), tidak ada pengukuran waktu teknis. |
| 2 | Puji Sa'adah et al. | 2024 | SUS (System Usability Scale) | 100 Responden pengguna GoPay | Skor SUS 70,15 (Kategori Good/Acceptable). | Tidak membandingkan secara langsung dengan aplikasi kompetitor. |
| 3 | N. I. Rosyidah | 2026 | Heuristic Evaluation | 3 Expert Evaluator (Ahli) | GoPay unggul pada efisiensi fitur; DANA lebih informatif. | Penilaian berdasarkan sudut pandang ahli, bukan performa user asli. |
| 4 | Y. E. Achyani | 2024 | Usability Testing (Nielsen Model) | 150 Responden (ShopeePay, GoPay, DANA) | Skor GoPay (83,5%) sedikit lebih tinggi dibanding DANA (82,1%). | Masih menggunakan skala Likert, bukan durasi waktu nyata (detik). |
| 5 | Angga Permana | 2025 | UEQ (Comparative Study) | 45 Pengguna aktif e-wallet | GoPay dinilai lebih efisien dibandingkan DANA dan OVO. | Tidak dilakukan observasi stopwatch terhadap jumlah klik/langkah. |

**Pola yang terlihat — Metode dominan:** Penggunaan kuesioner evaluasi standar seperti UEQ (User Experience Questionnaire) dan SUS (System Usability Scale) untuk mengukur persepsi pengguna.

**Limitasi yang berulang:** Mayoritas penelitian masih bergantung pada data subjektif (opini pengguna) melalui kuesioner dan belum ada yang melakukan pengujian performa objektif secara empiris seperti menghitung durasi waktu penyelesaian tugas (*time-on-task*) menggunakan stopwatch.

---

## Latihan 2 — Gap Identification

Berdasarkan tabel di Latihan 1, identifikasi gap.

| Jenis Gap | Ditemukan? | Gap Statement |
|-----------|-----------|---------------|
| Performance Gap | [X] Ya / [ ] Tidak | Belum ada data kuantitatif yang membuktikan apakah skor efisiensi tinggi pada kuesioner berbanding lurus dengan kecepatan waktu transaksi (detik). |
| Method Gap | [X] Ya / [ ] Tidak | Seluruh referensi menggunakan metode subjektif (UEQ/SUS/Heuristic); belum ada yang menerapkan *direct observation* dengan metrik *Time on Task*. |
| Data Gap | [ ] Ya / [ ] Tidak | |
| Context Gap | [X] Ya / [ ] Tidak | Belum ada evaluasi komparatif yang spesifik menguji aplikasi GoPay setelah rilis sebagai aplikasi mandiri (*stand-alone*) dibandingkan dengan model *super-app* DANA. |

**Gap utama yang dipilih:** Method & Performance Gap

**Mengapa gap ini penting (bukan sekadar "belum ada yang meneliti")?**
> Gap ini penting karena efisiensi merupakan variabel krusial dalam aplikasi finansial yang sangat memengaruhi kepuasan pengguna. Mengandalkan data persepsi (kuesioner) saja memiliki risiko bias yang tinggi. Dengan menutup *Method Gap* melalui pengukuran waktu nyata (*stopwatch*), riset ini akan memberikan validasi empiris apakah desain aplikasi *stand-alone* (GoPay) secara teknis memang lebih efisien daripada desain *super-app* (DANA), ataukah hanya sekadar "terasa" lebih cepat oleh pengguna. Data ini akan menjadi acuan objektif bagi pengembang dalam mengoptimalkan alur transaksi.

---

> ___________________________________________________

---

## Latihan 3 — Baseline Selection

Pilih 2 baseline dari literatur yang sudah dibaca.

| # | Baseline | Mengapa Relevan | Mengapa Representatif | Apakah SOTA? | Sumber |
|---|----------|----------------|----------------------|-------------|--------|
| 1 | Evaluasi UEQ (User Experience Questionnaire) | Mengukur variabel efisiensi berdasarkan persepsi pengguna. | Digunakan oleh mayoritas peneliti e-wallet (3 dari 5 paper). | Ya (Terbaru 2025) | Angga Permana (2025) |
| 2 | Usability Testing (Model Nielsen) | Menyediakan framework standar untuk mengukur komponen Efficiency. | Merupakan standar baku dalam pengujian usability aplikasi. | Ya (Terbaru 2024) | Y. E. Achyani (2024) |

**Apakah pemilihan baseline ini bisa dianggap straw man?** [ ] Ya / [X] Tidak
> Justifikasi: Pemilihan baseline ini bukan *straw man* karena kedua referensi tersebut merupakan penelitian terbaru (State-of-the-Art) tahun 2024-2025 yang menggunakan metode standar industri dan akademik. Riset saya tidak membandingkan dengan metode yang lemah, melainkan mencoba melengkapi (augmentasi) hasil baseline tersebut dengan data stopwatch yang lebih presisi.

---

## Refleksi

> Apa perbedaan antara "belum ada yang meneliti ini" (klaim tanpa bukti) dengan research gap yang valid? Bagaimana cara membuktikan bahwa sebuah gap benar-benar ada?

**Jawaban:**
> Klaim "belum ada yang meneliti" seringkali hanya asumsi pribadi tanpa dasar kuat, sedangkan *research gap* yang valid adalah kesenjangan pengetahuan yang ditemukan setelah melakukan tinjauan literatur secara sistematis. Gap yang valid didasarkan pada bukti bahwa penelitian sebelumnya memiliki batasan (limitasi) tertentu, seperti keterbatasan metode, data, atau konteks.
> 
> Cara membuktikan bahwa sebuah gap benar-benar ada adalah dengan menyusun **Literature Matrix (concept-centric)**. Melalui tabel tersebut, kita bisa memetakan secara hitam di atas putih bahwa meskipun topik tersebut sudah banyak dibahas, terdapat aspek spesifik (seperti pengukuran waktu teknis/stopwatch) yang secara konsisten belum disentuh oleh peneliti-peneliti sebelumnya. Bukti pencarian di database (seperti Google Scholar) dengan query yang relevan juga menjadi pendukung kuat bahwa gap tersebut memang nyata dan layak untuk diteliti.

---
