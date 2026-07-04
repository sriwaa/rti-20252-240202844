# 03-tinjauan-pustaka

Draf bab tinjauan pustaka naskah ilmiah — **Tahap 5**.

---

## 2.1 Interaksi Manusia dan Komputer serta Usability

Interaksi Manusia dan Komputer (Human-Computer Interaction/HCI) merupakan bidang studi yang fokus pada desain, evaluasi, dan implementasi antarmuka pengguna sistem komputasi agar mudah digunakan oleh manusia. Salah satu atribut penentu kualitas dari sebuah antarmuka dalam disiplin ilmu HCI adalah *usability* (kegunaan). Berdasarkan standar ISO 9241-11, *usability* dinilai dari seberapa efektif, efisien, dan memuaskan suatu sistem saat digunakan oleh kelompok pengguna tertentu untuk mencapai tujuan spesifik mereka.

Dalam konteks aplikasi finansial digital, aspek *efficiency* (efisiensi) menjadi komponen yang sangat krusial. Efisiensi dalam HCI mengukur seberapa cepat dan seberapa sedikit usaha kognitif (daya pikir) yang dihabiskan oleh pengguna dalam menyelesaikan suatu tugas operasional. Antarmuka yang memiliki tingkat efisiensi tinggi akan meminimalkan hambatan visual, memotong alur navigasi yang berbelit-belit, dan mempercepat proses interaksi harian pengguna.

---

## 2.2 Efisiensi Interaksi dan Metrik Time-on-Task (ToT)

Untuk mengukur tingkat efisiensi interaksi sebuah antarmuka aplikasi secara objektif dan kuantitatif, penelitian dalam domain HCI kerap mengandalkan metrik performa berbasis waktu, salah satunya adalah *Time-on-Task* (ToT) atau disebut juga *Task Completion Time*. Berbeda dengan metode kuesioner kualitatif yang mengandalkan persepsi, opini, atau ingatan pengguna, metrik ToT merekam durasi waktu nyata (dalam satuan detik) secara presisi sejak pengguna memulai suatu tugas hingga tugas tersebut sukses diselesaikan.

Pengukuran objektif berbasis waktu ini memberikan data primer yang sangat jujur mengenai kualitas navigasi sebuah sistem. Semakin kecil nilai rata-rata *Time-on-Task* yang diraih oleh pengguna saat mengeksekusi suatu menu, maka semakin optimal, intuitif, dan efisien tata letak komponen antarmuka serta arsitektur informasi pada aplikasi tersebut.

---

## 2.3 Arsitektur Informasi: Super App vs Stand-alone App

Kompleksitas visual dari sebuah antarmuka pengguna dompet digital sangat dipengaruhi oleh model arsitektur informasi yang diterapkan pada aplikasi tersebut:

*   **Model Super App:** Platform ekosistem digital yang mengintegrasikan berbagai jenis layanan yang tidak sejenis (seperti sistem pembayaran, transportasi daring, pesan antar makanan, hiburan, hingga investasi) ke dalam satu aplikasi tunggal. Penambahan fitur yang masif dan padat ini berdampak langsung pada tingginya kepadatan elemen visual pada halaman utama. Kepadatan tersebut berpotensi menimbulkan *information overload* (beban informasi berlebih) yang memicu terjadinya *scanning delay*—suatu kondisi di mana mata pengguna terdiam beberapa saat karena kebingungan mencari letak menu utama di antara tumpukan menu lainnya.
*   **Model Stand-alone App:** Pendekatan desain antarmuka modern yang memisahkan fungsi inti ke dalam aplikasi mandiri yang bersifat tunggal dan minimalis. Model ini berfokus pada reduksi elemen visual yang tidak diperlukan untuk menurunkan beban kognitif pengguna. Dengan memangkas fitur eksternal yang tidak relevan, alur navigasi operasional menjadi lebih pendek dan intuitif.

---

## 2.4 Penelitian Terdahulu (Related Work) dan Celah Penelitian

Evaluasi kegunaan (*usability*) pada aplikasi dompet digital di Indonesia telah banyak dilakukan oleh peneliti terdahulu. Mayoritas studi tersebut mengevaluasi tingkat kenyamanan platform dompet digital populer menggunakan instrumen kuesioner standar seperti *System Usability Scale* (SUS) atau *User Experience Questionnaire* (UEQ). Penelitian-penelitian tersebut berhasil memetakan tingkat kepuasan dan preferensi kenyamanan pengguna dari sudut pandang penilaian subjektif.

Namun, dari kajian literatur tersebut ditemukan sebuah celah penelitian (*research gap*) yang sangat nyata. Evaluasi yang sepenuhnya berbasis kuesioner memiliki keterbatasan berupa ketergantungan pada opini ingatan responden yang rentan terhadap bias (*memory bias*), serta tidak mampu mencerminkan performa kecepatan teknis yang sebenarnya di lapangan. Belum ditemukan studi komparatif kuantitatif yang secara khusus mengadu performa teknis model *Stand-alone* melawan model *Super App* menggunakan metode eksperimen terkontrol dengan parameter objektif berupa durasi waktu nyata. Oleh karena itu, penelitian ini hadir untuk mengisi celah tersebut dengan memanfaatkan data durasi empiris *Time-on-Task* guna menyajikan pembuktian efisiensi arsitektur informasi yang lebih akurat dan presisi.