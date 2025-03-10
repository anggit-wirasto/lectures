# Pertemuan 2: Himpunan Fuzzy

## Tujuan Pembelajaran
Pada akhir pertemuan ini, mahasiswa diharapkan mampu:
- Memahami perbedaan antara himpunan klasik dan himpunan fuzzy.
- Menjelaskan konsep fungsi keanggotaan dalam logika fuzzy.
- Menganalisis cara representasi himpunan fuzzy dalam sistem komputasi.

---

## 1. Himpunan Klasik vs. Himpunan Fuzzy
### 1.1 Himpunan Klasik (Crisp Set)
Himpunan klasik adalah himpunan yang elemen-elemennya memiliki keanggotaan yang tegas (binary). Setiap elemen dalam semesta pembicaraan hanya memiliki dua kemungkinan:
- **Termasuk dalam himpunan** (nilai 1 atau "True").
- **Tidak termasuk dalam himpunan** (nilai 0 atau "False").

**Contoh:**
Jika kita memiliki semesta pembicaraan bilangan real antara 0 hingga 10, dan kita mendefinisikan himpunan **Bilangan Besar** sebagai bilangan yang lebih besar dari 5, maka:

$$ A = \{6, 7, 8, 9, 10\}$$

Bilangan 4 tidak termasuk dalam himpunan ini, karena tidak memenuhi kriteria yang diberikan.

### 1.2 Himpunan Fuzzy
Himpunan fuzzy memungkinkan elemen dalam semesta pembicaraan memiliki derajat keanggotaan antara 0 dan 1. Artinya, suatu elemen dapat "sebagian" menjadi anggota suatu himpunan.

Himpunan fuzzy didefinisikan dengan **fungsi keanggotaan** $\mu_A(x)$ yang menentukan seberapa besar suatu elemen $ x $ termasuk dalam himpunan fuzzy $ A $, dengan:

$ \mu_A(x) \in [0,1] $

**Contoh:**
Jika kita mendefinisikan himpunan fuzzy **Bilangan Besar**, maka nilai keanggotaannya bisa sebagai berikut:
- $ \mu_A(4) = 0.2 $ → Bilangan 4 hanya sedikit besar.
- $ \mu_A(6) = 0.7 $ → Bilangan 6 cukup besar.
- $ \mu_A(9) = 1.0 $ → Bilangan 9 sangat besar.

Dengan pendekatan ini, kita bisa menangani ketidakpastian dan konsep "keanggotaan sebagian" yang lebih dekat dengan cara berpikir manusia.

---

## 2. Fungsi Keanggotaan (Membership Function)
Fungsi keanggotaan menentukan nilai keanggotaan setiap elemen dalam semesta pembicaraan terhadap suatu himpunan fuzzy.

### 2.1 Bentuk-Bentuk Fungsi Keanggotaan
Beberapa bentuk fungsi keanggotaan yang umum digunakan adalah:
1. **Fungsi Keanggotaan Segitiga (Triangular Membership Function)**
   $
   \mu_A(x) = \begin{cases} 
   0, & x \leq a \\ 
   \frac{x-a}{b-a}, & a < x < b \\ 
   \frac{c-x}{c-b}, & b < x < c \\ 
   0, & x \geq c
   \end{cases}
   $

2. **Fungsi Keanggotaan Trapesium (Trapezoidal Membership Function)**
   $
   \mu_A(x) = \begin{cases} 
   0, & x \leq a \\ 
   \frac{x-a}{b-a}, & a < x < b \\ 
   1, & b \leq x \leq c \\ 
   \frac{d-x}{d-c}, & c < x < d \\ 
   0, & x \geq d
   \end{cases}
   $

3. **Fungsi Keanggotaan Gaussian (Gaussian Membership Function)**
   $
   \mu_A(x) = e^{-\frac{(x - c)^2}{2 \sigma^2}}
   $
   Fungsi ini digunakan dalam banyak aplikasi karena sifatnya yang halus dan kontinu.

### 2.2 Contoh Implementasi Fungsi Keanggotaan
Sebagai contoh, kita ingin menentukan derajat keanggotaan suatu suhu dalam kategori **Dingin**, **Normal**, dan **Panas** berdasarkan derajat Celsius.

| Suhu (°C) | Dingin (μ) | Normal (μ) | Panas (μ) |
|-----------|------------|------------|-----------|
| 10        | 1.0        | 0.0        | 0.0       |
| 15        | 0.8        | 0.2        | 0.0       |
| 20        | 0.4        | 0.6        | 0.0       |
| 25        | 0.0        | 1.0        | 0.0       |
| 30        | 0.0        | 0.6        | 0.4       |
| 35        | 0.0        | 0.2        | 0.8       |
| 40        | 0.0        | 0.0        | 1.0       |

Dari tabel di atas, kita bisa melihat bagaimana suatu suhu memiliki lebih dari satu keanggotaan fuzzy secara simultan.

---

## 3. Representasi Himpunan Fuzzy
Himpunan fuzzy dapat direpresentasikan dalam beberapa cara:
1. **Grafik Fungsi Keanggotaan**: Biasanya digambarkan dalam bentuk kurva yang menunjukkan derajat keanggotaan setiap elemen dalam semesta pembicaraan.
2. **Notasi Matematis**: Ditulis sebagai pasangan nilai dan derajat keanggotaannya, misalnya:
   $ A = \{(10,1.0), (15,0.8), (20,0.4), (25,0.0)\} $
3. **Implementasi Komputasi**: Menggunakan bahasa pemrograman seperti Python (skfuzzy) atau MATLAB.

---

## Kesimpulan
- Himpunan klasik memiliki keanggotaan yang tegas (0 atau 1), sementara himpunan fuzzy memiliki derajat keanggotaan antara 0 hingga 1.
- Fungsi keanggotaan menentukan seberapa besar suatu elemen termasuk dalam suatu himpunan fuzzy.
- Terdapat berbagai jenis fungsi keanggotaan seperti segitiga, trapesium, dan Gaussian.
- Himpunan fuzzy dapat direpresentasikan dalam bentuk grafik, notasi matematis, atau kode program.

---

