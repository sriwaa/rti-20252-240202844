# WS-16: Presentation & Defense (UAS)

> **Bab 16 — Presentasi & Pertahanan Ilmiah**

---

## Ringkasan Materi

### Scientific Defense Model

```
Research Work → Presentation → Questioning → Defense → Evaluation → Acceptance
```

### Presentasi ≠ Ringkasan Paper

| Paper | Presentasi |
|-------|-----------|
| Dibaca (self-paced) | Didengar (presenter-paced) |
| Detail lengkap | Ide kunci + highlight |
| Tabel numerik detail | Grafik visual + angka kunci |
| Pembaca bisa re-read | Audiens dengar sekali |

**Prinsip:** Presentasi membutuhkan **reformulasi**, bukan kompresi. Medium berbeda = pendekatan berbeda.

### Claim-Evidence-Reasoning (CER)

Setiap jawaban defense harus memiliki:
1. **Claim** — Pernyataan yang dijawab
2. **Evidence** — Data/fakta pendukung
3. **Reasoning** — Logika yang menghubungkan evidence ke claim

**Contoh:**
| Pertanyaan | Bad Answer | Good Answer (CER) |
|-----------|-----------|-------------------|
| "Kenapa hanya 3 dataset?" | "Tiga sudah cukup" | "3 dataset mewakili variasi: small-clean, medium-clean, medium-noisy [E]. Generalisasi perlu validasi lanjut — listed as limitation [R]" |
| "Hasil DS-3 menurun?" | "Itu outlier" | "Ya, karena distribusi heavy-tail melanggar asumsi Gaussian [E]. Ini menunjukkan boundary condition metode [R]" |
| "Effect size?" | "p=0.003, jadi signifikan" | "Cohen's d=1.2 (large effect) [E] — bukan hanya signifikan tapi substansial [R]" |

### Slide Design — One Slide, One Message

**Optimal 9-Slide Plan (15 menit):**

| # | Slide | Waktu | Pesan |
|---|-------|-------|-------|
| 1 | Title + context | 1 min | Apa ini tentang apa |
| 2 | Problem + motivation | 2 min | Mengapa penting |
| 3 | Gap + RQ | 1.5 min | Apa yang belum terjawab |
| 4 | Method overview | 2 min | Bagaimana dijawab (diagram) |
| 5 | Key result — tabel | 2 min | Temuan utama |
| 6 | Key result — grafik | 2 min | Pola visual |
| 7 | Interpretation + failure | 2 min | Apa artinya |
| 8 | Limitation + future | 1.5 min | Batasan & arah |
| 9 | Conclusion + contribution | 1 min | Closing message |

### Anticipatory Defense

Prediksi pertanyaan berdasarkan kategori:

| Kategori | Contoh Pertanyaan |
|---------|------------------|
| Problem | "Mengapa masalah ini penting?" |
| Gap | "Bagaimana dengan studi X yang sudah menjawab ini?" |
| Method | "Mengapa metode ini, bukan Y?" |
| Results | "Bagaimana menjelaskan anomali di DS-3?" |
| Generalization | "Apakah bisa diterapkan di domain lain?" |

### Tiga Prinsip Jawaban

1. **Direct** — Jawab dulu, elaborasi kemudian
2. **Data-based** — Tunjuk evidence spesifik
3. **Honest** — Akui limitasi jika memang ada

### Jebakan Kognitif

1. "Presentasi = semua yang ada di paper" → terlalu padat
2. "Slide cantik = presentasi bagus" → konten > estetika
3. "Tidak bisa jawab = gagal" → "I don't know, but..." menunjukkan kejujuran
4. "Tidak perlu latihan — saya paham riset saya" → latihan = menemukan celah

---

## Template A.16 — Defense Preparation Sheet

