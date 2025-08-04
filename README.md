# BAB I. PENDAHULUAN
## 1.1 Latar Belakang Masalah

Indonesia merupakan negara dengan ekosistem mangrove terbesar di dunia, mencakup 23% dari total luas mangrove global atau sekitar 3,7 juta hektare. Ekosistem ini memiliki fungsi ekologis dan ekonomi yang sangat vital, seperti perlindungan pantai, sekuestrasi karbon, habitat biodiversitas, dan sumber ekonomi masyarakat pesisir. Namun, sejak 1980, Indonesia telah kehilangan sekitar 40% hutan mangrovenya akibat konversi lahan, polusi, serta kurangnya kesadaran masyarakat dan dukungan teknologi konservasi.
Dalam dekade terakhir, konsep ekonomi karbon semakin berkembang, dan mangrove telah diakui sebagai salah satu ekosistem penyerap karbon (blue carbon) paling efisien. Namun, tantangan serius muncul dalam aspek transparansi, legalitas, pemantauan, serta pendanaan konservasi. Di sinilah teknologi blockchain muncul sebagai solusi potensial. Blockchain menyediakan mekanisme pencatatan yang transparan, tidak dapat diubah (immutable), serta dapat diverifikasi untuk semua transaksi lingkungan, termasuk perdagangan kredit karbon dan keterlibatan masyarakat.

Proyek MangroveChain hadir sebagai sistem analitik dan teknologi berbasis blockchain yang dirancang untuk mendukung konservasi mangrove secara menyeluruh dari Aceh hingga Papua. Platform ini mengintegrasikan 14 dimensi data penting yang mencakup pemantauan ekologi, transaksi karbon, legalitas lahan, hingga distribusi manfaat ekonomi bagi komunitas lokal. Dengan kemampuan ini, MangroveChain menjadi alat strategis dalam menjawab tantangan konservasi mangrove berbasis sains dan teknologi mutakhir.

CTO perlu memahami pola berbagi data blockchain untuk mengoptimalkan arsitektur sistem:
- Distribusi tipe data (Geografis/Personal/Transaksi) per wilayah
- Korelasi antara level akses dengan volume transaksi karbon
- Pola temporal penerbitan izin vs aktivitas blockchain
- Analisis awal menunjukkan proyek dengan data geografis terbuka memiliki volume transaksi 2.5x lebih tinggi.

Analisis yang perlu dilakukan oleh CTO ini bukan sekadar optimasi teknis, melainkan sebuah fondasi strategis untuk memastikan keberhasilan dan skalabilitas platform konservasi mangrove berbasis blockchain. Masalah intinya terletak pada ketidakselarasan antara potensi teknologi blockchain (transparansi, imutabilitas) dengan realitas implementasi di lapangan yang kompleks dan beragam.

### 1. Dilema Transparansi vs. Keamanan Data Sensitif
Temuan awal bahwa proyek dengan data geografis terbuka memiliki volume transaksi 2.5x lebih tinggi adalah pedang bermata dua dan menjadi inti dari dilema strategis CTO.
Sisi Positif (Mengapa Volume Naik): Transparansi data geografis (misalnya, poligon area konservasi, titik koordinat pemantauan) secara drastis meningkatkan kepercayaan (trust) dari para pemangku kepentingan. Pembeli kredit karbon, investor, dan lembaga donor dapat secara independen memverifikasi klaim proyek di lapangan menggunakan citra satelit atau drone. Kepercayaan inilah yang mendorong partisipasi dan meningkatkan volume transaksi. Ini mengubah kredit karbon dari aset abstrak menjadi sesuatu yang "nyata" dan dapat diverifikasi.

Sisi Negatif (Risiko yang Muncul): Di sisi lain, keterbukaan data geografis yang absolut di negara seperti Indonesia dapat menimbulkan risiko. Wilayah konservasi mangrove sering bersinggungan dengan hak ulayat masyarakat adat, rentan terhadap perambahan ilegal, atau tumpang tindih dengan konsesi lain. Mempublikasikan lokasi persis dari area restorasi yang baru dan rentan bisa saja mengundang aktivitas ilegal sebelum ekosistemnya cukup kuat untuk dilindungi.
Oleh karena itu, analisis mengenai distribusi tipe data per wilayah menjadi krusial. CTO harus merancang arsitektur yang tidak hanya "terbuka" atau "tertutup", melainkan arsitektur dengan tingkat transparansi yang dapat dikonfigurasi (configurable transparency). Mungkin beberapa data (seperti batas luar area proyek) bisa bersifat publik, sementara data lain (seperti lokasi pembibitan atau data personal petani) hanya dapat diakses oleh pihak terverifikasi.

### 2. Menghubungkan Aktivitas On-Chain dengan Realitas Off-Chain
Tantangan mendasar lainnya adalah memastikan bahwa aktivitas di dalam blockchain (transaksi, penerbitan token) benar-benar mencerminkan kemajuan konservasi di dunia nyata.
Korelasi Level Akses & Volume Transaksi: Analisis ini bukan hanya tentang melihat siapa yang bertransaksi paling banyak. Ini tentang memahami insentif. Apakah level akses "Auditor Pemerintah" hanya digunakan untuk memantau, ataukah verifikasi dari mereka memicu pencairan dana (transaksi bervolume tinggi)? Jika proyek dengan partisipasi aktif komunitas lokal (yang mungkin memiliki level akses lebih rendah) menunjukkan volume transaksi mikro yang tinggi, ini bisa menandakan sistem distribusi manfaat yang berfungsi baik. Sebaliknya, jika semua volume besar hanya terkonsentrasi pada level akses "Investor", sistem mungkin terlalu top-down dan berisiko gagal di tingkat akar rumput.

Pola Temporal Izin vs. Aktivitas Blockchain: Analisis ini sangat penting untuk efisiensi dan interoperabilitas sistem. Seringkali ada jeda waktu yang signifikan antara penerbitan izin dari pemerintah (aktivitas off-chain) dengan dimulainya proyek di lapangan dan pencatatannya di blockchain (on-chain). Jika analisis menunjukkan jeda rata-rata 6 bulan, CTO bisa merancang fitur "pra-registrasi" atau escrow pintar (smart contract escrow) yang otomatis aktif saat nomor izin resmi dimasukkan ke dalam sistem. Ini dapat mempercepat mobilisasi dana dan meningkatkan efisiensi operasional secara keseluruhan.

### Implikasi Strategis bagi CTO
Berdasarkan pembahasan di atas, latar belakang masalah ini mengarah pada beberapa keputusan arsitektural dan strategis yang fundamental:
- Arsitektur Data yang Fleksibel: Sistem tidak bisa one-size-fits-all. Perlu ada arsitektur yang memungkinkan penerapan kebijakan akses data yang berbeda-beda untuk setiap proyek atau wilayah, tergantung pada konteks sosial dan keamanan lokal.
- Desain Smart Contract yang Adaptif: Smart contract harus dirancang untuk tidak hanya mengeksekusi transaksi finansial, tetapi juga untuk mengelola alur kerja verifikasi yang melibatkan berbagai level akses (Masyarakat -> Manajer Proyek -> Auditor -> Investor).
- Fokus pada Interoperabilitas: Sistem harus memiliki API atau oracle yang kuat untuk dapat menarik data secara andal dari sistem pemerintah (seperti database perizinan) dan sumber data eksternal lainnya (seperti citra satelit) untuk memvalidasi aktivitas on-chain.
- Jadi, analisis jaringan blockchain ini adalah langkah krusial untuk beralih dari sekadar membangun "database konservasi di blockchain" menjadi menciptakan ekosistem digital yang terpercaya, efisien, dan benar-benar berdampak bagi konservasi mangrove di Indonesia.


## 1.2 Identifikasi Masalah
Berdasarkan hasil analisis dan referensi ilmiah dalam tutorial konservasi mangrove serta data lapangan, proyek ini mengidentifikasi permasalahan utama sebagai berikut:
1. Kerusakan Hutan Mangrove yang terus berlangsung akibat konversi lahan dan deforestasi tanpa legalitas yang jelas.
2. Kurangnya transparansi dan akuntabilitas dalam proses konservasi dan perdagangan kredit karbon.
3. Minimnya integrasi teknologi dalam pemantauan dan pelaporan konservasi berbasis data.
4. Ketimpangan distribusi manfaat dari proyek konservasi terhadap komunitas lokal.
5. Tantangan verifikasi dan regulasi dalam skema perdagangan karbon berbasis mangrove.
6. Kebutuhan sistem berbasis data yang komprehensif dan kredibel untuk mendukung keputusan kebijakan konservasi.

## 1.3 Rumusan Masalah
Berdasarkan latar belakang dan identifikasi di atas, rumusan masalah yang menjadi fokus kajian dan pengembangan sistem MangroveChain adalah:
1. Bagaimana membangun sistem berbasis blockchain yang dapat menjamin integritas dan transparansi dalam pengelolaan proyek konservasi mangrove?
2. Bagaimana platform ini dapat mengukur efektivitas konservasi berdasarkan indikator ekologis, legalitas, partisipasi masyarakat, dan dampak ekonomi?
3. Bagaimana sistem dapat mendukung proses validasi kredit karbon dan memastikan distribusi manfaat yang adil dan terverifikasi?
4. Bagaimana teknologi analitik data dapat digunakan untuk memberikan wawasan strategis kepada pemangku kepentingan dari 30 proyek konservasi?

# BAB II. PEMBAHASAN

## 2.1 Deskripsi Proyek MangroveChain

Proyek MangroveChain adalah sebuah inisiatif konservasi berbasis teknologi yang memanfaatkan sistem blockchain untuk mendokumentasikan, memverifikasi, dan mengoptimalkan proyek mangrove di Indonesia. Platform ini tidak hanya mencatat transaksi karbon, tetapi juga menganalisis efektivitas regulasi, distribusi manfaat sosial, struktur legalitas lahan, dan efisiensi pendanaan dari 30 proyek konservasi mangrove yang tersebar dari Aceh hingga Papua.
Sistem ini memanfaatkan integrasi 14 tabel data yang dikembangkan dari dimensi: lingkungan (biodiversity dan kualitas air), legalitas (izin dan kepemilikan), sosial (keterlibatan masyarakat), dan transaksi digital (blockchain dan smart contract). Analisis dilakukan secara real-time menggunakan SQL, Python, dan visualisasi interaktif seperti heatmap, scatter plot 3D, time-series ARIMA, dan network graph berbasis PyVis.

## 2.2 Tujuan dan Lingkup Proyek MangroveChain

Tujuan Proyek MangroveChain:
1. Menganalisis korelasi antara regulasi, struktur kepemilikan, dan biodiversitas.
2. Menilai efisiensi penggunaan dana berbasis blockchain dan dampak karbonnya.
3. Memprediksi keberhasilan konservasi berdasarkan partisipasi komunitas.
4. Mengidentifikasi proyek dengan risiko hukum tertinggi berdasarkan faktor multi-dimensi.
5. Mengoptimalkan arsitektur jaringan data blockchain dan smart contract konservasi.

Lingkup Proyek
- Wilayah Implementasi: 30 lokasi proyek konservasi mangrove dari Aceh, Kalimantan Barat, Sulawesi, Nusa Tenggara hingga Papua.
- Dimensi Analisis:
  - Lingkungan: Luas rehabilitasi, kualitas air, keanekaragaman spesies.
  - Sosial: Jumlah peserta komunitas, nilai manfaat yang diterima.
  - konomi: Volume dan nilai perdagangan kredit karbon
  - Legal: Status izin, batas lahan, dokumen hukum.
- Teknologi: Blockchain, GIS, drone, dan sistem pelaporan berbasis dashboard.
- Pemangku Kepentingan: Masyarakat lokal, KLHK, lembaga donor, investor karbon, akademisi, dan pemerintah daerah.

