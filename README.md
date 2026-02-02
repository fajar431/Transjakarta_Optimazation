# Transjakarta_Optimazation
## Latar Belakang

Transportasi publik merupakan elemen penting dalam mendukung mobilitas masyarakat perkotaan sekaligus mengurangi tingkat kemacetan. Sebagai salah satu moda transportasi utama di DKI Jakarta, Transjakarta menghadapi tantangan dalam mengelola rute dan operasional akibat tingginya jumlah penumpang serta beragamnya pola perjalanan. Ketidakseimbangan distribusi armada, kepadatan pada jam sibuk, dan potensi keterlambatan layanan menjadi indikator perlunya strategi berbasis data untuk meningkatkan efisiensi.

Oleh karena itu, analisis pola penumpang pada bulan April 2023 dilakukan untuk mengidentifikasi tren penggunaan layanan, menentukan koridor dengan permintaan tinggi, serta menemukan peluang optimasi rute dan operasional. Melalui pendekatan data analytics, penelitian ini diharapkan mampu menghasilkan rekomendasi yang mendukung peningkatan kualitas layanan, efektivitas operasional, dan kenyamanan penumpang secara berkelanjutan.

## Rumusan Masalah

TransJakarta yang ingin mengoptimalkan perencanaan rute dan operasional berdasarkan permintaan penumpang. Berdasarkan rumusan masalah tersebut, dapat dirumuskan beberapa permasalahan utama:

1. Apakah terdapat pola dan fluktuasi permintaan penumpang TransJakarta dalam periode analisis bulan April 2023, baik secara harian maupun mingguan, serta faktor waktu apa saja yang memengaruhi perubahan volume penumpang tersebut?
2. Rute mana yang memiliki volume penumpang tertinggi dan terendah secara keseluruhan? Apakah terdapat rute tertentu yang secara konsisten mengalami permintaan penumpang tinggi sepanjang tahun?
3. Bagaimana pengaruh jenis kendaraan (BRT, mikrotrans, angkutan umum terintegrasi) terhadap jumlah penumpang?
4. Apakah terdapat rute yang mengalami pertumbuhan atau penurunan jumlah penumpang secara signifikan dibandingkan tahun-tahun sebelumnya? Bagaimana cara mengoptimalkan rute agar dapat melayani permintaan penumpang dengan lebih baik?
5. Apakah rute atau jenis kendaraan tertentu menarik demografi atau segmen penumpang tertentu? Adakah terdapat korelasi antara jumlah penumpang dengan faktor-faktor seperti hari dalam seminggu atau waktu dalam sehari?

# Data Sheet Information

Dataset Transjakarta ini berisikan 22 kolom yang menjelaskan informasi sebagai berikut:

| **Nama Kolom**       | **Deskripsi Kolom**                                                                          |
| -------------------- | -------------------------------------------------------------------------------------------- |
| **transID**          | ID transaksi unik untuk setiap transaksi.                                                    |
| **payCardID**        | Identitas utama pelanggan berupa kartu yang digunakan sebagai tiket saat tap in dan tap out. |
| **payCardBank**      | Nama bank penerbit kartu pelanggan.                                                          |
| **payCardName**      | Nama pelanggan yang tertera pada kartu.                                                      |
| **payCardSex**       | Jenis kelamin pelanggan yang tercantum pada kartu.                                           |
| **payCardBirthDate** | Tahun kelahiran pelanggan.                                                                   |
| **corridorID**       | ID koridor atau rute yang digunakan sebagai kunci pengelompokan rute.                        |
| **corridorName**     | Nama koridor atau rute yang mencakup titik awal dan akhir perjalanan.                        |
| **direction**        | Arah perjalanan rute: 0 untuk berangkat (go), 1 untuk kembali (back).                        |
| **tapInStops**       | ID halte tap in (masuk) untuk mengidentifikasi nama halte.                                   |
| **tapInStopsName**   | Nama halte tempat pelanggan melakukan tap in (masuk).                                        |
| **tapInStopsLat**    | Koordinat lintang (latitude) dari halte tap in.                                              |
| **tapInStopsLon**    | Koordinat bujur (longitude) dari halte tap in.                                               |
| **stopStartSeq**     | Urutan halte awal (halte ke-1, ke-2, dan seterusnya) sesuai dengan arah rute.                |
| **tapInTime**        | Waktu pelanggan melakukan tap in (tanggal dan jam).                                          |
| **tapOutStops**      | ID halte tap out (keluar) untuk mengidentifikasi nama halte.                                 |
| **tapOutStopsName**  | Nama halte tempat pelanggan melakukan tap out (keluar).                                      |
| **tapOutStopsLat**   | Koordinat lintang (latitude) dari halte tap out.                                             |
| **tapOutStopsLon**   | Koordinat bujur (longitude) dari halte tap out.                                              |
| **stopEndSeq**       | Urutan halte akhir sesuai dengan arah rute.                                                  |
| **tapOutTime**       | Waktu pelanggan melakukan tap out (tanggal dan jam).                                         |
| **payAmount**        | Jumlah tarif yang dibayarkan pelanggan (beberapa perjalanan gratis, sebagian berbayar).      |

