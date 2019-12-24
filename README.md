# Praktikum 5

# Program Data Mahasiswa

Pada praktikum 5, kita akan membuat program sederhana untuk membuat data mahasiswa menggunakan Dictionary dengan python.

# Codingan

x = {}

while True:
    c = input("\n(T)ambah, (U)bah, (H)apus, (C)ari, (L)ihat, (K)eluar: ")

    if c.lower() == 't':
        print("Tambah Data")
        nama = input("Nama           : ")
        nim = int(input("NIM            : "))
        uts = int(input("Nilai UTS      : "))
        uas = int(input("Nilai UAS      : "))
        tugas = int(input("Nilai Tugas    : "))
        akhir = tugas*30/100 + uts*35/100 + uas*35/100
        x[nama] = nim, uts, uas, tugas, akhir

    elif c.lower() == 'u':
        print("Ubah Data")
        nama = input("Masukkan Nama  : ")
        if nama in x.keys():
            nim = int(input("NIM            : "))
            uts = int(input("Nilai UTS      : "))
            uas = int(input("Nilai UAS      : "))
            tugas = int(input("Nilai Tugas    : "))
            akhir = tugas * 30 / 100 + uts * 35 / 100 + uas * 35 / 100
            x[nama] = nim, uts, uas, tugas, akhir
        else:
            print("Nama {0} tidak ditemukan".format(nama))

    elif c.lower() == 'h':
        print("Hapus Data")
        nama = input("Masukkan Nama  : ")
        if nama in x.keys():
            del x[nama]
        else:
            print("Nama {0} Tidak Ditemukan".format(nama))

    elif c.lower() == 'c':
        print("Cari Data")
        nama = input("Masukkan Nama : ")
        if nama in x.keys():
            print("="*73)
            print("|                             Daftar Mahasiswa                          |")
            print("="*73)
            print("| Nama            |       NIM       |  UTS  |  UAS  |  Tugas  |  Akhir  |")
            print("="*73)
            print("| {0:15s} | {1:15d} | {2:5d} | {3:5d} | {4:7d} | {5:7.2f} |"
                  .format(nama, nim, uts, uas, tugas, akhir))
            print("="*73)
        else:
            print("Nama {0} Tidak Ditemukan".format(nama))

    elif c.lower() == 'l':
        if x.items():
            print("="*78)
            print("|                               Daftar Mahasiswa                             |")
            print("="*78)
            print("|No. | Nama            |       NIM       |  UTS  |  UAS  |  Tugas  |  Akhir  |")
            print("="*78)
            i = 0
            for z in x.items():
                i += 1
                print("| {no:2d} | {0:15s} | {1:15d} | {2:5d} | {3:5d} | {4:7d} | {5:7.2f} |"
                      .format(z[0][:13], z[1][0], z[1][1], z[1][2], z[1][3], z[1][4], no=i))
            print("=" * 78)
        else:
            print("="*78)
            print("|                               Daftar Mahasiswa                             |")
            print("="*78)
            print("|No. | Nama            |       NIM       |  UTS  |  UAS  |  Tugas  |  Akhir  |")
            print("="*78)
            print("|                                TIDAK ADA DATA                              |")
            print("="*78)

    elif c. lower() == 'k':
        break

    else:
        print("Pilih menu yang tersedia")

# Penjelasan :

1.) Pertama buatlah sebuah dictionary kosong yang nantinya akan diinputkan data ketika program dijalankan.

    x = {}

2.) Membuat kondisi perulangan dan sebuah keterangan untuk pilihan menu yang akan menjalankan program.

    while True:
       c = input("\n(T)ambah, (U)bah, (H)apus, (C)ari, (L)ihat, (K)eluar: ")

3.) Selanjutnya Membuat syntax untuk menambahkan data.
    
    if c.lower() == 't':
        print("Tambah Data")
        nama = input("Nama           : ")
        nim = int(input("NIM            : "))
        uts = int(input("Nilai UTS      : "))
        uas = int(input("Nilai UAS      : "))
        tugas = int(input("Nilai Tugas    : "))
        akhir = tugas*30/100 + uts*35/100 + uas*35/100
        x[nama] = nim, uts, uas, tugas, akhir

Disini apabila kita menginputkan 't' maka akan diminta untuk menginputkan beberapa data. Data yang di inputkan akan masuk ke dictionary 'x' yang telah dibuat tadi dengan data 'nama' sebagai keys dan sisanya sebagai valuesnya.

4.) Membuat syntax untuk mengubah data.
   
        elif c.lower() == 'u':
        print("Ubah Data")
        nama = input("Masukkan Nama  : ")
        if nama in x.keys():
            nim = int(input("NIM            : "))
            uts = int(input("Nilai UTS      : "))
            uas = int(input("Nilai UAS      : "))
            tugas = int(input("Nilai Tugas    : "))
            akhir = tugas * 30 / 100 + uts * 35 / 100 + uas * 35 / 100
            x[nama] = nim, uts, uas, tugas, akhir
        else:
            print("Nama {0} tidak ditemukan".format(nama))

