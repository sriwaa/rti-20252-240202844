# Perbandingan Efisiensi Model Stand-alone (GoPay) dan Super App (DANA) Menggunakan Metrik Time-on-Task pada Mahasiswa UPB

## RINGKASAN

Penelitian ini dilatarbelakangi oleh fenomena transisi model desain aplikasi dompet digital dari model Super App yang padat fitur menuju model Stand-alone App yang lebih fokus pada fungsi tunggal[cite: 2]. Urgensi penelitian ini terletak pada adanya risiko *information overload* pada model Super App yang dapat menghambat efisiensi interaksi pengguna, namun evaluasi saat ini masih didominasi oleh persepsi subjektif melalui kuesioner[cite: 2]. Tujuan utama penelitian adalah untuk memberikan bukti empiris mengenai perbedaan performa kecepatan transaksi antara aplikasi GoPay (model Stand-alone) dan DANA (model Super App)[cite: 2].

Metode yang digunakan adalah pengujian kegunaan (*Usability Testing*) melalui desain eksperimen komparatif terhadap 40 responden mahasiswa Universitas Putra Bangsa (UPB)[cite: 2]. Pengukuran dilakukan secara objektif menggunakan metrik *Time-on-Task* (ToT) untuk menghitung durasi waktu penyelesaian tugas transaksi QRIS dalam satuan detik[cite: 2]. Guna menjaga validitas internal, pengujian dilakukan menggunakan satu perangkat terkontrol (Samsung A55) dan menerapkan teknik *counterbalancing* untuk mengeliminasi efek belajar pada responden[cite: 2].

Luaran yang ditargetkan dari penelitian ini adalah dokumen laporan analisis performa yang memvalidasi efektivitas model arsitektur aplikasi terhadap efisiensi interaksi pengguna[cite: 2]. Hasil penelitian diharapkan dapat menjadi rujukan ilmiah bagi pengembang aplikasi finansial dalam menentukan strategi desain antarmuka yang optimal bagi produktivitas pengguna[cite: 2].

**Kata Kunci:** *User Experience*; *Time-on-Task*; *Super App*; *Stand-alone App*; Dompet Digital[cite: 2].

---

## I. PENDAHULUAN

Perkembangan teknologi finansial di Indonesia telah membawa perubahan besar pada cara masyarakat melakukan transaksi harian, khususnya melalui penggunaan dompet digital yang semakin masif[cite: 2]. Transformasi ini melahirkan dua model arsitektur aplikasi yang berbeda: model Super App yang mengintegrasikan berbagai layanan dalam satu pintu, dan model Stand-alone App yang fokus pada efisiensi fungsi tunggal[cite: 2]. Di lingkungan akademis seperti Universitas Putra Bangsa (UPB) Kebumen, mahasiswa sebagai kelompok pengguna *tech-savvy* sangat bergantung pada kecepatan dan kemudahan akses fitur finansial untuk mendukung mobilitas mereka[cite: 2].

Namun, peningkatan jumlah fitur pada platform digital sering kali berbanding lurus dengan kompleksitas antarmuka, yang berpotensi menimbulkan beban kognitif bagi pengguna[cite: 2]. Fenomena ini memicu perdebatan mengenai model arsitektur mana yang benar-benar memberikan efisiensi nyata dalam penggunaan harian[cite: 2]. Penelitian ini disusun untuk menjawab permasalahan tersebut melalui pendekatan eksperimen objektif, memetakan posisi riset di antara studi terdahulu, serta memberikan gambaran jalur pengembangan penelitian yang sistematis guna menghasilkan bukti empiris yang valid di lingkungan Universitas Putra Bangsa Kebumen[cite: 2].

### 1.1. Latar Belakang dan Rumusan Masalah
Perkembangan industri finansial digital di Indonesia saat ini didominasi oleh strategi pengembangan aplikasi model Super App, di mana satu platform menyediakan berbagai layanan kompleks mulai dari pembayaran, transportasi, hingga investasi dalam satu antarmuka[cite: 2]. Namun, seiring bertambahnya fitur, kompleksitas elemen visual turut meningkat secara signifikan[cite: 2]. Gejala yang terukur di lapangan menunjukkan bahwa banyak pengguna sering terdiam sejenak (*scanning delay*) dan membutuhkan waktu yang lebih lama hanya untuk menemukan fitur utama pada aplikasi yang padat fitur[cite: 2]. Akar masalah dari fenomena ini adalah adanya *information overload* atau beban informasi akibat kepadatan elemen visual dan arsitektur informasi yang kompleks pada halaman utama aplikasi[cite: 2].

