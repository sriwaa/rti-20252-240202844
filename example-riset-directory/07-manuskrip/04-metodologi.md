# 04-metodologi

Draf bab metodologi penelitian naskah ilmiah — **Tahap 5**.

---

## 3.1 Desain Penelitian dan Unit Analisis

Penelitian ini menggunakan pendekatan kuantitatif dengan metode eksperimen terkontrol (*Controlled Experiment*) menggunakan rancangan eksperimen berpasangan (*Within-Subject / Paired Design*). Desain ini dipilih untuk menguji hubungan kausalitas antara model arsitektur antarmuka aplikasi terhadap tingkat efisiensi performa pengguna secara langsung, di mana seluruh responden menguji kedua kondisi artefak sistem secara bergantian.

Unit analisis dalam penelitian ini adalah mahasiswa aktif Universitas Putra Bangsa (UPB) Kebumen yang dikategorikan sebagai pengguna aktif dompet digital. Pengujian dilakukan langsung di lingkungan kampus untuk mensimulasikan kondisi penggunaan riil dalam aktivitas finansial harian mahasiswa. Dalam alur eksperimen ini, aplikasi DANA diposisikan sebagai *baseline* (kondisi dasar) yang mewakili karakteristik arsitektur *Super App* dengan kepadatan fitur yang tinggi pada halaman utama, sedangkan aplikasi GoPay bertindak sebagai intervensi yang menawarkan pendekatan desain *Stand-alone* yang minimalis untuk menyelesaikan tugas transaksional yang sama.

---

## 3.2 Variabel, Metrik, dan Instrumen Penelitian

Penelitian ini mengonfigurasi hubungan antarvariabel secara ketat untuk menjamin validitas hasil pengukuran:
*   **Variabel Independen (IV):** Model Arsitektur Antarmuka Aplikasi, yang terdiri dari dua kategori, yaitu model *Super App* (DANA) dan model *Stand-alone* (GoPay).
*   **Variabel Dependen (DV):** Efisiensi Interaksi Pengguna, yang dioperasinalisasikan secara terukur melalui kecepatan waktu penyelesaian tugas.
*   **Variabel Kontrol:** Spesifikasi perangkat keras, versi sistem operasi, stabilitas koneksi internet, dan lokasi fisik pengujian untuk meminimalkan bias faktor teknis di luar desain antarmuka.

Metrik utama yang digunakan untuk mengukur Variabel Dependen adalah *Time-on-Task* (ToT) dengan skala rasio dan satuan pengukuran detik (s). Pemilihan metrik ini merujuk pada standar ISO 9241-11, di mana durasi waktu penyelesaian tugas merupakan indikator paling objektif dan akurat untuk merepresentasikan efisiensi kerja pengguna.

Instrumen pengumpulan data yang digunakan meliputi satu unit perangkat komputer genggam kontrol, stopwatch digital presisi, serta lembar observasi (*observation sheet*). Data primer diperoleh secara langsung dari hasil pengukuran interaksi fisik 40 responden mahasiswa UPB Kebumen. Batasan awal perhitungan waktu ($t = 0$) dimulai tepat saat jari responden menyentuh ikon aplikasi pada layar, dan perhitungan waktu dihentikan ($t = \text{akhir}$) tepat saat jendela bidik (*viewfinder*) kamera pemindaian QRIS aktif sepenuhnya di layar smartphone dan siap digunakan untuk memindai.

---

## 3.3 Skenario dan Prosedur Eksperimen

Skenario eksperimen dirancang secara tunggal dan spesifik untuk membandingkan performa navigasi kedua aplikasi melalui perintah: *"Lakukan akses fitur pindai QRIS hingga kamera aktif sepenuhnya"*. Prosedur pelaksanaan eksperimen dijalankan secara runtut melalui tahapan berikut:

1.  **Fase Persiapan Teknis:** Peneliti menyiapkan satu unit smartphone Samsung Galaxy A55 dalam kondisi kapasitas baterai di atas 50%. Sebelum pengujian dilakukan untuk setiap responden, peneliti menerapkan *Cold Start Protocol*, yaitu melakukan pengosongan memori cache dan penghentian paksa (*Force Stop*) pada aplikasi GoPay dan DANA untuk memastikan pemrosesan arsitektur dimulai dari awal secara adil.
2.  **Fase Pemberian Instruksi:** Responden diberikan penjelasan mengenai tugas transaksional yang harus diselesaikan tanpa disertai petunjuk arah navigasi atau letak menu, guna mengukur kecepatan murni responden dalam memindai antarmuka.
3.  **Fase Eksekusi dan Pengukuran:** Responden menyentuh ikon aplikasi berdasarkan aba-aba mulai dari peneliti, bersamaan dengan diaktifkannya stopwatch digital. Stopwatch dihentikan tepat ketika fungsi kamera QRIS aktif.
4.  **Fase Pencatatan Data:** Nilai durasi waktu dalam satuan detik direkam secara langsung ke dalam lembar observasi untuk dipindahkan ke dalam basis data spreadsheet.

Untuk memitigasi ancaman *Testing Effect* atau efek belajar (*learning effect*) yang dapat merusak validitas internal, penelitian ini menerapkan teknik *Counterbalancing*. Dari total 40 responden, separuh kelompok (20 responden) diatur untuk menguji aplikasi GoPay terlebih dahulu baru kemudian aplikasi DANA, sedangkan separuh kelompok sisanya (20 responden) menguji aplikasi DANA terlebih dahulu baru kemudian aplikasi GoPay.

---

## 3.4 Teknik Analisis Data

Data durasi waktu (*Time-on-Task*) kuantitatif yang telah dikumpulkan dari 40 responden berpasangan akan dianalisis menggunakan statistik inferensial parametrik melalui perangkat lunak IBM SPSS Statistics. Alur analisis data dilakukan melalui tahapan komputasi sebagai berikut:

1.  **Uji Asumsi Normalitas:** Melakukan pengujian distribusi data menggunakan metode Shapiro-Wilk atau Kolmogorov-Smirnov. Asumsi normalitas terpenuhi apabila nilai signifikansi ($p\text{-value}$) dari sebaran data durasi kedua aplikasi berada di atas nilai $\alpha = 0,05$.
2.  **Analisis Deskriptif:** Menghitung nilai rata-rata (*Mean*) dan standar deviasi durasi waktu untuk masing-masing kelompok aplikasi guna melihat visualisasi perbedaan awal performa kecepatan interaksi.
3.  **Uji Hipotesis Komparatif:** Melakukan komputasi statistik **Paired Samples T-Test** (Uji T Berpasangan) pada tingkat kepercayaan 95% ($\alpha = 0,05$). Pemilihan teknik ini didasarkan pada karakteristik data berpasangan dari satu sampel responden yang sama (*Within-Subject*). Kriteria pengambilan keputusan statistik diatur sebagai berikut:
    *   Jika nilai *Sig. (2-tailed)* $< 0,05$, maka Hipotesis Nol ($H_0$) ditolak dan Hipotesis Alternatif ($H_a$) diterima, yang berarti terdapat perbedaan efisiensi waktu transaksi yang signifikan secara statistik antara model *Stand-alone* (GoPay) dan *Super App* (DANA).
    *   Jika nilai *Sig. (2-tailed)* $\ge 0,05$, maka Hipotesis Nol ($H_0$) diterima, yang berarti perbedaan waktu yang terjadi bukan dipengaruhi oleh desain arsitektur melainkan faktor kebetulan.