## Kesimpulan

Analisis terhadap dataset awal yang mencakup **36.556 perjalanan TransJakarta selama April 2023**, yang setelah melalui proses pembersihan data menghasilkan **35.478 transaksi valid** menunjukkan bahwa permintaan penumpang bersifat **stabil dan terprediksi**, dengan pola yang kuat pada aktivitas *commuting* harian.

Konsentrasi perjalanan pada **weekday** serta **jam sibuk pagi dan sore** menegaskan peran TransJakarta sebagai infrastruktur mobilitas utama bagi populasi usia produktif di Jakarta.

Meskipun durasi perjalanan relatif konsisten, terdapat **variasi volume yang signifikan antar rute**. Temuan ini mengindikasikan bahwa peningkatan efisiensi operasional dapat dicapai melalui **optimalisasi alokasi sumber daya berbasis data**, tanpa harus bergantung pada ekspansi layanan secara besar.

Secara keseluruhan, hasil analisis menunjukkan bahwa pendekatan **data-driven** berpotensi menjadi fondasi utama dalam meningkatkan kinerja dan keberlanjutan sistem transportasi publik.

---

## Rekomendasi Operasional untuk Optimasi

### 1. Perencanaan Kapasitas Operasional
- Jam sibuk teridentifikasi: **06:00**
- Penumpang di jam sibuk: **5.624**
- Perkiraan estimasi kebutuhan unit transport: **113**
- Asumsi kapasitas rata-rata: **50 penumpang/unit**

---

### 2. Optimasi Operasional Berdasarkan Pola
- Rata-rata harian weekday: **1.571 penumpang**
- Rata-rata harian weekend: **396 penumpang**
- Rasio weekend/weekday: **0.25**

**Insight:** Weekday sangat dominan → layanan perlu berfokus pada kebutuhan commuter.  
**Rekomendasi:** Optimalkan armada dan frekuensi selama peak hours.

---

### 3. Prioritas dan Optimasi Rute

#### A. Rute Prioritas (Volume Tertinggi) - Berdasarkan Analisis Akhir
1. **Cibubur – Balai Kota (BRT)**: **375 penumpang** - Rute tersibuk dengan volume tinggi dan durasi optimal
2. **Ciputat – CSW (BRT)**: **371 penumpang** - Permintaan tinggi dengan pola komuter jelas
3. **Harmoni – Jakarta International Stadium (BRT)**: **350 penumpang** - Rute event-driven dengan potensi pertumbuhan

#### B. Rute dengan Potensi Optimasi Tertinggi
- **Cibubur – Balai Kota**: 
  - **Durasi 72 menit** dengan volume tinggi
  - **Rekomendasi**: Evaluasi bottleneck operasional, pertimbangkan layanan express untuk mengurangi waktu tempuh
  - **Target**: Kurangi durasi menjadi ≤60 menit

