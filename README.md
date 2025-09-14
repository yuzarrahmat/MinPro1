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
