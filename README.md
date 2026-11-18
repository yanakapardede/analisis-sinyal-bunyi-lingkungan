# Analisis Jenis Sinyal Bunyi Lingkungan Menggunakan Visualisasi Spectrogram dan Ekstraksi Fitur MFCC

**Proyek Akhir Pengolahan Sinyal Digital - Kelompok 7**

| Nama | NIM |
|------|-----|
| Yanaka Sofia Pardede | 24031554065 |
| Fajria Rasmi Ridha Rumkel | 24031554191 |
| Shakyla Andhara Chandraningtyas | 24031554199 |

Program Studi S1 Sains Data, Fakultas Matematika dan Ilmu Pengetahuan Alam, Universitas Negeri Surabaya (Semester Gasal 2025/2026)

Dosen pengampu: Dr. Atik Wintarti, M.Kom. dan Kartika Chandra Dewi, S.Si., M.Si.

---

## Deskripsi

Proyek ini menganalisis lima jenis suara lingkungan (burung, hujan, kendaraan, mesin, dan angin) menggunakan metode pengolahan sinyal digital, yaitu **waveform**, **Fast Fourier Transform (FFT)**, **spectrogram**, dan **Mel-Frequency Cepstral Coefficients (MFCC)**. Tujuannya adalah membandingkan karakteristik tiap suara pada domain waktu, domain frekuensi, domain waktu-frekuensi, dan fitur akustik, serta melihat metode mana yang mampu membedakan kelima suara tersebut.

Penjelasan lengkap tersedia pada laporan proyek (lihat folder `docs/`).

## Dataset

Audio diambil dari video TikTok dan diunduh menggunakan `yt-dlp` (dikonversi ke MP3, 192 kbps).

| Suara | Karakter Umum |
|-------|---------------|
| Burung | Frekuensi tinggi, tidak periodik, sangat dinamis |
| Hujan | Kontinu, stabil, dominasi frekuensi rendah hingga menengah |
| Kendaraan | Semi-periodik, ada struktur harmonik |
| Mesin | Periodik, stasioner, harmonik kuat |
| Angin | Acak, tidak periodik, spektrum menyebar |

## Metode

- **Waveform:** amplitudo terhadap waktu.
- **FFT:** distribusi frekuensi dominan (ditampilkan 0-8000 Hz).
- **Spectrogram:** perubahan energi terhadap waktu dan frekuensi (STFT, skala dB).
- **MFCC:** 13 koefisien untuk menangkap ciri spektral berdasarkan persepsi pendengaran manusia.

Setelah itu dihitung nilai rata-rata tiap metode dan dibuat grafik perbandingan kelima suara.

## Alur Kerja

1. Unduh audio dan muat dengan `librosa` (durasi maksimum 60 detik).
2. Analisis waveform, FFT, spectrogram, dan MFCC untuk tiap suara.
3. Hitung rata-rata tiap metode dan buat grafik perbandingan.
4. Gabungkan kelima suara pada satu grafik (waveform dan FFT).
5. Tarik kesimpulan.

## Hasil Ringkas

| Metode | Tertinggi | Terendah |
|--------|-----------|----------|
| Rata-rata amplitudo waveform | Hujan (0,1665) | Angin (0,0785) |
| Rata-rata magnitude FFT | Burung (127,84) | Angin (27,71) |
| Rata-rata energi spectrogram (dB) | Mesin (-53,75) | Burung (-71,92) |
| Rata-rata MFCC | Hujan (9,57) | Burung (-15,79) |

Temuan utama:

- Mesin bersifat periodik dan stasioner dengan puncak harmonik tajam pada frekuensi rendah.
- Burung memiliki energi tersebar pada frekuensi menengah hingga tinggi dan bersifat non-stasioner.
- Hujan dan angin didominasi frekuensi rendah tanpa puncak dominan, dengan hujan lebih stabil dibanding angin.
- Kendaraan berada di antara suara alami dan mekanis (semi-periodik).
- Keempat metode saling melengkapi dalam membedakan intensitas, distribusi frekuensi, pola energi, dan timbre suara.

## Teknologi

Python, Google Colab, `librosa`, `numpy`, `pandas`, `matplotlib`, `soundfile`, `yt-dlp`


## Cara Menjalankan

```bash
pip install yt-dlp librosa soundfile matplotlib numpy pandas
```

Pengunduhan audio dengan `yt-dlp` memerlukan FFmpeg. Buka notebook di Google Colab atau Jupyter, lalu jalankan sel secara berurutan.

## Catatan

File audio tidak disertakan dalam repositori. Sumber audio berupa tautan video TikTok yang tercantum pada laporan.
