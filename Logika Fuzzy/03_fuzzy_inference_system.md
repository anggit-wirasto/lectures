Berikut adalah materi lengkap untuk **Pertemuan 3: Fuzzy Inference System (FIS)** dalam mata kuliah **Logika Fuzzy**.  

---

## **PERTEMUAN 3: FUZZY INFERENCE SYSTEM (FIS)**  
### **Tujuan Pembelajaran**  
Setelah mengikuti pertemuan ini, mahasiswa diharapkan mampu:  
1. Memahami konsep dasar Sistem Inferensi Fuzzy (FIS).  
2. Menjelaskan struktur dan komponen utama dalam FIS.  
3. Membuat aturan fuzzy sederhana untuk suatu sistem.  

---

## **1. Pengenalan Fuzzy Inference System (FIS)**  
### **Apa itu FIS?**  
Fuzzy Inference System (FIS) adalah suatu kerangka kerja berbasis logika fuzzy yang digunakan untuk mengambil keputusan atau mengontrol suatu sistem berdasarkan aturan fuzzy.  

FIS mengubah input numerik menjadi output yang dapat ditafsirkan dengan menggunakan aturan fuzzy dan operasi himpunan fuzzy.  

### **Contoh Penerapan FIS:**  
- Sistem pendukung keputusan  
- Kontrol suhu otomatis  
- Sistem rekomendasi  
- Pengenalan pola  

---

## **2. Struktur Fuzzy Inference System (FIS)**  
FIS terdiri dari lima komponen utama:  
1. **Fuzzification** – Mengubah input numerik menjadi nilai fuzzy.  
2. **Knowledge Base (Basis Pengetahuan)** – Berisi himpunan fuzzy dan aturan fuzzy.  
3. **Inference Engine** – Melakukan proses inferensi berdasarkan aturan fuzzy.  
4. **Rule Base (Basis Aturan)** – Sekumpulan aturan fuzzy berbentuk "IF-THEN".  
5. **Defuzzification** – Mengubah output fuzzy menjadi nilai numerik.  

**Diagram Alur FIS:**  
\[
\text{Input} \rightarrow \text{Fuzzification} \rightarrow \text{Inference Engine} \rightarrow \text{Defuzzification} \rightarrow \text{Output}
\]  

---

## **3. Komponen Utama FIS**  

### **1. Fuzzification (Fuzzifikasi)**  
- Mengubah data numerik menjadi variabel linguistik.  
- Contoh:  
  - Suhu 30°C → “Panas”  
  - Kecepatan 80 km/jam → “Cepat”  

### **2. Rule Base (Basis Aturan)**  
- Berisi aturan fuzzy dalam bentuk **IF-THEN**.  
- Contoh:  
  - **Jika suhu tinggi maka kipas berputar cepat**  
  - **Jika permintaan tinggi dan stok rendah maka produksi ditingkatkan**  

### **3. Inference Engine (Mesin Inferensi)**  
- Menentukan cara kerja sistem fuzzy menggunakan aturan.  
- Dua metode inferensi utama:  
  - **Mamdani** (menghasilkan himpunan fuzzy)  
  - **Sugeno** (menghasilkan nilai numerik)  

### **4. Defuzzification (Defuzzifikasi)**  
- Mengubah output fuzzy menjadi nilai numerik.  
- Metode yang umum digunakan:  
  - **Centroid (COG – Center of Gravity)**  
  - **Mean of Maximum (MoM)**  
  - **Bisector**  

---

## **4. Metode Inferensi Fuzzy**  

### **1. Metode Mamdani**  
- Menggunakan aturan berbasis himpunan fuzzy.  
- Contoh aturan:  
  - **IF suhu panas THEN kipas cepat**  
  - **IF jarak dekat THEN rem kuat**  

### **2. Metode Sugeno**  
- Menghasilkan output dalam bentuk numerik langsung.  
- Contoh aturan:  
  - **IF suhu panas THEN output = 80% kecepatan kipas**  
  - **IF jarak dekat THEN output = 0.9 gaya pengereman**  

---

## **5. Contoh Implementasi FIS (Studi Kasus: Pengaturan Kecepatan Kipas)**  

**Variabel Input:**  
- Suhu (Dingin, Normal, Panas)  

**Variabel Output:**  
- Kecepatan Kipas (Lambat, Sedang, Cepat)  

**Aturan Fuzzy:**  
1. Jika suhu **Dingin**, maka kecepatan kipas **Lambat**.  
2. Jika suhu **Normal**, maka kecepatan kipas **Sedang**.  
3. Jika suhu **Panas**, maka kecepatan kipas **Cepat**.  

---

## **Contoh Soal dan Pembahasan**  

### **Soal 1: Menentukan Keanggotaan Fuzzy**
Diketahui himpunan fuzzy untuk suhu sebagai berikut:  
- **Dingin:** Segitiga (0, 0, 15)  
- **Normal:** Trapesium (10, 15, 25, 30)  
- **Panas:** Segitiga (25, 30, 40)  

Hitung nilai keanggotaan suhu **x = 20** untuk masing-masing himpunan fuzzy!  

#### **Jawaban:**
- Untuk **Dingin**:  
  \[
  \mu(20) = 0 \quad (\text{karena di luar range})
  \]

- Untuk **Normal** (trapesium):  
  \[
  \mu(20) = \frac{25-20}{25-15} = \frac{5}{10} = 0.5
  \]

- Untuk **Panas**:  
  \[
  \mu(20) = 0 \quad (\text{karena di luar range})
  \]

**Jawaban Akhir:**  
\[
\mu_{\text{Dingin}}(20) = 0, \quad \mu_{\text{Normal}}(20) = 0.5, \quad \mu_{\text{Panas}}(20) = 0
\]  

---

### **Soal 2: Menentukan Output Defuzzifikasi**  
Diketahui fungsi keanggotaan hasil inferensi:  
- \( \mu(10) = 0.3 \)  
- \( \mu(20) = 0.5 \)  
- \( \mu(30) = 0.7 \)  

Hitung nilai output menggunakan metode **Centroid**!

#### **Jawaban:**
\[
Z = \frac{\sum (\mu(x) \cdot x)}{\sum \mu(x)}
\]

\[
Z = \frac{(0.3 \times 10) + (0.5 \times 20) + (0.7 \times 30)}{0.3 + 0.5 + 0.7}
\]

\[
Z = \frac{(3 + 10 + 21)}{1.5} = \frac{34}{1.5} = 22.67
\]

**Jawaban Akhir:** Output defuzzifikasi adalah **22.67**.

---
