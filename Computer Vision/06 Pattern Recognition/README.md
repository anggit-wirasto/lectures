# Pengenalan Pola

## Tujuan Pembelajaran

Setelah mempelajari materi ini, mahasiswa diharapkan mampu:

- Menjelaskan prinsip dasar pengenalan pola.
- Memahami proses dasar pengolahan citra untuk keperluan pengenalan pola.
- Melakukan konversi citra warna ke skala keabuan, citra biner, serta memahami histogram citra.

---

# 1. Pengenalan Citra

**Citra digital** adalah representasi dua dimensi dunia nyata yang direpresentasikan sebagai array piksel.

Jenis-jenis citra:

- **Citra Berwarna (Color Image)**: Tiap piksel terdiri dari tiga komponen warna (R, G, B).
- **Citra Skala Keabuan (Grayscale Image)**: Setiap piksel memiliki satu nilai intensitas antara 0 (hitam) hingga 255 (putih).
- **Citra Biner (Binary Image)**: Piksel hanya memiliki dua nilai, 0 (hitam) atau 255 (putih).

> **Ilustrasi**
>
> ![Contoh Citra Berwarna dan Skala Keabuan](https://upload.wikimedia.org/wikipedia/commons/2/24/Lenna.png)
> 
> Kiri: Citra berwarna, Kanan: Citra skala keabuan.


# 2. Konversi Citra Berwarna menjadi Citra Skala Keabuan

Konversi citra warna ke grayscale menyederhanakan analisis dan mengurangi kompleksitas data.

### Formula Konversi

\[ Gray = 0.299R + 0.587G + 0.114B \]

### Contoh Perhitungan

Misal:
- \( R = 120, G = 200, B = 150 \)

Maka:

\[ Gray = (0.299 \times 120) + (0.587 \times 200) + (0.114 \times 150) \]
\[ Gray = 35.88 + 117.4 + 17.1 = 170.38 \]
\[ Gray \approx 170 \]

### Contoh Lain

| R  | G  | B  | Gray (hasil) |
|----|----|----|--------------|
| 50 | 50 | 50 | 50           |
| 255| 0  | 0  | 76           |
| 0  | 255| 0  | 150          |
| 0  | 0  | 255| 29           |

> **Ilustrasi**
>
> ![Grayscale Transformation](https://upload.wikimedia.org/wikipedia/commons/8/86/Color_to_Gray.png)


# 3. Citra Biner dari Citra Skala Keabuan

Konversi citra grayscale ke biner dilakukan dengan **thresholding**.

### Prinsip Thresholding

- Piksel > threshold: Putih (255)
- Piksel \<= threshold: Hitam (0)

### Contoh Manual

Misal threshold = 100:

| Nilai Piksel | Setelah Threshold |
|--------------|-------------------|
| 50           | 0                 |
| 120          | 255               |
| 90           | 0                 |
| 200          | 255               |

### Thresholding Otomatis

Metode seperti **Otsu's Method** secara otomatis menentukan threshold optimal berdasarkan histogram citra.

> **Ilustrasi Thresholding**
>
> ![Thresholding Example](https://upload.wikimedia.org/wikipedia/commons/thumb/d/d3/Otsu_example.png/400px-Otsu_example.png)
>
> Kiri: Asli, Tengah: Grayscale, Kanan: Biner


# 4. Histogram Citra

Histogram citra adalah grafik distribusi frekuensi nilai piksel.

- **Sumbu X**: Nilai intensitas (0-255)
- **Sumbu Y**: Jumlah piksel dengan nilai tersebut

### Contoh Data Histogram

| Intensitas | Jumlah Piksel |
|------------|---------------|
| 0          | 50            |
| 128        | 100           |
| 200        | 75            |
| 255        | 25            |

### Membaca Histogram
- Puncak di intensitas rendah → Gambar lebih gelap.
- Puncak di intensitas tinggi → Gambar lebih terang.

> **Ilustrasi Histogram**
>
> ![Histogram Example](https://upload.wikimedia.org/wikipedia/commons/7/7c/Image_Histogram.png)


---

# Contoh Praktik Lengkap (Python OpenCV)

```python
import cv2
import matplotlib.pyplot as plt

# Load gambar berwarna
image_color = cv2.imread('contoh.jpg')

# Konversi ke grayscale
image_gray = cv2.cvtColor(image_color, cv2.COLOR_BGR2GRAY)

# Konversi ke citra biner
_, image_binary = cv2.threshold(image_gray, 128, 255, cv2.THRESH_BINARY)

# Tampilkan hasil
plt.figure(figsize=(12,8))

plt.subplot(2,2,1)
plt.title('Original (Color)')
plt.imshow(cv2.cvtColor(image_color, cv2.COLOR_BGR2RGB))
plt.axis('off')

plt.subplot(2,2,2)
plt.title('Grayscale')
plt.imshow(image_gray, cmap='gray')
plt.axis('off')

plt.subplot(2,2,3)
plt.title('Binary')
plt.imshow(image_binary, cmap='gray')
plt.axis('off')

plt.subplot(2,2,4)
plt.title('Histogram')
plt.hist(image_gray.ravel(), 256, [0, 256])
plt.grid(True)

plt.tight_layout()
plt.show()
```

> **Hasil Visualisasi:**
>
> - Gambar asli
> - Gambar grayscale
> - Gambar biner
> - Histogram distribusi intensitas


# Kesimpulan

- Citra digital dapat direpresentasikan dalam berbagai format.
- Konversi warna → grayscale → biner adalah proses umum dalam pengolahan pola.
- Histogram membantu dalam menganalisis distribusi cahaya dalam citra.
- Pengolahan dasar ini penting sebelum masuk ke tahap pengenalan pola lebih lanjut seperti segmentasi, ekstraksi fitur, dan klasifikasi.

---

> _Disusun untuk pertemuan ke-5 Mata Kuliah Computer Vision / Pengolahan Citra Digital._
