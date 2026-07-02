# Survey-AI-ITSB

Survei persepsi mahasiswa Institut Teknologi Sains Bandung (ITSB) terhadap integrasi *Artificial Intelligence* (AI) dalam lingkungan akademik. Dikerjakan oleh **Kelompok 4 — Sains Data B** untuk mata kuliah **Survey dan Sampling**, dibawah asuhan Bapak Dr. Andi Pujo Rahadi, S.T.,M.Sc.

---

## 📌 Daftar Isi

- [Latar Belakang & Tujuan](#-latar-belakang--tujuan)
- [Populasi & Sampel](#-populasi--sampel)
- [Metode Sampling](#-metode-sampling)
- [Struktur Repository](#-struktur-repository)
- [Dataset](#-dataset)
- [Tools & Library](#-tools--library)
- [Cara Menjalankan](#-cara-menjalankan)
- [Hasil Utama](#-hasil-utama)
- [Batasan Studi](#-batasan-studi-baca-ini-sebelum-generalisasi-hasil)
- [Referensi](#-referensi)
- [Tim Penyusun](#-tim-penyusun)
- [Lisensi](#-lisensi)

---

## 🎯 Latar Belakang & Tujuan

Studi ini memetakan adopsi AI di kalangan mahasiswa ITSB dan mengukur persepsi mereka terhadap manfaat, risiko, dan kebutuhan kebijakan kampus. Empat tujuan spesifik:

1. Memetakan jenis platform AI yang digunakan dan frekuensi penggunaannya.
2. Mengukur persepsi manfaat AI terhadap pemahaman materi, kualitas tugas, dan belajar mandiri.
3. Menganalisis kekhawatiran mahasiswa (penurunan berpikir kritis, ketergantungan, privasi data).
4. Merumuskan rekomendasi kebijakan bagi dosen dan kampus.

## 📊 Populasi & Sampel

| Aspek | Nilai |
|---|---|
| Populasi | 2.039 mahasiswa aktif ITSB (seluruh program studi) |
| Target sampel (rumus Slovin, e=12%, CI 95%) | ≈ 67 responden |
| Realisasi | **64 responden** (≈3% populasi) |
| Margin of Error | ±12,25% |
| Periode pengumpulan | 2 minggu via Google Form |

**Margin of error ±12,25% itu besar** — ini bukan detail kecil. Artinya interval kepercayaan di sekitar tiap persentase dalam laporan ini lebar; klaim seperti "62% mahasiswa pakai AI ≥4x/minggu" secara statistik bisa saja sebenarnya di kisaran 50–74% pada populasi nyata. Jangan disajikan ke pembaca luar sebagai angka presisi.

## 🔬 Metode Sampling

- **Teknik:** *Convenience sampling* (non-probability) — disebar via media sosial dan grup mahasiswa, tanpa randomisasi.
- **Instrumen:** Kuesioner Google Form, 16 pertanyaan (demografis, pilihan ganda, skala Likert 1–4, 3 pertanyaan terbuka).
- **Implikasi:** Karena non-probability sampling, secara metodologis hasil ini **tidak bisa digeneralisasi** ke seluruh populasi ITSB — ini diakui eksplisit oleh tim penyusun sendiri di notebook maupun PPT sebagai *pilot study*.

## 📁 Struktur Repository

```
Survey-AI-ITSB/
├── Data Hasil Olahan.ipynb    # Notebook EDA: cleaning, visualisasi matplotlib, analisis pertanyaan terbuka
├── Dataset Survey.csv         # Data mentah, 64 baris x 16 kolom, identitas responden sudah dianonimkan
├── PPT Survey Final.pdf       # Slide presentasi hasil (12 halaman, termasuk daftar pustaka)
├── Foto Kelompok.jpeg         # Dokumentasi kelompok
└── README.md                  # Dokumentasi proyek (file ini)
```

## 🗂️ Dataset

`Dataset Survey.csv` — 64 baris, 16 kolom:

| Kategori | Kolom |
|---|---|
| Demografis | ID Mahasiswa (anonim), Jenis Kelamin, Angkatan, Program Studi |
| Perilaku | AI yang paling sering digunakan (multi-select), Frekuensi penggunaan/minggu |
| Skala Likert 1–4 (7 pernyataan) | Membantu memahami materi, meningkatkan kualitas tugas, percaya diri ujian, mendukung belajar mandiri, memengaruhi privasi data, mengurangi berpikir kritis, kesiapan ITSB |
| Terbuka (3 pertanyaan) | Pendapat integrasi AI oleh dosen, risiko terbesar AI, perlu-tidaknya kebijakan AI di ITSB |

**Komposisi responden** :
- Jenis kelamin: 33 laki-laki (52%), 31 perempuan (48%)
- Angkatan: 2025 = 55 orang (86%), 2023 = 5, 2024 = 4 — **timpang, hampir seluruhnya angkatan 2025**
- Program studi: Sains Data 24 (38%), sisanya tersebar di 9 prodi lain (masing-masing 2–7 orang)

Karena dominasi angkatan 2025 dan prodi Sains Data ini, hasil lebih mencerminkan pandangan mahasiswa baru/rumpun Sains Data ketimbang populasi ITSB secara keseluruhan — bukan cuma catatan formalitas, tapi keterbatasan riil yang memengaruhi interpretasi tiap angka di bawah.

## 🛠️ Tools & Library

Berdasarkan isi notebook: Python 3, Jupyter Notebook, pandas, matplotlib.

## 🚀 Cara Menjalankan

```bash
git clone https://github.com/rabiblolong/Survey-AI-ITSB.git
cd Survey-AI-ITSB
pip install pandas matplotlib jupyter
jupyter notebook "Data Hasil Olahan.ipynb"
```

## 📈 Hasil Utama

**Adopsi:**
- 62% responden (40 dari 64) menggunakan AI ≥4x/minggu; hanya 19 orang (30%) di kategori >7x.
- Platform terpopuler (multi-select, dari 64 responden): ChatGPT 70%, Gemini 62%, Claude 45%, Deepseek 25%, Perplexity 19%.

**Skor Likert (skala 1–4, makin tinggi = makin setuju):**

| Pernyataan | Skor rata-rata |
|---|---|
| AI mendukung belajar mandiri di luar jam kuliah | **3,50** (tertinggi) |
| AI membantu memahami materi sulit lebih cepat | 3,31 |
| Meningkatkan kualitas tugas/laporan | 3,17 |
| Khawatir AI mengurangi kemampuan berpikir kritis | 3,12 |
| ITSB sudah siap mendukung AI secara etis | 2,97 |
| Lebih percaya diri di ujian setelah pakai AI | 2,89 |
| AI memengaruhi privasi data | 2,47 (terendah) |

Poin yang layak digarisbawahi: skor kekhawatiran soal berpikir kritis (3,12) hampir sama tingginya dengan skor manfaat memahami materi (3,31). Mahasiswa merasakan manfaat AI, tapi kesadaran akan risikonya juga tinggi — ini bukan kelompok yang naif terhadap AI, tapi ambivalen terhadapnya.

**Pertanyaan terbuka (n=64):**

| Pertanyaan | Temuan |
|---|---|
| Integrasi AI oleh dosen | 84% setuju (54 responden), 13% bersyarat, 3% tidak setuju |
| Risiko terbesar AI | Berpikir kritis menurun 38% (24 respons), ketergantungan 33% (21), malas belajar 17% (11) |
| Perlu kebijakan AI di ITSB? | 84% menyatakan perlu (54), 11% kondisional, 5% tidak perlu |

## ⚠️ Batasan Studi (baca ini sebelum generalisasi hasil)

Ini bukan formalitas standar skripsi — ini batasan yang benar-benar membatasi apa yang bisa diklaim dari studi ini:

1. **Convenience sampling, bukan random sampling** — responden self-selected dari media sosial. Kemungkinan besar mahasiswa yang sudah aktif pakai AI lebih terdorong untuk mengisi survei ini dibanding yang tidak, sehingga angka adopsi (62% pakai ≥4x/minggu) berisiko bias ke atas.
2. **Margin of error ±12,25% dengan komposisi sampel timpang** (86% angkatan 2025, 38% Sains Data) — jangan menyajikan temuan ini seolah mewakili "mahasiswa ITSB" secara umum; lebih akurat disebut mewakili "mahasiswa baru, khususnya rumpun Sains Data."
3. **Pertanyaan terbuka dianalisis dengan keyword matching**, bukan coding kualitatif berlapis — kategori seperti "berpikir kritis menurun" vs "ketergantungan" berpotensi tumpang tindih maknanya tapi dihitung terpisah.
4. Tim penyusun sendiri sudah melabeli ini sebagai **pilot study / studi eksploratif**, bukan studi konklusif — ini sikap yang tepat dan sebaiknya dipertahankan, jangan di-upgrade jadi klaim yang lebih kuat saat dipresentasikan ke pihak luar.

## 📚 Referensi

[High confidence — disalin dari daftar pustaka di `PPT Survey Final.pdf`, ini bukan sumber yang saya cari sendiri]

1. Zawacki-Richter, O., Marín, V.I., Bond, M., & Gouverneur, F. (2019). Systematic review of research on AI applications in higher education. *International Journal of Educational Technology in Higher Education*, 16(39).
2. Kasneci, E., Seßler, K., Küchemann, S., et al. (2023). ChatGPT for good? On opportunities and challenges of LLMs for education. *Learning and Individual Differences*, 103, 102274.
3. Cochran, W.G. (1977). *Sampling Techniques* (3rd ed.). New York: John Wiley & Sons.
4. Sugiyono. (2019). *Metode Penelitian Kuantitatif, Kualitatif, dan R&D*. Bandung: Alfabeta.
5. Lim, W.M., Gunasekara, A., Pallant, J.L., Pallant, J.I., & Pechenkina, E. (2023). Generative AI and the future of education. *The International Journal of Management Education*, 21(2), 100790.

## 👥 Tim Penyusun

**Kelompok 4 — Sains Data B, Survey dan Sampling**

| Nama | NIM | Peran |
|---|---|---|
| Januaria Teresinha | 52250076 | Ketua Kelompok — koordinasi, tujuan survei, finalisasi presentasi |
| Ignasius Rabi Blolong | 52250073 | Pengumpul Data — perancangan Google Form, penyebaran survei |
| Refantanur Husnul Haqib | 52250052 | Analisis Data — cleaning, visualisasi matplotlib, interpretasi statistik |
| Muhammad Nabil Khairil Anam | 52250066 | Penyusun Laporan — slide presentasi, daftar pustaka |

## 📄 Lisensi

Proyek akademik untuk mata kuliah Survey dan Sampling, ITSB. Tidak diperjualbelikan.

---
*Kelompok 4 — Sains Data B, ITSB, 2026*