------------

# PEMBAHASAN TOPIC PERMASALAHAN

## Studi Kasus 1 : Analisis Efektivitas Regulasi & Dampak Biodiversitas

### Latar Belakang Masalah
Tim konservasi menemukan variasi signifikan dalam hasil monitoring biodiversitas di berbagai proyek. Di Kalimantan Timur, proyek dengan izin disetujui menunjukkan kerapatan pohon 40% lebih tinggi dibandingkan proyek dengan status pending, sementara di Jawa, kualitas air tetap buruk meskipun izin sudah disetujui. Analisis ini bertujuan mengungkap pola sistemik bagaimana kerangka regulasi dan struktur kepemilikan lahan mempengaruhi hasil konservasi.

### Pertanyaan Kunci
- Apakah status persetujuan izin berkorelasi dengan peningkatan biodiversitas yang terukur (kualitas air, kerapatan pohon)?
- Bagaimana pengaturan kepemilikan lahan yang berbeda (negara, swasta, masyarakat) mempengaruhi keanekaragaman spesies?
- Apakah proyek dengan batas lahan yang terdefinisi secara hukum mencapai hasil ekologis yang lebih baik?

## Pembahasan Analisa dengan Query SQL

### Topic : Apakah status persetujuan izin berkorelasi dengan peningkatan biodiversitas yang terukur (kualitas air, kerapatan pohon)?

    SELECT
      rp.Permit_Status AS "Status Izin",
      AVG(bm.Tree_Density) AS "Rata-Rata Kerapatan Pohon",
      AVG(
        CASE
          WHEN bm.Water_Quality = 'Good' THEN 3
          WHEN bm.Water_Quality = 'Moderate' THEN 2
          WHEN bm.Water_Quality = 'Poor' THEN 1
          ELSE 0
        END
      ) AS "Skor Rata-Rata Kualitas Air",
      COUNT(*) AS "Jumlah Proyek"
    FROM
      regulatory_permits AS rp
    INNER JOIN
      biodiversity_monitoring AS bm ON rp.Conservation_ID = bm.Conservation_ID
    GROUP BY
      rp.Permit_Status
    ORDER BY
      "Rata-Rata Kerapatan Pohon" DESC;
Output data:
<img width="521" height="64" alt="image" src="https://github.com/user-attachments/assets/b2feb856-88fa-4964-966a-726b5663bdf4" />

#### Tujuan Utama
Tujuan utama dari SQL query ini adalah untuk menganalisis pengaruh status izin konservasi terhadap indikator lingkungan, yaitu:
- Kerapatan pohon
- Kualitas air
- Jumlah proyek konservasi

Query ini merangkum data biodiversitas berdasarkan status perizinan, untuk mengetahui apakah status izin tertentu cenderung berkorelasi dengan kondisi lingkungan yang lebih baik atau buruk.

Struktur Konsep dan Cara Kerja Query
#### 1. SELECT Clause
- Mengambil status izin konservasi.
- Menghitung rata-rata dari kerapatan pohon.
- Mengkonversi kualitas air ke bentuk skor numerik (3 = Baik, 2 = Sedang, 1 = Buruk), lalu diambil rata-ratanya.
- Menghitung jumlah proyek untuk masing-masing status izin.

#### 2. JOIN Clause
Menggabungkan dua tabel: regulatory_permits (izin) dan biodiversity_monitoring (lingkungan) berdasarkan Conservation_ID.

#### 3. GROUP BY
Mengelompokkan hasil berdasarkan status izin konservasi seperti Approved, Pending, atau Denied.

#### 4. ORDER BY
Mengurutkan hasil dari status izin dengan kerapatan pohon tertinggi ke terendah.

#### Manfaat Analisa
- Analisa ini sangat bermanfaat untuk:
- Mengevaluasi efektivitas kebijakan izin konservasi terhadap kondisi lingkungan.
- Menunjukkan apakah proyek dengan status izin tertentu (misalnya disetujui) cenderung menjaga biodiversitas dengan lebih baik.
- Memberikan bukti berbasis data untuk perbaikan kebijakan perizinan dan pengawasan.

#### Interpretasi:
- Proyek dengan izin "Approved" memiliki rata-rata kerapatan pohon dan kualitas air lebih tinggi dibandingkan proyek lain.
- Proyek tanpa izin yang disetujui mungkin memiliki dampak lingkungan lebih negatif.
- Skor kualitas air mendekati 3 berarti semakin baik.

#### Rekomendasi Analisa
- Prioritaskan pengawasan pada proyek yang izinnya ditolak atau belum disetujui, karena mereka menunjukkan indikasi dampak ekologis lebih buruk.
- Gunakan hasil ini untuk menetapkan kriteria izin yang lebih ketat, misalnya hanya menyetujui proyek yang memiliki rencana konservasi jangka panjang.
- Lakukan pemantauan berkala pada proyek dengan skor kualitas air rendah untuk mencegah kerusakan lebih lanjut.
- Buat laporan visual tambahan, misalnya grafik batang atau heatmap, untuk mempermudah pemahaman bagi pihak non-teknis atau pemangku kebijakan.

## Heatmap Matriks Korelasi Faktor Regulasi vs Metrik Biodiversitas
    import pandas as pd
    import psycopg2
    from sqlalchemy import create_engine
    import matplotlib.pyplot as plt
    import seaborn as sns
    import numpy as np
    
    # Setup koneksi database
    conn_string = "postgresql://postgres:postgresql@localhost:5432/postgres"
    db = create_engine(conn_string)
    conn = db.connect()
    
    # Query data untuk visualisasi
    query = """
    SELECT rp.Permit_Status, ltr.Land_Type, ltr.Boundary_Defined,
    bm.Species_Count, bm.Tree_Density,
    CASE WHEN bm.Water_Quality = 'Good' THEN 3
    WHEN bm.Water_Quality = 'Moderate' THEN 2
    ELSE 1 END AS Water_Quality
    FROM regulatory_permits rp
    JOIN land_tenure_records ltr ON rp.Conservation_ID = ltr.Conservation_ID
    JOIN biodiversity_monitoring bm ON rp.Conservation_ID = bm.Conservation_ID
    """
    
    df = pd.read_sql(query, conn)
    conn.close()
    
    # Langkah 1: One-hot encoding kolom kategorikal
    df_encoded = pd.get_dummies(df, columns=['permit_status', 'land_type', 'boundary_defined'])
    
    # Langkah 2: Hitung korelasi antar semua kolom numerik
    corr_matrix = df_encoded.corr()
    
    # Langkah 3: Pilih hanya korelasi antara faktor regulasi dan metrik biodiversitas
    biodiversity_metrics = ['species_count', 'tree_density', 'water_quality']
    regulation_vars = [col for col in df_encoded.columns if col not in biodiversity_metrics]
    
    # Filter: ambil baris dari regulation_vars dan kolom dari biodiversity_metrics
    filtered_corr = corr_matrix.loc[regulation_vars, biodiversity_metrics]
    
    # Langkah 4: Visualisasi heatmap
    plt.figure(figsize=(10, 6))
    sns.heatmap(
        filtered_corr,
        annot=True,
        cmap='coolwarm',
        center=0,
        fmt='.2f',
        linewidths=0.5,
        linecolor='black',
        cbar_kws={'label': 'Koefisien Korelasi'}
    )
    
    plt.title('Korelasi Faktor Regulasi dengan Metrik Biodiversitas', fontsize=14, pad=20)
    plt.xticks(fontsize=10, rotation=45, ha='right')
    plt.yticks(fontsize=10, rotation=0)
    plt.tight_layout()
    plt.show()
<img width="972" height="598" alt="image" src="https://github.com/user-attachments/assets/23ed79dd-9476-4f03-8f2e-c817af675ad1" />

# Analisis Korelasi Faktor Regulasi terhadap Metrik Biodiversitas

Script ini digunakan untuk menganalisis **hubungan antara kebijakan/regulasi konservasi** (seperti status izin dan jenis kepemilikan lahan) dengan **indikator biodiversitas** (jumlah spesies, kerapatan pohon, dan kualitas air) menggunakan data dari database PostgreSQL. Hasil analisis divisualisasikan dalam bentuk **heatmap korelasi** agar lebih mudah dipahami.


## Konsep Cara Kerja Script

### 1. **Koneksi ke Database PostgreSQL**
Script terhubung ke database lokal PostgreSQL untuk mengambil data yang dibutuhkan. Koneksi dibuat menggunakan sqlalchemy dan psycopg2.

### 2. **Mengambil Data dari Tiga Tabel**
Data diambil menggunakan query SQL dari tiga tabel:
- regulatory_permits → informasi status perizinan konservasi.
- land_tenure_records → jenis dan batas kepemilikan lahan.
- biodiversity_monitoring → data biodiversitas seperti jumlah spesies, kepadatan pohon, dan kualitas air.
Data dari ketiga tabel ini di-*join* berdasarkan Conservation_ID.

### 3. **Transformasi Data Kategorikal**
Kolom-kolom kategorikal seperti permit_status, land_type, dan boundary_defined diubah menjadi format numerik menggunakan **One-Hot Encoding**, agar bisa dihitung korelasinya.

### 4. **Menghitung Korelasi**
Dengan menggunakan .corr(), script menghitung **matriks korelasi Pearson** antar semua kolom numerik, termasuk hasil encoding dan metrik biodiversitas.

### 5. **Filter Korelasi Tertentu**
Script hanya mengambil bagian dari matriks korelasi yang menunjukkan hubungan antara:
- Variabel regulasi (permit, tipe lahan, batas lahan)
- Indikator biodiversitas (species_count, tree_density, water_quality)

### 6. **Visualisasi dengan Heatmap**
Menggunakan seaborn.heatmap(), hubungan tersebut divisualisasikan dalam **heatmap** untuk memperlihatkan kekuatan dan arah korelasi.

## Tujuan Script Ini
- Mengetahui apakah kebijakan/regulasi konservasi berdampak pada biodiversitas.
- Membantu pengambilan keputusan dalam manajemen konservasi berbasis data.
- Menyajikan hasil analisis dalam visual yang jelas dan mudah dipahami.


## Hasil Analisa (Heatmap Korelasi)

Output dari script ini adalah sebuah **heatmap** yang memperlihatkan:
- **Kekuatan hubungan** antara faktor regulasi dan indikator biodiversitas.
- **Arah hubungan** (positif atau negatif).

### Interpretasi Nilai Korelasi:
| Nilai Korelasi | Interpretasi             |
|----------------|--------------------------|
| > 0.7 / < -0.7 | Korelasi kuat            |
| 0.3 - 0.7      | Korelasi sedang          |
| < 0.3          | Korelasi lemah/tidak ada |

Contoh:
- Korelasi 0.65 antara permit_status_Approved dan species_count → status izin yang disetujui berkorelasi positif sedang-kuat terhadap jumlah spesies.
- Korelasi -0.50 antara land_type_Private dan water_quality → lahan privat memiliki hubungan negatif terhadap kualitas air.

## Kesimpulan
Heatmap ini menunjukkan korelasi antara faktor regulasi (seperti status izin, tipe kepemilikan lahan, dan keberadaan batas wilayah) dengan metrik biodiversitas (jumlah spesies, kepadatan pohon, dan kualitas air). Nilai korelasi berkisar dari -1 hingga 1, di mana:
- Positif (+) → hubungan searah: jika satu naik, yang lain cenderung naik juga.
- Negatif (–) → hubungan berlawanan: jika satu naik, yang lain cenderung turun.
- Semakin mendekati 0 → hubungan lemah atau tidak ada hubungan.

