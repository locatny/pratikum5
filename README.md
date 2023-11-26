# Praktikum 5
# Latihan
## Membuat Dictionary daftar kontak
```python
kontak = {'Jaemin':'0812678567', 'Hanny' : '087677824'}
```

## Menampilkan Kontak Jaemin
```python
print("Kontak Jaemin", kontak['Jaemin'])
```

## Menambahkan kontak Zidny
```python
kontak['Zidny'] = '087654544'
```

## Mengubah kontak Hanny
```python
kontak['Hanny'] = '088999776'
```

## Tampilkan semua nama
```python print("=====Menampilkan semua nama=====")
for nama in kontak.keys():
    print(nama)
```

## Tampilkan semua nomor
```python print("\n=====Menampilkan semua nomor=====")
for nomor in kontak.values():
    print(nomor)
```

## Tampilkan daftar Nama dan nomornya
```python print("\n=====Menampilkan nama dan nomor=====")
for nama, nomor in kontak.items():
    print(f"{nama}: {nomor}")
```

## Menghapus kontak Hanny
```python 
del kontak['Hanny']
```


![gambar](p2.png)

# Praktik
## Program Data Mahasiswa

![gambar](p1.png)

- Membuat dictionary kosong
```python
x = {}
```
- Membuat kondisi perulangan dan keterangan untuk pilihan menu
```python
while True:
    a = input("\n(T)ambah, (U)bah, (H)apus, (C)ari, (L)ihat, (K)eluar: ")
```
- Menambahkan data
```python
if a.lower() == 't':
        print("Tambah Data")
        nama = input("Nama           : ")
        nim = int(input("NIM            : "))
        tugas = int(input("Nilai Tugas    : "))
        uts = int(input("Nilai UTS      : ")) 
        uas = int(input("Nilai UAS      : "))
        nilaiakhir = tugas * 0.3 + uts * 0.35 + uas * 0.35
        x[nama] = nim, tugas, uts, uas, nilaiakhir
```
Apabila kita mengitputkan 't' maka kita akan diminta untuk mengitputkan data, seperti nama, nim, uts, dan uas. Data tersebut akan masuk ke dalam dictionary 'x' yang telah dibuat dengan data 'nama' sebagai keys dan sisanya sebagai values.

- Mengubah data
```python
elif a.lower() == 'u':
        print("Ubah Data")
        nama = input("Masukkan Nama  : ")
        if nama in x.keys():
            nim = int(input("NIM            : "))
            tugas = int(input("Nilai Tugas    : "))
            uts = int(input("Nilai UTS      : "))
            uas = int(input("Nilai UAS      : "))
            nilaiakhir = tugas * 0.3 + uts * 0.35 + uas * 0.35
            x[nama] = nim, tugas, uts, uas, nilaiakhir
        else:
            print("Nama {0} tidak ditemukan".format(nama))
```
Jika menginputkan 'u' makan akan ada keterangan untuk mengubah data dan kita akan diminta untuk menginputkan nama yang ingin diubah datanya, apabila nama tidak ada maka outputnya "Nama {} tidak ditemukan". {} adalah nama atau data yang mau diubah.

- Menghapus data
```python
elif a.lower() == 'h':
        print("Hapus Data")
        nama = input("Masukkan Nama  : ")
        if nama in x.keys():
            del x[nama]
        else:
            print("Nama {0} Tidak Ditemukan".format(nama))
```
Jika menginputkan 'h' maka akan diminta menginputkan nama yang ingin dihapus datanya. Jika nama ada dalam dictionary, maka sistem akan menghapus nama dan datanya.

- Mencari data
```python
 elif a.lower() == 'c':
        print("Cari Data")
        nama = input("Masukkan Nama : ")
        if nama in x.keys():
            print("="*79)
            print("|                                Daftar Mahasiswa                             |")
            print("="*79)
            print("| Nama            |       NIM       |  Tugas  |  UTS  |  UAS  |  Nilai Akhir  |")
            print("="*79)
            print("| {0:15s} | {1:15d} | {2:7d} | {3:5d} | {4:5d} | {5:9.2f}    |"
                  .format(nama, nim, tugas, uts, uas, nilaiakhir))
            print("="*79)
        else:
            print("Nama {0} Tidak Ditemukan".format(nama))
```
Jika menginput 'c' makan akan diminta untuk memasukkan nama yang ingin dicari. Apabila nama yang dicari ada dalam dictionary maka outputnya akan menampilkan data dari nama tersebut.

- Menampilkan data
```python
elif a.lower() == 'l':
        if x.items():
            print("="*84)
            print("|                                  Daftar Mahasiswa                                |")
            print("="*84)
            print("|No. | Nama            |       NIM       |  Tugas  |  UTS  |  UAS  |  Nilai Akhir  |")
            print("="*84)
            i = 0
            for z in x.items():
                i += 1
                print("| {no:2d} | {0:15s} | {1:15d} | {2:7d} | {3:5d} | {4:5d} | {5:9.2f}     |"
                      .format(z[0][:13], z[1][0], z[1][1], z[1][2], z[1][3], z[1][4], no=i))
            print("=" * 84)
        else:
            print("="*84)
            print("|                                  Daftar Mahasiswa                                |")
            print("="*84)
            print("|No. | Nama            |       NIM       |  Tugas  |  UTS  |  UAS  |  Nilai Akhir  |")
            print("="*84)
            print("|                                   TIDAK ADA DATA                                 |")
            print("="*84)
```
Jika menginput 'l' maka akan menampilkan data yang sudah kita masukkan sebelumnya. Jika belum memasukkan data maka outputnya menjadi "TIDAK ADA DATA"

- Menghentikan perulangan
```python
 elif a. lower() == 'k':
        print("=====| Keluar |=====")
        break
```
Apabila menginput 'k' maka program langsung berhenti

## Tampilan Program
- Menambahkan Data

![gambar](tambahdata.png)

- Tampil Data

![gambar](tampildata.png)

- Keluar

![gambar](keluar.png)

## Flowchart

![gambar](flowchart.prt5.png)
