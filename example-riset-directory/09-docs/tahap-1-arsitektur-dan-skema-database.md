# Tahap 1 — Perancangan Arsitektur & Skema Variabel

**Status:** Selesai

---

## 1. Komponen Eksperimen dan Pengujian

1. **Artefak Antarmuka (GoPay vs DANA)** — dua model arsitektur dompet digital yang diuji. GoPay merepresentasikan model Stand-alone App (bersih, fokus fungsi tunggal), sedangkan DANA merepresentasikan model Super App (padat fitur eksternal, berpotensi memicu information overload).
2. **Perangkat Kontrol Universal (Samsung Galaxy A55)** — unit pengujian perangkat keras tunggal untuk memastikan performa pemrosesan sistem, peluncuran memori, dan kartu grafis berjalan adil tanpa bias spesifikasi smartphone.
3. **Instrumen Pengukur Waktu (Stopwatch Digital & Lembar Fisik)** — digunakan oleh peneliti selaku observer untuk mencatat metrik durasi kuantitatif secara presisi (Time-on-Task) dalam satuan detik.
4. **Pipeline Data (Excel & IBM SPSS Statistics)** — tempat tabulasi master data primer (gopay dana.xlsx) untuk mengeksekusi uji parametrik deskriptif dan inferensial.

## 2. Alur Pelaksanaan Eksperimen (Protokol Kontrol)

```
Responden Masuk (N=40 Mahasiswa UPB) → Pembagian Kelompok Counterbalancing
  │
  ├─ Kelompok A (20 Responden): Uji GoPay dahulu → baru DANA
  └─ Kelompok B (20 Responden): Uji DANA dahulu → baru GoPay
        │
        ▼ (Protokol Alur Per Aplikasi)
Aplikasi Siap Diuji → Aktivasi Cold Start Protocol (Force Stop & Clear Cache)
  │
  ├─ t-awal (0,0000 detik): Responden menyentuh ikon aplikasi di beranda Samsung A55
  │     │
  │     ▼
  ├─ Fase Interaksi: Responden melakukan pemindaian visual dan navigasi menu QRIS
  │     │ (Terjadi scanning delay / beban kognitif akibat visual clutter pada Super App)
  │     ▼
  └─ t-akhir (durasi tercatat): Jendela bidik kamera pemindai QRIS aktif sepenuhnya 
        │
        ▼
Stopwatch Berhenti → Catat durasi ke Lembar Observasi Fisik → Pindahkan ke Excel

Catatan:
Pada pengujian ini, Cold Start Protocol wajib dijalankan setiap kali akan berpindah sesi pengujian responden. Aplikasi dipaksa berhenti melalui pengaturan Android dan cache dibersihkan agar aplikasi benar-benar dimuat dari memori kosong. Hal ini memastikan tidak ada efek pemuatan instan (RAM caching) yang mengacaukan akurasi pencatatan waktu.

Mekanisme **Validitas Data**: Jika responden salah menekan menu atau aplikasi mengalami gangguan koneksi internet kampus di tengah jalan, running pengujian pada responden tersebut dianggap gugur (fail-closed) dan wajib diulang setelah sistem kembali normal agar tidak merusak distribusi data.
```

## 3. Skema Penataan Data dan Variabel (Master Spreadsheet / SPSS)

Berikut adalah skema struktur penataan kolom data primer yang dirancang pada file master `gopay dana.xlsx` sebelum diimpor ke variabel IBM SPSS Statistics untuk pengujian Paired Samples T-Test:

| Nama Variabel | Tipe Data | Atribut / Keterangan | Tujuan Analisis |
|---|---|---|---|
| `ID_Responden` | NUMERIC (Nominal) | Angka urut identitas responden (1 sampai 40) | Identifikasi sampel berpasangan |
| `Urutan_Uji` | STRING (Nominal) | Kode kelompok: "GoPay-DANA" atau "DANA-GoPay" | Kontrol efek belajar (Counterbalancing) |
| `Waktu_GoPay` | NUMERIC (Scale) | Durasi waktu dalam satuan detik (Desimal 4 angka) | Mengukur Time-on-Task model Stand-alone |
| `Waktu_DANA` | NUMERIC (Scale) | Durasi waktu dalam satuan detik (Desimal 4 angka) | Mengukur Time-on-Task model Super App |
| `Selisih_Waktu` | NUMERIC (Scale) | Hasil pengurangan otomatis: Waktu_GoPay - Waktu_DANA | Dasar perhitungan Mean Paired Differences |

**Skema Formula Perhitungan Selisih (Secara Konseptual):**

Selisih_Waktu = Waktu_GoPay - Waktu_DANA

Jika nilai rata-rata `Selisih_Waktu` bernilai negatif (kurang dari 0), hal itu secara matematis membuktikan arsitektur Stand-alone (GoPay) beroperasi lebih cepat dan efisien dalam memangkas durasi transaksi dibandingkan model Super App (DANA).

## 4. Skema Penetapan Matrik Eksperimen

| Komponen Eksperimen | Tipe Variabel | Nilai / Batasan Pengukuran | Target Output |
|---|---|---|---|
| **Model Arsitektur Antarmuka** | Variabel Independen | Kondisi 1: Stand-alone (GoPay)<br>Kondisi 2: Super App (DANA) | Menjadi stimulus perbedaan performa kognitif |
| **Durasi Transaksi (Time-on-Task)** | Variabel Dependen | Nilai riil durasi waktu pengerjaan tugas dalam detik | Metrik utama efisiensi interaksi pengguna |

## 5. Keputusan Teknis dan Operasional (Final)

1. **Mode Eksperimen**: Menggunakan rancangan eksperimen berpasangan (Within-Subject Design) pada satu sampel tunggal (N = 40). Artinya seluruh responden yang sama menguji kedua aplikasi secara bergantian agar hasil perbandingan performa benar-benar murni (*apple-to-apple*) tanpa terpengaruh faktor subjektivitas individu.
2. **Teknik Mitigasi Efek Belajar**: Menerapkan **Counterbalancing** dengan membagi subjek secara adil (20 responden di Kelompok A, 20 responden di Kelompok B) untuk meniadakan bias kemahiran karena urutan pencobaan aplikasi.
3. **Standarisasi Perangkat Keras**: Mengunci alat uji pada satu tipe unit, yaitu **Samsung Galaxy A55**. Pengujian tidak boleh menggunakan smartphone milik responden masing-masing demi menghindari bias kecepatan prosesor.
4. **Lingkungan Pengujian**: Penelitian dilakukan langsung di area kampus Universitas Putra Bangsa (UPB) Kebumen dengan kondisi jaringan internet yang setara pada setiap sesi running.
5. **Software Analisis**: Menggunakan **IBM SPSS Statistics** sebagai pipeline komputasi utama untuk menguji hipotesis statistik melalui menu *Analyze -> Compare Means -> Paired-Samples T-Test*.
6. **Skenario Tugas**: Skenario tunggal yang diseragamkan: "Buka aplikasi dari kondisi tertutup, temukan dan akses fitur pemindai QRIS hingga kamera aktif siap memindai". Tidak ada instruksi tambahan selama pengujian berlangsung.
