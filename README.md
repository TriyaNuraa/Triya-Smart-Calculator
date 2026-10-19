# Triya Smart Calculator

Kalkulator desktop Windows berbasis Python dengan operasi desimal, mode ilmiah,
alat finansial, konverter satuan, riwayat lokal, dan pengaturan tema.

## Menjalankan dari source

Gunakan Python 3.11 atau lebih baru:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
python main.py
```

## Fitur

- **Standar:** operasi dasar, persen kontekstual (`200000 - 15%`), tanda, dan memori.
- **Ilmiah:** trigonometri, logaritma, akar, pangkat, faktorial, konstanta pi/e, DEG/RAD.
- **Finansial:** diskon, PPN tambah/pisah, margin/markup, dan cicilan anuitas.
- **Konverter:** panjang, berat, suhu, volume, dan kecepatan.
- Riwayat hingga 100 item, klik item untuk memuat kembali ekspresi, serta hapus semua.
- Tema terang/gelap/sistem, empat warna aksen, format angka Indonesia/internasional,
  presisi 2–12 desimal, dan opsi selalu di atas.
- Pintasan: `0–9`, operator, `Enter`/`=`, `Backspace`, `Esc`, `Delete`,
  `Ctrl+C`, `Ctrl+V`, `Ctrl+H`, `Ctrl+1/2/3`, dan `Ctrl+T`.

## Data lokal dan privasi

Pengaturan serta riwayat disimpan di folder `data` di samping executable (atau di
folder project saat dijalankan dari source). Tidak ada akun, koneksi internet,
Registry, ataupun evaluasi ekspresi menggunakan `eval()`. Jika folder aplikasi
tidak dapat ditulis, riwayat tetap tersedia selama sesi berjalan dan aplikasi
menampilkan peringatan penyimpanan.

## Pengujian

```powershell
python -m pytest
```

## Membuat executable portable

Di Windows, pasang dependensi terlebih dahulu lalu jalankan:

```powershell
.\build.bat
```

Executable satu file akan dibuat di `dist\TriyaSmartCalculator.exe`. Saat pertama
dijalankan, aplikasi membuat folder `data` di samping executable. Untuk distribusi,
salin executable dan folder `data` (jika sudah ada) bersama-sama.

PyInstaller `--onefile` mengekstrak aplikasi ke folder sementara saat startup;
waktu buka dan ukuran executable bergantung pada versi Python/dependensi. Uji
hasil build di Windows 10/11 sebelum dibagikan.