```
DEFENSE PREPARATION

Slide Deck Plan:
  Total slides   : 11 (target: 10-12 konten + title/closing)
  Time per slide : ~1.5 - 2 min
  Total time     : 15 menit

Slide Outline:
| # | Pesan Utama | Visual | Waktu |
|---|-------------|--------|-------|
| 1 | Title & Context | Identitas Peneliti + Judul Komparasi QRIS | 30s |
| 2 | Problem & Motivation | Urgensi Latensi Transaksi Fintech Mobile | 2min |
| 3 | Gap + RQ | Batasan Riset Terdahulu & Rumusan Masalah | 1.5min |
| 4 | Method Overview | Diagram Alir Pengujian Sepasang Responden | 2min |
| 5 | Key Result — Tabel | Output Tabel Deskriptif SPSS (Mean & Std) | 2min |
| 6 | Key Result — Grafik | Bar Chart Perbandingan Durasi GoPay vs DANA | 2min |
| 7 | Interpretation | Analisis Efisiensi Stand-alone vs Super App | 2min |
| 8 | Limitation + Future | Batasan Demografi Kampus & Kelompok Gawai | 1.5min |
| 9 | Conclusion | Jawaban Signifikan RQ & Kontribusi Praktis | 1min |

Anticipatory Defense Matrix:
| Kategori | Pertanyaan Potensial | Jawaban (CER) |
|----------|---------------------|---------------|
| Problem  | Mengapa perbedaan waktu muat QRIS ini penting diteliti? | **Claim:** Latensi inisialisasi QRIS berdampak langsung pada efisiensi antrean fisik kasir.<br>**Evidence:** Teori interaksi manusia-komputer menyatakan tunda >1 detik menurunkan kepuasan UX.<br>**Reasoning:** Memahami aplikasi mana yang lebih tangkas memotong waktu transaksi membantu optimasi UI/UX finansial digital. |
| Gap      | Apa yang membedakan riset Anda dari studi komparasi fintech lain? | **Claim:** Riset ini fokus pada aspek kinerja teknis muat visual, bukan sekadar persepsi kepuasan pengguna.<br>**Evidence:** Studi literatur terdahulu didominasi metode kuesioner TAM kualitatif.<br>**Reasoning:** Data durasi murni (detik) memberikan bukti empiris objektif performa aplikasi. |
| Method   | Kenapa Anda menggunakan Paired Samples T-Test? | **Claim:** Karena pengujian mengevaluasi dua perlakuan pada subjek yang sama.<br>**Evidence:** Sebanyak 40 responden menguji aplikasi GoPay dan DANA sekaligus (data berpasangan).<br>**Reasoning:** Karakteristik data kontinu berpasangan dan normal mewajibkan uji parametrik tersebut. |
| Results  | Hasil statistik Anda menunjukkan p=.000, apa artinya? | **Claim:** Berarti terdapat perbedaan performa durasi muat yang sangat signifikan.<br>**Evidence:** Nilai t-hitung -10.104 jauh melampaui t-tabel dengan taraf signifikansi p < 0.001.<br>**Reasoning:** Hipotesis nol (H₀) resmi ditolak secara telak, keunggulan GoPay bukan faktor kebetulan. |
| Generalization | Apakah temuan ini bisa digeneralisasikan secara luas? | **Claim:** Generalisasi saat ini terbatas pada demografi usia produktif mahasiswa gawai kelas menengah.<br>**Evidence:** Sampel diambil secara purposive dari 40 responden mahasiswa UPB Kebumen.<br>**Reasoning:** Perbedaan spek gawai di kelompok usia lain mungkin memengaruhi volatilitas latensi aplikasi. |

Latihan:
  Latihan 1: [26 Juni 2026] — Waktu berlebih 17 menit, slide hasil statistik terlalu padat teks, perlu reformulasi.
  Latihan 2: [27 Juni 2026] — Waktu pas 14.5 menit, penyampaian bagian metodologi lebih lancar memakai diagram alir.
  Latihan 3: [28 Juni 2026] — Waktu stabil 14.2 menit, artikulasi bagian interpretasi CER sudah mantap dan tajam.
```

---

## Latihan 1 — Slide Outline

Rencanakan presentasi 15 menit untuk riset Anda.