- **Ciputat – CSW**:
  - **Durasi 76 menit** dengan demand stabil
  - **Rekomendasi**: Optimasi rute untuk menghindari titik kemacetan, penyesuaian jadwal berdasarkan peak hour patterns
  - **Target**: Tingkatkan efisiensi 15% dalam 3 bulan

- **Rute dengan durasi >90 menit**:
  - **Identifikasi**: 8 rute dengan durasi sangat panjang (>90 menit)
  - **Rekomendasi**: Priority review untuk route redesign atau layanan express
  - **Target**: Reduksi durasi 20% melalui optimasi rute

#### C. Service Type Optimization Priorities
1. **BRT (48.8% market share)**:
   - **Status**: Backbone system - pertahankan reliability
   - **Rekomendasi**: Tambah frekuensi pada peak hours (06:00-08:00 & 16:00-18:00)
   - **Target**: >95% on-time performance selama peak hours

2. **Mikrotrans (43.9% market share)**:
   - **Status**: High volume feeder - tingkatkan connectivity
   - **Rekomendasi**: Optimasi last-mile connectivity dengan BRT stations
   - **Target**: Kurangi average waiting time menjadi <10 menit

3. **Royaltrans (4.5% market share)**:
   - **Status**: Premium service - fokus pada profitability
   - **Rekomendasi**: Segmentasi pricing berdasarkan waktu dan demand
   - **Target**: Tingkatkan load factor menjadi >70%

---

### 4. Strategi Pelayanan

#### A. Penyesuaian Frekuensi
- **Tingkatkan:** 05:00–07:00 (peak morning) & 16:00–18:00 (peak evening)
- **Pertahankan:** 09:00–15:00 (off-peak daytime) & 20:00–22:00 (evening tail)  
- **Evaluasi:** 22:00–04:00 (utilisasi rendah)

#### B. Optimasi Berdasarkan Tipe Layanan
1. **BRT (48.8% market share) - Priority Service:**
   - **Fokus:** Reliability & capacity during peak hours
   - **Target On-time Performance:** >95% selama peak hours
   - **Frekuensi:** Interval 5-8 menit (peak), 10-15 menit (off-peak)
   - **Rekomendasi Spesifik:**
     - Express services untuk rute >60 menit
     - Dynamic scheduling berdasarkan real-time demand

2. **Mikrotrans (43.9% market share) - High Volume Feeder:**
   - **Fokus:** Last-mile connectivity & affordability
   - **Target Waiting Time:** <10 menit di titik integrasi
   - **Frekuensi:** Interval 8-12 menit (peak), 15-20 menit (off-peak)
   - **Rekomendasi Spesifik:**
     - 5 priority integration points dengan BRT
     - Micro-zoning untuk optimal coverage

3. **Royaltrans (4.5% market share) - Premium Service:**
   - **Fokus:** Profitability & customer experience
   - **Target Load Factor:** >70%
   - **Frekuensi:** Interval 15-20 menit (peak), 25-30 menit (off-peak)
   - **Rekomendasi Spesifik:**
     - Dynamic pricing berdasarkan demand
     - Priority seating & amenities

4. **Angkutan Pengumpan (2.6% market share) - Niche Service:**
   - **Fokus:** Connectivity to terminals/stations
   - **Target Integration Efficiency:** <5 menit transfer time
   - **Rekomendasi Spesifik:**
     - Schedule synchronization dengan moda lain
     - On-demand services untuk low-demand areas

5. **Wisata/Event (0.2% market share) - Special Service:**
   - **Fokus:** Event-driven demand & tourist mobility
   - **Target:** 100% coverage for major events
   - **Rekomendasi Spesifik:**
     - Calendar-based scheduling
     - Multi-lingual information & ticketing 

#### C. Segmentasi Berdasarkan Perilaku
- **Commuter services:** prioritaskan ketepatan waktu dan keandalan  
- **Leisure services:** tingkatkan kenyamanan dan aksesibilitas  
- **Student services:** fokus pada keterjangkauan dan keamanan  

