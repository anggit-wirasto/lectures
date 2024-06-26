# Implementasi MAUT dalam Python

MAUT, atau Multi-Attribute Utility Theory, adalah salah satu metode pengambilan keputusan multikriteria yang digunakan untuk mengevaluasi dan membandingkan alternatif berdasarkan beberapa atribut atau kriteria. Berikut adalah langkah-langkah umum dalam menggunakan metode MAUT:

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

## Contoh Kasus

Misalkan kita memiliki tiga alternatif (A1, A2, A3) dan tiga kriteria (C1, C2, C3) dengan bobot masing-masing 0.4, 0.3, dan 0.3. Berikut adalah tabel nilai alternatif untuk setiap kriteria:

| Alternatif | C1 | C2 | C3 |
|------------|----|----|----|
| A1         | 8  | 7  | 9  |
| A2         | 6  | 9  | 8  |
| A3         | 7  | 6  | 7  |

### Langkah 1: Normalisasi Matriks Keputusan

Normalisasi dapat dilakukan dengan metode min-max atau lainnya. Misalkan kita gunakan min-max:

\[ \text{Normalized Value} = \frac{\text{Value} - \text{Min Value}}{\text{Max Value} - \text{Min Value}} \]

### Langkah 2: Menghitung Utility

Setelah normalisasi, kita hitung nilai utility untuk masing-masing alternatif dan kriteria.

### Langkah 3: Menghitung Total Utility

Total utility untuk setiap alternatif dihitung dengan formula:

\[ \text{Total Utility} = (U1 \times W1) + (U2 \times W2) + (U3 \times W3) \]

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