Berikut penjelasan per faktor:
#### Status Izin (permit_status)
Approved:
- tree_density: korelasi negatif kuat (-0.20) → wilayah dengan izin disetujui cenderung memiliki kepadatan pohon lebih rendah.
- water_quality: korelasi positif (+0.14) → sedikit peningkatan kualitas air.
- species_count: korelasi lemah (-0.06) → tidak signifikan.

Pending:
- tree_density: korelasi positif (+0.20) → menunggu izin justru berkaitan dengan kepadatan pohon yang lebih tinggi.
- water_quality: negatif (-0.14) → kualitas air cenderung menurun.
- species_count: positif lemah (+0.06) → hampir netral.

#### Tipe Kepemilikan Lahan (land_type)
Community Land:
- tree_density: korelasi positif tertinggi (+0.21) → lahan komunitas mendukung kepadatan pohon.
- species_count: positif (+0.11) → cenderung lebih banyak spesies.
- water_quality: hampir netral (-0.02).

Private Land:
- water_quality: positif (+0.13) → kualitas air relatif baik.
- Korelasi lainnya lemah dan mendekati nol.

State Land:
- Korelasi negatif di ketiga metrik, terutama tree_density (-0.14), menunjukkan potensi degradasi dalam kawasan milik negara.

#### Batas Wilayah Terdefinisi (boundary_defined)
Yes:
- water_quality: korelasi positif (+0.13) → adanya batas wilayah berhubungan dengan kualitas air lebih baik.
- species_count dan tree_density: korelasi lemah positif.

No:
- water_quality: korelasi negatif (-0.13) → kualitas air menurun bila batas tidak jelas.
- Korelasi lainnya juga sedikit negatif.

#### Kesimpulan Umum
- Faktor regulasi memang berpengaruh, tapi sebagian besar korelasinya lemah.
- Lahan komunitas dan izin yang belum disetujui justru berkaitan dengan kepadatan pohon yang lebih tinggi, mungkin karena belum terjadi intervensi pembangunan.
- Kehadiran batas wilayah tampaknya mendukung kualitas air, mungkin karena pengelolaan lebih teratur.
- Lahan negara menunjukkan hasil negatif di semua metrik, yang bisa menandakan kurangnya perlindungan atau pengelolaan efektif.

------------

## Studi Kasus 2 : Optimalisasi Pendanaan Berbasis Blockchain

### Latar Belakang Masalah
Investor dampak semakin membutuhkan bukti terverifikasi tentang dampak lingkungan dan integritas data. Sebuah konsorsium investor hijau telah mengalokasikan $15 juta untuk proyek mangrove tetapi membutuhkan jaminan bahwa dana akan mendukung proyek dengan:
- Perlindungan data blockchain yang kuat (enkripsi tinggi)
- Persetujuan masyarakat yang terdokumentasi
- Efisiensi penyerapan karbon yang terbukti

### Persyaratan Analisis
- Kuantifikasi penyerapan CO2 per juta Rupiah yang diinvestasikan
- Verifikasi kepatuhan tata kelola data blockchain
- Identifikasi proyek berkinerja terbaik yang memenuhi semua kriteria

## Pembahasan Analisa dengan Query SQL

### Topic 1 : Kuantifikasi penyerapan CO2 per juta Rupiah yang diinvestasikan
    SELECT
      fs.Conservation_ID,
      fs.Source_Name AS "Sumber Dana",
      fs.Amount_IDR,
      ei.CO2_Sequestration_Tonnes,
      ei.CO2_Sequestration_Tonnes / (fs.Amount_IDR/1000000) AS "CO2_per_juta_IDR",
      ei.Impact_Type
    FROM
      funding_sources fs
    JOIN
      environmental_impact ei ON fs.Conservation_ID = ei.Conservation_ID
    WHERE
      ei.Impact_Type = 'Carbon Storage'
    ORDER BY
      "CO2_per_juta_IDR" DESC;
  Output file:
  <img width="699" height="83" alt="image" src="https://github.com/user-attachments/assets/267fd1d8-83b0-456f-b8c2-29b2c70a478a" />

### Analisis Efisiensi Pendanaan Konservasi terhadap Penyerapan Karbon
SQL ini dirancang untuk **mengevaluasi seberapa efisien dana konservasi digunakan dalam menyerap emisi karbon (CO₂)**. Fokus analisa diarahkan pada proyek-proyek konservasi yang berdampak langsung pada **penyimpanan karbon (carbon storage)**, dengan membandingkan jumlah karbon yang berhasil diserap terhadap jumlah dana yang dikeluarkan.

### Tujuan Utama
Tujuan dari analisa ini adalah untuk:
- Mengidentifikasi **proyek konservasi karbon** yang paling **efisien secara anggaran**.
- Menghitung rasio **ton CO₂ yang diserap per satu juta rupiah**.
- Memberikan dasar bagi pengambilan keputusan dalam **alokasi dana konservasi** berdasarkan kinerja aktual.
- Membantu stakeholders memahami nilai ekonomis dari setiap investasi konservasi.


### Struktur Konsep dan Cara Kerja Query

#### 1. **Tabel yang Digunakan**
- `funding_sources`: berisi informasi dana proyek, termasuk ID proyek (`Conservation_ID`), nama sumber dana, dan jumlah dana (`Amount_IDR`).
- `environmental_impact`: mencatat dampak lingkungan dari masing-masing proyek, termasuk jenis dampak (`Impact_Type`) dan jumlah CO₂ yang diserap (`CO2_Sequestration_Tonnes`).

#### 2. **JOIN antar Tabel**
Data digabung berdasarkan `Conservation_ID`, yaitu ID unik dari proyek konservasi, untuk menghubungkan data pendanaan dengan hasil dampak lingkungannya.

#### 3. **Filter Data**
Query hanya memilih data dengan `Impact_Type = 'Carbon Storage'`, sehingga hanya proyek penyimpanan karbon yang dianalisis.

#### 4. **Perhitungan Efisiensi**
Rasio efisiensi dihitung dengan rumus:
CO₂ per 1 juta IDR = Total CO₂ diserap / (Jumlah dana / 1.000.000)
Hasilnya memberikan metrik: **berapa ton CO₂ yang diserap setiap 1 juta rupiah** dana.

#### 5. **Pengurutan Hasil**
Hasil diurutkan dari proyek dengan **efisiensi tertinggi ke terendah**, sehingga proyek paling berdampak langsung terlihat di atas.

#### Manfaat Analisa
- **Mendeteksi proyek konservasi yang hemat biaya** dan berdampak tinggi.
- Memberikan alat ukur objektif untuk **perbandingan antar proyek** berbasis rasio hasil terhadap biaya.
- Menjadi dasar evaluasi dalam pelaporan efektivitas investasi konservasi kepada donor, lembaga pendanaan, dan regulator.
- Memperkuat akuntabilitas dan transparansi dalam program lingkungan berbasis dana publik atau swasta.

#### Interpretasi Hasil
Hasil query akan menampilkan daftar proyek konservasi dengan kolom:
- **Sumber Dana**: dari mana dana berasal.
- **Jumlah Dana (IDR)**: total dana yang digunakan.
- **Penyerapan CO₂**: jumlah karbon yang berhasil diserap (dalam ton).
- **Efisiensi (CO₂ per juta IDR)**: metrik utama untuk analisa.
- **Jenis Dampak**: dalam hal ini selalu `'Carbon Storage'`.

#### Contoh Interpretasi:
| Conservation_ID | Sumber Dana     | Amount_IDR | CO₂ (Ton) | CO₂ per juta IDR |
|-----------------|------------------|------------|-----------|------------------|
| 101             | Lembaga A         | 10.000.000 | 50        | 5.00             |
| 102             | Donatur B         | 20.000.000 | 60        | 3.00             |
| 103             | Pemerintah C      | 15.000.000 | 75        | 5.00             |

Interpretasi:
- Proyek 101 dan 103 memiliki efisiensi yang sama (5 ton per juta IDR), meskipun jumlah CO₂-nya berbeda.
- Proyek 102 terlihat kurang efisien meskipun menyerap karbon dalam jumlah besar, karena biayanya lebih tinggi.

#### Rekomendasi Analisa
Berdasarkan hasil analisa ini, berikut rekomendasi yang dapat diambil:
1. **Prioritaskan proyek dengan efisiensi tinggi** dalam pendanaan selanjutnya, karena mampu menyerap karbon lebih banyak per unit dana.
2. Gunakan hasil ini untuk **membuat klasifikasi proyek**: efisiensi tinggi, sedang, dan rendah.
3. Lakukan investigasi lebih lanjut pada proyek dengan **efisiensi rendah**, untuk mengetahui penyebabnya (misalnya: biaya overhead, lokasi geografis, teknologi yang digunakan).
4. Jadikan metrik ini sebagai bagian dari **framework evaluasi rutin** dalam program konservasi karbon.
5. Gunakan visualisasi tambahan (grafik batang, bubble chart, atau heatmap) untuk menyampaikan hasil ke publik atau pengambil keputusan.

#### Kesimpulan
Analisa ini memberikan **indikator kuantitatif sederhana namun kuat** untuk mengukur efektivitas dana konservasi dalam menyerap karbon. Dengan membandingkan CO₂ per juta IDR, organisasi dapat lebih bijak dalam:
- Menentukan proyek prioritas
- Menyusun anggaran
- Menyampaikan bukti kinerja lingkungan kepada para pemangku kepentingan

### Topic 2 : Persetujuan masyarakat yang terdokumentasi
    WITH compliance_stats AS (
      SELECT
        Conservation_ID,
        COUNT(*) AS total_records,
        SUM(CASE WHEN Encryption_Level = 'High' AND Consent_Obtained = 'Yes' THEN 1 ELSE 0 END) AS compliant_records
      FROM
        blockchain_data_compliance
      GROUP BY
        Conservation_ID
    )
    SELECT
      Conservation_ID,
      total_records,
      compliant_records,
      ROUND((compliant_records::numeric / total_records) * 100, 2) AS compliance_percentage
    FROM
      compliance_stats
    ORDER BY
      compliance_percentage DESC;
Output File : <img width="483" height="84" alt="image" src="https://github.com/user-attachments/assets/38ce9474-c01f-487b-95d2-c6768a34da85" />

### Analisis Kepatuhan Proyek terhadap Standar Keamanan Data Blockchain
Analisa ini berfokus pada pengukuran **tingkat kepatuhan proyek konservasi** terhadap dua indikator utama dalam standar keamanan data blockchain:
1. **Tingkat enkripsi (Encryption Level)** yang harus *tinggi*.
2. **Persetujuan data (Consent Obtained)** yang harus *ada/Yes*.

#### Tujuan Utama
Tujuan dari query ini adalah:
- Mengukur **presentase kepatuhan data** proyek konservasi terhadap standar keamanan berbasis blockchain.
- Mengidentifikasi proyek mana yang sudah memenuhi **standar tertinggi** dalam hal perlindungan data.
- Menyediakan **indikator numerik (dalam persen)** untuk mempermudah pemantauan dan pelaporan tingkat kepatuhan.

### Struktur Konsep dan Cara Kerja
#### 1. **CTE (Common Table Expression): `compliance_stats`**
- Mengelompokkan data dari tabel `blockchain_data_compliance` berdasarkan `Conservation_ID`.
- Untuk setiap proyek:
  - **`total_records`**: jumlah total entri terkait data blockchain.
  - **`compliant_records`**: jumlah entri yang memenuhi syarat:
    - Enkripsi = 'High'
    - Persetujuan = 'Yes'

#### 2. **Perhitungan Presentase Kepatuhan**
- Menghitung **presentase kepatuhan** dengan membagi jumlah data yang memenuhi syarat (`compliant_records`) dengan total data (`total_records`), dikalikan 100 dan dibulatkan ke dua desimal.

