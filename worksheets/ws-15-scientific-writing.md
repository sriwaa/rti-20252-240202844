# WS-15: Scientific Writing

> **Bab 15 — Penulisan Ilmiah**

---

## Ringkasan Materi

### Scientific Argument Flow

```
Problem → Gap → RQ → Method → Result → Analysis → Conclusion → Contribution
```

Paper ilmiah adalah **satu argumen utuh** dari masalah ke kontribusi. Setiap node harus terhubung logis ke node sebelum dan sesudahnya.

### Struktur IMRAD

| Section | Peran | Pertanyaan Kunci |
|---------|-------|-----------------|
| **Introduction** | Motivasi + frame | Why is this needed? |
| **Method** | Deskripsi (reproducible) | How was it done? |
| **Results** | Laporan objektif | What was found? |
| **Discussion** | Interpretasi + refleksi | What does it mean? |
| **Conclusion** | Ringkasan + kontribusi | So what? |

### Logical Flow — "Red Thread"

Setiap paragraf menjawab satu pertanyaan dan memicu pertanyaan berikutnya. Alur logis ini harus terasa di tiga level:
1. **Antar-kalimat** dalam paragraf
2. **Antar-paragraf** dalam section
3. **Antar-section** dalam paper

### Internal Consistency

Setiap elemen yang dijanjikan di Introduction harus hadir di Discussion/Conclusion.

**Consistency Matrix:**
```
           Intro  Method  Result  Discuss  Conclude
RQ1          ✓      ✓       ✓       ✓        ✓
RQ2          ✓      ✓       ✓       ✗ ←      ✓
Metrik-X     ✗      ✗       ✓ ←     ✗        ✗
```
**Masalah:** RQ2 dibahas di semua bagian kecuali Discussion. Metrik-X muncul di Result tapi tidak diperkenalkan di Method.

### Writing Quality Triad

| Kualitas | Deskripsi | Contoh Buruk → Baik |
|----------|----------|---------------------|
| **Clarity** | Dipahami sekali baca | "Performa meningkat" → "Accuracy meningkat dari 85.3% ke 89.7%" |
| **Precision** | Istilah eksak, tanpa ambiguitas | "signifikan" → "signifikan secara statistik (p=0.003, d=1.2)" |
| **Conciseness** | Setiap kata menambah informasi | Hapus kalimat redundan, filler words |

### Urutan Penulisan yang Disarankan

1. **Method & Results** — paling stabil, tulis pertama
2. **Discussion** — interpretasi berdasarkan hasil
3. **Introduction** — frame sesuai temuan aktual
4. **Abstract & Conclusion** — terakhir

### Target Jumlah Kata

| Section | Target |
|---------|--------|
| Introduction | 500–700 |
| Related Work | 700–1000 |
| Method | 800–1200 |
| Results | 500–800 |
| Discussion | 600–900 |
| Conclusion | 200–400 |

### Jebakan Kognitif

1. "Lebih panjang = lebih lengkap" → conciseness lebih berharga
2. "Introduction harus ditulis pertama" → justru ditulis terakhir
3. "Jargon teknis = lebih ilmiah" → clarity lebih penting
4. "Discussion = ringkasan Results" → Discussion = interpretasi + konteks

---

## Template A.15 — Paper Structure Checklist

```
PAPER STRUCTURE CHECKLIST

Title   : ____________________
Target  : [ ] Jurnal  [ ] Konferensi  [ ] Laporan

Section Check:
  [ ] Abstract — masalah, metode, hasil utama, kontribusi (max 250 kata)
  [ ] Introduction — konteks → gap → RQ → kontribusi → struktur paper
  [ ] Related Work — concept-centric, gap positioning
  [ ] Method — reproducible: desain, variabel, metrik, setup, prosedur
  [ ] Results — tabel + grafik + observasi (tanpa interpretasi)
  [ ] Discussion — interpretasi, perbandingan, implikasi, limitation
  [ ] Conclusion — jawaban RQ, kontribusi, future work

Consistency Matrix:
  [ ] RQ di Introduction = RQ di Method = RQ di Conclusion
  [ ] Variabel di Method = variabel di Results
  [ ] Klaim di Discussion didukung data di Results
  [ ] Limitasi di Discussion di-address di Conclusion/Future Work

Writing Quality:
  [ ] Clarity — mudah dipahami tanpa re-read
  [ ] Precision — tidak ada istilah ambigu
  [ ] Conciseness — tidak ada kalimat redundan
```

