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

<div align="center">
  <img src="https://github.com/user-attachments/assets/19cf2982-894c-4eb1-bf52-3aac8c1a8fed" width="250" />
  <img src="https://github.com/user-attachments/assets/58744cfe-a0a8-4753-aeea-cfc1d9520e4f" width="250" />
  <img src="https://github.com/user-attachments/assets/ced5e8ba-ed07-4830-87e2-3aeea6d7ec43" width="250" />
  <img src="https://github.com/user-attachments/assets/d632f665-fd0f-4e27-83bc-cbd7ca071ac7" width="250" />
  <img src="https://github.com/user-attachments/assets/cd13f852-b24a-4bef-963b-48d33b30e31c" width="250" />
  <img src="https://github.com/user-attachments/assets/aba87619-6f17-45da-a44e-28241a1229cf" width="250" />
  <img src="https://github.com/user-attachments/assets/6bc6df45-269d-49f6-8fe8-6bccbab8abc2" width="250" />
  <img src="https://github.com/user-attachments/assets/1c903b0c-89a2-464a-a5ec-0fe4d2c4b52e" width="250" />
  <img src="https://github.com/user-attachments/assets/77983633-d4af-4e57-93bd-f2a892b1afe8" width="250" />
  <img src="https://github.com/user-attachments/assets/36e8da99-e49e-43cb-8e17-7d70913e24b5" width="250" />

  ### DeepLink dari toko jaket ke e uang
  <img src="https://github.com/user-attachments/assets/4ea2e1af-07d3-40e1-840c-9beb5f0e6790" width="250" />
  <img src="https://github.com/user-attachments/assets/48a259da-a17f-472c-b653-2f52d6cddf65" width="250" />
  <img src="https://github.com/user-attachments/assets/7b1fa14b-6bbb-4acd-8485-ace7e8c10ac3" width="250" />
  <img src="https://github.com/user-attachments/assets/d7513557-159c-43dd-86d9-f67f84131e94" width="250" />
  <br>
  setelah memasukan totp dari google authenticator :
  <br>
  <img src="https://github.com/user-attachments/assets/3267302e-e984-47c7-9be7-eb45be1204cd" width="250" />
</div>


## Video Presentasi

[Video Presentasi](https://www.youtube.com/watch?v=3ffwMaRlKmo)