#### 3. **Pengurutan Hasil**
- Data diurutkan dari proyek dengan tingkat kepatuhan tertinggi ke yang terendah untuk memudahkan identifikasi proyek paling patuh.

#### Manfaat Analisa
- **Evaluasi akuntabilitas dan keamanan data** dalam proyek konservasi.
- Memberikan dasar untuk **audit teknologi dan kepatuhan digital** terhadap prinsip transparansi dan perlindungan data.
- Membantu organisasi atau regulator dalam **mengidentifikasi risiko pelanggaran privasi atau keamanan data**.
- Mendukung pelaporan ke publik atau donor mengenai tingkat keandalan sistem data berbasis blockchain.

#### Interpretasi Hasil
Tabel hasil akan berisi:
| Conservation_ID | Total Records | Compliant Records | Compliance (%) |
|-----------------|----------------|--------------------|----------------|
| 101             | 10             | 10                 | 100.00         |
| 102             | 8              | 5                  | 62.50          |
| 103             | 12             | 6                  | 50.00          |

#### Penjelasan:
- Proyek dengan **100% kepatuhan** menunjukkan bahwa semua data terenkripsi secara maksimal **dan** memiliki persetujuan data.
- Proyek dengan **<100%** mungkin memiliki:
  - Tingkat enkripsi yang tidak sesuai (Medium/Low).
  - Kurangnya persetujuan data.
- Proyek dengan **0%** sangat rentan terhadap masalah keamanan dan etika data.

#### Rekomendasi
Berdasarkan analisa ini, rekomendasi yang bisa diambil antara lain:
1. **Audit menyeluruh** terhadap proyek dengan kepatuhan rendah untuk memahami akar permasalahan.
2. Terapkan **kebijakan internal** agar semua entri data memiliki enkripsi tinggi dan persetujuan sah.
3. Jadikan **persentase kepatuhan** ini sebagai **Key Performance Indicator (KPI)** untuk evaluasi proyek digital.
4. Lakukan **pelatihan kepada tim teknis dan hukum** terkait pentingnya kepatuhan data digital.
5. Kembangkan sistem **pemberitahuan otomatis** saat entri data baru tidak memenuhi standar keamanan.

#### Kesimpulan
Analisis ini memberikan pandangan yang jelas tentang **sejauh mana proyek konservasi menerapkan keamanan dan etika pengelolaan data** dalam sistem blockchain. Tingkat kepatuhan yang tinggi mencerminkan:
- Kinerja data yang aman
- Proses administrasi yang transparan
- Kepatuhan terhadap prinsip digital governance
Sementara itu, proyek dengan tingkat kepatuhan rendah memerlukan perhatian khusus sebelum berlanjut ke fase pendanaan atau ekspansi.

### Topic 3 : Efisiensi penyerapan karbon yang terbukti
    SELECT
      fs.Conservation_ID,
      fs.Source_Name,
      fs.Amount_IDR,
      ei.CO2_Sequestration_Tonnes,
      ei.CO2_Sequestration_Tonnes / (fs.Amount_IDR/1000000) AS CO2_per_juta_IDR,
      bdc.Encryption_Level,
      bdc.Consent_Obtained
    FROM
      funding_sources fs
    JOIN
      environmental_impact ei ON fs.Conservation_ID = ei.Conservation_ID
    JOIN
      blockchain_data_compliance bdc ON fs.Conservation_ID = bdc.Conservation_ID
    WHERE
      ei.Impact_Type = 'Carbon Storage'
      AND bdc.Encryption_Level = 'High'
      AND bdc.Consent_Obtained = 'Yes'
      AND fs.Amount_IDR >= 50000000
    ORDER BY
      CO2_per_juta_IDR DESC,
      fs.Amount_IDR DESC;
Output File : <img width="824" height="84" alt="image" src="https://github.com/user-attachments/assets/527ff627-8d76-42dc-9e0c-39219dd24460" />

### Analisis Proyek Konservasi Karbon dengan Standar Keamanan Data Tinggi dan Efisiensi Anggaran
SQL ini dirancang untuk **mengidentifikasi proyek konservasi karbon yang memenuhi standar keamanan data blockchain tertinggi**, telah mendapat persetujuan penggunaan data, dan memiliki jumlah dana minimum yang layak. Fokus utamanya adalah **efisiensi penyerapan CO₂ terhadap dana**, hanya untuk proyek yang sudah *terverifikasi secara digital dan aman*.

#### Tujuan Utama
Tujuan dari analisis ini adalah:
- Menilai **efisiensi penyerapan karbon (CO₂)** untuk proyek dengan **enkripsi data tinggi dan persetujuan legal lengkap**.
- Menyaring hanya proyek yang memiliki **pendanaan minimum sebesar 50 juta rupiah**, agar analisis berfokus pada proyek berdampak menengah hingga besar.
- Menyediakan metrik **CO₂ per juta rupiah** sebagai tolok ukur efisiensi lingkungan berbasis keuangan.
- Membantu dalam seleksi dan pembiayaan proyek konservasi berbasis data.

### Struktur Konsep dan Cara Kerja
#### 1. **Tabel yang Digunakan**
- `funding_sources`: menyimpan informasi pendanaan, nama donor, dan ID proyek.
- `environmental_impact`: berisi data dampak lingkungan, termasuk penyerapan karbon (CO₂).
- `blockchain_data_compliance`: mencatat status enkripsi data dan persetujuan penggunaan data.

#### 2. **JOIN dan Filter**
Data digabung menggunakan `Conservation_ID`, lalu difilter dengan kriteria:
- **Jenis dampak** = `'Carbon Storage'`
- **Tingkat enkripsi** = `'High'`
- **Persetujuan data** = `'Yes'`
- **Jumlah dana** ≥ 50 juta IDR

#### 3. **Perhitungan Efisiensi**
Menghitung rasio efisiensi:
CO₂_per_juta_IDR = Total CO₂ diserap / (Jumlah Dana / 1.000.000)

Nilai ini menunjukkan seberapa banyak CO₂ (dalam ton) yang berhasil diserap untuk setiap satu juta rupiah.

#### 4. **Pengurutan Hasil**
- Proyek dengan efisiensi tertinggi ditampilkan paling atas.
- Jika efisiensi sama, proyek dengan dana lebih besar diurutkan terlebih dahulu.

#### Manfaat Analisa
- Menyediakan data terverifikasi yang mendukung **pengambilan keputusan berbasis performa dan kepatuhan data**.
- Menyaring proyek yang sudah **siap didanai dan transparan**, karena telah memenuhi semua aspek keamanan dan legalitas digital.
- Membantu donor, pemerintah, atau investor untuk memilih proyek yang **paling hemat biaya** dan **berdampak maksimal terhadap lingkungan**.
- Memudahkan audit dan pelaporan karena hanya menampilkan proyek yang **memenuhi semua syarat minimum kualitas data dan anggaran**.

#### Interpretasi Hasil
Tabel hasil akan mencantumkan:
| Conservation_ID | Source_Name | Amount_IDR | CO₂ (Ton) | CO₂/Juta IDR | Encryption | Consent |
|-----------------|-------------|------------|-----------|--------------|------------|---------|
| 200             | GreenFund   | 80.000.000 | 100       | 1.25         | High       | Yes     |
| 187             | EcoBank     | 120.000.000| 120       | 1.00         | High       | Yes     |
| 165             | ClimateOrg  | 50.000.000 | 60        | 1.20         | High       | Yes     |

#### Penjelasan:
- Proyek pertama paling efisien (1.25 ton CO₂ per juta IDR).
- Semua proyek memiliki tingkat keamanan data dan persetujuan yang sah.
- Semua proyek memenuhi syarat minimal pendanaan dan bisa dianggap prioritas dalam pemilihan program lanjutan.

#### Rekomendasi
Berdasarkan hasil dan kriteria yang digunakan, beberapa rekomendasi yang dapat diambil:
1. **Fokuskan pendanaan ke proyek dengan efisiensi tinggi**, terutama jika tingkat keamanan data dan persetujuan sudah memenuhi syarat.
2. Jadikan metrik **CO₂/juta IDR** sebagai bagian dari sistem evaluasi rutin proyek konservasi.
3. Terapkan filter keamanan data yang sama dalam proyek-proyek masa depan sebagai standar minimum.
4. Kembangkan laporan publik atau dashboard visual berdasarkan analisis ini agar mudah dipahami oleh pemangku kepentingan non-teknis.
5. Gunakan hasil ini sebagai referensi untuk **pemeringkatan proyek konservasi karbon** di tingkat nasional atau internasional.

#### Kesimpulan
Query ini memberikan metode penyaringan yang sangat terarah dan terukur untuk:
- Menentukan proyek konservasi yang **bernilai tinggi secara lingkungan**,
- Sudah **patuh pada prinsip etika dan keamanan data digital**, serta
- Layak diprioritaskan untuk **alokasi pendanaan** lebih lanjut.
Dengan menggabungkan aspek **efisiensi lingkungan**, **integritas digital**, dan **kelayakan finansial**, analisis ini menciptakan pendekatan yang seimbang antara konservasi, teknologi, dan transparansi.

# Analisis Pendanaan Konservasi terhadap Penyerapan CO₂ dan Keamanan Data
    import pandas as pd
    import psycopg2
    from sqlalchemy import create_engine
    import matplotlib.pyplot as plt
    import seaborn as sns
    import numpy as np
    import plotly.express as px
    
    # Setup koneksi database
    conn_string = "postgresql://postgres:postgresql@localhost:5432/postgres"
    db = create_engine(conn_string)
    conn = db.connect()
    
    # Query data untuk visualisasi
    query = """
    SELECT fs.conservation_id, fs.source_name, fs.amount_idr,
    ei.co2_sequestration_tonnes,
    ei.CO2_Sequestration_Tonnes / (fs.amount_idr/1000000) AS co2_per_juta_idr,
    bdc.encryption_level, bdc.Consent_Obtained
    FROM funding_sources fs
    JOIN environmental_impact ei ON fs.conservation_id = ei.conservation_id
    JOIN blockchain_data_compliance bdc ON fs.Conservation_ID = bdc.conservation_id
    WHERE ei.Impact_Type = 'Carbon Storage'
    """
    
    df = pd.read_sql(query, conn)
    conn.close()
    
    # Konversi Encription_level
    df['encryption_score'] = df['encryption_level'].map({'High': 3, 'Medium' : 2, 'Low' : 1})
    
    #vIsualisasi 3D dengan Plotly
    fig = px.scatter_3d(
        df,
        x = 'amount_idr',
        y = 'co2_sequestration_tonnes',
        z = "encryption_score",
        color = 'source_name',
        size = 'co2_per_juta_idr',
        hover_name= 'conservation_id',
        labels = {
            'amount_idr' : 'Jumlah Dana (IDR)',
            'co2_sequestration_tonnes' : 'Penyerapan CO2 (Dalam Ton)',
            'encryption_score' : 'Tingkat Enkripsi',
            'source_name' : 'Sumber Dana',
            'co2_per_juta_rupiah' : 'Rata-rata CO2/Juta Rupiah'
            },
            title = 'Visualisasi Python: Scatter 3D (Jumlah Dana vs Penyerapan CO2 vs Tingkat Enkripsi'
    )
    # UPDATE LAYOUT
    fig.update_layout(
        scene = dict(
            xaxis_title = 'Jumlah Dana (Juta IDR)',
            yaxis_title = 'Penyerapan CO2',
            zaxis_title = "Tingkat Enkripsi",
            zaxis = dict(tickvals= [1,2,3], ticktext=['Low','medium','High'])
        ),
        margin = dict(l=0, r=0 , b=0, t=30),
        height = 600,
        width = 800
    )
    fig.show()
<img width="809" height="609" alt="image" src="https://github.com/user-attachments/assets/c8879490-8830-4699-8ed0-d5fb5b9ed608" />

