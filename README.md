# MINI PROJECT 1

NAMA: HANIF AMELIA PUTRI

NIM: 2509116075

KELAS: SISTEM INFORMASI B

                                              SISTEM CATATAN PENGGUNAAN LABORATORIUM KOMPUTER

# DESKRIPSI SINGKAT

Program ini merupakan sistem pencatatan penggunaan laboratorium komputer sederhana. Melalui menu yang tersedia, pengguna dapat melihat daftar catatan, menambahkan data baru, mengubah data lama, maupun menghapus catatan yang sudah tidak diperlukan. Dengan sistem ini, pengguna dapat melakukan pencatatan secara sederhana namun terstruktur. Program berjalan terus sampai pengguna memilih keluar, sehingga memudahkan dalam mengelola data penggunaan laboratorium komputer tanpa harus menulis ulang secara manual.

# FLOWCHART

<img width="1480" height="1412" alt="catatan lab drawio" src="https://github.com/user-attachments/assets/9a35a67f-c489-4c55-97dc-cebe9cf84d6f" />

PENJELASAN:

Start: Program dimulai.

Menu Utama (1–5): Pengguna memilih menu yang tersedia.

Menu 1 (Lihat Catatan): 
Jika pilih cek ruangan tertentu maka pengguna menginput nama ruangan yang ingin di cek dan sistem akan menampilkan ruangan apakah dipakai/kosong.
Jika tidak sistem akan menampilkan semua catatan.

Menu 2 (Tambah Catatan): Pengguna menginput ruangan, kelas, tanggal, dan jam lalu data disimpan dan catatan berhasil ditambahkan.

Menu 3 (Ubah Catatan): Sistem akan menampilkan catatan lalu pengguna menginput input data baru dan data berhasil diubah.

Menu 4 (Hapus Catatan): Sistem akan menampilkan catatan lalu pengguna memilih catatan yang ingin dihapus dan data berhasil dihapus.

Menu 5 (Keluar): Sistem akan mengkonfirmasi apakah ingin keluar, jika iya program berhenti dan jika tidak kembali ke menu utama.

Setelah menjalankan menu 1–4: Sistem akan menanyakan apakah ingin kembali ke menu utama, jika iya kembali ke menu utama dan jika tidak program End.

End: Program selesai dijalankan.

