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

## Langkah-langkah MAUT Menggunakan Excel

## Langkah 1: Normalisasi Matriks Keputusan

### Rumus Excel untuk Normalisasi

Untuk harga, nilai yang lebih rendah lebih baik, jadi kita menggunakan formula:

\[ \text{Normalized Value} = \frac{\text{Max Value} - \text{Value}}{\text{Max Value} - \text{Min Value}} \]

Untuk kinerja dan daya tahan baterai, nilai yang lebih tinggi lebih baik, jadi kita menggunakan formula:

\[ \text{Normalized Value} = \frac{\text{Value} - \text{Min Value}}{\text{Max Value} - \text{Min Value}} \]

### Excel Formula untuk Normalisasi

1. **Norm Harga**:
   - A1: `=(MAX($B$2:$B$4)-B2)/(MAX($B$2:$B$4)-MIN($B$2:$B$4))`
   - A2: `=(MAX($B$2:$B$4)-B3)/(MAX($B$2:$B$4)-MIN($B$2:$B$4))`
   - A3: `=(MAX($B$2:$B$4)-B4)/(MAX($B$2:$B$4)-MIN($B$2:$B$4))`

2. **Norm Kinerja**:
   - A1: `=(C2-MIN($C$2:$C$4))/(MAX($C$2:$C$4)-MIN($C$2:$C$4))`
   - A2: `=(C3-MIN($C$2:$C$4))/(MAX($C$2:$C$4)-MIN($C$2:$C$4))`
   - A3: `=(C4-MIN($C$2:$C$4))/(MAX($C$2:$C$4)-MIN($C$2:$C$4))`

3. **Norm Daya Tahan Baterai**:
   - A1: `=(D2-MIN($D$2:$D$4))/(MAX($D$2:$D$4)-MIN($D$2:$D$4))`
   - A2: `=(D3-MIN($D$2:$D$4))/(MAX($D$2:$D$4)-MIN($D$2:$D$4))`
   - A3: `=(D4-MIN($D$2:$D$4))/(MAX($D$2:$D$4)-MIN($D$2:$D$4))`

### Hasil Normalisasi

| Alternatif | Harga | Kinerja | Daya Tahan Baterai | Norm Harga | Norm Kinerja | Norm Baterai |
|------------|-------|---------|--------------------|------------|--------------|--------------|
| A1         | 15    | 8       | 10                 | 1          | 0.5          | 1            |
| A2         | 20    | 9       | 8                  | 0          | 1            | 0            |
| A3         | 18    | 7       | 9                  | 0.4        | 0            | 0.5          |

## Langkah 2: Menghitung Utility

### Excel Formula untuk Utility

1. **Utility Harga**:
   - A1: `=H2 * $G$2`
   - A2: `=H3 * $G$2`
   - A3: `=H4 * $G$2`

2. **Utility Kinerja**:
   - A1: `=I2 * $G$3`
   - A2: `=I3 * $G$3`
   - A3: `=I4 * $G$3`

3. **Utility Baterai**:
   - A1: `=J2 * $G$4`
   - A2: `=J3 * $G$4`
   - A3: `=J4 * $G$4`

### Hasil Utility

| Alternatif | Harga | Kinerja | Daya Tahan Baterai | Norm Harga | Norm Kinerja | Norm Baterai | Utility Harga | Utility Kinerja | Utility Baterai |
|------------|-------|---------|--------------------|------------|--------------|--------------|---------------|-----------------|-----------------|
| A1         | 15    | 8       | 10                 | 1          | 0.5          | 1            | 0.4           | 0.15            | 0.3             |
| A2         | 20    | 9       | 8                  | 0          | 1            | 0            | 0             | 0.3             | 0               |
| A3         | 18    | 7       | 9                  | 0.4        | 0            | 0.5          | 0.16          | 0               | 0.15            |

## Langkah 3: Menghitung Total Utility

### Excel Formula untuk Total Utility

1. **Total Utility**:
   - A1: `=K2 + L2 + M2`
   - A2: `=K3 + L3 + M3`
   - A3: `=K4 + L4 + M4`

### Hasil Total Utility

| Alternatif | Total Utility |
|------------|---------------|
| A1         | 0.85          |
| A2         | 0.30          |
| A3         | 0.31          |

## Peringkat Alternatif

| Alternatif | Total Utility | Peringkat |
|------------|---------------|-----------|
| A1         | 0.85          | 1         |
| A3         | 0.31          | 2         |
| A2         | 0.30          | 3         |

## Kesimpulan

Laptop A1 dengan total utility tertinggi adalah pilihan terbaik berdasarkan kriteria yang telah ditentukan.


## Implementasi MAUT dalam Python

### Langkah 1: Normalisasi Matriks Keputusan

Untuk harga, nilai yang lebih rendah lebih baik, jadi kita menggunakan formula:
\[ \text{Normalized Value} = \frac{\text{Max Value} - \text{Value}}{\text{Max Value} - \text{Min Value}} \]

Untuk kinerja dan daya tahan baterai, nilai yang lebih tinggi lebih baik, jadi kita menggunakan formula:
\[ \text{Normalized Value} = \frac{\text{Value} - \text{Min Value}}{\text{Max Value} - \text{Min Value}} \]

### Langkah 2: Menghitung Utility

Utility dihitung dengan mengalikan nilai normalisasi dengan bobot kriteria.

### Langkah 3: Menghitung Total Utility

Total utility untuk setiap alternatif dihitung dengan menjumlahkan utility dari setiap kriteria.

### Langkah 4: Peringkat Alternatif

Alternatif diurutkan berdasarkan total utility.

### Kode Python

```python
import numpy as np
import pandas as pd

# Data alternatif dan kriteria
data = {
    'Alternatif': ['A1', 'A2', 'A3'],
    'Harga': [15, 20, 18],
    'Kinerja': [8, 9, 7],
    'Daya Tahan Baterai': [10, 8, 9]
}

# Bobot kriteria
bobot = {
    'Harga': 0.4,
    'Kinerja': 0.3,
    'Daya Tahan Baterai': 0.3
}

# Konversi ke DataFrame
df = pd.DataFrame(data)

# Normalisasi matriks keputusan
df['Norm Harga'] = (df['Harga'].max() - df['Harga']) / (df['Harga'].max() - df['Harga'].min())
df['Norm Kinerja'] = (df['Kinerja'] - df['Kinerja'].min()) / (df['Kinerja'].max() - df['Kinerja'].min())
df['Norm Daya Tahan Baterai'] = (df['Daya Tahan Baterai'] - df['Daya Tahan Baterai'].min()) / (df['Daya Tahan Baterai'].max() - df['Daya Tahan Baterai'].min())

# Hitung utility
df['Utility Harga'] = df['Norm Harga'] * bobot['Harga']
df['Utility Kinerja'] = df['Norm Kinerja'] * bobot['Kinerja']
df['Utility Daya Tahan Baterai'] = df['Norm Daya Tahan Baterai'] * bobot['Daya Tahan Baterai']

# Hitung total utility
df['Total Utility'] = df['Utility Harga'] + df['Utility Kinerja'] + df['Utility Daya Tahan Baterai']

# Peringkat alternatif
df['Peringkat'] = df['Total Utility'].rank(ascending=False)

# Tampilkan hasil
print(df[['Alternatif', 'Total Utility', 'Peringkat']])
