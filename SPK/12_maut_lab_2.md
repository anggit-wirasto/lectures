# Contoh Kasus MAUT: Memilih Rumah Sakit Terbaik untuk Operasi Jantung

## Data Alternatif dan Kriteria

| Rumah Sakit | Biaya (Rp juta) | Tingkat Keberhasilan (%) | Jarak (km) |
|-------------|------------------|-------------------------|------------|
| RS1         | 80               | 90                      | 10         |
| RS2         | 100              | 85                      | 5          |
| RS3         | 90               | 92                      | 15         |

## Bobot Kriteria

| Kriteria                  | Bobot |
|---------------------------|-------|
| Biaya                     | 0.3   |
| Tingkat Keberhasilan      | 0.5   |
| Jarak                     | 0.2   |

## Langkah-langkah MAUT dalam Excel

### Langkah 1: Normalisasi Matriks Keputusan

Untuk biaya dan jarak, nilai yang lebih rendah lebih baik, jadi kita menggunakan formula:

\[ \text{Normalized Value} = \frac{\text{Max Value} - \text{Value}}{\text{Max Value} - \text{Min Value}} \]

Untuk tingkat keberhasilan, nilai yang lebih tinggi lebih baik, jadi kita menggunakan formula:

\[ \text{Normalized Value} = \frac{\text{Value} - \text{Min Value}}{\text{Max Value} - \text{Min Value}} \]

### Rumus Excel untuk Normalisasi

1. **Norm Biaya**:
   - RS1: `=(MAX($B$2:$B$4)-B2)/(MAX($B$2:$B$4)-MIN($B$2:$B$4))`
   - RS2: `=(MAX($B$2:$B$4)-B3)/(MAX($B$2:$B$4)-MIN($B$2:$B$4))`
   - RS3: `=(MAX($B$2:$B$4)-B4)/(MAX($B$2:$B$4)-MIN($B$2:$B$4))`

2. **Norm Tingkat Keberhasilan**:
   - RS1: `=(C2-MIN($C$2:$C$4))/(MAX($C$2:$C$4)-MIN($C$2:$C$4))`
   - RS2: `=(C3-MIN($C$2:$C$4))/(MAX($C$2:$C$4)-MIN($C$2:$C$4))`
   - RS3: `=(C4-MIN($C$2:$C$4))/(MAX($C$2:$C$4)-MIN($C$2:$C$4))`

3. **Norm Jarak**:
   - RS1: `=(MAX($D$2:$D$4)-D2)/(MAX($D$2:$D$4)-MIN($D$2:$D$4))`
   - RS2: `=(MAX($D$2:$D$4)-D3)/(MAX($D$2:$D$4)-MIN($D$2:$D$4))`
   - RS3: `=(MAX($D$2:$D$4)-D4)/(MAX($D$2:$D$4)-MIN($D$2:$D$4))`

### Hasil Normalisasi

| Rumah Sakit | Biaya | Tingkat Keberhasilan | Jarak | Norm Biaya | Norm Tingkat Keberhasilan | Norm Jarak |
|-------------|-------|----------------------|-------|------------|---------------------------|------------|
| RS1         | 80    | 90                   | 10    | 1          | 0.714                     | 0.333      |
| RS2         | 100   | 85                   | 5     | 0          | 0.286                     | 1          |
| RS3         | 90    | 92                   | 15    | 0.5        | 1                         | 0          |

### Langkah 2: Menghitung Utility

| Rumah Sakit | Norm Biaya | Norm Tingkat Keberhasilan | Norm Jarak | Utility Biaya | Utility Tingkat Keberhasilan | Utility Jarak |
|-------------|------------|---------------------------|------------|---------------|------------------------------|---------------|
| RS1         | 1          | 0.714                     | 0.333      | 0.3           | 0.357                        | 0.067         |
| RS2         | 0          | 0.286                     | 1          | 0             | 0.143                        | 0.2           |
| RS3         | 0.5        | 1                         | 0          | 0.15          | 0.5                          | 0             |

### Langkah 3: Menghitung Total Utility

| Rumah Sakit | Utility Biaya | Utility Tingkat Keberhasilan | Utility Jarak | Total Utility |
|-------------|---------------|------------------------------|---------------|---------------|
| RS1         | 0.3           | 0.357                        | 0.067         | 0.724         |
| RS2         | 0             | 0.143                        | 0.2           | 0.343         |
| RS3         | 0.15          | 0.5                          | 0             | 0.65          |

### Langkah 4: Peringkat Alternatif

| Rumah Sakit | Total Utility | Peringkat |
|-------------|---------------|-----------|
| RS1         | 0.724         | 1         |
| RS3         | 0.65          | 2         |
| RS2         | 0.343         | 3         |

## Kesimpulan

Rumah Sakit RS1 dengan total utility tertinggi adalah pilihan terbaik berdasarkan kriteria yang telah ditentukan.

## Implementasi MAUT dalam Python

```python
import numpy as np
import pandas as pd

# Data alternatif dan kriteria
data = {
    'Rumah Sakit': ['RS1', 'RS2', 'RS3'],
    'Biaya': [80, 100, 90],
    'Tingkat Keberhasilan': [90, 85, 92],
    'Jarak': [10, 5, 15]
}

# Bobot kriteria
bobot = {
    'Biaya': 0.3,
    'Tingkat Keberhasilan': 0.5,
    'Jarak': 0.2
}

# Konversi ke DataFrame
df = pd.DataFrame(data)

# Normalisasi matriks keputusan
df['Norm Biaya'] = (df['Biaya'].max() - df['Biaya']) / (df['Biaya'].max() - df['Biaya'].min())
df['Norm Tingkat Keberhasilan'] = (df['Tingkat Keberhasilan'] - df['Tingkat Keberhasilan'].min()) / (df['Tingkat Keberhasilan'].max() - df['Tingkat Keberhasilan'].min())
df['Norm Jarak'] = (df['Jarak'].max() - df['Jarak']) / (df['Jarak'].max() - df['Jarak'].min())

# Hitung utility
df['Utility Biaya'] = df['Norm Biaya'] * bobot['Biaya']
df['Utility Tingkat Keberhasilan'] = df['Norm Tingkat Keberhasilan'] * bobot['Tingkat Keberhasilan']
df['Utility Jarak'] = df['Norm Jarak'] * bobot['Jarak']

# Hitung total utility
df['Total Utility'] = df['Utility Biaya'] + df['Utility Tingkat Keberhasilan'] + df['Utility Jarak']

# Peringkat alternatif
df['Peringkat'] = df['Total Utility'].rank(ascending=False)

# Tampilkan hasil
print(df[['Rumah Sakit', 'Total Utility', 'Peringkat']])
