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

# PEMBAHASAN TOPIC PERMASALAHAN

## Studi Kasus 1 : Analisis Efektivitas Regulasi & Dampak Biodiversitas

### Latar Belakang Masalah
Tim konservasi menemukan variasi signifikan dalam hasil monitoring biodiversitas di berbagai proyek. Di Kalimantan Timur, proyek dengan izin disetujui menunjukkan kerapatan pohon 40% lebih tinggi dibandingkan proyek dengan status pending, sementara di Jawa, kualitas air tetap buruk meskipun izin sudah disetujui. Analisis ini bertujuan mengungkap pola sistemik bagaimana kerangka regulasi dan struktur kepemilikan lahan mempengaruhi hasil konservasi.

### Pertanyaan Kunci
- Apakah status persetujuan izin berkorelasi dengan peningkatan biodiversitas yang terukur (kualitas air, kerapatan pohon)?
- Bagaimana pengaturan kepemilikan lahan yang berbeda (negara, swasta, masyarakat) mempengaruhi keanekaragaman spesies?
- Apakah proyek dengan batas lahan yang terdefinisi secara hukum mencapai hasil ekologis yang lebih baik?

## Pembahasan Analisa dengan Query SQL

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