## Tujuan Analisis
Analisis ini bertujuan untuk:
- Menilai **seberapa efektif** dana konservasi dalam menyerap karbon (CO₂).
- Mengukur **efisiensi penyerapan karbon** berdasarkan setiap **satu juta rupiah** dana yang dikeluarkan.
- Mengetahui bagaimana **tingkat keamanan data (encryption level)** berhubungan dengan kualitas proyek.
- Menyediakan **visualisasi eksploratif** untuk mendukung pengambilan keputusan yang berbasis data.

## Konsep dan Cara Kerja
### 1. Koneksi ke Database
Data diambil dari database PostgreSQL yang berisi informasi terkait proyek konservasi, dampak lingkungan, dan kepatuhan terhadap standar keamanan data.

### 2. Pengambilan dan Penyatuan Data
Data digabung dari tiga sumber utama:
- **Sumber Dana Konservasi**: Jumlah dana, nama penyumbang, dan ID proyek.
- **Dampak Lingkungan**: Fokus pada **penyerapan CO₂** sebagai indikator manfaat lingkungan.
- **Kepatuhan Blockchain**: Menyediakan informasi tentang **tingkat enkripsi** dan **persetujuan data**.

### 3. Transformasi dan Perhitungan
Beberapa transformasi dilakukan:
- **Konversi kualitas enkripsi** (High, Medium, Low) menjadi skor numerik (3, 2, 1).
- Perhitungan **rasio efisiensi**: seberapa banyak CO₂ yang berhasil diserap untuk setiap **1 juta rupiah** yang digunakan.

### 4. Visualisasi Interaktif 3D
Data divisualisasikan dalam bentuk **grafik scatter 3D** dengan sumbu:
- **X**: Jumlah dana proyek (IDR)
- **Y**: Total penyerapan karbon (Ton CO₂)
- **Z**: Skor enkripsi (1–3)
Ukuran titik menggambarkan efisiensi penyerapan karbon per satu juta rupiah, dan warna dibedakan berdasarkan sumber pendanaan.

## Hasil Analisa
Hasil visualisasi menunjukkan berbagai pola penting:
- Beberapa proyek dengan **dana sedang** memiliki **efisiensi penyerapan karbon yang sangat tinggi**, ditunjukkan oleh ukuran titik yang besar.
- Proyek dengan **skor enkripsi tinggi** cenderung memiliki **kinerja lingkungan yang lebih baik**, menandakan integritas data dan pelaporan yang lebih dapat dipercaya.
- Ada proyek dengan **dana besar** tapi **efisiensi rendah**, yang bisa menjadi perhatian dalam evaluasi keberlanjutan.

## Interpretasi Data
Beberapa interpretasi yang dapat ditarik:
- Proyek dengan **penyerapan CO₂ tinggi dan skor enkripsi tinggi** kemungkinan merupakan proyek yang **berdampak dan aman** secara digital.
- Titik-titik besar menunjukkan proyek **efisien secara anggaran**, dan perlu dijadikan contoh dalam pendanaan berikutnya.
- Banyaknya titik di skor enkripsi rendah bisa mengindikasikan perlunya peningkatan standar keamanan data dalam proyek konservasi.

## Rekomendasi
Berdasarkan temuan dari analisis ini, beberapa rekomendasi yang dapat diberikan adalah:
1. **Dukung proyek yang efisien**, yaitu yang mampu menyerap karbon dengan rasio tinggi terhadap dana yang digunakan.
2. **Naikkan standar keamanan data** (enkripsi) untuk seluruh proyek konservasi, agar transparansi dan kepercayaan publik meningkat.
3. Gunakan hasil analisa ini untuk merancang **kebijakan pendanaan berbasis dampak**, bukan hanya berdasarkan jumlah pengeluaran.
4. Lakukan **monitoring rutin** terhadap proyek yang punya dana besar tapi dampak kecil, untuk evaluasi dan audit.

## Manfaat Analisa
- Memberikan gambaran **multidimensi** antara keuangan, lingkungan, dan keamanan data.
- Membantu stakeholder dan pemangku kebijakan dalam **memprioritaskan alokasi dana** secara strategis.
- Memperkenalkan metode visualisasi yang **interaktif dan modern**, cocok untuk pelaporan ke publik atau presentasi.

## Kesimpulan
1. Hubungan Dana vs Penyerapan CO₂
Terlihat hubungan searah (positif): semakin besar dana yang diberikan, semakin besar penyerapan CO₂.
Titik-titik merah (Kementerian LHK) menunjukkan pendanaan lebih besar dan hasil penyerapan CO₂ lebih tinggi dibandingkan titik-titik biru (Yayasan Hijau).

2. Tingkat Enkripsi dan Efektivitas
Yayasan Hijau (biru) beroperasi pada tingkat enkripsi "High", tetapi hanya mencapai penyerapan CO₂ yang relatif rendah (400–520) dengan dana di bawah 50 juta IDR.
Kementerian LHK (merah) beroperasi pada tingkat enkripsi "Medium", tetapi dengan dana lebih besar (50–70 juta IDR), berhasil mencapai penyerapan CO₂ hingga 700.

Interpretasi: meskipun Yayasan Hijau menjaga keamanan tinggi (High encryption), program mereka tampaknya kurang efektif dalam penyerapan CO₂ dibanding program dari Kementerian LHK yang menggunakan tingkat enkripsi medium tapi memberikan lebih banyak dana.

### Kesimpulan Analisa
- Dana yang lebih besar secara konsisten berasosiasi dengan peningkatan penyerapan CO₂, terlepas dari tingkat enkripsi.
- Tingkat enkripsi tidak terlihat memengaruhi efektivitas secara langsung terhadap penyerapan CO₂ dalam data ini.
- Kementerian LHK menunjukkan performa lebih baik dalam hal efisiensi pendanaan terhadap penyerapan CO₂, walau dengan standar keamanan (enkripsi) yang lebih rendah.
  
------------

## Studi Kasus 3 : Prediksi Kinerja Proyek Berbasis Keterlibatan Masyarakat

### Latar Belakang Masalah
CEO ingin mengembangkan model prediktif untuk mengalokasikan sumber daya secara optimal berdasarkan pola keterlibatan masyarakat dalam 6 bulan pertama proyek. Data historis menunjukkan proyek dengan partisipasi masyarakat di atas 30% memiliki tingkat keberlanjutan 75% lebih tinggi setelah 3 tahun.

### Faktor Analisis
- Frekuensi kegiatan masyarakat (Lokakarya/Konsultasi/Pelatihan)
- Distribusi manfaat ekonomi kepada masyarakat lokal
- Tingkat partisipasi relatif terhadap ukuran komunitas
- Korelasi temporal antara kegiatan dan peningkatan biodiversitas

## Pembahasan Analisa dengan Query SQL

### Topic 1 : Frekuensi kegiatan masyarakat (Lokakarya/Konsultasi/Pelatihan)

    SELECT
      ce.Conservation_ID,
      mc.Location,
      ce.Activity_Type,
      COUNT(*) AS Frequency,
      AVG(ce.Participants) AS Avg_Participants,
      SUM(ce.Benefit_Distributed) AS Total_Benefit
    FROM
      community_engagement ce
    JOIN
      mangrove_conservation_records mc ON ce.Conservation_ID = mc.Conservation_ID
    GROUP BY
      ce.Conservation_ID, mc.Location, ce.Activity_Type
    ORDER BY
      ce.Conservation_ID, Frequency DESC;
    
Output file:
<img width="594" height="84" alt="image" src="https://github.com/user-attachments/assets/81072856-3474-4417-8e31-bff92646499d" />

#### Tujuan Utama
Query ini digunakan untuk menganalisis keterlibatan masyarakat (community engagement) berdasarkan jenis aktivitas (Activity_Type) dalam proyek konservasi mangrove. Hasilnya memberikan insight tentang:
- Seberapa sering tiap aktivitas dilakukan per proyek.
- Rata-rata jumlah peserta per aktivitas.
- Total manfaat ekonomi (dalam bentuk distribusi) dari aktivitas tersebut.

#### Struktur dan Penjelasan Komponen
#### 1. SELECT
- ce.Conservation_ID: Mengidentifikasi proyek konservasi.
- mc.Location: Menyediakan lokasi geografis proyek (dari tabel mangrove_conservation_records).
- ce.Activity_Type: Menunjukkan jenis kegiatan masyarakat (misalnya: pelatihan, pembersihan pantai, dll).
- COUNT(*) AS Frequency: Menghitung berapa kali aktivitas tersebut dilakukan dalam satu proyek.
- AVG(ce.Participants): Menghitung rata-rata jumlah peserta dari kegiatan tersebut.
- SUM(ce.Benefit_Distributed): Menjumlahkan total manfaat yang dibagikan kepada masyarakat dari aktivitas tersebut.

#### 2. FROM & JOIN
Menggabungkan data dari dua tabel:
- community_engagement → berisi data aktivitas masyarakat.
- mangrove_conservation_records → berisi info proyek dan lokasinya.
- Penggabungan berdasarkan Conservation_ID yang sama di kedua tabel.

#### 3. GROUP BY
Pengelompokan data dilakukan per:
- Proyek konservasi (Conservation_ID)
- Lokasi
- Jenis aktivitas
Setiap kombinasi unik akan menjadi satu baris hasil (aggregasi).

#### 4. ORDER BY
Dalam setiap proyek, jenis aktivitas diurutkan berdasarkan frekuensi tertinggi → memberi informasi aktivitas mana yang paling dominan dilakukan.

#### Manfaat Analisis Ini
- Mengidentifikasi aktivitas yang paling sering dilakukan di setiap proyek.
- Menilai partisipasi masyarakat untuk tiap jenis kegiatan.
- Melihat kontribusi ekonomi langsung melalui distribusi manfaat.
- Menyediakan dasar untuk perencanaan ulang kegiatan atau alokasi dana di masa depan.

#### Analisis Hasil:
Dari hasil query terlihat bahwa:
- Frekuensi Seragam: Setiap jenis kegiatan hanya dilakukan sekali per proyek dalam dataset ini
- Partisipasi: Workshop cenderung memiliki peserta lebih banyak (rata-rata 10-15 orang) dibanding konsultasi (8-9 orang)
- Manfaat Ekonomi: Konsultasi memiliki manfaat ekonomi yang lebih besar per kegiatan dibanding jenis lainnya

#### Interpretasi:
Hasil ini menunjukkan bahwa:
- Mungkin ada bias dalam dataset karena setiap jenis kegiatan hanya direkam sekali per proyek
- Workshop lebih efektif dalam menjangkau lebih banyak peserta
- Konsultasi mungkin melibatkan transfer manfaat ekonomi yang lebih signifikan

#### Rekomendasi:
- Diversifikasi Kegiatan: Lakukan lebih banyak variasi kegiatan dalam setiap proyek
- Pelacakan Lebih Detail: Rekam frekuensi kegiatan yang lebih akurat
- Analisis Longitudinal: Lakukan studi lanjutan untuk melihat perkembangan frekuensi kegiatan dari waktu ke waktu

### Topic 2 : Distribusi manfaat ekonomi kepada masyarakat lokal

    SELECT
      ce.Conservation_ID,
      mc.Location,
      SUM(ce.Benefit_Distributed) AS Total_Benefit,
      AVG(ce.Benefit_Distributed) AS Avg_Benefit_Per_Activity,
      SUM(ce.Participants) AS Total_Participants,
      SUM(ce.Benefit_Distributed) / NULLIF(SUM(ce.Participants), 0) AS Benefit_Per_Participant
    FROM
      community_engagement ce
    JOIN
      mangrove_conservation_records mc ON ce.Conservation_ID = mc.Conservation_ID
    GROUP BY
      ce.Conservation_ID, mc.Location
    ORDER BY
      Benefit_Per_Participant DESC;

