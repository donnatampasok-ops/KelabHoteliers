# Pelan Pembangunan — Dashboard Kelab Hoteliers

## Gambaran Keseluruhan

Membina dashboard web statik menggunakan HTML, Tailwind CSS, dan Vanilla JavaScript untuk membantu Penyelaras Kelab Hoteliers di Jabatan Pelancongan dan Hospitaliti, Politeknik Kota Kinabalu memantau ahli, aktiviti, kewangan, dan pencapaian kelab. Semua data disimpan dalam `localStorage` supaya tiada backend diperlukan. Antaramuka sepenuhnya dalam Bahasa Melayu.

**Skop:**
- Satu fail HTML utama dengan navigasi sidebar
- Data disimpan dalam `localStorage` (boleh dinaik taraf ke Firebase kemudian)
- Tiada sistem log masuk
- Sesuai untuk ~100 ahli

**Bukan Skop:**
- Backend server / API
- Sistem pengesahan pengguna
- Penyegerakan data antara peranti

---

## Sub-Tugas 1 — Struktur Asas & Susun Atur Dashboard

**Niat:**
Mewujudkan fail `index.html` utama dengan rangka susun atur dashboard — sidebar navigasi, header, dan kawasan kandungan utama — menggunakan Tailwind CSS via CDN.

**Hasil Dijangka:**
- Fail `index.html` wujud dan boleh dibuka dalam pelayar
- Sidebar dengan pautan navigasi ke semua 5 modul
- Header menunjukkan nama kelab dan logo/ikon
- Kawasan kandungan utama yang responsif

**Senarai Todo:**
- [ ] Cipta fail `index.html` dengan boilerplate HTML5
- [ ] Tambah Tailwind CSS via CDN
- [ ] Tambah Chart.js via CDN
- [ ] Bina sidebar dengan ikon dan pautan navigasi 5 modul
- [ ] Bina header dengan nama "Kelab Hoteliers — PKK"
- [ ] Cipta kawasan kandungan utama yang bertukar mengikut modul aktif
- [ ] Pastikan susun atur responsif untuk skrin desktop

**Konteks Relevan:**
- Fail: `index.html` (fail baharu)
- Modul navigasi: Utama, Ahli, Aktiviti, Kewangan, Pencapaian

**Status:** [ ] Belum Selesai

---

## Sub-Tugas 2 — Halaman Utama (Dashboard Ringkasan)

**Niat:**
Membina halaman utama yang menunjukkan kad ringkasan statistik kelab dan senarai aktiviti terkini sebagai pandangan pertama penyelaras.

**Hasil Dijangka:**
- 4 kad statistik: Jumlah Ahli, Aktiviti Aktif, Kadar Kehadiran, Baki Kewangan
- Carta bar kehadiran aktiviti menggunakan Chart.js
- Senarai 5 aktiviti akan datang
- Data diambil daripada `localStorage`

**Senarai Todo:**
- [ ] Bina 4 kad ringkasan statistik dengan ikon
- [ ] Integrasi Chart.js untuk carta bar kehadiran bulanan
- [ ] Bina jadual ringkas aktiviti akan datang
- [ ] Tulis fungsi JavaScript untuk mengira statistik daripada `localStorage`

**Konteks Relevan:**
- Bergantung pada struktur data yang ditetapkan dalam Sub-Tugas 3 dan 4
- Gunakan warna tema: biru gelap dan emas (sesuai dengan hospitaliti)

**Status:** [ ] Belum Selesai

---

## Sub-Tugas 3 — Modul Pengurusan Ahli

**Niat:**
Membolehkan penyelaras menambah, mengedit, memadam, dan mencari maklumat ahli kelab.

**Hasil Dijangka:**
- Jadual senarai ahli dengan lajur: Nama, No. Matrik, Tahun, Jawatan, Status
- Borang tambah/edit ahli dalam modal pop-up
- Fungsi carian dan tapisan mengikut status atau tahun
- Data disimpan dan diambil daripada `localStorage`

**Senarai Todo:**
- [ ] Definisi struktur data ahli dalam JavaScript (objek JSON)
- [ ] Bina jadual HTML dinamik yang dihasilkan dari data `localStorage`
- [ ] Bina modal borang tambah ahli dengan medan: Nama, No. Matrik, No. Telefon, E-mel, Tahun Pengajian, Jawatan, Status
- [ ] Tambah fungsi edit ahli (isi semula borang modal)
- [ ] Tambah fungsi padam ahli dengan pengesahan
- [ ] Bina bar carian dan tapisan status
- [ ] Paparkan kiraan jumlah ahli aktif/tidak aktif

**Konteks Relevan:**
- Struktur data ahli: `{ id, nama, noMatrik, noTelefon, emel, tahunPengajian, jawatan, status }`
- Status: "Aktif" / "Tidak Aktif"
- Jawatan: "Pengerusi", "Timbalan Pengerusi", "Setiausaha", "Bendahari", "Ahli Jawatankuasa", "Ahli Biasa"

**Status:** [ ] Belum Selesai

---

## Sub-Tugas 4 — Modul Aktiviti & Kehadiran