| # | Pesan Utama | Visual yang Digunakan | Waktu |
|---|-------------|----------------------|-------|
| 1 | Judul, Identitas Peneliti, dan Afiliasi Kampus | Slide judul formal dengan logo Universitas Putra Bangsa Kebumen | 1.0 min |
| 2 | Urgensi latensi transaksi QRIS pada ekosistem pembayaran digital mahasiswa | Foto antrean kasir merchant dan grafik pertumbuhan transaksi non-tunai | 2.0 min |
| 3 | Celah riset komparasi empiris performa *Stand-alone App* vs *Super App* | Tabel pemetaan *gap consistency matrix* dari literatur terdahulu | 1.5 min |
| 4 | Kerangka kerja eksperimen kuantitatif parametrik berpasangan (*paired design*) | Diagram alir tahapan pengujian stopwatch dan metode perekam layar | 2.0 min |
| 5 | Laporan data ringkasan nilai statistik deskriptif dari SPSS | Tabel ringkasan data rata-rata waktu muat (Mean GoPay vs DANA) | 2.0 min |
| 6 | Hasil pengujian hipotesis inferensial dan visualisasi error bar | *Bar chart* komparatif durasi beserta nilai t-hitung dan p-value | 2.0 min |
| 7 | Interpretasi efisiensi arsitektur aplikasi (*bloatware background service*) | Diagram konseptual relasi beban inisialisasi memori gawai | 2.0 min |
| 8 | Batasan metodologis riset terkait spek gawai dan demografi lokal | Poin matriks *Internal vs External Validity Threats* | 1.5 min |
| 9 | Penegasan jawaban *Research Question* dan penutupan kontribusi praktis | Slide closing ringkas berisi rekomendasi untuk pengembang fintech | 1.0 min |

**Total waktu estimasi:** 15.0 menit

---

## Latihan 2 — Anticipatory Defense

Prediksi 5 pertanyaan yang mungkin diajukan penguji, lalu siapkan jawaban CER.

| # | Kategori | Pertanyaan | Claim | Evidence | Reasoning |
|---|----------|-----------|-------|----------|-----------|
| 1 | *Problem* | Mengapa Anda mengukur durasi muat QRIS hingga hitungan milidetik, apakah berdampak nyata di lapangan? | Selisih durasi sekecil apa pun sangat memengaruhi retensi kenyamanan psikologis pengguna saat bertransaksi. | Hasil deskriptif menunjukkan nilai rata-rata selisih pangkas waktu muat antar aplikasi mencapai 1.188 detik penuh. | Berdasarkan teori *Time-on-Task*, tunda visual di atas 1 detik terasa menghambat alur aktivitas kognitif manusia di kasir belanja. |
| 2 | *Method* | Bagaimana Anda menjamin kondisi pengujian adil bagi kedua aplikasi gawai tersebut? | Variabel pengganggu eksternal telah dikontrol seketat mungkin di dalam laboratorium pengujian. | Semua tes memakai titik akses Wi-Fi lab yang sama pada jam sepi lalu lintas jaringan yang stabil. | Langkah mitigasi ini berhasil menjaga nilai validitas internal (*internal validity*) dari distorsi fluktuasi sinyal *provider*. |
| 3 | *Results* | Nilai Cohen's d riset Anda bernilai sangat besar (1.58), apa interpretasi praktisnya? | Variasi jenis model arsitektur aplikasi memberikan efek perbedaan performa kecepatan yang masif pada kenyataannya. | Nilai $d = 1.58$ berada jauh di atas ambang batas standar efek besar ($> 0.80$). | Angka ini membuktikan keunggulan performa kecepatan GoPay bersifat mutlak, konsisten, dan bukan merupakan faktor kebetulan. |
| 4 | *Gap* | Mengapa Anda membatasi objek riset pada GoPay dan DANA saja tanpa menyertakan ShopeePay atau OVO? | Pembatasan objek dilakukan demi mengisolasi variabel bebas untuk mempertajam fokus perbandingan model arsitektur. | Fokus riset mengevaluasi model *Stand-alone App* (GoPay) murni melawan model *Super App* (DANA). | Menambahkan entitas pihak ketiga tanpa kesamaan fundamental arsitektur berisiko memperluas bias variabel pengganggu lainnya. |
| 5 | *Generalization* | Apakah temuan hasil riset ini menjamin GoPay akan selalu lebih cepat di semua tipe smartphone? | Tidak, tingkat keunggulan performa kecepatan ini masih terikat pada batas spesifikasi gawai tertentu. | Nilai rentang variasi data tercatat di *Confidence Interval* 95% yaitu pada rentang nilai [-1.42643, -0.95057] detik. | Performa komparasi pada gawai berspesifikasi sangat rendah (*low-end*) dicatat sebagai batas limitasi riset masa depan. |

