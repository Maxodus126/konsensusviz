# 🚀 Interactive Distributed Systems Laboratory

> Simulator Interaktif & Dokumentasi Komprehensif untuk Sistem Terdistribusi

---

## 👤 Identitas Pengembang

| Field | Detail |
|---|---|
| **Nama Mahasiswa** | Aflin Awaludin |
| **NIM / Kelas** | *(24360007)* |
| **Dosen Pembimbing** | Dikky Suryadi, S.Kom., M.Kom. |
| **Institusi** | *(Institut Sains Dan Teknologi Nasional)* |
| **Status Proyek** | ✅ Selesai & Lolos Uji (100% Tested) |
| **Terakhir Diperbarui** | 18 Mei 2026 |

---

## 📖 Tentang Proyek

Repositori ini merupakan proyek komprehensif yang menggabungkan **mesin simulasi interaktif berbasis web (Flask)** dengan **dokumentasi analitis mendalam** untuk membedah empat pilar utama arsitektur sistem terdistribusi:

- 🗳️ **Algoritma Konsensus Raft**
- 🔄 **Conflict-free Replicated Data Types (CRDT)**
- 💼 **Distributed Transactions (2PC vs Saga)**
- 🔢 **Analisis Teorema Quorum**

Proyek ini tidak hanya berfungsi sebagai visualisasi perangkat lunak, melainkan juga sebagai **instrumen akademik** dan **panduan studi taktis** untuk menguasai skenario kegagalan, partisi jaringan, dan sinkronisasi data pada sistem skala besar.

---

## 📂 Struktur Repositori

```
Raft Simulator/
├── README.md                    # Panduan utama proyek & instruksi operasional
├── SOLUSI_SEMUA_LAB.md          # ⭐ Solusi teoretis ekstensif (2.880+ baris)
├── PANDUAN_CEPAT.md             # ⭐ Ringkasan taktis untuk persiapan ujian
├── app.py                       # Backend Flask utama
│
├── raft/                        # [Modul 1] Konsensus Raft
│   ├── node.py                  # State machine Raft (Follower, Candidate, Leader)
│   └── cluster.py               # Orkestrasi cluster 5-node & simulasi kegagalan
│
├── crdt/                        # [Modul 2] Eventual Consistency
│   ├── g_counter.py             # G-Counter (Grow-only Counter)
│   ├── pn_counter.py            # PN-Counter (Positive-Negative Counter)
│   ├── version_vector.py        # Version Vector untuk causal ordering
│   └── simulator.py             # Merge machine & simulasi node CRDT
│
├── transactions/                # [Modul 3] Transaksi Terdistribusi
│   ├── two_phase_commit.py      # Protokol 2PC (Coordinator & Participant)
│   └── saga.py                  # Saga Pattern Orchestrator + kompensasi
│
└── templates/                   # [Visualisasi] Antarmuka Web Interaktif
    ├── lab1-raft.html           # GUI Leader Election & Log Replication
    ├── lab2-crdt.html           # GUI state merge CRDT
    ├── lab3-2pc.html            # GUI komparasi 2PC vs Saga
    └── lab4-quorum.html         # Kalkulator & visualisasi Quorum
```

---

## 🔬 Modul Laboratorium

### 🗳️ Lab 1 — Raft Consensus Algorithm

Mensimulasikan konsensus ketat (*strong consistency*) pada kluster yang menghadapi kegagalan node.

**Pertanyaan kritis yang dijawab:**
- Berapa jumlah node minimum untuk membentuk kuorum, dan bagaimana tabel toleransi kesalahan diformulasikan?
- Apa yang terjadi jika Leader crash sebelum mayoritas ACK tercapai?
- Bagaimana mekanisme *up-to-date log check* menjamin keamanan pemilihan kandidat?

---

### 🔄 Lab 2 — Conflict-free Replicated Data Types (CRDT)

Pendekatan *eventual consistency* tanpa koordinasi pusat menggunakan struktur data matematis yang menjamin konvergensi antar replika.

**Pertanyaan kritis yang dijawab:**
- Apa perbedaan mendasar struktur internal G-Counter vs PN-Counter?
- Mengapa sifat komutativitas krusial di jaringan yang tidak andal?
- Studi kasus nyata: Apple Notes, VS Code Live Share, AWS DynamoDB.

---

### 💼 Lab 3 — Distributed Transactions (2PC vs Saga)

Perbandingan metode atomisitas transaksi lintas layanan: pendekatan pesimis (2PC) vs optimis (Saga).

**Pertanyaan kritis yang dijawab:**
- Mengapa masalah *blocking* terjadi saat Koordinator 2PC mati di fase krusial?
- Bagaimana Three-Phase Commit (3PC) memecahkan masalah *blocking*?
- Mengapa Saga tidak memiliki isolasi ACID, dan apa strategi mitigasinya?

---

### 🔢 Lab 4 — Quorum Analysis & Consistency Configurations

Kalkulator matematis interaktif untuk menganalisis konfigurasi kluster berdasarkan parameter **N** (replika), **W** (write acknowledgment), dan **R** (read acknowledgment).

