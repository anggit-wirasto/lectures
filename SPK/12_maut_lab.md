# Memilih Laptop Terbaik untuk Keperluan Bisnis Menggunakan Metode MAUT

## Pendahuluan

Metode MAUT (Multi-Attribute Utility Theory) digunakan untuk mengevaluasi dan membandingkan alternatif berdasarkan beberapa atribut atau kriteria. Dalam kasus ini, kita akan memilih laptop terbaik untuk keperluan bisnis berdasarkan tiga kriteria: Harga, Kinerja, dan Daya Tahan Baterai.

## Kriteria dan Bobot

Kriteria yang digunakan dan bobotnya adalah sebagai berikut:
- Harga: 0.4
- Kinerja: 0.3
- Daya Tahan Baterai: 0.3

## Data Alternatif

| Alternatif | Harga (Rp juta) | Kinerja (1-10) | Daya Tahan Baterai (jam) |
|------------|-----------------|----------------|--------------------------|
| A1         | 15              | 8              | 10                       |
| A2         | 20              | 9              | 8                        |
| A3         | 18              | 7              | 9                        |

## Langkah-langkah MAUT

### 1. Normalisasi Matriks Keputusan

Normalisasi dilakukan dengan metode min-max:
\[ \text{Normalized Value} = \frac{\text{Value} - \text{Min Value}}{\text{Max Value} - \text{Min Value}} \]

### 2. Menghitung Utility

Nilai utility untuk setiap alternatif dan kriteria dihitung sebagai berikut:

| Alternatif | Harga | Kinerja | Daya Tahan Baterai | Norm Harga | Norm Kinerja | Norm Baterai | Utility Harga | Utility Kinerja | Utility Baterai | Total Utility |
|------------|-------|---------|--------------------|------------|--------------|--------------|---------------|-----------------|-----------------|---------------|
| A1         | 15    | 8       | 10                 | 1          | 0.5          | 1            | 0.4           | 0.15            | 0.3             | 0.85          |
| A2         | 20    | 9       | 8                  | 0          | 1            | 0            | 0             | 0.3             | 0               | 0.30          |
| A3         | 18    | 7       | 9                  | 0.4        | 0            | 0.5          | 0.16          | 0               | 0.15            | 0.31          |

### 3. Peringkat Alternatif

Berdasarkan total utility, peringkat alternatif adalah sebagai berikut:

| Alternatif | Total Utility | Peringkat |
|------------|---------------|-----------|
| A1         | 0.85          | 1         |
| A3         | 0.31          | 2         |
| A2         | 0.30          | 3         |

## Kesimpulan

Laptop A1 dengan total utility tertinggi adalah pilihan terbaik berdasarkan kriteria yang telah ditentukan.

## Implementasi dalam Excel

Berikut adalah langkah-langkah untuk mengimplementasikan perhitungan ini dalam Excel:

1. **Buat Tabel Data Alternatif dan Kriteria:**

    | Alternatif | Harga | Kinerja | Daya Tahan Baterai |
    |------------|-------|---------|--------------------|
    | A1         | 15    | 8       | 10                 |
    | A2         | 20    | 9       | 8                  |
    | A3         | 18    | 7       | 9                  |

2. **Buat Tabel Bobot Kriteria:**

    | Kriteria             | Bobot |
    |----------------------|-------|
    | Harga                | 0.4   |
    | Kinerja              | 0.3   |
    | Daya Tahan Baterai   | 0.3   |

3. **Normalisasi Matriks Keputusan:**

    | Alternatif | Harga | Kinerja | Daya Tahan Baterai | Norm Harga | Norm Kinerja | Norm Baterai |
    |------------|-------|---------|--------------------|------------|--------------|--------------|
    | A1         | 15    | 8       | 10                 | = (B2-MIN($B$2:$B$4))/(MAX($B$2:$B$4)-MIN($B$2:$B$4)) | = (C2-MIN($C$2:$C$4))/(MAX($C$2:$C$4)-MIN($C$2:$C$4)) | = (D2-MIN($D$2:$D$4))/(MAX($D$2:$D$4)-MIN($D$2:$D$4)) |
    | A2         | 20    | 9       | 8                  | = (B3-MIN($B$2:$B$4))/(MAX($B$2:$B$4)-MIN($B$2:$B$4)) | = (C3-MIN($C$2:$C$4))/(MAX($C$2:$C$4)-MIN($C$2:$C$4)) | = (D3-MIN($D$2:$D$4))/(MAX($D$2:$D$4)-MIN($D$2:$D$4)) |
    | A3         | 18    | 7       | 9                  | = (B4-MIN($B$2:$B$4))/(MAX($B$2:$B$4)-MIN($B$2:$B$4)) | = (C4-MIN($C$2:$C$4))/(MAX($C$2:$C$4)-MIN($C$2:$C$4)) | = (D4-MIN($D$2:$D$4))/(MAX($D$2:$D$4)-MIN($D$2:$D$4)) |

4. **Hitung Utility:**

    | Alternatif | Harga | Kinerja | Daya Tahan Baterai | Norm Harga | Norm Kinerja | Norm Baterai | Utility Harga | Utility Kinerja | Utility Baterai |
    |------------|-------|---------|--------------------|------------|--------------|--------------|---------------|-----------------|-----------------|
    | A1         | 15    | 8       | 10                 | 1          | 0.5          | 1            | =H2*$G$2      | =I2*$G$3        | =J2*$G$4        |
    | A2         | 20    | 9       | 8                  | 0          | 1            | 0            | =H3*$G$2      | =I3*$G$3        | =J3*$G$4        |
    | A3         | 18    | 7       | 9                  | 0.4        | 0            | 0.5          | =H4*$G$2      | =I4*$G$3        | =J4*$G$4        |

5. **Hitung Total Utility:**

    | Alternatif | Harga | Kinerja | Daya Tahan Baterai | Norm Harga | Norm Kinerja | Norm Baterai | Utility Harga | Utility Kinerja | Utility Baterai | Total Utility |
    |------------|-------|---------|--------------------|------------|--------------|--------------|---------------|-----------------|-----------------|---------------|
    | A1         | 15    | 8       | 10                 | 1          | 0.5          | 1            | 0.4           | 0.15            | 0.3             | =K2+L2+M2     |
    | A2         | 20    | 9       | 8                  | 0          | 1            | 0            | 0             | 0.3             | 0               | =K3+L3+M3     |
    | A3         | 18    | 7       | 9                  | 0.4        | 0            | 0.5          | 0.16          | 0               | 0.15            | =K4+L4+M4     |

6. **Peringkat Alternatif:**

    | Alternatif | Total Utility | Peringkat |
    |------------|---------------|-----------|
    | A1         | 0.85          | 1         |
    | A3         | 0.31          | 2         |
    | A2         | 0.30          | 3         |

Dengan langkah-langkah di atas, Anda dapat menentukan laptop terbaik menggunakan metode MAUT dalam Excel.