---

## Latihan 3 — Simulasi Q&A

Minta teman/kolega mengajukan 3 pertanyaan tentang riset Anda. Catat pertanyaan dan evaluasi jawaban Anda.

| # | Pertanyaan | Jawaban Saya | Evaluasi |
|---|-----------|-------------|---------|
| 1 | "Mengapa Anda tidak memasukkan spesifikasi atau RAM gawai responden ke dalam analisis data statistik?" | "Karena riset awal ini difokuskan pada isolasi variabel model perangkat lunak sistem. Namun, keberagaman spesifikasi RAM gawai tersebut sudah kami akui dan masukkan ke dalam bab batasan penelitian." | [✓] Direct [✓] Data-based [✓] Honest |
| 2 | "Bagaimana jika sebaran data durasi waktu muat yang Anda kumpulkan kemarin ternyata tidak berdistribusi normal?" | "Jika asumsi normalitas terbukti dilanggar saat pengujian, maka analisis inferensial akan langsung saya alihkan menggunakan uji non-parametrik Wilcoxon Signed-Rank Test untuk menjaga keabsahan penarikan kesimpulan ilmiah." | [✓] Direct [✓] Data-based [✓] Honest |
| 3 | "Apakah pemangkasan waktu muat sekadar satu detik sebanding dengan hilangnya banyak fitur multi-layanan di GoPay jika dibandingkan dengan DANA?" | "Dari segi kelengkapan fitur layanan, DANA memang unggul. Namun dari sudut pandang efisiensi kegunaan tugas tunggal di kasir belanja, pemangkasan waktu muat sebesar 1.18 detik milik GoPay jauh lebih bernilai praktis bagi pengguna." | [✓] Direct [✓] Data-based [✓] Honest |

**Pertanyaan yang paling sulit dijawab:**
> Mempertahankan argumentasi objektivitas keunggulan durasi kuantitatif (kecepatan performa) ketika dihadapkan pada pertanyaan yang mengungkit preferensi kenyamanan subjektif terhadap kelengkapan fitur aplikasi (*super app multi-service*).

**Apa yang perlu disiapkan lebih baik:**
> Memperkuat penguasaan landasan teoretis mengenai Interaksi Manusia dan Komputer (IMK), khususnya yang berkaitan erat dengan relasi beban kognitif (*cognitive load*) pengguna terhadap ambang batas latensi respons antarmuka sistem digital.

---

## Refleksi

> Dari seluruh proses WS-01 sampai WS-16 — dari paradigma riset hingga presentasi — bagian mana yang paling mengubah cara Anda berpikir tentang riset? Apa satu hal yang akan selalu Anda terapkan di riset berikutnya?

**Insight terbesar:**
> Pergeseran paradigma bahwa riset ilmiah yang baik bukanlah riset yang harus selalu menghasilkan kesempurnaan data tanpa cela, melainkan riset yang dikerjakan dengan tingkat kejujuran metodologis yang tinggi. Menemukan hasil negatif atau keterbatasan data operasional (*boundary conditions*) justru merupakan kontribusi ilmiah yang sangat berharga bagi komunitas akademis, selama peneliti mampu menganalisis alasan di balik kegagalan tersebut secara objektif menggunakan formula argumen CER (Claim-Evidence-Reasoning).

**Yang akan selalu diterapkan:**
> Penerapan matriks konsistensi (*Consistency Matrix*) sejak awal merumuskan ide riset. Memastikan benang merah (*Red Thread*) yang mengaitkan rumusan masalah (RQ), definisi variabel operasional di bab metodologi, hingga bab pelaporan hasil statistik inferensial selalu lurus berkesinambungan tanpa ada lompatan asumsi sepihak.