---

## Latihan 1 — Paper Outline

Buat outline paper untuk riset Anda menggunakan struktur IMRAD.

| Section | Konten Utama (2-3 kalimat) | Target Kata |
|---------|---------------------------|------------|
| Abstract | Fitur pembayaran QRIS menuntut efisiensi waktu muat demi kepuasan transaksi. Penelitian ini membandingkan durasi inisialisasi QRIS antara GoPay (*stand-alone*) dan DANA (*super app*) menggunakan data 40 responden. Hasil *Paired Samples T-Test* menunjukkan GoPay secara signifikan lebih cepat 1.18 detik ($p < 0.001$), membuktikan keunggulan arsitektur aplikasi terfokus. | 200-250 |
| Introduction | QRIS menjadi pilar transaksi digital di lingkungan mahasiswa, namun kompleksitas *bloatware* pada aplikasi sering kali memperlambat *response time*. Riset terdahulu banyak berfokus pada sisi keamanan data, sementara studi komparasi waktu muat murni berbasis arsitektur aplikasi (*stand-alone* vs *super app*) masih sangat terbatas. Penelitian ini bertujuan mengukur signifikansi perbedaan durasi tersebut untuk memberikan acuan optimasi UI/UX fintech. | 500-700 |
| Related Work | Meninjau literatur mengenai arsitektur *Super App* vs *Stand-alone App*, beban *resource rendering* antarmuka, serta pengaruh *Time-on-Task* terhadap kepuasan pengalaman pengguna (UX). | 700-1000 |
| Method | Eksperimen dilakukan dengan pendekatan kuantitatif parametrik berpasangan (*paired design*) melibatkan 40 responden mahasiswa UPB Kebumen. Variabel bebas adalah jenis aplikasi (GoPay dan DANA), sedangkan variabel terikat adalah durasi waktu muat fitur QRIS dalam satuan detik yang dicatat menggunakan perekam layar beresolusi tinggi. Data dianalisis via SPSS menggunakan *Paired Samples T-Test*. | 800-1200 |
| Results | Menyajikan tabel data deskriptif dan visualisasi grafik durasi muat kedua aplikasi. GoPay mencatatkan rerata waktu muat sebesar 4.85 detik, sementara DANA mencatatkan waktu 6.04 detik. Hasil uji inferensial menunjukkan nilai $t(39) = -10.104$ dengan tingkat signifikansi $p = .000$ ($p < 0.001$), menandakan hipotesis nol (H₀) ditolak secara telak. | 500-800 |
| Discussion | Menginterpretasikan bahwa perbedaan 1.18 detik disebabkan oleh ringannya beban inisialisasi memori pada GoPay yang bersifat terfokus dibandingkan DANA yang harus memuat banyak modul *background service*. Batasan riset ini terletak pada variasi spesifikasi gawai responden yang belum dikelompokkan secara spesifik. | 600-900 |
| Conclusion | Penelitian menyimpulkan bahwa aplikasi bertipe *stand-alone* (GoPay) menawarkan performa kecepatan QRIS yang jauh lebih unggul secara signifikan dibanding *super app* (DANA). Kontribusi riset ini menjadi referensi empiris bagi pengembang *fintech* dalam mengoptimalkan kecepatan respons fitur kritikal. | 200-400 |

---

## Latihan 2 — Consistency Matrix

Buat consistency matrix untuk memverifikasi internal consistency paper Anda.

|  | Intro | Method | Result | Discussion | Conclusion |
|--|-------|--------|--------|-----------|-----------|
| RQ1 | ✓ | ✓ | ✓ | ✓ | ✓ |
| Metrik utama | ✓ | ✓ | ✓ | ✓ | ✓ |
| Variabel IV | ✓ | ✓ | ✓ | ✓ | ✓ |
| Variabel DV | ✓ | ✓ | ✓ | ✓ | ✓ |
| Klaim/kontribusi | ✓ | ✓ | ✓ | ✓ | ✓ |

