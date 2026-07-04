# 00-outline

Outline, peta sumber data, dan daftar klaim kunci untuk draf manuskrip ilmiah — **Tahap 5**.

---

## 1. Peta Sumber Data & Keselarasan Berkas

Dokumen ini berfungsi sebagai peta kendali untuk memastikan seluruh data statistik yang ditulis pada naskah bersumber dari data empiris yang valid:

*   **Sumber Data Mentah:** `gopay dana.xlsx` (Data pengukuran durasi waktu tugas transaksional dari 40 responden berpasangan).
*   **Sumber Output Statistik:** `SS_outputRTI.jpg` (Hasil analisis Paired Samples T-Test pada IBM SPSS Statistics).
*   **Target Publikasi:** Sinta 2 (Jurnal RESTI / Telematika) atau Scopus Q3-Q4.

---

## 2. Struktur Outline Manuskrip (Template IMRAD)

Naskah lengkap pada file `naskah-jurnal.md` wajib mengikuti struktur standar jurnal ilmiah berikut:

### Judul Penelitian
*   *Perbandingan Efisiensi Model Stand-alone (GoPay) dan Super App (DANA) Menggunakan Metrik Time-on-Task pada Mahasiswa UPB*

### Abstrak (Abstract)
*   Memuat ringkasan latar belakang transisi model desain aplikasi dompet digital, metode eksperimen kegunaan (*Usability Testing*), hasil statistik SPSS, dan kesimpulan efisiensi platform. Tersedia dalam versi Bahasa Indonesia dan English.

### 1. Pendahuluan
*   **Latar Belakang:** Perkembangan fintech di Indonesia, serta munculnya dua model arsitektur aplikasi (Super App dan Stand-alone App) di kalangan mahasiswa Universitas Putra Bangsa (UPB) Kebumen.
*   **Rumusan Masalah:** Risiko *information overload* pada model Super App yang dapat meningkatkan beban kognitif pengguna dan menghambat efisiensi interaksi (durasi transaksi QRIS).
*   **Pendekatan Pemecahan Masalah:** Pengujian kegunaan (*Usability Testing*) melalui eksperimen terkontrol untuk membandingkan performa model Stand-alone (GoPay) terhadap model Super App (DANA).

### 2. Tinjauan Pustaka
*   Definisi *User Experience* (UX) dan aspek kegunaan (*Usability*).
*   Metrik efisiensi menggunakan pengukuran objektif *Time-on-Task* (ToT).
*   Konsep dasar pengujian komparatif sampel berpasangan (*Paired Samples T-Test*) untuk desain subjek yang sama (*Within-Subject*).
*   Analisis celah penelitian (*Research Gap*) dari penelitian terdahulu yang masih didominasi kuesioner subjektif (SUS/UEQ).

### 3. Metodologi Penelitian
*   **Desain Penelitian & Unit Analisis:** Eksperimen terkontrol (*Controlled Experiment*) dengan 40 responden berpasangan dari kalangan mahasiswa UPB Kebumen.
*   **Prosedur & Skenario:** Melakukan akses fitur pindai QRIS hingga kamera aktif sepenuhnya pada perangkat Samsung Galaxy A55.
*   **Mitigasi Bias:** Penerapan teknik *Counterbalancing* untuk mengeliminasi efek belajar (*learning effect*) dan *Cold Start Protocol* (*force stop* dan *clear cache*).

### 4. Hasil dan Analisis (Pembahasan)
*   **Statistik Deskriptif:** Penyajian nilai rata-rata (*Mean*) durasi GoPay (4.8565 detik) dan DANA (6.0450 detik).
*   **Uji Hubungan:** Pembahasan nilai koefisien korelasi sebesar 0.531 (Sig. 0.000).
*   **Uji Hipotesis Berpasangan:** Pembahasan nilai t-hitung (-10.104) dengan derajat kebebasan df = 39 dan nilai Sig. (2-tailed) = 0.000.
*   **Pembahasan Desain Antarmuka:** Diskusi mengenai pengaruh kepadatan elemen visual terhadap *scanning delay* dan beban kognitif pengguna.

### 5. Kesimpulan dan Saran
*   Kesimpulan utama bahwa model arsitektur Stand-alone (GoPay) terbukti secara nyata lebih efisien secara statistik dalam memangkas waktu transaksi dibanding model Super App (DANA).
*   Saran berupa pengembangan penelitian lanjutan lintas platform (seperti OVO dan ShopeePay) atau penambahan variasi tugas operasional lainnya.

---

## 3. Daftar Klaim Kunci (Key Claims) yang Harus Konsisten

Untuk menghindari kesalahan penulisan atau ketidaksesuaian data antar bab, seluruh draf modul wajib mengacu pada angka-angka kunci di bawah ini:

1.  **Klaim Jumlah Sampel:** Total responden yang berpartisipasi adalah **40 orang** mahasiswa Universitas Putra Bangsa dalam desain berpasangan (N = 40).
2.  **Klaim Perangkat Terkontrol:** Seluruh pengujian menggunakan satu jenis perangkat genggam yang sama, yaitu **Samsung Galaxy A55**.
3.  **Klaim Rata-Rata Waktu (Mean):** Durasi rata-rata GoPay adalah **4.8565 detik**, sedangkan DANA adalah **6.0450 detik**.
4.  **Klaim Selisih Efisiensi:** Pengguna GoPay lebih cepat **1.18850 detik** dibandingkan DANA (nilai Mean Paired Differences = -1.18850).
5.  **Klaim Nilai Signifikansi:** Nilai Sig. (2-tailed) adalah **0.000**, yang berarti hasil pengujian berada jauh di bawah ambang batas alpha 0.05 (Sangat Signifikan).
6.  **Klaim Nilai t-Hitung:** Nilai t yang diperoleh dari output uji berpasangan SPSS adalah **-10.104**.