# PROYEK AKHIR PENGOLAHAN SINYAL DIGITAL
## KELOMPOK 7

# Analisis Jenis Sinyal Bunyi Lingkungan Menggunakan Visualisasi Spectrogram dan Ekstraksi Fitur MFCC

## Identitas Kelompok

| No. | Nama | NIM |
|:---:|---|:---:|
| 1 | Yanaka Sofia Pardede | 24031554065 |
| 2 | Fajria Rasmi Ridha Rumkel | 24031554191 |
| 3 | Shakyla Andhara Chandraningtyas | 24031554199 |

**Program Studi:** S1 Sains Data  
**Fakultas:** Matematika dan Ilmu Pengetahuan Alam  
**Universitas:** Universitas Negeri Surabaya  
**Semester:** Gasal 2025/2026

**Dosen Pengampu:**
- Dr. Atik Wintarti, M.Kom.
- Kartika Chandra Dewi, S.Si., M.Si.

---

## Deskripsi Proyek

Proyek ini merupakan proyek akhir mata kuliah **Pengolahan Sinyal Digital** yang bertujuan untuk menganalisis dan membandingkan karakteristik lima jenis suara lingkungan, yaitu burung, hujan, kendaraan, mesin, dan angin, menggunakan beberapa metode pengolahan sinyal digital.

Analisis dilakukan melalui empat pendekatan utama, yaitu *Waveform*, *Fast Fourier Transform* (FFT), *Spectrogram*, dan *Mel-Frequency Cepstral Coefficients* (MFCC). Keempat metode tersebut digunakan untuk mengamati karakteristik sinyal dari berbagai perspektif, mulai dari amplitudo terhadap waktu, distribusi frekuensi, perubahan energi terhadap waktu dan frekuensi, hingga karakteristik akustik suara.

Melalui proyek ini, dilakukan perbandingan karakteristik dari kelima jenis suara untuk mengetahui perbedaan pola sinyal serta melihat bagaimana masing-masing metode dapat membantu mengidentifikasi karakteristik suara lingkungan.

Penjelasan lebih lengkap mengenai proses penelitian dan hasil analisis dapat dilihat pada laporan proyek yang tersedia di folder `docs/`.

## Dataset

Dataset yang digunakan dalam penelitian ini berupa rekaman audio dari lima jenis suara lingkungan. Audio diperoleh dari video TikTok, kemudian diunduh menggunakan `yt-dlp` dan dikonversi ke format MP3 dengan bitrate 192 kbps.

### Jenis Suara yang Dianalisis

| Jenis Suara | Karakteristik Umum |
|---|---|
| Burung | Memiliki frekuensi tinggi, pola tidak periodik, dan karakteristik yang dinamis. |
| Hujan | Memiliki karakter suara kontinu dan relatif stabil dengan dominasi frekuensi rendah hingga menengah. |
| Kendaraan | Memiliki pola semi-periodik dengan struktur harmonik. |
| Mesin | Memiliki pola periodik dan stasioner dengan karakteristik harmonik yang kuat. |
| Angin | Memiliki pola acak, tidak periodik, dan distribusi spektrum yang menyebar. |

**Catatan:** File audio tidak disertakan dalam repository. Sumber audio berupa tautan video TikTok yang tercantum dalam laporan proyek.

## Metode Pengolahan Sinyal Digital

Penelitian ini menggunakan empat metode utama untuk menganalisis karakteristik sinyal audio.

### 1. Waveform

*Waveform* digunakan untuk menggambarkan perubahan amplitudo sinyal terhadap waktu. Visualisasi ini membantu mengamati pola gelombang, intensitas, serta dinamika setiap jenis suara.

### 2. Fast Fourier Transform (FFT)

FFT digunakan untuk mengubah sinyal dari domain waktu ke domain frekuensi sehingga distribusi frekuensi dan komponen frekuensi dominan dapat diamati.

Pada proyek ini, visualisasi FFT difokuskan pada rentang frekuensi 0–8.000 Hz.

### 3. Spectrogram

*Spectrogram* digunakan untuk memperlihatkan perubahan energi sinyal berdasarkan waktu dan frekuensi menggunakan metode *Short-Time Fourier Transform* (STFT).

Visualisasi ditampilkan dalam skala desibel (dB) untuk membantu mengidentifikasi distribusi energi dan karakteristik frekuensi dari masing-masing suara.

### 4. Mel-Frequency Cepstral Coefficients (MFCC)

MFCC merupakan metode ekstraksi fitur yang digunakan untuk merepresentasikan karakteristik spektral suara berdasarkan skala Mel yang menyesuaikan persepsi pendengaran manusia.

Dalam penelitian ini, digunakan 13 koefisien MFCC untuk menangkap karakteristik akustik dari setiap jenis suara.

Setelah proses analisis dilakukan, nilai rata-rata dari masing-masing metode dihitung dan digunakan untuk membuat grafik perbandingan kelima jenis suara.

## Alur Kerja Penelitian

Proses pengerjaan proyek dilakukan melalui beberapa tahapan berikut:

1. **Pengumpulan Audio:** Mengunduh sumber audio dari video TikTok menggunakan `yt-dlp` dan mengonversinya ke format MP3.
2. **Pemrosesan Audio:** Memuat file audio menggunakan library `librosa` dengan durasi maksimum 60 detik.
3. **Analisis Waveform:** Mengamati pola amplitudo sinyal terhadap waktu.
4. **Analisis FFT:** Mengidentifikasi distribusi dan komponen frekuensi dominan.
5. **Analisis Spectrogram:** Mengamati perubahan energi sinyal terhadap waktu dan frekuensi.
6. **Ekstraksi Fitur MFCC:** Mengekstraksi 13 koefisien MFCC untuk memperoleh karakteristik akustik suara.
7. **Perhitungan Rata-Rata:** Menghitung nilai rata-rata dari setiap metode analisis.
8. **Visualisasi Perbandingan:** Membuat grafik perbandingan kelima jenis suara, termasuk penggabungan waveform dan FFT dalam satu visualisasi.
9. **Analisis Hasil:** Membandingkan karakteristik setiap suara dan menyusun kesimpulan berdasarkan hasil pengolahan sinyal.

## Hasil Analisis

Berdasarkan hasil pengolahan dan analisis terhadap lima jenis suara lingkungan, diperoleh ringkasan nilai tertinggi dan terendah dari setiap metode sebagai berikut.

### 1. Perbandingan Hasil Setiap Metode

| Metode Analisis | Nilai Tertinggi | Nilai Terendah |
|---|---|---|
| Rata-rata amplitudo Waveform | Hujan (0,1665) | Angin (0,0785) |
| Rata-rata Magnitude FFT | Burung (127,84) | Angin (27,71) |
| Rata-rata Energi Spectrogram (dB) | Mesin (-53,75) | Burung (-71,92) |
| Rata-rata MFCC | Hujan (9,57) | Burung (-15,79) |

### 2. Temuan Utama

Berdasarkan hasil visualisasi dan perbandingan karakteristik sinyal, diperoleh beberapa temuan berikut:

- **Suara Burung:** Memiliki energi yang tersebar pada frekuensi menengah hingga tinggi serta karakteristik sinyal yang tidak stasioner dan dinamis.
- **Suara Hujan:** Memiliki karakteristik suara yang relatif kontinu dan stabil dengan dominasi frekuensi rendah hingga menengah.
- **Suara Kendaraan:** Menunjukkan karakteristik semi-periodik yang berada di antara suara alami dan suara mekanis.
- **Suara Mesin:** Memiliki karakteristik periodik dan stasioner dengan puncak harmonik yang tajam, terutama pada frekuensi rendah.
- **Suara Angin:** Memiliki karakteristik acak dan tidak periodik dengan distribusi spektrum yang menyebar serta tanpa puncak frekuensi dominan yang kuat.

### 3. Interpretasi Hasil

Hasil penelitian menunjukkan bahwa setiap metode memiliki kemampuan yang berbeda dalam menggambarkan karakteristik suara lingkungan.

- *Waveform* membantu mengidentifikasi perubahan amplitudo dan intensitas suara.
- FFT memberikan informasi mengenai distribusi frekuensi dan komponen frekuensi dominan.
- *Spectrogram* memperlihatkan pola perubahan energi berdasarkan waktu dan frekuensi.
- MFCC memberikan representasi fitur akustik yang dapat digunakan untuk membandingkan karakteristik suara.

Dengan demikian, penggunaan keempat metode secara bersamaan memberikan gambaran yang lebih menyeluruh dalam menganalisis dan membedakan karakteristik kelima jenis suara lingkungan.

## Kesimpulan

Berdasarkan hasil penelitian, dapat disimpulkan bahwa lima jenis suara lingkungan, yaitu burung, hujan, kendaraan, mesin, dan angin, memiliki karakteristik sinyal yang berbeda berdasarkan domain waktu, domain frekuensi, domain waktu-frekuensi, dan fitur akustiknya.

Suara mesin menunjukkan karakteristik periodik dan stasioner dengan struktur harmonik yang kuat. Sebaliknya, suara burung memiliki karakteristik yang lebih dinamis dengan distribusi energi pada frekuensi menengah hingga tinggi. Sementara itu, suara hujan dan angin cenderung memiliki distribusi frekuensi yang menyebar, tetapi menunjukkan perbedaan pada kestabilan pola sinyal. Suara kendaraan memiliki karakteristik semi-periodik.

Hasil analisis juga menunjukkan bahwa keempat metode yang digunakan saling melengkapi. Waveform membantu mengamati amplitudo, FFT menggambarkan distribusi frekuensi, Spectrogram menunjukkan perubahan energi terhadap waktu dan frekuensi, sedangkan MFCC memberikan representasi karakteristik akustik suara.

Oleh karena itu, kombinasi visualisasi Spectrogram dan ekstraksi fitur MFCC, bersama dengan analisis Waveform dan FFT, dapat memberikan pemahaman yang lebih lengkap mengenai karakteristik berbagai jenis suara lingkungan.

## Cara Menjalankan Proyek

Untuk menjalankan proyek ini, pastikan Python sudah tersedia atau gunakan Google Colab sebagai lingkungan pengembangan.

### 1. Install Dependencies

Jalankan perintah berikut pada terminal atau sel notebook:

```bash
pip install yt-dlp librosa soundfile matplotlib numpy pandas
```

### 2. Install FFmpeg

Pengunduhan dan konversi audio menggunakan `yt-dlp` memerlukan FFmpeg.

Pastikan FFmpeg sudah terpasang dan dapat diakses oleh sistem sebelum menjalankan proses pengunduhan serta konversi audio.

### 3. Menjalankan Notebook

1. Buka file notebook proyek menggunakan Google Colab atau Jupyter Notebook.
2. Pastikan seluruh library yang dibutuhkan sudah terinstal.
3. Siapkan tautan sumber audio sesuai dengan yang tercantum dalam laporan.
4. Jalankan setiap sel notebook secara berurutan.
5. Amati hasil visualisasi dan analisis yang dihasilkan untuk masing-masing jenis suara.
