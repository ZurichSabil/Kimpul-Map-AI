# KIMPUL MAP AI

## Analisis Kesesuaian Lahan Kimpul (*Xanthosoma sagittifolium*) di Kabupaten Magelang

Repository ini berisi kode, dataset, data hasil pengolahan, visualisasi, serta dokumentasi yang digunakan dalam penelitian **analisis kesesuaian lahan untuk budidaya kimpul (*Xanthosoma sagittifolium*) di Kabupaten Magelang**.

Penelitian mengintegrasikan data tanah dan iklim untuk menghasilkan klasifikasi kesesuaian lahan berdasarkan kelas **S1, S2, S3, dan N**, kemudian memetakan distribusinya secara spasial serta mengidentifikasi faktor pembatas pada setiap titik pengamatan.

##  Tujuan

Penelitian ini bertujuan untuk:

* Menganalisis karakteristik tanah dan iklim di wilayah penelitian.
* Menentukan kelas kesesuaian lahan untuk tanaman kimpul.
* Mengidentifikasi faktor pembatas pada setiap titik pengamatan.
* Menghasilkan peta spasial kesesuaian lahan kimpul di Kabupaten Magelang.
* Menyediakan hasil pengolahan data yang dapat digunakan untuk mendukung analisis dan pembahasan penelitian.

##  Isi Repository

### `HASIL PEMROSESAN/`

Berisi kode utama dan hasil pengolahan data penelitian.

* `Code_Gemastik_Karya_Tulis.ipynb`
  Notebook utama yang berisi seluruh tahapan pengolahan data, mulai dari preprocessing, ekstraksi data tanah dan iklim, klasifikasi kesesuaian, identifikasi faktor pembatas, hingga pemetaan spasial.

* `NASA_POWER_PREPROCESS (1).csv`
  Data iklim hasil tahap preprocessing.

* `NASA_POWER_CLEAN (1).csv`
  Data iklim yang telah dibersihkan dan disiapkan untuk analisis.

* `Rekap_Kesesuaian_Akhir_Kimpul.csv`
  Rekapitulasi kelas kesesuaian akhir S1, S2, S3, dan N.

* `Rekap_Faktor_Pembatas_Kimpul.csv`
  Rekapitulasi kombinasi faktor pembatas yang ditemukan pada titik pengamatan.

* `Rekap_Faktor_Pembatas_Per_Parameter.csv`
  Rekapitulasi distribusi faktor pembatas berdasarkan masing-masing parameter.

### `soilgrids/`

Berisi raster parameter tanah wilayah Kabupaten Magelang hasil pengolahan SoilGrids dalam format GeoTIFF.

Parameter yang tersedia:

* `Magelang_pH.tif`
* `Magelang_Clay.tif`
* `Magelang_Sand.tif`
* `Magelang_Silt.tif`
* `Magelang_SOC.tif`
* `Magelang_CEC.tif`
* `Magelang_Bulk.tif`

Parameter tersebut digunakan untuk menggambarkan karakteristik fisik dan kimia tanah yang meliputi pH, clay, sand, silt, Soil Organic Carbon (SOC), Cation Exchange Capacity (CEC), dan bulk density.

### `DATA BPS/`

Berisi data statistik wilayah yang digunakan sebagai informasi pendukung penelitian.

* `kabupaten-magelang-dalam-angka-2025.pdf`

### `Jurnal/`

Berisi literatur dan referensi yang digunakan dalam penyusunan penelitian, termasuk literatur mengenai evaluasi lahan, SoilGrids, GeoAI, ketahanan pangan, dan topik terkait.

### `Alur Penelitian.jpg`

Berisi diagram alur penelitian yang menggambarkan tahapan pengolahan data dari input hingga menghasilkan klasifikasi dan peta kesesuaian lahan.

##  Tahapan Analisis

Secara umum, alur pengolahan data dalam repository ini meliputi:

1. **Persiapan dan instalasi library**
2. **Pengolahan data iklim NASA POWER**
3. **Pembersihan dan penyesuaian variabel iklim**
4. **Pengambilan data tanah dari SoilGrids**
5. **Penentuan batas wilayah Kabupaten Magelang**
6. **Pengolahan tujuh parameter tanah**
7. **Ekspor data tanah dalam format GeoTIFF**
8. **Ekstraksi nilai raster menjadi data titik**
9. **Penambahan koordinat Latitude dan Longitude**
10. **Agregasi data iklim periode 2020–2025**
11. **Penggabungan data tanah dan iklim**
12. **Analisis statistik deskriptif**
13. **Klasifikasi parameter ke dalam kelas S1, S2, S3, dan N**
14. **Klasifikasi tekstur tanah**
15. **Penentuan kelas kesesuaian akhir berdasarkan faktor pembatas**
16. **Identifikasi faktor pembatas utama**
17. **Pemetaan spasial kesesuaian lahan**
18. **Rekapitulasi hasil kesesuaian dan faktor pembatas**

##  Parameter Kesesuaian

Parameter yang digunakan dalam klasifikasi meliputi:

| Kelompok | Parameter    |
| -------- | ------------ |
| Tanah    | pH           |
| Tanah    | Clay         |
| Tanah    | Sand         |
| Tanah    | Silt         |
| Tanah    | SOC          |
| Tanah    | CEC          |
| Tanah    | Bulk Density |
| Iklim    | Suhu         |
| Iklim    | Curah Hujan  |

Data kelembapan udara dan kelembapan tanah juga digunakan sebagai informasi pendukung dalam menggambarkan kondisi iklim wilayah penelitian.

##  Klasifikasi Kesesuaian

Hasil klasifikasi menggunakan empat kelas:

* **S1** — Sangat sesuai
* **S2** — Cukup sesuai
* **S3** — Sesuai marginal
* **N** — Tidak sesuai

Kelas kesesuaian akhir pada setiap titik ditentukan berdasarkan **parameter dengan tingkat pembatas paling berat**.

##  Pemetaan Spasial

Hasil klasifikasi akhir divisualisasikan dalam bentuk peta spasial interaktif menggunakan **Folium**. Setiap titik pengamatan diberi kelas kesesuaian berdasarkan hasil analisis sehingga pola persebaran S1, S2, S3, dan N dapat diamati secara spasial.

##  Tools dan Library

Pengolahan data dilakukan menggunakan Python dengan beberapa library, antara lain:

* Python
* Pandas
* NumPy
* Matplotlib
* Rasterio
* rioxarray
* SoilGrids
* Google Earth Engine
* geemap
* Folium

##  Output Penelitian

Repository ini menghasilkan beberapa keluaran utama:

* Dataset tanah hasil ekstraksi raster.
* Dataset iklim hasil preprocessing dan agregasi.
* Statistik deskriptif parameter tanah dan iklim.
* Distribusi kelas kesesuaian setiap parameter.
* Kelas kesesuaian akhir setiap titik pengamatan.
* Rekapitulasi faktor pembatas.
* Peta spasial kesesuaian lahan kimpul.
* Data hasil analisis dalam format CSV.

##  Sumber Data

Data penelitian berasal dari beberapa sumber, termasuk:

* **SoilGrids / ISRIC – World Soil Information** untuk parameter tanah.
* **NASA POWER** untuk data iklim.
* **Badan Pusat Statistik Kabupaten Magelang** untuk data statistik wilayah.
* Dataset batas administrasi yang digunakan dalam proses penentuan wilayah penelitian.

##  Catatan

Beberapa proses dalam notebook memerlukan koneksi ke layanan eksternal seperti **Google Earth Engine** dan **SoilGrids**. Oleh karena itu, notebook mungkin memerlukan autentikasi dan penyesuaian konfigurasi sebelum dapat dijalankan kembali secara penuh.
Dataset dan kode dalam repository ini disusun sebagai bagian dari dokumentasi dan reproducibility penelitian **Analisis Kesesuaian Lahan Kimpul di Kabupaten Magelang**.
