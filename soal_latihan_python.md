# Soal Latihan Python

---

## Soal 1 — Daftar Nilai Siswa

### Latar Belakang

Kamu adalah seorang ketua kelas yang bertugas mencatat dan mengolah nilai ujian teman-temanmu. Kamu diminta membuat program Python yang dapat:

1. Meminta pengguna memasukkan **jumlah siswa** (minimal 2, maksimal 10)
2. Meminta pengguna memasukkan **nama** dan **nilai** (0–100) setiap siswa satu per satu
3. Menyimpan semua nama dan nilai ke dalam array
4. Menampilkan **laporan akhir** berisi:
   - Daftar nama dan nilai seluruh siswa
   - Nilai tertinggi beserta nama pemiliknya
   - Nilai terendah beserta nama pemiliknya
   - Rata-rata nilai kelas
   - Status setiap siswa: **LULUS** jika nilai ≥ 75, **TIDAK LULUS** jika nilai < 75

---

### Petunjuk Pengerjaan

Pecah program menjadi beberapa **fungsi** dan **prosedur** berikut:

| Nama | Jenis | Tugas |
|---|---|---|
| `hitung_rata(nilai, n)` | Fungsi | Menghitung rata-rata nilai |
| `cari_nilai_tertinggi(nilai, n)` | Fungsi | Mengembalikan nilai tertinggi |
| `cari_nilai_terendah(nilai, n)` | Fungsi | Mengembalikan nilai terendah |
| `cari_indeks_tertinggi(nilai, n)` | Fungsi | Mengembalikan indeks siswa dengan nilai tertinggi |
| `cari_indeks_terendah(nilai, n)` | Fungsi | Mengembalikan indeks siswa dengan nilai terendah |
| `tampilkan_laporan(nama, nilai, n)` | Prosedur | Mencetak seluruh laporan akhir |

> **Ingat:** Fungsi mengembalikan nilai (`return`), prosedur hanya melakukan aksi (tanpa `return`).

---

### Contoh Jalannya Program

```
Masukkan jumlah siswa (2-10): 4

--- Input Data Siswa ---
Siswa ke-1
  Nama  : Andi
  Nilai : 88
Siswa ke-2
  Nama  : Budi
  Nilai : 60
Siswa ke-3
  Nama  : Citra
  Nilai : 95
Siswa ke-4
  Nama  : Dewi
  Nilai : 72

============================================================
                   LAPORAN NILAI KELAS
============================================================
  No   Nama             Nilai    Status
  --------------------------------------------------
  1    Andi             88       LULUS
  2    Budi             60       TIDAK LULUS
  3    Citra            95       LULUS
  4    Dewi             72       TIDAK LULUS
  --------------------------------------------------
  Nilai tertinggi : 95  (Citra)
  Nilai terendah  : 60  (Budi)
  Rata-rata kelas : 78.75
============================================================
```

---

### Hal yang Harus Diperhatikan

- Jumlah siswa **wajib** divalidasi. Jika pengguna memasukkan angka di luar rentang 2–10, minta ulang hingga valid.
- Nilai siswa **wajib** divalidasi. Jika pengguna memasukkan angka di luar 0–100, minta ulang hingga valid.
- Gunakan `while` untuk looping input data siswa.
- Gunakan `while` juga di dalam setiap fungsi (bukan fungsi bawaan Python).

---

### Kerangka Awal (Boleh Dimodifikasi)

```python
# ── FUNGSI ──────────────────────────────────────────────

def hitung_rata(nilai, n):
    # TODO: hitung dan kembalikan rata-rata
    pass

def cari_nilai_tertinggi(nilai, n):
    # TODO: kembalikan nilai terbesar
    pass

def cari_nilai_terendah(nilai, n):
    # TODO: kembalikan nilai terkecil
    pass

def cari_indeks_tertinggi(nilai, n):
    # TODO: kembalikan indeks elemen terbesar
    pass

def cari_indeks_terendah(nilai, n):
    # TODO: kembalikan indeks elemen terkecil
    pass


# ── PROSEDUR ────────────────────────────────────────────

def tampilkan_laporan(nama, nilai, n):
    # TODO: tampilkan seluruh laporan
    pass


# ── PROGRAM UTAMA ────────────────────────────────────────

nama_siswa  = []
nilai_siswa = []

# TODO: input jumlah siswa (validasi 2-10)
# TODO: input nama dan nilai tiap siswa (validasi nilai 0-100)
# TODO: panggil tampilkan_laporan()
```

---

---

## Soal 2 — Toko Buah Digital

### Latar Belakang

Kamu membantu pemilik toko buah untuk membuat program kasir sederhana. Toko menjual **5 jenis buah** dengan harga tetap. Pelanggan dapat memilih buah dan memasukkan jumlah yang dibeli. Program kemudian menghitung total belanja dan menentukan kembalian.

Daftar buah dan harga (sudah ditentukan, tidak perlu diinput):