# PROGRAM PYTHON
```python
penggunaan_lab = [
    ("D404", "Kelas A", "10-09-2025", "08:00-09:00"),
    ("D302", "Kelas B", "10-09-2025", "09:00-10:00"),
    ("D401", "Kelas C", "10-09-2025", "10:00-11:00"),
    ("D203", "Kelas D", "10-09-2025", "11:00-12:00"),
    ("D202", "Kelas E", "10-09-2025", "13:00-14:00")
]

while True:
    print("Daftar Menu Sistem Catatan Penggunaan Lab Komputer")
    print("1. Lihat Catatan")
    print("2. Tambah Catatan")
    print("3. Ubah Catatan")
    print("4. Hapus Catatan")
    print("5. Keluar")

    Pilih_Menu = input("Ingin Memilih Menu Apa (Ketik 1-5): ")

    if Pilih_Menu == "1":
        cek = input("Apakah ingin cek ruangan tertentu? (iya/tidak): ")
        if cek == "iya":
            cari = input("Masukkan Nama Ruangan: ")
            if penggunaan_lab[0][0] == cari:
                print("Ruangan", cari, "sudah dipakai oleh", penggunaan_lab[0][1], "pada", penggunaan_lab[0][2], "jam", penggunaan_lab[0][3])
            elif penggunaan_lab[1][0] == cari:
                print("Ruangan", cari, "sudah dipakai oleh", penggunaan_lab[1][1], "pada", penggunaan_lab[1][2], "jam", penggunaan_lab[1][3])
            elif penggunaan_lab[2][0] == cari:
                print("Ruangan", cari, "sudah dipakai oleh", penggunaan_lab[2][1], "pada", penggunaan_lab[2][2], "jam", penggunaan_lab[2][3])
            elif penggunaan_lab[3][0] == cari:
                print("Ruangan", cari, "sudah dipakai oleh", penggunaan_lab[3][1], "pada", penggunaan_lab[3][2], "jam", penggunaan_lab[3][3])
            elif penggunaan_lab[4][0] == cari:
                print("Ruangan", cari, "sudah dipakai oleh", penggunaan_lab[4][1], "pada", penggunaan_lab[4][2], "jam", penggunaan_lab[4][3])
            else:
                print("Ruangan", cari, "masih kosong.")
        else:
            print("Semua Catatan:", penggunaan_lab)

    elif Pilih_Menu == "2":
        ruang = input("Masukan Ruangan: ")
        kelas = input("Masukan Kelas: ")
        tanggal = input("Masukan Tanggal (DD-MM-YYY): ")
        jam = input("Masukan Jam Penggunaan (00:00-00:00): ")
        penggunaan_lab.append((ruang, kelas, tanggal, jam))
        print("Catatan ditambahkan", penggunaan_lab)

    elif Pilih_Menu == "3":
        print("Catatan yang ada:")
        print("1.", penggunaan_lab[0])
        print("2.", penggunaan_lab[1])
        print("3.", penggunaan_lab[2])
        print("4.", penggunaan_lab[3])
        print("5.", penggunaan_lab[4])
        pilih = input("Pilih nomor catatan yang mau diubah (1-5): ")

        ruang = input("Masukan Ruangan Baru: ")
        kelas = input("Masukan Kelas Baru: ")
        tanggal = input("Masukan Tanggal (DD-MM-YYY): ")
        jam = input("Masukan Jam Penggunaan (00:00-00:00): ")

        if pilih == "1":
            penggunaan_lab[0] = (ruang, kelas, tanggal, jam)
        elif pilih == "2":
            penggunaan_lab[1] = (ruang, kelas, tanggal, jam)
        elif pilih == "3":
            penggunaan_lab[2] = (ruang, kelas, tanggal, jam)
        elif pilih == "4":
            penggunaan_lab[3] = (ruang, kelas, tanggal, jam)
        elif pilih == "5":
            penggunaan_lab[4] = (ruang, kelas, tanggal, jam)

        print("Catatan berhasil diubah!")

    elif Pilih_Menu == "4":
        print("Catatan yang ada:")
        print("1.", penggunaan_lab[0])
        print("2.", penggunaan_lab[1])
        print("3.", penggunaan_lab[2])
        print("4.", penggunaan_lab[3])
        print("5.", penggunaan_lab[4])
        pilih = input("Pilih nomor catatan yang mau dihapus (1-5): ")

        if pilih == "1":
            penggunaan_lab.pop(0)
        elif pilih == "2":
            penggunaan_lab.pop(1)
        elif pilih == "3":
            penggunaan_lab.pop(2)
        elif pilih == "4":
            penggunaan_lab.pop(3)
        elif pilih == "5":
            penggunaan_lab.pop(4)

        print("Catatan berhasil dihapus!")

    elif Pilih_Menu == "5":
        keluar = input("Apakah benar ingin keluar? (iya/tidak): ")
        if keluar == "iya":
            print("Anda keluar dari sistem...")
            break
        else:
            continue   

    else:
        print("Pilihan tidak valid, coba lagi!")

    
    if Pilih_Menu in ["1","2","3","4"]:
        ulang = input("Apakah ingin kembali ke menu utama? (iya/tidak): ")
        if ulang == "iya":
            continue
        else:
            print("Anda keluar dari sistem...")
            break
```

# TAMPILAN AWAL
<img width="1647" height="368" alt="Screenshot_20250914_103809" src="https://github.com/user-attachments/assets/5edbf74f-0761-4c7e-9c53-7cc82e2cac63" />