Dampak dari kompleksitas ini adalah terhambatnya efisiensi interaksi pengguna, terutama pada aktivitas finansial yang membutuhkan respon cepat seperti transaksi QRIS[cite: 2]. Masalah ini menjadi sangat relevan dalam konteks mahasiswa Universitas Putra Bangsa (UPB) Kebumen yang merupakan generasi *tech-savvy* dengan mobilitas tinggi dan ekspektasi transaksi yang bersifat instan[cite: 2]. Munculnya model aplikasi Stand-alone seperti GoPay yang fokus pada fungsi inti menawarkan potensi efisiensi yang lebih tinggi dibandingkan model Super App konvensional seperti DANA, namun perbedaan performa teknis keduanya belum teruji secara empiris di lingkungan kampus[cite: 2].

> **Problem Statement:**
> Mahasiswa Universitas Putra Bangsa Kebumen selaku pengguna dompet digital (**Siapa**) mengalami penurunan efisiensi waktu transaksi akibat beban kognitif dari kepadatan elemen visual pada antarmuka Super App (**Apa**), yang berdampak pada terhambatnya produktivitas dalam melakukan aktivitas finansial harian yang membutuhkan respon cepat (**Dampak**)[cite: 2].

### 1.2. Pendekatan Pemecahan Masalah
Penelitian ini bertujuan untuk membuktikan secara empiris perbedaan tingkat efisiensi interaksi pengguna antara model arsitektur aplikasi Stand-alone dan Super App[cite: 2]. Masalah ini akan dijawab melalui *Research Question* (RQ) utama: *"Apakah terdapat perbedaan signifikan pada rata-rata durasi waktu transaksi (Time-on-Task) antara aplikasi GoPay (model stand-alone) dan aplikasi DANA (model super app) pada mahasiswa Universitas Putra Bangsa?"*[cite: 2]. Sejalan dengan RQ tersebut, hipotesis awal yang diajukan adalah aplikasi GoPay memiliki durasi waktu transaksi yang lebih cepat secara signifikan dibandingkan aplikasi DANA karena struktur antarmukanya yang lebih sederhana[cite: 2].

Pendekatan solusi yang diusulkan adalah melakukan pengujian kegunaan (*Usability Testing*) melalui eksperimen terkontrol[cite: 2]. Pemilihan intervensi berupa aplikasi GoPay (versi stand-alone) didasarkan pada alasan logis bahwa model ini memisahkan fitur finansial dari layanan hiburan atau transportasi, sehingga diharapkan dapat mengurangi beban kognitif pengguna saat melakukan transaksi spesifik[cite: 2]. Sebagai pembanding atau *baseline*, penelitian ini menggunakan aplikasi DANA yang merepresentasikan model Super App konvensional dengan tingkat kepadatan fitur yang tinggi pada halaman utama[cite: 2].

### 1.3. State of the Art dan Kebaruan
Kajian literatur saat ini mengenai *user experience* (UX) pada dompet digital di Indonesia umumnya berfokus pada pengukuran tingkat kepuasan dan kegunaan melalui data persepsi subjektif responden[cite: 2]. Pola studi terdahulu sering menggunakan kuesioner standar seperti *System Usability Scale* (SUS) atau *User Experience Questionnaire* (UEQ) untuk mengevaluasi aplikasi seperti DANA, OVO, maupun GoPay dalam ekosistem Super App[cite: 2]. Namun, terdapat keterbatasan yang berulang dalam studi-studi tersebut, yaitu ketergantungan pada opini pengguna yang rentan terhadap bias ingatan dan tidak mencerminkan efisiensi performa teknis yang sebenarnya di lapangan[cite: 2].

Gap penelitian ini muncul sebagai selisih eksplisit antara kondisi ideal di mana efisiensi desain seharusnya dibuktikan melalui performa interaksi yang presisi dan kondisi aktual penelitian saat ini yang masih didominasi oleh data kualitatif/subjektif[cite: 2]. Belum ditemukan penelitian yang secara khusus mengadu performa model Stand-alone (GoPay) melawan model Super App (DANA) sebagai baseline menggunakan metrik durasi waktu nyata[cite: 2]. Oleh karena itu, posisi penelitian ini adalah sebagai studi komparatif teknis yang menawarkan kebaruan (*novelty*) berupa transisi metodologi dari pengukuran persepsi subjektif menuju pengukuran performa objektif melalui metrik *Time-on-Task*[cite: 2]. Hal ini penting untuk memberikan bukti empiris yang lebih akurat mengenai dampak arsitektur informasi terhadap kecepatan transaksi pengguna[cite: 2].

