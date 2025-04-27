# Computer Vision - Pertemuan 5: Edge Detection

---

## **Deskripsi Umum**

**Edge Detection** adalah proses mendeteksi perubahan intensitas yang tajam dalam suatu citra digital. Ini merupakan dasar dari banyak aplikasi computer vision, seperti segmentasi objek, pelacakan objek, pengenalan wajah, kendaraan otonom, dan augmented reality.

Dalam pertemuan ini, kita akan membahas teori dasar edge detection, metode thresholding, operator Canny, operator Laplacian, serta implementasinya menggunakan Python dan OpenCV.

> "Deteksi tepi adalah langkah awal penting untuk memahami struktur objek dalam gambar."

---

## **Learning Outcomes (Capaian Pembelajaran)**

Setelah mengikuti pertemuan ini, mahasiswa mampu:
- Menjelaskan konsep dasar edge detection.
- Membedakan berbagai teknik edge detection.
- Menerapkan metode Thresholding, Canny, dan Laplacian menggunakan Python OpenCV.
- Mengevaluasi kelebihan dan kekurangan masing-masing metode.

---

# 📚 Materi Detail

## 1. **Konsep Dasar Edge Detection**

### Definisi
Edge adalah titik dalam citra di mana perubahan intensitas atau warna terjadi secara drastis. Biasanya, edge mengindikasikan batas antar objek atau fitur penting dalam gambar.

### Pentingnya Edge Detection:
- Mempermudah segmentasi objek.
- Meningkatkan pemrosesan bentuk dan fitur.
- Menjadi dasar berbagai algoritma computer vision lanjutan.

### Representasi Edge
- **Strong Edge**: perubahan intensitas tajam.
- **Weak Edge**: perubahan intensitas kecil, namun tetap signifikan.

### Gradient
Gradient adalah besaran dan arah perubahan intensitas piksel.

$$
G(x, y) = \sqrt{G_x^2 + G_y^2}
$$

Dengan $G_x$ dan $G_y$ masing-masing adalah derivatif ke arah X dan Y.

---

## 2. **Thresholding**

### Pengertian
Metode Thresholding mengubah citra grayscale menjadi citra biner berdasarkan nilai ambang tertentu.

### Jenis Thresholding:
- **Global Thresholding**
- **Adaptive Thresholding** (Local)
- **Otsu's Method** (otomatis menentukan threshold optimal)

### Implementasi OpenCV:
```python
import cv2

# Load image in grayscale
img = cv2.imread('image.jpg', 0)

# Global Thresholding
_, thresh_global = cv2.threshold(img, 127, 255, cv2.THRESH_BINARY)

# Adaptive Thresholding
thresh_adaptive = cv2.adaptiveThreshold(img, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
                                        cv2.THRESH_BINARY, 11, 2)

# Otsu's Thresholding
_, thresh_otsu = cv2.threshold(img, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)

cv2.imshow('Threshold Global', thresh_global)
cv2.imshow('Threshold Adaptive', thresh_adaptive)
cv2.imshow('Threshold Otsu', thresh_otsu)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

### Ilustrasi
![Thresholding Example](https://upload.wikimedia.org/wikipedia/commons/2/22/Thresholding.png)

---

## 3. **Operator Canny**

### Sejarah dan Latar Belakang
John F. Canny mengembangkan algoritma ini pada tahun 1986 untuk menghasilkan edge detection optimal.

### Tahapan Algoritma Canny:

1. **Noise Reduction** dengan Gaussian Filter.
2. **Gradient Calculation** menggunakan Sobel Operator.
3. **Non-Maximum Suppression** untuk menipiskan edge.
4. **Double Thresholding**:
   - Strong edges: piksel dengan gradien tinggi.
   - Weak edges: piksel gradien sedang.
5. **Edge Tracking by Hysteresis** untuk menghubungkan weak edges ke strong edges.

### Implementasi OpenCV:
```python
import cv2

img = cv2.imread('image.jpg', 0)
edges = cv2.Canny(img, threshold1=50, threshold2=150)

cv2.imshow('Canny Edge', edges)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

### Visualisasi
![Canny Pipeline](https://upload.wikimedia.org/wikipedia/commons/8/88/Canny_edge_detection_algorithm_diagram.png)

---

## 4. **Operator Laplacian**

### Konsep
Laplacian adalah operator berbasis second derivative yang mengidentifikasi area perubahan intensitas cepat.

### Rumus Laplacian
$$
\nabla^2 f = \frac{\partial^2 f}{\partial x^2} + \frac{\partial^2 f}{\partial y^2}
$$

### Implementasi OpenCV:
```python
import cv2

img = cv2.imread('image.jpg', 0)
laplacian = cv2.Laplacian(img, cv2.CV_64F)

cv2.imshow('Laplacian Edge', laplacian)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

### Kekurangan:
- Sensitif terhadap noise
- Butuh kombinasi dengan filter smoothing seperti Gaussian Blur

---


# 📖 Referensi
- Gonzalez, R. C., & Woods, R. E. (2008). *Digital Image Processing*.
- OpenCV Documentation: [https://docs.opencv.org/](https://docs.opencv.org/)
- Wikipedia: [Canny Edge Detector](https://en.wikipedia.org/wiki/Canny_edge_detector)

---

# ✨ Penutup

Edge Detection adalah keterampilan mendasar yang harus dikuasai sebelum melanjutkan ke bidang computer vision yang lebih kompleks seperti object detection, image segmentation, dan recognition.

_Selamat bereksperimen dan semoga sukses!_

> **Next Meeting:** Pengenalan Pola (*Pattern Recognition*)