| Indeks | Nama Buah | Harga per kg |
|---|---|---|
| 0 | Apel | Rp 15.000 |
| 1 | Mangga | Rp 12.000 |
| 2 | Jeruk | Rp 10.000 |
| 3 | Pisang | Rp 8.000 |
| 4 | Anggur | Rp 35.000 |

Program harus bisa:

1. Menampilkan daftar buah dan harga
2. Meminta pelanggan memilih buah berdasarkan **nomor** (1–5)
3. Meminta pelanggan memasukkan **berat dalam kg** (harus lebih dari 0)
4. Menghitung **subtotal** untuk buah tersebut
5. Menanyakan apakah pelanggan ingin membeli buah lagi (`y` / `t`)
6. Jika selesai belanja, tampilkan **struk** berisi semua item yang dibeli, total belanja, uang bayar (diinput), dan kembalian
7. Jika uang bayar **kurang dari total**, minta input ulang

---

### Petunjuk Pengerjaan

Pecah program menjadi fungsi dan prosedur berikut:

| Nama | Jenis | Tugas |
|---|---|---|
| `hitung_subtotal(harga, berat)` | Fungsi | Mengembalikan harga × berat |
| `hitung_total(subtotal, n)` | Fungsi | Mengembalikan total semua subtotal |
| `hitung_kembalian(bayar, total)` | Fungsi | Mengembalikan selisih bayar − total |
| `tampilkan_menu(nama_buah, harga, n)` | Prosedur | Mencetak daftar buah dan harga |
| `tampilkan_struk(nama_buah, berat_beli, subtotal, n, total, bayar)` | Prosedur | Mencetak struk belanja |

---

### Contoh Jalannya Program

```
===========================
     TOKO BUAH SEGAR
===========================
  1. Apel        Rp 15.000/kg
  2. Mangga      Rp 12.000/kg
  3. Jeruk       Rp 10.000/kg
  4. Pisang      Rp  8.000/kg
  5. Anggur      Rp 35.000/kg
===========================

Pilih buah (1-5): 1
Berat (kg)      : 2
  >> Apel 2 kg = Rp 30.000

Beli buah lagi? (y/t): y

Pilih buah (1-5): 5
Berat (kg)      : 0
  [!] Berat harus lebih dari 0. Coba lagi.
Berat (kg)      : 1
  >> Anggur 1 kg = Rp 35.000

Beli buah lagi? (y/t): t

============================================================
                       STRUK BELANJA
============================================================
  No   Buah        Berat     Harga/kg    Subtotal
  --------------------------------------------------
  1    Apel        2 kg      Rp 15.000   Rp  30.000
  2    Anggur      1 kg      Rp 35.000   Rp  35.000
  --------------------------------------------------
  Total Belanja   : Rp  65.000
  Uang Bayar      : Rp 100.000
  Kembalian       : Rp  35.000
============================================================
  Terima kasih sudah berbelanja!
```

---

### Hal yang Harus Diperhatikan

- **Data buah dan harga** disimpan dalam dua array terpisah sejak awal program (bukan diinput).
- **Data transaksi** (buah yang dibeli, berat, subtotal) disimpan dalam array yang dibangun selama program berjalan menggunakan operator `+`.
- Pilihan buah wajib divalidasi: harus angka 1–5.
- Berat wajib divalidasi: harus lebih dari 0.
- Uang bayar wajib divalidasi: harus ≥ total belanja.
- Gunakan `while True` dengan `break` untuk looping pembelian.

---

### Kerangka Awal (Boleh Dimodifikasi)

```python
# ── DATA TOKO (sudah ditentukan) ─────────────────────────

nama_buah = ["Apel", "Mangga", "Jeruk", "Pisang", "Anggur"]
harga     = [15000, 12000, 10000, 8000, 35000]
N_BUAH    = 5


# ── FUNGSI ──────────────────────────────────────────────

def hitung_subtotal(harga_satuan, berat):
    # TODO: kembalikan harga_satuan * berat
    pass

def hitung_total(subtotal, n):
    # TODO: hitung dan kembalikan total semua subtotal
    pass

def hitung_kembalian(bayar, total):
    # TODO: kembalikan selisih
    pass


# ── PROSEDUR ────────────────────────────────────────────

def tampilkan_menu(nama_buah, harga, n):
    # TODO: tampilkan daftar buah dan harga
    pass

def tampilkan_struk(nama_buah, harga, berat_beli, subtotal_beli, n_beli, total, bayar):
    # TODO: tampilkan struk lengkap
    pass


# ── PROGRAM UTAMA ────────────────────────────────────────

buah_dibeli    = []   # menyimpan indeks buah yang dipilih
berat_dibeli   = []   # menyimpan berat tiap buah
subtotal_dibeli = []  # menyimpan subtotal tiap buah
n_transaksi    = 0

tampilkan_menu(nama_buah, harga, N_BUAH)

# TODO: loop pembelian (while True ... break)
# TODO: input dan validasi pilihan buah
# TODO: input dan validasi berat
# TODO: hitung subtotal dan simpan ke array
# TODO: tanya lagi atau selesai

# TODO: input dan validasi uang bayar
# TODO: panggil tampilkan_struk()
```

---