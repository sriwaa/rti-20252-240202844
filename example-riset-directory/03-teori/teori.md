# 03-teori

Landasan teori dan metodologi analisis statistik komparatif — hasil **Tahap 1**.

## Isi Dokumen
- Landasan Teori *Usability Testing* (Metrik Efisiensi)
- Konsep Dasar Pengujian *Paired Samples T-Test*
- Perumusan Hipotesis Penelitian
- Aturan Pengambilan Keputusan (Kriteria Signifikansi)

---

## 1. Landasan Teori Metrik Usability (Efficiency)

Dalam mengevaluasi antarmuka dan pengalaman pengguna (*User Experience / UX*) pada aplikasi dompet digital (GoPay dan DANA), aspek efisiensi (*Efficiency*) merupakan metrik krusial. Efisiensi mengukur kecepatan dan ketepatan pengguna dalam menyelesaikan tugas (*task*) tertentu di dalam sistem.

*   **Task Completion Time (Durasi):** Diukur berdasarkan satuan waktu (detik atau menit) sejak pengguna memulai suatu tugas hingga tugas tersebut selesai divalidasi oleh sistem.
*   **Beban Kognitif:** Durasi penyelesaian tugas yang lebih lama sering kali mengindikasikan adanya kendala pada *User Interface* (UI), seperti menu yang berlapis, alur navigasi yang membingungkan, atau hilangnya informasi penting secara instan (misalnya letak sisa saldo saat melakukan transaksi).

---

## 2. Landasan Teori Paired Samples T-Test

*Paired Samples T-Test* (Uji T Sampel Berpasangan) adalah analisis statistik parametrik yang digunakan untuk membandingkan rata-rata (*mean*) dari dua variabel yang bersumber dari satu kelompok sampel yang sama (saling berpasangan). 

Dalam eksperimen ini, uji dilakukan karena sampel responden bersifat tetap ($N = 40$), namun diberikan dua perlakuan berbeda, yaitu menguji **Durasi GoPay** dan **Durasi DANA**.

### Model Matematika & Rumus Uji T Berpasangan

Statistik uji $t$ dihitung berdasarkan perbedaan selisih nilai rata-rata sampel dengan rumus sebagai berikut:

$$t = \frac{\bar{D}}{\frac{S_D}{\sqrt{n}}}$$

**Keterangan:**
*   $\bar{D}$: Rata-rata perbedaan selisih antara pengamatan pertama dan kedua ($\text{Durasi GoPay} - \text{Durasi DANA}$)
*   $S_D$: Standar deviasi dari perbedaan selisih pengamatan
*   $n$: Jumlah sampel berpasangan ($n = 40$)
*   $\text{df}$ (*Degree of Freedom*): Derajat kebebasan yang ditentukan dengan rumus $\text{df} = n - 1$

---

## 3. Perumusan Hipotesis Penelitian

Pengujian hipotesis dilakukan untuk mengetahui secara valid apakah terdapat perbedaan efisiensi waktu yang signifikan antara kedua platform dompet digital tersebut:

*   **$H_0$ (Hipotesis Nol):** Tidak terdapat perbedaan rata-rata durasi yang signifikan antara penggunaan aplikasi GoPay dan aplikasi DANA ($\mu_1 = \mu_2$).
*   **$H_a$ (Hipotesis Alternatif):** Terdapat perbedaan rata-rata durasi yang signifikan antara penggunaan aplikasi GoPay dan aplikasi DANA ($\mu_1 \neq \mu_2$).

---

## 4. Kriteria Pengambilan Keputusan (Signifikansi)

Analisis data dilakukan dengan menggunakan alat bantu software **IBM SPSS Statistics**. Pengambilan keputusan untuk menolak atau menerima $H_0$ didasarkan pada nilai signifikansi p-value (*Sig. 2-tailed*) pada output tabel *Paired Samples Test* dengan ketentuan:

> *   Jika nilai $\text{Sig. (2-tailed)} < 0.05$, maka **$H_0$ Ditolak** dan **$H_a$ Diterima**. (Artinya, perbedaan durasi bersifat signifikan secara statistik).
> *   Jika nilai $\text{Sig. (2-tailed)} \ge 0.05$, maka **$H_0$ Diterima** dan **$H_a$ Ditolak**. (Artinya, perbedaan durasi hanya terjadi karena faktor kebetulan dan tidak signifikan).