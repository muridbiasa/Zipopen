
import zipfile
import itertools
# Buka file zip yang terkunci
with zipfile.ZipFile("file.zip", "r") as zip_file:
    # Buat daftar kata sandi
    passwords = ["password", "123456", "qwerty"]
    # Cari kata sandi yang cocok
    for password in passwords:
        try:
            zip_file.extractall(pwd=password.encode())
            print("Kata sandi yang cocok:", password)
            break
        except:
            pass
    # Jika tidak ditemukan kata sandi yang cocok
    else:
        print("Kata sandi tidak ditemukan.")
