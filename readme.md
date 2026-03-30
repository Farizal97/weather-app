![Build Status](https://img.shields.io)
![Version](https://img.shields.io/badge/version-1.0.0-blue)
![License](https://img.shields.io/badge/license-MIT-orange)

#  ☁️ Mantap WeatherApp
by ** FrustDev **

[![Mantap](https://img.shields.io)](https://github.com/mantap-digital-training)

[![Contact](https://img.shields.io)](mailto:info@md.id)

[![X](https://img.shields.io)](https://x.com/mantapdigital)

[![Instagram](https://img.shields.io)](https://instagram.com/mantapdigital)

[![LinkedIn](https://img.shields.io)](https://linkedin.com)

[![YouTube](https://img.shields.io)](https://youtube.com @mantapdigital)


[! [Demo] (./assets/img/demo.gif) ]
[![Demo](https://img.shields.io)](https://mantap-digital-training.github.io)


Aplikasi web sederhana dengan HTML,CSS,JAVASCRIPT dan api dari 
[Open-Meteo] (https://open-meteo.com) untuk menampilkan cuaca terkini di lokasi pilihan anda.

##Fitur :
✅ Informasi cuaca saat ini :  lokasi kamu/kota kamu tentukan sendiri
✅ Informasi perkiraan cuaca 7 hari kedepan
✅ Informasi cuaca termasuk suhu,angin,kelembapan,hujan,(hari ini), dan kode cuaca
✅ Akses Cepat Informasi cuca sesuai histori pencarian terakhir
✅ Tampilan sederhana dan responsif
✅ Jalankan tanpa ribet konfigurasi

## Persyaratan Pengguna 📦
- **Browser** modern (Chrome, Firefox, Edge, Safari)
- **Koneksi Internet** (Untuk ambil data dari Open-Meteo API)

## Instalasi ⚙️
Pastikan sudah memiliki web server / application server aktif (Apache2, Node.js, Python 3, atau lainnya)

```bash
# Clone repository
git clone https://github.com/mantap-digital-training/weatherapp.git

## Struktur Direktori 📂

```plaintext
weatherapp/                  # Root project folder
├── assets/                  # Berisi file pendukung (CSS, JS, Image)
│   ├── css/                 # Styling (tampilan UI)
│   │   └── style.css        # File utama stylesheet
│   ├── img/                 # Media/Gambar untuk aplikasi
│   │   ├── demo.gif         # Demo aplikasi
│   │   └── mantaplogo.png   # Logo aplikasi
│   └── js/                  # Script JavaScript utama
│       ├── app.js           # File script utama aplikasi
│       └── include.js       # Script untuk menyertakan komponen
├── components/              # Kumpulan komponen HTML terpisah
│   ├── footer.html          # Komponen footer
│   ├── header.html          # Komponen header
│   └── navbar.html          # Komponen navbar (navigasi)
├── index.html               # Entry point aplikasi (halaman utama)
└── readme.md                # Dokumentasi project

## Cara Penggunaan 🚀
1. Buka **index.html** dengan browser.
2. Masukkan nama kota atau lokasi yang diinginkan lalu klik **"Cari"**.
3. Gunakan geolokasi dengan cara klik **"Lokasi saya"**.
4. Aplikasi akan menampilkan suhu, kelembaban, angin, curah hujan, dan kode cuaca saat ini serta perkiraan 7 hari kedepan.
5. Untuk melihat informasi cuaca dari pencarian sebelumnya, klik salah **"satu tombol kota"** dari list histori pencarian terakhir.

## Cuplikan Kode 💻
**Mencari Koordinat** (latitude & longitude) dan **Zona Waktu** (timezone) dari **Nama Kota** menggunakan API Geocoding Open-Meteo:

```javascript
async function geocode(name){
  const url = `https://geocoding-api.open-meteo.com/v1/search?name=${encodeURIComponent(name)}&count=1&language=id&format=json`;
  const res = await fetch(url, {headers:{'Accept':'application/json'}});
  if(!res.ok) throw new Error('Gagal geocoding');
  const data = await res.json();
  if(!data.results || !data.results.length) throw new Error('Kota tidak ditemukan');
  const r = data.results[0];
  return {
    id: r.id,
    name: r.name,
    admin1: r.admin1,
    country: r.country,
    lat: r.latitude,
    lon: r.longitude,
    tz: r.timezone
  };
}

## Roadmap Pengembangan 🗺️

### ✅ Tahap 1: Dasar Aplikasi
- [x] Membuat halaman utama dengan UI modern
- [x] Navbar dengan menu **Beranda, Tentang, Kontak**
- [x] Pencarian kota (search bar + tombol "Lokasi Saya")
- [x] Ringkasan cuaca saat ini (suhu, kondisi, kelembapan, angin, curah hujan, kode cuaca)
- [x] Icon cuaca yang beragam
- [x] Perkiraan cuaca 7 hari (ikon, suhu, curah hujan)
- [x] Riwayat pencarian kota terakhir
- [x] Styling modern dengan tema gelap (dark mode default)
- [x] Deploy ke **GitHub Pages**

### 🚀 Tahap 2: Peningkatan Fitur
- [ ] Update atau refresh cuaca real-time/frekuensi tertentu
- [ ] Mode terang (Light Mode) selain dark mode
- [ ] Format tanggal otomatis sesuai dengan bahasa yang konsisten
- [ ] Tambahkan detail cuaca per jam (hourly forecast)
- [ ] Buat tampilan **responsive penuh** untuk semua ukuran layar (mobile, tablet, desktop)

### 🌟 Tahap 3: Fitur Tingkat Lanjut
- [ ] Integrasi peta interaktif (Leaflet.js / Mapbox)
- [ ] Grafik tren suhu & curah hujan mingguan (Chart.js / Recharts)
- [ ] Multi-bahasa (Indonesia, Inggris, dll.)
- [ ] Pengaturan preferensi pengguna (lokasi default, unit suhu, bahasa)
- [ ] Notifikasi cuaca ekstrem (hujan deras, badai, panas ekstrem)

## Lisensi 📜
Proyek ini dilisensikan di bawah [MIT License](LICENSE).
*Anda bebas menggunakan, menyalin, memodifikasi, menggabungkan, menerbitkan, dan mendistribusikan proyek ini dengan syarat tetap mencantumkan atribusi kepada **Mantap Digital**. Tidak ada jaminan yang diberikan, gunakan dengan risiko Anda sendiri.*

