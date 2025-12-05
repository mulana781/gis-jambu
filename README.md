# SIG Desa Jambu Barat

Prototype Sistem Informasi Geografis (SIG) berbasis web untuk Desa Jambu Barat, Kecamatan Mlonggo, Kabupaten Jepara, Jawa Tengah.

## 📋 Deskripsi

Aplikasi web interaktif yang menampilkan informasi geografis Desa Jambu Barat dengan fitur-fitur berikut:

- **Peta Interaktif**: Visualisasi peta dengan berbagai layer dan kontrol zoom/pan
- **Batas Desa**: Menampilkan batas administratif Desa Jambu Barat dalam format GeoJSON
- **Fasilitas Umum**: Marker untuk berbagai fasilitas umum seperti:
  - 🏫 Pendidikan (SD, TPQ, MA, MI, TK/KB)
  - 🏥 Kesehatan (Rumah Sakit, Klinik, Poliklinik)
  - ⛪ Tempat Ibadah (Masjid, Mushola, Gereja)
  - ⭐ Fasilitas Umum Lainnya (Lapangan, SPBU, Balai Desa, TPI)
- **Layer Control**: Toggle untuk menampilkan/menyembunyikan layer tertentu
- **Mode Layar Penuh**: Fitur untuk fokus pada peta tanpa sidebar
- **Legenda**: Informasi tentang simbol dan warna yang digunakan

## 🚀 Teknologi yang Digunakan

- **HTML5**: Struktur halaman web
- **CSS3**: Styling dengan desain modern dan responsif
- **JavaScript (Vanilla)**: Logika aplikasi dan interaktivitas
- **Leaflet.js v1.9.4**: Library JavaScript untuk peta interaktif
- **GeoJSON**: Format data geospasial untuk batas desa
- **OpenStreetMap**: Layer peta dasar standar
- **Esri World Imagery**: Layer citra satelit

## 📁 Struktur Project

```
GIS/
├── web/
│   ├── index.html          # Halaman utama aplikasi
│   ├── css/
│   │   └── style.css       # Stylesheet aplikasi
│   └── js/
│       └── map.js          # Logika peta dan interaktivitas
├── batas desa.geojson      # Data batas administratif desa
├── batas desa.qmd          # File Quarto (jika ada)
└── README.md               # Dokumentasi project
```

## 🛠️ Instalasi & Penggunaan

### Prasyarat

- Web browser modern (Chrome, Firefox, Edge, Safari)
- Web server lokal (opsional, untuk menghindari masalah CORS)

### Cara Menjalankan

1. **Clone atau download repository ini**

2. **Jika menggunakan web server lokal:**
   - Buka folder `web` di web server Anda (misalnya: XAMPP, Laragon, atau Live Server)
   - Akses melalui browser: `http://localhost/GIS/web/`

3. **Jika tidak menggunakan web server:**
   - Buka file `web/index.html` langsung di browser
   - **Catatan**: Beberapa browser mungkin memblokir loading file lokal untuk alasan keamanan

### Menggunakan Live Server (Rekomendasi)

Jika menggunakan VS Code:
1. Install ekstensi "Live Server"
2. Klik kanan pada `web/index.html`
3. Pilih "Open with Live Server"

## 🎯 Fitur Utama

### 1. Layer Peta Dasar
- **OpenStreetMap Standar**: Peta jalan dan landmark standar
- **Citra Satelit (Esri)**: Tampilan satelit untuk melihat kondisi aktual wilayah

### 2. Kontrol Layer
- Toggle untuk menampilkan/menyembunyikan batas desa
- Toggle untuk setiap kategori fasilitas umum:
  - Pendidikan
  - Kesehatan
  - Tempat Ibadah
  - Fasilitas Umum Lainnya

### 3. Marker Fasilitas
Setiap marker memiliki:
- Icon dengan emoji sesuai kategori
- Popup informasi saat diklik
- Warna berbeda untuk setiap kategori

### 4. Mode Layar Penuh
- Tombol untuk masuk ke mode layar penuh
- Fokus pada peta tanpa sidebar
- Tombol untuk keluar dari mode layar penuh

### 5. Legenda
- Menampilkan informasi tentang simbol dan warna yang digunakan
- Terletak di pojok kanan bawah peta

## 📝 Data

### Batas Desa
Data batas administratif Desa Jambu Barat disimpan dalam format GeoJSON (`batas desa.geojson`). Data ini mencakup:
- Koordinat batas wilayah
- Informasi administratif (Nama Desa, Kecamatan, Kabupaten, Provinsi)

### Fasilitas Umum
Data fasilitas umum disimpan dalam JavaScript object di file `map.js`, mencakup:
- Nama fasilitas
- Koordinat (latitude, longitude)
- Deskripsi/kategori
- Kategori (education, health, worship, public)

## 🔧 Konfigurasi

### Mengubah Koordinat Awal
Edit file `web/js/map.js`:
```javascript
const INITIAL_COORDS = [-6.5099748, 110.6635872, 4116]; // [lat, lng, altitude]
const INITIAL_ZOOM = 14;
```

### Menambah/Mengubah Fasilitas
Edit object `fasilitas` di file `web/js/map.js`:
```javascript
const fasilitas = {
  education: [
    {
      name: "Nama Fasilitas",
      coords: [latitude, longitude],
      description: "Deskripsi"
    },
    // ... tambahkan lebih banyak
  ],
  // ... kategori lainnya
};
```

### Mengubah Style Batas Desa
Edit bagian style GeoJSON di `web/js/map.js`:
```javascript
batasDesaLayer = L.geoJSON(data, {
  style: {
    color: "#f97316",        // Warna garis batas
    weight: 2,               // Ketebalan garis
    fillColor: "#fed7aa",    // Warna isian
    fillOpacity: 0.25,       // Opacity isian
  },
  // ...
});
```

## 🌐 Browser Support

Aplikasi ini kompatibel dengan browser modern:
- Chrome/Edge (versi terbaru)
- Firefox (versi terbaru)
- Safari (versi terbaru)
- Opera (versi terbaru)

## 📱 Responsive Design

Aplikasi dirancang responsif dan dapat digunakan di:
- Desktop/Laptop
- Tablet
- Smartphone

## 🔒 Lisensi

Project ini dibuat untuk keperluan akademik dan demonstrasi. Silakan gunakan sesuai kebutuhan Anda.

## 👥 Kontribusi

Jika Anda ingin berkontribusi pada project ini:
1. Fork repository
2. Buat branch untuk fitur baru (`git checkout -b fitur-baru`)
3. Commit perubahan Anda (`git commit -m 'Menambah fitur baru'`)
4. Push ke branch (`git push origin fitur-baru`)
5. Buat Pull Request

## 📧 Kontak & Informasi

Untuk pertanyaan atau informasi lebih lanjut tentang project ini, silakan hubungi pengembang atau pihak terkait.

## 🗺️ Lokasi

**Desa Jambu Barat**
- Kecamatan: Mlonggo
- Kabupaten: Jepara
- Provinsi: Jawa Tengah
- Koordinat: -6.5099748, 110.6635872

---

**Catatan**: Project ini adalah prototype dan masih dalam tahap pengembangan. Data yang ditampilkan mungkin belum lengkap atau akurat 100%. Silakan verifikasi data dengan sumber resmi jika diperlukan untuk keperluan penting.
