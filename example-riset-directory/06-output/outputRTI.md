# 04-analisis-dan-pembahasan

Analisis data hasil pengujian komparatif Task Completion Time antara GoPay dan DANA menggunakan metode Paired Samples T-Test.

## 1. Analisis Deskriptif (Paired Samples Statistics)

Berdasarkan hasil pemrosesan data pada tabel Paired Samples Statistics, berikut adalah ringkasan performa durasi waktu dari kedua platform:

*   **Rata-rata (Mean) Durasi GoPay:** `4.8565` detik dengan standar deviasi sebesar `0.65912`.
*   **Rata-rata (Mean) Durasi DANA:** `6.0450` detik dengan standar deviasi sebesar `0.84165`.
*   **Jumlah Sampel (N):** `40` responden.

**Interpretasi:**  
Secara deskriptif, terdapat perbedaan nilai rata-rata durasi penyelesaian tugas di antara kedua aplikasi. Pengguna rata-rata mampu menyelesaikan tugas di aplikasi GoPay `1.1885` detik lebih cepat dibandingkan ketika menggunakan aplikasi DANA.

---

## 2. Analisis Hubungan (Paired Samples Correlations)

Tabel Paired Samples Correlations mengukur kekuatan hubungan (korelasi) linier antara durasi pengerjaan tugas pada aplikasi GoPay dan DANA dari responden yang sama:

*   **Nilai Koefisien Korelasi:** `0.531`
*   **Nilai Signifikansi (Sig.):** `0.000`

**Interpretasi:**  
Nilai korelasi sebesar `0.531` menunjukkan adanya hubungan positif yang cukup kuat dan searah antara kedua variabel. Nilai **Sig. (0.000) < 0.05** menandakan bahwa hubungan atau korelasi durasi antar kedua platform tersebut bersifat signifikan secara statistik.

---

## 3. Uji Hipotesis Perbedaan (Paired Samples Test)

Tabel Paired Samples Test merupakan inti dari pengujian untuk menarik kesimpulan apakah perbedaan rata-rata durasi yang ditemukan pada analisis deskriptif benar-benar signifikan (nyata) atau hanya kebetulan semata.

*   **Nilai Rata-rata Perbedaan (Mean Paired Differences):** `-1.18850` (Arah pengurangan GoPay dikurangi DANA bernilai negatif, mengonfirmasi durasi GoPay lebih singkat).
*   **Nilai t Hitung:** `-10.104`
*   **Derajat Kebebasan (df):** `39`
*   **Nilai Signifikansi / Sig. (2-tailed):** `0.000`

### Pengambilan Keputusan:
Sesuai dengan kriteria pengujian statistik dasar:
*   Jika nilai Sig. (2-tailed) < 0.05, maka H0 Ditolak dan Ha Diterima.

Karena nilai **Sig. (2-tailed) adalah 0.000 (lebih kecil dari 0.05)**, maka keputusan statistik yang diambil adalah **Menolak H0** dan **Menerima Ha**.

---

## 4. Kesimpulan Akhir Penelitian

Berdasarkan rangkaian uji Paired Samples T-Test di atas, dapat disimpulkan bahwa **terdapat perbedaan rata-rata durasi penyelesaian tugas yang sangat signifikan antara aplikasi GoPay dan aplikasi DANA**. 

Dari sisi usability (metrik efficiency), aplikasi **GoPay terbukti secara nyata lebih efisien** dalam memangkas waktu transaksional pengguna dibandingkan aplikasi DANA bagi 40 responden yang diuji dalam penelitian ini.