Output file:
<img width="764" height="82" alt="image" src="https://github.com/user-attachments/assets/ee8abb89-d3a2-45d2-a1c4-d0a6e8d4b6b7" />

#### Tujuan Utama
Query ini dirancang untuk mengukur efektivitas distribusi manfaat dari kegiatan komunitas dalam proyek konservasi mangrove. Fokus utamanya adalah menghitung berapa besar manfaat ekonomi yang diterima rata-rata oleh setiap peserta di setiap proyek.

#### Struktur dan Penjelasan Komponen
#### 1. SELECT
Penjelasan masing-masing kolom hasil:
- ce.Conservation_ID: ID proyek konservasi.
- mc.Location: Lokasi dari proyek konservasi (dari tabel mangrove_conservation_records).
- SUM(ce.Benefit_Distributed) → Total_Benefit: Total manfaat ekonomi (misal dalam rupiah) yang didistribusikan untuk satu proyek.
- AVG(ce.Benefit_Distributed) → Avg_Benefit_Per_Activity: Rata-rata manfaat ekonomi per aktivitas dalam proyek.
- SUM(ce.Participants) → Total_Participants: Jumlah total peserta dalam seluruh aktivitas proyek.
- SUM(ce.Benefit_Distributed) / NULLIF(SUM(ce.Participants), 0) → Benefit_Per_Participant: Rata-rata manfaat yang diterima per peserta. NULLIF() digunakan untuk mencegah pembagian dengan nol (jika tidak ada peserta sama sekali).

#### 2. FROM & JOIN
Menggabungkan dua tabel:
- community_engagement (ce): Data keterlibatan masyarakat.
- mangrove_conservation_records (mc): Informasi proyek konservasi.
- Disatukan berdasarkan Conservation_ID untuk menggabungkan informasi lokasi proyek dengan aktivitas yang dilakukan.

#### 3. GROUP BY
Hasilnya: setiap baris mewakili satu proyek konservasi di satu lokasi tertentu.

#### 4. ORDER BY
Mengurutkan hasil berdasarkan manfaat rata-rata per peserta dari tertinggi ke terendah.
Ini membantu mengidentifikasi proyek mana yang paling efisien dalam memberikan manfaat kepada masyarakat yang terlibat.

#### Manfaat Analisis Ini
- Memberi gambaran nilai ekonomi langsung yang diterima masyarakat per proyek.
- Memungkinkan evaluasi efisiensi sosial tiap proyek (apakah banyak peserta namun manfaatnya kecil, atau sedikit peserta tapi manfaatnya besar).
- Berguna untuk pengambilan keputusan berbasis data, misalnya:
- Proyek mana yang perlu efisiensi distribusi manfaat?
- Di mana distribusi terlalu tersebar/tidak merata?
- Bagaimana standar minimal benefit per peserta bisa diterapkan?

#### Analisis Hasil:
Dari hasil query terlihat bahwa:
- Variasi Manfaat: Manfaat ekonomi per peserta bervariasi dari 400,000 hingga 937,500 IDR
- Proyek Unggulan: Takalar memiliki manfaat per peserta tertinggi (937,500 IDR)
- Trade-off: Proyek dengan peserta lebih banyak cenderung memiliki manfaat per peserta lebih rendah
- Konsistensi: Beberapa proyek memiliki manfaat total yang sama (7,500,000 IDR) meski jumlah peserta berbeda

#### Interpretasi:
Hasil ini menunjukkan bahwa:
- Distribusi manfaat tidak merata antar proyek
- Ada kemungkinan perbedaan strategi distribusi manfaat
- Proyek dengan skala lebih kecil (peserta lebih sedikit) bisa memberikan manfaat lebih besar per orang

#### Rekomendasi:
- Standarisasi Manfaat: Kembangkan pedoman distribusi manfaat yang lebih adil
- Studi Komparatif: Pelajari mengapa proyek tertentu bisa memberikan manfaat lebih besar per peserta
- Monitoring: Lacak dampak manfaat ekonomi terhadap partisipasi jangka panjang

### Topic 3 : Tingkat partisipasi relatif terhadap ukuran komunitas
    WITH community_stats AS (
      SELECT
        ce.Conservation_ID,
        mc.Location,
        COUNT(DISTINCT cm.Member_ID) AS Total_Community_Members,
        SUM(ce.Participants) AS Total_Participants,
        SUM(ce.Participants)*100.0 / NULLIF(COUNT(DISTINCT cm.Member_ID), 0) AS Participation_Percentage
      FROM
        community_engagement ce
      JOIN
        mangrove_conservation_records mc ON ce.Conservation_ID = mc.Conservation_ID
      CROSS JOIN
        community_members cm
      GROUP BY
        ce.Conservation_ID, mc.Location
    )
    SELECT
      Conservation_ID,
      Location,
      Total_Community_Members,
      Total_Participants,
      Participation_Percentage,
      RANK() OVER (ORDER BY Participation_Percentage DESC) AS Participation_Rank
    FROM
      community_stats
    ORDER BY
      Participation_Percentage DESC;
Output File:
<img width="823" height="83" alt="image" src="https://github.com/user-attachments/assets/e68bf1cc-5c1e-43f6-93cc-d82ade14b164" />

#### Tujuan Utama
Query ini digunakan untuk mengukur tingkat partisipasi masyarakat dalam proyek konservasi, dengan membandingkan jumlah peserta kegiatan dengan jumlah total anggota komunitas yang tersedia di setiap proyek. Selain itu, query juga memberi peringkat proyek berdasarkan tingkat partisipasi.

#### Struktur dan Penjelasan Komponen
#### 1. CTE (WITH community_stats AS (...))
CTE atau Common Table Expression ini digunakan untuk menyusun data ringkasan partisipasi komunitas per proyek sebelum dianalisis lebih lanjut.

Penjelasan kolom:
- ce.Conservation_ID: ID proyek konservasi.
- mc.Location: Lokasi proyek.
- COUNT(DISTINCT cm.Member_ID) → Total_Community_Members: Jumlah unik anggota komunitas (menghindari duplikasi).
- SUM(ce.Participants) → Total_Participants: Jumlah total peserta dari semua aktivitas dalam satu proyek.

SUM(...) * 100 / COUNT(...) → Participation_Percentage: Persentase partisipasi, yaitu:

(Total Peserta / Jumlah Anggota Komunitas)
×
100
(Total Peserta / Jumlah Anggota Komunitas)×100
Digunakan NULLIF(..., 0) untuk menghindari pembagian dengan nol jika tidak ada anggota terdaftar.

#### 2. CROSS JOIN
CROSS JOIN menyebabkan setiap baris dari community_engagement digabungkan dengan setiap baris dari community_members. Jika tidak disaring lebih lanjut (misalnya berdasarkan Conservation_ID)

#### 3. GROUP BY
Mengelompokkan data per proyek dan lokasi.
Setiap baris hasilnya mewakili satu proyek konservasi di satu lokasi.

#### 4. Main SELECT
Mengambil semua metrik dari CTE.

RANK() OVER (...) digunakan untuk memberi peringkat proyek berdasarkan tingkat partisipasi dari yang tertinggi ke terendah.

#### 5. ORDER BY
Menampilkan proyek dengan partisipasi tertinggi terlebih dahulu, untuk membantu mengidentifikasi proyek yang paling efektif melibatkan masyarakat.

#### Manfaat Analisis Ini
- Memberikan wawasan tentang seberapa besar keterlibatan masyarakat dalam proyek konservasi.
- Memudahkan dalam mengidentifikasi proyek yang membutuhkan peningkatan partisipasi.
- Mendukung pembuatan kebijakan berbasis data seperti:
- Perluasan komunikasi ke komunitas dengan partisipasi rendah.
- Insentif untuk proyek dengan keterlibatan tinggi.

#### Analisis Hasil:
Dari hasil query terlihat bahwa:
- Partisipasi Tinggi: Semua proyek menunjukkan persentase partisipasi >100% karena jumlah peserta melebihi anggota komunitas
- Data Anggota Terbatas: Hanya 1 anggota komunitas yang tercatat per proyek, menunjukkan kemungkinan ketidaklengkapan data
- Proyek Unggulan: Lampung Barat memiliki partisipasi relatif tertinggi (1500%)

#### Interpretasi:
Hasil ini menunjukkan bahwa:
- Data anggota komunitas mungkin tidak lengkap atau tidak terhubung dengan benar ke proyek
- Partisipasi sebenarnya mungkin jauh lebih rendah dari yang terlihat
- Perlu verifikasi dan pelengkapan data anggota komunitas

#### Rekomendasi:
- Validasi Data: Verifikasi hubungan antara anggota komunitas dan proyek
- Pelengkapan Data: Tambahkan data anggota komunitas yang lebih lengkap
- Metrik Alternatif: Pertimbangkan metrik partisipasi absolut jika data relatif tidak akurat

### Topic 4 : Korelasi temporal antara kegiatan dan peningkatan biodiversitas

    WITH activity_stats AS (
      SELECT
        ce.Conservation_ID,
        mc.Location,
        mc.Carbon_Credits,
        COUNT(ce.Engage_ID) AS Activity_Count,
        AVG(ce.Participants) AS Avg_Participants,
        SUM(ce.Benefit_Distributed) AS Total_Benefit,
        AVG(mc.Date_Recorded - ce.Engagement_Date) AS Avg_Days_Between_Activity_And_Record
      FROM
        community_engagement ce
      JOIN
        mangrove_conservation_records mc ON ce.Conservation_ID = mc.Conservation_ID
      GROUP BY
        ce.Conservation_ID, mc.Location, mc.Carbon_Credits
    )
    SELECT
      Conservation_ID,
      Location,
      Carbon_Credits,
      Activity_Count,
      Avg_Participants,
      Total_Benefit,
      Avg_Days_Between_Activity_And_Record,
      CORR(Activity_Count, Carbon_Credits) OVER () AS Correlation_Activity_Carbon
    FROM
      activity_stats
    ORDER BY
      Carbon_Credits DESC;

  Output File:
  <img width="1073" height="85" alt="image" src="https://github.com/user-attachments/assets/cd494f73-b427-4b02-ac91-9b04971f0e67" />

#### Tujuan Utama
Query ini digunakan untuk:
- Menganalisis statistik kegiatan komunitas dalam proyek konservasi.
- Mengukur hubungan (korelasi) antara jumlah kegiatan dan jumlah kredit karbon yang dihasilkan.
- Memberikan gambaran menyeluruh per proyek: intensitas kegiatan, partisipasi, manfaat, efisiensi pencatatan, dan hasil akhir berupa kredit karbon.

#### Struktur dan Penjelasan Komponen
#### 1. CTE (WITH activity_stats AS (...))
Digunakan untuk menyusun data statistik per proyek terlebih dahulu sebelum dianalisis lebih lanjut.

Kolom dalam CTE:
- ce.Conservation_ID: ID proyek konservasi.
- mc.Location: Lokasi proyek.
- mc.Carbon_Credits: Total kredit karbon yang dihasilkan oleh proyek.
- COUNT(ce.Engage_ID) → Activity_Count: Jumlah kegiatan komunitas dalam proyek tersebut.
- AVG(ce.Participants) → Avg_Participants: Rata-rata peserta per kegiatan.
- SUM(ce.Benefit_Distributed) → Total_Benefit: Total manfaat ekonomi (dalam IDR atau satuan lain) yang didistribusikan ke masyarakat.
- AVG(mc.Date_Recorded - ce.Engagement_Date) → Avg_Days_Between_Activity_And_Record: - Rata-rata selisih hari antara tanggal kegiatan dan tanggal pencatatan di sistem.

