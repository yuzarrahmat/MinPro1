# MinPro1
Nama : Yuzar Rahmat Rafi Alhaq, Nim : 2509116025, Sistem Informasi A '2025
# Program Sistem Manajemen Progress Game

def main():

    game_list = []  # Ini adalah List Game yang Saat Ini Ku Mainkan
    pilihan = [] # Menampung data
    
    while True:
        print("\n=== SISTEM MANAJEMEN PROGRESS GAME ===")
        print("1. Tambah Game Baru")
        print("2. Lihat Daftar Game")
        print("3. Update Progress Game")
        print("4. Hapus Game")
        print("5. Reset dan Keluar")
        
        pilihan = input("Pilih menu (1-5): ")
        
        if pilihan == '1':
            # Menambah game baru
            judul = input("Judul Game: ")
            try:
                progress = int(input("Progress (%): "))
                if progress < 0 or progress > 100:
                    print("Progress harus antara 0-100%!")
                    continue
            except ValueError:
                print("Progress harus berupa angka!")
                continue
                
            # Tentukan status berdasarkan progress
            if progress == 0:
                status = "Baru Dimulai"
            elif progress == 100:
                status = "Sudah Tamat/Selesai"
            else:
                status = "Lagi Dimainkan"
                
            # Simpan sebagai tuple dalam list
            game_baru = (judul, progress, status)
            game_list.append(game_baru)
            print("Game ", judul, "berhasil ditambahkan!")
            
        elif pilihan == '2':
            # Menampilkan daftar game ku
            if not game_list:
                print("Belum ada game yang ditambahkan.")
            else:
                print("\nDAFTAR GAME:")
                print("=" * 45 * len(game_list))
                print(game_list)
                print("=" * 45 * len(game_list))

        elif pilihan == '3':
            # Update progress game ku
            if not game_list:
                print("Belum ada game yang ditambahkan.")
                continue
                
            # Tampilkan game untuk dipilih
            print("\nPilih game yang akan diupdate:")
            print("=" * 45 * len(game_list))
            print(game_list)
            print("=" * 45 * len(game_list))
            print("Input = 1, 2, 3, dst sesuai urutan game di list")
            
            try:
                pilihan = int(input("Nomor game: ")) - 1
                if 0 <= pilihan < len(game_list):
                    try:
                        progress_baru = int(input("Progress baru (%): "))
                        if progress_baru < 0 or progress_baru > 100:
                            print("Progress harus antara 0-100%!")
                            continue
                    except ValueError:
                        print("Progress harus berupa angka!")
                        continue
                        
                    # Update status berdasarkan progress baru
                    if progress_baru == 0:
                        status_baru = "Baru Dimulai"
                    elif progress_baru == 100:
                        status_baru = "Sudah Tamat/Selesai"
                    else:
                        status_baru = "Lagi Dimainkan"

                    # Update data game
                    game_list[pilihan] = (game_list[pilihan][0], game_list[pilihan][1], game_list[pilihan][2], progress_baru, status_baru)
                    print("Progress game berhasil diupdate!")
                else:
                    print("Nomor tidak valid!")
            except ValueError:
                print("Input harus berupa angka!")
                
        elif pilihan == '4':
            # Hapus game dari List  
            if not game_list:
                print("Belum ada game yang ditambahkan.")
                continue
                
            # Tampilkan game untuk dipilih
            print("\nPilih game yang akan dihapus:")
            print("=" * 45 * len(game_list))
            print(game_list)
            print("=" * 45 * len(game_list))
            print("Input = 1, 2, 3, dst sesuai urutan game di list")
            
            try:
                pilihan = int(input("Nomor game: ")) - 1
                if 0 <= pilihan < len(game_list):
                    game_terhapus = game_list.pop(pilihan)
                    print("Game ", game_terhapus[0], "berhasil dihapus!")
                else:
                    print("Nomor tidak valid!")
            except ValueError:
                print("Input harus berupa angka!")
                
        elif pilihan == '5':
            print("Mantap, Gaming boleh jalan, tapi Jangan lupa belajar, olahraga, ibadah, dan istirahat Masbro.")
            break
            
        else:
            print("Pilihan tidak valid. Silakan pilih 1-5.")
          
if __name__ == "__main__":
    main()