**Pertanyaan kritis yang dijawab:**
- Pembuktian matematis mengapa `N=5, W=3, R=3` menghasilkan Strong Consistency.
- Trade-off konfigurasi *Write-Fast* (`N=5, W=1, R=5`) dan dampaknya pada disaster recovery.
- Trade-off konfigurasi *Read-Fast* (`N=5, W=5, R=1`) dan strategi mitigasi kegagalan tulis.

---

## 🚀 Instalasi & Menjalankan Simulator

### 1. Prasyarat

Pastikan **Python 3.8+** dan `pip` sudah terpasang di komputer Anda.

### 2. Klon Repositori

```bash
git clone https://github.com/username-anda/raft-simulator-lab.git
cd "Raft Simulator"
```

### 3. Instalasi Dependensi

```bash
pip install flask
```

### 4. Jalankan Server

```bash
python app.py
```

Server akan berjalan di `http://localhost:5000/` secara default.

### 5. Akses Simulator di Browser

| Lab | URL |
|---|---|
| 🗳️ Raft (Lab 1) | http://localhost:5000/lab1 |
| 🔄 CRDT (Lab 2) | http://localhost:5000/lab2 |
| 💼 Transaksi (Lab 3) | http://localhost:5000/lab3 |
| 🔢 Quorum (Lab 4) | http://localhost:5000/lab4 |

---

## 💡 Strategi Belajar

**Strategi 1 — Alur Linear (Teori → Simulator → Kode)**
1. Baca `PANDUAN_CEPAT.md` untuk menangkap definisi awal.
2. Jalankan simulator dan modifikasi state secara langsung.
3. Buka kode backend Python untuk melihat implementasi algoritmanya.

**Strategi 2 — Problem-Based Learning (PBL)**
1. Buka `SOLUSI_SEMUA_LAB.md` dan pilih satu pertanyaan ujian.
2. Rumuskan jawaban atau hipotesis Anda sendiri terlebih dahulu.
3. Bandingkan dengan solusi yang tersedia, lalu validasi menggunakan simulator.

**Strategi 3 — Chaos Engineering Sederhana**
1. Rancang skenario kegagalan kompleks, misalnya: *"Bagaimana jika kluster Raft terpisah 3-2 saat penulisan data?"*
2. Buat prediksi tertulis tentang perilaku masing-masing node.
3. Simulasikan dan analisis apakah hasilnya sesuai prediksi.

---

## 🎯 Checklist Kesiapan Ujian

### Konsensus Raft
- [ ] Prinsip majority voting dan kuorum pengambilan keputusan
- [ ] Transisi 3 status: Follower → Candidate → Leader
- [ ] Konsep waktu logis (Term) dan aturan perbandingan pesan
- [ ] Mekanisme replikasi log dan aturan komit
- [ ] Pembuktian Leader Election Safety
- [ ] Jaminan Leader Completeness

### CRDT
- [ ] Perbedaan struktur internal G-Counter dan PN-Counter
- [ ] Sifat Idempotent, Commutative, dan Associative pada operasi merge
- [ ] Cara kerja Version Vector untuk kausalitas antar kejadian
- [ ] Minimal 3 contoh penerapan CRDT di aplikasi modern

### Transaksi Terdistribusi & Saga
- [ ] Diagram alur Prepare Phase dan Commit Phase pada 2PC
- [ ] Status mesin partisipan: `INITIAL → PREPARED → COMMITTED/ABORTED`
- [ ] Penjelasan kondisi *in-doubt state* dan masalah blocking
- [ ] Mitigasi 3PC terhadap kelemahan 2PC
- [ ] Arsitektur Saga lengkap dengan transaksi kompensasinya

### Teorema Quorum
- [ ] Rumus konsistensi kuat: `W + R > N`
- [ ] Perhitungan ambang kegagalan tulis `(N - W)` dan baca `(N - R)`
- [ ] Klasifikasi tingkat konsistensi dan pemilihan konfigurasi berdasarkan kebutuhan

---

## 🛠️ Troubleshooting

**Port sudah digunakan (`Address already in use`)**
```bash
# Linux / macOS
pkill -f "python app.py"

# Windows
taskkill /F /IM python.exe
```
Kemudian jalankan ulang `python app.py`.

**State visual di browser tidak sinkron**
Lakukan *Hard Refresh*: `Ctrl + F5` (Windows/Linux) atau `Cmd + Shift + R` (Mac).

**Tombol simulator tidak merespons**
Buka Developer Tools (`F12`) → tab **Console** → periksa error JavaScript.

**Memverifikasi Flask berjalan normal**
```bash
curl http://localhost:5000/
```

---

## 📚 Referensi Akademik

**Konsensus Raft:**
- Ongaro, D., & Ousterhout, J. (2014). *In Search of an Understandable Consensus Algorithm*. USENIX ATC.
- Dokumentasi & visualisasi komunitas: https://raft.github.io/

**CRDT:**
- Shapiro, M., et al. (2011). *Conflict-free Replicated Data Types*. SSS 2011.
- Portal riset komunitas: https://crdt.tech/

**Sistem Terdistribusi (Umum):**
- Kleppmann, M. (2017). *Designing Data-Intensive Applications*. O'Reilly Media.
- Google Spanner: *Becoming a SQL System*
- Amazon Aurora: *Design Considerations for High Throughput Cloud-Native Relational Databases*

---

> Proyek ini dibuat untuk keperluan pembelajaran dan pengujian mandiri di bidang sistem terdistribusi.