#### 2. Main SELECT
Mengambil semua kolom dari activity_stats dan menambahkan analisis korelasi:
- CORR(...) OVER (): Fungsi agregat window untuk menghitung korelasi Pearson antara dua variabel:
- Activity_Count: Banyaknya kegiatan
- Carbon_Credits: Kredit karbon yang dihasilkan

Korelasi ini bersifat global (dihitung sekali untuk semua baris) dan ditampilkan di setiap baris.

#### 3. ORDER BY
Mengurutkan hasil dari proyek yang menghasilkan kredit karbon tertinggi ke yang terendah.
Mempermudah identifikasi proyek paling berdampak dari sisi lingkungan.

#### Manfaat Analisis Ini
Evaluasi Efektivitas Proyek:
- Apakah lebih banyak kegiatan komunitas berkontribusi pada lebih banyak kredit karbon?
- Monitoring Pelaksanaan Proyek:
- Cek apakah pencatatan dilakukan tepat waktu (Avg_Days_Between...).

#### Penilaian Dampak Sosial:
- Total manfaat ekonomi (Total_Benefit) bisa jadi indikator pemberdayaan masyarakat.

#### Makna Korelasi
Nilai korelasi (Correlation_Activity_Carbon) berkisar antara:
+1 → Hubungan sangat positif (semakin banyak kegiatan, semakin banyak kredit karbon).
0 → Tidak ada hubungan linier.
-1 → Hubungan sangat negatif (semakin banyak kegiatan, semakin sedikit kredit karbon).

Jika hasilnya misalnya 0.42, maka:

Ada korelasi positif sedang antara jumlah kegiatan dan kredit karbon. Artinya, kegiatan masyarakat kemungkinan berkontribusi terhadap peningkatan karbon terserap, meskipun tidak sepenuhnya linear.

#### Analisis Hasil:
Dari hasil query terlihat bahwa:
- Korelasi Positif: Ada korelasi moderat (0.42) antara jumlah kegiatan dan kredit karbon
- Waktu Respons: Rata-rata pencatatan kredit karbon dilakukan 0-7 hari setelah kegiatan
- Konsistensi: Semua proyek hanya memiliki 1 kegiatan yang tercatat
- Pola Temporal: Tidak ada pola jelas antara waktu kegiatan dan kredit karbon

#### Interpretasi:
Hasil ini menunjukkan bahwa:
- Kegiatan masyarakat mungkin berkontribusi pada peningkatan kredit karbon
- Efek kegiatan terlihat dalam waktu singkat (kurang dari seminggu)
- Data yang terbatas (hanya 1 kegiatan per proyek) membuat analisis temporal kurang akurat

#### Rekomendasi:
- Pelacakan Lebih Lama: Lakukan pencatatan kegiatan dan kredit karbon dalam periode lebih panjang
- Analisis Lanjutan: Gunakan model statistik lebih canggih dengan data lebih banyak
- Studi Lapangan: Verifikasi hubungan kausal antara kegiatan masyarakat dan biodiversitas

## Prediksi Kredit Karbon Berbasis Time Series dengan ARIMA

    import pandas as pd
    import psycopg2
    from sqlalchemy import create_engine
    import matplotlib.pyplot as plt
    import seaborn as sns
    import numpy as np
    from statsmodels.tsa.arima.model import ARIMA
    from xgboost import XGBRegressor
    from sklearn.metrics import mean_squared_error, r2_score
    from sklearn.model_selection import train_test_split

    # Setup koneksi database
    conn_string = "postgresql://postgres:postgresql@localhost:5432/postgres"
    db = create_engine(conn_string)
    conn = db.connect()
    
    # Query data untuk analisis prediktif
    query = """
    SELECT
    ce.Conservation_ID,
    mc.Location,
    COUNT(ce.Engage_ID) AS activity_count,
    AVG(ce.Participants) AS avg_participants,
    SUM(ce.Benefit_Distributed) AS total_benefit,
    AVG(mc.Date_Recorded - ce.Engagement_Date) AS avg_days_to_record,
    mc.Carbon_Credits
    FROM community_engagement ce
    JOIN mangrove_conservation_records mc ON ce.Conservation_ID = mc.Conservation_ID
    GROUP BY ce.Conservation_ID, mc.Location, mc.Carbon_Credits
    """
    
    df = pd.read_sql(query, conn)
    
    # Konversi timedelta ke hari
    df['avg_days_to_record'] = pd.to_timedelta(df['avg_days_to_record'])
    df['avg_days_to_record'] = df['avg_days_to_record'].dt.days

    arima_query = """
    SELECT
    ce.Engagement_Date,
    AVG(mc.Carbon_Credits) AS avg_carbon_credits,
    SUM(ce.Participants) AS total_participants
    FROM community_engagement ce
    JOIN mangrove_conservation_records mc ON ce.Conservation_ID = mc.Conservation_ID
    GROUP BY ce.Engagement_Date
    ORDER BY ce.Engagement_Date
    """
    
    df_1 = pd.read_sql(arima_query, conn)
    conn.close()
    df_1['engagement_date'] = pd.to_datetime(df_1['engagement_date'])
    df_1.set_index('engagement_date', inplace=True)
    
    # #save file
    # df_new.to_csv('file_analisa_arima.csv')
    
    # #load file
    # df_1 = pd.read_csv('file_analisa_arima.csv')
    
    # Visualisasi data time-series
    plt.figure(figsize=(12, 6))
    plt.plot(df_1.index, df_1['avg_carbon_credits'], label='Kredit Karbon')
    plt.plot(df_1.index, df_1['total_participants'], label='Total Peserta')
    plt.title('Trend Kredit Karbon dan Partisipasi Masyarakat')
    plt.xlabel('Tanggal Kegiatan')
    plt.ylabel('Nilai')
    plt.legend()
    plt.grid(True)
    plt.show()
    
    # Model ARIMA
    # Parameter (p,d,q) bisa dioptimalkan lebih lanjut
    model = ARIMA(df_1['avg_carbon_credits'], order=(1, 1, 1))
    model_fit = model.fit()
    
    # Prediksi
    forecast_steps = 5
    forecast = model_fit.get_forecast(steps=forecast_steps)
    forecast_index = pd.date_range(start=df_1.index[-1], periods=forecast_steps+1, freq='D')[1:]
    
    # Visualisasi hasil prediksi
    plt.figure(figsize=(12, 6))
    plt.plot(df_1.index, df_1['avg_carbon_credits'], label='Data Historis')
    plt.plot(forecast_index, forecast.predicted_mean, label='Prediksi', color='red')
    plt.fill_between(forecast_index,
    forecast.conf_int()['lower avg_carbon_credits'],
    forecast.conf_int()['upper avg_carbon_credits'],
    color='pink', alpha=0.3)
    plt.title('Prediksi Kredit Karbon dengan ARIMA')
    plt.xlabel('Tanggal')
    plt.ylabel('Kredit Karbon')
    plt.legend()
    plt.grid(True)
    plt.show()
    
    # Evaluasi model
    print(f"AIC: {model_fit.aic}")
    print(f"Parameter Model: {model_fit.params}")

<img width="1012" height="552" alt="image" src="https://github.com/user-attachments/assets/72de342e-425c-47a0-9872-e127de4b85e5" />

<img width="1011" height="553" alt="image" src="https://github.com/user-attachments/assets/a30193f1-ff4b-4421-8c94-3dad824c2854" />

AIC: 220.68799136046565
Parameter Model: ar.L1       -0.554273
ma.L1       -0.996031
sigma2    3805.257813
dtype: float64

## Prediksi Kredit Karbon Berbasis Time Series dengan ARIMA

Script ini bertujuan untuk:
- Mengambil data kegiatan konservasi dari database,
- Menganalisis tren historis,
- Melakukan prediksi nilai kredit karbon menggunakan model ARIMA.

### 1. Pengambilan dan Penggabungan Data

Langkah pertama adalah mengeksekusi query SQL untuk menggabungkan data dari dua tabel:
- Tabel kegiatan komunitas (community_engagement)
- Tabel rekaman konservasi (mangrove_conservation_records)
- Data dikelompokkan berdasarkan tanggal kegiatan (engagement date), dan diambil:
    - Rata-rata kredit karbon
    - Total peserta
Hasilnya membentuk dataset time series dengan satu baris per tanggal kegiatan.

### 2. Persiapan Data Time Series

Data yang diambil dari database perlu dikonversi:
- Kolom tanggal dikonversi ke format waktu (datetime)
- Ditetapkan sebagai indeks utama dataset
Langkah ini penting karena model prediksi time series seperti ARIMA memerlukan urutan waktu yang eksplisit.

### 3. Visualisasi Tren Historis

Setelah data siap, grafik time series dibuat:
- Menampilkan tren rata-rata kredit karbon dari waktu ke waktu
- Ditampilkan pula total peserta setiap tanggal
- Tujuannya untuk memahami pola data secara visual sebelum melakukan pemodelan, seperti:
    - Apakah terjadi tren naik/turun?
    - Apakah ada fluktuasi ekstrem?

### 4. Pemodelan Time Series dengan ARIMA

Model ARIMA digunakan untuk memprediksi tren ke depan berdasarkan data historis.

ARIMA memiliki 3 parameter:
- p (autoregressive): mempertimbangkan nilai masa lalu
- d (differencing): membuat data stasioner
- q (moving average): mempertimbangkan kesalahan masa lalu

Model dilatih menggunakan data kredit karbon yang telah disiapkan sebelumnya.

### 5. Prediksi ke Depan

Setelah model dilatih, dilakukan prediksi untuk beberapa hari ke depan (misalnya 5 hari).
Model tidak hanya memberikan nilai prediksi, tetapi juga:
- Interval kepercayaan (confidence interval)
- Batas atas dan bawah yang menunjukkan ketidakpastian prediksi

### 6. Visualisasi Hasil Prediksi

Hasil prediksi divisualisasikan:
- Data historis digambarkan sebagai garis utama
- Prediksi digambarkan dalam garis merah
- Area prediksi dibungkus dalam bayangan merah muda (confidence interval)
- Visualisasi ini membantu melihat bagaimana model memperkirakan nilai karbon mendatang.

### HASIL ANALISA

Grafik ini menunjukkan tren Kredit Karbon dan Partisipasi Masyarakat selama periode dari awal tahun 2024 hingga pertengahan 2025. Berikut adalah penjelasan hasil dari grafik tersebut:

#### Kredit Karbon (Garis Biru)
- Fluktuatif: Nilai kredit karbon mengalami fluktuasi yang cukup tajam dari bulan ke bulan.
- Puncak tertinggi terjadi sekitar Juni 2024 (nilai mendekati 400).
- Penurunan drastis tampak setelah bulan-bulan dengan nilai tinggi, misalnya dari Juni ke Juli 2024, dan dari Februari ke Maret 2025.

Tren Umum: Tidak ada tren naik atau turun yang konsisten nilai naik dan turun secara acak, menandakan bahwa produksi atau pencapaian kredit karbon sangat bergantung pada faktor tertentu yang mungkin tidak stabil.

#### Total Peserta (Garis Oranye)
- Stabil Rendah: Jumlah peserta relatif stabil di kisaran 8–15 orang setiap bulannya.
- Peningkatan kecil: Ada sedikit peningkatan partisipasi di beberapa bulan seperti April 2024 dan Februari 2025.
Namun, tidak tampak ada hubungan langsung antara banyaknya peserta dengan naik turunnya nilai kredit karbon.

#### Kesimpulan dan Interpretasi
Kredit karbon tidak selalu sejalan dengan partisipasi masyarakat. Ini bisa berarti:
- Efisiensi kegiatan bervariasi (sedikit peserta bisa menghasilkan kredit karbon tinggi).
- Ada faktor eksternal seperti jenis kegiatan, lokasi, atau teknologi yang memengaruhi output kredit karbon lebih besar dibanding jumlah peserta.

