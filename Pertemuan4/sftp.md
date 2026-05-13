# Migrasi Data Lokal ke Cloud SFTP dan Manajemen Hak Akses Web

1. Unduh dan Install FileZilla di https://filezilla-project.org/
2. Running Instance EC2 di AWS (instance -> start Instance)
3. Buka FileZilla dan masukkan data berikut:
    - Host: [IP_ADDRESS]
    - Username: ubuntu
    - Password: [PASSWORD]
    - Port: 22
    - Klik Connect
![alt text]({8E4E50C0-1D49-4018-9035-D80DF54ACDA2}.png)
![alt text]({F2403E9D-6847-4479-B63B-062A6BDB5AD5}.png)
4. Remote SSH via PowerShell Windows
    - masuk folder penyimpanan private key
    - open with -> powershell
    - masukan command (ssh -i nama file-Private-Key.pem ubuntu@[IP_ADDRESS])
5. DIrectori Folder Cloud arahakan ke Folder Web Services Area
    - Keluar dari directori /home/ubuntu
    - Masuk ke direktori /var/www/html
    - buka file index.html dengan code editor
    - akan gagal melakukan editing - Permission denied
    - karena kita masuk user ubuntu tidak punya akses untuk write
6. Ubah Hak Akses Folder Web Services Area
    - ke Terminal PowerShell
    - masukan command (sudo chown -R ubuntu:ubuntu /var/www/html)
    - cek kembali hak akses folder dengan command (ls -l /var/www/html)

![alt text]({F84B8144-78B7-4D20-9D26-80C57240E67C}.png)
![alt text]({516B4BEB-B24E-4D43-AB9E-572E238C2689}.png)

7. kita lakukan editing di file index.html setelah hak akses folder sudah diubah
![alt text]({8AACADC5-6FC2-490B-B486-10C7F14FD538}.png)
8. Pastikan Design Responsive 
![alt text]({0FEFB0BF-F838-4CE9-B319-7E8112C52EA8}.png)