**Isi setiap sel:** ✓ (ada & konsisten), ✗ (missing), ~ (ada tapi inkonsisten)

**Inkonsistensi yang ditemukan:**
> Tidak ditemukan adanya inkonsistensi. Seluruh elemen mulai dari rumusan pertanyaan penelitian (RQ), definisi operasional variabel, hingga indikator hasil pengujian statistik parametrik telah terintegrasi secara runtut di setiap bab.

**Tindakan perbaikan:**
> Mempertahankan konsistensi terminologi penggunaan kata baku (seperti memakai istilah "waktu muat" secara konsisten, bukan berganti-ganti dengan kata "loading") di seluruh bagian teks dokumen.

---

## Latihan 3 — Writing Quality Check

Ambil satu paragraf dari tulisan Anda (atau tulis paragraf baru) dan evaluasi kualitasnya.

**Paragraf asli:**
> Berdasarkan dari pengujian yang sudah dilakukan oleh peneliti di lab kemarin, aplikasi bernama GoPay ternyata terbukti punya kecepatan yang lumayan lebih cepat banget jika dibandingkan sama aplikasi DANA pas dibuka menu QRIS-nya oleh para mahasiswa responden, di mana hasil ujinya itu kelihatan sangat signifikan sekali bedanya.

| Kriteria | Evaluasi | Perbaikan |
|----------|---------|-----------|
| Clarity | Paragraf mengandung kata non-baku ("pas", "kelihatan") dan struktur kalimat terlalu bertele-tele. | Mengubah kalimat menjadi formal dan fokus pada kejelasan subjek serta objek. |
| Precision | Frasa "lumayan lebih cepat banget" dan "sangat signifikan sekali" bersifat ambigu dan tidak ilmiah. | Menggantinya dengan representasi angka rata-rata durasi dan nilai statistik presisi ($t$-value dan $p$-value). |
| Conciseness | Terlalu banyak menggunakan kata pemborosan/filler ("berdasarkan dari", "sudah dilakukan", "oleh peneliti"). | Memangkas kata redundan agar langsung tertuju pada poin temuan inti eksperimen. |

**Paragraf setelah perbaikan:**
> Analisis inferensial menggunakan *Paired Samples T-Test* menunjukkan bahwa aplikasi GoPay memiliki rata-rata waktu muat fitur QRIS yang signifikan lebih cepat (4.85 detik) dibandingkan dengan aplikasi DANA (6.04 detik), dengan nilai $t(39) = -10.104$ dan tingkat signifikansi $p < 0.001$. Hasil ini secara empiris membuktikan adanya pengaruh nyata dari tipe arsitektur aplikasi terhadap efisiensi durasi transaksi digital.

---

## Refleksi

> Apa perbedaan antara menulis "tentang" riset dan menulis sebagai "argumen" riset? Bagaimana urutan penulisan (Method → Discussion → Introduction) mengubah kualitas tulisan?

**Jawaban:**
> Menulis "tentang" riset cenderung bersifat naratif-deskriptif yang hanya melaporkan kronologi jalannya aktivitas pengujian tanpa arah yang tajam. Sebaliknya, menulis sebagai sebuah "argumen" riset adalah menyusun dokumen ilmiah sebagai satu kesatuan fondasi bukti yang kokoh; di mana setiap data, kutipan teori, dan hasil statistik sengaja dihadirkan untuk mempertahankan posisi klaim peneliti dalam menjawab rumusan masalah (*Research Question*).
> 
> Mengubah urutan penulisan dengan mendahulukan bagian yang paling stabil (*Method* dan *Results*), kemudian disusul oleh *Discussion* dan *Introduction*, secara drastis meningkatkan objektivitas dan kualitas tulisan. Pendekatan ini menghindarkan peneliti dari jebakan bias kognitif (membuat narasi pengantar yang terlalu luas atau tidak nyambung dengan temuan riil), sehingga bab *Introduction* yang ditulis paling akhir dapat membingkai masalah secara presisi, jujur, dan selaras dengan fakta yang didapatkan di lapangan.