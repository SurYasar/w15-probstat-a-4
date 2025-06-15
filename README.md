# W15 ASSIGNMENT - ANOVA
</div>

|    NRP     |      Name      |
| :--------: | :------------: |
| 5025231114 | Muhammad Surya Yasar |
| 5025231115 | Arkananta Masarief |
| 5025231116 | Rafi Faheem Aziz |
| 5025231243 | Ahmad Izzul Hamdan Zoelfa |

</div>

## ANOVA

ANOVA (Analysis of Variance) adalah metode statistik untuk menguji apakah terdapat perbedaan yang signifikan antara rata-rata dua atau lebih grup. ANOVA menganalisis variabilitas antar grup dan dalam grup, lalu membandingkannya melalui rasio statistik yang disebut F-statistik.
- Tujuan utama: Mengetahui apakah perbedaan rata-rata grup berasal dari variasi acak atau dari faktor yang signifikan.
- Dasar pemikiran: Jika grup memiliki varians yang kecil di dalamnya tapi perbedaan rata-ratanya besar, kemungkinan besar ada pengaruh signifikan dari faktor yang diuji.

## Konsep Dasar ANOVA
- Komponen Variansi
  1. Total Variance (SST) = variasi total dalam data
  2. Between-Group Variance (SSB) = variasi antar grup (karena perlakuan)
  3. Within-Group Variance (SSW) = variasi dalam grup (karena variasi acak)
  Hubungan matematis:
  ```
  SST = SSB + SSW
  ```
- Statistik F
  Digunakan untuk membandingkan variasi antar grup dengan variasi dalam grup:
  
  ```
  F + (MSB / MSW)
  ```
  - MSB (Mean Square Between) = SSB / dfB
  - MSW (Mean Square Within) = SSW / dfW
  - Bandingkan nilai F dengan F-tabel untuk menentukan signiificance

## One-Way ANOVA
One-way ANOVA digunakan untuk menguji perbedaan rata-rata antar lebih dari dua grupp berdasarkan satu faktor/variabel bebas.
Asumsi One-Way ANOVA:
1. Data dalam setiap grup berdistribusi normal
2. Homogenitas varians (varians tiap grup relatif sama)
3. Observasi independen

### Contoh Kasus
  Menilai apakah rata-rata nilai ujian berbeda untuk 3 metode belajar: tradisional, online, dan campuran
### Langkah-langkah
  1. Hipotesis:
  2. Hitung Total Sum of Squares (SST))
  3. Hitung Between Groups Sum of Squares (SSB)
  4. Hitung Within Groups Sum of Squares (SSW)
  5. Hitung F-statistic
  6. Bandingkan F-hitung dengan F-tabel
  7. Jika F-hitung > F-tabel, makan tolak H<sub>0</sub>
### Post-Hoc Test (jika H<sub>0</sub> ditolak)
Jika terdapat perbedaan siignifikan, lakukan uji lanjut seperti:
- Turkey HSD
- Bonferroni
- Duncan test

### Contoh Tabel

| Sumber Variasi | df | SS | MS | F |
| :---: | :--: | :--: | :--: | :--: | 
| Antar Grup (SSB) | k-1 | SSB | MSB | F = MSB/MSW |
| Dalam Grup (SSW) | N-k | SSW | MSW |  |
| Total (SST) | N-1 | SST |  |  |

- k: jumlah grup
- N: total observasi

## Two-Way ANOVA
Two-Way ANOVA digunakan ketika kita memiliki dua faktor yang dapat mempengaruhi variable dependen, dan kita ingin mengetahui apakah masing-masing faktor berpengaruh serta adakah interaksi antara dua faktor.
Asumsi Two-Way ANOVA:
1. Data dalam setiap grup berdistribusi normal
2. Homogenitas varians (varians tiap grup relatif sama)
3. Observasi independen
4. Observasi di setiap sel kombinasi antar faktor bersifat independen

### Contoh Kasus
Menganalisis pengaruh jenis metode belajar (faktor A) dan jenis kelamin (faktor B) terhadap nilai ujian.
- Komponen Variansi:
  - SSA = variasi karena faktor A
  - SSB = variasi karena faktor B
  - SSAB = interaksi A x B
  - SSE = variasi residual/error

### Hipotesis:
- H<<sub>0</sub> (A): Tidak ada pengaruh faktor A
- H<<sub>0</sub> (B): Tidak ada pengaruh faktor B
- H<<sub>0</sub> (AB): Tidak ada pengaruh faktor A x B

