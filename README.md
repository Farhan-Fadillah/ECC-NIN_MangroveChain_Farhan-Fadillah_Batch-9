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

REFERENSI