### 1.4. Peta Jalan Penelitian
Peta jalan penelitian ini disusun secara sistematis untuk menggambarkan perkembangan riset dari tahap inisiasi hingga tahap diseminasi hasil sebagai berikut[cite: 2]:

1. **Tahap Pra-Penelitian (Telah Dicapai)**
   Berfokus pada identifikasi masalah terkait beban kognitif pada Super App dan pencarian *method gap* melalui studi literatur[cite: 2]. Hasil dari tahap ini adalah penetapan *Research Question* (RQ) yang tajam serta pemilihan metrik *Time-on-Task* sebagai standar pengukuran objektif untuk menggantikan metode kuesioner subjektif yang sudah ada sebelumnya[cite: 2].
2. **Tahap Eksperimen dan Koleksi Data (Usulan Saat Ini)**
   Pada tahapan ini, fokus utama adalah pengujian artefak sistem (GoPay vs DANA) melalui eksperimen terkontrol terhadap 40 responden mahasiswa di lingkungan kampus UPB Kebumen[cite: 2]. Tahap ini melibatkan kesiapan setup perangkat Samsung A55, penerapan teknik *counterbalancing*, serta pencatatan durasi transaksi secara presisi untuk memastikan data yang dikumpulkan memiliki validitas internal yang tinggi[cite: 2].
3. **Tahap Analisis dan Rekomendasi (Tahap Lanjutan)**
   Tahap akhir ini direncanakan untuk mengolah data mentah (detik) menggunakan teknik analisis statistik *Independent Samples T-test* guna membuktikan hipotesis kausalitas[cite: 2]. Hasil analisis ini tidak hanya akan memberikan kesimpulan ilmiah mengenai perbedaan efisiensi antar-model aplikasi, tetapi juga akan dikembangkan menjadi rekomendasi praktis bagi pengembang aplikasi finansial dalam mengoptimalkan arsitektur informasi untuk meningkatkan produktivitas pengguna[cite: 2].

---

## II. METODE

Metodologi dalam penelitian ini disusun untuk memberikan pembuktian empiris yang objektif mengenai pengaruh arsitektur aplikasi terhadap efisiensi interaksi pengguna[cite: 2]. Fokus utama metode ini adalah menjamin validitas internal melalui eksperimen yang adil (*fair*), di mana setiap variabel pengganggu dikontrol secara ketat agar hasil yang didapatkan murni merupakan representasi dari perbedaan variabel independen yang diuji[cite: 2].

Guna menjawab *Research Question* secara akurat, penelitian ini mengalihkan parameter pengukuran dari persepsi subjektif menuju data performa nyata[cite: 2]. Penggunaan metrik *Time-on-Task* dipilih karena secara logis merupakan indikator paling jujur untuk mengukur *outcome* efisiensi; semakin singkat waktu yang dibutuhkan untuk menyelesaikan tugas transaksi, maka semakin tinggi tingkat efisiensi antarmuka tersebut[cite: 2]. Instrumen berupa perangkat kendali tunggal dan pencatatan waktu presisi berfungsi sebagai jalur nyata untuk mendapatkan data primer yang bersifat kuantitatif dan faktual[cite: 2].

Rangkaian prosedur pengujian, mulai dari penentuan unit analisis pada mahasiswa Universitas Putra Bangsa hingga penerapan teknik mitigasi bias, dirancang untuk memastikan bahwa kesimpulan yang dihasilkan memiliki derajat keandalan yang tinggi dan dapat dipertanggungjawabkan secara ilmiah dalam domain *Human-Computer Interaction*[cite: 2].