Perlu Evaluasi Program:
- Jika tujuan utama adalah meningkatkan partisipasi, maka pendekatan baru mungkin dibutuhkan.
- Jika fokusnya pada efisiensi hasil karbon, maka strategi yang sudah ada mungkin cukup baik, tetapi perlu dioptimalkan agar lebih konsisten.


### HASIL ANALISA GRAFIK DENGAN MODEL FORECASTING ARIMA

#### Komponen Grafik
- Garis Biru (Data Historis): Menunjukkan nilai aktual kredit karbon dari waktu ke waktu.
- Garis Merah (Prediksi): Prediksi nilai kredit karbon untuk beberapa periode ke depan menggunakan model ARIMA.
- Bayangan Merah Muda: Interval kepercayaan (confidence interval) prediksi memberikan rentang kemungkinan nilai kredit karbon di masa depan.

#### Analisis Hasil
Prediksi Stabil di Sekitar 250–280:
- Model memprediksi nilai kredit karbon akan berfluktuasi sedikit, tetapi berada di sekitar nilai rata-rata historis.
- Tidak ada tren meningkat atau menurun yang jelas model ARIMA memproyeksikan masa depan akan mirip dengan nilai rata-rata masa lalu.

#### Parameter Model (ditampilkan di bawah grafik):
- ar.L1 = -0.554273 → koefisien autoregresif negatif, mengindikasikan bahwa nilai sebelumnya berpengaruh, tetapi dengan arah berlawanan.
- ma.L1 = -0.996031 → komponen moving average mendekati -1, yang menunjukkan pengaruh fluktuasi acak di masa lalu terhadap nilai sekarang.
- AIC = 220.68 → ukuran kebaikan model; makin kecil nilainya, makin baik (tidak dibandingkan di sini, tapi bisa digunakan untuk tuning).
- sigma² ≈ 3805 → menunjukkan varian kesalahan prediksi cukup tinggi, artinya fluktuasi data cukup besar.

#### Kesimpulan
- Prediksi jangka pendek untuk kredit karbon cukup stabil dan konservatif, tanpa ekspektasi lonjakan besar.
- Model ARIMA ini cocok untuk prediksi jangka pendek, tetapi perlu hati-hati karena data historis yang sangat fluktuatif membatasi akurasi.
- Untuk hasil lebih akurat, bisa dipertimbangkan:
    - Menambahkan variabel eksternal (misal jumlah peserta, jenis kegiatan, cuaca).
    - Menggunakan model lanjutan seperti SARIMA, Prophet, atau bahkan machine learning (LSTM, Random Forest) bila data lebih kompleks.

## Prediksi Kredit Karbon dengan XGBoost Regressor

    df = pd.get_dummies(df, columns=['location'])
    
    # Pisahkan fitur dan target
    X = df.drop(['conservation_id', 'carbon_credits'], axis=1)
    y = df['carbon_credits']
    
    # Bagi data menjadi training dan test set
    X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
    
    # Model XGBoost
    xgb_model = XGBRegressor(objective='reg:squarederror', n_estimators=100, random_state=42)
    xgb_model.fit(X_train, y_train)
    
    # Prediksi
    y_pred = xgb_model.predict(X_test)
    
    # Evaluasi model
    mse = mean_squared_error(y_test, y_pred)
    r2 = r2_score(y_test, y_pred)
    
    print(f"Mean Squared Error: {mse:.2f}")
    print(f"R-squared: {r2:.2f}")
    
    # Visualisasi feature importance
    plt.figure(figsize=(10, 6))
    feature_importance = pd.Series(xgb_model.feature_importances_, index=X.columns)
    feature_importance.sort_values().plot(kind='barh')
    plt.title('Feature Importance - XGBoost')
    plt.xlabel('Importance Score')
    plt.tight_layout()
    plt.show()

Mean Squared Error: 342.33
R-squared: 0.85

<img width="989" height="590" alt="image" src="https://github.com/user-attachments/assets/e65f2e5a-ded8-4324-a610-67e72f705c58" />

Script ini bertujuan untuk:
- Mengolah data kategorikal
- Melatih model regresi menggunakan XGBoost
- Mengevaluasi performa model
- Menganalisis fitur yang paling berpengaruh.

#### 1. One-Hot Encoding Lokasi
Pada tahap ini, kolom location yang berisi data kategorikal (teks) dikonversi menjadi format numerik biner menggunakan pd.get_dummies().

Konversi ini penting agar algoritma ML seperti XGBoost bisa memahami dan menggunakan informasi dari kategori tersebut.

#### 2. Pisahkan Fitur (X) dan Target (y)
Data dibagi menjadi:
- X: semua kolom fitur yang akan digunakan untuk memprediksi
- y: kolom target yaitu carbon_credits
Kolom conservation_id dibuang karena itu hanya ID unik yang tidak relevan dalam prediksi.

#### 3. Split Data: Training dan Test Set
Data dibagi menjadi:
- 80% untuk melatih model (training)
- 20% untuk menguji performa model (test)
Parameter random_state=42 digunakan agar hasil split-nya reproducible (bisa diulang dan sama setiap kali dijalankan).

#### 4. Latih Model XGBoost
Model XGBoost Regressor digunakan karena:
- Efisien untuk regresi dengan data tabular
- Tangguh terhadap outlier dan data tidak terdistribusi normal
- Bisa menangani missing value secara internal
- Model dilatih menggunakan data training (X_train dan y_train).

#### 5. Prediksi Data Uji
Model yang sudah dilatih digunakan untuk memprediksi nilai kredit karbon dari data uji (X_test).

Hasilnya adalah array nilai prediksi (y_pred), satu untuk setiap baris di test set.

#### 6. Evaluasi Model
Dua metrik evaluasi utama digunakan:
- Mean Squared Error (MSE): semakin kecil, semakin baik.
- R-squared (R² Score): menunjukkan seberapa baik model menjelaskan variasi data.
- Nilai R² mendekati 1 berarti model sangat akurat
- Nilai mendekati 0 atau negatif menunjukkan model buruk

#### 7. Visualisasi Feature Importance
- Langkah ini menunjukkan fitur mana yang paling berkontribusi terhadap prediksi model.
- Fitur dengan nilai importance tertinggi berarti paling relevan dalam menentukan nilai carbon_credits.
- Visualisasi dibuat dalam bentuk horizontal bar chart agar mudah dibaca.

#### Kapan Menggunakan Pendekatan Ini?
- Saat kita punya data historis konservasi dan ingin memprediksi hasilnya (kredit karbon).
- Ingin tahu faktor mana yang paling memengaruhi output.
- Cocok untuk decision support system dalam proyek berbasis dampak lingkungan.

## Interpretasi Hasil Analisa

#### 1. Fitur total_benefit
Memiliki kontribusi terbesar dalam menentukan nilai carbon_credits.
Artinya, semakin besar manfaat (benefit) yang didistribusikan kepada masyarakat, semakin tinggi nilai kredit karbon yang diprediksi.
Bisa disebabkan karena benefit seringkali menjadi indikator keberhasilan konservasi.

#### 2. Fitur avg_participants
Memiliki pengaruh yang jauh lebih kecil dari total_benefit, tapi masih relevan.
Ini menunjukkan bahwa jumlah rata-rata peserta dalam kegiatan konservasi mungkin berkorelasi dengan dampak terhadap lingkungan (karbon yang diserap).

#### 3. Fitur Lokasi (One-hot Encoding seperti location_Pontianak, location_Blitar, dst.)
Hampir semua lokasi memiliki importance score mendekati 0.
Ini menandakan bahwa lokasi tidak terlalu menentukan nilai kredit karbon dalam dataset ini.

Bisa jadi karena:
- Perbedaan antar lokasi kurang signifikan, atau
- Informasi lokasi belum cukup mewakili karakter konservasi.

#### 4. Fitur Lain (avg_days_to_record, activity_count)
Kontribusi sangat kecil atau bahkan tidak digunakan oleh model.
Model menilai bahwa informasi ini kurang informatif dalam memprediksi nilai kredit karbon.

#### Kesimpulan Utama
- XGBoost mengandalkan total_benefit sebagai prediktor utama. Tanpanya, model kemungkinan besar akan kehilangan performa.
- Fitur-fitur lain seperti lokasi atau waktu pencatatan memiliki pengaruh yang kecil, dan mungkin bisa dipertimbangkan untuk dioptimalkan, direkayasa ulang, atau bahkan dihapus jika tidak memberikan nilai tambah.

Model bekerja cukup baik, karena memiliki:
- Mean Squared Error (MSE): 342.33 (cukup rendah tergantung konteks datanya),
- R-squared (R²): 0.85 → Artinya 85% variasi data berhasil dijelaskan oleh model, ini indikasi model yang sangat baik.

### Kesimpulan dan Rekomendasi Strategis
Berdasarkan analisis data keterlibatan masyarakat dan hasil konservasi mangrove menggunakan pendekatan time series dan machine learning, berikut temuan utama dan strategi tindak lanjut untuk meningkatkan efektivitas dan akurasi prediksi kinerja proyek:

#### Temuan Kunci:
- Tren Historis Kredit Karbon: Terlihat peningkatan fluktuatif kredit karbon dan partisipasi masyarakat dari waktu ke waktu, berdasarkan data historis yang divisualisasikan.
- Model Time Series (ARIMA): ARIMA dapat menangkap tren dan memprediksi nilai rata-rata kredit karbon dengan cukup baik, namun kurang efektif untuk prediksi jangka panjang atau data non-linear.
- Model Prediktif (XGBoost):
    - Akurasi tinggi dengan R² = 0.85 dan MSE = 342.33, menunjukkan model sangat baik dalam memprediksi kredit karbon berdasarkan data proyek.
    - Total benefit menjadi fitur paling penting yang sangat memengaruhi prediksi karbon.
    - Peran Lokasi dan Fitur Lain: Lokasi geografis dan variabel lainnya (seperti activity_count, avg_days_to_record) memiliki pengaruh yang sangat kecil terhadap prediksi kredit karbon.

#### Rencana Aksi Prioritas:
| Intervensi                   | Target                                     | Indikator Keberhasilan                      | Timeline     |
|-----------------------------|--------------------------------------------|---------------------------------------------|--------------|
| Peningkatan Kualitas Data   | Data konservasi dan partisipasi lengkap     | Semua proyek memiliki data lengkap dan valid| 3 bulan      |
| Penguatan Model Prediktif   | Implementasi model XGBoost                 | Akurasi prediksi ≥85% di dashboard real-time| 6 bulan      |
| Analisis Tren Waktu Lanjutan| Time-series untuk tren jangka panjang      | Dapat memproyeksikan 6–12 bulan ke depan    | 6 bulan      |
| Pelatihan dan Sosialisasi Tim | Tim lapangan memahami pemanfaatan data  | Tim bisa membaca dashboard & menindaklanjuti| 3–6 bulan    |


#### Langkah Monitoring:
- Bangun dashboard pemantauan performa proyek berbasis Python + PostgreSQL secara otomatis
- Jadwalkan evaluasi performa model setiap bulan
- Integrasikan sistem pelaporan manfaat dan partisipasi ke dalam pipeline data
- Libatkan masyarakat untuk validasi data di lapangan secara berkala

#### Visi Ke Depan:
Dengan implementasi strategi ini, dalam waktu 12 bulan ke depan diharapkan:
- Akurasi prediksi proyek meningkat hingga 85–90%
- Partisipasi masyarakat meningkat hingga 30%
- Kredit karbon meningkat 20% melalui pengambilan keputusan berbasis data
- Terbangun sistem pelaporan dan pemantauan proyek konservasi yang transparan, otomatis, dan real-time








