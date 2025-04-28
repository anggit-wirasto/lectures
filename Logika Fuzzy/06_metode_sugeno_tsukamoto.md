# Materi Kuliah: Logika Fuzzy
## Topik: Metode Sugeno dan Tsukamoto

---

## 1. Pendahuluan

Logika fuzzy adalah perluasan dari logika Boolean yang memungkinkan nilai kebenaran berada dalam rentang kontinu antara 0 dan 1. Ini sangat berguna untuk memodelkan ketidakpastian dan ambiguitas dunia nyata.

Dalam sistem inferensi fuzzy, dua metode yang banyak digunakan untuk menghasilkan output adalah **Metode Sugeno** dan **Metode Tsukamoto**.

Pada sesi ini, kita akan membahas kedua metode tersebut secara rinci.

---

## 2. Metode Sugeno

### 2.1 Definisi

Metode Sugeno, atau **Takagi-Sugeno-Kang (TSK)**, adalah metode inferensi fuzzy di mana **konsekuen** dari aturan berbentuk fungsi linear (atau konstan) dari input.

Bentuk umum aturan Sugeno:
- Jika `x` adalah `A1` dan `y` adalah `B1`, maka `z = f1(x,y)`
- Jika `x` adalah `A2` dan `y` adalah `B2`, maka `z = f2(x,y)`

Output sistem dihitung menggunakan **weighted average** dari hasil setiap aturan.

### 2.2 Tahapan Metode Sugeno

1. **Fuzzifikasi** input ke dalam derajat keanggotaan.
2. **Evaluasi aturan** berdasarkan operator fuzzy (misal min untuk AND).
3. **Hitung output** tiap aturan menggunakan fungsi konsekuen.
4. **Agregasi output** menggunakan rata-rata berbobot.

### 2.3 Contoh Soal Sugeno

**Kasus:**
Sebuah sistem kontrol kendaraan menggunakan dua input:
- `Kecepatan` (km/jam): Lambat, Cepat
- `Jarak` ke mobil depan (m): Dekat, Jauh

Output: Percepatan (`z`) dalam m/s^2.

Aturan:
- R1: Jika Kecepatan **Lambat** dan Jarak **Dekat**, maka `z = 0`
- R2: Jika Kecepatan **Cepat** dan Jarak **Dekat**, maka `z = -2`
- R3: Jika Kecepatan **Lambat** dan Jarak **Jauh**, maka `z = 2`
- R4: Jika Kecepatan **Cepat** dan Jarak **Jauh**, maka `z = 1`

**Diketahui:**
- Kecepatan = 70 km/jam
- Jarak = 15 m

**Langkah 1:** Tentukan derajat keanggotaan.

Misal:
- Kecepatan 70 km/jam:
  - Lambat: 0.2
  - Cepat: 0.8
- Jarak 15 m:
  - Dekat: 0.7
  - Jauh: 0.3

**Langkah 2:** Hitung firing strength tiap aturan (AND = min).

- R1: min(0.2, 0.7) = 0.2
- R2: min(0.8, 0.7) = 0.7
- R3: min(0.2, 0.3) = 0.2
- R4: min(0.8, 0.3) = 0.3

**Langkah 3:** Hitung output.

Weighted output:
\[
\text{Output} = \frac{\sum (\text{firing strength} \times \text{konsekuen})}{\sum (\text{firing strength})}
\]

\[
\text{Output} = \frac{(0.2 \times 0) + (0.7 \times -2) + (0.2 \times 2) + (0.3 \times 1)}{0.2+0.7+0.2+0.3}
= \frac{-1.4 + 0.4 + 0.3}{1.4} = \frac{-0.7}{1.4} = -0.5 \text{ m/s}^2
\]

**Hasil:** Percepatan -0.5 m/s^2.

---

## 3. Metode Tsukamoto

### 3.1 Definisi

Metode Tsukamoto menggunakan aturan fuzzy di mana konsekuen adalah himpunan fuzzy dengan fungsi keanggotaan **monoton** (naik atau turun).

Ciri khas metode ini adalah:
- Setiap output dari aturan adalah nilai crisp.
- Agregasi menggunakan rata-rata berbobot dari semua output aturan.

### 3.2 Tahapan Metode Tsukamoto

1. **Fuzzifikasi** input.
2. **Evaluasi aturan** dan tentukan derajat keanggotaan.
3. **Inferensikan** nilai output crisp berdasarkan konsekuen.
4. **Agregasikan** output dengan rata-rata berbobot.

