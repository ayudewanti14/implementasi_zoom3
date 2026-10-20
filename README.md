# implementasi_zoom3
Deskripsi
Notebook implementasi3.ipynb berisi implementasi analisis sederhana untuk menentukan prioritas pemeliharaan aset infrastruktur. Aset yang dianalisis meliputi jalan, jembatan, drainase, taman, lampu jalan, dan halte.

Analisis menggunakan metode weighted scoring (pembobotan skor) berdasarkan tiga aspek:
- Kondisi aset
- Usia aset
- Tingkat penggunaan aset
Hasilnya digunakan untuk memberikan skor, menentukan kategori prioritas, menyusun peringkat aset, dan menghasilkan rekomendasi pemeliharaan.
Catatan: Dataset di dalam notebook merupakan data contoh yang dibuat langsung di kode, bukan data lapangan atau data resmi suatu wilayah. Hasilnya ditujukan untuk demonstrasi dan pembelajaran.

Tujuan
- Mengolah data aset infrastruktur menggunakan Python.
- Menghitung skor prioritas pemeliharaan berdasarkan beberapa kriteria.
- Mengelompokkan aset ke kategori prioritas tinggi, sedang, dan rendah.
- Menampilkan hasil analisis melalui tabel dan grafik.
- Menghasilkan rekomendasi pemeliharaan berdasarkan kategori prioritas.
Dataset
Dataset contoh berisi 15 aset dengan kolom berikut:
Kolom	Keterangan
ID	Nomor identitas aset
Nama_Aset	Nama aset infrastruktur
Jenis_Aset	Jenis aset, seperti jalan atau jembatan
Usia_Tahun	Usia aset dalam tahun
Kondisi	Nilai kondisi aset pada skala 0–100
Penggunaan	Nilai tingkat penggunaan aset pada skala 0–100


Nilai dataset dimasukkan langsung di notebook, kemudian disimpan menjadi file dataset_aset.csv.
Metode Perhitungan
Notebook mengubah setiap kriteria menjadi skor, lalu menghitung skor prioritas dengan bobot berikut:
- Kondisi aset: 50% — skor kondisi dihitung sebagai 100 - Kondisi, sehingga kondisi dengan nilai lebih rendah menghasilkan skor kebutuhan pemeliharaan lebih tinggi.
- Usia aset: 30% — usia dibandingkan dengan usia maksimum acuan 30 tahun dan dibatasi pada skala 0–100.
- Penggunaan aset: 20% — menggunakan nilai Penggunaan yang tersedia pada dataset.
Rumus skor prioritas:
Skor_Prioritas =
    (0.50 × Skor_Kondisi) +
    (0.30 × Skor_Usia) +
    (0.20 × Skor_Penggunaan)
Kategori prioritas ditetapkan sebagai berikut:
Skor Prioritas	Kategori
70 atau lebih	Tinggi
40 sampai kurang dari 70	Sedang
Kurang dari 40	Rendah


Aset kemudian diurutkan dari skor prioritas tertinggi ke terendah dan diberi nomor peringkat.
Rekomendasi Pemeliharaan
Notebook menghasilkan rekomendasi berdasarkan kategori:
- Tinggi: Segera inspeksi dan rencanakan perbaikan.
- Sedang: Jadwalkan inspeksi dan pemeliharaan.
- Rendah: Lakukan pemantauan rutin.
Rekomendasi ini merupakan aturan sederhana untuk contoh analisis, bukan keputusan teknis pemeliharaan yang tervalidasi.
Teknologi yang Digunakan
- Python 3 — bahasa pemrograman.
- Pandas — pengolahan tabel dan ekspor CSV.
- NumPy — operasi numerik dan pembuatan peringkat.
- Matplotlib — pembuatan grafik.
- Seaborn — visualisasi hubungan antarvariabel.
- Google Colab atau Jupyter Notebook — lingkungan untuk menjalankan notebook.
Visualisasi dan File Keluaran
Notebook menghasilkan:
1. dataset_aset.csv — dataset contoh aset infrastruktur.
2. grafik_peringkat_aset.png — grafik batang peringkat skor prioritas pemeliharaan.
3. grafik_analisis_aset.png — grafik hubungan usia, kondisi, penggunaan, dan kategori prioritas.
4. hasil_analisis_prioritas_aset.csv — hasil analisis yang mencakup skor, kategori, peringkat, dan rekomendasi.
File keluaran tersimpan di lingkungan tempat notebook dijalankan. Jika menggunakan Google Colab, unduh file yang diperlukan sebelum sesi berakhir.
Cara Menjalankan di Google Colab
1. Unduh file implementasi3.ipynb.
2. Buka Google Colab.
3. Pilih File → Upload notebook, lalu unggah file tersebut.
4. Jalankan sel secara berurutan dari atas ke bawah, atau pilih Runtime → Run all.
5. Periksa tabel data aset, skor prioritas, kategori, peringkat, grafik, dan rekomendasi yang dihasilkan.
6. Unduh file CSV atau PNG yang dibutuhkan dari panel file Google Colab.
Library yang digunakan umumnya sudah tersedia di Google Colab. Jika dijalankan pada lingkungan lokal dan ada library yang belum tersedia, instal dengan:
pip install pandas numpy matplotlib seaborn
Batasan
- Data yang digunakan merupakan data sintetis/contoh, bukan data aset nyata.
- Bobot kriteria (50%, 30%, 20%) dan ambang kategori ditentukan sebagai asumsi demonstrasi.
- Skor kondisi diasumsikan semakin tinggi berarti kondisi aset semakin baik.
- Usia maksimum acuan ditetapkan 30 tahun untuk perhitungan skor usia.
- Hasil analisis tidak menggantikan inspeksi lapangan, standar teknis, penilaian ahli, atau pertimbangan anggaran.
- Sebelum digunakan untuk perencanaan nyata, kriteria, bobot, skala penilaian, dan rekomendasi perlu divalidasi oleh pihak yang berwenang.
Pengembangan Selanjutnya
Analisis dapat dikembangkan dengan:
- Mengganti data contoh dengan data aset dari sumber resmi.
- Menentukan bobot kriteria bersama ahli atau pemangku kepentingan.
- Menambahkan kriteria seperti biaya perbaikan, tingkat risiko, dampak terhadap masyarakat, dan riwayat kerusakan.
- Menguji hasil peringkat dengan data inspeksi atau keputusan pemeliharaan sebelumnya.
- Membuat dashboard agar hasil analisis lebih mudah dipantau.
Penggunaan
Notebook ini dibuat untuk keperluan pembelajaran dan demonstrasi analisis data. Jika dikembangkan lebih lanjut, dokumentasikan sumber dataset dan asumsi perhitungan yang digunakan.
