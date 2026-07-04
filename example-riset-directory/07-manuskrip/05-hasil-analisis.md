# 05-hasil-analisis

Draf bab hasil dan analisis naskah ilmiah — **Tahap 5**.

---

## 4.1 Statistik Deskriptif Performa Durasi Transaksi

Berdasarkan hasil pengumpulan data primer terhadap 40 responden mahasiswa Universitas Putra Bangsa (UPB) Kebumen yang tercatat dalam basis data `gopay dana.xlsx`, analisis statistik deskriptif dilakukan untuk melihat profil pemusatan data durasi waktu (*Time-on-Task*) pada masing-masing aplikasi. Ringkasan hasil pengolahan data menggunakan IBM SPSS Statistics disajikan pada tabel berikut:

### Tabel 1. Statistik Deskriptif Paired Samples

| Aplikasi Dompet Digital | Mean (Detik) | N | Std. Deviation | Std. Error Mean |
| :--- | :---: | :---: | :---: | :---: |
| **GoPay** (Stand-alone Model) | 4,8565 | 40 | 0,65912 | 0,10422 |
| **DANA** (Super App Model) | 6,0450 | 40 | 0,84165 | 0,13308 |

Melalui data deskriptif di atas, terlihat perbedaan awal yang konsisten pada performa interaksi pengguna. Rata-rata durasi waktu yang dibutuhkan oleh responden untuk mengaktifkan fitur QRIS pada aplikasi GoPay adalah **4,8565 detik**. Sebaliknya, pada aplikasi DANA, responden memerlukan durasi rata-rata yang lebih lama, yaitu **6,0450 detik**. Nilai standar deviasi yang relatif kecil pada kedua kelompok (GoPay = 0,65912; DANA = 0,84165) mengindikasikan bahwa variasi sebaran data durasi antar-responden bersifat homogen dan tidak memiliki pencilan (*outlier*) yang ekstrem.

---

## 4.2 Analisis Korelasi Sampel Berpasangan

Sebelum melakukan pengujian hipotesis komparatif, dilakukan analisis korelasi linear untuk melihat kekuatan hubungan antara durasi waktu pengerjaan tugas pada kedua aplikasi yang diuji oleh subjek yang sama.

### Tabel 2. Paired Samples Correlations

| Hubungan Variabel | N | Correlation | Sig. |
| :--- | :---: | :---: | :---: |
| **Pair 1:** GoPay & DANA | 40 | 0,531 | 0,000 |

Hasil pengujian korelasi pada Tabel 2 menunjukkan nilai koefisien korelasi sebesar **0,531** dengan tingkat signifikansi (*p-value*) sebesar **0,000**. Karena nilai signifikansi jauh lebih kecil dari ambang batas \alpha = 0,05, dapat disimpulkan bahwa terdapat korelasi positif yang signifikan pada tingkat moderat antara durasi waktu transaksi GoPay dan DANA. Hal ini mengonfirmasi keabsahan penggunaan desain *Within-Subject* (sampel berpasangan), di mana karakteristik bawaan dari responden (seperti kecepatan motorik jari atau kecepatan pemahaman visual) secara konsisten memengaruhi performa mereka di kedua platform sistem.

---

## 4.3 Pengujian Hipotesis Komparatif (Paired Samples T-Test)

Pengujian hipotesis dilakukan menggunakan analisis parametrik *Paired Samples T-Test* untuk menentukan apakah perbedaan nilai rata-rata durasi yang ditemukan pada analisis deskriptif memiliki signifikansi secara statistik atau hanya bersifat kebetulan. Hasil komputasi dari berkas output `SS_outputRTI.jpg` diringkas pada tabel di bawah ini:

### Tabel 3. Hasil Uji Paired Samples T-Test