### 3.3 Contoh Soal Tsukamoto

**Kasus:**
Input:
- `Pendapatan` (Rendah, Tinggi)
- `Harga Rumah` (Murah, Mahal)

Output: `Kelayakan Kredit` (layak 0-1).

Aturan:
- R1: Jika Pendapatan **Rendah** dan Harga Rumah **Murah**, maka Kelayakan **Turun**.
- R2: Jika Pendapatan **Tinggi** dan Harga Rumah **Mahal**, maka Kelayakan **Naik**.

**Diketahui:**
- Pendapatan = 6 juta
- Harga Rumah = 500 juta

**Langkah 1:** Hitung derajat keanggotaan.

Misal:
- Pendapatan 6 juta:
  - Rendah: 0.4
  - Tinggi: 0.6
- Harga 500 juta:
  - Murah: 0.5
  - Mahal: 0.5

**Langkah 2:** Hitung firing strength.

- R1: min(0.4, 0.5) = 0.4
- R2: min(0.6, 0.5) = 0.5

**Langkah 3:** Tentukan z untuk tiap aturan.

Misal:
- Fungsi "Turun" adalah monoton menurun dari 1 ke 0.
- Fungsi "Naik" adalah monoton naik dari 0 ke 1.

Cari nilai z1 dan z2 sesuai keanggotaan:

- Untuk R1 (Turun), \( \mu_{Turun}(z_1) = 0.4 \) -> z1 = 0.6
- Untuk R2 (Naik), \( \mu_{Naik}(z_2) = 0.5 \) -> z2 = 0.5

**Langkah 4:** Agregasi.

\[
Kelayakan = \frac{(0.4 \times 0.6) + (0.5 \times 0.5)}{0.4 + 0.5} = \frac{0.24+0.25}{0.9} = \frac{0.49}{0.9} \approx 0.544
\]

**Hasil:** Kelayakan Kredit 0.544

---

## 4. Contoh Kode Jupyter Notebook

Berikut contoh implementasi sederhana metode Sugeno dan Tsukamoto menggunakan Python (tanpa library fuzzy khusus):

```python
# Implementasi sederhana metode Sugeno dan Tsukamoto

# Fungsi Sugeno sederhana

def sugeno_inference(input_kecepatan, input_jarak):
    # Membership
    lambat = max(0, min(1, (80 - input_kecepatan) / 40))  # linear dari 40-80
    cepat = max(0, min(1, (input_kecepatan - 40) / 40))
    dekat = max(0, min(1, (30 - input_jarak) / 20))
    jauh = max(0, min(1, (input_jarak - 10) / 20))

    # Firing strength
    w1 = min(lambat, dekat)
    w2 = min(cepat, dekat)
    w3 = min(lambat, jauh)
    w4 = min(cepat, jauh)

    # Konsekuen
    z1, z2, z3, z4 = 0, -2, 2, 1

    # Weighted average
    output = (w1*z1 + w2*z2 + w3*z3 + w4*z4) / (w1+w2+w3+w4)
    return output

# Fungsi Tsukamoto sederhana

def tsukamoto_inference(input_pendapatan, input_harga):
    # Membership
    rendah = max(0, min(1, (8 - input_pendapatan) / 4))
    tinggi = max(0, min(1, (input_pendapatan - 4) / 4))
    murah = max(0, min(1, (600 - input_harga) / 200))
    mahal = max(0, min(1, (input_harga - 400) / 200))

    # Firing strength
    w1 = min(rendah, murah)
    w2 = min(tinggi, mahal)

    # Output mapping
    z1 = 1 - w1  # turun (semakin kecil)
    z2 = w2      # naik (semakin besar)

    output = (w1*z1 + w2*z2) / (w1+w2)
    return output

# Contoh penggunaan
print("Output Sugeno:", sugeno_inference(70, 15))
print("Output Tsukamoto:", tsukamoto_inference(6, 500))
```

---

## 5. Penutup

Metode Sugeno dan Tsukamoto adalah pendekatan inferensi fuzzy yang efektif untuk berbagai aplikasi kontrol dan pengambilan keputusan.
- Sugeno cocok untuk sistem yang memerlukan model matematis sederhana.
- Tsukamoto cocok untuk kebutuhan output yang lebih "smooth" dengan mempertahankan sifat monoton fungsi.