Penjelasan: Tampilan awal akan menampilkan "Daftar Menu Sistem Catatan Penggunaan Lab Komputer", dan sistem akan menanyakan "Ingin Memilih Menu Apa?".

# KONDISI 1
<img width="1656" height="879" alt="Screenshot_20250914_093853" src="https://github.com/user-attachments/assets/136fa2c3-90c2-4c51-b597-a760b94e6479" />

Penjelasan: Kondisi 1 ketika pengguna ingin memilih menu 1 (lihat catatan), sistem akan menanyakan "Apakah Ingin cek ruangan tertentu?", jika iya maka pengguna diarahkan untuk menginput nama ruangan yang ingin dicek dan sistem akan menampilkan ruangan kosong/tidak. Jika tidak sistem akan menampilkan seluruh daftar catatan ruangan.

# KONDISI 2
<img width="1648" height="526" alt="Screenshot_20250914_094853" src="https://github.com/user-attachments/assets/a1b10fd2-816a-487f-9f7d-d964892097a1" />

Penjelasan: Kondisi 2 ketika pengguna ingin memilih menu 2 (Tambah Catatan), pengguna akan diarahkan untuk menginput nama ruangan, kelas, tanggal, dan jam penggunaan. Setelah itu sistem akan menambah dan menampilkan daftar catatan baru.

# KONDISI 3
<img width="1650" height="815" alt="Screenshot_20250914_095729" src="https://github.com/user-attachments/assets/4919459f-3db7-45f7-9c07-3ed1283b4706" />

Penjelasan: Kondisi 3 ketika pengguna ingin memilih menu 3 (Ubah Catatan), sistem akan menampilkan daftar catatan penggunaan laboratorium komputer, lalu sistem akan menanyakan nomor catatan ruangan yang ingin diubah dan pengguna akan diarahkan untuk mengisi nama ruangan baru, kelas, tanggal dan jam penggunaan. Setelah itu, sistem akan mengubah daftar catatan sesuai permintaan pengguna. Jika pengguna ingin melihat daftar catatan yang telah diubah, maka pengguna memilih kembali menu 1 untuk melihat catatan.

# KONDISI 4
<img width="1660" height="701" alt="Screenshot_20250914_101114" src="https://github.com/user-attachments/assets/ed742afb-61a4-425b-a086-70eae0a2676a" />

Penjelasan: Kondisi 4 ketika pengguna ingin memilih menu 4 (Hapus Catatan), sistem akan menampilkan daftar catatan penggunaan laboratorium komputer, lalu sistem akan menanyakan nomor catatan yang ingin dihapus dan sistem akan menghapus catatan sesuai permintaan pengguna. Jika pengguna ingin melihat catatan sudah terhapus atau belum, pengguna bisa memilih kembali menu 1 untuk melihat catatan.

# KONDISI 5
<img width="1658" height="603" alt="Screenshot_20250914_102916" src="https://github.com/user-attachments/assets/ce8572b4-63e6-4c2d-af7d-7e4892b52d19" />
Penjelasan: Kondisi 5 ketika pengguna ingin memilih menu 5 (keluar), sistem akan menanyakan "Apakah benar ingin keluar?". jika tidak maka pengguna akan diarahkan kembali ke menu utama, jika iya maka sistem akan menampilkan "Anda keluar dari sistem..." dan sistem akan selesai dijalankan.

# KONDISI 6
<img width="1640" height="416" alt="Screenshot_20250914_105504" src="https://github.com/user-attachments/assets/795e865c-93b2-4a38-ab7c-5c3bbb235efe" />
Penjelasan: Kondisi 6 ketika pengguna memasukan variabel yang tidak ada dalam daftar menu maka sistem akan menampilkan "Pilihan tidak valid, coba lagi!", lalu sistem akan menampilkan kembali menu utama.











