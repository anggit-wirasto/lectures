# Metode MAUT untuk Pengambilan Keputusan

## Pengenalan
Multi-Attribute Utility Theory (MAUT) adalah salah satu metode pengambilan keputusan multikriteria yang digunakan untuk mengevaluasi dan membandingkan beberapa alternatif berdasarkan beberapa atribut atau kriteria. Metode ini didasarkan pada konsep utilitas, yang mengukur kepuasan atau preferensi pengambil keputusan terhadap berbagai alternatif yang ada.

## Komponen Utama MAUT

1. **Alternatif**: Alternatif adalah opsi atau pilihan yang tersedia untuk pengambilan keputusan. Dalam konteks MAUT, setiap alternatif dievaluasi berdasarkan sejumlah kriteria.
2. **Kriteria**: Kriteria adalah atribut atau faktor yang digunakan untuk mengevaluasi alternatif. Kriteria ini bisa bersifat kuantitatif maupun kualitatif.
3. **Bobot Kriteria**: Bobot diberikan pada setiap kriteria untuk mencerminkan pentingnya kriteria tersebut dalam proses pengambilan keputusan. Bobot ini biasanya dinyatakan dalam bentuk persentase atau nilai numerik.
4. **Fungsi Utilitas**: Fungsi utilitas adalah fungsi matematika yang mengukur tingkat kepuasan atau preferensi terhadap nilai kriteria tertentu. Fungsi ini membantu dalam mengubah nilai asli dari kriteria ke dalam skala utilitas yang seragam.
5. **Total Utilitas**: Total utilitas adalah nilai agregat yang diperoleh dari menjumlahkan utilitas masing-masing kriteria yang telah dikalikan dengan bobotnya. Nilai total utilitas digunakan untuk menentukan peringkat alternatif.


## Langkah-langkah MAUT

1. **Identifikasi Kriteria dan Alternatif:**
   - Tentukan kriteria yang relevan untuk pengambilan keputusan.
   - Identifikasi alternatif yang akan dievaluasi.

2. **Penentuan Bobot Kriteria:**
   - Tentukan bobot untuk masing-masing kriteria berdasarkan tingkat kepentingannya.
   - Bobot biasanya dinyatakan dalam bentuk angka, di mana jumlah total bobot adalah 1 atau 100%.

3. **Normalisasi Matriks Keputusan:**
   - Normalisasi dilakukan untuk mengubah nilai kriteria ke dalam skala yang sama.
   - Salah satu metode normalisasi adalah menggunakan skala 0-1 atau 0-100.

4. **Penghitungan Utility:**
   - Hitung nilai utility untuk setiap alternatif berdasarkan masing-masing kriteria.
   - Utility adalah ukuran preferensi untuk nilai suatu kriteria, biasanya dinyatakan dalam skala 0-1.

5. **Penghitungan Total Utility:**
   - Hitung total utility untuk setiap alternatif dengan menjumlahkan utility yang sudah dikalikan dengan bobot kriteria masing-masing.
   - Total utility menunjukkan seberapa baik suatu alternatif memenuhi semua kriteria yang telah ditentukan.

6. **Peringkat Alternatif:**
   - Peringkatkan alternatif berdasarkan total utility yang dihitung.
   - Alternatif dengan total utility tertinggi dianggap sebagai alternatif terbaik.

## Penentuan Bobot dalam Metode MAUT

Penentuan bobot kriteria merupakan langkah penting dalam metode MAUT karena bobot ini mencerminkan tingkat kepentingan masing-masing kriteria dalam pengambilan keputusan. Berikut adalah beberapa pendekatan yang umum digunakan untuk menentukan bobot kriteria:

### 1. Pendekatan Subjektif

#### A. Pembobotan Langsung
Pengambil keputusan secara langsung menetapkan bobot untuk setiap kriteria berdasarkan penilaian subjektif mereka tentang pentingnya masing-masing kriteria. Jumlah total bobot harus sama dengan 1 (atau 100%).

#### B. Teknik AHP (Analytic Hierarchy Process)
Pendekatan ini melibatkan pengambil keputusan dalam proses berpasangan untuk membandingkan pentingnya masing-masing kriteria. Berikut adalah langkah-langkah umum dalam AHP:
   1. Buat matriks perbandingan berpasangan untuk kriteria.
   2. Isi matriks dengan perbandingan berpasangan yang menunjukkan seberapa penting satu kriteria dibandingkan dengan kriteria lainnya.
   3. Hitung bobot relatif untuk setiap kriteria dengan menggunakan metode eigenvector atau rata-rata geometrik.
   4. Normalisasi bobot sehingga jumlah totalnya sama dengan 1.

### 2. Pendekatan Objektif

#### A. Metode Entropi
Metode entropi digunakan untuk menentukan bobot berdasarkan variasi data dari setiap kriteria. Langkah-langkahnya adalah sebagai berikut:
   1. Normalisasi data kriteria.
   2. Hitung nilai entropi untuk setiap kriteria.
   3. Tentukan derajat divergensi dari setiap kriteria.
   4. Hitung bobot kriteria berdasarkan derajat divergensi.

