# Data Visualization Layanan ART

## 1. Deskripsi Proyek

Proyek ini merupakan analisis dan visualisasi data pemesanan layanan asisten rumah tangga (ART) menggunakan Python melalui Google Colab. Proyek dilakukan untuk mengolah data transaksi menjadi informasi yang lebih mudah dipahami, khususnya mengenai pendapatan bulanan, jumlah pelanggan dan transaksi, serta waktu mulai layanan yang paling ramai.

Dataset diolah menggunakan Pandas, sedangkan visualisasi data dibuat menggunakan Matplotlib. Dataset disimpan dalam format Excel dan diakses melalui Google Drive.

## 2. Tujuan Proyek

Tujuan dari proyek ini adalah menyajikan hasil pengolahan data dalam bentuk grafik untuk memudahkan interpretasi dan evaluasi.

## 3. Dataset

Dataset yang digunakan adalah Dataset Layanan ART dalam format Excel (`.xlsx`).

Kolom utama dalam dataset meliputi:

| Kolom | Keterangan |
|---|---|
| No | Nomor urut transaksi |
| Nama | Nama pelanggan |
| Alamat | Alamat pelanggan |
| No. Telepon | Nomor telepon pelanggan |
| Tanggal | Tanggal pemesanan atau layanan |
| Jam/Waktu Layanan | Waktu mulai atau waktu layanan |
| Jam Kerja | Durasi layanan dalam jam |
| Jenis Layanan | Jenis layanan yang dipilih |
| Status Layanan | Status transaksi atau pemesanan |

Program menambahkan dua kolom baru, yaitu `Tarif per Jam` dan `Total Biaya`, untuk mendukung perhitungan pendapatan.

## 4. Tarif Layanan dan Perhitungan Biaya

Tarif per jam ditentukan berdasarkan jenis layanan sebagai berikut:

| Jenis Layanan | Tarif per Jam |
|---|---:|
| Bersih-bersih | Rp18.000 |
| Memasak | Rp23.000 |
| Paket lengkap | Rp30.000 |

Total biaya setiap transaksi dihitung menggunakan rumus:

`Total Biaya = Tarif per Jam × Jam Kerja`

## 5. Tahapan Pengolahan dan Analisis Data

Program dijalankan melalui beberapa tahapan berikut:

1. **Import Library**  
   Mengimpor Pandas, Matplotlib, NumPy, dan library pendukung lainnya.

2. **Menghubungkan Google Drive**  
   Menghubungkan Google Colab dengan Google Drive sebagai sumber dataset.

3. **Membaca Dataset**  
   Membaca file Excel dan memeriksa struktur data, jumlah baris, kolom, serta beberapa contoh data.

4. **Persiapan Data**  
   Menyesuaikan format tanggal dan jam kerja.

5. **Menentukan Tarif Layanan**  
   Memetakan setiap jenis layanan ke tarif per jam yang telah ditentukan.

6. **Menghitung Total Biaya**  
   Mengalikan tarif per jam dengan jumlah jam kerja untuk memperoleh total biaya setiap transaksi.

7. **Agregasi Data Bulanan**  
   Mengelompokkan data berdasarkan bulan untuk menghitung pendapatan, pelanggan unik, seluruh transaksi, dan transaksi yang diterima.

8. **Agregasi Waktu Layanan**  
   Mengekstrak jam mulai layanan dan menghitung jumlah pemesanan pada setiap jam.

9. **Visualisasi Data**  
   Membuat tiga grafik utama menggunakan Matplotlib.

10. **Menyimpan Hasil Analisis**  
    Menyimpan data.

## 6. Visualisasi Data

Proyek ini menghasilkan tiga jenis visualisasi utama.

### 6.1 Pendapatan Setiap Bulan

**Jenis grafik:** Line Chart.

Grafik ini digunakan untuk menampilkan perubahan pendapatan setiap bulan berdasarkan transaksi berstatus Diterima.

Komponen grafik:
- Judul grafik.
- Sumbu X yang menunjukkan bulan.
- Sumbu Y yang menunjukkan pendapatan dalam rupiah.
- Garis penghubung antartitik.
- Marker pada setiap titik data.
- Grid untuk membantu membaca nilai.
- Legenda yang menjelaskan garis pendapatan.

Interpretasi:

Garis yang meningkat menunjukkan bahwa pendapatan lebih tinggi dibandingkan bulan sebelumnya. Sebaliknya, garis yang menurun menunjukkan penurunan pendapatan. Titik tertinggi menunjukkan bulan dengan pendapatan terbesar dalam periode analisis.

Grafik ini dapat digunakan untuk melihat pola perubahan pendapatan dari waktu ke waktu, tetapi tidak secara langsung menjelaskan penyebab kenaikan atau penurunan tersebut.

### 6.2 Jumlah Pelanggan dan Transaksi Setiap Bulan

**Jenis grafik:** Bar Chart dengan batang berkelompok.

Grafik ini digunakan untuk membandingkan tiga ukuran:

1. **Pelanggan Unik** — jumlah nama pelanggan berbeda yang tercatat pada bulan tersebut.
2. **Seluruh Transaksi** — jumlah seluruh pemesanan yang tercatat pada bulan tersebut.
3. **Transaksi Diterima** — jumlah pemesanan yang berstatus Diterima.

Komponen grafik:
- Judul grafik.
- Sumbu X yang menunjukkan bulan.
- Sumbu Y yang menunjukkan jumlah.
- Batang dengan warna berbeda untuk setiap ukuran.
- Grid horizontal.
- Legenda untuk membedakan ketiga ukuran.

Interpretasi:

Perbandingan jumlah pelanggan unik dengan seluruh transaksi dapat membantu mengidentifikasi kemungkinan pemesanan berulang. 

### 6.3 Waktu Pemesanan Paling Ramai

**Jenis grafik:** Bar Chart.

Grafik ini digunakan untuk mengetahui distribusi pemesanan berdasarkan jam mulai layanan.

Program mengekstrak jam awal dari kolom `Jam/Waktu Layanan`, kemudian menghitung jumlah pemesanan pada setiap jam.

Komponen grafik:
- Judul grafik.
- Sumbu X yang menunjukkan jam mulai layanan.
- Sumbu Y yang menunjukkan jumlah pemesanan.
- Batang berwarna biru untuk jam lainnya.
- Batang berwarna oranye untuk jam dengan jumlah pemesanan tertinggi.
- Grid horizontal.
- Legenda untuk menjelaskan warna batang.

Interpretasi:

Batang tertinggi menunjukkan jam mulai layanan yang paling sering dipesan. Informasi tersebut dapat digunakan sebagai bahan pertimbangan dalam mengatur jadwal layanan dan ketersediaan tenaga kerja.

## 7. Interpretasi dan Kesimpulan Proyek

Melalui pengolahan dan visualisasi data, informasi transaksi layanan ART dapat disajikan secara lebih terstruktur dan mudah dipahami.

Line Chart membantu mengamati perubahan pendapatan setiap bulan. Bar Chart pelanggan dan transaksi membantu membandingkan jumlah pelanggan unik, seluruh pemesanan, serta pemesanan yang diterima. Sementara itu, Bar Chart waktu layanan membantu mengidentifikasi jam mulai layanan yang paling ramai.

Ketiga visualisasi tersebut dapat menjadi bahan pendukung evaluasi layanan dan pengambilan keputusan, misalnya dalam mengamati tren pendapatan, volume transaksi, serta kebutuhan pengaturan jadwal tenaga kerja.