| Parameter Uji | Nilai Komputasi Statistik |
| :--- | :--- |
| **Mean Paired Differences** | -1,18850 detik |
| **Std. Deviation Differences** | 0,74421 |
| **Std. Error Mean Differences** | 0,11767 |
| **95% Confidence Interval - Lower** | -1,42651 |
| **95% Confidence Interval - Upper** | -0,95049 |
| **Nilai t-hitung** | -10,104 |
| **Degree of Freedom (df)** | 39 |
| **Sig. (2-tailed)** | 0,000 |

Berdasarkan hasil analisis pada Tabel 3, diperoleh nilai rata-rata perbedaan (Mean Paired Differences) sebesar -1,18850 detik. Nilai negatif ini menunjukkan adanya selisih pengurangan durasi, di mana penggunaan model Stand-alone (GoPay) terbukti secara konsisten memangkas waktu pengerjaan tugas transaksi pengguna sebesar 1,18850 detik menjadi lebih cepat jika dibandingkan dengan model Super App (DANA).

Nilai statistik uji t-hitung diperoleh sebesar -10,104 dengan derajat kebebasan (df) = 39 dan tingkat signifikansi Sig. (2-tailed) sebesar 0,000. Kriteria pengambilan keputusan statistik diatur sebagai berikut:

Apabila nilai Sig. (2-tailed) kurang dari 0,05, maka H0 ditolak dan Ha diterima.

Karena nilai signifikansi 0,000 kurang dari 0,05, maka Hipotesis Nol (H0) secara mutlak ditolak dan Hipotesis Alternatif (Ha) diterima. Hasil komputasi inferensial ini memberikan bukti empiris yang sangat kuat bahwa terdapat perbedaan tingkat efisiensi interaksi pengguna yang sangat signifikan secara statistik antara model arsitektur aplikasi Stand-alone (GoPay) dan model Super App (DANA).
---

## 4.4 Pembahasan Desain Antarmuka dan Beban Kognitif

Temuan kuantitatif dari pengujian *Time-on-Task* ini mendukung landasan teoretis Interaksi Manusia dan Komputer (HCI) terkait beban kognitif dan arsitektur informasi. Selisih efisiensi waktu sebesar 1,18850 detik yang dimenangkan oleh GoPay bukan disebabkan oleh perbedaan performa perangkat keras, karena seluruh variabel teknis telah dikunci menggunakan perangkat Samsung Galaxy A55 melalui *Cold Start Protocol*. Perbedaan performa ini murni lahir dari perbedaan filosofi desain antarmuka kedua aplikasi.

Aplikasi DANA yang mengusung model arsitektur *Super App* memiliki tingkat kepadatan elemen visual (*visual clutter*) yang tinggi pada halaman utama. Ketika aplikasi dibuka, mata pengguna dihadapkan pada puluhan ikon menu yang bervariasi mulai dari fitur finansial, hiburan, gaya hidup, hingga spanduk promosi interaktif. Kepadatan informasi ini memicu fenomena *information overload* yang memaksa sistem visual responden melakukan proses penyaringan informasi (*selective attention*) yang lebih berat. Akibatnya, terjadi penundaan pemindaian visual (*scanning delay*) yang meningkatkan beban kognitif pengguna sebelum akhirnya berhasil mengeklik menu QRIS.

Sebaliknya, GoPay versi *Stand-alone* menerapkan prinsip desain minimalis yang berfokus pada fungsi tunggal (*core-functionality*). Antarmuka halaman utama GoPay dirancang bersih dengan mereduksi elemen visual non-finansial secara agresif. Struktur informasi yang sederhana ini meminimalkan distrasi visual, sehingga mempermudah proses pemetaan mental pengguna (*mental mapping*). Karena usaha kognitif yang dibutuhkan untuk mengenali letak menu sangat rendah, responden dapat langsung mengeksekusi tindakan motorik untuk menekan tombol QRIS tanpa mengalami hambatan *scanning delay*. Reduksi beban kognitif inilah yang secara nyata mempercepat durasi interaksi (*Time-on-Task*) dan meningkatkan produktivitas efisiensi transaksi harian mahasiswa di lapangan.