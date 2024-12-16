# Rangkuman Materi Persamaan Diferensial

## 1. Pengertian Persamaan Diferensial
Persamaan diferensial adalah persamaan yang melibatkan turunan fungsi. Persamaan ini digunakan untuk memodelkan fenomena yang berubah terhadap suatu variabel, seperti waktu, ruang, atau lainnya.

---

## 2. Klasifikasi Persamaan Diferensial
Persamaan diferensial diklasifikasikan berdasarkan:
- **Orde**: Ditentukan oleh turunan tertinggi yang muncul dalam persamaan.
- **Linearitas**: Linear jika fungsi dan turunannya muncul dengan pangkat 1 dan tidak dikalikan satu sama lain.

---

## 3. Bentuk Umum
- **Persamaan Diferensial Orde Satu**:
  \[
  \frac{dy}{dx} + P(x)y = Q(x)
  \]
- **Persamaan Diferensial Orde Dua**:
  \[
  \frac{d^2y}{dx^2} + p(x)\frac{dy}{dx} + q(x)y = g(x)
  \]

---

## 4. Metode Penyelesaian Persamaan Diferensial Orde Satu
1. **Metode Pemisahan Variabel**:  
   Digunakan jika persamaan dapat ditulis sebagai \( g(y)dy = f(x)dx \).
2. **Metode Integrasi Langsung**:  
   Digunakan jika persamaan berbentuk sederhana, seperti \( \frac{dy}{dx} = f(x) \).
3. **Persamaan Linear**:  
   Menggunakan faktor integrasi.
4. **Persamaan Eksak**:  
   Diterapkan jika \( M(x, y)dx + N(x, y)dy = 0 \) memenuhi syarat eksak \( \frac{\partial M}{\partial y} = \frac{\partial N}{\partial x} \).

---

## Contoh dan Penyelesaian

### 1. Contoh Metode Pemisahan Variabel
**Persamaan**:
\[
\frac{dy}{dx} = xy
\]

**Penyelesaian**:
1. Pisahkan variabel \( y \) dan \( x \):  
   \[
   \frac{1}{y} dy = x dx
   \]
2. Integrasikan kedua sisi:  
   \[
   \int \frac{1}{y} dy = \int x dx
   \]
   \[
   \ln|y| = \frac{x^2}{2} + C
   \]
3. Tulis solusi dalam bentuk eksplisit:  
   \[
   y = e^{\frac{x^2}{2} + C} = Ce^{\frac{x^2}{2}}
   \]

---

### 2. Contoh Metode Linear
**Persamaan**:
\[
\frac{dy}{dx} + y = e^x
\]

**Penyelesaian**:
1. Identifikasi \( P(x) = 1 \), \( Q(x) = e^x \).
2. Cari faktor integrasi:  
   \[
   \mu(x) = e^{\int P(x)dx} = e^{\int 1 dx} = e^x
   \]
3. Kalikan seluruh persamaan dengan \( \mu(x) \):  
   \[
   e^x \frac{dy}{dx} + e^x y = e^{2x}
   \]
4. Bentuk kiri menjadi turunan \( (e^x y) \):  
   \[
   \frac{d}{dx}(e^x y) = e^{2x}
   \]
5. Integrasikan kedua sisi:  
   \[
   e^x y = \int e^{2x} dx = \frac{e^{2x}}{2} + C
   \]
6. Solusi umum:  
   \[
   y = \frac{e^x}{2} + Ce^{-x}
   \]

---

### 3. Contoh Persamaan Eksak
**Persamaan**:
\[
(2xy + y^2)dx + (x^2 + 2xy)dy = 0
\]

**Penyelesaian**:
1. Identifikasi \( M(x, y) = 2xy + y^2 \) dan \( N(x, y) = x^2 + 2xy \).
2. Periksa eksak:  
   \[
   \frac{\partial M}{\partial y} = 2x + 2y, \quad \frac{\partial N}{\partial x} = 2x + 2y
   \]
   Karena \( \frac{\partial M}{\partial y} = \frac{\partial N}{\partial x} \), persamaan eksak.
3. Cari fungsi \( \psi(x, y) \):  
   \[
   \frac{\partial \psi}{\partial x} = M(x, y) \quad \Rightarrow \quad \psi = \int (2xy + y^2) dx = x^2y + y^2x + h(y)
   \]
4. Turunkan \( \psi \) terhadap \( y \):  
   \[
   \frac{\partial \psi}{\partial y} = x^2 + 2xy + h'(y) = N(x, y)
   \]
   \[
   h'(y) = 0 \quad \Rightarrow \quad h(y) = C
   \]
5. Solusi:  
   \[
   \psi(x, y) = x^2y + y^2x = C
   \]

---

## Kesimpulan
Persamaan diferensial sangat penting dalam memodelkan fenomena dunia nyata. Penyelesaian bergantung pada bentuk persamaan, seperti metode pemisahan variabel, linear, atau eksak. Memahami langkah sistematis sangat penting untuk mendapatkan solusi yang benar.