### 2.1. Desain Penelitian dan Unit Analisis
Penelitian ini merupakan jenis penelitian kuantitatif dengan tipe desain eksperimen komparatif (*Controlled Experiment*)[cite: 2]. Desain ini dipilih untuk menguji hubungan kausalitas antara model desain aplikasi terhadap performa pengguna secara langsung[cite: 2]. Penelitian ini dirancang untuk menjawab *research question* final: *"Apakah terdapat perbedaan signifikan pada rata-rata durasi waktu transaksi (Time-on-Task) antara aplikasi GoPay (model stand-alone) dan aplikasi DANA (model super app) pada mahasiswa Universitas Putra Bangsa?"*[cite: 2]. Sejalan dengan pertanyaan tersebut, hipotesis penelitian menyatakan bahwa aplikasi dengan model *stand-alone* (GoPay) memiliki durasi waktu transaksi yang secara signifikan lebih cepat dibandingkan aplikasi model *super app* (DANA)[cite: 2].

Unit analisis dalam penelitian ini adalah mahasiswa aktif Universitas Putra Bangsa (UPB) Kebumen yang dikategorikan sebagai pengguna aktif dompet digital[cite: 2]. Konteks penelitian dilakukan di lingkungan kampus untuk mensimulasikan kondisi penggunaan nyata saat mahasiswa melakukan transaksi harian[cite: 2]. *Outcome* yang dituju adalah validasi empiris mengenai efektivitas penyederhanaan arsitektur informasi terhadap efisiensi interaksi[cite: 2]. Dalam pengujian ini, aplikasi DANA diposisikan sebagai *baseline* (kondisi dasar) yang mewakili kompleksitas fitur yang tinggi, sementara aplikasi GoPay bertindak sebagai intervensi yang menawarkan pendekatan desain minimalis untuk menyelesaikan tugas yang sama[cite: 2].

### 2.2. Variabel, Metric, Instrumen, dan Data
Penelitian ini menggunakan satu **Variabel Independen (IV) Utama**, yaitu *Model Arsitektur Antarmuka Aplikasi* yang terdiri dari dua kategori: model Super App (DANA) dan model Stand-alone (GoPay)[cite: 2]. Variabel ini diuji pengaruhnya terhadap satu **Variabel Dependen (DV)**, yaitu *Efisiensi Interaksi Pengguna*[cite: 2]. Untuk memastikan hasil yang objektif, digunakan pula **Variabel Kontrol** berupa spesifikasi perangkat keras (satu unit smartphone Samsung A55) dan stabilitas koneksi internet yang seragam untuk meminimalkan bias performa teknis di luar desain antarmuka[cite: 2].

**Metric Utama** yang digunakan adalah *Time-on-Task* (ToT) dengan skala rasio dan satuan pengukuran detik (s)[cite: 2]. Justifikasi pemilihan metric ini didasarkan pada standar ISO 9241-11, di mana durasi waktu merupakan indikator paling akurat dan jujur untuk mengukur efisiensi kerja pengguna; semakin rendah nilai ToT, maka semakin tinggi tingkat efisiensi interaksi yang dihasilkan[cite: 2].

**Instrumen** atau cara ukur yang digunakan adalah stopwatch digital presisi dan lembar pencatatan data (*observation sheet*)[cite: 2]. Data diperoleh langsung dari sumber data primer, yaitu 40 responden mahasiswa Universitas Putra Bangsa melalui pengujian langsung[cite: 2]. Proses pengukuran dimulai saat pengguna menyentuh ikon aplikasi dan berakhir saat layar pemindaian (QRIS) aktif sepenuhnya dan siap digunakan[cite: 2]. Pendekatan ini menjamin jalur nyata bagi data untuk membuktikan secara empiris perbedaan performa antara kedua model arsitektur yang diuji[cite: 2].

### 2.3. Skenario dan Prosedur Pengujian
Skenario pengujian dirancang untuk membandingkan performa aplikasi DANA (*baseline*) dan GoPay (*intervensi*) melalui tugas tunggal yang spesifik, yaitu: **"Melakukan akses fitur pindai QRIS hingga kamera aktif"**[cite: 2]. Langkah pengujian dilakukan secara berurutan sebagai berikut[cite: 2]:

1. **Persiapan:** Peneliti menyiapkan perangkat Samsung A55 dalam kondisi baterai di atas 50% dan memastikan seluruh aplikasi latar belakang telah ditutup (*Force Stop*) untuk menjamin kondisi *Cold Start* yang adil bagi kedua aplikasi[cite: 2].
2. **Instruksi:** Responden diberikan penjelasan mengenai tugas tanpa diberikan arahan navigasi, guna melihat kecepatan murni responden dalam menemukan menu pada masing-masing arsitektur antarmuka[cite: 2].
3. **Eksekusi:** Pengukuran dimulai saat peneliti memberi aba-aba dan responden menyentuh ikon aplikasi[cite: 2]. Stopwatch dihentikan tepat saat *viewfinder* kamera QRIS muncul di layar[cite: 2].
4. **Pencatatan:** Hasil durasi dalam detik dicatat langsung ke dalam tabel observasi[cite: 2].