### 3. Pendekatan Kombinasi

Pengambil keputusan dapat menggunakan kombinasi dari pendekatan subjektif dan objektif untuk menentukan bobot kriteria. Contohnya, mereka bisa menggunakan AHP untuk mendapatkan bobot awal dan kemudian mengkalibrasinya dengan menggunakan metode entropi.

### Contoh Penentuan Bobot dengan AHP

Misalkan ada tiga kriteria: Biaya, Kinerja, dan Daya Tahan. Pengambil keputusan melakukan perbandingan berpasangan dan menghasilkan matriks berikut:

| Kriteria     | Biaya | Kinerja | Daya Tahan |
|--------------|-------|---------|------------|
| Biaya        | 1     | 1/3     | 1/5        |
| Kinerja      | 3     | 1       | 1/2        |
| Daya Tahan   | 5     | 2       | 1          |

- Setiap elemen di matriks ini menunjukkan preferensi relatif antara dua kriteria.
- Nilai `1` di diagonal utama (Biaya vs. Biaya, Kinerja vs. Kinerja, Daya Tahan vs. Daya Tahan) menunjukkan bahwa setiap kriteria dibandingkan dengan dirinya sendiri memiliki nilai yang sama.
- Nilai `1/3` di baris Biaya dan kolom Kinerja menunjukkan bahwa Biaya dianggap kurang penting dibandingkan Kinerja.
- Nilai `3` di baris Kinerja dan kolom Biaya menunjukkan bahwa Kinerja dianggap tiga kali lebih penting dibandingkan Biaya.
- Nilai `1/5` di baris Biaya dan kolom Daya Tahan menunjukkan bahwa Biaya dianggap jauh kurang penting dibandingkan Daya Tahan.
- Nilai `5` di baris Daya Tahan dan kolom Biaya menunjukkan bahwa Daya Tahan dianggap lima kali lebih penting dibandingkan Biaya.

### Langkah 2: Jumlahkan Setiap Kolom

Hitung jumlah setiap kolom di matriks:

| Kriteria         | Biaya | Kinerja | Daya Tahan |
|------------------|-------|---------|------------|
| **Jumlah Kolom** | 9     | 3.333   | 1.7        |

Cara menghitung:
- **Jumlah kolom Biaya**: $$\(1 + 3 + 5 = 9\)$$
- **Jumlah kolom Kinerja**: $$\( \frac{1}{3} + 1 + 2 = 3.333 \)$$
- **Jumlah kolom Daya Tahan**: $$\( \frac{1}{5} + \frac{1}{2} + 1 = 1.7 \)$$

### Langkah 3: Normalisasi Matriks

Normalisasi dilakukan dengan membagi setiap elemen matriks dengan jumlah kolomnya masing-masing:

| Kriteria     | Biaya   | Kinerja | Daya Tahan |
|--------------|---------|---------|------------|
| **Biaya**    | 0.111   | 0.1     | 0.117      |
| **Kinerja**  | 0.333   | 0.3     | 0.294      |
| **Daya Tahan**| 0.556   | 0.6     | 0.588      |

Cara menghitung:
- **Biaya vs. Biaya**: $$\( \frac{1}{9} = 0.111 \)$$
- **Biaya vs. Kinerja**: $$\( \frac{1/3}{3.333} = 0.1 \)$$
- **Biaya vs. Daya Tahan**: $$\( \frac{1/5}{1.7} = 0.117 \)$$
- **Kinerja vs. Biaya**: $$\( \frac{3}{9} = 0.333 \)$$
- **Kinerja vs. Kinerja**: $$\( \frac{1}{3.333} = 0.3 \)$$
- **Kinerja vs. Daya Tahan**: $$\( \frac{1/2}{1.7} = 0.294 \)$$
- **Daya Tahan vs. Biaya**: $$\( \frac{5}{9} = 0.556 \)$$
- **Daya Tahan vs. Kinerja**: $$\( \frac{2}{3.333} = 0.6 \)$$
- **Daya Tahan vs. Daya Tahan**: $$\( \frac{1}{1.7} = 0.588 \)$$

### Langkah 4: Hitung Rata-rata Setiap Baris

Hitung rata-rata dari setiap baris yang telah dinormalisasi untuk mendapatkan bobot kriteria:

| Kriteria   | Bobot  |
|------------|--------|
| **Biaya**      | 0.109  |
| **Kinerja**    | 0.309  |
| **Daya Tahan** | 0.582  |

Cara menghitung:
- **Biaya**: $$\( \frac{0.111 + 0.1 + 0.117}{3} = 0.109 \)$$
- **Kinerja**: $$\( \frac{0.333 + 0.3 + 0.294}{3} = 0.309 \)$$
- **Daya Tahan**: $$\( \frac{0.556 + 0.6 + 0.588}{3} = 0.582 \)$$

### Kesimpulan

Bobot kriteria yang diperoleh dari perbandingan berpasangan adalah:

| Kriteria   | Bobot  |
|------------|--------|
| Biaya      | 0.109  |
| Kinerja    | 0.309  |
| Daya Tahan | 0.582  |

### Kesimpulan

Penentuan bobot dalam metode MAUT sangat penting karena mempengaruhi hasil akhir dari proses pengambilan keputusan. Dengan memilih pendekatan yang tepat untuk menentukan bobot, pengambil keputusan dapat memastikan bahwa kriteria yang paling penting mendapatkan perhatian yang sesuai dalam evaluasi alternatif.


## Kelebihan dan Kekurangan MAUT

### Kelebihan

1. **Pendekatan Sistematis dan Terstruktur**:
   - MAUT menyediakan pendekatan yang sistematis dan terstruktur untuk mengevaluasi dan membandingkan alternatif berdasarkan beberapa kriteria.

2. **Penggabungan Kriteria yang Berbeda**:
   - Memungkinkan penggabungan berbagai jenis kriteria, baik kuantitatif maupun kualitatif, sehingga memberikan fleksibilitas dalam pengambilan keputusan.

3. **Pengambilan Keputusan yang Transparan**:
   - Dengan menggunakan bobot dan fungsi utilitas yang jelas, proses pengambilan keputusan menjadi lebih transparan dan dapat dipertanggungjawabkan.

4. **Fleksibilitas dalam Penentuan Bobot**:
   - Pengambil keputusan dapat menentukan bobot kriteria sesuai dengan preferensi dan prioritas mereka, memberikan fleksibilitas yang lebih besar.

5. **Dapat Digunakan dalam Berbagai Konteks**:
   - MAUT dapat diterapkan dalam berbagai konteks, termasuk bisnis, kesehatan, dan manajemen proyek, membuatnya menjadi alat yang serbaguna.

### Kekurangan

1. **Subjektivitas dalam Penentuan Bobot**:
   - Penentuan bobot kriteria bisa subjektif dan sangat bergantung pada preferensi pengambil keputusan, yang dapat mempengaruhi hasil akhir.

2. **Normalisasi Data yang Rumit**:
   - Membutuhkan normalisasi data, yang bisa menjadi rumit jika kriteria memiliki skala pengukuran yang sangat berbeda.

3. **Kesulitan dalam Menentukan Fungsi Utilitas**:
   - Menentukan fungsi utilitas yang tepat untuk setiap kriteria bisa sulit dan mungkin tidak selalu mencerminkan preferensi sebenarnya dari pengambil keputusan.

4. **Ketergantungan pada Data yang Akurat**:
   - Hasil MAUT sangat bergantung pada keakuratan data yang digunakan. Data yang tidak akurat atau tidak lengkap dapat mengarah pada keputusan yang salah.

5. **Memerlukan Perhitungan yang Kompleks**:
   - Proses perhitungan utilitas dan total utilitas bisa menjadi kompleks, terutama jika melibatkan banyak kriteria dan alternatif.


## Contoh Kasus

Misalkan kita memiliki tiga alternatif (A1, A2, A3) dan tiga kriteria (C1, C2, C3) dengan bobot masing-masing 0.4, 0.3, dan 0.3. Berikut adalah tabel nilai alternatif untuk setiap kriteria:

| Alternatif | C1 | C2 | C3 |
|------------|----|----|----|
| A1         | 8  | 7  | 9  |
| A2         | 6  | 9  | 8  |
| A3         | 7  | 6  | 7  |

### Langkah 1: Normalisasi Matriks Keputusan

Normalisasi dapat dilakukan dengan metode min-max atau lainnya. Misalkan kita gunakan min-max:

$$\[ \text{Normalized Value} = \frac{\text{Value} - \text{Min Value}}{\text{Max Value} - \text{Min Value}} \]$$

### Langkah 2: Menghitung Utility

Setelah normalisasi, kita hitung nilai utility untuk masing-masing alternatif dan kriteria.

### Langkah 3: Menghitung Total Utility

Total utility untuk setiap alternatif dihitung dengan formula:

$$\[ \text{Total Utility} = (U1 \times W1) + (U2 \times W2) + (U3 \times W3) \]$$

### Langkah 4: Peringkat Alternatif

Alternatif dengan nilai total utility tertinggi adalah alternatif terbaik.

## Implementasi dalam Python

Berikut adalah contoh implementasi sederhana dalam Python:

```python
import numpy as np

# Data input
alternatives = np.array([[8, 7, 9], [6, 9, 8], [7, 6, 7]])
weights = np.array([0.4, 0.3, 0.3])

# Normalisasi menggunakan metode min-max
norm_alternatives = (alternatives - alternatives.min(axis=0)) / (alternatives.max(axis=0) - alternatives.min(axis=0))

# Menghitung utility
utility = norm_alternatives * weights

# Menghitung total utility untuk setiap alternatif
total_utility = utility.sum(axis=1)

# Peringkat alternatif
rankings = np.argsort(total_utility)[::-1]

print("Peringkat Alternatif: ", rankings + 1)  # +1 karena indeks mulai dari 0