**Niat:**
Membolehkan penyelaras merekod aktiviti kelab dan menandakan kehadiran ahli bagi setiap aktiviti.

**Hasil Dijangka:**
- Senarai aktiviti dengan status (Akan Datang, Sedang Berjalan, Selesai)
- Borang tambah aktiviti
- Halaman kehadiran per aktiviti dengan senarai semak ahli
- Peratusan kehadiran dikira secara automatik

**Senarai Todo:**
- [ ] Definisi struktur data aktiviti dalam JavaScript
- [ ] Bina jadual senarai aktiviti dengan penapis status
- [ ] Bina modal borang tambah/edit aktiviti dengan medan: Nama, Tarikh, Tempat, Penerangan, Status
- [ ] Bina paparan kehadiran per aktiviti — senarai ahli dengan checkbox
- [ ] Tulis fungsi simpan kehadiran ke `localStorage`
- [ ] Kira dan papar peratusan kehadiran setiap aktiviti

**Konteks Relevan:**
- Struktur data aktiviti: `{ id, nama, tarikh, tempat, penerangan, status, kehadiran: [idAhli] }`
- Status aktiviti: "Akan Datang", "Sedang Berjalan", "Selesai"

**Status:** [ ] Belum Selesai

---

## Sub-Tugas 5 — Modul Kewangan

**Niat:**
Membolehkan penyelaras merekod yuran keahlian yang diterima dan perbelanjaan aktiviti kelab, serta melihat baki semasa.

**Hasil Dijangka:**
- Ringkasan kewangan: Jumlah masuk, Jumlah keluar, Baki
- Rekod penerimaan yuran ahli (siapa sudah bayar / belum)
- Rekod perbelanjaan aktiviti
- Carta pai perbelanjaan mengikut kategori

**Senarai Todo:**
- [ ] Definisi struktur data transaksi kewangan
- [ ] Bina kad ringkasan kewangan (masuk, keluar, baki)
- [ ] Bina jadual rekod yuran dengan status bayaran setiap ahli
- [ ] Bina jadual rekod perbelanjaan dengan borang tambah perbelanjaan
- [ ] Integrasi Chart.js untuk carta pai perbelanjaan mengikut kategori
- [ ] Kira baki kewangan secara automatik

**Konteks Relevan:**
- Struktur data transaksi: `{ id, jenis, kategori, amaun, tarikh, penerangan, idAhli }`
- Jenis: "Masuk" / "Keluar"
- Kategori perbelanjaan: "Aktiviti", "Peralatan", "Makanan", "Pengangkutan", "Lain-lain"

**Status:** [ ] Belum Selesai

---

## Sub-Tugas 6 — Modul Pencapaian

**Niat:**
Merekod dan memaparkan pencapaian atau anugerah yang diterima oleh ahli atau kelab secara keseluruhan.

**Hasil Dijangka:**
- Senarai pencapaian/anugerah kelab
- Borang tambah pencapaian
- Galeri pencapaian yang menarik

**Senarai Todo:**
- [ ] Definisi struktur data pencapaian
- [ ] Bina grid kad pencapaian yang menarik secara visual
- [ ] Bina modal borang tambah pencapaian dengan medan: Tajuk, Tarikh, Penerangan, Kategori, Nama Penerima
- [ ] Tambah fungsi padam pencapaian
- [ ] Papar bilangan pencapaian di halaman utama

**Konteks Relevan:**
- Struktur data pencapaian: `{ id, tajuk, tarikh, penerangan, kategori, penerima }`
- Kategori: "Pertandingan", "Anugerah", "Pengiktirafan", "Lain-lain"

**Status:** [ ] Belum Selesai

---

## Sub-Tugas 7 — Fungsi Eksport Laporan

**Niat:**
Membolehkan penyelaras mengeksport data kelab ke format PDF atau Excel untuk pelaporan rasmi.

**Hasil Dijangka:**
- Butang eksport senarai ahli ke Excel menggunakan SheetJS
- Butang eksport laporan kehadiran ke PDF menggunakan jsPDF
- Butang eksport penyata kewangan ke Excel

**Senarai Todo:**
- [ ] Tambah SheetJS via CDN
- [ ] Tambah jsPDF via CDN
- [ ] Tulis fungsi eksport senarai ahli ke `.xlsx`
- [ ] Tulis fungsi eksport laporan kehadiran ke `.pdf`
- [ ] Tulis fungsi eksport penyata kewangan ke `.xlsx`
- [ ] Tambah butang eksport di modul berkaitan

**Konteks Relevan:**
- SheetJS CDN: `https://cdn.sheetjs.com/xlsx-latest/package/dist/xlsx.full.min.js`
- jsPDF CDN: `https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js`

**Status:** [ ] Belum Selesai

---

## Seni Bina Fail

```
hoteliers-dashboard/
├── index.html          # Fail utama (semua modul dalam satu fail)
└── hoteliers-dashboard-plan.md
```

## Struktur Data localStorage

```
localStorage keys:
- hoteliers_ahli        → Array objek ahli
- hoteliers_aktiviti    → Array objek aktiviti
- hoteliers_kewangan    → Array objek transaksi
- hoteliers_pencapaian  → Array objek pencapaian
```