Untuk menjaga aspek *fairness* dan validitas, penelitian ini menerapkan teknik **Counterbalancing**: separuh jumlah responden (20 orang) menguji GoPay terlebih dahulu, sementara separuh sisanya menguji DANA terlebih dahulu untuk mengeliminasi efek belajar (*learning effect*)[cite: 2]. Faktor yang dijaga tetap (*controlled factors*) meliputi jenis perangkat, versi sistem operasi, koneksi jaringan yang sama, dan titik lokasi pengujian yang seragam di area kampus UPB[cite: 2]. Logika pengamatan ini memastikan bahwa setiap perbedaan waktu yang muncul murni disebabkan oleh perbedaan arsitektur informasi aplikasi, sehingga hasil penelitian dapat direplikasi secara konsisten dalam kondisi yang serupa[cite: 2].

### 2.4. Artifact, Setup, atau Kesiapan Implementasi
Penelitian ini menggunakan dua artefak sistem utama sebagai alat uji, yaitu aplikasi GoPay (versi terbaru yang telah mengadopsi model *stand-alone*) dan aplikasi DANA (versi terbaru yang tetap konsisten dengan model *super app*)[cite: 2]. Kedua artefak ini tidak diposisikan sebagai produk konsumsi, melainkan sebagai objek eksperimen untuk menguji dampak arsitektur informasi terhadap efisiensi interaksi[cite: 2]. Komponen pendukung dan setup operasional yang digunakan meliputi[cite: 2]:

1. **Hardware Kendali (Samsung Galaxy A55):** Berfungsi sebagai lingkungan uji tunggal yang seragam[cite: 2]. Penggunaan satu tipe perangkat bertujuan untuk mengunci variabel spesifikasi prosesor dan RAM, sehingga *loading time* aplikasi tidak dipengaruhi oleh perbedaan performa perangkat keras[cite: 2].
2. **Sistem Operasi dan Koneksi:** Perangkat diatur pada versi Android yang sama dengan koneksi data seluler 4G/5G yang stabil di lingkungan kampus UPB[cite: 2]. Hal ini berfungsi untuk memastikan bahwa variabel kontrol lingkungan tetap konstan bagi seluruh responden[cite: 2].
3. **Instrumen Pengukuran (Stopwatch Digital):** Berfungsi sebagai alat pencatat data objektif untuk mengukur durasi *Time-on-Task*[cite: 2]. Instrumen ini merupakan jalur penghubung antara interaksi fisik responden pada artefak dengan data numerik yang akan dianalisis[cite: 2].
4. **Setup Operasional (Cold Start Protocol):** Sebelum pengujian setiap responden, sistem akan dilakukan *clear cache* dan *force stop*[cite: 2]. Setup ini krusial untuk memastikan bahwa data yang diperoleh adalah performa murni aplikasi saat memproses arsitektur informasinya dari awal, bukan karena data yang sudah tersimpan di memori jangka pendek perangkat[cite: 2].

Seluruh setup ini dikonfigurasi sedemikian rupa agar hasil pengukuran durasi waktu (Variabel Dependen) benar-benar merepresentasikan kualitas desain antarmuka dari kedua model arsitektur (Variabel Independen) yang diuji, sehingga eksperimen ini memiliki tingkat validitas dan reliabilitas yang dapat dipertanggungjawabkan[cite: 2].

### 2.5. Teknik Analisis, Asumsi, dan Validitas
Data durasi waktu (*Time-on-Task*) yang telah dikumpulkan akan dianalisis menggunakan pendekatan statistik inferensial untuk membandingkan performa antara Kondisi A (DANA) dan Kondisi B (GoPay)[cite: 2]. Tahapan analisis dimulai dengan uji normalitas (seperti Kolmogorov-Smirnov) untuk menentukan distribusi data[cite: 2]. Jika data berdistribusi normal, maka teknik analisis yang digunakan adalah *Independent Samples T-test* dengan tingkat kepercayaan 95% ($\alpha=0.05$)[cite: 2]. Hasil perbandingan akan dibaca secara eksplisit melalui nilai rata-rata (*mean*) dan nilai signifikansi (*p-value*); jika $p < 0.05$, maka perbedaan efisiensi antara kedua model arsitektur dinyatakan signifikan secara statistik dan bukan merupakan faktor kebetulan[cite: 2].

