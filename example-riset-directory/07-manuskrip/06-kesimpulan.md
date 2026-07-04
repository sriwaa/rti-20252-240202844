# 06-kesimpulan

Draf bab kesimpulan dan saran naskah ilmiah — **Tahap 5**.

---

## 5.1 Kesimpulan

Berdasarkan hasil eksperimen terkontrol dan analisis statistik inferensial yang telah dilakukan terhadap 40 responden mahasiswa Universitas Putra Bangsa (UPB) Kebumen, penelitian ini berhasil menarik dua kesimpulan utama yang menjawab pertanyaan penelitian:

1.  **Pembuktian Efisiensi Secara Empiris:**  
    Terdapat perbedaan tingkat efisiensi interaksi pengguna yang sangat signifikan secara statistik antara aplikasi GoPay (model *Stand-alone*) dan aplikasi DANA (model *Super App*). Hasil uji *Paired Samples T-Test* membuktikan bahwa nilai rata-rata durasi waktu transaksi (*Time-on-Task*) untuk mengakses fitur QRIS pada GoPay adalah **4,8565 detik**, sedangkan pada DANA membutuhkan waktu yang lebih lama yaitu **6,0450 detik**.
2.  **Validasi Hipotesis Desain:**  
    Hipotesis penelitian terbukti secara sah di mana model arsitektur *Stand-alone* yang minimalis mampu memangkas waktu pengerjaan transaksi secara konsisten dengan selisih rata-rata sebesar **1,18850 detik** lebih cepat dibandingkan model *Super App*. Reduksi elemen visual non-inti pada halaman utama terbukti efektif menurunkan beban kognitif pengguna dan mengeliminasi hambatan pemindaian visual (*scanning delay*) saat melakukan aktivitas finansial yang membutuhkan respons cepat.

---

## 5.2 Saran Penelitian Lanjutan

Untuk menyempurnakan batasan dan memperluas cakupan temuan dalam penelitian ini, beberapa saran yang diajukan untuk agenda riset mendatang meliputi:

*   **Perluasan Demografi dan Karakteristik Sampel:**  
    Penelitian selanjutnya disarankan untuk memperluas cakupan responden di luar kelompok mahasiswa *tech-savvy*, misalnya melibatkan kelompok masyarakat dengan rentang usia yang lebih tua (generasi X atau *baby boomers*) atau masyarakat di wilayah pedesaan Kebumen. Hal ini penting untuk menguji apakah perbedaan arsitektur informasi tetap memberikan dampak efisiensi yang konstan pada tingkat literasi digital yang berbeda.
*   **Variasi Skenario Tugas (Task Scenarios):**  
    Skenario pengujian dalam riset ini terbatas pada akses awal fitur pemindaian QRIS dari kondisi aplikasi mati (*cold start*). Riset berikutnya dapat mengembangkan skenario tugas yang lebih kompleks dan end-to-end, seperti proses transfer antar-bank, pengisian saldo (*top-up*), atau pembayaran tagihan bulanan guna memetakan efisiensi arsitektur informasi pada kedalaman menu yang berbeda.
*   **Integrasi Pengukuran Biometrik Objektif:**  
    Untuk memperkuat analisis beban kognitif yang saat ini dianalisis berbasis durasi waktu, penelitian lanjutan dapat mengintegrasikan perangkat keras tambahan seperti alat pelacak pandangan mata (*Eye Tracker*) untuk mengukur arah tatapan (*fixation duration*) atau sensor *Electroencephalography* (EEG) guna menangkap data gelombang otak secara langsung saat pengguna berinteraksi dengan antarmuka aplikasi.