## Peluang Bersyarat
Peluang bersyarat (conditional probability) adalah peluang terjadinya suatu peristiwa dengan asumsi bahwa peristiwa lain sudah terjadi. Dalam istilah matematis, peluang bersyarat dari peristiwa A terjadi, dengan syarat bahwa peristiwa B sudah terjadi, dinyatakan sebagai 𝑃(𝐴∣𝐵), yang dibaca sebagai "peluang 𝐴 terjadi diberikan 𝐵 terjadi."

Rumus dasar peluang bersyarat adalah:
$$P(A|B) = \frac{P(A \cap B)}{P(B)}$$

Dimana:
- P(A|B) adalah peluang terjadinya peristiwa A jika diketahui bahwa peristiwa B terjadi
- P(A ∩ B) adalah peluang terjadinya kedua peristiwa A dan B secara bersamaan
- P(B) adalah peluang terjadinya peristiwa B

Contoh:
Sebuah kotak berisi tiga bola merah dan dua bola biru. Apabila dilakukan pengambilan bola dari kotak sebanyak dua kali tanpa dikembalikan, berapa peluang pada pengambilan kedua akan terambil bola biru, jika pada pengambilan pertama terambil bola merah?

Dari contoh di atas maka: 
- P(A|B) adalah peluang terambilnya bola biru pada pengambilan kedua, jika pada pengambilan pertama mendapatkan bola merah
- P(A ∩ B) adalah peluang terambilnya bola merah pada pengambilan pertama dan bola biru pada pengambilan kedua, dari semua kemungkinan kombinasi pengambilan bola
- P(B) adalah peluang terambilnya bola merah pada pengambilan pertama

### P(B)
Peluang terambilnya bola merah pada pengambilan pertama adalah:
$$P(B) = \frac{3}{5}$$
Nilai di atas diperoleh dari jumlah bola merah yaitu tiga bola, dan total bola di dalam kotak ada lima bola.

### P(A)
Peluang terambilnya bola biru pada pengambilan kedua adalah:
$$P(A) = \frac{2}{4}$$
Nilai di atas diperoleh dari jumlah bola biru (tanpa mempedulikan bola pertama yang terambil) sebanyak dua bola, dan total bola tersisa pada pengambilan kedua ada empat bola.

### P(A ∩ B)
Peluang terambilnya bola merah pada pengambilan pertama dan bola biru pada pengambilan kedua adalah:
$$P(A \cap B) = P(A) . P(B)$$
$$P(A \cap B) = \frac{2}{4} . \frac{3}{5} = \frac{6}{20} = \frac{3}{10}$$

Secara visual semua kemungkinan kombinasi pengambilan bola (sample space) juga dapat kita tuliskan atau gambarkan dalam tabel, lalu hitung semua kombinasi bola merah - biru pada pengambilan pertama dan kedua.

Kita anggap bola merah adalah bola m1, m2, dan m3. Bola biru adalah bola b1 dan b2.

Untuk pengambilan pertama bola merah, kemungkinannya adalah:
- m1 - m2
- m1 - m3
- **m1 - b1** 
- **m1 - b2**
- m2 - m1
- m2 - m3
- **m2 - b1**
- **m2 - b2**
- m3 - m1
- m3 - m2
- **m3 - b1**
- **m3 - b2**

Untuk pengambilan pertama bola biru, kemungkinannya adalah:
- b1 - b2
- b1 - m1
- b1 - m2
- b1 - m3
- b2 - b1
- b2 - m1
- b2 - m2
- b2 - m3

Dari daftar di atas, ada 20 kombinasi kemungkinan hasil pengambilan bola, dan ada enam kombinasi yang memenuhi syarat bola pertama merah dan bola kedua biru, sesuai dengan perhitungan sebelumnya bahwa
$$P(A \cap B) = \frac{6}{20} = \frac{3}{10}$$

## P(A | B)
Sesuai dengan rumus dasar peluang bersyarat, kemudian dapat dihitung bahwa:

$$P(A|B) = \frac{\frac{3}{10}}{\frac{3}{5}}$$
$$P(A|B) = \frac{3}{10} . \frac{5}{3} = \frac{15}{30} = \frac{1}{2}$$

Dengan demikian, peluang terambilnya bola biru setelah pada pengambilan pertama didapatkan bola merah adalah $$\frac{1}{2}$$ atau 0,5.