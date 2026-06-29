# E Uang

Aplikasi dompet digital berbasis Flutter untuk kebutuhan transaksi kampus. Mendukung transfer saldo antar pengguna, top up, pembayaran ke merchant, serta autentikasi via Google. Dikembangkan sebagai Ujian Akhir Semester mata kuliah Aplikasi Mobile.

## Deskripsi Aplikasi

E Uang adalah aplikasi mobile wallet yang memudahkan mahasiswa dan civitas kampus dalam melakukan transaksi keuangan digital. Fitur utama yang tersedia:

- Autentikasi dengan akun Google via Firebase Auth
- Melihat saldo dan riwayat transaksi
- Top up saldo
- Pembayaran ke merchant
- Deep link untuk menerima pembayaran langsung dari luar aplikasi

## Arsitektur Aplikasi

Proyek ini menggunakan Clean Architecture yang dibagi menjadi tiga lapisan utama:

```
lib/
├── core/               # Komponen inti yang digunakan lintas fitur
│   ├── constants/      # Konstanta aplikasi (URL, key, dll)
│   ├── error/          # Penanganan error dan failure
│   ├── network/        # Konfigurasi Dio dan interceptor
│   ├── router/         # Konfigurasi navigasi dengan GoRouter
│   ├── services/       # Layanan seperti DeeplinkService
│   ├── theme/          # Warna, tipografi, dan tema global
│   └── utils/          # Utilitas umum
│
├── data/               # Lapisan data
│   ├── datasources/    # Remote dan local data source
│   ├── models/         # Model data (JSON serialization)
│   └── repositories/   # Implementasi repository
│
├── domain/             # Lapisan bisnis
│   ├── entities/       # Entitas domain
│   ├── repositories/   # Kontrak repository (abstrak)
│   └── usecases/       # Use case per fitur (auth, payment, account)
│
├── injection/          # Dependency injection dengan GetIt
│
└── presentation/       # Lapisan tampilan
    ├── blocs/          # State management dengan flutter_bloc
    ├── pages/          # Halaman: auth, home, transfer, topup, merchant, dll
    └── widgets/        # Widget yang dapat digunakan ulang
```

State management menggunakan BLoC pattern (flutter_bloc), navigasi menggunakan GoRouter, dan dependency injection menggunakan GetIt.

## Cara Menjalankan Proyek

### Prasyarat

- Flutter SDK versi 3.x ke atas
- Dart SDK versi ^3.9.2
- Android Studio atau VS Code dengan ekstensi Flutter
- Perangkat Android atau emulator (Android 6.0+)
- Akun Firebase yang sudah dikonfigurasi (file `google-services.json` harus ada di `android/app/`)

### Langkah Menjalankan

1. Clone repositori:

```bash
git clone https://github.com/damarbagas-234/UAS_Aplikasi_Mobile.git
cd uas_aplikasi_mobile
```

2. Install dependensi:

```bash
flutter pub get
```

3. Pastikan file konfigurasi Firebase sudah ada:
   - `android/app/google-services.json`

4. Jalankan aplikasi:

```bash
flutter run
```

pastikan backend nya sudah jalan :
<br>
[be-uang (repo backend)](https://github.com/damarbagas-234/be-uang)
```bash
go run main.go
```

jalankan redis untuk otp :
```bash
redis-cli
```


## Daftar Dependensi Utama

| Dependensi | Versi | Kegunaan |
|---|---|---|
| flutter_bloc | ^9.0.0 | State management dengan pola BLoC |
| equatable | ^2.0.5 | Perbandingan objek pada state/event |
| get_it | ^8.0.2 | Dependency injection |
| go_router | ^14.8.1 | Navigasi deklaratif |
| dio | ^5.7.0 | HTTP client |
| pretty_dio_logger | ^1.4.0 | Logging request/response HTTP |
| firebase_core | ^3.12.1 | Inisialisasi Firebase |
| firebase_auth | ^5.5.2 | Autentikasi pengguna |
| firebase_messaging | ^15.2.4 | Push notification |
| google_sign_in | ^6.2.2 | Login dengan akun Google |
| flutter_secure_storage | ^9.2.2 | Penyimpanan token secara aman |
| shared_preferences | ^2.3.4 | Penyimpanan preferensi lokal |
| mobile_scanner | ^7.0.0 | Scan QR Code |
| cached_network_image | ^3.4.1 | Cache gambar dari jaringan |
| shimmer | ^3.0.0 | Efek loading skeleton |
| intl | ^0.19.0 | Format angka dan tanggal |
| app_links | ^6.3.2 | Penanganan deep link |
| url_launcher | ^6.3.1 | Membuka URL eksternal |

## Screenshot Aplikasi



## Video Presentasi