### Langkah-langkah:
1. Hitung SSB, SSA, SSAB, SSE, SST
2. Hitung masing-masing MS
3. Hitung F untuk setiap faktor dan interaksi
4. Bandingkan dengan nilai F-tabel
5. Lakukan post-hoc jika perlu

## Uji Perbedaan Rata-rata untuk Lebih dari 2 Grup
Ketika membandingkan lebih dari dua rata-rata, kita tidak boleh langsung menggunakan t-test berulang kali, karena akan meningkatkan peluang Type 1 Error (false positive)
### Solusi:
- Gunakan One-Way ANOVA terlebih dahulu
- Jika hasil signifikan, lanjutkan dengan post-hoc test
### Alternatif: Non-parametrik
Jika asumsi ANOVA tidak terpenuhi, bisa gunakan:
- Kruskal-Wallis Test (untuk One-Way ANOVA non-parametrik
- Friedman Test (jika data berpasangan)

### Contoh Tabel
Misalnya kita memiliki dua faktor:
- Faktor A: Jenis Metode Belajar (3 level)
- Faktor B: Jenis Kelamin (2 level)

Misalnya, setiap kombinasi AxB memiliki 5 pengamatan -> total N = 3x2x5 = 30

| Sumber Variasi | df | SS | MS | F |
| :--: | :--: | :--: | :--: | :--: |
| Faktor A | a-1 | SSA | MSA = SSA/(a-1) | F<sub>1</sub> = MSA/MSE |
| Faktor B | b-1 | SSB | MSB = SSB/(b-1) | F<sub>2</sub> = MSb/MSE |
| Interaksi AxB | (a-1)(b-1) | SSAB | MSAB = SSAB/(a-1)(b-1) | F<sub>3</sub> = MSAB/MSE |
| Error (dalam sel/kesalahan) | ab(n-1) | SSE | MSE = SSE/ab(n-1) | -- |
| Total | N-1 = abn-1 | SST = SSA+SSB+SSAB+SSE | -- | -- |

Keterangan:
- a: jumlah level faktor A
- b: jumlah level faktor B
- n: jumlah observasi per sel
- ab: jumlah kombinasi level
- N: total data (a x b x n)

## Contoh Soal One-Way ANOVA
### Soal
Seorang peneliti ingin mengetahui apakah tiga metode belajar (tatap muka, daring, dan blended) memberikan hasil nilai ujian yang berbeda secara signifikan kepada siswa.
Nilai ujian dari 5 siswa untuk masing-masing metode:

| Metode | Nilai | n |
| :--: | :--: | :--: |
| Tatap Muka | 80, 85, 78, 82, 84 | 5 |
| Daring | 75, 78, 74, 72, 76 | 5 |
| Blended | 88, 85, 90, 87, 89 | 5 |
| Total n |  | 15 |

Gunakan One-Way ANOVA dengan tingkat signifikansi a = 0.05 untuk menjawab:
1. Apakah terdapat perbedaan rata-rata nilai ujian antar ketiga metode belajar tersebut?
2. Jika terdapat perbedaan, metode mana yang memiliki perbedaan paling signifikan?

### Jawab
1. Hitung rata-rata tiap grup & rata-rata total
   - Tatap Muka: (80+85+78+82+84)/5 = 81.8
   - Daring: (75+78+74+72+76)/5 = 75.0
   - Blended: (88+85+90+87+89)/5 = 87.8
   - Rata-rata total (grand mean) = (Σ semua nilai)/15 = 81.53
2. Hitung SST <br>
   ![image](https://github.com/user-attachments/assets/9b608b4f-54ea-4928-aade-a7af48f3671c) <br>
   Gunakan semua 15 data dan kurangi dengan grand mean, maka
   ![image](https://github.com/user-attachments/assets/f0872ce6-d2cb-4d5c-970d-434e6a5ec315)

3. Hitung SSB <br>
   ![image](https://github.com/user-attachments/assets/b4944574-7951-4f53-8715-c2847e9a37ff)

4. Hitung SSW
   - SSW=SST−SSB=425.2−410.81=14.39
   
5. Hitung df dan F-score
   - df between = k - 1 = 2
   - df within = N - k = 12
     ![image](https://github.com/user-attachments/assets/1c418e19-26df-4b5f-9617-9c572b3375c2)

6. Uji hipotesis
   Bandingkan F hitung (171.18) dengan F kritis dari tabel F (3.89)
   Kesimpulan: Karena 171.18 > 3.89 -> Tolak H<sub>0</sub> -> ada perbedaan signifikan.

## Contoh Soal Two-Way ANOVA
### Soal
Seorang guru ingin mengetahui pengaruh jenis metode belajar dan jenis kelamin terhadap nilai ujian siswa.
Setiap guru terdiri dari 3 siswa (total 18 siswa)
| Metode Belajar | Laki-laki | Perempuan |
| :--: | :--: | :--: |
| Tatap Muka | 80, 85, 82 | 88, 90, 87 |
| Daring | 75, 70, 73 | 76, 78, 74 |
| Blended | 84, 86, 85 | 89, 91, 90 |

Gunakan Two-Way ANOVA (a = 0.05) untuk menentukan:
1. Apakah terdapat pengaruh jenis metode belajar terhadap nilai ujian?
2. Apakah terdapat pengaruh jenis kelamin terhadap nilai ujian?
3. Apakah terdapat interaksi antara metode belajar dan jenis kelamin?

### Jawab
#### Struktur Data
Setiap kombinasi (AxB) berisi 3 siswa -> total = 18 data
Faktor A (Metode Belajar): Tatap Muka, Daring, Blended (a = 3)
Faktor B (Jenis Kelamin): Laki-laki, Perempuan (b = 2)

#### 1. Hitung rata-rata sel, rata-rata baris (A), kolom (B), dan grand mean
- Rata-rata per sel:
  - Tatap Muka (L): (80+85+82)/3 = 82.33
  - Tatap Muka (P): (88+90+87)/3 = 88.33
  - Daring (L): (75+70+73)/3 = 72.67
  - Daring (P): (76+78+74)/3 = 76.00
  - Blended (L): (84+86+85)/3 = 85.00
  - Blended (P): (89+91+90)/3 = 90.00
- Rata-rata per metode (A):
  - Tatap Muka: (82.33 + 88.33)/2 = 85.33
  - Daring: (72.67 + 76.00)/2 = 74.33
  - Blended: (85.00 + 90.00)/2 = 87.5
- Rata-rata per jenis kelamin (B):
  - Laki-laki: (82.33 + 72.67 + 85.00)/3 = 80.00
  - Perempuan: (88.33 + 76.00 + 90.00)/3 = 84.78
- Grand mean (GM): ![image](https://github.com/user-attachments/assets/09ebead1-fd09-497b-9171-18281258b000)

#### 2. Hitung SSA, SSB, SSAB, SSE, SST
Secara ringkas (hasil perhitungan dibulatkan):
- SSA = n_b × Σ (rata²A - GM)² = 2×[(85.33 - 82.39)² + (74.33 - 82.39)² + (87.5 - 82.39)²] ≈ 263.66
- SSB = n_a × Σ (rata²B - GM)² = 3×[(80.00 - 82.39)² + (84.78 - 82.39)²] ≈ 50.89
- SSAB = Σ ((sel mean - rataA - rataB + GM)² × n) ≈ 9.56
- SST = Σ semua (X - GM)² ≈ 518.22
- SSE = SST - SSA - SSB - SSAB = 518.22 - 263.66 - 50.89 - 9.56 ≈ 194.11

#### 3. df dan F

| Sumber       | df | SS     | MS     | F    |
| ------------ | -- | ------ | ------ | ---- |
| Metode (A)   | 2  | 263.66 | 131.83 | 8.14 |
| Kelamin (B)  | 1  | 50.89  | 50.89  | 3.14 |
| Interaksi AB | 2  | 9.56   | 4.78   | 0.30 |
| Error        | 12 | 194.11 | 16.18  | —    |
| Total        | 17 | 518.22 | —      | —    |

#### 4. Interpretasi
Bandingkan dengan F-tabel (a = 0.05):
- F(2,12) ≈ 3.89
- F(1,12) ≈ 4.75

Hasil:
- Faktor A (metode belajar) → F = 8.14 > 3.89 → Signifikan
- Faktor B (jenis kelamin) → F = 3.14 < 4.75 → Tidak signifikan
- Interaksi A×B → F = 0.30 < 3.89 → Tidak signifikan

Maka hanya metode belajar yang berpengaruh signifikan. Jenis kelamin dan interaksi tidak signifikan.