Penelitian ini berjalan dengan asumsi bahwa seluruh responden memiliki tingkat literasi digital yang setara sebagai mahasiswa dan tidak mengalami gangguan penglihatan yang dapat menghambat interaksi dengan antarmuka aplikasi[cite: 2]. Adapun beberapa *constraints* atau batasan yang diakui adalah variasi kecepatan respon motorik setiap individu dan fluktuasi latensi jaringan yang mungkin terjadi meski sudah diminimalisir[cite: 2].

Untuk menjaga validitas, penelitian ini mengidentifikasi ancaman utama berupa *Testing Effect* atau efek belajar, yang dimitigasi melalui teknik *counterbalancing*[cite: 2]. Selain itu, validitas eksternal dijaga dengan melakukan pengujian pada lingkungan alami (kampus) agar hasil penelitian tetap relevan dengan konteks penggunaan nyata[cite: 2]. Dengan mengikuti alur analisis ini, transisi dari data mentah (detik) menuju kesimpulan mengenai efisiensi arsitektur dapat dilakukan secara logis, objektif, dan dapat dipertanggungjawabkan tanpa adanya lompatan asumsi[cite: 2].

---

## III. HASIL YANG DIHARAPKAN DAN LUARAN

Hasil utama yang diharapkan dari penelitian ini adalah diperolehnya data empiris yang valid mengenai perbandingan efisiensi waktu antara model arsitektur Stand-alone dan Super App[cite: 2]. Berdasarkan hipotesis dan metrik *Time-on-Task* yang digunakan, hasil terukur yang dijanjikan adalah sebuah kesimpulan statistik yang menunjukkan apakah penyederhanaan antarmuka pada aplikasi GoPay memberikan reduksi durasi waktu yang signifikan dibandingkan aplikasi DANA[cite: 2]. Hasil ini akan dibuktikan melalui perolehan nilai rata-rata (*mean*) durasi transaksi yang lebih rendah pada kelompok intervensi[cite: 2].

Secara praktis, hasil penelitian ini diharapkan dapat memberikan implikasi berupa rekomendasi desain bagi pengembang aplikasi finansial dalam mengelola kompleksitas fitur agar tidak mengorbankan kecepatan interaksi pengguna[cite: 2]. Luaran (*deliverables*) yang dijanjikan dari penelitian ini meliputi[cite: 2]:

1. **Dataset Primer:** Kumpulan data durasi waktu transaksi dari 40 responden mahasiswa UPB Kebumen yang telah diolah[cite: 2].
2. **Laporan Analisis Statistik:** Dokumen teknis hasil uji *Independent Samples T-test* yang membuktikan pengaruh arsitektur informasi terhadap efisiensi[cite: 2].
3. **Artikel Ilmiah:** Draft publikasi yang merangkum temuan penelitian mengenai komparasi UX pada dompet digital untuk kontribusi pengetahuan di bidang *Human-Computer Interaction*[cite: 2].

Target ini dinilai sangat realistis karena seluruh instrumen pengukuran telah siap, subjek penelitian (mahasiswa UPB) mudah dijangkau, dan metode analisis yang digunakan sudah sesuai dengan standar kaidah penelitian kuantitatif[cite: 2].

---

## IV. JADWAL PENELITIAN

| No | Nama Kegiatan | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 |
|---|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| 1 | Identifikasi masalah dan topik | ✓ | | | | | | | |
| 2 | Literatur dan gap | | ✓ | | | | | | |
| 3 | RQ dan desain metode | | | ✓ | | | | | |
| 4 | Implementasi atau instrumen | | | | ✓ | | | | |
| 5 | Pengujian atau eksperimen | | | | | ✓ | ✓ | | |
| 6 | Analisis dan penulisan | | | | | | | ✓ | |
| 7 | Revisi final | | | | | | | | ✓ |

### Narasi Peta Jalan dan Kesiapan Operasional
Jadwal ini disusun selama 8 minggu dengan pembagian fase yang saling berkesinambungan untuk menjamin validitas data[cite: 2]:

* **Fase Inisiasi (Minggu 1-3):** Berfokus pada penguatan landasan teori mengenai beban kognitif dan arsitektur informasi[cite: 2]. Luaran dari fase ini adalah dokumen metodologi yang presisi untuk menjawab *research question* melalui metrik *Time-on-Task*[cite: 2].
* **Fase Persiapan Instrumen (Minggu 4):** Merupakan *checkpoint* evaluasi internal untuk memastikan seluruh artefak (GoPay dan DANA) serta perangkat uji (Samsung A55) dalam kondisi siap pakai sesuai protokol *Cold Start*[cite: 2].
* **Fase Eksperimen (Minggu 5-6):** Tahap krusial pengambilan data primer dari 40 responden mahasiswa di lingkungan Universitas Putra Bangsa[cite: 2]. Penggunaan durasi dua minggu bertujuan untuk memastikan proses *counterbalancing* berjalan tertib tanpa terburu-buru[cite: 2].
* **Fase Finalisasi (Minggu 7-8):** Data mentah dikonversi menjadi informasi ilmiah melalui uji statistik *T-test*[cite: 2]. Luaran akhir adalah draf proposal final yang telah divalidasi dan siap untuk dipresentasikan atau dipublikasikan sebagai artikel ilmiah[cite: 2].

---

## V. DAFTAR PUSTAKA

* Pratama, A., & Sari, D. P. (2023). Analisis Kegunaan Aplikasi GoPay Berdasarkan Metode System Usability Scale (SUS). *Jurnal Sistem Informasi dan Teknologi*, 5(1), 12-18[cite: 2].
* Ramadhan, R., dkk. (2022). Analisis User Experience pada Pengguna Aplikasi Dompet Digital Menggunakan Teori Jacob Nielsen. *Informasi dan Teknologi: Jurnal Ilmiah*, 4(2), 45-52[cite: 2].
* Naufal, M. (2024). Evaluasi User Experience Pada Aplikasi E-Wallet DANA Menggunakan Metode User Experience Questionnaire (UEQ). *Jurnal Teknologi Informasi*, 7(3), 110-120. (Sumber Pembanding Efisiensi Subjektif)[cite: 2].
* Sa'adah, P., dkk. (2024). Analisis Kegunaan Aplikasi GoPay Menggunakan Metode System Usability Scale. *Jurnal Riset Sistem Informasi*, 2(1), 34-42. (Sumber Baseline Skor SUS GoPay)[cite: 2].
* Rosyidah, N. I. (2026). Heuristic Evaluation pada Perbandingan Arsitektur Informasi GoPay dan DANA. *Jurnal Inovasi Teknologi*, 10(1), 55-64. (Sumber Gap: Evaluasi Ahli vs Real User)[cite: 2].
* Achyani, Y. E. (2024). Usability Testing pada Aplikasi Dompet Digital Menggunakan Model Nielsen. *Jurnal Teknik Informatika*, 8(2), 101-109. (Sumber Baseline Komponen Efisiensi)[cite: 2].
* Permana, A. (2025). Studi Komparatif User Experience GoPay, DANA, dan OVO Menggunakan UEQ. *Jurnal Komputasi dan Sistem Informasi*, 12(1), 20-29. (Sumber Gap: Kebutuhan Pengukuran Objektif)[cite: 2].
* Warto, Nurmawati, L., & Dewi, S. C. (2023). Pengolahan Dan Interpretasi Data Penelitian Dengan SPSS Bagi Mahasiswa Akhir. *KALANDRA: Jurnal Pengabdian Kepada Masyarakat*, 2(6), 292-297[cite: 2].
* Mahendra, dkk. (2026). Analisis Statistik Perbandingan Rata-rata Menggunakan Independent Sample T-test pada Aplikasi SPSS Versi 26. *Jurnal Ilmiah M-Progress*, 16(1), 45-58[cite: 2].
* Setiawan, A., & Herlambang, A. D. (2023). Analisis Perbandingan Beban Kognitif Pengguna pada Arsitektur Super App dan Single-purpose App. *Jurnal Pengembangan Teknologi Informasi dan Ilmu Komputer*, 7(4), 1820-1829[cite: 2].
* Ramadhani, F., dkk. (2025). Dampak Kompleksitas Fitur terhadap Kecepatan Transaksi pada Pengguna Generasi Z: Studi Komparatif DANA dan GoPay. *Jurnal Sistem Informasi Bisnis*, 15(2), 210-218[cite: 2].