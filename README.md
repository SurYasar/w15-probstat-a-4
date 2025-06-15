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
