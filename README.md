# praktikum-5
## Latihan 1

![soal 1](https://github.com/user-attachments/assets/3aea3a1a-43d3-4681-a023-76f7a2278d27)

```python
kontak = {
    "Ari": "081267888",
    "Dina": "087677776"
}
````
Buat Dictionary daftar kontak

```Python
print("Kontak Ari:", kontak["Ari"])
````
Tampilkan kontaknya Ari

```Python
kontak["Riko"] = "087654544"
````
Tambah kontak baru dengan nama Riko, nomor 087654544

```Python
kontak["Dina"] = "088999776"
````
Ubah kontak Dina dengan nomor baru 088999776

```Python
print("Semua Nama:", list(kontak.keys()))
````
Tampilkan semua Nama

```Python
print("Semua Nomor:", list(kontak.values()))
````
Tampilkan semua Nomor

```Python
print("Daftar Nama dan Nomor:")
for nama, nomor in kontak.items():
    print(nama, ":", nomor)
````
Tampilkan daftar Nama dan nomornya

```Python
del kontak["Dina"]
````
Hapus kontak Dina

```Python
print("Daftar Nama dan Nomor setelah menghapus Dina:")
for nama, nomor in kontak.items():
    print(nama, ":", nomor)
````
Tampilkan daftar Nama dan Nomor setelah menghapus Dina

## Menampilkan daftar nilai mahasiswa

![daaf](https://github.com/user-attachments/assets/5b58b40a-271a-4e54-a8ac-d31b28f17ac8)

```Python
import time

def tambah_data(data):
    nim = input("masukan nim anda: ")
    nama = input("masukan nama anda: ")
    nilai_tugas = float(input("masukan nilai tugas: "))
    nilai_uts = float(input ("masukan nilai uts: "))
    nilai_uas = float(input ("masukan nilai uas: "))
    nilai_akhir = (nilai_tugas * 0.3) + (nilai_uts * 0.35) + (nilai_uas * 0.3)
    
    data[nim] = {
        'nama' : nama,
        'nilai_tugas' : nilai_tugas,
        'nilai_uts':nilai_uts,
        'nilai_uas':nilai_uas,    
        'nilai_akhir':round(nilai_akhir, 2)
    }
    
def ubah_data(data):
    nim = input("masukan nim yang ingin di ubah: ")
    if nim in data:
        print("Data ditemukan. masukkan data baru")
        nama = input("masukan nama anda: ")
        nilai_tugas = float(input("masukan nilai tugas: "))
        nilai_uts = float(input ("masukan nilai uts: "))
        nilai_uas = float(input ("masukan nilai uas: "))
        nilai_akhir = (nilai_tugas * 0.3) + (nilai_uts * 0.35) + (nilai_uas * 0.3)
        
        data[nim] = {
            'nama' : nama,
            'nilai_tugas' : nilai_tugas,
            'nilai_uts':nilai_uts,
            'nilai_uas':nilai_uas,    
            'nilai_akhir':round(nilai_akhir, 2)
        }
        print("Data Berhasil diubah")
    else:
        print("Nim tidak ditemukan")
        
def hapus_data(data):
    nim = input("temukan data anda dengan memasukan nim jika ingin di hapus: ")
    if nim in data:
        del data[nim]
        print("Data berhasil dihapus")
    else:
        print("Nim tidak ditemukan")
        
def cari_data(data):
    nim = input("masukan nim yang ingin dicari: ")
    if nim in data:
        info = data[nim]
        print("\nData ditemukan:")
        print(f'''
              nim           : {nim}
              nama          : {info['nama']}
              nilai_tugas   : {info['nilai_tugas']}
              nilai_uts     : {info['nilai_uts']}
              nilai_uas     : {info['nilai_uas']}
              nilai_akhir   : {info['nilai_akhir']}
              ''')
    else:
        print("nim tidak ditemukan ")

def keluar_program():
    print("program akan dihentikan")
    time.sleep(1)
    print("3...")
    time.sleep(1)
    print("2...")
    time.sleep(1)
    print("1...")
    time.sleep(1)
    print("Program berhasil dihentikan")
    exit()
    
def lihat_data(data):
    print("\nDaftar Nilai: ")
    print("="*83)
    print("| NO | NAMA                           | NIM       | TUGAS | UTS   | UAS   | AKHIR |")
    print("="*83)
    
    for i, (nim, info) in enumerate (data.items(), start=1):
        print(f"| {i:<2} | {info['nama']:<30} | {nim:<9} | {info['nilai_tugas']:<5} | {info['nilai_uts']:<5} | {info['nilai_uas']:<5} | {info['nilai_akhir']:<5.2f} |")
    
    print("="*83)
    
def main():
    data = dict()
    
    while True:
        print("\n(L)ihat, (T)ambah, (U)bah, (H)apus, (C)ari (K)eluar")
        pilihan = input("\nPilih menu: ").lower()
        
        if pilihan == "l":
            lihat_data(data)
        elif pilihan == "t":
            tambah_data(data)
        elif pilihan == "u":
            ubah_data(data)
        elif pilihan == "h":
            hapus_data(data)
        elif pilihan == "c":
            cari_data(data)
        elif pilihan == "k":
            keluar_program()
        else:
            print("pilihan tidak valid")
            
if __name__ == "__main__":
    main()
````
program sederhana yang akan menampilkan daftar nilai mahasiswa.

```Python
def tambah_data(data):
    nim = input("masukan nim anda: ")
    nama = input("masukan nama anda: ")
    nilai_tugas = float(input("masukan nilai tugas: "))
    nilai_uts = float(input ("masukan nilai uts: "))
    nilai_uas = float(input ("masukan nilai uas: "))
    nilai_akhir = (nilai_tugas * 0.3) + (nilai_uts * 0.35) + (nilai_uas * 0.3)
````

membuat fungsi def tambah_data(), yang berproses ke fungsi `input()` , dan berproses ke (nilai_akhir)

```Python
data[nim] = {
        'nama' : nama,
        'nilai_tugas' : nilai_tugas,
        'nilai_uts':nilai_uts,
        'nilai_uas':nilai_uas,    
        'nilai_akhir':round(nilai_akhir, 2)
    }
````
masih didalam fungsi `tambah_data()` ,fungsi ini disebut dengan `dictionary` yang akan menambah menambah data, dan informasi data

```Python
def ubah_data(data):
    nim = input("masukan nim yang ingin di ubah: ")
    if nim in data:
        print("Data ditemukan. masukkan data baru")
        nama = input("masukan nama anda: ")
        nilai_tugas = float(input("masukan nilai tugas: "))
        nilai_uts = float(input ("masukan nilai uts: "))
        nilai_uas = float(input ("masukan nilai uas: "))
        nilai_akhir = (nilai_tugas * 0.3) + (nilai_uts * 0.35) + (nilai_uas * 0.3)
````
membuat fungsi ubah_data(), yang berproses ke fungsi `input()` dan `decicion` if nim data, yang akan merubah data yang sebelumnya di tambahkan, yang akan memilih perubahan tersebut melalui fungsi `input()`

```Python
data[nim] = {
            'nama' : nama,
            'nilai_tugas' : nilai_tugas,
            'nilai_uts':nilai_uts,
            'nilai_uas':nilai_uas,    
            'nilai_akhir':round(nilai_akhir, 2)
        }
        print("Data Berhasil diubah")
    else:
        print("Nim tidak ditemukan")
````
masih di fungsi `ubah_data()` , fungsi ini `dictionary` yang akan menambah kan data atau informasi, dan akan berproses ke desision `else` akan mencetak output

```Python
def hapus_data(data):
    nim = input("temukan data anda dengan memasukan nim jika ingin di hapus: ")
    if nim in data:
        del data[nim]
        print("Data berhasil dihapus")
    else:
        print("Nim tidak ditemukan")
````

menambah kan fungsi `hapus_data()` yang akan berproses ke fungsi `input()` untuk mencari data mana yang mau dihapus, desision if nim in data yang akan berproses ke fungsi `del` data[nim], yang berfungsi untuk menghapus data, dan akan berproses ke desision `else` yang akan mencetak output

```Python
def cari_data(data):
    nim = input("masukan nim yang ingin dicari: ")
    if nim in data:
        info = data[nim]
        print("\nData ditemukan:")
        print(f'''
              nim           : {nim}
              nama          : {info['nama']}
              nilai_tugas   : {info['nilai_tugas']}
              nilai_uts     : {info['nilai_uts']}
              nilai_uas     : {info['nilai_uas']}
              nilai_akhir   : {info['nilai_akhir']}
              ''')
    else:
        print("nim tidak ditemukan ")
````
menambahkan fungsi `cari_data()` yang akan berproses ke fungsi `input()`, untuk mencari data mana yang ingin dicari, desision if nim in data yang akan berproses ke variable (info), yang akan mencetak menggunakan `f` untuk bisa memasukan fungsi `{}` ke dalam cetak, yang akan berproses ke variable tersebut, dan akan berproses ke desision `else` yang akan mencetak output

```Python
def keluar_program():
    print("program akan dihentikan")
    time.sleep(1)
    print("3...")
    time.sleep(1)
    print("2...")
    time.sleep(1)
    print("1...")
    time.sleep(1)
    print("Program berhasil dihentikan")
    exit()
````
membuat fungsi `keluar_program()` yang mencetak output, dan memberikan fungsi `time.sleep(1)` yang akan mengeluarkan output delay 1 detik, dan akan berproses ke fungsi `exit()`

```Python
def lihat_data(data):
    print("\nDaftar Nilai: ")
    print("="*83)
    print("| NO | NAMA                           | NIM       | TUGAS | UTS   | UAS   | AKHIR |")
    print("="*83)
    
    for i, (nim, info) in enumerate (data.items(), start=1):
        print(f"| {i:<2} | {info['nama']:<30} | {nim:<9} | {info['nilai_tugas']:<5} | {info['nilai_uts']:<5} | {info['nilai_uas']:<5} | {info['nilai_akhir']:<5.2f} |")
    
    print("="*83)
````
membuat fungsi `lihat_data()` yang akan mencetak suatu design table, dan akan berproses ke fungsi `for` yang akan mencetak suatu data `dictionary` di fungsi `tambah_data()`

```Python
def main():
    data = dict()
    
    while True:
        print("\n(L)ihat, (T)ambah, (U)bah, (H)apus, (C)ari (K)eluar")
        pilihan = input("Pilih menu: ").lower()
        
        if pilihan == "l":
            lihat_data(data)
        elif pilihan == "t":
            tambah_data(data)
        elif pilihan == "u":
            ubah_data(data)
        elif pilihan == "h":
            hapus_data(data)
        elif pilihan == "c":
            cari_data(data)
        elif pilihan == "k":
            keluar_program()
        else:
            print("pilihan tidak valid")
````
membuat fungsi `main()` untuk menjalankan fungsi yang dibuat diatas, dengan memasukan fungsi `input()` dengan pilihan "l","t","u","h","c","k" yang akan berproses ke fungsi yang telah di buat, dan akan berproses ke desision `else` yang akan mencetak output

```Python
if __name__ == "__main__":
    main()
````
fungsi ini untuk menjalankan fungsi `main()`

<p>hasil program tersebut</p>

![1](https://github.com/user-attachments/assets/dfcbc517-86c1-405a-a20e-61c7375e990c)

![2](https://github.com/user-attachments/assets/207f7135-152a-4d11-8748-922d162cea8a)

![3](https://github.com/user-attachments/assets/755ec20a-7f46-4caa-8ba7-7b82f63ee811)

![4](https://github.com/user-attachments/assets/c1502a7a-b91b-44c6-a281-fbca4efc66ce)


<p>flowchart</p>

![flow bp 1](https://github.com/user-attachments/assets/58437db1-b69e-436c-8761-f543edfa6973)

![flo bp2](https://github.com/user-attachments/assets/23b06cb3-6b89-4bbd-996a-28d1572111ea)






