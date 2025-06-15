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
