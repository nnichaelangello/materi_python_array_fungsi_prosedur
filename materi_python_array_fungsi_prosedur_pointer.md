# Materi Python: Array, Fungsi, dan Prosedur

---

## Daftar Isi

1. [Array](#1-array)
2. [Fungsi](#2-fungsi)
3. [Prosedur](#3-prosedur)

---

## 1. Array

### Apa itu Array?

**Array** adalah struktur data yang menyimpan kumpulan nilai dalam satu variabel, di mana setiap nilai dapat diakses menggunakan **indeks**. Indeks dimulai dari `0`.

Di Python, array direpresentasikan menggunakan **`list`**. List bersifat dinamis — ukurannya bisa bertambah atau berkurang, dan dapat menyimpan berbagai tipe data sekaligus.

```
Indeks :  0       1        2        3
List   : ["apel", "mangga", "jeruk", "pisang"]
```

---

### 1.1 Deklarasi dan Akses Array

```python
# Deklarasi array (list)
buah   = ["apel", "mangga", "jeruk", "pisang"]
angka  = [10, 20, 30, 40, 50]
nilai  = [85, 92, 78, 90, 88]

# Mengakses elemen berdasarkan indeks
print(buah[0])   # indeks 0 = elemen pertama
print(buah[2])   # indeks 2 = elemen ketiga
print(angka[4])  # indeks 4 = elemen terakhir

# Mengubah nilai elemen
nilai[2] = 95
print(nilai[2])  # sekarang bernilai 95
```

**Output:**
```
apel
jeruk
50
95
```

---

### 1.2 Menghitung Panjang Array Secara Manual

Karena tidak menggunakan fungsi bawaan, panjang array dihitung dengan perulangan `for`.

```python
mahasiswa = ["Andi", "Budi", "Citra", "Dewi", "Eka"]

# Menghitung panjang array secara manual
panjang = 0
for _ in mahasiswa:
    panjang = panjang + 1

print("Jumlah mahasiswa:", panjang)
```

**Output:**
```
Jumlah mahasiswa: 5
```

---

### 1.3 Menampilkan Seluruh Elemen Array

```python
nilai = [75, 82, 90, 68, 95, 77]

print("Daftar nilai:")
i = 0
while i < 6:          # 6 = panjang array (sudah diketahui)
    print(f"  nilai[{i}] = {nilai[i]}")
    i = i + 1
```

**Output:**
```
Daftar nilai:
  nilai[0] = 75
  nilai[1] = 82
  nilai[2] = 90
  nilai[3] = 68
  nilai[4] = 95
  nilai[5] = 77
```

---

### 1.4 Mencari Nilai Terbesar dan Terkecil

```python
data = [64, 25, 90, 12, 47, 83, 31]

terbesar  = data[0]
terkecil  = data[0]

i = 1
while i < 7:
    if data[i] > terbesar:
        terbesar = data[i]
    if data[i] < terkecil:
        terkecil = data[i]
    i = i + 1

print("Nilai terbesar:", terbesar)
print("Nilai terkecil:", terkecil)
```

**Output:**
```
Nilai terbesar: 90
Nilai terkecil: 12
```

---

### 1.5 Menghitung Total dan Rata-rata

```python
nilai = [80, 75, 90, 85, 70]
jumlah_elemen = 5

total = 0
i = 0
while i < jumlah_elemen:
    total = total + nilai[i]
    i = i + 1

rata_rata = total / jumlah_elemen

print("Total nilai  :", total)
print("Rata-rata    :", rata_rata)
```

**Output:**
```
Total nilai  : 400
Rata-rata    : 80.0
```

---

### 1.6 Menambah Elemen ke Array Secara Manual

Menambah elemen dilakukan dengan menggabungkan dua list menggunakan operator `+`.

```python
buah = ["apel", "mangga", "jeruk"]
print("Sebelum:", buah)

# Tambah elemen di akhir
buah = buah + ["pisang"]
print("Sesudah :", buah)

# Tambah beberapa elemen sekaligus
buah = buah + ["anggur", "melon"]
print("Sesudah :", buah)
```

**Output:**
```
Sebelum: ['apel', 'mangga', 'jeruk']
Sesudah : ['apel', 'mangga', 'jeruk', 'pisang']
Sesudah : ['apel', 'mangga', 'jeruk', 'pisang', 'anggur', 'melon']
```

---

### 1.7 Menghapus Elemen dari Array Secara Manual

```python
angka = [10, 20, 30, 40, 50]
print("Sebelum:", angka)

# Hapus elemen di indeks 2 (nilai 30)
indeks_hapus = 2
angka_baru = []

i = 0
while i < 5:
    if i != indeks_hapus:
        angka_baru = angka_baru + [angka[i]]
    i = i + 1

angka = angka_baru
print("Sesudah :", angka)
```

**Output:**
```
Sebelum: [10, 20, 30, 40, 50]
Sesudah : [10, 20, 40, 50]
```

---

### 1.8 Menyisipkan Elemen di Posisi Tertentu

```python
kota = ["Jakarta", "Surabaya", "Medan"]
print("Sebelum:", kota)

# Sisipkan "Bandung" di indeks 1
posisi  = 1
sisip   = "Bandung"
kota_baru = []

i = 0
while i < 3:
    if i == posisi:
        kota_baru = kota_baru + [sisip]
    kota_baru = kota_baru + [kota[i]]
    i = i + 1

kota = kota_baru
print("Sesudah :", kota)
```

**Output:**
```
Sebelum: ['Jakarta', 'Surabaya', 'Medan']
Sesudah : ['Jakarta', 'Bandung', 'Surabaya', 'Medan']
```

---

### 1.9 Mencari Elemen (Sequential Search)

```python
produk = ["buku", "pensil", "penghapus", "penggaris", "spidol"]
cari   = "penghapus"
n      = 5
ketemu = False
posisi = -1

i = 0
while i < n:
    if produk[i] == cari:
        ketemu = True
        posisi = i
    i = i + 1

if ketemu:
    print(f'"{cari}" ditemukan di indeks {posisi}')
else:
    print(f'"{cari}" tidak ditemukan')
```

**Output:**
```
"penghapus" ditemukan di indeks 2
```

---

### 1.10 Mengurutkan Array (Bubble Sort)

```python
angka = [64, 34, 25, 12, 22, 11, 90]
n = 7

print("Sebelum diurutkan:", angka)

# Bubble sort — urutkan dari kecil ke besar
i = 0
while i < n - 1:
    j = 0
    while j < n - i - 1:
        if angka[j] > angka[j + 1]:
            # Tukar posisi
            sementara      = angka[j]
            angka[j]       = angka[j + 1]
            angka[j + 1]   = sementara
        j = j + 1
    i = i + 1

print("Sesudah diurutkan:", angka)
```

**Output:**
```
Sebelum diurutkan: [64, 34, 25, 12, 22, 11, 90]
Sesudah diurutkan: [11, 12, 22, 25, 34, 64, 90]
```

---

### 1.11 Array 2 Dimensi (Matriks)

Array 2 dimensi adalah array yang setiap elemennya juga berupa array — membentuk struktur baris dan kolom seperti tabel.

```
          Kolom 0  Kolom 1  Kolom 2
Baris 0:     1        2        3
Baris 1:     4        5        6
Baris 2:     7        8        9
```

```python
# Deklarasi matriks 3x3
matriks = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

# Mengakses elemen: matriks[baris][kolom]
print("Elemen [0][0]:", matriks[0][0])  # pojok kiri atas
print("Elemen [1][2]:", matriks[1][2])  # baris 1, kolom 2
print("Elemen [2][2]:", matriks[2][2])  # pojok kanan bawah

print("\nSeluruh isi matriks:")
baris = 0
while baris < 3:
    kolom = 0
    while kolom < 3:
        print(matriks[baris][kolom], end="  ")
        kolom = kolom + 1
    print()
    baris = baris + 1
```

**Output:**
```
Elemen [0][0]: 1
Elemen [1][2]: 6
Elemen [2][2]: 9

Seluruh isi matriks:
1  2  3  
4  5  6  
7  8  9  
```

---

### 1.12 Penjumlahan Dua Matriks

```python
A = [
    [1, 2, 3],
    [4, 5, 6]
]

B = [
    [7,  8,  9],
    [10, 11, 12]
]

# Hasil penjumlahan A + B
C = [
    [0, 0, 0],
    [0, 0, 0]
]

baris = 0
while baris < 2:
    kolom = 0
    while kolom < 3:
        C[baris][kolom] = A[baris][kolom] + B[baris][kolom]
        kolom = kolom + 1
    baris = baris + 1

print("Matriks A + B:")
baris = 0
while baris < 2:
    kolom = 0
    while kolom < 3:
        print(C[baris][kolom], end="  ")
        kolom = kolom + 1
    print()
    baris = baris + 1
```

**Output:**
```
Matriks A + B:
8  10  12  
14  16  18  
```

---

## 2. Fungsi

### Apa itu Fungsi?

**Fungsi** adalah blok kode yang diberi nama, dapat dipanggil berulang kali, dan **mengembalikan sebuah nilai** melalui perintah `return`. Fungsi menerima input (parameter) dan menghasilkan output (nilai kembalian).

```
        ┌─────────────────────┐
Input → │   Proses di dalam   │ → Output (nilai kembalian)
        │       fungsi        │
        └─────────────────────┘
```

**Sintaks dasar:**
```python
def nama_fungsi(parameter1, parameter2):
    # blok kode
    return nilai
```

---

### 2.1 Fungsi Tanpa Parameter

```python
def phi():
    return 3.14159

def pesan_selamat_datang():
    return "Selamat datang di program kami!"

# Memanggil fungsi
nilai_phi = phi()
pesan     = pesan_selamat_datang()

print("Nilai phi :", nilai_phi)
print(pesan)
```

**Output:**
```
Nilai phi : 3.14159
Selamat datang di program kami!
```

---

### 2.2 Fungsi dengan Parameter

```python
def luas_persegi(sisi):
    return sisi * sisi

def luas_persegi_panjang(panjang, lebar):
    return panjang * lebar

def luas_segitiga(alas, tinggi):
    return (alas * tinggi) / 2

def keliling_lingkaran(jari_jari):
    return 2 * 3.14159 * jari_jari

print("Luas persegi (s=7)         :", luas_persegi(7))
print("Luas persegi panjang (5x3) :", luas_persegi_panjang(5, 3))
print("Luas segitiga (a=10,t=6)   :", luas_segitiga(10, 6))
print("Keliling lingkaran (r=7)   :", keliling_lingkaran(7))
```

**Output:**
```
Luas persegi (s=7)         : 49
Luas persegi panjang (5x3) : 15
Luas segitiga (a=10,t=6)   : 30.0
Keliling lingkaran (r=7)   : 43.98226
```

---

### 2.3 Fungsi dengan Parameter Default

Parameter default adalah nilai yang digunakan apabila argumen tidak diberikan saat pemanggilan fungsi.

```python
def pangkat(bilangan, eksponen=2):
    hasil = 1
    i = 0
    while i < eksponen:
        hasil = hasil * bilangan
        i = i + 1
    return hasil

# Tanpa eksponen → gunakan default (kuadrat)
print(pangkat(5))       # 5^2 = 25
print(pangkat(3))       # 3^2 = 9

# Dengan eksponen → override default
print(pangkat(2, 8))    # 2^8 = 256
print(pangkat(3, 3))    # 3^3 = 27
```

**Output:**
```
25
9
256
27
```

---

### 2.4 Fungsi Mengembalikan Banyak Nilai

Python memungkinkan fungsi mengembalikan lebih dari satu nilai sekaligus dalam bentuk tuple.

```python
def hitung_statistik(data, n):
    # Hitung total
    total = 0
    i = 0
    while i < n:
        total = total + data[i]
        i = i + 1

    rata_rata = total / n

    # Cari terbesar dan terkecil
    terbesar = data[0]
    terkecil = data[0]
    i = 1
    while i < n:
        if data[i] > terbesar:
            terbesar = data[i]
        if data[i] < terkecil:
            terkecil = data[i]
        i = i + 1

    return total, rata_rata, terbesar, terkecil

nilai = [75, 90, 60, 85, 95, 70]
total, rata, maks, minn = hitung_statistik(nilai, 6)

print(f"Total     : {total}")
print(f"Rata-rata : {rata:.2f}")
print(f"Terbesar  : {maks}")
print(f"Terkecil  : {minn}")
```

**Output:**
```
Total     : 475
Rata-rata : 79.17
Terbesar  : 95
Terkecil  : 60
```

---

### 2.5 Fungsi Rekursif

**Rekursi** adalah teknik di mana sebuah fungsi memanggil dirinya sendiri. Setiap fungsi rekursif harus memiliki:
- **Base case** — kondisi berhenti agar tidak looping selamanya
- **Recursive case** — bagian yang memanggil dirinya sendiri dengan nilai yang lebih kecil

```python
# Faktorial: n! = n × (n-1) × (n-2) × ... × 1
# Contoh: 5! = 5 × 4 × 3 × 2 × 1 = 120
def faktorial(n):
    if n == 0 or n == 1:       # base case
        return 1
    return n * faktorial(n - 1)  # recursive case

i = 0
while i <= 6:
    print(f"{i}! = {faktorial(i)}")
    i = i + 1
```

**Output:**
```
0! = 1
1! = 1
2! = 2
3! = 6
4! = 24
5! = 120
6! = 720
```

```python
# Deret Fibonacci: F(n) = F(n-1) + F(n-2)
# Contoh: 0, 1, 1, 2, 3, 5, 8, 13, ...
def fibonacci(n):
    if n == 0:               # base case 1
        return 0
    if n == 1:               # base case 2
        return 1
    return fibonacci(n - 1) + fibonacci(n - 2)  # recursive case

print("Deret Fibonacci ke-0 s/d ke-9:")
i = 0
while i < 10:
    print(fibonacci(i), end="  ")
    i = i + 1
print()
```

**Output:**
```
Deret Fibonacci ke-0 s/d ke-9:
0  1  1  2  3  5  8  13  21  34  
```

---

### 2.6 Fungsi Menerima Array sebagai Parameter

```python
def hitung_total(data, n):
    total = 0
    i = 0
    while i < n:
        total = total + data[i]
        i = i + 1
    return total

def cari_indeks_terbesar(data, n):
    indeks_maks = 0
    i = 1
    while i < n:
        if data[i] > data[indeks_maks]:
            indeks_maks = i
        i = i + 1
    return indeks_maks

def balik_array(data, n):
    hasil = []
    i = n - 1
    while i >= 0:
        hasil = hasil + [data[i]]
        i = i - 1
    return hasil

skor = [88, 72, 95, 61, 83, 90]

print("Data skor      :", skor)
print("Total skor     :", hitung_total(skor, 6))

idx = cari_indeks_terbesar(skor, 6)
print(f"Skor tertinggi : {skor[idx]} (indeks {idx})")

terbalik = balik_array(skor, 6)
print("Array terbalik :", terbalik)
```

**Output:**
```
Data skor      : [88, 72, 95, 61, 83, 90]
Total skor     : 489
Skor tertinggi : 95 (indeks 2)
Array terbalik : [90, 83, 61, 95, 72, 88]
```

---

### 2.7 Fungsi Mengembalikan Array

```python
def buat_array_kelipatan(bilangan, banyak):
    hasil = []
    i = 1
    while i <= banyak:
        hasil = hasil + [bilangan * i]
        i = i + 1
    return hasil

def filter_genap(data, n):
    hasil = []
    i = 0
    while i < n:
        if data[i] % 2 == 0:
            hasil = hasil + [data[i]]
        i = i + 1
    return hasil

kelipatan_3 = buat_array_kelipatan(3, 7)
print("Kelipatan 3 (7 pertama):", kelipatan_3)

angka = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
bilangan_genap = filter_genap(angka, 10)
print("Bilangan genap          :", bilangan_genap)
```

**Output:**
```
Kelipatan 3 (7 pertama): [3, 6, 9, 12, 15, 18, 21]
Bilangan genap          : [2, 4, 6, 8, 10]
```

---

## 3. Prosedur

### Apa itu Prosedur?

**Prosedur** adalah blok kode yang diberi nama dan dapat dipanggil berulang kali, namun **tidak mengembalikan nilai**. Prosedur melakukan suatu aksi — seperti mencetak, menulis, atau memodifikasi data — tanpa menghasilkan output yang bisa ditangkap ke variabel.

Di Python, prosedur ditulis dengan `def` tetapi **tanpa `return`** (atau hanya `return` kosong).

```
Perbedaan mendasar:

  FUNGSI   : hasil = hitung_luas(5, 3)   → nilai 15 tersimpan di 'hasil'
  PROSEDUR : cetak_luas(5, 3)            → langsung mencetak, tidak ada nilai kembalian
```

---

### 3.1 Prosedur Sederhana

```python
def cetak_garis(panjang, karakter):
    i = 0
    baris = ""
    while i < panjang:
        baris = baris + karakter
        i = i + 1
    print(baris)

def cetak_judul(teks):
    cetak_garis(35, "=")
    print("  " + teks)
    cetak_garis(35, "=")

def cetak_subjudul(teks):
    print(">> " + teks)
    cetak_garis(35, "-")

cetak_judul("SISTEM INFORMASI AKADEMIK")
cetak_subjudul("Data Nilai Mahasiswa")
```

**Output:**
```
===================================
  SISTEM INFORMASI AKADEMIK
===================================
>> Data Nilai Mahasiswa
-----------------------------------
```

---

### 3.2 Prosedur Mencetak Array

```python
def cetak_array(data, n, label):
    print(label + ":")
    i = 0
    while i < n:
        print(f"  [{i}] {data[i]}")
        i = i + 1

def cetak_array_horizontal(data, n):
    print("[", end="")
    i = 0
    while i < n:
        print(data[i], end="")
        if i < n - 1:
            print(", ", end="")
        i = i + 1
    print("]")

nama  = ["Andi", "Budi", "Citra", "Dewi"]
skor  = [85, 72, 90, 68]

cetak_array(nama, 4, "Daftar Nama")
print()
cetak_array(skor, 4, "Daftar Skor")
print()
print("Skor : ", end="")
cetak_array_horizontal(skor, 4)
```

**Output:**
```
Daftar Nama:
  [0] Andi
  [1] Budi
  [2] Citra
  [3] Dewi

Daftar Skor:
  [0] 85
  [1] 72
  [2] 90
  [3] 68

Skor : [85, 72, 90, 68]
```

---

### 3.3 Prosedur Memodifikasi Array

```python
def isi_dengan_nol(data, n):
    i = 0
    while i < n:
        data[i] = 0
        i = i + 1

def kali_semua(data, n, pengali):
    i = 0
    while i < n:
        data[i] = data[i] * pengali
        i = i + 1

def tukar_elemen(data, indeks_a, indeks_b):
    sementara      = data[indeks_a]
    data[indeks_a] = data[indeks_b]
    data[indeks_b] = sementara

angka = [5, 10, 15, 20, 25]
print("Awal         :", angka)

kali_semua(angka, 5, 3)
print("Dikali 3     :", angka)

tukar_elemen(angka, 0, 4)
print("Tukar [0],[4]:", angka)

isi_dengan_nol(angka, 5)
print("Diisi nol    :", angka)
```

**Output:**
```
Awal         : [5, 10, 15, 20, 25]
Dikali 3     : [15, 30, 45, 60, 75]
Tukar [0],[4]: [75, 30, 45, 60, 15]
Diisi nol    : [0, 0, 0, 0, 0]
```

---

### 3.4 Prosedur Mencetak Tabel Data

```python
def cetak_header_tabel():
    print(f"{'No':<5} {'Nama':<12} {'Nilai':<8} {'Grade':<8} {'Status'}")
    print("-" * 45)

def tentukan_grade(nilai):
    if nilai >= 90:
        return "A"
    elif nilai >= 80:
        return "B"
    elif nilai >= 70:
        return "C"
    elif nilai >= 60:
        return "D"
    else:
        return "E"

def cetak_baris_siswa(nomor, nama, nilai):
    grade  = tentukan_grade(nilai)
    status = "LULUS" if nilai >= 60 else "TIDAK LULUS"
    print(f"{nomor:<5} {nama:<12} {nilai:<8} {grade:<8} {status}")

def cetak_footer_tabel(total_nilai, jumlah):
    print("-" * 45)
    rata = total_nilai / jumlah
    print(f"Rata-rata nilai : {rata:.1f}")

# Data
nama_siswa = ["Andi", "Budi", "Citra", "Dewi", "Eka"]
nilai_siswa = [88, 55, 92, 73, 67]
n = 5

cetak_header_tabel()

total = 0
i = 0
while i < n:
    cetak_baris_siswa(i + 1, nama_siswa[i], nilai_siswa[i])
    total = total + nilai_siswa[i]
    i = i + 1

cetak_footer_tabel(total, n)
```

**Output:**
```
No    Nama         Nilai    Grade    Status
---------------------------------------------
1     Andi         88       B        LULUS
2     Budi         55       E        TIDAK LULUS
3     Citra        92       A        LULUS
4     Dewi         73       C        LULUS
5     Eka          67       D        LULUS
---------------------------------------------
Rata-rata nilai : 75.0
```

---

### 3.5 Perbedaan Fungsi dan Prosedur

```python
# ─── FUNGSI: menghitung dan mengembalikan nilai ───
def hitung_luas_persegi_panjang(panjang, lebar):
    return panjang * lebar

# ─── PROSEDUR: mencetak hasil tanpa mengembalikan nilai ───
def tampilkan_luas_persegi_panjang(panjang, lebar):
    luas = panjang * lebar
    print(f"Luas persegi panjang {panjang}x{lebar} = {luas}")


# Fungsi → hasilnya bisa ditangkap dan digunakan lagi
luas = hitung_luas_persegi_panjang(8, 5)
print("Nilai tersimpan:", luas)
print("Dua kali luas  :", luas * 2)

print()

# Prosedur → hanya melakukan aksi cetak, tidak bisa ditangkap
tampilkan_luas_persegi_panjang(8, 5)
coba_tangkap = tampilkan_luas_persegi_panjang(8, 5)
print("Hasil tangkapan prosedur:", coba_tangkap)  # None
```

**Output:**
```
Nilai tersimpan: 40
Dua kali luas  : 80

Luas persegi panjang 8x5 = 40
Luas persegi panjang 8x5 = 40
Hasil tangkapan prosedur: None
```

---

### 3.6 Kombinasi Fungsi dan Prosedur dalam Satu Program

Contoh program lengkap pengolahan data nilai siswa yang memadukan fungsi dan prosedur.

```python
# ── FUNGSI-FUNGSI ────────────────────────────────────────

def hitung_total(data, n):
    total = 0
    i = 0
    while i < n:
        total = total + data[i]
        i = i + 1
    return total

def hitung_rata(data, n):
    return hitung_total(data, n) / n

def cari_terbesar(data, n):
    maks = data[0]
    i = 1
    while i < n:
        if data[i] > maks:
            maks = data[i]
        i = i + 1
    return maks

def cari_terkecil(data, n):
    minn = data[0]
    i = 1
    while i < n:
        if data[i] < minn:
            minn = data[i]
        i = i + 1
    return minn

def hitung_jumlah_lulus(data, n, batas):
    jumlah = 0
    i = 0
    while i < n:
        if data[i] >= batas:
            jumlah = jumlah + 1
        i = i + 1
    return jumlah


# ── PROSEDUR-PROSEDUR ─────────────────────────────────────

def tampilkan_garis(n, kar):
    baris = ""
    i = 0
    while i < n:
        baris = baris + kar
        i = i + 1
    print(baris)

def tampilkan_judul(teks):
    tampilkan_garis(40, "=")
    print(teks.center(40))
    tampilkan_garis(40, "=")

def tampilkan_data(nama, nilai, n):
    print(f"  {'Nama':<12} {'Nilai':>6}")
    tampilkan_garis(22, "-")
    i = 0
    while i < n:
        print(f"  {nama[i]:<12} {nilai[i]:>6}")
        i = i + 1

def tampilkan_ringkasan(nilai, n):
    tampilkan_garis(40, "-")
    print("  RINGKASAN")
    tampilkan_garis(40, "-")
    rata  = hitung_rata(nilai, n)
    maks  = cari_terbesar(nilai, n)
    minn  = cari_terkecil(nilai, n)
    lulus = hitung_jumlah_lulus(nilai, n, 75)
    print(f"  Rata-rata    : {rata:.2f}")
    print(f"  Nilai tertinggi  : {maks}")
    print(f"  Nilai terendah   : {minn}")
    print(f"  Siswa lulus  : {lulus} dari {n}")
    tampilkan_garis(40, "=")


# ── PROGRAM UTAMA ─────────────────────────────────────────

nama_siswa  = ["Andi", "Budi", "Citra", "Dewi", "Eka", "Fajar"]
nilai_siswa = [88, 62, 95, 71, 83, 55]
jumlah      = 6

tampilkan_judul("LAPORAN NILAI KELAS")
tampilkan_data(nama_siswa, nilai_siswa, jumlah)
tampilkan_ringkasan(nilai_siswa, jumlah)
```

**Output:**
```
========================================
         LAPORAN NILAI KELAS
========================================
  Nama         Nilai
----------------------
  Andi            88
  Budi            62
  Citra           95
  Dewi            71
  Eka             83
  Fajar           55
----------------------------------------
  RINGKASAN
----------------------------------------
  Rata-rata    : 75.67
  Nilai tertinggi  : 95
  Nilai terendah   : 55
  Siswa lulus  : 3 dari 6
========================================
```

---