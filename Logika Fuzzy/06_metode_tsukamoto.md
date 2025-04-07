# Pertemuan 4: Fuzzy Inference System – Metode Tsukamoto

## 🎯 Tujuan Pembelajaran
- Memahami konsep dasar metode Tsukamoto dalam sistem inferensi fuzzy (FIS).
- Mengetahui bagaimana proses inferensi dilakukan dalam metode Tsukamoto.
- Membedakan metode Tsukamoto dengan metode Mamdani dan Sugeno.
- Menerapkan metode Tsukamoto pada studi kasus sederhana.

---

## 📘 1. Pengantar FIS Metode Tsukamoto

Metode Tsukamoto merupakan salah satu metode sistem inferensi fuzzy yang menggunakan **aturan berbasis IF-THEN** dengan **konsekuen berupa fungsi keanggotaan fuzzy monoton**. Berbeda dari Mamdani yang menggunakan output fuzzy, pada Tsukamoto setiap aturan menghasilkan **nilai output crisp (tegas)** melalui proses defuzzifikasi **per aturan**.

---

## 🧩 2. Ciri Khas Metode Tsukamoto

- **Konsekuen (THEN)** harus memiliki fungsi keanggotaan **monoton** (naik atau turun).
- Setiap aturan menghasilkan **output crisp**.
- Hasil akhir diperoleh melalui **rata-rata berbobot** dari semua output aturan.

---

## ⚙️ 3. Struktur Proses FIS Tsukamoto

1. **Fuzzifikasi**: Ubah input crisp menjadi derajat keanggotaan fuzzy.
2. **Aplikasi Aturan (Inferensi)**: Gunakan aturan fuzzy dalam bentuk IF-THEN.
3. **Perhitungan Output Crisp**:  
   - Gunakan **fungsi keanggotaan monoton** untuk mendapatkan nilai \( z \) dari derajat keanggotaan \( \alpha \).
4. **Agregasi (Defuzzifikasi)**: Hitung output akhir menggunakan rata-rata berbobot:

\[
Z = \frac{\sum (\alpha_i \cdot z_i)}{\sum \alpha_i}
\]

---

## 🧠 4. Contoh Aturan Tsukamoto

**Contoh Kasus: Sistem Penilaian Kelayakan Pinjaman**

### Variabel Input:
- Pendapatan: {Rendah, Sedang, Tinggi}
- Jaminan: {Buruk, Cukup, Bagus}

### Variabel Output:
- Kelayakan Pinjaman: {Tidak Layak (0), Layak (100)} ← fungsi keanggotaan monoton

### Contoh Aturan:
- **Rule 1**: IF Pendapatan Rendah AND Jaminan Buruk THEN Kelayakan = Tidak Layak  
- **Rule 2**: IF Pendapatan Tinggi AND Jaminan Bagus THEN Kelayakan = Layak

---

## 🧪 5. Contoh Perhitungan FIS Tsukamoto

### Diketahui:
- Pendapatan = 6 juta  
- Jaminan = sedang  
- Fungsi keanggotaan:
  - Pendapatan rendah: turun dari 1 (≤ 5 juta) ke 0 (≥ 10 juta)  
  - Pendapatan tinggi: naik dari 0 (≤ 5 juta) ke 1 (≥ 10 juta)  
  - Jaminan sedang: segitiga (40, 60, 80)

### Langkah-langkah:
1. **Fuzzifikasi**: Hitung derajat keanggotaan (μ) dari masing-masing input.
2. **Aturan 1**:
   - α1 = min(μ_pendapatan_rendah, μ_jaminan_cukup)
   - Hitung z1 berdasarkan fungsi keanggotaan monoton output
3. **Aturan 2**:
   - α2 = min(μ_pendapatan_tinggi, μ_jaminan_bagus)
   - Hitung z2
4. **Output akhir**:
   \[
   Z = \frac{\alpha_1 z_1 + \alpha_2 z_2}{\alpha_1 + \alpha_2}
   \]

---

## 🆚 6. Perbandingan Metode FIS

| Aspek                     | Mamdani                    | Sugeno                      | Tsukamoto                      |
|--------------------------|----------------------------|-----------------------------|--------------------------------|
| Konsekuen                | Fuzzy                      | Linear / Konstanta          | Fungsi keanggotaan monoton     |
| Output tiap aturan       | Himpunan fuzzy             | Nilai numerik               | Nilai numerik (crisp)          |
| Defuzzifikasi            | Setelah agregasi           | Tidak perlu / Weighted avg  | Per aturan, lalu weighted avg  |
| Interpretasi             | Lebih intuitif             | Cepat untuk komputasi       | Komputasi menengah, hasil tegas|
| Kompatibilitas logika    | Lebih fleksibel            | Lebih presisi               | Cocok untuk sistem tegas       |


---
