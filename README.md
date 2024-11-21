## Latihan Praktikum 

## Hasil Input
```python
def tampilkan_menu():
    print("\n[(L)ihat, (T)ambah, (U)bah, (H)apus, (C)ari, (K)eluar]:")

def tampilkan_daftar_nilai(daftar_nilai):
    if not daftar_nilai:
        print("Daftar Nilai")
        print("=" * 66)
        print("| NO |    NIM    |     NAMA      | TUGAS  | UTS  | UAS  | AKHIR  |")
        print("=" * 66)
        print("|                       TIDAK ADA DATA                           |")
        print("=" * 66)
    else:
        print("Daftar Nilai")
        print("=" * 66)
        print("| NO |    NIM    |     NAMA      | TUGAS  | UTS  | UAS  | AKHIR  |")
        print("=" * 66)
        for i, data in enumerate(daftar_nilai, start=1):
            print(f"| {i:<2} | {data[0]:<8} | {data[1]:<13} | {data[2]:<6} | {data[3]:<4} | {data[4]:<4} | {data[5]:<6.2f} |")
        print("=" * 66)

def tambah_data(daftar_nilai):
    print("Tambahkan Data")
    nim = input("NIM: ")
    nama = input("Nama: ")
    tugas = float(input("Nilai Tugas: "))
    uts = float(input("Nilai UTS: "))
    uas = float(input("Nilai UAS: "))
    nilai_akhir = (tugas + uts + uas) / 3
    daftar_nilai.append([nim, nama, tugas, uts, uas, nilai_akhir])
    print("Data berhasil ditambahkan.")

def ubah_data(daftar_nilai):
    tampilkan_daftar_nilai(daftar_nilai)
    index = int(input("Pilih nomor data yang ingin diubah: ")) - 1
    if 0 <= index < len(daftar_nilai):
        nim = input("NIM baru: ")
        nama = input("Nama baru: ")
        tugas = float(input("Nilai Tugas baru: "))
        uts = float(input("Nilai UTS baru: "))
        uas = float(input("Nilai UAS baru: "))
        nilai_akhir = (tugas + uts + uas) / 3
        daftar_nilai[index] = [nim, nama, tugas, uts, uas, nilai_akhir]
        print("Data berhasil diubah.")
    else:
        print("Nomor tidak valid.")

def hapus_data(daftar_nilai):
    tampilkan_daftar_nilai(daftar_nilai)
    index = int(input("Pilih nomor data yang ingin dihapus: ")) - 1
    if 0 <= index < len(daftar_nilai):
        daftar_nilai.pop(index)
        print("Data berhasil dihapus.")
    else:
        print("Nomor tidak valid.")

def cari_data(daftar_nilai):
    nim = input("Masukkan NIM yang dicari: ")
    ditemukan = False
    for data in daftar_nilai:
        if data[0] == nim:
            print(f"Data ditemukan: NIM: {data[0]}, Nama: {data[1]}, Tugas: {data[2]}, UTS: {data[3]}, UAS: {data[4]}, Akhir: {data[5]:.2f}")
            ditemukan = True
            break
    if not ditemukan:
        print("Data tidak ditemukan.")

if __name__ == "__main__":
    daftar_nilai = []
    while True:
        tampilkan_menu()
        pilihan = input().lower()

        if pilihan == 'l':
            tampilkan_daftar_nilai(daftar_nilai)
        elif pilihan == 't':
            tambah_data(daftar_nilai)
        elif pilihan == 'u':
            ubah_data(daftar_nilai)
        elif pilihan == 'h':
            hapus_data(daftar_nilai)
        elif pilihan == 'c':
            cari_data(daftar_nilai)
        elif pilihan == 'k':
            print("Keluar dari program.")
            break
        else:
            print("Pilihan tidak valid")

```

## Hasil Output
````markdown
[(L)ihat, (T)ambah, (U)bah, (H)apus, (C)ari, (K)eluar]:
L
Daftar Nilai
==================================================================
| NO |    NIM    |     NAMA      | TUGAS  | UTS  | UAS  | AKHIR  |
==================================================================
|                       TIDAK ADA DATA                           |
==================================================================

[(L)ihat, (T)ambah, (U)bah, (H)apus, (C)ari, (K)eluar]:
T
Tambahkan Data
NIM: 312410692
Nama: ALYA FEBRIANTI
Nilai Tugas: 100
Nilai UTS: 99
Nilai UAS: 100
Data berhasil ditambahkan.

[(L)ihat, (T)ambah, (U)bah, (H)apus, (C)ari, (K)eluar]:
L
Daftar Nilai
==================================================================
| NO |    NIM    |     NAMA      | TUGAS  | UTS  | UAS  | AKHIR  |
==================================================================
| 1  | 312410692 | ALYA FEBRIANTI | 100.0  | 99.0 | 100.0 | 99.67  |
==================================================================

[(L)ihat, (T)ambah, (U)bah, (H)apus, (C)ari, (K)eluar]:
T
Tambahkan Data
NIM: 3124
Nama: SHEILA
Nilai Tugas: 98
Nilai UTS: 98
Nilai UAS: 98
Data berhasil ditambahkan.

[(L)ihat, (T)ambah, (U)bah, (H)apus, (C)ari, (K)eluar]:
L
Daftar Nilai
==================================================================
| NO |    NIM    |     NAMA      | TUGAS  | UTS  | UAS  | AKHIR  |
==================================================================
| 1  | 312410692 | ALYA FEBRIANTI | 100.0  | 99.0 | 100.0 | 99.67  |
| 2  | 3124     | SHEILA        | 98.0   | 98.0 | 98.0 | 98.00  |
==================================================================

[(L)ihat, (T)ambah, (U)bah, (H)apus, (C)ari, (K)eluar]:
U
Daftar Nilai
==================================================================
| NO |    NIM    |     NAMA      | TUGAS  | UTS  | UAS  | AKHIR  |
==================================================================
| 1  | 312410692 | ALYA FEBRIANTI | 100.0  | 99.0 | 100.0 | 99.67  |
| 2  | 3124     | SHEILA        | 98.0   | 98.0 | 98.0 | 98.00  |
==================================================================
Pilih nomor data yang ingin diubah: 3124
Nomor tidak valid.

[(L)ihat, (T)ambah, (U)bah, (H)apus, (C)ari, (K)eluar]:
K
Keluar dari program.
````