Apabila kita menginput 'u' maka akan ada keterangan untuk mengubah data dan akan diminta untuk menginputkan nama yang mau diubah datanya, apabila nama tidak ada maka outputnya "Nama {} tidak ditemukan". Dimana {} adalah nama/data yang mau di ubah.

5.) Membuat syntax untuk menghapus data.
    
    elif c.lower() == 'h':
        print("Hapus Data")
        nama = input("Masukkan Nama  : ")
        if nama in x.keys():
            del x[nama]
        else:
            print("Nama {0} Tidak Ditemukan".format(nama))

Apabila kita menginput 'h' maka akan diminta menginput nama yang akan dihapus. Jika nama ada di dalam dictionary, maka system akan menghapus keys/nama tersebut beserta valuesnya pada statement del x[nama].

6.) Membuat syntax untuk mencari data.
    
    elif c.lower() == 'c':
        print("Cari Data")
        nama = input("Masukkan Nama : ")
        if nama in x.keys():
            print("="*73)
            print("|                             Daftar Mahasiswa                          |")
            print("="*73)
            print("| Nama            |       NIM       |  UTS  |  UAS  |  Tugas  |  Akhir  |")
            print("="*73)
            print("| {0:15s} | {1:15d} | {2:5d} | {3:5d} | {4:7d} | {5:7.2f} |"
                  .format(nama, nim, uts, uas, tugas, akhir))
            print("="*73)
        else:
            print("Nama {0} Tidak Ditemukan".format(nama))

Apabila kita menginputkan 'c' maka akan diminta untuk memasukkan nama yang akan dicari. Apabila nama yang dicari ada di dalam dictionary maka outputnya akan menampilkan data dari nama tersebut.

7.) Membuat syntax untuk melihat atau menampilkan data.
    
    elif c.lower() == 'l':
        if x.items():
            print("="*78)
            print("|                               Daftar Mahasiswa                             |")
            print("="*78)
            print("|No. | Nama            |       NIM       |  UTS  |  UAS  |  Tugas  |  Akhir  |")
            print("="*78)
            i = 0
            for z in x.items():
                i += 1
                print("| {no:2d} | {0:15s} | {1:15d} | {2:5d} | {3:5d} | {4:7d} | {5:7.2f} |"
                      .format(z[0][:13], z[1][0], z[1][1], z[1][2], z[1][3], z[1][4], no=i))
            print("=" * 78)
        else:
            print("="*78)
            print("|                               Daftar Mahasiswa                             |")
            print("="*78)
            print("|No. | Nama            |       NIM       |  UTS  |  UAS  |  Tugas  |  Akhir  |")
            print("="*78)
            print("|                                TIDAK ADA DATA                              |")
            print("="*78)

Apabila kita menginput 'l' maka sistem akan menampilkan data - data yang sudah di masukkan. Jika belum memasukkan data maka outputnya menjadi "TIDAK ADA DATA".

8.) Membuat syntax untuk menghentikan perulangan.
        
        elif c. lower() == 'k':
            break
Apabila kita menginput 'k' maka program akan langsung berhenti.

9.) Membuat syntax untuk memilih pilihan yang tidak ada di menu.
    
        else:
            print("Pilih menu yang tersedia")
Jika kita menginputkan selain yang ada pada menu (t, u, h, c, l, k) maka akan diminta untuk memilih menu yang tersedia.

# Tampilan Program Saat Dijalankan

+ Tambah data & Lihat data

![2019-12-21 21_02_19-Run - Pertemuan4 - Tambah + Lihat](https://user-images.githubusercontent.com/56252129/71395578-2137e200-2649-11ea-9c2d-c7a116769e22.png)

+ Ubah data & Lihat data

![2019-12-21 21_06_01-Run - Pertemuan4 - Ubah + Lihat](https://user-images.githubusercontent.com/56252129/71395755-e6827980-2649-11ea-9f01-396bb7c04cd0.png)

+ Cari data

![2019-12-24 12_43_33-pertemuan4  J__Mata Kuliah_Bahasa Pemrograman_pertemuan4  -  _Praktikum5 py - Find data](https://user-images.githubusercontent.com/56252129/71396225-d7043000-264b-11ea-9491-8e6c3693ac77.png)


+ Hapus data & Lihat data

![2019-12-24 12_47_05-Praktikum5_README md at master · JOdiCO_Praktikum5 - Delete](https://user-images.githubusercontent.com/56252129/71396246-ed11f080-264b-11ea-978d-ee0cd4549070.png)

+ Keluar

![2019-12-24 12_48_33-Run - pertemuan4 - End](https://user-images.githubusercontent.com/56252129/71396266-fdc26680-264b-11ea-85c7-f060f539f540.png)

> End
