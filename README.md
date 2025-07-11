# 🎰 Casino Game C++

Sebuah program kasino sederhana yang dibangun dengan C++ yang menyediakan permainan mesin slot dan dadu dengan fitur pembayaran dan notifikasi lengkap.

## 🚀 Fitur Utama

- **🎰 Mesin Slot** - Permainan slot dengan 6 simbol berbeda
- **🎲 Permainan Dadu** - Permainan dadu head-to-head melawan kasino
- **💰 Sistem Pembayaran** - Integrasi dengan QR code untuk top-up saldo
- **🔔 Notifikasi Discord** - Sistem notifikasi otomatis ke Discord
- **🎵 Efek Suara** - Suara game dan notifikasi pembayaran

## 📋 Persyaratan Sistem

- Windows OS (menggunakan PowerShell)
- C++ Compiler (GCC/MinGW/Visual Studio)
- File suara: `lgg.wav` dan `notif_dana.wav`
- File QR code: `qr.jpg`
- Webhook Discord (opsional)

## 🛠️ Instalasi

1. Clone repository ini
2. Pastikan file-file berikut ada di `C:\Users\asus\Downloads\`:
   - `lgg.wav` (suara permainan)
   - `notif_dana.wav` (suara notifikasi)
   - `qr.jpg` (QR code pembayaran)
3. Compile program:
   ```bash
   g++ -o casino Tugas_5.cpp
   ```
4. Jalankan program:
   ```bash
   ./casino
   ```

## 🎮 Cara Bermain

### 1. Memulai Permainan
- Masukkan nama pemain
- Tentukan saldo awal

### 2. Pilihan Menu
- **1. Main Mesin Slot** - Mainkan permainan slot
- **2. Main Dadu** - Mainkan permainan dadu
- **3. Isi Saldo** - Top-up saldo via QR code
- **4. Keluar** - Keluar dari program

### 3. Mesin Slot 🎰
- Pilih jumlah spin: 1, 10, 20, atau 30
- Tentukan jumlah taruhan per spin
- Simbol yang tersedia: 🤑, 👾, 🔥, ⭐, 💎, 🚀
- **Menang**: 3 simbol sama = 10x taruhan
- **Kalah**: Simbol berbeda = kehilangan taruhan

### 4. Permainan Dadu 🎲
- Pilih jumlah lemparan: 1, 5, 10, atau 20
- Tentukan jumlah taruhan per lemparan
- Bandingkan dadu Anda vs dadu kasino
- **Menang**: Dadu Anda lebih besar
- **Kalah**: Dadu kasino lebih besar
- **Seri**: Tidak ada perubahan saldo

## 🏗️ Struktur Kode

### Kelas Utama

#### `Permainan` (Base Class)
```cpp
class Permainan {
protected:
    string namaPemain;
    int saldo;
public:
    virtual void mainkan() = 0;
    int getSaldo();
};
```

#### `MesinSlot` (Derived Class)
- Implementasi permainan mesin slot
- Sistem taruhan multi-spin
- Kalkulasi kemenangan otomatis

#### `Dadu` (Derived Class)
- Implementasi permainan dadu
- Sistem lemparan multi-round
- Perbandingan dadu real-time

### Fungsi Utility

| Fungsi | Deskripsi |
|--------|-----------|
| `playGameSoundDirect()` | Memutar suara permainan |
| `playDanaSound()` | Memutar suara notifikasi pembayaran |
| `kirimNotifikasiDiscord()` | Mengirim notifikasi ke Discord |
| `tampilkanQRPembayaran()` | Menampilkan QR code untuk pembayaran |

## ⚙️ Konfigurasi

### Discord Webhook
Untuk mengaktifkan notifikasi Discord, edit URL webhook di fungsi `kirimNotifikasiDiscord()`:

```cpp
string webhookUrl = "MASUKKAN_WEBHOOK_URL_ANDA_DISINI";
```

### Path File
Secara default, program mencari file di `C:\Users\asus\Downloads\`. Ubah path sesuai kebutuhan:

```cpp
string audioPath = "C:\\Users\\asus\\Downloads\\lgg.wav";
string qrPath = "C:\\Users\\asus\\Downloads\\qr.jpg";
```

## 🎯 Contoh Gameplay

```
=== KASINO ONLINE ===
Nama: John
Saldo: 1000

1. Main Mesin Slot
2. Main Dadu  
3. Isi Saldo
4. Keluar

Pilih: 1

=== MESIN SLOT ===
Jumlah spin: 10
Taruhan per spin: 50
Total taruhan: 500

Spin 1: 🤑 👾 🔥 - KALAH
Spin 2: 💎 💎 💎 - MENANG! +500
...

Total Kemenangan: 500
Saldo Akhir: 1000
```

## 📊 Statistik Permainan

Program mencatat dan menampilkan:
- Total taruhan
- Total kemenangan
- Total kerugian
- Saldo akhir
- Riwayat permainan

## 🔧 Troubleshooting

### Masalah Umum

1. **Suara tidak terdengar**
   - Pastikan file `.wav` ada di path yang benar
   - Periksa volume sistem

2. **QR code tidak muncul**
   - Verifikasi file `qr.jpg` ada di direktori yang ditentukan
   - Pastikan PowerShell dapat mengakses Windows Forms

3. **Notifikasi Discord tidak terkirim**
   - Periksa URL webhook Discord
   - Pastikan koneksi internet stabil

## 📝 Catatan Pengembangan

- Program menggunakan PowerShell untuk integrasi sistem Windows
- Implementasi OOP dengan inheritance dan polymorphism
- Sistem pembayaran menggunakan QR code statis
- Notifikasi otomatis untuk tracking kerugian

## 🤝 Kontribusi

Kontribusi sangat diterima! Silakan:
1. Fork repository ini
2. Buat branch fitur baru
3. Commit perubahan Anda
4. Push ke branch
5. Buat Pull Request

## 📄 Lisensi

Program ini dibuat untuk tujuan edukasi dan pembelajaran C++.

## 👨‍💻 Developer

Program ini dikembangkan sebagai bagian dari pembelajaran pemrograman C++ dengan fokus pada implementasi OOP dan integrasi sistem.

---

⭐ **Jangan lupa untuk star repository ini jika bermanfaat!**