---

### 5. Rekomendasi Strategis

#### **Short-term (0-3 bulan):**
1. **Dynamic Scheduling BRT**:
   - Tambah 20% kapasitas pada jam 06:00-08:00
   - Kurangi 15% kapasitas pada jam 10:00-14:00
   - Implementasi: Monitoring real-time demand patterns

2. **Mikrotrans-BRT Integration**:
   - 5 titik integrasi prioritas (berdasarkan transfer patterns)
   - Synchronized scheduling untuk mengurangi waiting time
   - Target: Kurangi transfer time menjadi <5 menit

3. **Route Optimization Pilot**:
   - Pilih 3 rute dengan durasi >90 menit
   - Implementasi route redesign dengan A/B testing
   - Metrik: Durasi, passenger satisfaction, operational cost

#### **Medium-term (3-6 bulan):**
1. **Service Type Rebalancing**:
   - Konversi 10% BRT capacity ke express services selama peak hours
   - Pengembangan dedicated Mikrotrans corridors untuk high-density areas
   - Royaltrans premium pricing untuk non-peak hours

2. **Data-Driven Resource Allocation**:
   - Implementasi predictive analytics untuk demand forecasting
   - Dynamic resource allocation berdasarkan real-time data
   - Automated reporting untuk performance monitoring

3. **Customer Segmentation Strategy**:
   - Commuter packages untuk frequent riders (BRT)
   - Student discounts untuk Mikrotrans
   - Event-based packages untuk Wisata/Event services

#### **Long-term (6-12 bulan):**
1. **System-wide Optimization**:
   - Network redesign berdasarkan origin-destination patterns
   - Integrated fare system across service types
   - Multi-modal integration (MRT, LRT, Commuter Line)

2. **Technology Enablement**:
   - Real-time tracking & notification system
   - Mobile app untuk integrated planning & payment
   - IoT sensors untuk occupancy monitoring

3. **Sustainability Initiatives**:
   - Electric vehicle adoption roadmap
   - Carbon footprint tracking
   - Green route optimization# **Short-term (0-3 bulan):**
1. **Dynamic Scheduling BRT**:
   - Tambah 20% kapasitas pada jam 06:00-08:00
   - Kurangi 15% kapasitas pada jam 10:00-14:00
   - Implementasi: Monitoring real-time demand patterns

2. **Mikrotrans-BRT Integration**:
   - 5 titik integrasi prioritas (berdasarkan transfer patterns)
   - Synchronized scheduling untuk mengurangi waiting time
   - Target: Kurangi transfer time menjadi <5 menit

3. **Route Optimization Pilot**:
   - Pilih 3 rute dengan durasi >90 menit
   - Implementasi route redesign dengan A/B testing
   - Metrik: Durasi, passenger satisfaction, operational cost

#### **Medium-term (3-6 bulan):**
1. **Service Type Rebalancing**:
   - Konversi 10% BRT capacity ke express services selama peak hours
   - Pengembangan dedicated Mikrotrans corridors untuk high-density areas
   - Royaltrans premium pricing untuk non-peak hours

2. **Data-Driven Resource Allocation**:
   - Implementasi predictive analytics untuk demand forecasting
   - Dynamic resource allocation berdasarkan real-time data
   - Automated reporting untuk performance monitoring

3. **Customer Segmentation Strategy**:
   - Commuter packages untuk frequent riders (BRT)
   - Student discounts untuk Mikrotrans
   - Event-based packages untuk Wisata/Event services
---

### 6. Mitigasi Risiko 
- **Operational disruption:** lakukan pilot sebelum rollout penuh  
- **Customer resistance:** komunikasikan perubahan secara bertahap  
- **Resource constraints:** prioritaskan inisiatif berdampak tinggi

Dengan pendekatan berbasis data, TransJakarta memiliki peluang untuk bertransformasi dari sistem transportasi reaktif menjadi sistem mobilitas perkotaan yang adaptif dan berkelanjutan.