# Flowchart
![Flowchart sistem manajemen progress game (2)](https://github.com/user-attachments/assets/6230b795-0ae7-4c8d-b457-5a0d1597a5ea)

# Penjelasan Menu Pilihan
<img width="1327" height="216" alt="Menu Pilihan" src="https://github.com/user-attachments/assets/d73faf69-87f5-4f19-aff5-7b40e1dccc9a" />
Ini adalah tampilan awal saat program dijalankan, yang mana adalah menu pilihan utama dengan urutan 1-5 serta memiliki fungsi masing-masing sesuai dengan yang tertulis.

# Penjelasan Pilihan 1
<img width="466" height="228" alt="Menu 1 Valid progres" src="https://github.com/user-attachments/assets/3f4db82e-3136-4b5e-ab2f-00310faa5615" />
<img width="427" height="225" alt="Menu 1 Invalid non angka progres" src="https://github.com/user-attachments/assets/5e99c21c-1243-4157-b8bc-882dff95d831" />
<img width="386" height="237" alt="Menu 1 Invalid not in range progres" src="https://github.com/user-attachments/assets/a083ee68-9e39-47f7-8ff0-2b991bff83fd" />
saat memilih pilihan 1, akan diminta mengisi input dan progress. setelah menginput judul dan input progress yang benar(%), judul akan langsung dimasukkan dalam list [Game_List] sebagai variabel dan tersimpan.
Sedangkan, saat menginput progress nya salah, yaitu menggunakan selain angka dan tidak di antara 0-100, sistem akan membatalkan proses dan mengembalikan tampilan menjadi menu pilihan.

# Penjelasan Pilihan 2
<img width="523" height="268" alt="Menu 2 Valid" src="https://github.com/user-attachments/assets/0dcc18d8-fde3-466a-95b6-b555547c5760" />
Saat memilih pilihan 2, program akan menampilkan list[Game_List]

# Penjelasan Pilihan 3
<img width="484" height="361" alt="Menu 3 Valid progres baru" src="https://github.com/user-attachments/assets/84d163be-b1db-4509-ad5b-e41476c6d026" />
<img width="602" height="340" alt="Menu 3 non angka" src="https://github.com/user-attachments/assets/529a2634-d2a6-40e8-9935-c5d76df45ca5" />
<img width="613" height="351" alt="Menu 3 Invalid angka not in range" src="https://github.com/user-attachments/assets/dcd363d1-b5ce-45fb-b719-d6f3a8e6e700" />
<img width="610" height="198" alt="Menu 3 Invalid, Seperti error progress pada menu 1" src="https://github.com/user-attachments/assets/78a398e7-7ca4-462b-8546-abbd70344fbd" />
Saat memilih pilihan 3, Program akan meminta untuk menginput nomor pilihan game mana yang akan di update progress nya sesuai urutan index (-1). jika input yang diisi salah(bukan angka/tidak dalam jangkauan total variabel dalam list), maka proses akan dibatalkan dan tampilan akan kembalikan ke menu pilihan.  jika input benar, akan diminta untuk mengisi input progress baru. Input Progress baru yang salah akan memiliki alur yang sama seperti saat menginput progress yang salah pada pilihan 1. Input progress baru yang benar akan menambah variael pada list sebagai "progress baru".

 # Penjelasan Pilihan 4
 <img width="598" height="351" alt="Menu 4 Valid hapus" src="https://github.com/user-attachments/assets/86444401-c1ec-4583-8b13-8186e7f3f830" />
<img width="619" height="363" alt="Menu 4 Invalid, seperti error input pada menu 3" src="https://github.com/user-attachments/assets/c123ea9c-55c2-4fea-9c5a-024c78e2f10d" />
Saat memilih pilihan 4,  Program akan meminta untuk menginput nomor pilihan game mana yang akan di hapus(.pop) sesuai urutan index (-1). jika input yang diisi salah(bukan angka/tidak dalam jangkauan total variabel dalam list), maka proses akan dibatalkan dan tampilan akan kembalikan ke menu pilihan. Jika input benar, maka program akan mengapus(.pop) game pada list [Game_List] dan menjadi bagian dari variabel pada list [game_terhapus]. 

# Penjelasan Pilihan 5 
<img width="854" height="205" alt="Menu 5, break" src="https://github.com/user-attachments/assets/ebf01dc6-b20d-471a-8f46-e753dd7bb285" />






